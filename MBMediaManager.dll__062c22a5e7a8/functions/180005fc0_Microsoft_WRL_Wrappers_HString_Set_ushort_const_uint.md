# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180005fc0`
- end: `0x180006006`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `11`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003108`
- `0x180004980`
- `0x180005d10`
- `0x180005d3c`
- `0x180011450`
- `0x1800164ec`
- `0x18001a494`
- `0x18001a864`
- `0x18001dc70`
- `0x1800208b0`
- `0x18004d970`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005fdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005fdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180005fff`

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
0x180005fc0  mov     [rsp+arg_0], rbx
0x180005fc5  mov     [rsp+arg_8], rsi
0x180005fca  push    rdi
0x180005fcb  sub     rsp, 20h
0x180005fcf  mov     rbx, rcx
0x180005fd2  mov     edi, r8d
0x180005fd5  mov     rcx, [rcx]; string
0x180005fd8  mov     rsi, rdx
0x180005fdb  call    cs:__imp_WindowsDeleteString
0x180005fe1  mov     r8, rbx
0x180005fe4  mov     qword ptr [rbx], 0
0x180005feb  mov     edx, edi
0x180005fed  mov     rcx, rsi
0x180005ff0  mov     rbx, [rsp+28h+arg_0]
0x180005ff5  mov     rsi, [rsp+28h+arg_8]
0x180005ffa  add     rsp, 20h
0x180005ffe  pop     rdi
0x180005fff  jmp     cs:__imp_WindowsCreateString
```
