# SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo::~CMcpServerPackageInfo(void)

- ea: `0x1800a1a7c`
- end: `0x1800a1b45`
- name: `??1CMcpServerPackageInfo@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `201`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a2520`

## callees

- `0x180017ec8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1ab9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1ad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1ae3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1af1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1b0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1b29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1ab9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1ad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1ae3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1af1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1b0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1b29`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo::~CMcpServerPackageInfo(HSTRING *this)
{
  WindowsDeleteString(this[15]);
  this[15] = 0;
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
0x1800a1a7c  mov     [rsp+arg_0], rbx
0x1800a1a81  push    rdi
0x1800a1a82  sub     rsp, 20h
0x1800a1a86  mov     rbx, rcx
0x1800a1a89  mov     rcx, [rcx+78h]; string
0x1800a1a8d  call    cs:__imp_WindowsDeleteString
0x1800a1a93  xor     edi, edi
0x1800a1a95  mov     [rbx+78h], rdi
0x1800a1a99  mov     rcx, [rbx+70h]; string
0x1800a1a9d  call    cs:__imp_WindowsDeleteString
0x1800a1aa3  mov     [rbx+70h], rdi
0x1800a1aa7  mov     rcx, [rbx+68h]; string
0x1800a1aab  call    cs:__imp_WindowsDeleteString
0x1800a1ab1  mov     [rbx+68h], rdi
0x1800a1ab5  mov     rcx, [rbx+60h]; string
0x1800a1ab9  call    cs:__imp_WindowsDeleteString
0x1800a1abf  mov     [rbx+60h], rdi
0x1800a1ac3  mov     rcx, [rbx+58h]; string
0x1800a1ac7  call    cs:__imp_WindowsDeleteString
0x1800a1acd  mov     [rbx+58h], rdi
0x1800a1ad1  mov     rcx, [rbx+50h]; string
0x1800a1ad5  call    cs:__imp_WindowsDeleteString
0x1800a1adb  mov     [rbx+50h], rdi
0x1800a1adf  mov     rcx, [rbx+48h]; string
0x1800a1ae3  call    cs:__imp_WindowsDeleteString
0x1800a1ae9  mov     [rbx+48h], rdi
0x1800a1aed  mov     rcx, [rbx+40h]; string
0x1800a1af1  call    cs:__imp_WindowsDeleteString
0x1800a1af7  mov     [rbx+40h], rdi
0x1800a1afb  mov     rcx, [rbx+38h]; string
0x1800a1aff  call    cs:__imp_WindowsDeleteString
0x1800a1b05  mov     [rbx+38h], rdi
0x1800a1b09  mov     rcx, [rbx+30h]; string
0x1800a1b0d  call    cs:__imp_WindowsDeleteString
0x1800a1b13  mov     [rbx+30h], rdi
0x1800a1b17  mov     rcx, [rbx+28h]; string
0x1800a1b1b  call    cs:__imp_WindowsDeleteString
0x1800a1b21  mov     [rbx+28h], rdi
0x1800a1b25  mov     rcx, [rbx+20h]; string
0x1800a1b29  call    cs:__imp_WindowsDeleteString
0x1800a1b2f  mov     rcx, rbx
0x1800a1b32  mov     [rbx+20h], rdi
0x1800a1b36  mov     rbx, [rsp+28h+arg_0]
0x1800a1b3b  add     rsp, 20h
0x1800a1b3f  pop     rdi
0x1800a1b40  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIMcpServerInfo@StorageSense@DataModel@SystemSettings@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::StorageSense::IMcpServerInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::StorageSense::IMcpServerInfo>(void)
```
