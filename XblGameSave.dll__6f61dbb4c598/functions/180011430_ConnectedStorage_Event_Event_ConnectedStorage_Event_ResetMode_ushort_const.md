# ConnectedStorage::Event::Event(ConnectedStorage::Event::ResetMode,ushort const *)

- ea: `0x180011430`
- end: `0x180011483`
- name: `??0Event@ConnectedStorage@@QEAA@W4ResetMode@01@PEBG@Z`
- size: `83`
- prototype: `_QWORD *__fastcall(_QWORD *, int, const WCHAR *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800036a0`
- `0x180003750`
- `0x18001005c`
- `0x180011504`
- `0x180066db4`
- `0x180076b5c`

## callees

- `0x18000aae4`
- `0x180011430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011459`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001144b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001144b`

## string_xrefs

- `0x18001146b`: `Event: CreateEvent failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall ConnectedStorage::Event::Event(_QWORD *a1, int a2, const WCHAR *a3)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  const unsigned __int16 *v6; // r8

  EventW = CreateEventW(0, a2 == 1, 0, a3);
  *a1 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)LastError,
      (int)L"Event: CreateEvent failed",
      v6);
  }
  return a1;
}

```

## disassembly

```asm
0x180011430  push    rbx
0x180011432  sub     rsp, 20h
0x180011436  xor     eax, eax
0x180011438  mov     rbx, rcx
0x18001143b  cmp     edx, 1
0x18001143e  mov     r9, r8; lpName
0x180011441  setz    al
0x180011444  xor     r8d, r8d; bInitialState
0x180011447  mov     edx, eax; bManualReset
0x180011449  xor     ecx, ecx; lpEventAttributes
0x18001144b  call    cs:__imp_CreateEventW
0x180011451  mov     [rbx], rax
0x180011454  test    rax, rax
0x180011457  jnz     short loc_18001147A
0x180011459  call    cs:__imp_GetLastError
0x18001145f  test    eax, eax
0x180011461  jle     short loc_18001146B
0x180011463  movzx   eax, ax
0x180011466  or      eax, 80070000h
0x18001146b  lea     rdx, aEventCreateeve; "Event: CreateEvent failed"
0x180011472  mov     ecx, eax; this
0x180011474  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18001147a  mov     rax, rbx
0x18001147d  add     rsp, 20h
0x180011481  pop     rbx
0x180011482  retn
```
