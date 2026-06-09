# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180016e84`
- end: `0x180016ed5`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `81`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000eacc`
- `0x18001a5c8`
- `0x18001dd00`
- `0x180039cd0`
- `0x18003bbf8`
- `0x18003e780`
- `0x180040ac0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180016ec9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016e9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016e9f`

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
0x180016e84  mov     [rsp+arg_0], rbx
0x180016e89  mov     [rsp+arg_8], rsi
0x180016e8e  push    rdi
0x180016e8f  sub     rsp, 20h
0x180016e93  mov     rbx, rcx
0x180016e96  mov     edi, r8d
0x180016e99  mov     rcx, [rcx]; string
0x180016e9c  mov     rsi, rdx
0x180016e9f  call    cs:__imp_WindowsDeleteString
0x180016ea6  nop     dword ptr [rax+rax+00h]
0x180016eab  mov     r8, rbx
0x180016eae  mov     qword ptr [rbx], 0
0x180016eb5  mov     edx, edi
0x180016eb7  mov     rcx, rsi
0x180016eba  mov     rbx, [rsp+28h+arg_0]
0x180016ebf  mov     rsi, [rsp+28h+arg_8]
0x180016ec4  add     rsp, 20h
0x180016ec8  pop     rdi
0x180016ec9  jmp     cs:__imp_WindowsCreateString
```
