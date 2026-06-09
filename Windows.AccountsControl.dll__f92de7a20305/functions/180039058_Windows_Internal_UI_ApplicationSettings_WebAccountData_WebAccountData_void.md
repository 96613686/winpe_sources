# Windows::Internal::UI::ApplicationSettings::WebAccountData::~WebAccountData(void)

- ea: `0x180039058`
- end: `0x1800390ad`
- name: `??1WebAccountData@ApplicationSettings@UI@Internal@Windows@@UEAA@XZ`
- size: `85`
- prototype: `void __fastcall(Windows::Internal::UI::ApplicationSettings::WebAccountData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800396e0`

## callees

- `0x180011ffc`
- `0x18001aa8c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039089`

## pseudocode

```c
void __fastcall Windows::Internal::UI::ApplicationSettings::WebAccountData::~WebAccountData(HSTRING *this)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 12);
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 8);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180039058  push    rbx
0x18003905a  sub     rsp, 20h
0x18003905e  mov     rbx, rcx
0x180039061  add     rcx, 68h ; 'h'
0x180039065  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003906a  lea     rcx, [rbx+60h]
0x18003906e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039073  mov     rcx, [rbx+58h]; string
0x180039077  call    cs:__imp_WindowsDeleteString
0x18003907d  mov     qword ptr [rbx+58h], 0
0x180039085  mov     rcx, [rbx+50h]; string
0x180039089  call    cs:__imp_WindowsDeleteString
0x18003908f  lea     rcx, [rbx+40h]
0x180039093  mov     qword ptr [rbx+50h], 0
0x18003909b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800390a0  mov     rcx, rbx
0x1800390a3  add     rsp, 20h
0x1800390a7  pop     rbx
0x1800390a8  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAccountsSettingsPaneEventDeferral@ApplicationSettings@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>(void)
```
