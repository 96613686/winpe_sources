# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18001d728`
- end: `0x18001d76e`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180013be0`
- `0x18003fb8c`
- `0x18003ff70`
- `0x180051d0c`
- `0x18005249c`
- `0x18005387c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001d767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d743`

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
0x18001d728  mov     [rsp+arg_0], rbx
0x18001d72d  mov     [rsp+arg_8], rsi
0x18001d732  push    rdi
0x18001d733  sub     rsp, 20h
0x18001d737  mov     rbx, rcx
0x18001d73a  mov     edi, r8d
0x18001d73d  mov     rcx, [rcx]; string
0x18001d740  mov     rsi, rdx
0x18001d743  call    cs:__imp_WindowsDeleteString
0x18001d749  mov     r8, rbx
0x18001d74c  mov     qword ptr [rbx], 0
0x18001d753  mov     edx, edi
0x18001d755  mov     rcx, rsi
0x18001d758  mov     rbx, [rsp+28h+arg_0]
0x18001d75d  mov     rsi, [rsp+28h+arg_8]
0x18001d762  add     rsp, 20h
0x18001d766  pop     rdi
0x18001d767  jmp     cs:__imp_WindowsCreateString
```
