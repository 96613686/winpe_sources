# ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties(void)

- ea: `0x1801b88ec`
- end: `0x1801b898e`
- name: `??1ComServerRegistrationEntryProperties@@QEAA@XZ`
- size: `162`
- prototype: `void __fastcall(ComServerRegistrationEntryProperties *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009c650`
- `0x1800e7bc0`
- `0x18020a9cd`

## callees

- `0x18003a9c8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b88fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b893b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8956`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8968`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b897a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b88fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b893b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8956`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8968`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b897a`

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
0x1801b88ec  push    rbx
0x1801b88ee  sub     rsp, 20h
0x1801b88f2  mov     rbx, rcx
0x1801b88f5  mov     rcx, [rcx+0A8h]; string
0x1801b88fc  call    cs:__imp_WindowsDeleteString
0x1801b8902  mov     qword ptr [rbx+0A8h], 0
0x1801b890d  mov     rcx, [rbx+98h]; string
0x1801b8914  call    cs:__imp_WindowsDeleteString
0x1801b891a  mov     qword ptr [rbx+98h], 0
0x1801b8925  mov     rcx, [rbx+70h]; string
0x1801b8929  call    cs:__imp_WindowsDeleteString
0x1801b892f  mov     qword ptr [rbx+70h], 0
0x1801b8937  mov     rcx, [rbx+50h]; string
0x1801b893b  call    cs:__imp_WindowsDeleteString
0x1801b8941  lea     rcx, [rbx+38h]; this
0x1801b8945  mov     qword ptr [rbx+50h], 0
0x1801b894d  call    ?Release@SecurityDescriptor@@QEAAXXZ; SecurityDescriptor::Release(void)
0x1801b8952  mov     rcx, [rbx+28h]; string
0x1801b8956  call    cs:__imp_WindowsDeleteString
0x1801b895c  mov     qword ptr [rbx+28h], 0
0x1801b8964  mov     rcx, [rbx+18h]; string
0x1801b8968  call    cs:__imp_WindowsDeleteString
0x1801b896e  mov     qword ptr [rbx+18h], 0
0x1801b8976  mov     rcx, [rbx+8]; string
0x1801b897a  call    cs:__imp_WindowsDeleteString
0x1801b8980  mov     qword ptr [rbx+8], 0
0x1801b8988  add     rsp, 20h
0x1801b898c  pop     rbx
0x1801b898d  retn
```
