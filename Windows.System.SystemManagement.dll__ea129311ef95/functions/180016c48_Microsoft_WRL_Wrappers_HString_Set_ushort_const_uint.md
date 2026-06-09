# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180016c48`
- end: `0x180016c8e`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180015d04`
- `0x18001bad0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016c63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016c63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180016c87`

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
0x180016c48  mov     [rsp+arg_0], rbx
0x180016c4d  mov     [rsp+arg_8], rsi
0x180016c52  push    rdi
0x180016c53  sub     rsp, 20h
0x180016c57  mov     rbx, rcx
0x180016c5a  mov     edi, r8d
0x180016c5d  mov     rcx, [rcx]; string
0x180016c60  mov     rsi, rdx
0x180016c63  call    cs:__imp_WindowsDeleteString
0x180016c69  mov     r8, rbx
0x180016c6c  mov     qword ptr [rbx], 0
0x180016c73  mov     edx, edi
0x180016c75  mov     rcx, rsi
0x180016c78  mov     rbx, [rsp+28h+arg_0]
0x180016c7d  mov     rsi, [rsp+28h+arg_8]
0x180016c82  add     rsp, 20h
0x180016c86  pop     rdi
0x180016c87  jmp     cs:__imp_WindowsCreateString
```
