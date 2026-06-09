# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18001dc6c`
- end: `0x18001dcb2`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001d6d0`
- `0x180029780`
- `0x1800373ec`
- `0x18004aa68`
- `0x18004d750`
- `0x18005a344`
- `0x180063508`
- `0x18007fec8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001dcab`

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
0x18001dc6c  mov     [rsp+arg_0], rbx
0x18001dc71  mov     [rsp+arg_8], rsi
0x18001dc76  push    rdi
0x18001dc77  sub     rsp, 20h
0x18001dc7b  mov     rbx, rcx
0x18001dc7e  mov     edi, r8d
0x18001dc81  mov     rcx, [rcx]; string
0x18001dc84  mov     rsi, rdx
0x18001dc87  call    cs:__imp_WindowsDeleteString
0x18001dc8d  mov     r8, rbx
0x18001dc90  mov     qword ptr [rbx], 0
0x18001dc97  mov     edx, edi
0x18001dc99  mov     rcx, rsi
0x18001dc9c  mov     rbx, [rsp+28h+arg_0]
0x18001dca1  mov     rsi, [rsp+28h+arg_8]
0x18001dca6  add     rsp, 20h
0x18001dcaa  pop     rdi
0x18001dcab  jmp     cs:__imp_WindowsCreateString
```
