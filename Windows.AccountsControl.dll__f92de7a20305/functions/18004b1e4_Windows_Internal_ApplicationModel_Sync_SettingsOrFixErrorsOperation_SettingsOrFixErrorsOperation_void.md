# Windows::Internal::ApplicationModel::Sync::SettingsOrFixErrorsOperation::~SettingsOrFixErrorsOperation(void)

- ea: `0x18004b1e4`
- end: `0x18004b22a`
- name: `??1SettingsOrFixErrorsOperation@Sync@ApplicationModel@Internal@Windows@@UEAA@XZ`
- size: `70`
- prototype: `void __fastcall(Windows::Internal::ApplicationModel::Sync::SettingsOrFixErrorsOperation *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b2e0`

## callees

- `0x180049054`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b1f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b20c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b1f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b20c`

## pseudocode

```c
void __fastcall Windows::Internal::ApplicationModel::Sync::SettingsOrFixErrorsOperation::~SettingsOrFixErrorsOperation(
        HSTRING *this)
{
  WindowsDeleteString(this[76]);
  this[76] = 0;
  WindowsDeleteString(this[75]);
  this[75] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,ViewOperationBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,ViewOperationBase>((ViewOperationBase *)this);
}

```

## disassembly

```asm
0x18004b1e4  push    rbx
0x18004b1e6  sub     rsp, 20h
0x18004b1ea  mov     rbx, rcx
0x18004b1ed  mov     rcx, [rcx+260h]; string
0x18004b1f4  call    cs:__imp_WindowsDeleteString
0x18004b1fa  mov     qword ptr [rbx+260h], 0
0x18004b205  mov     rcx, [rbx+258h]; string
0x18004b20c  call    cs:__imp_WindowsDeleteString
0x18004b212  mov     rcx, rbx; this
0x18004b215  mov     qword ptr [rbx+258h], 0
0x18004b220  add     rsp, 20h
0x18004b224  pop     rbx
0x18004b225  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VViewOperationBase@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,ViewOperationBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,ViewOperationBase>(void)
```
