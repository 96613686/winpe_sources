# SystemSettings::StorageSenseHandlers::CAppInfo::~CAppInfo(void)

- ea: `0x180051e10`
- end: `0x180051e99`
- name: `??1CAppInfo@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `137`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAppInfo *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051f80`

## callees

- `0x180004cfc`
- `0x180015848`
- `0x1800158d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051e6b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051e6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051e47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051e47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051e7e`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::~CAppInfo(
        SystemSettings::StorageSenseHandlers::CAppInfo *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 144);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 136);
  WindowsDeleteString(*((HSTRING *)this + 14));
  *((_QWORD *)this + 14) = 0;
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>((char *)this + 40);
  WindowsDeleteString(*((HSTRING *)this + 4));
  *((_QWORD *)this + 4) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorChangedEventArgs>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorChangedEventArgs>(this);
}

```

## disassembly

```asm
0x180051e10  push    rbx
0x180051e12  sub     rsp, 20h
0x180051e16  mov     rbx, rcx
0x180051e19  add     rcx, 90h
0x180051e20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051e25  lea     rcx, [rbx+88h]
0x180051e2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051e31  mov     rcx, [rbx+70h]; string
0x180051e35  call    cs:__imp_WindowsDeleteString
0x180051e3b  mov     qword ptr [rbx+70h], 0
0x180051e43  mov     rcx, [rbx+68h]; string
0x180051e47  call    cs:__imp_WindowsDeleteString
0x180051e4d  mov     qword ptr [rbx+68h], 0
0x180051e55  mov     rcx, [rbx+60h]; string
0x180051e59  call    cs:__imp_WindowsDeleteString
0x180051e5f  lea     rcx, [rbx+38h]; lpCriticalSection
0x180051e63  mov     qword ptr [rbx+60h], 0
0x180051e6b  call    cs:__imp_DeleteCriticalSection
0x180051e71  lea     rcx, [rbx+28h]
0x180051e75  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x180051e7a  mov     rcx, [rbx+20h]; string
0x180051e7e  call    cs:__imp_WindowsDeleteString
0x180051e84  mov     rcx, rbx
0x180051e87  mov     qword ptr [rbx+20h], 0
0x180051e8f  add     rsp, 20h
0x180051e93  pop     rbx
0x180051e94  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIVectorChangedEventArgs@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorChangedEventArgs>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorChangedEventArgs>(void)
```
