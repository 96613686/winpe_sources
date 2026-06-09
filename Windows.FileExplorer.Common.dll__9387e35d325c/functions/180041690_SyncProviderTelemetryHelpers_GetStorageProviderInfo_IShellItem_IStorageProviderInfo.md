# SyncProviderTelemetryHelpers::GetStorageProviderInfo(IShellItem *,IStorageProviderInfo * *)

- ea: `0x180041690`
- end: `0x1800417d2`
- name: `?GetStorageProviderInfo@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAUIStorageProviderInfo@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IStorageProviderInfo **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180041334`

## callees

- `0x180004a54`
- `0x18000b9b0`
- `0x18002e778`
- `0x180041008`
- `0x180041690`
- `0x180043eb8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004177b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004177b`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180041742`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180041742`

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
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v7);
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
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v7);
  return (unsigned int)FilePath;
}

```

## disassembly

```asm
0x180041690  mov     [rsp-8+arg_0], rbx
0x180041695  mov     [rsp-8+arg_10], rdi
0x18004169a  push    rbp
0x18004169b  mov     rbp, rsp
0x18004169e  sub     rsp, 50h
0x1800416a2  mov     rdi, rdx
0x1800416a5  mov     rbx, rcx
0x1800416a8  mov     qword ptr [rdx], 0
0x1800416af  call    ?AreAnyStorageProvidersRegistered@SyncRootHelpers@Internal@Windows@@YA_NXZ; Windows::Internal::SyncRootHelpers::AreAnyStorageProvidersRegistered(void)
0x1800416b4  test    al, al
0x1800416b6  jnz     short loc_1800416C2
0x1800416b8  mov     eax, 80070490h
0x1800416bd  jmp     loc_1800417C2
0x1800416c2  mov     [rbp+var_20], 0
0x1800416ca  mov     [rbp+var_18], 0
0x1800416d2  mov     [rbp+var_10], 0
0x1800416da  lea     rcx, [rbp+var_20]
0x1800416de  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800416e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800416e7  mov     [rbp+var_18], rax
0x1800416eb  mov     [rbp+var_10], rax
0x1800416ef  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x1800416f3  mov     rcx, rbx; struct IShellItem *
0x1800416f6  call    ?GetFilePath@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAG@Z; SyncProviderTelemetryHelpers::GetFilePath(IShellItem *,ushort * *)
0x1800416fb  mov     ebx, eax
0x1800416fd  test    eax, eax
0x1800416ff  js      loc_1800417B7
0x180041705  mov     [rbp+arg_8], 0
0x18004170d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61110674@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674> `wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl(void)'::`2'::impl
0x180041714  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(void)
0x180041719  lea     rcx, [rbp+arg_8]
0x18004171d  test    al, al
0x18004171f  jz      short loc_180041759
0x180041721  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180041726  lea     rax, [rbp+arg_8]
0x18004172a  mov     [rsp+50h+ppv], rax; ppv
0x18004172f  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180041736  xor     r8d, r8d; pUnkOuter
0x180041739  lea     rdx, CLSID_SyncRootManager; pclsid
0x180041740  xor     ecx, ecx; pszCLSID
0x180041742  call    cs:__imp_SHCoCreateInstance
0x180041748  mov     ebx, eax
0x18004174a  test    eax, eax
0x18004174c  jns     short loc_180041783
0x18004174e  lea     rcx, [rbp+arg_8]
0x180041752  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180041757  jmp     short loc_1800417B7
0x180041759  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004175e  lea     rax, [rbp+arg_8]
0x180041762  mov     [rsp+50h+ppv], rax; ppv
0x180041767  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x18004176e  xor     edx, edx; pUnkOuter
0x180041770  lea     r8d, [rdx+1]; dwClsContext
0x180041774  lea     rcx, CLSID_SyncRootManager; rclsid
0x18004177b  call    cs:__imp_CoCreateInstance
0x180041781  jmp     short loc_180041748
0x180041783  mov     rcx, [rbp+arg_8]
0x180041787  mov     rax, [rcx]
0x18004178a  mov     [rsp+50h+ppv], 0
0x180041793  xor     r9d, r9d
0x180041796  mov     r8, rdi
0x180041799  mov     rdx, [rbp+var_20]
0x18004179d  mov     rax, [rax+20h]
0x1800417a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417a6  mov     ebx, eax
0x1800417a8  lea     rcx, [rbp+arg_8]
0x1800417ac  test    eax, eax
0x1800417ae  js      short loc_180041752
0x1800417b0  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800417b5  xor     ebx, ebx
0x1800417b7  lea     rcx, [rbp+var_20]
0x1800417bb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800417c0  mov     eax, ebx
0x1800417c2  mov     rbx, [rsp+50h+arg_0]
0x1800417c7  mov     rdi, [rsp+50h+arg_10]
0x1800417cc  add     rsp, 50h
0x1800417d0  pop     rbp
0x1800417d1  retn
```
