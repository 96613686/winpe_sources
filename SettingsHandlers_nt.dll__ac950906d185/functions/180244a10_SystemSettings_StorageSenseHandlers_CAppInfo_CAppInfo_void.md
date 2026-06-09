# SystemSettings::StorageSenseHandlers::CAppInfo::~CAppInfo(void)

- ea: `0x180244a10`
- end: `0x180244abd`
- name: `??1CAppInfo@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `173`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAppInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180244ba0`

## callees

- `0x18002d720`
- `0x18002d7a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180244a9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180244a9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180244a20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180244a3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180244a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180244a6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180244a83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180244a20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180244a3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180244a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180244a6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180244a83`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::~CAppInfo(
        SystemSettings::StorageSenseHandlers::CAppInfo *this)
{
  WindowsDeleteString(*((HSTRING *)this + 16));
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(*((HSTRING *)this + 14));
  *((_QWORD *)this + 14) = 0;
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>((char *)this + 32);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::IPackageInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::IPackageInfo>(this);
}

```

## disassembly

```asm
0x180244a10  push    rbx
0x180244a12  sub     rsp, 20h
0x180244a16  mov     rbx, rcx
0x180244a19  mov     rcx, [rcx+80h]; string
0x180244a20  call    cs:__imp_WindowsDeleteString
0x180244a27  nop     dword ptr [rax+rax+00h]
0x180244a2c  mov     qword ptr [rbx+80h], 0
0x180244a37  mov     rcx, [rbx+70h]; string
0x180244a3b  call    cs:__imp_WindowsDeleteString
0x180244a42  nop     dword ptr [rax+rax+00h]
0x180244a47  mov     qword ptr [rbx+70h], 0
0x180244a4f  mov     rcx, [rbx+68h]; string
0x180244a53  call    cs:__imp_WindowsDeleteString
0x180244a5a  nop     dword ptr [rax+rax+00h]
0x180244a5f  mov     qword ptr [rbx+68h], 0
0x180244a67  mov     rcx, [rbx+60h]; string
0x180244a6b  call    cs:__imp_WindowsDeleteString
0x180244a72  nop     dword ptr [rax+rax+00h]
0x180244a77  mov     qword ptr [rbx+60h], 0
0x180244a7f  mov     rcx, [rbx+58h]; string
0x180244a83  call    cs:__imp_WindowsDeleteString
0x180244a8a  nop     dword ptr [rax+rax+00h]
0x180244a8f  lea     rcx, [rbx+30h]; lpCriticalSection
0x180244a93  mov     qword ptr [rbx+58h], 0
0x180244a9b  call    cs:__imp_DeleteCriticalSection
0x180244aa2  nop     dword ptr [rax+rax+00h]
0x180244aa7  lea     rcx, [rbx+20h]
0x180244aab  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x180244ab0  mov     rcx, rbx
0x180244ab3  add     rsp, 20h
0x180244ab7  pop     rbx
0x180244ab8  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIPackageInfo@DataModel@SystemSettings@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::IPackageInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::IPackageInfo>(void)
```
