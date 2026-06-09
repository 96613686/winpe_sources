# Windows::Networking::UX::Internal::CCertItemInfo::~CCertItemInfo(void)

- ea: `0x18006a380`
- end: `0x18006a402`
- name: `??1CCertItemInfo@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `130`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CCertItemInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006a440`

## callees

- `0x18000bb9c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a38d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a39f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a3d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a3e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a38d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a39f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a3d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a3e7`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CCertItemInfo::~CCertItemInfo(HSTRING *this)
{
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>(this);
}

```

## disassembly

```asm
0x18006a380  push    rbx
0x18006a382  sub     rsp, 20h
0x18006a386  mov     rbx, rcx
0x18006a389  mov     rcx, [rcx+50h]; string
0x18006a38d  call    cs:__imp_WindowsDeleteString
0x18006a393  mov     qword ptr [rbx+50h], 0
0x18006a39b  mov     rcx, [rbx+48h]; string
0x18006a39f  call    cs:__imp_WindowsDeleteString
0x18006a3a5  mov     qword ptr [rbx+48h], 0
0x18006a3ad  mov     rcx, [rbx+40h]; string
0x18006a3b1  call    cs:__imp_WindowsDeleteString
0x18006a3b7  mov     qword ptr [rbx+40h], 0
0x18006a3bf  mov     rcx, [rbx+38h]; string
0x18006a3c3  call    cs:__imp_WindowsDeleteString
0x18006a3c9  mov     qword ptr [rbx+38h], 0
0x18006a3d1  mov     rcx, [rbx+30h]; string
0x18006a3d5  call    cs:__imp_WindowsDeleteString
0x18006a3db  mov     qword ptr [rbx+30h], 0
0x18006a3e3  mov     rcx, [rbx+28h]; string
0x18006a3e7  call    cs:__imp_WindowsDeleteString
0x18006a3ed  mov     rcx, rbx
0x18006a3f0  mov     qword ptr [rbx+28h], 0
0x18006a3f8  add     rsp, 20h
0x18006a3fc  pop     rbx
0x18006a3fd  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@U_GUID@@PEAUIAvailableNetwork@UX@Networking@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>(void)
```
