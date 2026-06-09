# WJOpenSetTaskStateRetryTimer

- ea: `0x18002b634`
- end: `0x18002b6f4`
- name: `WJOpenSetTaskStateRetryTimer`
- size: `192`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002ba14`

## callees

- `0x18002b634`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b66d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002b690`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002b690`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b6df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b6df`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002b65b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002b65b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b6ca`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b6ca`

## string_xrefs

- `0x18002b6bc`: `WJOpenSetTaskStateRetryTimer`
- `0x18002b6c3`: `AutoJoinSvc/%s: Starting thread pool timer to retry %s task "%s\%s".`

## pseudocode

```c
__int64 __fastcall WJOpenSetTaskStateRetryTimer(char *pv, __int64 a2, __int64 a3, __int16 a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  unsigned int v9; // edi
  const wchar_t *v10; // r8
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  ThreadpoolTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)WJWorkplaceJoinTaskStateCallback, pv, 0);
  *((_QWORD *)pv + 8) = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    *(_QWORD *)pv = a2;
    v9 = 0;
    *((_QWORD *)pv + 1) = a3;
    *((_WORD *)pv + 8) = a4;
    *((_DWORD *)pv + 5) = 60;
    InitializeCriticalSection((LPCRITICAL_SECTION)(pv + 24));
    pftDueTime = (struct _FILETIME)-10000000LL;
    v10 = L"enabling";
    if ( !a4 )
      v10 = L"disabling";
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Starting thread pool timer to retry %s task \"%s\\%s\".",
      L"WJOpenSetTaskStateRetryTimer",
      v10,
      a2,
      a3);
    SetThreadpoolTimer(*((PTP_TIMER *)pv + 8), &pftDueTime, 0, 0);
  }
  else
  {
    return GetLastError();
  }
  return v9;
}

```

## disassembly

```asm
0x18002b634  push    rbx
0x18002b636  push    rbp
0x18002b637  push    rsi
0x18002b638  push    rdi
0x18002b639  push    r14
0x18002b63b  push    r15
0x18002b63d  sub     rsp, 38h
0x18002b641  mov     r14, rdx
0x18002b644  mov     rbp, r8
0x18002b647  mov     rdx, rcx; pv
0x18002b64a  mov     rbx, rcx
0x18002b64d  lea     rcx, WJWorkplaceJoinTaskStateCallback; pfnti
0x18002b654  xor     r8d, r8d; pcbe
0x18002b657  movzx   esi, r9w
0x18002b65b  call    cs:__imp_CreateThreadpoolTimer
0x18002b661  xor     r15d, r15d
0x18002b664  mov     [rbx+40h], rax
0x18002b668  test    rax, rax
0x18002b66b  jnz     short loc_18002B677
0x18002b66d  call    cs:__imp_GetLastError
0x18002b673  mov     edi, eax
0x18002b675  jmp     short loc_18002B6E5
0x18002b677  lea     rcx, [rbx+18h]; lpCriticalSection
0x18002b67b  mov     [rbx], r14
0x18002b67e  mov     edi, r15d
0x18002b681  mov     [rbx+8], rbp
0x18002b685  mov     [rbx+10h], si
0x18002b689  mov     dword ptr [rbx+14h], 3Ch ; '<'
0x18002b690  call    cs:__imp_InitializeCriticalSection
0x18002b696  lea     rax, aDisabling; "disabling"
0x18002b69d  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFF676980h
0x18002b6a6  test    si, si
0x18002b6a9  mov     [rsp+68h+var_48], rbp
0x18002b6ae  lea     r8, aEnabling; "enabling"
0x18002b6b5  mov     r9, r14
0x18002b6b8  cmovz   r8, rax
0x18002b6bc  lea     rdx, aWjopensettasks; "WJOpenSetTaskStateRetryTimer"
0x18002b6c3  lea     rcx, aAutojoinsvcSSt; "AutoJoinSvc/%s: Starting thread pool ti"...
0x18002b6ca  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b6d0  mov     rcx, [rbx+40h]; pti
0x18002b6d4  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18002b6d9  xor     r9d, r9d; msWindowLength
0x18002b6dc  xor     r8d, r8d; msPeriod
0x18002b6df  call    cs:__imp_SetThreadpoolTimer
0x18002b6e5  mov     eax, edi
0x18002b6e7  add     rsp, 38h
0x18002b6eb  pop     r15
0x18002b6ed  pop     r14
0x18002b6ef  pop     rdi
0x18002b6f0  pop     rsi
0x18002b6f1  pop     rbp
0x18002b6f2  pop     rbx
0x18002b6f3  retn
```
