# Windows::Networking::UX::UXCategoryChangedSink::~UXCategoryChangedSink(void)

- ea: `0x18003886c`
- end: `0x180038895`
- name: `??1UXCategoryChangedSink@UX@Networking@Windows@@UEAA@XZ`
- size: `41`
- prototype: `void __fastcall(Windows::Networking::UX::UXCategoryChangedSink *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038b20`

## callees

- `0x18000955c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038882`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038882`

## pseudocode

```c
void __fastcall Windows::Networking::UX::UXCategoryChangedSink::~UXCategoryChangedSink(
        Windows::Networking::UX::UXCategoryChangedSink *this)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18003886c  push    rbx
0x18003886e  sub     rsp, 20h
0x180038872  mov     rbx, rcx
0x180038875  add     rcx, 40h ; '@'
0x180038879  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003887e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180038882  call    cs:__imp_DeleteCriticalSection
0x180038888  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18003888f  add     rsp, 20h
0x180038893  pop     rbx
0x180038894  retn
```
