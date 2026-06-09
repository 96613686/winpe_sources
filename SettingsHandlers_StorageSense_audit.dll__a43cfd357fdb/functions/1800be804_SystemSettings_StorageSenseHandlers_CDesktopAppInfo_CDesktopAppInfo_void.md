# SystemSettings::StorageSenseHandlers::CDesktopAppInfo::~CDesktopAppInfo(void)

- ea: `0x1800be804`
- end: `0x1800be898`
- name: `??1CDesktopAppInfo@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `148`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CDesktopAppInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800be930`

## callees

- `0x180017ec8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be811`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be835`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be86b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be87d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be811`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be835`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be86b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be87d`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CDesktopAppInfo::~CDesktopAppInfo(HSTRING *this)
{
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::StorageSense::IMcpServerInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::StorageSense::IMcpServerInfo>(this);
}

```

## disassembly

```asm
0x1800be804  push    rbx
0x1800be806  sub     rsp, 20h
0x1800be80a  mov     rbx, rcx
0x1800be80d  mov     rcx, [rcx+50h]; string
0x1800be811  call    cs:__imp_WindowsDeleteString
0x1800be817  mov     qword ptr [rbx+50h], 0
0x1800be81f  mov     rcx, [rbx+48h]; string
0x1800be823  call    cs:__imp_WindowsDeleteString
0x1800be829  mov     qword ptr [rbx+48h], 0
0x1800be831  mov     rcx, [rbx+40h]; string
0x1800be835  call    cs:__imp_WindowsDeleteString
0x1800be83b  mov     qword ptr [rbx+40h], 0
0x1800be843  mov     rcx, [rbx+38h]; string
0x1800be847  call    cs:__imp_WindowsDeleteString
0x1800be84d  mov     qword ptr [rbx+38h], 0
0x1800be855  mov     rcx, [rbx+30h]; string
0x1800be859  call    cs:__imp_WindowsDeleteString
0x1800be85f  mov     qword ptr [rbx+30h], 0
0x1800be867  mov     rcx, [rbx+28h]; string
0x1800be86b  call    cs:__imp_WindowsDeleteString
0x1800be871  mov     qword ptr [rbx+28h], 0
0x1800be879  mov     rcx, [rbx+20h]; string
0x1800be87d  call    cs:__imp_WindowsDeleteString
0x1800be883  mov     rcx, rbx
0x1800be886  mov     qword ptr [rbx+20h], 0
0x1800be88e  add     rsp, 20h
0x1800be892  pop     rbx
0x1800be893  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIMcpServerInfo@StorageSense@DataModel@SystemSettings@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::StorageSense::IMcpServerInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::StorageSense::IMcpServerInfo>(void)
```
