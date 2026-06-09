# UserOOBEControllerAutoElevated::LaunchCommandPrompt(void)

- ea: `0x180025ec0`
- end: `0x180025f43`
- name: `?LaunchCommandPrompt@UserOOBEControllerAutoElevated@@UEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(UserOOBEControllerAutoElevated *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x180025ec0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025ef7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025ef7`

## string_xrefs

- `0x180025f0b`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 __fastcall UserOOBEControllerAutoElevated::LaunchCommandPrompt(UserOOBEControllerAutoElevated *this)
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
    v2 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 80LL))(v6);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AC,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v1,
      ppv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v6);
  return v2;
}

```

## disassembly

```asm
0x180025ec0  push    rbx
0x180025ec2  sub     rsp, 30h
0x180025ec6  mov     [rsp+38h+arg_8], 0
0x180025ecf  lea     rcx, [rsp+38h+arg_8]
0x180025ed4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025ed9  lea     rax, [rsp+38h+arg_8]
0x180025ede  mov     qword ptr [rsp+38h+ppv], rax; int
0x180025ee3  lea     r9, _GUID_3853c14b_e028_4cea_93ea_ae9cf14aa9dd; riid
0x180025eea  xor     edx, edx; pUnkOuter
0x180025eec  lea     r8d, [rdx+1]; dwClsContext
0x180025ef0  lea     rcx, _GUID_2b2cad40_19c1_4794_b32d_397e41d5e8a7; rclsid
0x180025ef7  call    cs:__imp_CoCreateInstance
0x180025efd  mov     ebx, eax
0x180025eff  test    eax, eax
0x180025f01  jns     short loc_180025F1E
0x180025f03  mov     rcx, [rsp+38h]; this
0x180025f08  mov     r9d, eax; char *
0x180025f0b  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180025f12  mov     edx, 4ACh; void *
0x180025f17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f1c  jmp     short loc_180025F31
0x180025f1e  mov     rcx, [rsp+38h+arg_8]
0x180025f23  mov     rax, [rcx]
0x180025f26  mov     rax, [rax+50h]
0x180025f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f2f  mov     ebx, eax
0x180025f31  lea     rcx, [rsp+38h+arg_8]
0x180025f36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025f3b  mov     eax, ebx
0x180025f3d  add     rsp, 30h
0x180025f41  pop     rbx
0x180025f42  retn
```
