# ComProxyStubRegistrationEntryProperties::~ComProxyStubRegistrationEntryProperties(void)

- ea: `0x18014be60`
- end: `0x18014bf00`
- name: `??1ComProxyStubRegistrationEntryProperties@@QEAA@XZ`
- size: `160`
- prototype: `void __fastcall(ComProxyStubRegistrationEntryProperties *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18014be38`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014be6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014be85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014be9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014beb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014becd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bee5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014be6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014be85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014be9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014beb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014becd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bee5`

## pseudocode

```c
void __fastcall ComProxyStubRegistrationEntryProperties::~ComProxyStubRegistrationEntryProperties(HSTRING *this)
{
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
}

```

## disassembly

```asm
0x18014be60  push    rbx
0x18014be62  sub     rsp, 20h
0x18014be66  mov     rbx, rcx
0x18014be69  mov     rcx, [rcx+58h]; string
0x18014be6d  call    cs:__imp_WindowsDeleteString
0x18014be74  nop     dword ptr [rax+rax+00h]
0x18014be79  mov     qword ptr [rbx+58h], 0
0x18014be81  mov     rcx, [rbx+48h]; string
0x18014be85  call    cs:__imp_WindowsDeleteString
0x18014be8c  nop     dword ptr [rax+rax+00h]
0x18014be91  mov     qword ptr [rbx+48h], 0
0x18014be99  mov     rcx, [rbx+38h]; string
0x18014be9d  call    cs:__imp_WindowsDeleteString
0x18014bea4  nop     dword ptr [rax+rax+00h]
0x18014bea9  mov     qword ptr [rbx+38h], 0
0x18014beb1  mov     rcx, [rbx+28h]; string
0x18014beb5  call    cs:__imp_WindowsDeleteString
0x18014bebc  nop     dword ptr [rax+rax+00h]
0x18014bec1  mov     qword ptr [rbx+28h], 0
0x18014bec9  mov     rcx, [rbx+18h]; string
0x18014becd  call    cs:__imp_WindowsDeleteString
0x18014bed4  nop     dword ptr [rax+rax+00h]
0x18014bed9  mov     qword ptr [rbx+18h], 0
0x18014bee1  mov     rcx, [rbx+8]; string
0x18014bee5  call    cs:__imp_WindowsDeleteString
0x18014beec  nop     dword ptr [rax+rax+00h]
0x18014bef1  mov     qword ptr [rbx+8], 0
0x18014bef9  add     rsp, 20h
0x18014befd  pop     rbx
0x18014befe  retn
```
