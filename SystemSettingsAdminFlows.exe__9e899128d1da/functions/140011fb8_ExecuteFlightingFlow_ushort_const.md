# ExecuteFlightingFlow(ushort const *)

- ea: `0x140011fb8`
- end: `0x140012082`
- name: `?ExecuteFlightingFlow@@YAJPEBG@Z`
- size: `202`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x140011fb8`
- `0x14001a2a0`
- `0x14001f3d4`
- `0x14007d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140012015`
- `ole32!CoCreateInstance` at `0x140012015`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140011fd4`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140011fd4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x14001206a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x14001206a`

## string_xrefs

- `0x140012049`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ExecuteFlightingFlow(const unsigned __int16 *a1, __int64 a2)
{
  HRESULT v3; // ebx
  __int64 v4; // rdx
  int ppv; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  int v8; // [rsp+58h] [rbp+18h]
  LPVOID v9; // [rsp+60h] [rbp+20h] BYREF

  v8 = RoInitialize(1, a2);
  v9 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  v3 = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_4ab30937_1c1f_4ffd_b66f_b3cf3d092bd6, &v9);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v9 + 24LL))(v9, a1);
    if ( v3 >= 0 )
      goto LABEL_6;
    v4 = 1744;
  }
  else
  {
    v4 = 1742;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
    (const char *)(unsigned int)v3,
    ppv);
LABEL_6:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  if ( v8 >= 0 )
    RoUninitialize();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140011fb8  mov     [rsp-8+arg_0], rbx
0x140011fbd  mov     [rsp-8+arg_18], rdi
0x140011fc2  push    rbp
0x140011fc3  mov     rbp, rsp
0x140011fc6  sub     rsp, 40h
0x140011fca  mov     rdi, rcx
0x140011fcd  mov     ebx, 1
0x140011fd2  mov     ecx, ebx
0x140011fd4  call    cs:__imp_RoInitialize
0x140011fda  mov     [rbp+arg_8], eax
0x140011fdd  lea     rax, [rbp+arg_8]
0x140011fe1  mov     [rbp+var_10], rax
0x140011fe5  mov     [rbp+var_8], bl
0x140011fe8  mov     [rbp+arg_10], 0
0x140011ff0  lea     rcx, [rbp+arg_10]
0x140011ff4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011ff9  lea     rax, [rbp+arg_10]
0x140011ffd  mov     qword ptr [rsp+40h+ppv], rax; int
0x140012002  lea     r9, _GUID_4ab30937_1c1f_4ffd_b66f_b3cf3d092bd6; riid
0x140012009  mov     r8d, ebx; dwClsContext
0x14001200c  xor     edx, edx; pUnkOuter
0x14001200e  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x140012015  call    cs:__imp_CoCreateInstance
0x14001201b  mov     ebx, eax
0x14001201d  test    eax, eax
0x14001201f  jns     short loc_140012028
0x140012021  mov     edx, 6CEh
0x140012026  jmp     short loc_140012046
0x140012028  mov     rcx, [rbp+arg_10]
0x14001202c  mov     rax, [rcx]
0x14001202f  mov     rdx, rdi
0x140012032  mov     rax, [rax+18h]
0x140012036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001203b  mov     ebx, eax
0x14001203d  test    eax, eax
0x14001203f  jns     short loc_14001205A
0x140012041  mov     edx, 6D0h; void *
0x140012046  mov     r9d, ebx; char *
0x140012049  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x140012050  mov     rcx, [rbp+8]; this
0x140012054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012059  nop
0x14001205a  lea     rcx, [rbp+arg_10]
0x14001205e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140012063  nop
0x140012064  cmp     [rbp+arg_8], 0
0x140012068  jl      short loc_140012070
0x14001206a  call    cs:__imp_RoUninitialize
0x140012070  mov     eax, ebx
0x140012072  mov     rbx, [rsp+40h+arg_0]
0x140012077  mov     rdi, [rsp+40h+arg_18]
0x14001207c  add     rsp, 40h
0x140012080  pop     rbp
0x140012081  retn
```
