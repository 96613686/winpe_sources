# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x1800185e4`
- end: `0x18001862a`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180014990`
- `0x180020a1c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018623`

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
0x1800185e4  mov     [rsp+arg_0], rbx
0x1800185e9  mov     [rsp+arg_8], rsi
0x1800185ee  push    rdi
0x1800185ef  sub     rsp, 20h
0x1800185f3  mov     rbx, rcx
0x1800185f6  mov     edi, r8d
0x1800185f9  mov     rcx, [rcx]; string
0x1800185fc  mov     rsi, rdx
0x1800185ff  call    cs:__imp_WindowsDeleteString
0x180018605  mov     r8, rbx
0x180018608  mov     qword ptr [rbx], 0
0x18001860f  mov     edx, edi
0x180018611  mov     rcx, rsi
0x180018614  mov     rbx, [rsp+28h+arg_0]
0x180018619  mov     rsi, [rsp+28h+arg_8]
0x18001861e  add     rsp, 20h
0x180018622  pop     rdi
0x180018623  jmp     cs:__imp_WindowsCreateString
```
