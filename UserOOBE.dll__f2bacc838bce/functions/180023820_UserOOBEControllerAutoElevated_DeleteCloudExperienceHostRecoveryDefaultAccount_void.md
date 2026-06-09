# UserOOBEControllerAutoElevated::DeleteCloudExperienceHostRecoveryDefaultAccount(void)

- ea: `0x180023820`
- end: `0x1800238a3`
- name: `?DeleteCloudExperienceHostRecoveryDefaultAccount@UserOOBEControllerAutoElevated@@UEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(UserOOBEControllerAutoElevated *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x180023820`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023857`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023857`

## string_xrefs

- `0x18002386b`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 __fastcall UserOOBEControllerAutoElevated::DeleteCloudExperienceHostRecoveryDefaultAccount(
        UserOOBEControllerAutoElevated *this)
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
    v2 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 56LL))(v6);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49A,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v1,
      ppv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v6);
  return v2;
}

```

## disassembly

```asm
0x180023820  push    rbx
0x180023822  sub     rsp, 30h
0x180023826  mov     [rsp+38h+arg_8], 0
0x18002382f  lea     rcx, [rsp+38h+arg_8]
0x180023834  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023839  lea     rax, [rsp+38h+arg_8]
0x18002383e  mov     qword ptr [rsp+38h+ppv], rax; int
0x180023843  lea     r9, _GUID_3853c14b_e028_4cea_93ea_ae9cf14aa9dd; riid
0x18002384a  xor     edx, edx; pUnkOuter
0x18002384c  lea     r8d, [rdx+1]; dwClsContext
0x180023850  lea     rcx, _GUID_2b2cad40_19c1_4794_b32d_397e41d5e8a7; rclsid
0x180023857  call    cs:__imp_CoCreateInstance
0x18002385d  mov     ebx, eax
0x18002385f  test    eax, eax
0x180023861  jns     short loc_18002387E
0x180023863  mov     rcx, [rsp+38h]; this
0x180023868  mov     r9d, eax; char *
0x18002386b  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180023872  mov     edx, 49Ah; void *
0x180023877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002387c  jmp     short loc_180023891
0x18002387e  mov     rcx, [rsp+38h+arg_8]
0x180023883  mov     rax, [rcx]
0x180023886  mov     rax, [rax+38h]
0x18002388a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002388f  mov     ebx, eax
0x180023891  lea     rcx, [rsp+38h+arg_8]
0x180023896  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002389b  mov     eax, ebx
0x18002389d  add     rsp, 30h
0x1800238a1  pop     rbx
0x1800238a2  retn
```
