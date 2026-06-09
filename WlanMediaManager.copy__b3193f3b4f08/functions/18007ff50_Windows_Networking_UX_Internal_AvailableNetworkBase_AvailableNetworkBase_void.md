# Windows::Networking::UX::Internal::AvailableNetworkBase::~AvailableNetworkBase(void)

- ea: `0x18007ff50`
- end: `0x18007ff8d`
- name: `??1AvailableNetworkBase@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::AvailableNetworkBase *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18005849c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ff67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ff79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ff67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ff79`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::AvailableNetworkBase::~AvailableNetworkBase(HSTRING *this)
{
  *this = (HSTRING)&Windows::Networking::UX::Internal::AvailableNetworkBase::`vftable';
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
}

```

## disassembly

```asm
0x18007ff50  push    rbx
0x18007ff52  sub     rsp, 20h
0x18007ff56  lea     rax, ??_7AvailableNetworkBase@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::AvailableNetworkBase::`vftable'
0x18007ff5d  mov     rbx, rcx
0x18007ff60  mov     [rcx], rax
0x18007ff63  mov     rcx, [rcx+48h]; string
0x18007ff67  call    cs:__imp_WindowsDeleteString
0x18007ff6d  mov     qword ptr [rbx+48h], 0
0x18007ff75  mov     rcx, [rbx+30h]; string
0x18007ff79  call    cs:__imp_WindowsDeleteString
0x18007ff7f  mov     qword ptr [rbx+30h], 0
0x18007ff87  add     rsp, 20h
0x18007ff8b  pop     rbx
0x18007ff8c  retn
```
