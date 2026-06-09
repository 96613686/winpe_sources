# ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties(void)

- ea: `0x18014bf08`
- end: `0x18014bfd5`
- name: `??1ComServerRegistrationEntryProperties@@QEAA@XZ`
- size: `205`
- prototype: `void __fastcall(ComServerRegistrationEntryProperties *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006abf0`
- `0x1800a3c14`
- `0x18019fdaa`

## callees

- `0x180163550`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bf18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bf36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bf51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bf69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bf8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bfa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bfba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bf18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bf36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bf51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bf69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bf8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bfa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014bfba`

## pseudocode

```c
void __fastcall ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties(HSTRING *this)
{
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[19]);
  this[19] = 0;
  WindowsDeleteString(this[14]);
  this[14] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  SecurityDescriptor::Release((SecurityDescriptor *)(this + 7));
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
0x18014bf08  push    rbx
0x18014bf0a  sub     rsp, 20h
0x18014bf0e  mov     rbx, rcx
0x18014bf11  mov     rcx, [rcx+0A8h]; string
0x18014bf18  call    cs:__imp_WindowsDeleteString
0x18014bf1f  nop     dword ptr [rax+rax+00h]
0x18014bf24  mov     qword ptr [rbx+0A8h], 0
0x18014bf2f  mov     rcx, [rbx+98h]; string
0x18014bf36  call    cs:__imp_WindowsDeleteString
0x18014bf3d  nop     dword ptr [rax+rax+00h]
0x18014bf42  mov     qword ptr [rbx+98h], 0
0x18014bf4d  mov     rcx, [rbx+70h]; string
0x18014bf51  call    cs:__imp_WindowsDeleteString
0x18014bf58  nop     dword ptr [rax+rax+00h]
0x18014bf5d  mov     qword ptr [rbx+70h], 0
0x18014bf65  mov     rcx, [rbx+50h]; string
0x18014bf69  call    cs:__imp_WindowsDeleteString
0x18014bf70  nop     dword ptr [rax+rax+00h]
0x18014bf75  lea     rcx, [rbx+38h]; this
0x18014bf79  mov     qword ptr [rbx+50h], 0
0x18014bf81  call    ?Release@SecurityDescriptor@@QEAAXXZ; SecurityDescriptor::Release(void)
0x18014bf86  mov     rcx, [rbx+28h]; string
0x18014bf8a  call    cs:__imp_WindowsDeleteString
0x18014bf91  nop     dword ptr [rax+rax+00h]
0x18014bf96  mov     qword ptr [rbx+28h], 0
0x18014bf9e  mov     rcx, [rbx+18h]; string
0x18014bfa2  call    cs:__imp_WindowsDeleteString
0x18014bfa9  nop     dword ptr [rax+rax+00h]
0x18014bfae  mov     qword ptr [rbx+18h], 0
0x18014bfb6  mov     rcx, [rbx+8]; string
0x18014bfba  call    cs:__imp_WindowsDeleteString
0x18014bfc1  nop     dword ptr [rax+rax+00h]
0x18014bfc6  mov     qword ptr [rbx+8], 0
0x18014bfce  add     rsp, 20h
0x18014bfd2  pop     rbx
0x18014bfd3  retn
```
