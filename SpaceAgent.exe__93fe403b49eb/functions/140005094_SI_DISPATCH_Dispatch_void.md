# SI_DISPATCH::Dispatch(void)

- ea: `0x140005094`
- end: `0x14000515c`
- name: `?Dispatch@SI_DISPATCH@@QEAAHXZ`
- size: `200`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000cdc8`

## callees

- `0x140005094`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x1400050d2`
- `ADVAPI32!OpenThreadToken` at `0x1400050d2`
- `KERNEL32!CreateThreadpoolWork` at `0x140005106`
- `KERNEL32!CreateThreadpoolWork` at `0x140005106`
- `KERNEL32!SubmitThreadpoolWork` at `0x14000512e`
- `KERNEL32!SubmitThreadpoolWork` at `0x14000512e`
- `KERNEL32!SetLastError` at `0x1400050ed`
- `KERNEL32!SetLastError` at `0x1400050ed`
- `KERNEL32!GetLastError` at `0x1400050de`
- `KERNEL32!GetLastError` at `0x1400050de`
- `KERNEL32!CloseThreadpoolWork` at `0x14000514b`
- `KERNEL32!CloseThreadpoolWork` at `0x14000514b`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x140005142`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x140005142`
- `KERNEL32!GetCurrentThread` at `0x1400050bd`
- `KERNEL32!GetCurrentThread` at `0x1400050bd`

## pseudocode

```c
__int64 __fastcall SI_DISPATCH::Dispatch(PVOID pv)
{
  _QWORD *v1; // rax
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  struct _TP_WORK *ThreadpoolWork; // rbp
  _QWORD *v6; // rcx
  _QWORD *v7; // rsi

  v1 = (_QWORD *)*((_QWORD *)pv + 1);
  v3 = 1;
  if ( v1 && (_QWORD *)*v1 != v1 )
  {
    CurrentThread = GetCurrentThread();
    v3 = OpenThreadToken(CurrentThread, 0x2000Cu, 0, (PHANDLE)pv + 7);
    if ( !v3 )
    {
      if ( GetLastError() != 1008 )
        return v3;
      SetLastError(0);
      v3 = 1;
    }
    ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)SI_DISPATCH::Callback, pv, &ThreadpoolEnv);
    if ( ThreadpoolWork )
    {
      v6 = (_QWORD *)*((_QWORD *)pv + 1);
      *((_QWORD *)pv + 6) = *v6;
      v7 = (_QWORD *)*v6;
      if ( (_QWORD *)*v6 != v6 )
      {
        do
        {
          SubmitThreadpoolWork(ThreadpoolWork);
          v7 = (_QWORD *)*v7;
        }
        while ( v7 != *((_QWORD **)pv + 1) );
      }
      WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
      CloseThreadpoolWork(ThreadpoolWork);
    }
    else
    {
      return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140005094  push    rbx
0x140005096  push    rbp
0x140005097  push    rsi
0x140005098  push    rdi
0x140005099  sub     rsp, 28h
0x14000509d  mov     rax, [rcx+8]
0x1400050a1  mov     esi, 1
0x1400050a6  mov     rdi, rcx
0x1400050a9  mov     ebx, esi
0x1400050ab  test    rax, rax
0x1400050ae  jz      loc_140005151
0x1400050b4  cmp     [rax], rax
0x1400050b7  jz      loc_140005151
0x1400050bd  call    cs:__imp_GetCurrentThread
0x1400050c3  lea     r9, [rdi+38h]; TokenHandle
0x1400050c7  xor     r8d, r8d; OpenAsSelf
0x1400050ca  mov     rcx, rax; ThreadHandle
0x1400050cd  mov     edx, 2000Ch; DesiredAccess
0x1400050d2  call    cs:__imp_OpenThreadToken
0x1400050d8  mov     ebx, eax
0x1400050da  test    eax, eax
0x1400050dc  jnz     short loc_1400050F5
0x1400050de  call    cs:__imp_GetLastError
0x1400050e4  cmp     eax, 3F0h
0x1400050e9  jnz     short loc_140005151
0x1400050eb  xor     ecx, ecx; dwErrCode
0x1400050ed  call    cs:__imp_SetLastError
0x1400050f3  mov     ebx, esi
0x1400050f5  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1400050fc  mov     rdx, rdi; pv
0x1400050ff  lea     rcx, ?Callback@SI_DISPATCH@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x140005106  call    cs:__imp_CreateThreadpoolWork
0x14000510c  mov     rbp, rax
0x14000510f  test    rax, rax
0x140005112  jnz     short loc_140005118
0x140005114  xor     ebx, ebx
0x140005116  jmp     short loc_140005151
0x140005118  mov     rcx, [rdi+8]
0x14000511c  mov     rax, [rcx]
0x14000511f  mov     [rdi+30h], rax
0x140005123  mov     rsi, [rcx]
0x140005126  cmp     rsi, rcx
0x140005129  jz      short loc_14000513D
0x14000512b  mov     rcx, rbp; pwk
0x14000512e  call    cs:__imp_SubmitThreadpoolWork
0x140005134  mov     rsi, [rsi]
0x140005137  cmp     rsi, [rdi+8]
0x14000513b  jnz     short loc_14000512B
0x14000513d  xor     edx, edx; fCancelPendingCallbacks
0x14000513f  mov     rcx, rbp; pwk
0x140005142  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x140005148  mov     rcx, rbp; pwk
0x14000514b  call    cs:__imp_CloseThreadpoolWork
0x140005151  mov     eax, ebx
0x140005153  add     rsp, 28h
0x140005157  pop     rdi
0x140005158  pop     rsi
0x140005159  pop     rbp
0x14000515a  pop     rbx
0x14000515b  retn
```
