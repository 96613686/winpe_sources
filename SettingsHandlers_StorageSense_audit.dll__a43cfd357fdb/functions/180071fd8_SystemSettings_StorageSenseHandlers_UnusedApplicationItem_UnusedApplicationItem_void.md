# SystemSettings::StorageSenseHandlers::UnusedApplicationItem::~UnusedApplicationItem(void)

- ea: `0x180071fd8`
- end: `0x180072036`
- name: `??1UnusedApplicationItem@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::UnusedApplicationItem *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180072dd0`

## callees

- `0x18003be2c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071fe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071fe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072018`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::UnusedApplicationItem::~UnusedApplicationItem(HSTRING *this)
{
  WindowsDeleteString(this[52]);
  this[52] = 0;
  WindowsDeleteString(this[51]);
  this[51] = 0;
  WindowsDeleteString(this[50]);
  this[50] = 0;
  SystemSettings::StorageSenseHandlers::CPackageSizeSetting::~CPackageSizeSetting((SystemSettings::StorageSenseHandlers::CPackageSizeSetting *)this);
}

```

## disassembly

```asm
0x180071fd8  push    rbx
0x180071fda  sub     rsp, 20h
0x180071fde  mov     rbx, rcx
0x180071fe1  mov     rcx, [rcx+1A0h]; string
0x180071fe8  call    cs:__imp_WindowsDeleteString
0x180071fee  mov     qword ptr [rbx+1A0h], 0
0x180071ff9  mov     rcx, [rbx+198h]; string
0x180072000  call    cs:__imp_WindowsDeleteString
0x180072006  mov     qword ptr [rbx+198h], 0
0x180072011  mov     rcx, [rbx+190h]; string
0x180072018  call    cs:__imp_WindowsDeleteString
0x18007201e  mov     rcx, rbx; this
0x180072021  mov     qword ptr [rbx+190h], 0
0x18007202c  add     rsp, 20h
0x180072030  pop     rbx
0x180072031  jmp     ??1CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@UEAA@XZ; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::~CPackageSizeSetting(void)
```
