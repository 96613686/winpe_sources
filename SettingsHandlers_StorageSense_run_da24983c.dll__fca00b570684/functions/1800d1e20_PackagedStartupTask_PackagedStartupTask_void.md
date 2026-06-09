# PackagedStartupTask::~PackagedStartupTask(void)

- ea: `0x1800d1e20`
- end: `0x1800d1ec6`
- name: `??1PackagedStartupTask@@QEAA@XZ`
- size: `166`
- prototype: `void __fastcall(PackagedStartupTask *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d77f4`

## callees

- `0x18000c964`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1eab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1eab`

## pseudocode

```c
void __fastcall PackagedStartupTask::~PackagedStartupTask(HSTRING *this)
{
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
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(this);
}

```

## disassembly

```asm
0x1800d1e20  push    rbx
0x1800d1e22  sub     rsp, 20h
0x1800d1e26  mov     rbx, rcx
0x1800d1e29  mov     rcx, [rcx+40h]; string
0x1800d1e2d  call    cs:__imp_WindowsDeleteString
0x1800d1e33  mov     qword ptr [rbx+40h], 0
0x1800d1e3b  mov     rcx, [rbx+38h]; string
0x1800d1e3f  call    cs:__imp_WindowsDeleteString
0x1800d1e45  mov     qword ptr [rbx+38h], 0
0x1800d1e4d  mov     rcx, [rbx+30h]; string
0x1800d1e51  call    cs:__imp_WindowsDeleteString
0x1800d1e57  mov     qword ptr [rbx+30h], 0
0x1800d1e5f  mov     rcx, [rbx+28h]; string
0x1800d1e63  call    cs:__imp_WindowsDeleteString
0x1800d1e69  mov     qword ptr [rbx+28h], 0
0x1800d1e71  mov     rcx, [rbx+20h]; string
0x1800d1e75  call    cs:__imp_WindowsDeleteString
0x1800d1e7b  mov     qword ptr [rbx+20h], 0
0x1800d1e83  mov     rcx, [rbx+18h]; string
0x1800d1e87  call    cs:__imp_WindowsDeleteString
0x1800d1e8d  mov     qword ptr [rbx+18h], 0
0x1800d1e95  mov     rcx, [rbx+10h]; string
0x1800d1e99  call    cs:__imp_WindowsDeleteString
0x1800d1e9f  mov     qword ptr [rbx+10h], 0
0x1800d1ea7  mov     rcx, [rbx+8]; string
0x1800d1eab  call    cs:__imp_WindowsDeleteString
0x1800d1eb1  mov     rcx, rbx
0x1800d1eb4  mov     qword ptr [rbx+8], 0
0x1800d1ebc  add     rsp, 20h
0x1800d1ec0  pop     rbx
0x1800d1ec1  jmp     ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
```
