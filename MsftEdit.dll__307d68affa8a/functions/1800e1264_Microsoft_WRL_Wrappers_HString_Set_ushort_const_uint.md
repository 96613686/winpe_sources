# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x1800e1264`
- end: `0x1800e12aa`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800d7984`
- `0x1800e1204`
- `0x1800e7b3c`
- `0x1801f5f18`
- `0x1801f5f8c`
- `0x1801f6420`
- `0x1801f750c`
- `0x180205168`
- `0x180275d5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e127f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e127f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e12a3`

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
0x1800e1264  mov     [rsp+arg_0], rbx
0x1800e1269  mov     [rsp+arg_8], rsi
0x1800e126e  push    rdi
0x1800e126f  sub     rsp, 20h
0x1800e1273  mov     rbx, rcx
0x1800e1276  mov     edi, r8d
0x1800e1279  mov     rcx, [rcx]; string
0x1800e127c  mov     rsi, rdx
0x1800e127f  call    cs:__imp_WindowsDeleteString
0x1800e1285  mov     r8, rbx
0x1800e1288  mov     qword ptr [rbx], 0
0x1800e128f  mov     edx, edi
0x1800e1291  mov     rcx, rsi
0x1800e1294  mov     rbx, [rsp+28h+arg_0]
0x1800e1299  mov     rsi, [rsp+28h+arg_8]
0x1800e129e  add     rsp, 20h
0x1800e12a2  pop     rdi
0x1800e12a3  jmp     cs:__imp_WindowsCreateString
```
