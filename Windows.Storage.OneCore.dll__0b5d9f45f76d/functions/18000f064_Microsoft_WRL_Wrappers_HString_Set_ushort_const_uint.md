# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18000f064`
- end: `0x18000f0aa`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000e20c`
- `0x180010cb8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f07f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f07f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000f0a3`

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
0x18000f064  mov     [rsp+arg_0], rbx
0x18000f069  mov     [rsp+arg_8], rsi
0x18000f06e  push    rdi
0x18000f06f  sub     rsp, 20h
0x18000f073  mov     rbx, rcx
0x18000f076  mov     edi, r8d
0x18000f079  mov     rcx, [rcx]; string
0x18000f07c  mov     rsi, rdx
0x18000f07f  call    cs:__imp_WindowsDeleteString
0x18000f085  mov     r8, rbx
0x18000f088  mov     qword ptr [rbx], 0
0x18000f08f  mov     edx, edi
0x18000f091  mov     rcx, rsi
0x18000f094  mov     rbx, [rsp+28h+arg_0]
0x18000f099  mov     rsi, [rsp+28h+arg_8]
0x18000f09e  add     rsp, 20h
0x18000f0a2  pop     rdi
0x18000f0a3  jmp     cs:__imp_WindowsCreateString
```
