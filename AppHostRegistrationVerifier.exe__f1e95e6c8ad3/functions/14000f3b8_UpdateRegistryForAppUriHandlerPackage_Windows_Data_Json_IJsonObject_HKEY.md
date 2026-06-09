# UpdateRegistryForAppUriHandlerPackage(Windows::Data::Json::IJsonObject *,HKEY__ *)

- ea: `0x14000f3b8`
- end: `0x14000f76e`
- name: `?UpdateRegistryForAppUriHandlerPackage@@YAXPEAUIJsonObject@Json@Data@Windows@@PEAUHKEY__@@@Z`
- size: `950`
- prototype: `void __fastcall(struct Windows::Data::Json::IJsonObject *, HKEY)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000eb7c`
- `0x14000ed9c`

## callees

- `0x140002210`
- `0x140003cd8`
- `0x14000834c`
- `0x14000a934`
- `0x14000c2c0`
- `0x14000d49c`
- `0x14000f3b8`
- `0x14000fbb0`
- `0x14000fc20`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f47c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f513`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f5b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f62c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f676`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f6af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f6f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f47c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f513`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f5b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f62c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f676`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f6af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f6f0`

## string_xrefs

- `0x14000f6a5`: `LastValidationAttemptTime`
- `0x14000f472`: `AllowedPaths`
- `0x14000f509`: `ExcludedPaths`

## pseudocode

```c
void __fastcall UpdateRegistryForAppUriHandlerPackage(struct Windows::Data::Json::IJsonObject *a1, HKEY a2)
{
  __int64 (__fastcall *v4)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *); // rbx
  __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  int (__fastcall *v9)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *); // rbx
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // r8d
  int (__fastcall *v13)(struct Windows::Data::Json::IJsonObject *, _QWORD, char *); // rbx
  __int64 v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // r8d
  int (__fastcall *v17)(struct Windows::Data::Json::IJsonObject *, _QWORD, _BYTE *); // rbx
  __int64 v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // r8d
  unsigned int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // eax
  unsigned int v26; // r8d
  int lpData; // [rsp+20h] [rbp-39h]
  unsigned int lpDataa; // [rsp+20h] [rbp-39h]
  unsigned int lpDatab; // [rsp+20h] [rbp-39h]
  unsigned int lpDatac; // [rsp+20h] [rbp-39h]
  unsigned int lpDatad; // [rsp+20h] [rbp-39h]
  unsigned int lpDatae; // [rsp+20h] [rbp-39h]
  unsigned int lpDataf; // [rsp+20h] [rbp-39h]
  unsigned int lpDatag; // [rsp+20h] [rbp-39h]
  char v35; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v36[3]; // [rsp+31h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-25h] BYREF
  __int64 v38; // [rsp+38h] [rbp-21h] BYREF
  __int64 v39; // [rsp+40h] [rbp-19h] BYREF
  BYTE v40[8]; // [rsp+48h] [rbp-11h] BYREF
  BYTE v41[8]; // [rsp+50h] [rbp-9h] BYREF
  BYTE *v42[2]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v43; // [rsp+68h] [rbp+Fh]
  BYTE *v44[4]; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v39 = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *))(*(_QWORD *)a1 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v39);
  v5 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, off_14001B050);
  v6 = v4(a1, *(_QWORD *)(v5 + 24), &v39);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v6,
      lpData);
  ConvertArrayToPaths(v42, v39);
  v7 = RegSetValueExW(a2, L"AllowedPaths", 0, 7u, v42[0], 2 * ((v42[1] - v42[0]) >> 1));
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x25F, v8, (const char *)v7, lpDataa);
  v38 = 0;
  v9 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *))(*(_QWORD *)a1 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v38);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, off_14001B048);
  if ( v9(a1, *(_QWORD *)(v10 + 24), &v38) >= 0 )
  {
    ConvertArrayToPaths(v44, v38);
    v11 = RegSetValueExW(a2, L"ExcludedPaths", 0, 7u, v44[0], 2 * ((v44[1] - v44[0]) >> 1));
    if ( v11 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x266, v12, (const char *)v11, lpDatab);
    if ( v44[0] )
      std::_Deallocate<16>(v44[0], 2 * ((v44[2] - v44[0]) >> 1));
  }
  v35 = 0;
  v13 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, _QWORD, char *))(*(_QWORD *)a1 + 96LL);
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, off_14001B040);
  if ( v13(a1, *(_QWORD *)(v14 + 24), &v35) >= 0 )
  {
    *(_DWORD *)Data = v35 != 0;
    v15 = RegSetValueExW(a2, L"AllowSubdomains", 0, 4u, Data, 4u);
    if ( v15 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x26E, v16, (const char *)v15, lpDatac);
  }
  v36[0] = 0;
  v17 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, _QWORD, _BYTE *))(*(_QWORD *)a1 + 96LL);
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, off_14001B038);
  if ( v17(a1, *(_QWORD *)(v18 + 24), v36) >= 0 )
  {
    *(_DWORD *)Data = v36[0] != 0;
    v19 = RegSetValueExW(a2, L"DisableFromBrowser", 0, 4u, Data, 4u);
    if ( v19 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x276, v20, (const char *)v19, lpDatad);
  }
  *(_QWORD *)v41 = GetCurrentSystemTime();
  v21 = RegSetValueExW(a2, L"LastSuccessfulValidationTime", 0, 0xBu, v41, 8u);
  if ( v21 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x27B, v22, (const char *)v21, lpDatae);
  v23 = RegSetValueExW(a2, L"LastValidationAttemptTime", 0, 0xBu, v41, 8u);
  if ( v23 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x27E, v24, (const char *)v23, lpDataf);
  *(_DWORD *)v40 = 0;
  v25 = RegSetValueExW(a2, L"FailedValiationCount", 0, 4u, v40, 4u);
  if ( v25 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x282, v26, (const char *)v25, lpDatag);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v38);
  if ( v42[0] )
  {
    std::_Deallocate<16>(v42[0], 2 * ((signed __int64)(v43 - (unsigned __int64)v42[0]) >> 1));
    *(_OWORD *)v42 = 0;
    v43 = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v39);
}

```

## disassembly

```asm
0x14000f3b8  mov     [rsp-8+arg_10], rbx
0x14000f3bd  mov     [rsp-8+arg_18], rsi
0x14000f3c2  push    rbp
0x14000f3c3  push    rdi
0x14000f3c4  push    r15
0x14000f3c6  lea     rbp, [rsp-47h]
0x14000f3cb  sub     rsp, 0A0h
0x14000f3d2  mov     rax, cs:__security_cookie
0x14000f3d9  xor     rax, rsp
0x14000f3dc  mov     [rbp+57h+var_20], rax
0x14000f3e0  mov     rdi, rdx
0x14000f3e3  mov     rsi, rcx
0x14000f3e6  mov     [rbp+57h+var_70], 0
0x14000f3ee  mov     rax, [rcx]
0x14000f3f1  mov     rbx, [rax+48h]
0x14000f3f5  lea     rcx, [rbp+57h+var_70]
0x14000f3f9  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f3fe  lea     rdx, off_14001B050; "paths"
0x14000f405  lea     rcx, [rbp+57h+var_40]
0x14000f409  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000f40e  nop
0x14000f40f  lea     r8, [rbp+57h+var_70]
0x14000f413  mov     rdx, [rax+18h]
0x14000f417  mov     rcx, rsi
0x14000f41a  mov     rax, rbx
0x14000f41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f422  mov     rcx, [rbp+5Fh]; this
0x14000f426  test    eax, eax
0x14000f428  jns     short loc_14000F43F
0x14000f42a  mov     r9d, eax; char *
0x14000f42d  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000f434  mov     edx, 25Ch; void *
0x14000f439  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000f43f  mov     rdx, [rbp+57h+var_70]
0x14000f443  lea     rcx, [rbp+57h+var_58]
0x14000f447  call    ?ConvertArrayToPaths@@YA?AV?$vector@GV?$allocator@G@std@@@std@@PEAUIJsonArray@Json@Data@Windows@@@Z; ConvertArrayToPaths(Windows::Data::Json::IJsonArray *)
0x14000f44c  nop
0x14000f44d  mov     rcx, [rbp+57h+var_58]
0x14000f451  mov     rax, [rbp+57h+var_58+8]
0x14000f455  sub     rax, rcx
0x14000f458  sar     rax, 1
0x14000f45b  add     eax, eax
0x14000f45d  mov     [rsp+0B0h+cbData], eax; cbData
0x14000f461  mov     [rsp+0B0h+lpData], rcx; unsigned int
0x14000f466  mov     r15d, 7
0x14000f46c  mov     r9d, r15d; dwType
0x14000f46f  xor     r8d, r8d; Reserved
0x14000f472  lea     rdx, aAllowedpaths; "AllowedPaths"
0x14000f479  mov     rcx, rdi; hKey
0x14000f47c  call    cs:__imp_RegSetValueExW
0x14000f482  mov     rcx, [rbp+5Fh]; this
0x14000f486  test    eax, eax
0x14000f488  jz      short loc_14000F498
0x14000f48a  mov     r9d, eax; char *
0x14000f48d  mov     edx, 25Fh; void *
0x14000f492  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000f498  mov     [rbp+57h+var_78], 0
0x14000f4a0  mov     rax, [rsi]
0x14000f4a3  mov     rbx, [rax+48h]
0x14000f4a7  lea     rcx, [rbp+57h+var_78]
0x14000f4ab  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f4b0  lea     rdx, off_14001B048; "excludePaths"
0x14000f4b7  lea     rcx, [rbp+57h+var_40]
0x14000f4bb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000f4c0  nop
0x14000f4c1  lea     r8, [rbp+57h+var_78]
0x14000f4c5  mov     rdx, [rax+18h]
0x14000f4c9  mov     rcx, rsi
0x14000f4cc  mov     rax, rbx
0x14000f4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f4d4  nop
0x14000f4d5  shr     eax, 1Fh
0x14000f4d8  xor     al, 1
0x14000f4da  jz      short loc_14000F54A
0x14000f4dc  mov     rdx, [rbp+57h+var_78]
0x14000f4e0  lea     rcx, [rbp+57h+var_40]
0x14000f4e4  call    ?ConvertArrayToPaths@@YA?AV?$vector@GV?$allocator@G@std@@@std@@PEAUIJsonArray@Json@Data@Windows@@@Z; ConvertArrayToPaths(Windows::Data::Json::IJsonArray *)
0x14000f4e9  nop
0x14000f4ea  mov     rcx, [rbp+57h+var_40]
0x14000f4ee  mov     rax, [rbp+57h+var_38]
0x14000f4f2  sub     rax, rcx
0x14000f4f5  sar     rax, 1
0x14000f4f8  add     eax, eax
0x14000f4fa  mov     [rsp+0B0h+cbData], eax; cbData
0x14000f4fe  mov     [rsp+0B0h+lpData], rcx; unsigned int
0x14000f503  mov     r9d, r15d; dwType
0x14000f506  xor     r8d, r8d; Reserved
0x14000f509  lea     rdx, aExcludedpaths; "ExcludedPaths"
0x14000f510  mov     rcx, rdi; hKey
0x14000f513  call    cs:__imp_RegSetValueExW
0x14000f519  mov     rcx, [rbp+5Fh]; this
0x14000f51d  test    eax, eax
0x14000f51f  jz      short loc_14000F52F
0x14000f521  mov     r9d, eax; char *
0x14000f524  mov     edx, 266h; void *
0x14000f529  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000f52f  mov     rcx, [rbp+57h+var_40]
0x14000f533  test    rcx, rcx
0x14000f536  jz      short loc_14000F54A
0x14000f538  mov     rdx, [rbp+57h+var_30]
0x14000f53c  sub     rdx, rcx
0x14000f53f  sar     rdx, 1
0x14000f542  add     rdx, rdx
0x14000f545  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000f54a  mov     [rbp+57h+var_80], 0
0x14000f54e  mov     rax, [rsi]
0x14000f551  mov     rbx, [rax+60h]
0x14000f555  lea     rdx, off_14001B040; "allowSubdomains"
0x14000f55c  lea     rcx, [rbp+57h+var_40]
0x14000f560  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000f565  nop
0x14000f566  lea     r8, [rbp+57h+var_80]
0x14000f56a  mov     rdx, [rax+18h]
0x14000f56e  mov     rcx, rsi
0x14000f571  mov     rax, rbx
0x14000f574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f579  nop
0x14000f57a  shr     eax, 1Fh
0x14000f57d  mov     r15d, 4
0x14000f583  xor     al, 1
0x14000f585  jz      short loc_14000F5CC
0x14000f587  xor     eax, eax
0x14000f589  cmp     [rbp+57h+var_80], al
0x14000f58c  setnz   al
0x14000f58f  mov     dword ptr [rbp+57h+Data], eax
0x14000f592  mov     [rsp+0B0h+cbData], r15d; cbData
0x14000f597  lea     rax, [rbp+57h+Data]
0x14000f59b  mov     [rsp+0B0h+lpData], rax; unsigned int
0x14000f5a0  mov     r9d, r15d; dwType
0x14000f5a3  xor     r8d, r8d; Reserved
0x14000f5a6  lea     rdx, aAllowsubdomain_0; "AllowSubdomains"
0x14000f5ad  mov     rcx, rdi; hKey
0x14000f5b0  call    cs:__imp_RegSetValueExW
0x14000f5b6  mov     rcx, [rbp+5Fh]; this
0x14000f5ba  test    eax, eax
0x14000f5bc  jz      short loc_14000F5CC
0x14000f5be  mov     r9d, eax; char *
0x14000f5c1  mov     edx, 26Eh; void *
0x14000f5c6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000f5cc  mov     [rbp+57h+var_7F], 0
0x14000f5d0  mov     rax, [rsi]
0x14000f5d3  mov     rbx, [rax+60h]
0x14000f5d7  lea     rdx, off_14001B038; "disableFromBrowser"
0x14000f5de  lea     rcx, [rbp+57h+var_40]
0x14000f5e2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000f5e7  nop
0x14000f5e8  lea     r8, [rbp+57h+var_7F]
0x14000f5ec  mov     rdx, [rax+18h]
0x14000f5f0  mov     rcx, rsi
0x14000f5f3  mov     rax, rbx
0x14000f5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f5fb  nop
0x14000f5fc  shr     eax, 1Fh
0x14000f5ff  xor     al, 1
0x14000f601  jz      short loc_14000F648
0x14000f603  xor     eax, eax
0x14000f605  cmp     [rbp+57h+var_7F], al
0x14000f608  setnz   al
0x14000f60b  mov     dword ptr [rbp+57h+Data], eax
0x14000f60e  mov     [rsp+0B0h+cbData], r15d; cbData
0x14000f613  lea     rax, [rbp+57h+Data]
0x14000f617  mov     [rsp+0B0h+lpData], rax; unsigned int
0x14000f61c  mov     r9d, r15d; dwType
0x14000f61f  xor     r8d, r8d; Reserved
0x14000f622  lea     rdx, aDisablefrombro_0; "DisableFromBrowser"
0x14000f629  mov     rcx, rdi; hKey
0x14000f62c  call    cs:__imp_RegSetValueExW
0x14000f632  mov     rcx, [rbp+5Fh]; this
0x14000f636  test    eax, eax
0x14000f638  jz      short loc_14000F648
0x14000f63a  mov     r9d, eax; char *
0x14000f63d  mov     edx, 276h; void *
0x14000f642  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000f648  call    ?GetCurrentSystemTime@@YA_KXZ; GetCurrentSystemTime(void)
0x14000f64d  mov     qword ptr [rbp+57h+var_60], rax
0x14000f651  mov     ebx, 8
0x14000f656  mov     [rsp+0B0h+cbData], ebx; cbData
0x14000f65a  lea     rax, [rbp+57h+var_60]
0x14000f65e  mov     [rsp+0B0h+lpData], rax; unsigned int
0x14000f663  lea     esi, [rbx+3]
0x14000f666  mov     r9d, esi; dwType
0x14000f669  xor     r8d, r8d; Reserved
0x14000f66c  lea     rdx, aLastsuccessful; "LastSuccessfulValidationTime"
0x14000f673  mov     rcx, rdi; hKey
0x14000f676  call    cs:__imp_RegSetValueExW
0x14000f67c  mov     rcx, [rbp+5Fh]; this
0x14000f680  test    eax, eax
0x14000f682  jz      short loc_14000F692
0x14000f684  mov     r9d, eax; char *
0x14000f687  mov     edx, 27Bh; void *
0x14000f68c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000f692  mov     [rsp+0B0h+cbData], ebx; cbData
0x14000f696  lea     rax, [rbp+57h+var_60]
0x14000f69a  mov     [rsp+0B0h+lpData], rax; unsigned int
0x14000f69f  mov     r9d, esi; dwType
0x14000f6a2  xor     r8d, r8d; Reserved
0x14000f6a5  lea     rdx, ValueName; "LastValidationAttemptTime"
0x14000f6ac  mov     rcx, rdi; hKey
0x14000f6af  call    cs:__imp_RegSetValueExW
0x14000f6b5  mov     rcx, [rbp+5Fh]; this
0x14000f6b9  test    eax, eax
0x14000f6bb  jz      short loc_14000F6CB
0x14000f6bd  mov     r9d, eax; char *
0x14000f6c0  mov     edx, 27Eh; void *
0x14000f6c5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000f6cb  mov     dword ptr [rbp+57h+var_68], 0
0x14000f6d2  mov     [rsp+0B0h+cbData], r15d; cbData
0x14000f6d7  lea     rax, [rbp+57h+var_68]
0x14000f6db  mov     [rsp+0B0h+lpData], rax; unsigned int
0x14000f6e0  mov     r9d, r15d; dwType
0x14000f6e3  xor     r8d, r8d; Reserved
0x14000f6e6  lea     rdx, aFailedvaliatio; "FailedValiationCount"
0x14000f6ed  mov     rcx, rdi; hKey
0x14000f6f0  call    cs:__imp_RegSetValueExW
0x14000f6f6  mov     rcx, [rbp+5Fh]; this
0x14000f6fa  test    eax, eax
0x14000f6fc  jz      short loc_14000F70C
0x14000f6fe  mov     r9d, eax; char *
0x14000f701  mov     edx, 282h; void *
0x14000f706  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000f70c  lea     rcx, [rbp+57h+var_78]
0x14000f710  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f715  nop
0x14000f716  mov     rcx, [rbp+57h+var_58]
0x14000f71a  test    rcx, rcx
0x14000f71d  jz      short loc_14000F741
0x14000f71f  mov     rdx, [rbp+57h+var_48]
0x14000f723  sub     rdx, rcx
0x14000f726  sar     rdx, 1
0x14000f729  add     rdx, rdx
0x14000f72c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000f731  xorps   xmm0, xmm0
0x14000f734  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x14000f739  mov     [rbp+57h+var_48], 0
0x14000f741  lea     rcx, [rbp+57h+var_70]
0x14000f745  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000f74a  mov     rcx, [rbp+57h+var_20]
0x14000f74e  xor     rcx, rsp; StackCookie
0x14000f751  call    __security_check_cookie
0x14000f756  lea     r11, [rsp+0B0h+var_10]
0x14000f75e  mov     rbx, [r11+30h]
0x14000f762  mov     rsi, [r11+38h]
0x14000f766  mov     rsp, r11
0x14000f769  pop     r15
0x14000f76b  pop     rdi
0x14000f76c  pop     rbp
0x14000f76d  retn
```
