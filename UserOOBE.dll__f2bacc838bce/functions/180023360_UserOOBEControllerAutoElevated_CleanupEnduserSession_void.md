# UserOOBEControllerAutoElevated::CleanupEnduserSession(void)

- ea: `0x180023360`
- end: `0x1800233e3`
- name: `?CleanupEnduserSession@UserOOBEControllerAutoElevated@@UEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(UserOOBEControllerAutoElevated *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x180023360`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023397`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023397`

## string_xrefs

- `0x1800233ab`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserOOBEControllerAutoElevated::CleanupEnduserSession(UserOOBEControllerAutoElevated *this)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v6);
  v1 = CoCreateInstance(
         &GUID_2b2cad40_19c1_4794_b32d_397e41d5e8a7,
         0,
         1u,
         &GUID_3853c14b_e028_4cea_93ea_ae9cf14aa9dd,
         &v6);
  v2 = v1;
  if ( v1 >= 0 )
    v2 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 96LL))(v6);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B2,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v1,
      ppv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v6);
  return v2;
}

```

## disassembly

```asm
0x180023360  push    rbx
0x180023362  sub     rsp, 30h
0x180023366  mov     [rsp+38h+arg_8], 0
0x18002336f  lea     rcx, [rsp+38h+arg_8]
0x180023374  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023379  lea     rax, [rsp+38h+arg_8]
0x18002337e  mov     qword ptr [rsp+38h+ppv], rax; int
0x180023383  lea     r9, _GUID_3853c14b_e028_4cea_93ea_ae9cf14aa9dd; riid
0x18002338a  xor     edx, edx; pUnkOuter
0x18002338c  lea     r8d, [rdx+1]; dwClsContext
0x180023390  lea     rcx, _GUID_2b2cad40_19c1_4794_b32d_397e41d5e8a7; rclsid
0x180023397  call    cs:__imp_CoCreateInstance
0x18002339d  mov     ebx, eax
0x18002339f  test    eax, eax
0x1800233a1  jns     short loc_1800233BE
0x1800233a3  mov     rcx, [rsp+38h]; this
0x1800233a8  mov     r9d, eax; char *
0x1800233ab  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800233b2  mov     edx, 4B2h; void *
0x1800233b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800233bc  jmp     short loc_1800233D1
0x1800233be  mov     rcx, [rsp+38h+arg_8]
0x1800233c3  mov     rax, [rcx]
0x1800233c6  mov     rax, [rax+60h]
0x1800233ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233cf  mov     ebx, eax
0x1800233d1  lea     rcx, [rsp+38h+arg_8]
0x1800233d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800233db  mov     eax, ebx
0x1800233dd  add     rsp, 30h
0x1800233e1  pop     rbx
0x1800233e2  retn
```
