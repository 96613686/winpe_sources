# DllUnregisterServer

- ea: `0x1800b7cb0`
- end: `0x1800b7d9d`
- name: `DllUnregisterServer`
- size: `237`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001ae80`
- `0x18004d240`
- `0x18004d260`
- `0x180094fa8`
- `0x1800b7874`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1800b7d16`
- `ole32!StringFromGUID2` at `0x1800b7d16`

## string_xrefs

- `0x1800b7d25`: `CLSID\`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // r8
  __int64 v1; // r8
  __int64 v2; // r8
  wchar_t Destination[96]; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t v5[96]; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR sz[96]; // [rsp+1A0h] [rbp+A0h] BYREF

  memset(Destination, 0, 180);
  memset(v5, 0, 180);
  StringFromGUID2(&rguid, sz, 90);
  sub_18001AE80((wchar_t *)L"CLSID\\", Destination);
  sub_180094FA8(sz, Destination);
  sub_1800B7874(Destination, v5, v0, (__int64)L"\\NotInsertable");
  sub_1800B7874(Destination, v5, v1, (__int64)L"\\InprocServer32");
  return sub_1800B7874(Destination, v5, v2, 0);
}

```

## disassembly

```asm
0x1800b7cb0  mov     [rsp-8+arg_0], rdi
0x1800b7cb5  push    rbp
0x1800b7cb6  lea     rbp, [rsp-170h]
0x1800b7cbe  sub     rsp, 270h
0x1800b7cc5  mov     rax, cs:__security_cookie
0x1800b7ccc  xor     rax, rsp
0x1800b7ccf  mov     [rbp+170h+var_10], rax
0x1800b7cd6  xor     edi, edi
0x1800b7cd8  lea     rcx, [rsp+270h+var_24E]; void *
0x1800b7cdd  xor     edx, edx; Val
0x1800b7cdf  mov     [rsp+270h+Destination], di
0x1800b7ce4  mov     r8d, 0B2h; Size
0x1800b7cea  call    memset
0x1800b7cef  xor     edx, edx; Val
0x1800b7cf1  mov     [rbp+170h+var_190], di
0x1800b7cf5  mov     r8d, 0B2h; Size
0x1800b7cfb  lea     rcx, [rbp+170h+var_18E]; void *
0x1800b7cff  call    memset
0x1800b7d04  lea     r8d, [rdi+5Ah]; cchMax
0x1800b7d08  lea     rdx, [rbp+170h+sz]; lpsz
0x1800b7d0f  lea     rcx, rguid; rguid
0x1800b7d16  call    cs:StringFromGUID2
0x1800b7d1c  lea     r8d, [rdi+5Ah]
0x1800b7d20  lea     rdx, [rsp+270h+Destination]; Destination
0x1800b7d25  lea     rcx, aClsid; "CLSID\\"
0x1800b7d2c  call    sub_18001AE80
0x1800b7d31  lea     rdx, [rsp+270h+Destination]
0x1800b7d36  lea     rcx, [rbp+170h+sz]
0x1800b7d3d  call    sub_180094FA8
0x1800b7d42  lea     r9, aNotinsertable_0; "\\NotInsertable"
0x1800b7d49  lea     rdx, [rbp+170h+var_190]
0x1800b7d4d  lea     rcx, [rsp+270h+Destination]
0x1800b7d52  call    sub_1800B7874
0x1800b7d57  lea     r9, aInprocserver32_0; "\\InprocServer32"
0x1800b7d5e  lea     rdx, [rbp+170h+var_190]
0x1800b7d62  lea     rcx, [rsp+270h+Destination]
0x1800b7d67  call    sub_1800B7874
0x1800b7d6c  xor     r9d, r9d
0x1800b7d6f  lea     rdx, [rbp+170h+var_190]
0x1800b7d73  lea     rcx, [rsp+270h+Destination]
0x1800b7d78  call    sub_1800B7874
0x1800b7d7d  mov     rcx, [rbp+170h+var_10]
0x1800b7d84  xor     rcx, rsp; StackCookie
0x1800b7d87  call    __security_check_cookie
0x1800b7d8c  mov     rdi, [rsp+270h+arg_0]
0x1800b7d94  add     rsp, 270h
0x1800b7d9b  pop     rbp
0x1800b7d9c  retn
```
