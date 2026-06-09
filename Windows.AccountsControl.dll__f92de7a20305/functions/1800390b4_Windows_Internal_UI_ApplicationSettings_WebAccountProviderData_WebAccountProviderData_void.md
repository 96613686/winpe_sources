# Windows::Internal::UI::ApplicationSettings::WebAccountProviderData::~WebAccountProviderData(void)

- ea: `0x1800390b4`
- end: `0x18003911b`
- name: `??1WebAccountProviderData@ApplicationSettings@UI@Internal@Windows@@UEAA@XZ`
- size: `103`
- prototype: `void __fastcall(Windows::Internal::UI::ApplicationSettings::WebAccountProviderData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039720`

## callees

- `0x180011ffc`
- `0x18001aa8c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800390d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800390e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800390f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800390d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800390e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800390f7`

## pseudocode

```c
void __fastcall Windows::Internal::UI::ApplicationSettings::WebAccountProviderData::~WebAccountProviderData(
        HSTRING *this)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 14);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 13);
  WindowsDeleteString(this[12]);
  this[12] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 8);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800390b4  push    rbx
0x1800390b6  sub     rsp, 20h
0x1800390ba  mov     rbx, rcx
0x1800390bd  add     rcx, 70h ; 'p'
0x1800390c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800390c6  lea     rcx, [rbx+68h]
0x1800390ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800390cf  mov     rcx, [rbx+60h]; string
0x1800390d3  call    cs:__imp_WindowsDeleteString
0x1800390d9  mov     qword ptr [rbx+60h], 0
0x1800390e1  mov     rcx, [rbx+50h]; string
0x1800390e5  call    cs:__imp_WindowsDeleteString
0x1800390eb  mov     qword ptr [rbx+50h], 0
0x1800390f3  mov     rcx, [rbx+48h]; string
0x1800390f7  call    cs:__imp_WindowsDeleteString
0x1800390fd  lea     rcx, [rbx+40h]
0x180039101  mov     qword ptr [rbx+48h], 0
0x180039109  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003910e  mov     rcx, rbx
0x180039111  add     rsp, 20h
0x180039115  pop     rbx
0x180039116  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAccountsSettingsPaneEventDeferral@ApplicationSettings@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::IAccountsSettingsPaneEventDeferral,Microsoft::WRL::FtmBase>(void)
```
