# DllRegisterServer

- ea: `0x1800b7b90`
- end: `0x1800b7cae`
- name: `DllRegisterServer`
- size: `286`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001ae80`
- `0x18004d240`
- `0x1800b7998`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1800b7c6e`
- `KERNEL32!GetModuleFileNameW` at `0x1800b7c6e`
- `Mso20Win32Client!Mso20Win32Client_59137` at `0x1800b7bef`
- `Mso20Win32Client!Mso20Win32Client_59137` at `0x1800b7c2d`
- `Mso20Win32Client!Mso20Win32Client_59137` at `0x1800b7bef`
- `Mso20Win32Client!Mso20Win32Client_59137` at `0x1800b7c2d`
- `ole32!StringFromGUID2` at `0x1800b7bc9`
- `ole32!StringFromGUID2` at `0x1800b7c03`
- `ole32!StringFromGUID2` at `0x1800b7bc9`
- `ole32!StringFromGUID2` at `0x1800b7c03`

## string_xrefs

- `0x1800b7bd7`: `CLSID\`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  wchar_t Destination[128]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR sz[128]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v3[128]; // [rsp+220h] [rbp+120h] BYREF
  WCHAR Filename[512]; // [rsp+320h] [rbp+220h] BYREF

  StringFromGUID2(&rguid, sz, 128);
  sub_18001AE80((wchar_t *)L"CLSID\\", Destination);
  Mso20Win32Client_59137(sz, Destination, 128);
  StringFromGUID2(&stru_1800CAD28, sz, 128);
  sub_18001AE80((wchar_t *)L"TypeLib\\", v3);
  Mso20Win32Client_59137(sz, v3, 128);
  sub_1800B7998(Destination, 0, L"QuillStoriesManager");
  sub_1800B7998(Destination, (__int64)L"NotInsertable", 0);
  GetModuleFileNameW(hModule, Filename, 0x200u);
  sub_1800B7998(Destination, (__int64)L"InprocServer32", Filename);
  return 0;
}

```

## disassembly

```asm
0x1800b7b90  mov     [rsp-8+arg_0], rbx
0x1800b7b95  push    rbp
0x1800b7b96  lea     rbp, [rsp-630h]
0x1800b7b9e  sub     rsp, 730h
0x1800b7ba5  mov     rax, cs:__security_cookie
0x1800b7bac  xor     rax, rsp
0x1800b7baf  mov     [rbp+630h+var_10], rax
0x1800b7bb6  mov     ebx, 80h
0x1800b7bbb  lea     rdx, [rbp+630h+sz]; lpsz
0x1800b7bbf  mov     r8d, ebx; cchMax
0x1800b7bc2  lea     rcx, rguid; rguid
0x1800b7bc9  call    cs:StringFromGUID2
0x1800b7bcf  mov     r8d, ebx
0x1800b7bd2  lea     rdx, [rsp+730h+Destination]; Destination
0x1800b7bd7  lea     rcx, aClsid; "CLSID\\"
0x1800b7bde  call    sub_18001AE80
0x1800b7be3  mov     r8d, ebx
0x1800b7be6  lea     rdx, [rsp+730h+Destination]
0x1800b7beb  lea     rcx, [rbp+630h+sz]
0x1800b7bef  call    cs:Mso20Win32Client_59137
0x1800b7bf5  mov     r8d, ebx; cchMax
0x1800b7bf8  lea     rdx, [rbp+630h+sz]; lpsz
0x1800b7bfc  lea     rcx, stru_1800CAD28; rguid
0x1800b7c03  call    cs:StringFromGUID2
0x1800b7c09  mov     r8d, ebx
0x1800b7c0c  lea     rdx, [rbp+630h+var_510]; Destination
0x1800b7c13  lea     rcx, aTypelib; "TypeLib\\"
0x1800b7c1a  call    sub_18001AE80
0x1800b7c1f  mov     r8d, ebx
0x1800b7c22  lea     rdx, [rbp+630h+var_510]
0x1800b7c29  lea     rcx, [rbp+630h+sz]
0x1800b7c2d  call    cs:Mso20Win32Client_59137
0x1800b7c33  lea     r8, aQuillstoriesma; "QuillStoriesManager"
0x1800b7c3a  xor     edx, edx
0x1800b7c3c  lea     rcx, [rsp+730h+Destination]
0x1800b7c41  call    sub_1800B7998
0x1800b7c46  xor     r8d, r8d
0x1800b7c49  lea     rdx, aNotinsertable; "NotInsertable"
0x1800b7c50  lea     rcx, [rsp+730h+Destination]
0x1800b7c55  call    sub_1800B7998
0x1800b7c5a  mov     rcx, cs:hModule; hModule
0x1800b7c61  lea     rdx, [rbp+630h+Filename]; lpFilename
0x1800b7c68  mov     r8d, 200h; nSize
0x1800b7c6e  call    cs:GetModuleFileNameW
0x1800b7c74  lea     r8, [rbp+630h+Filename]
0x1800b7c7b  lea     rdx, aInprocserver32; "InprocServer32"
0x1800b7c82  lea     rcx, [rsp+730h+Destination]
0x1800b7c87  call    sub_1800B7998
0x1800b7c8c  xor     eax, eax
0x1800b7c8e  mov     rcx, [rbp+630h+var_10]
0x1800b7c95  xor     rcx, rsp; StackCookie
0x1800b7c98  call    __security_check_cookie
0x1800b7c9d  mov     rbx, [rsp+730h+arg_0]
0x1800b7ca5  add     rsp, 730h
0x1800b7cac  pop     rbp
0x1800b7cad  retn
```
