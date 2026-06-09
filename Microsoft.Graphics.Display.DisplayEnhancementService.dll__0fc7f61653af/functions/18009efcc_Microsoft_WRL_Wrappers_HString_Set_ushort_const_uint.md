# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18009efcc`
- end: `0x18009f012`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18009c934`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009efe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009efe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009f00b`

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
0x18009efcc  mov     [rsp+arg_0], rbx
0x18009efd1  mov     [rsp+arg_8], rsi
0x18009efd6  push    rdi
0x18009efd7  sub     rsp, 20h
0x18009efdb  mov     rbx, rcx
0x18009efde  mov     edi, r8d
0x18009efe1  mov     rcx, [rcx]; string
0x18009efe4  mov     rsi, rdx
0x18009efe7  call    cs:__imp_WindowsDeleteString
0x18009efed  mov     r8, rbx
0x18009eff0  mov     qword ptr [rbx], 0
0x18009eff7  mov     edx, edi
0x18009eff9  mov     rcx, rsi
0x18009effc  mov     rbx, [rsp+28h+arg_0]
0x18009f001  mov     rsi, [rsp+28h+arg_8]
0x18009f006  add     rsp, 20h
0x18009f00a  pop     rdi
0x18009f00b  jmp     cs:__imp_WindowsCreateString
```
