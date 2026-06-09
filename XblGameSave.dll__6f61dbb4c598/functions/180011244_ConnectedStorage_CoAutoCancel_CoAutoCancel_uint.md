# ConnectedStorage::CoAutoCancel::CoAutoCancel(uint)

- ea: `0x180011244`
- end: `0x1800112da`
- name: `??0CoAutoCancel@ConnectedStorage@@QEAA@I@Z`
- size: `150`
- prototype: `void **__fastcall(void **Parameter, DWORD DueTime)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016a40`
- `0x180019540`
- `0x180019660`
- `0x1800261d0`
- `0x180035e20`
- `0x18004ae14`
- `0x18004c830`
- `0x18004c8b0`
- `0x18004c900`
- `0x18005e8e4`
- `0x18006d2a0`
- `0x18006d4ec`
- `0x18006d74c`
- `0x18006d9b0`
- `0x18006dbf0`
- `0x18006dd64`
- `0x18006de64`
- `0x180076968`

## callees

- `0x18000ab18`
- `0x180011244`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011276`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ac`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180011263`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180011263`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800112a2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800112a2`

## string_xrefs

- `0x1800112be`: `Failed to create timer queue timer`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void **__fastcall ConnectedStorage::CoAutoCancel::CoAutoCancel(void **Parameter, DWORD DueTime)
{
  int LastError; // eax
  const unsigned __int16 *v5; // r8
  const wchar_t *v6; // rdx

  *Parameter = 0;
  *((_DWORD *)Parameter + 2) = 0;
  LastError = CoEnableCallCancellation(0);
  if ( LastError < 0 )
  {
    v6 = L"CoEnableCallCancellation";
LABEL_7:
    ConnectedStorage::ReportErrorNoThrow((ConnectedStorage *)(unsigned int)LastError, (int)v6, v5);
    return Parameter;
  }
  *((_DWORD *)Parameter + 2) = GetCurrentThreadId();
  if ( !CreateTimerQueueTimer(Parameter, 0, ConnectedStorage::CoAutoCancel::TimerCallback, Parameter, DueTime, 0, 8u) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = (const wchar_t *)L"Failed to create timer queue timer";
    goto LABEL_7;
  }
  return Parameter;
}

```

## disassembly

```asm
0x180011244  mov     [rsp+arg_0], rbx
0x180011249  push    rdi
0x18001124a  sub     rsp, 40h
0x18001124e  mov     rbx, rcx
0x180011251  mov     qword ptr [rcx], 0
0x180011258  mov     dword ptr [rcx+8], 0
0x18001125f  mov     edi, edx
0x180011261  xor     ecx, ecx; pReserved
0x180011263  call    cs:__imp_CoEnableCallCancellation
0x180011269  test    eax, eax
0x18001126b  jns     short loc_180011276
0x18001126d  lea     rdx, aCoenablecallca; "CoEnableCallCancellation"
0x180011274  jmp     short loc_1800112C5
0x180011276  call    cs:__imp_GetCurrentThreadId
0x18001127c  mov     [rsp+48h+Flags], 8; Flags
0x180011284  lea     r8, ?TimerCallback@CoAutoCancel@ConnectedStorage@@SAXPEAXE@Z; Callback
0x18001128b  mov     [rsp+48h+Period], 0; Period
0x180011293  mov     r9, rbx; Parameter
0x180011296  xor     edx, edx; TimerQueue
0x180011298  mov     [rbx+8], eax
0x18001129b  mov     rcx, rbx; phNewTimer
0x18001129e  mov     [rsp+48h+DueTime], edi; DueTime
0x1800112a2  call    cs:__imp_CreateTimerQueueTimer
0x1800112a8  test    eax, eax
0x1800112aa  jnz     short loc_1800112CC
0x1800112ac  call    cs:__imp_GetLastError
0x1800112b2  test    eax, eax
0x1800112b4  jle     short loc_1800112BE
0x1800112b6  movzx   eax, ax
0x1800112b9  or      eax, 80070000h
0x1800112be  lea     rdx, aFailedToCreate; "Failed to create timer queue timer"
0x1800112c5  mov     ecx, eax; this
0x1800112c7  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x1800112cc  mov     rax, rbx
0x1800112cf  mov     rbx, [rsp+48h+arg_0]
0x1800112d4  add     rsp, 40h
0x1800112d8  pop     rdi
0x1800112d9  retn
```
