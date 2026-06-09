# Windows::Networking::UX::Internal::AvailableNetworkProviderBase::~AvailableNetworkProviderBase(void)

- ea: `0x180085a94`
- end: `0x180085ae3`
- name: `??1AvailableNetworkProviderBase@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::AvailableNetworkProviderBase *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800635c4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085acf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085acf`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::AvailableNetworkProviderBase::~AvailableNetworkProviderBase(
        HSTRING *this)
{
  *this = (HSTRING)&Windows::Networking::UX::Internal::AvailableNetworkProviderBase::`vftable';
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
}

```

## disassembly

```asm
0x180085a94  push    rbx
0x180085a96  sub     rsp, 20h
0x180085a9a  lea     rax, ??_7AvailableNetworkProviderBase@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::AvailableNetworkProviderBase::`vftable'
0x180085aa1  mov     rbx, rcx
0x180085aa4  mov     [rcx], rax
0x180085aa7  mov     rcx, [rcx+20h]; string
0x180085aab  call    cs:__imp_WindowsDeleteString
0x180085ab1  mov     qword ptr [rbx+20h], 0
0x180085ab9  mov     rcx, [rbx+18h]; string
0x180085abd  call    cs:__imp_WindowsDeleteString
0x180085ac3  mov     qword ptr [rbx+18h], 0
0x180085acb  mov     rcx, [rbx+10h]; string
0x180085acf  call    cs:__imp_WindowsDeleteString
0x180085ad5  mov     qword ptr [rbx+10h], 0
0x180085add  add     rsp, 20h
0x180085ae1  pop     rbx
0x180085ae2  retn
```
