# SystemSettings::StorageSenseHandlers::CAppCapabilityListItemSetting::~CAppCapabilityListItemSetting(void)

- ea: `0x1800c8e70`
- end: `0x1800c8eda`
- name: `??1CAppCapabilityListItemSetting@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `106`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAppCapabilityListItemSetting *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c9890`

## callees

- `0x18000c964`
- `0x180017d04`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8e8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8ebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8e8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8ebc`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CAppCapabilityListItemSetting::~CAppCapabilityListItemSetting(
        HSTRING *this)
{
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(this + 33);
  WindowsDeleteString(this[32]);
  this[32] = 0;
  WindowsDeleteString(this[31]);
  this[31] = 0;
  WindowsDeleteString(this[30]);
  this[30] = 0;
  SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>((SystemSettings::DataModel::CSettingBase *)this);
}

```

## disassembly

```asm
0x1800c8e70  push    rbx
0x1800c8e72  sub     rsp, 20h
0x1800c8e76  mov     rbx, rcx
0x1800c8e79  add     rcx, 108h
0x1800c8e80  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c8e85  mov     rcx, [rbx+100h]; string
0x1800c8e8c  call    cs:__imp_WindowsDeleteString
0x1800c8e92  mov     qword ptr [rbx+100h], 0
0x1800c8e9d  mov     rcx, [rbx+0F8h]; string
0x1800c8ea4  call    cs:__imp_WindowsDeleteString
0x1800c8eaa  mov     qword ptr [rbx+0F8h], 0
0x1800c8eb5  mov     rcx, [rbx+0F0h]; string
0x1800c8ebc  call    cs:__imp_WindowsDeleteString
0x1800c8ec2  mov     rcx, rbx; this
0x1800c8ec5  mov     qword ptr [rbx+0F0h], 0
0x1800c8ed0  add     rsp, 20h
0x1800c8ed4  pop     rbx
0x1800c8ed5  jmp     ??1?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
