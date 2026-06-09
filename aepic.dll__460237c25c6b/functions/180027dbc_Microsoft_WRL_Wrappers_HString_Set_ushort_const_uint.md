# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180027dbc`
- end: `0x180027e02`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180026b04`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180027dfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027dd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027dd7`

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
0x180027dbc  mov     [rsp+arg_0], rbx
0x180027dc1  mov     [rsp+arg_8], rsi
0x180027dc6  push    rdi
0x180027dc7  sub     rsp, 20h
0x180027dcb  mov     rbx, rcx
0x180027dce  mov     edi, r8d
0x180027dd1  mov     rcx, [rcx]; string
0x180027dd4  mov     rsi, rdx
0x180027dd7  call    cs:__imp_WindowsDeleteString
0x180027ddd  mov     r8, rbx
0x180027de0  mov     qword ptr [rbx], 0
0x180027de7  mov     edx, edi
0x180027de9  mov     rcx, rsi
0x180027dec  mov     rbx, [rsp+28h+arg_0]
0x180027df1  mov     rsi, [rsp+28h+arg_8]
0x180027df6  add     rsp, 20h
0x180027dfa  pop     rdi
0x180027dfb  jmp     cs:__imp_WindowsCreateString
```
