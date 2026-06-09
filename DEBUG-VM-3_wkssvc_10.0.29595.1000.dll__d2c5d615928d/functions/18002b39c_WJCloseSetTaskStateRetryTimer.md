# WJCloseSetTaskStateRetryTimer

- ea: `0x18002b39c`
- end: `0x18002b43c`
- name: `WJCloseSetTaskStateRetryTimer`
- size: `160`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001d4c0`
- `0x18001dcc0`
- `0x18002ba14`
- `0x18002bed8`

## callees

- `0x18002b39c`
- `0x18002b444`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b402`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b402`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b3eb`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b42d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b3eb`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b42d`

## string_xrefs

- `0x18002b3d1`: `WJCloseSetTaskStateRetryTimer`
- `0x18002b40c`: `WJCloseSetTaskStateRetryTimer`
- `0x18002b3e4`: `AutoJoinSvc/%s: Canceling thread pool timer to %s task "%s\%s".`
- `0x18002b417`: `AutoJoinSvc/%s: Thread pool timer to %s task "%s\%s" is cancelled.`

## pseudocode

```c
__int64 __fastcall WJCloseSetTaskStateRetryTimer(_QWORD *a1)
{
  const wchar_t *v2; // rbx
  const wchar_t *v3; // r8
  __int64 result; // rax

  if ( a1 && a1[8] )
  {
    v2 = L"enable";
    v3 = L"enable";
    if ( !*((_WORD *)a1 + 8) )
      v3 = L"disable";
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Canceling thread pool timer to %s task \"%s\\%s\".",
      L"WJCloseSetTaskStateRetryTimer",
      v3,
      *a1,
      a1[1]);
    WJCloseThreadPoolTimer((PTP_TIMER)a1[8]);
    a1[8] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 3));
    if ( !*((_WORD *)a1 + 8) )
      v2 = L"disable";
    return DsrWriteAutoJoinSvcDebugEvent(
             L"AutoJoinSvc/%s: Thread pool timer to %s task \"%s\\%s\" is cancelled.",
             L"WJCloseSetTaskStateRetryTimer",
             v2,
             *a1,
             a1[1]);
  }
  return result;
}

```

## disassembly

```asm
0x18002b39c  test    rcx, rcx
0x18002b39f  jz      locret_18002B43B
0x18002b3a5  push    rbx
0x18002b3a6  push    rbp
0x18002b3a7  push    rsi
0x18002b3a8  push    rdi
0x18002b3a9  sub     rsp, 38h
0x18002b3ad  xor     ebp, ebp
0x18002b3af  mov     rdi, rcx
0x18002b3b2  cmp     [rcx+40h], rbp
0x18002b3b6  jz      short loc_18002B433
0x18002b3b8  cmp     [rcx+10h], bp
0x18002b3bc  lea     rbx, aEnable; "enable"
0x18002b3c3  mov     rax, [rcx+8]
0x18002b3c7  lea     rsi, aDisable; "disable"
0x18002b3ce  mov     r9, [rcx]
0x18002b3d1  lea     rdx, aWjclosesettask; "WJCloseSetTaskStateRetryTimer"
0x18002b3d8  mov     r8, rbx
0x18002b3db  mov     [rsp+58h+var_38], rax
0x18002b3e0  cmovz   r8, rsi
0x18002b3e4  lea     rcx, aAutojoinsvcSCa; "AutoJoinSvc/%s: Canceling thread pool t"...
0x18002b3eb  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b3f1  mov     rcx, [rdi+40h]; pti
0x18002b3f5  call    WJCloseThreadPoolTimer
0x18002b3fa  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002b3fe  mov     [rdi+40h], rbp
0x18002b402  call    cs:__imp_DeleteCriticalSection
0x18002b408  cmp     [rdi+10h], bp
0x18002b40c  lea     rdx, aWjclosesettask; "WJCloseSetTaskStateRetryTimer"
0x18002b413  mov     rax, [rdi+8]
0x18002b417  lea     rcx, aAutojoinsvcSTh_0; "AutoJoinSvc/%s: Thread pool timer to %s"...
0x18002b41e  mov     r9, [rdi]
0x18002b421  cmovz   rbx, rsi
0x18002b425  mov     r8, rbx
0x18002b428  mov     [rsp+58h+var_38], rax
0x18002b42d  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b433  add     rsp, 38h
0x18002b437  pop     rdi
0x18002b438  pop     rsi
0x18002b439  pop     rbp
0x18002b43a  pop     rbx
0x18002b43b  retn
```
