# SystemSettings::StorageSenseHandlers::CAppInfo::~CAppInfo(void)

- ea: `0x1800be760`
- end: `0x1800be7fd`
- name: `??1CAppInfo@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `157`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAppInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800be8f0`

## callees

- `0x18000c964`
- `0x180017ec8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be76d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be77f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be7a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be7b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be7e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be76d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be77f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be7a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be7b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800be7e2`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::~CAppInfo(HSTRING *this)
{
  WindowsDeleteString(this[14]);
  this[14] = 0;
  WindowsDeleteString(this[13]);
  this[13] = 0;
  WindowsDeleteString(this[12]);
  this[12] = 0;
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(this + 9);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(this + 8);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(this + 7);
  WindowsDeleteString(this[4]);
  this[4] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::StorageSense::IMcpServerInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::StorageSense::IMcpServerInfo>(this);
}

```

## disassembly

```asm
0x1800be760  push    rbx
0x1800be762  sub     rsp, 20h
0x1800be766  mov     rbx, rcx
0x1800be769  mov     rcx, [rcx+70h]; string
0x1800be76d  call    cs:__imp_WindowsDeleteString
0x1800be773  mov     qword ptr [rbx+70h], 0
0x1800be77b  mov     rcx, [rbx+68h]; string
0x1800be77f  call    cs:__imp_WindowsDeleteString
0x1800be785  mov     qword ptr [rbx+68h], 0
0x1800be78d  mov     rcx, [rbx+60h]; string
0x1800be791  call    cs:__imp_WindowsDeleteString
0x1800be797  mov     qword ptr [rbx+60h], 0
0x1800be79f  mov     rcx, [rbx+58h]; string
0x1800be7a3  call    cs:__imp_WindowsDeleteString
0x1800be7a9  mov     qword ptr [rbx+58h], 0
0x1800be7b1  mov     rcx, [rbx+50h]; string
0x1800be7b5  call    cs:__imp_WindowsDeleteString
0x1800be7bb  lea     rcx, [rbx+48h]
0x1800be7bf  mov     qword ptr [rbx+50h], 0
0x1800be7c7  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800be7cc  lea     rcx, [rbx+40h]
0x1800be7d0  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800be7d5  lea     rcx, [rbx+38h]
0x1800be7d9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800be7de  mov     rcx, [rbx+20h]; string
0x1800be7e2  call    cs:__imp_WindowsDeleteString
0x1800be7e8  mov     rcx, rbx
0x1800be7eb  mov     qword ptr [rbx+20h], 0
0x1800be7f3  add     rsp, 20h
0x1800be7f7  pop     rbx
0x1800be7f8  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIMcpServerInfo@StorageSense@DataModel@SystemSettings@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::StorageSense::IMcpServerInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::StorageSense::IMcpServerInfo>(void)
```
