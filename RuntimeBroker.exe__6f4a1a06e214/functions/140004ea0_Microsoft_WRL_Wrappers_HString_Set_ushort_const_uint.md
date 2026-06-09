# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x140004ea0`
- end: `0x140004ee6`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400027d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140004edf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140004ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140004ebb`

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
0x140004ea0  mov     [rsp+arg_0], rbx
0x140004ea5  mov     [rsp+arg_8], rsi
0x140004eaa  push    rdi
0x140004eab  sub     rsp, 20h
0x140004eaf  mov     rbx, rcx
0x140004eb2  mov     edi, r8d
0x140004eb5  mov     rcx, [rcx]; string
0x140004eb8  mov     rsi, rdx
0x140004ebb  call    cs:__imp_WindowsDeleteString
0x140004ec1  mov     r8, rbx
0x140004ec4  mov     qword ptr [rbx], 0
0x140004ecb  mov     edx, edi
0x140004ecd  mov     rcx, rsi
0x140004ed0  mov     rbx, [rsp+28h+arg_0]
0x140004ed5  mov     rsi, [rsp+28h+arg_8]
0x140004eda  add     rsp, 20h
0x140004ede  pop     rdi
0x140004edf  jmp     cs:__imp_WindowsCreateString
```
