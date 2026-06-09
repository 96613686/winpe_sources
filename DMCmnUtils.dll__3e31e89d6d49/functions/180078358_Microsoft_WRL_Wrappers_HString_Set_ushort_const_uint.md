# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180078358`
- end: `0x1800783a9`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `81`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18007759c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007839d`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set(HSTRING *this, const unsigned __int16 *a2, UINT32 a3)
{
  WindowsDeleteString(*this);
  *this = 0;
  return WindowsCreateString(a2, a3, this);
}

```

## disassembly

```asm
0x180078358  mov     [rsp+arg_0], rbx
0x18007835d  mov     [rsp+arg_8], rsi
0x180078362  push    rdi
0x180078363  sub     rsp, 20h
0x180078367  mov     rbx, rcx
0x18007836a  mov     edi, r8d
0x18007836d  mov     rcx, [rcx]; string
0x180078370  mov     rsi, rdx
0x180078373  call    cs:__imp_WindowsDeleteString
0x18007837a  nop     dword ptr [rax+rax+00h]
0x18007837f  mov     r8, rbx
0x180078382  mov     qword ptr [rbx], 0
0x180078389  mov     edx, edi
0x18007838b  mov     rcx, rsi
0x18007838e  mov     rbx, [rsp+28h+arg_0]
0x180078393  mov     rsi, [rsp+28h+arg_8]
0x180078398  add     rsp, 20h
0x18007839c  pop     rdi
0x18007839d  jmp     cs:__imp_WindowsCreateString
```
