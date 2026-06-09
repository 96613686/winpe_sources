# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180051e88`
- end: `0x180051ece`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180037c5c`
- `0x180058f80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180051ec7`

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
0x180051e88  mov     [rsp+arg_0], rbx
0x180051e8d  mov     [rsp+arg_8], rsi
0x180051e92  push    rdi
0x180051e93  sub     rsp, 20h
0x180051e97  mov     rbx, rcx
0x180051e9a  mov     edi, r8d
0x180051e9d  mov     rcx, [rcx]; string
0x180051ea0  mov     rsi, rdx
0x180051ea3  call    cs:__imp_WindowsDeleteString
0x180051ea9  mov     r8, rbx
0x180051eac  mov     qword ptr [rbx], 0
0x180051eb3  mov     edx, edi
0x180051eb5  mov     rcx, rsi
0x180051eb8  mov     rbx, [rsp+28h+arg_0]
0x180051ebd  mov     rsi, [rsp+28h+arg_8]
0x180051ec2  add     rsp, 20h
0x180051ec6  pop     rdi
0x180051ec7  jmp     cs:__imp_WindowsCreateString
```
