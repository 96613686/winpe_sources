# PoolNotify::Start(ulong)

- ea: `0x1400032dc`
- end: `0x140003401`
- name: `?Start@PoolNotify@@QEAAKK@Z`
- size: `293`
- prototype: `__int64 __fastcall(HANDLE *lpThreadId)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002868`

## callees

- `0x1400032dc`

## import_xrefs

- `KERNEL32!CreateThread` at `0x140003338`
- `KERNEL32!CreateThread` at `0x140003338`
- `KERNEL32!WaitForMultipleObjects` at `0x140003378`
- `KERNEL32!WaitForMultipleObjects` at `0x140003378`
- `KERNEL32!ResetEvent` at `0x1400033e2`
- `KERNEL32!ResetEvent` at `0x1400033e2`
- `KERNEL32!CloseHandle` at `0x1400033c5`
- `KERNEL32!CloseHandle` at `0x1400033c5`
- `KERNEL32!GetLastError` at `0x14000334a`
- `KERNEL32!GetLastError` at `0x14000334a`
- `KERNEL32!WaitForSingleObject` at `0x1400033bb`
- `KERNEL32!WaitForSingleObject` at `0x1400033bb`
- `USER32!PostThreadMessageW` at `0x1400033ae`
- `USER32!PostThreadMessageW` at `0x1400033ae`

## pseudocode

```c
__int64 __fastcall PoolNotify::Start(HANDLE *lpThreadId)
{
  LPDWORD v2; // rdi
  DWORD LastError; // esi
  HANDLE Thread; // rax
  void *v5; // rcx
  HANDLE v6; // rax
  HANDLE v8; // rcx
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( lpThreadId[2] && *((_DWORD *)lpThreadId + 20) )
  {
    v2 = (LPDWORD)(lpThreadId + 4);
    if ( *((_DWORD *)lpThreadId + 8) )
    {
      LastError = 1281;
    }
    else
    {
      *((_DWORD *)lpThreadId + 21) = 300;
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)PoolNotify::PnpThread, lpThreadId, 0, (LPDWORD)lpThreadId);
      lpThreadId[1] = Thread;
      v5 = Thread;
      if ( Thread )
      {
        v6 = lpThreadId[2];
        Handles[1] = v5;
        *v2 = 1;
        Handles[0] = v6;
        if ( !WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
          return 0;
        LastError = 1460;
      }
      else
      {
        LastError = GetLastError();
      }
    }
  }
  else
  {
    LastError = 8;
    v2 = (LPDWORD)(lpThreadId + 4);
  }
  if ( *v2 && lpThreadId[1] )
  {
    PostThreadMessageW(*(_DWORD *)lpThreadId, 0x12u, 0, 0);
    WaitForSingleObject(lpThreadId[1], 0xFFFFFFFF);
    CloseHandle(lpThreadId[1]);
    lpThreadId[1] = 0;
    *(_DWORD *)lpThreadId = 0;
  }
  v8 = lpThreadId[2];
  if ( v8 )
    ResetEvent(v8);
  *((_DWORD *)lpThreadId + 22) = 0;
  return LastError;
}

```

## disassembly

```asm
0x1400032dc  mov     [rsp+arg_0], rbx
0x1400032e1  mov     [rsp+arg_8], rsi
0x1400032e6  push    rdi
0x1400032e7  sub     rsp, 40h
0x1400032eb  cmp     qword ptr [rcx+10h], 0
0x1400032f0  mov     rbx, rcx
0x1400032f3  jz      loc_14000338D
0x1400032f9  cmp     dword ptr [rcx+50h], 0
0x1400032fd  jz      loc_14000338D
0x140003303  lea     rdi, [rcx+20h]
0x140003307  cmp     dword ptr [rdi], 0
0x14000330a  jz      short loc_140003316
0x14000330c  mov     esi, 501h
0x140003311  jmp     loc_140003396
0x140003316  mov     dword ptr [rcx+54h], 12Ch
0x14000331d  lea     r8, ?PnpThread@PoolNotify@@CAKPEAX@Z; lpStartAddress
0x140003324  xor     ecx, ecx; lpThreadAttributes
0x140003326  mov     [rsp+48h+lpThreadId], rbx; lpThreadId
0x14000332b  mov     r9, rbx; lpParameter
0x14000332e  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x140003336  xor     edx, edx; dwStackSize
0x140003338  call    cs:__imp_CreateThread
0x14000333e  mov     [rbx+8], rax
0x140003342  mov     rcx, rax
0x140003345  test    rax, rax
0x140003348  jnz     short loc_140003354
0x14000334a  call    cs:__imp_GetLastError
0x140003350  mov     esi, eax
0x140003352  jmp     short loc_140003396
0x140003354  mov     rax, [rbx+10h]
0x140003358  lea     rdx, [rsp+48h+Handles]; lpHandles
0x14000335d  xor     r8d, r8d; bWaitAll
0x140003360  mov     [rsp+48h+var_10], rcx
0x140003365  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140003369  mov     dword ptr [rdi], 1
0x14000336f  mov     [rsp+48h+Handles], rax
0x140003374  lea     ecx, [r8+2]; nCount
0x140003378  call    cs:__imp_WaitForMultipleObjects
0x14000337e  test    eax, eax
0x140003380  jz      short loc_140003389
0x140003382  mov     esi, 5B4h
0x140003387  jmp     short loc_140003396
0x140003389  xor     eax, eax
0x14000338b  jmp     short loc_1400033F1
0x14000338d  mov     esi, 8
0x140003392  lea     rdi, [rcx+20h]
0x140003396  cmp     dword ptr [rdi], 0
0x140003399  jz      short loc_1400033D9
0x14000339b  cmp     qword ptr [rbx+8], 0
0x1400033a0  jz      short loc_1400033D9
0x1400033a2  mov     ecx, [rbx]; idThread
0x1400033a4  xor     r9d, r9d; lParam
0x1400033a7  xor     r8d, r8d; wParam
0x1400033aa  lea     edx, [r9+12h]; Msg
0x1400033ae  call    cs:__imp_PostThreadMessageW
0x1400033b4  mov     rcx, [rbx+8]; hHandle
0x1400033b8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400033bb  call    cs:__imp_WaitForSingleObject
0x1400033c1  mov     rcx, [rbx+8]; hObject
0x1400033c5  call    cs:__imp_CloseHandle
0x1400033cb  mov     qword ptr [rbx+8], 0
0x1400033d3  mov     dword ptr [rbx], 0
0x1400033d9  mov     rcx, [rbx+10h]; hEvent
0x1400033dd  test    rcx, rcx
0x1400033e0  jz      short loc_1400033E8
0x1400033e2  call    cs:__imp_ResetEvent
0x1400033e8  mov     dword ptr [rbx+58h], 0
0x1400033ef  mov     eax, esi
0x1400033f1  mov     rbx, [rsp+48h+arg_0]
0x1400033f6  mov     rsi, [rsp+48h+arg_8]
0x1400033fb  add     rsp, 40h
0x1400033ff  pop     rdi
0x140003400  retn
```
