# Windows::Internal::UI::ApplicationSettings::BubbleHeadData::~BubbleHeadData(void)

- ea: `0x180038fdc`
- end: `0x18003901f`
- name: `??1BubbleHeadData@ApplicationSettings@UI@Internal@Windows@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(Windows::Internal::UI::ApplicationSettings::BubbleHeadData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039660`

## callees

- `0x180011ffc`
- `0x180038eec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038ff2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038ff2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039004`

## pseudocode

```c
void __fastcall Windows::Internal::UI::ApplicationSettings::BubbleHeadData::~BubbleHeadData(HSTRING *this)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 13);
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::ApplicationSettings::IBubbleHeadData,Windows::Internal::UI::ApplicationSettings::IBubbleHeadDataAsync,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::ApplicationSettings::IBubbleHeadData,Windows::Internal::UI::ApplicationSettings::IBubbleHeadDataAsync,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180038fdc  push    rbx
0x180038fde  sub     rsp, 20h
0x180038fe2  mov     rbx, rcx
0x180038fe5  add     rcx, 68h ; 'h'
0x180038fe9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038fee  mov     rcx, [rbx+50h]; string
0x180038ff2  call    cs:__imp_WindowsDeleteString
0x180038ff8  mov     qword ptr [rbx+50h], 0
0x180039000  mov     rcx, [rbx+48h]; string
0x180039004  call    cs:__imp_WindowsDeleteString
0x18003900a  mov     rcx, rbx
0x18003900d  mov     qword ptr [rbx+48h], 0
0x180039015  add     rsp, 20h
0x180039019  pop     rbx
0x18003901a  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@UIBubbleHeadDataAsync@5678@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::ApplicationSettings::IBubbleHeadData,Windows::Internal::UI::ApplicationSettings::IBubbleHeadDataAsync,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::ApplicationSettings::IBubbleHeadData,Windows::Internal::UI::ApplicationSettings::IBubbleHeadDataAsync,Microsoft::WRL::FtmBase>(void)
```
