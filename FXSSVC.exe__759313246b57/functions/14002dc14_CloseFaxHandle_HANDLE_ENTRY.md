# CloseFaxHandle(_HANDLE_ENTRY *)

- ea: `0x14002dc14`
- end: `0x14002de69`
- name: `?CloseFaxHandle@@YAXPEAU_HANDLE_ENTRY@@@Z`
- size: `597`
- prototype: `void __fastcall(struct _HANDLE_ENTRY *lpMem)`
- caller_count: `12`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140017310`
- `0x1400173d0`
- `0x140017650`
- `0x140017a60`
- `0x140017b10`
- `0x140023430`
- `0x1400235d0`
- `0x140023660`
- `0x140023710`
- `0x14002de70`
- `0x14002e090`
- `0x140049678`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14002dc14`
- `0x1400399f0`
- `0x14003fda0`
- `0x14006998c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002dcf7`
- `KERNEL32!GetLastError` at `0x14002dd5c`
- `KERNEL32!GetLastError` at `0x14002ddad`
- `KERNEL32!GetLastError` at `0x14002dcf7`
- `KERNEL32!GetLastError` at `0x14002dd5c`
- `KERNEL32!GetLastError` at `0x14002ddad`
- `KERNEL32!CloseHandle` at `0x14002dd34`
- `KERNEL32!CloseHandle` at `0x14002dd34`
- `KERNEL32!FindClose` at `0x14002dcbf`
- `KERNEL32!FindClose` at `0x14002dcbf`
- `KERNEL32!DeleteFileW` at `0x14002dd9d`
- `KERNEL32!DeleteFileW` at `0x14002dd9d`
- `KERNEL32!EnterCriticalSection` at `0x14002dc62`
- `KERNEL32!EnterCriticalSection` at `0x14002de08`
- `KERNEL32!EnterCriticalSection` at `0x14002dc62`
- `KERNEL32!EnterCriticalSection` at `0x14002de08`
- `KERNEL32!LeaveCriticalSection` at `0x14002de32`
- `KERNEL32!LeaveCriticalSection` at `0x14002de32`
- `KERNEL32!LeaveCriticalSection` at `0x14002de5d`

## pseudocode

```c
void __fastcall CloseFaxHandle(struct _HANDLE_ENTRY *lpMem)
{
  _QWORD *v2; // rax
  __int64 v3; // rcx
  int v4; // eax
  void *v5; // rcx
  DWORD LastError; // eax
  DWORD v7; // eax
  char v8; // al

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids);
  }
  EnterCriticalSection(&g_CsHandleTable);
  v2 = (_QWORD *)*((_QWORD *)lpMem + 1);
  v3 = *(_QWORD *)lpMem;
  *v2 = *(_QWORD *)lpMem;
  *(_QWORD *)(v3 + 8) = v2;
  v4 = *((_DWORD *)lpMem + 6);
  *(_QWORD *)lpMem = 0;
  *((_QWORD *)lpMem + 1) = 0;
  if ( !v4 )
  {
    if ( !*((_DWORD *)lpMem + 11) )
      SafeDecIdleCounter(&g_dwConnectionCount);
    goto LABEL_31;
  }
  if ( v4 == 2 )
  {
    v5 = (void *)*((_QWORD *)lpMem + 7);
    if ( v5 != (void *)-1LL
      && !FindClose(v5)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids, LastError);
    }
    goto LABEL_31;
  }
  if ( v4 != 3 )
    goto LABEL_31;
  if ( !CloseHandle(*((HANDLE *)lpMem + 7))
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids, v7);
  }
  if ( !*((_DWORD *)lpMem + 408) )
    goto LABEL_28;
  if ( *((_DWORD *)lpMem + 407) )
  {
    if ( !DeleteFileW((LPCWSTR)lpMem + 32) )
    {
      v8 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)&WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids,
          (_DWORD)lpMem + 64,
          v8);
      }
    }
LABEL_28:
    if ( *((_DWORD *)lpMem + 407) )
      goto LABEL_31;
  }
  if ( *((_QWORD *)lpMem + 205) )
  {
    EnterCriticalSection(&g_CsQueue);
    DecreaseJobRefCount(*((struct _JOB_QUEUE **)lpMem + 205), 1, 1, 1);
    LeaveCriticalSection(&g_CsQueue);
  }
LABEL_31:
  pMemFree(lpMem);
  LeaveCriticalSection(&g_CsHandleTable);
}

```

## disassembly

```asm
0x14002dc14  mov     [rsp+arg_0], rbx
0x14002dc19  mov     [rsp+arg_8], rdi
0x14002dc1e  push    r14
0x14002dc20  sub     rsp, 30h
0x14002dc24  mov     rbx, rcx
0x14002dc27  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dc2e  lea     r14, WPP_GLOBAL_Control
0x14002dc35  cmp     rcx, r14
0x14002dc38  jz      short loc_14002DC5B
0x14002dc3a  test    byte ptr [rcx+1Ch], 4
0x14002dc3e  jz      short loc_14002DC5B
0x14002dc40  cmp     byte ptr [rcx+19h], 5
0x14002dc44  jb      short loc_14002DC5B
0x14002dc46  mov     rcx, [rcx+10h]
0x14002dc4a  lea     r8, WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids
0x14002dc51  mov     edx, 14h
0x14002dc56  call    WPP_SF_
0x14002dc5b  lea     rcx, ?g_CsHandleTable@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002dc62  call    cs:__imp_EnterCriticalSection
0x14002dc69  nop     dword ptr [rax+rax+00h]
0x14002dc6e  mov     rax, [rbx+8]
0x14002dc72  mov     rcx, [rbx]
0x14002dc75  mov     [rax], rcx
0x14002dc78  mov     [rcx+8], rax
0x14002dc7c  mov     eax, [rbx+18h]
0x14002dc7f  mov     qword ptr [rbx], 0
0x14002dc86  mov     qword ptr [rbx+8], 0
0x14002dc8e  test    eax, eax
0x14002dc90  jnz     short loc_14002DCAC
0x14002dc92  cmp     [rbx+2Ch], eax
0x14002dc95  jnz     loc_14002DE3E
0x14002dc9b  lea     rcx, ?g_dwConnectionCount@@3KA; unsigned int *
0x14002dca2  call    ?SafeDecIdleCounter@@YAXPEAK@Z; SafeDecIdleCounter(ulong *)
0x14002dca7  jmp     loc_14002DE3E
0x14002dcac  cmp     eax, 2
0x14002dcaf  jnz     short loc_14002DD27
0x14002dcb1  mov     rcx, [rbx+38h]; hFindFile
0x14002dcb5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002dcb9  jz      loc_14002DE3E
0x14002dcbf  call    cs:__imp_FindClose
0x14002dcc6  nop     dword ptr [rax+rax+00h]
0x14002dccb  test    eax, eax
0x14002dccd  jnz     loc_14002DE3E
0x14002dcd3  mov     rax, cs:WPP_GLOBAL_Control
0x14002dcda  cmp     rax, r14
0x14002dcdd  jz      loc_14002DE3E
0x14002dce3  test    byte ptr [rax+1Ch], 4
0x14002dce7  jz      loc_14002DE3E
0x14002dced  cmp     byte ptr [rax+19h], 2
0x14002dcf1  jb      loc_14002DE3E
0x14002dcf7  call    cs:__imp_GetLastError
0x14002dcfe  nop     dword ptr [rax+rax+00h]
0x14002dd03  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dd0a  lea     r8, WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids
0x14002dd11  mov     edx, 15h
0x14002dd16  mov     r9d, eax
0x14002dd19  mov     rcx, [rcx+10h]
0x14002dd1d  call    WPP_SF_d
0x14002dd22  jmp     loc_14002DE3E
0x14002dd27  cmp     eax, 3
0x14002dd2a  jnz     loc_14002DE3E
0x14002dd30  mov     rcx, [rbx+38h]; hObject
0x14002dd34  call    cs:__imp_CloseHandle
0x14002dd3b  nop     dword ptr [rax+rax+00h]
0x14002dd40  test    eax, eax
0x14002dd42  jnz     short loc_14002DD87
0x14002dd44  mov     rax, cs:WPP_GLOBAL_Control
0x14002dd4b  cmp     rax, r14
0x14002dd4e  jz      short loc_14002DD87
0x14002dd50  test    byte ptr [rax+1Ch], 4
0x14002dd54  jz      short loc_14002DD87
0x14002dd56  cmp     byte ptr [rax+19h], 2
0x14002dd5a  jb      short loc_14002DD87
0x14002dd5c  call    cs:__imp_GetLastError
0x14002dd63  nop     dword ptr [rax+rax+00h]
0x14002dd68  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dd6f  lea     r8, WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids
0x14002dd76  mov     edx, 16h
0x14002dd7b  mov     r9d, eax
0x14002dd7e  mov     rcx, [rcx+10h]
0x14002dd82  call    WPP_SF_d
0x14002dd87  cmp     dword ptr [rbx+660h], 0
0x14002dd8e  jz      short loc_14002DDEE
0x14002dd90  cmp     dword ptr [rbx+65Ch], 0
0x14002dd97  jz      short loc_14002DDF7
0x14002dd99  lea     rcx, [rbx+40h]; lpFileName
0x14002dd9d  call    cs:__imp_DeleteFileW
0x14002dda4  nop     dword ptr [rax+rax+00h]
0x14002dda9  test    eax, eax
0x14002ddab  jnz     short loc_14002DDEE
0x14002ddad  call    cs:__imp_GetLastError
0x14002ddb4  nop     dword ptr [rax+rax+00h]
0x14002ddb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ddc0  cmp     rcx, r14
0x14002ddc3  jz      short loc_14002DDEE
0x14002ddc5  test    byte ptr [rcx+1Ch], 4
0x14002ddc9  jz      short loc_14002DDEE
0x14002ddcb  cmp     byte ptr [rcx+19h], 2
0x14002ddcf  jb      short loc_14002DDEE
0x14002ddd1  mov     rcx, [rcx+10h]
0x14002ddd5  lea     r9, [rbx+40h]
0x14002ddd9  mov     edx, 17h
0x14002ddde  mov     [rsp+38h+var_18], eax
0x14002dde2  lea     r8, WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids
0x14002dde9  call    WPP_SF_Sd
0x14002ddee  cmp     dword ptr [rbx+65Ch], 0
0x14002ddf5  jnz     short loc_14002DE3E
0x14002ddf7  cmp     qword ptr [rbx+668h], 0
0x14002ddff  jz      short loc_14002DE3E
0x14002de01  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002de08  call    cs:__imp_EnterCriticalSection
0x14002de0f  nop     dword ptr [rax+rax+00h]
0x14002de14  mov     rcx, [rbx+668h]; struct _JOB_QUEUE *
0x14002de1b  mov     edx, 1; int
0x14002de20  mov     r9d, edx; int
0x14002de23  mov     r8d, edx; int
0x14002de26  call    ?DecreaseJobRefCount@@YAXPEAU_JOB_QUEUE@@HHH@Z; DecreaseJobRefCount(_JOB_QUEUE *,int,int,int)
0x14002de2b  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002de32  call    cs:__imp_LeaveCriticalSection
0x14002de39  nop     dword ptr [rax+rax+00h]
0x14002de3e  mov     rcx, rbx; lpMem
0x14002de41  call    pMemFree
0x14002de46  lea     rcx, ?g_CsHandleTable@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CsHandleTable
0x14002de4d  mov     rbx, [rsp+38h+arg_0]
0x14002de52  mov     rdi, [rsp+38h+arg_8]
0x14002de57  add     rsp, 30h
0x14002de5b  pop     r14
0x14002de5d  jmp     cs:__imp_LeaveCriticalSection
```
