# WinStoreAuth::TicketHolder::~TicketHolder(void)

- ea: `0x180039acc`
- end: `0x180039aff`
- name: `??1TicketHolder@WinStoreAuth@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18004df3e`
- `0x18004e0a6`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ad9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039aeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ad9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039aeb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WinStoreAuth::TicketHolder::~TicketHolder(HSTRING *this)
{
  WindowsDeleteString(this[2]);
  this[2] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
}

```

## disassembly

```asm
0x180039acc  push    rbx
0x180039ace  sub     rsp, 20h
0x180039ad2  mov     rbx, rcx
0x180039ad5  mov     rcx, [rcx+10h]; string
0x180039ad9  call    cs:__imp_WindowsDeleteString
0x180039adf  mov     qword ptr [rbx+10h], 0
0x180039ae7  mov     rcx, [rbx+8]; string
0x180039aeb  call    cs:__imp_WindowsDeleteString
0x180039af1  mov     qword ptr [rbx+8], 0
0x180039af9  add     rsp, 20h
0x180039afd  pop     rbx
0x180039afe  retn
```
