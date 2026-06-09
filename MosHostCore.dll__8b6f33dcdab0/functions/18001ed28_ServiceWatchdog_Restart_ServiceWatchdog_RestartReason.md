# ServiceWatchdog::Restart(ServiceWatchdog::RestartReason)

- ea: `0x18001ed28`
- end: `0x18001eda8`
- name: `?Restart@ServiceWatchdog@@QEAAXW4RestartReason@1@@Z`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800166a8`
- `0x1800184a0`
- `0x18001ac34`

## callees

- `0x18001ed28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eda1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed60`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001ed56`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001ed56`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ed8d`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ed8d`

## string_xrefs

- `0x18001ed84`: `ServiceWatchdog::Restart`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServiceWatchdog::Restart(__int64 a1, int a2)
{
  signed int LastError; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  *(_DWORD *)(a1 + 136) = a2;
  *(_BYTE *)(a1 + 156) = 0;
  if ( !QueryUnbiasedInterruptTime((PULONGLONG)(a1 + 144)) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    ZTraceReportIgnore(LastError, "ServiceWatchdog::Restart", 95, (const void *)a1);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x18001ed28  mov     [rsp+arg_8], rbx
0x18001ed2d  push    rdi
0x18001ed2e  sub     rsp, 20h
0x18001ed32  mov     ebx, edx
0x18001ed34  mov     rdi, rcx
0x18001ed37  call    cs:__imp_EnterCriticalSection
0x18001ed3d  mov     [rsp+28h+arg_0], rdi
0x18001ed42  mov     [rdi+88h], ebx
0x18001ed48  mov     byte ptr [rdi+9Ch], 0
0x18001ed4f  lea     rcx, [rdi+90h]; UnbiasedTime
0x18001ed56  call    cs:__imp_QueryUnbiasedInterruptTime
0x18001ed5c  test    eax, eax
0x18001ed5e  jnz     short loc_18001ED94
0x18001ed60  call    cs:__imp_GetLastError
0x18001ed66  test    eax, eax
0x18001ed68  jz      short loc_18001ED76
0x18001ed6a  jle     short loc_18001ED7B
0x18001ed6c  movzx   eax, ax
0x18001ed6f  or      eax, 80070000h
0x18001ed74  jmp     short loc_18001ED7B
0x18001ed76  mov     eax, 80390004h
0x18001ed7b  mov     r9, rdi
0x18001ed7e  mov     r8d, 5Fh ; '_'
0x18001ed84  lea     rdx, aServicewatchdo; "ServiceWatchdog::Restart"
0x18001ed8b  mov     ecx, eax
0x18001ed8d  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001ed93  nop
0x18001ed94  mov     rcx, rdi
0x18001ed97  mov     rbx, [rsp+28h+arg_8]
0x18001ed9c  add     rsp, 20h
0x18001eda0  pop     rdi
0x18001eda1  jmp     cs:__imp_LeaveCriticalSection
```
