# SystemSettings::StorageSenseHandlers::AIComponentForLocalService::~AIComponentForLocalService(void)

- ea: `0x1800947ac`
- end: `0x180094822`
- name: `??1AIComponentForLocalService@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `118`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::AIComponentForLocalService *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180094a50`
- `0x180094a90`

## callees

- `0x180017cdc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094804`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094804`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::AIComponentForLocalService::~AIComponentForLocalService(
        HSTRING *this)
{
  WindowsDeleteString(this[33]);
  this[33] = 0;
  WindowsDeleteString(this[32]);
  this[32] = 0;
  WindowsDeleteString(this[31]);
  this[31] = 0;
  WindowsDeleteString(this[30]);
  this[30] = 0;
  SystemSettings::DataModel::CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>((SystemSettings::DataModel::CSettingBase *)this);
}

```

## disassembly

```asm
0x1800947ac  push    rbx
0x1800947ae  sub     rsp, 20h
0x1800947b2  mov     rbx, rcx
0x1800947b5  mov     rcx, [rcx+108h]; string
0x1800947bc  call    cs:__imp_WindowsDeleteString
0x1800947c2  mov     qword ptr [rbx+108h], 0
0x1800947cd  mov     rcx, [rbx+100h]; string
0x1800947d4  call    cs:__imp_WindowsDeleteString
0x1800947da  mov     qword ptr [rbx+100h], 0
0x1800947e5  mov     rcx, [rbx+0F8h]; string
0x1800947ec  call    cs:__imp_WindowsDeleteString
0x1800947f2  mov     qword ptr [rbx+0F8h], 0
0x1800947fd  mov     rcx, [rbx+0F0h]; string
0x180094804  call    cs:__imp_WindowsDeleteString
0x18009480a  mov     rcx, rbx; this
0x18009480d  mov     qword ptr [rbx+0F0h], 0
0x180094818  add     rsp, 20h
0x18009481c  pop     rbx
0x18009481d  jmp     ??1?$CCollectionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
