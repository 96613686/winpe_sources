# UserOOBEControllerAutoElevated::TryRefreshOneSettingsFeatureConfigurations(uchar *)

- ea: `0x1800278e0`
- end: `0x180027972`
- name: `?TryRefreshOneSettingsFeatureConfigurations@UserOOBEControllerAutoElevated@@UEAAJPEAE@Z`
- size: `146`
- prototype: `__int64 __fastcall(UserOOBEControllerAutoElevated *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x1800278e0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002791e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002791e`

## string_xrefs

- `0x180027932`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserOOBEControllerAutoElevated::TryRefreshOneSettingsFeatureConfigurations(
        UserOOBEControllerAutoElevated *this,
        unsigned __int8 *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  v3 = CoCreateInstance(
         &GUID_2b2cad40_19c1_4794_b32d_397e41d5e8a7,
         0,
         1u,
         &GUID_3853c14b_e028_4cea_93ea_ae9cf14aa9dd,
         &v8);
  v4 = v3;
  if ( v3 >= 0 )
    v4 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int8 *))(*(_QWORD *)v8 + 72LL))(v8, a2);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A6,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  return v4;
}

```

## disassembly

```asm
0x1800278e0  mov     [rsp+arg_0], rbx
0x1800278e5  push    rdi
0x1800278e6  sub     rsp, 30h
0x1800278ea  mov     rdi, rdx
0x1800278ed  mov     [rsp+38h+arg_10], 0
0x1800278f6  lea     rcx, [rsp+38h+arg_10]
0x1800278fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027900  lea     rax, [rsp+38h+arg_10]
0x180027905  mov     qword ptr [rsp+38h+ppv], rax; int
0x18002790a  lea     r9, _GUID_3853c14b_e028_4cea_93ea_ae9cf14aa9dd; riid
0x180027911  xor     edx, edx; pUnkOuter
0x180027913  lea     r8d, [rdx+1]; dwClsContext
0x180027917  lea     rcx, _GUID_2b2cad40_19c1_4794_b32d_397e41d5e8a7; rclsid
0x18002791e  call    cs:__imp_CoCreateInstance
0x180027924  mov     ebx, eax
0x180027926  test    eax, eax
0x180027928  jns     short loc_180027945
0x18002792a  mov     rcx, [rsp+38h]; this
0x18002792f  mov     r9d, eax; char *
0x180027932  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180027939  mov     edx, 4A6h; void *
0x18002793e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027943  jmp     short loc_18002795B
0x180027945  mov     rcx, [rsp+38h+arg_10]
0x18002794a  mov     rax, [rcx]
0x18002794d  mov     rdx, rdi
0x180027950  mov     rax, [rax+48h]
0x180027954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027959  mov     ebx, eax
0x18002795b  lea     rcx, [rsp+38h+arg_10]
0x180027960  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027965  mov     eax, ebx
0x180027967  mov     rbx, [rsp+38h+arg_0]
0x18002796c  add     rsp, 30h
0x180027970  pop     rdi
0x180027971  retn
```
