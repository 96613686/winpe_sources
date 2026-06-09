# UserOOBEControllerAutoElevated::SyncTimeZone(void)

- ea: `0x1800270a0`
- end: `0x180027123`
- name: `?SyncTimeZone@UserOOBEControllerAutoElevated@@UEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(UserOOBEControllerAutoElevated *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x1800270a0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800270d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800270d7`

## string_xrefs

- `0x1800270eb`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 __fastcall UserOOBEControllerAutoElevated::SyncTimeZone(UserOOBEControllerAutoElevated *this)
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
    v2 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 64LL))(v6);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A0,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v1,
      ppv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v6);
  return v2;
}

```

## disassembly

```asm
0x1800270a0  push    rbx
0x1800270a2  sub     rsp, 30h
0x1800270a6  mov     [rsp+38h+arg_8], 0
0x1800270af  lea     rcx, [rsp+38h+arg_8]
0x1800270b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800270b9  lea     rax, [rsp+38h+arg_8]
0x1800270be  mov     qword ptr [rsp+38h+ppv], rax; int
0x1800270c3  lea     r9, _GUID_3853c14b_e028_4cea_93ea_ae9cf14aa9dd; riid
0x1800270ca  xor     edx, edx; pUnkOuter
0x1800270cc  lea     r8d, [rdx+1]; dwClsContext
0x1800270d0  lea     rcx, _GUID_2b2cad40_19c1_4794_b32d_397e41d5e8a7; rclsid
0x1800270d7  call    cs:__imp_CoCreateInstance
0x1800270dd  mov     ebx, eax
0x1800270df  test    eax, eax
0x1800270e1  jns     short loc_1800270FE
0x1800270e3  mov     rcx, [rsp+38h]; this
0x1800270e8  mov     r9d, eax; char *
0x1800270eb  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800270f2  mov     edx, 4A0h; void *
0x1800270f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800270fc  jmp     short loc_180027111
0x1800270fe  mov     rcx, [rsp+38h+arg_8]
0x180027103  mov     rax, [rcx]
0x180027106  mov     rax, [rax+40h]
0x18002710a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002710f  mov     ebx, eax
0x180027111  lea     rcx, [rsp+38h+arg_8]
0x180027116  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002711b  mov     eax, ebx
0x18002711d  add     rsp, 30h
0x180027121  pop     rbx
0x180027122  retn
```
