# UserOOBEControllerAutoElevated::Restart(void)

- ea: `0x180026920`
- end: `0x1800269a3`
- name: `?Restart@UserOOBEControllerAutoElevated@@UEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(UserOOBEControllerAutoElevated *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x180026920`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026957`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026957`

## string_xrefs

- `0x18002696b`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 __fastcall UserOOBEControllerAutoElevated::Restart(UserOOBEControllerAutoElevated *this)
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
    v2 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 32LL))(v6);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48E,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v1,
      ppv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v6);
  return v2;
}

```

## disassembly

```asm
0x180026920  push    rbx
0x180026922  sub     rsp, 30h
0x180026926  mov     [rsp+38h+arg_8], 0
0x18002692f  lea     rcx, [rsp+38h+arg_8]
0x180026934  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026939  lea     rax, [rsp+38h+arg_8]
0x18002693e  mov     qword ptr [rsp+38h+ppv], rax; int
0x180026943  lea     r9, _GUID_3853c14b_e028_4cea_93ea_ae9cf14aa9dd; riid
0x18002694a  xor     edx, edx; pUnkOuter
0x18002694c  lea     r8d, [rdx+1]; dwClsContext
0x180026950  lea     rcx, _GUID_2b2cad40_19c1_4794_b32d_397e41d5e8a7; rclsid
0x180026957  call    cs:__imp_CoCreateInstance
0x18002695d  mov     ebx, eax
0x18002695f  test    eax, eax
0x180026961  jns     short loc_18002697E
0x180026963  mov     rcx, [rsp+38h]; this
0x180026968  mov     r9d, eax; char *
0x18002696b  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180026972  mov     edx, 48Eh; void *
0x180026977  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002697c  jmp     short loc_180026991
0x18002697e  mov     rcx, [rsp+38h+arg_8]
0x180026983  mov     rax, [rcx]
0x180026986  mov     rax, [rax+20h]
0x18002698a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002698f  mov     ebx, eax
0x180026991  lea     rcx, [rsp+38h+arg_8]
0x180026996  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002699b  mov     eax, ebx
0x18002699d  add     rsp, 30h
0x1800269a1  pop     rbx
0x1800269a2  retn
```
