# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18002337c`
- end: `0x1800233c2`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180023100`
- `0x1800231f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800233bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023397`

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
0x18002337c  mov     [rsp+arg_0], rbx
0x180023381  mov     [rsp+arg_8], rsi
0x180023386  push    rdi
0x180023387  sub     rsp, 20h
0x18002338b  mov     rbx, rcx
0x18002338e  mov     edi, r8d
0x180023391  mov     rcx, [rcx]; string
0x180023394  mov     rsi, rdx
0x180023397  call    cs:__imp_WindowsDeleteString
0x18002339d  mov     r8, rbx
0x1800233a0  mov     qword ptr [rbx], 0
0x1800233a7  mov     edx, edi
0x1800233a9  mov     rcx, rsi
0x1800233ac  mov     rbx, [rsp+28h+arg_0]
0x1800233b1  mov     rsi, [rsp+28h+arg_8]
0x1800233b6  add     rsp, 20h
0x1800233ba  pop     rdi
0x1800233bb  jmp     cs:__imp_WindowsCreateString
```
