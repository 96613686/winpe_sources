# Windows::Internal::UI::ApplicationSettings::AccountsControlData::~AccountsControlData(void)

- ea: `0x18001aabc`
- end: `0x18001ab29`
- name: `??1AccountsControlData@ApplicationSettings@UI@Internal@Windows@@UEAA@XZ`
- size: `109`
- prototype: `void __fastcall(Windows::Internal::UI::ApplicationSettings::AccountsControlData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ab70`

## callees

- `0x180011ffc`
- `0x18001aa8c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aacc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aafc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ab0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aacc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aafc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ab0e`

## pseudocode

```c
void __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlData::~AccountsControlData(HSTRING *this)
{
  WindowsDeleteString(this[18]);
  this[18] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 12);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 11);
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001aabc  push    rbx
0x18001aabe  sub     rsp, 20h
0x18001aac2  mov     rbx, rcx
0x18001aac5  mov     rcx, [rcx+90h]; string
0x18001aacc  call    cs:__imp_WindowsDeleteString
0x18001aad2  lea     rcx, [rbx+68h]
0x18001aad6  mov     qword ptr [rbx+90h], 0
0x18001aae1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001aae6  lea     rcx, [rbx+60h]
0x18001aaea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001aaef  lea     rcx, [rbx+58h]
0x18001aaf3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001aaf8  mov     rcx, [rbx+50h]; string
0x18001aafc  call    cs:__imp_WindowsDeleteString
0x18001ab02  mov     qword ptr [rbx+50h], 0
0x18001ab0a  mov     rcx, [rbx+48h]; string
0x18001ab0e  call    cs:__imp_WindowsDeleteString
0x18001ab14  mov     rcx, rbx
0x18001ab17  mov     qword ptr [rbx+48h], 0
0x18001ab1f  add     rsp, 20h
0x18001ab23  pop     rbx
0x18001ab24  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAccountsSettingsPaneEventDeferral@ApplicationSettings@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>(void)
```
