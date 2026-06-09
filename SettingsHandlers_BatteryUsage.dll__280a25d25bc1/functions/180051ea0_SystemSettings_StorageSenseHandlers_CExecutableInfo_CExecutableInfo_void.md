# SystemSettings::StorageSenseHandlers::CExecutableInfo::~CExecutableInfo(void)

- ea: `0x180051ea0`
- end: `0x180051eed`
- name: `??1CExecutableInfo@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `77`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CExecutableInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051fc0`

## callees

- `0x180015848`
- `0x1800158d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051ed1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051ed1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051ead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051ebf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051ead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051ebf`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CExecutableInfo::~CExecutableInfo(
        SystemSettings::StorageSenseHandlers::CExecutableInfo *this)
{
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>((char *)this + 32);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorChangedEventArgs>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorChangedEventArgs>(this);
}

```

## disassembly

```asm
0x180051ea0  push    rbx
0x180051ea2  sub     rsp, 20h
0x180051ea6  mov     rbx, rcx
0x180051ea9  mov     rcx, [rcx+60h]; string
0x180051ead  call    cs:__imp_WindowsDeleteString
0x180051eb3  mov     qword ptr [rbx+60h], 0
0x180051ebb  mov     rcx, [rbx+58h]; string
0x180051ebf  call    cs:__imp_WindowsDeleteString
0x180051ec5  lea     rcx, [rbx+30h]; lpCriticalSection
0x180051ec9  mov     qword ptr [rbx+58h], 0
0x180051ed1  call    cs:__imp_DeleteCriticalSection
0x180051ed7  lea     rcx, [rbx+20h]
0x180051edb  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x180051ee0  mov     rcx, rbx
0x180051ee3  add     rsp, 20h
0x180051ee7  pop     rbx
0x180051ee8  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIVectorChangedEventArgs@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorChangedEventArgs>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorChangedEventArgs>(void)
```
