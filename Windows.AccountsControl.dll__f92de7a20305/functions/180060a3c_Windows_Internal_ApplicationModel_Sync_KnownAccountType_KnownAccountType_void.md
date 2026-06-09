# Windows::Internal::ApplicationModel::Sync::KnownAccountType::~KnownAccountType(void)

- ea: `0x180060a3c`
- end: `0x180060a88`
- name: `??1KnownAccountType@Sync@ApplicationModel@Internal@Windows@@UEAA@XZ`
- size: `76`
- prototype: `void __fastcall(Windows::Internal::ApplicationModel::Sync::KnownAccountType *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060ba0`

## callees

- `0x180038eec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060a49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060a5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060a6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060a49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060a5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060a6d`

## pseudocode

```c
void __fastcall Windows::Internal::ApplicationModel::Sync::KnownAccountType::~KnownAccountType(HSTRING *this)
{
  WindowsDeleteString(this[12]);
  this[12] = 0;
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::ApplicationSettings::IBubbleHeadData,Windows::Internal::UI::ApplicationSettings::IBubbleHeadDataAsync,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::ApplicationSettings::IBubbleHeadData,Windows::Internal::UI::ApplicationSettings::IBubbleHeadDataAsync,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180060a3c  push    rbx
0x180060a3e  sub     rsp, 20h
0x180060a42  mov     rbx, rcx
0x180060a45  mov     rcx, [rcx+60h]; string
0x180060a49  call    cs:__imp_WindowsDeleteString
0x180060a4f  mov     qword ptr [rbx+60h], 0
0x180060a57  mov     rcx, [rbx+58h]; string
0x180060a5b  call    cs:__imp_WindowsDeleteString
0x180060a61  mov     qword ptr [rbx+58h], 0
0x180060a69  mov     rcx, [rbx+48h]; string
0x180060a6d  call    cs:__imp_WindowsDeleteString
0x180060a73  mov     rcx, rbx
0x180060a76  mov     qword ptr [rbx+48h], 0
0x180060a7e  add     rsp, 20h
0x180060a82  pop     rbx
0x180060a83  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@UIBubbleHeadDataAsync@5678@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::ApplicationSettings::IBubbleHeadData,Windows::Internal::UI::ApplicationSettings::IBubbleHeadDataAsync,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::ApplicationSettings::IBubbleHeadData,Windows::Internal::UI::ApplicationSettings::IBubbleHeadDataAsync,Microsoft::WRL::FtmBase>(void)
```
