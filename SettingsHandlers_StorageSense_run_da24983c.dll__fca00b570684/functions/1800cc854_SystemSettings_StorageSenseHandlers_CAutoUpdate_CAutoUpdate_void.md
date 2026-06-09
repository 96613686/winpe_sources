# SystemSettings::StorageSenseHandlers::CAutoUpdate::~CAutoUpdate(void)

- ea: `0x1800cc854`
- end: `0x1800cc8b2`
- name: `??1CAutoUpdate@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAutoUpdate *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800cc8c0`

## callees

- `0x180017d04`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cc864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cc87c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cc894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cc864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cc87c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cc894`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CAutoUpdate::~CAutoUpdate(HSTRING *this)
{
  WindowsDeleteString(this[33]);
  this[33] = 0;
  WindowsDeleteString(this[32]);
  this[32] = 0;
  WindowsDeleteString(this[31]);
  this[31] = 0;
  SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>((SystemSettings::DataModel::CSettingBase *)this);
}

```

## disassembly

```asm
0x1800cc854  push    rbx
0x1800cc856  sub     rsp, 20h
0x1800cc85a  mov     rbx, rcx
0x1800cc85d  mov     rcx, [rcx+108h]; string
0x1800cc864  call    cs:__imp_WindowsDeleteString
0x1800cc86a  mov     qword ptr [rbx+108h], 0
0x1800cc875  mov     rcx, [rbx+100h]; string
0x1800cc87c  call    cs:__imp_WindowsDeleteString
0x1800cc882  mov     qword ptr [rbx+100h], 0
0x1800cc88d  mov     rcx, [rbx+0F8h]; string
0x1800cc894  call    cs:__imp_WindowsDeleteString
0x1800cc89a  mov     rcx, rbx; this
0x1800cc89d  mov     qword ptr [rbx+0F8h], 0
0x1800cc8a8  add     rsp, 20h
0x1800cc8ac  pop     rbx
0x1800cc8ad  jmp     ??1?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
