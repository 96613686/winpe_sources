# SyncProviderTelemetryHelpers::GetStorageProviderInfo(IShellItem *,IStorageProviderInfo * *)

- ea: `0x18001966c`
- end: `0x1800197ae`
- name: `?GetStorageProviderInfo@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAUIStorageProviderInfo@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IStorageProviderInfo **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180018e38`

## callees

- `0x1800047b0`
- `0x180004a10`
- `0x1800064d4`
- `0x1800133a4`
- `0x18001966c`
- `0x18002158c`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x18001971e`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18001971e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019757`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019757`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SyncProviderTelemetryHelpers::GetStorageProviderInfo(
        struct IShellItem *a1,
        struct IStorageProviderInfo **a2)
{
  int FilePath; // ebx
  HRESULT v6; // eax
  unsigned __int16 *v7; // [rsp+30h] [rbp-20h] BYREF
  __int64 v8; // [rsp+38h] [rbp-18h]
  __int64 v9; // [rsp+40h] [rbp-10h]
  void *ppv; // [rsp+68h] [rbp+18h] BYREF

  *a2 = 0;
  if ( !Windows::Internal::SyncRootHelpers::AreAnyStorageProvidersRegistered((Windows::Internal::SyncRootHelpers *)a1) )
    return 2147943568LL;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v7);
  v8 = -1;
  v9 = -1;
  FilePath = SyncProviderTelemetryHelpers::GetFilePath(a1, &v7);
  if ( FilePath >= 0 )
  {
    ppv = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl'::`2'::impl) )
    {
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      v6 = SHCoCreateInstance(0, &CLSID_SyncRootManager, 0, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv);
    }
    else
    {
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      v6 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv);
    }
    FilePath = v6;
    if ( v6 < 0
      || (FilePath = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, struct IStorageProviderInfo **, _QWORD, _QWORD))(*(_QWORD *)ppv + 32LL))(
                       ppv,
                       v7,
                       a2,
                       0,
                       0),
          FilePath < 0) )
    {
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
    }
    else
    {
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      FilePath = 0;
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v7);
  return (unsigned int)FilePath;
}

```

## disassembly

```asm
0x18001966c  mov     [rsp-8+arg_0], rbx
0x180019671  mov     [rsp-8+arg_10], rdi
0x180019676  push    rbp
0x180019677  mov     rbp, rsp
0x18001967a  sub     rsp, 50h
0x18001967e  mov     rdi, rdx
0x180019681  mov     rbx, rcx
0x180019684  mov     qword ptr [rdx], 0
0x18001968b  call    ?AreAnyStorageProvidersRegistered@SyncRootHelpers@Internal@Windows@@YA_NXZ; Windows::Internal::SyncRootHelpers::AreAnyStorageProvidersRegistered(void)
0x180019690  test    al, al
0x180019692  jnz     short loc_18001969E
0x180019694  mov     eax, 80070490h
0x180019699  jmp     loc_18001979E
0x18001969e  mov     [rbp+var_20], 0
0x1800196a6  mov     [rbp+var_18], 0
0x1800196ae  mov     [rbp+var_10], 0
0x1800196b6  lea     rcx, [rbp+var_20]
0x1800196ba  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800196bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800196c3  mov     [rbp+var_18], rax
0x1800196c7  mov     [rbp+var_10], rax
0x1800196cb  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x1800196cf  mov     rcx, rbx; struct IShellItem *
0x1800196d2  call    ?GetFilePath@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAG@Z; SyncProviderTelemetryHelpers::GetFilePath(IShellItem *,ushort * *)
0x1800196d7  mov     ebx, eax
0x1800196d9  test    eax, eax
0x1800196db  js      loc_180019793
0x1800196e1  mov     [rbp+arg_8], 0
0x1800196e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61110674@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674> `wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl(void)'::`2'::impl
0x1800196f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(void)
0x1800196f5  lea     rcx, [rbp+arg_8]
0x1800196f9  test    al, al
0x1800196fb  jz      short loc_180019735
0x1800196fd  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180019702  lea     rax, [rbp+arg_8]
0x180019706  mov     [rsp+50h+ppv], rax; ppv
0x18001970b  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180019712  xor     r8d, r8d; pUnkOuter
0x180019715  lea     rdx, CLSID_SyncRootManager; pclsid
0x18001971c  xor     ecx, ecx; pszCLSID
0x18001971e  call    cs:__imp_SHCoCreateInstance
0x180019724  mov     ebx, eax
0x180019726  test    eax, eax
0x180019728  jns     short loc_18001975F
0x18001972a  lea     rcx, [rbp+arg_8]
0x18001972e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180019733  jmp     short loc_180019793
0x180019735  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001973a  lea     rax, [rbp+arg_8]
0x18001973e  mov     [rsp+50h+ppv], rax; ppv
0x180019743  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x18001974a  xor     edx, edx; pUnkOuter
0x18001974c  lea     r8d, [rdx+1]; dwClsContext
0x180019750  lea     rcx, CLSID_SyncRootManager; rclsid
0x180019757  call    cs:__imp_CoCreateInstance
0x18001975d  jmp     short loc_180019724
0x18001975f  mov     rcx, [rbp+arg_8]
0x180019763  mov     rax, [rcx]
0x180019766  mov     [rsp+50h+ppv], 0
0x18001976f  xor     r9d, r9d
0x180019772  mov     r8, rdi
0x180019775  mov     rdx, [rbp+var_20]
0x180019779  mov     rax, [rax+20h]
0x18001977d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019782  mov     ebx, eax
0x180019784  lea     rcx, [rbp+arg_8]
0x180019788  test    eax, eax
0x18001978a  js      short loc_18001972E
0x18001978c  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180019791  xor     ebx, ebx
0x180019793  lea     rcx, [rbp+var_20]
0x180019797  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001979c  mov     eax, ebx
0x18001979e  mov     rbx, [rsp+50h+arg_0]
0x1800197a3  mov     rdi, [rsp+50h+arg_10]
0x1800197a8  add     rsp, 50h
0x1800197ac  pop     rbp
0x1800197ad  retn
```
