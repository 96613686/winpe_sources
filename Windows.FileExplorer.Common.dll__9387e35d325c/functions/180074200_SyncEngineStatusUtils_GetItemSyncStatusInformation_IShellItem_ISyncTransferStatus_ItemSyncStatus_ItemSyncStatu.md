# SyncEngineStatusUtils::GetItemSyncStatusInformation(IShellItem *,ISyncTransferStatus *,ItemSyncStatus,ItemSyncStatus *,ushort * *)

- ea: `0x180074200`
- end: `0x180074405`
- name: `?GetItemSyncStatusInformation@SyncEngineStatusUtils@@YAJPEAUIShellItem@@PEAUISyncTransferStatus@@W4ItemSyncStatus@@PEAW44@PEAPEAG@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180078340`

## callees

- `0x180004a54`
- `0x18000b9b0`
- `0x180043eb8`
- `0x180073e24`
- `0x180074200`
- `0x180074828`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007428a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007428a`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180074260`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180074260`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SyncEngineStatusUtils::GetItemSyncStatusInformation(
        __int64 a1,
        __int64 a2,
        int a3,
        _DWORD *a4,
        int a5)
{
  HRESULT v7; // eax
  int GlobalItemStatusFromPropertyStore; // ebx
  __int64 (__fastcall *v9)(__int64, __int64, SyncEngineStatusUtils **); // rbx
  void *v10; // rdi
  __int64 (__fastcall *v11)(void *, SyncEngineStatusUtils *, __int64 *, __int64 *); // rbx
  const unsigned __int16 *v12; // rdx
  void *ppv; // [rsp+30h] [rbp-40h] BYREF
  __int64 v15; // [rsp+38h] [rbp-38h] BYREF
  SyncEngineStatusUtils *v16; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+48h] [rbp-28h]
  __int64 v18; // [rsp+50h] [rbp-20h]
  __int64 v19; // [rsp+58h] [rbp-18h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]
  __int64 v21; // [rsp+68h] [rbp-8h]
  __int64 v22; // [rsp+B8h] [rbp+48h] BYREF
  int v23; // [rsp+C0h] [rbp+50h] BYREF
  SYNC_TRANSFER_STATUS v24; // [rsp+C8h] [rbp+58h] BYREF

  v23 = a3;
  v22 = a2;
  *a4 = 0;
  ppv = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl'::`2'::impl) )
  {
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
    v7 = SHCoCreateInstance(0, &CLSID_SyncRootManager, 0, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv);
  }
  else
  {
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
    v7 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv);
  }
  GlobalItemStatusFromPropertyStore = v7;
  if ( v7 >= 0 )
  {
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, __int64, SyncEngineStatusUtils **))(*(_QWORD *)a1 + 40LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
    v17 = -1;
    v18 = -1;
    GlobalItemStatusFromPropertyStore = v9(a1, 2147844096LL, &v16);
    if ( GlobalItemStatusFromPropertyStore >= 0 )
    {
      v15 = 0;
      v19 = 0;
      v20 = 0;
      v21 = 0;
      LODWORD(v22) = 0;
      v10 = ppv;
      v11 = *(__int64 (__fastcall **)(void *, SyncEngineStatusUtils *, __int64 *, __int64 *))(*(_QWORD *)ppv + 32LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
      v20 = -1;
      v21 = -1;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v15);
      GlobalItemStatusFromPropertyStore = v11(v10, v16, &v15, &v19);
      if ( GlobalItemStatusFromPropertyStore >= 0 )
      {
        v23 = 0;
        GlobalItemStatusFromPropertyStore = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 168LL))(
                                              v15,
                                              &v23);
        if ( GlobalItemStatusFromPropertyStore >= 0 )
        {
          if ( (v23 & 4) != 0 )
          {
            v24 = STS_NONE;
            if ( (v22 & 2) != 0 )
            {
              GlobalItemStatusFromPropertyStore = anonymous_namespace_::GetGlobalItemStatusFromPropertyStore(
                                                    a1,
                                                    (_DWORD)v12,
                                                    (_DWORD)a4,
                                                    (unsigned int)&a5,
                                                    (__int64)&v24);
            }
            else
            {
              a5 = 0;
              GlobalItemStatusFromPropertyStore = SyncEngineStatusUtils::GetSyncTransferStatusFromIndexer(
                                                    v16,
                                                    v12,
                                                    (struct ISyncTransferStatus *)&a5,
                                                    &v24,
                                                    (int *)&v22);
              if ( GlobalItemStatusFromPropertyStore >= 0 )
              {
                if ( (a5 & 0x10) != 0 )
                  *a4 = 5;
                else
                  *a4 = ((a5 & 0xF) != 0) + 1;
              }
            }
          }
          else
          {
            GlobalItemStatusFromPropertyStore = -2147024846;
          }
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v15);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
  return (unsigned int)GlobalItemStatusFromPropertyStore;
}

```

## disassembly

```asm
0x180074200  mov     [rsp-38h+arg_10], r8d
0x180074205  mov     [rsp-38h+arg_8], rdx
0x18007420a  push    rbp
0x18007420b  push    rbx
0x18007420c  push    rsi
0x18007420d  push    rdi
0x18007420e  push    r12
0x180074210  push    r14
0x180074212  push    r15
0x180074214  mov     rbp, rsp
0x180074217  sub     rsp, 70h
0x18007421b  mov     rsi, r9
0x18007421e  mov     r14, rcx
0x180074221  xor     r15d, r15d
0x180074224  mov     [r9], r15d
0x180074227  mov     [rbp+var_40], r15
0x18007422b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61110674@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674> `wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl(void)'::`2'::impl
0x180074232  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(void)
0x180074237  lea     rcx, [rbp+var_40]
0x18007423b  test    al, al
0x18007423d  jz      short loc_180074268
0x18007423f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180074244  lea     rax, [rbp+var_40]
0x180074248  mov     [rsp+70h+ppv], rax; ppv
0x18007424d  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180074254  xor     r8d, r8d; pUnkOuter
0x180074257  lea     rdx, CLSID_SyncRootManager; pclsid
0x18007425e  xor     ecx, ecx; pszCLSID
0x180074260  call    cs:__imp_SHCoCreateInstance
0x180074266  jmp     short loc_180074290
0x180074268  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18007426d  lea     rax, [rbp+var_40]
0x180074271  mov     [rsp+70h+ppv], rax; ppv
0x180074276  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x18007427d  xor     edx, edx; pUnkOuter
0x18007427f  lea     r8d, [rdx+1]; dwClsContext
0x180074283  lea     rcx, CLSID_SyncRootManager; rclsid
0x18007428a  call    cs:__imp_CoCreateInstance
0x180074290  mov     ebx, eax
0x180074292  test    eax, eax
0x180074294  js      loc_1800743EB
0x18007429a  mov     [rbp+var_30], r15
0x18007429e  mov     [rbp+var_28], r15
0x1800742a2  mov     [rbp+var_20], r15
0x1800742a6  mov     rax, [r14]
0x1800742a9  mov     rbx, [rax+28h]
0x1800742ad  lea     rcx, [rbp+var_30]
0x1800742b1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800742b6  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800742ba  mov     [rbp+var_28], r12
0x1800742be  mov     [rbp+var_20], r12
0x1800742c2  lea     r8, [rbp+var_30]
0x1800742c6  mov     edx, 80058000h
0x1800742cb  mov     rcx, r14
0x1800742ce  mov     rax, rbx
0x1800742d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742d6  mov     ebx, eax
0x1800742d8  test    eax, eax
0x1800742da  js      loc_1800743E1
0x1800742e0  mov     [rbp+var_38], r15
0x1800742e4  mov     [rbp+var_18], r15
0x1800742e8  mov     [rbp+var_10], r15
0x1800742ec  mov     [rbp+var_8], r15
0x1800742f0  mov     dword ptr [rbp+arg_8], r15d
0x1800742f4  mov     rdi, [rbp+var_40]
0x1800742f8  mov     rax, [rdi]
0x1800742fb  mov     rbx, [rax+20h]
0x1800742ff  lea     rcx, [rbp+var_18]
0x180074303  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180074308  mov     [rbp+var_10], r12
0x18007430c  mov     [rbp+var_8], r12
0x180074310  lea     rcx, [rbp+var_38]
0x180074314  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180074319  lea     rax, [rbp+arg_8]
0x18007431d  mov     [rsp+70h+ppv], rax; int *
0x180074322  lea     r9, [rbp+var_18]
0x180074326  lea     r8, [rbp+var_38]
0x18007432a  mov     rdx, [rbp+var_30]
0x18007432e  mov     rcx, rdi
0x180074331  mov     rax, rbx
0x180074334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074339  mov     ebx, eax
0x18007433b  test    eax, eax
0x18007433d  js      loc_1800743CD
0x180074343  mov     [rbp+arg_10], r15d
0x180074347  mov     rcx, [rbp+var_38]
0x18007434b  mov     rax, [rcx]
0x18007434e  lea     rdx, [rbp+arg_10]
0x180074352  mov     rax, [rax+0A8h]
0x180074359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007435e  mov     ebx, eax
0x180074360  test    eax, eax
0x180074362  js      short loc_1800743CD
0x180074364  test    byte ptr [rbp+arg_10], 4
0x180074368  jnz     short loc_180074371
0x18007436a  mov     ebx, 80070032h
0x18007436f  jmp     short loc_1800743CD
0x180074371  mov     [rbp+arg_18], r15d
0x180074375  test    byte ptr [rbp+arg_8], 2
0x180074379  jz      short loc_180074397
0x18007437b  lea     rax, [rbp+arg_18]
0x18007437f  mov     [rsp+70h+ppv], rax
0x180074384  lea     r9, [rbp+arg_20]
0x180074388  mov     r8, rsi
0x18007438b  mov     rcx, r14
0x18007438e  call    _anonymous_namespace___GetGlobalItemStatusFromPropertyStore
0x180074393  mov     ebx, eax
0x180074395  jmp     short loc_1800743CD
0x180074397  mov     [rbp+arg_20], r15d
0x18007439b  lea     r9, [rbp+arg_18]; enum SYNC_TRANSFER_STATUS *
0x18007439f  lea     r8, [rbp+arg_20]; struct ISyncTransferStatus *
0x1800743a3  mov     rcx, [rbp+var_30]; this
0x1800743a7  call    ?GetSyncTransferStatusFromIndexer@SyncEngineStatusUtils@@YAJPEBGPEAUISyncTransferStatus@@PEAW4SYNC_TRANSFER_STATUS@@PEAJ@Z; SyncEngineStatusUtils::GetSyncTransferStatusFromIndexer(ushort const *,ISyncTransferStatus *,SYNC_TRANSFER_STATUS *,long *)
0x1800743ac  mov     ebx, eax
0x1800743ae  test    eax, eax
0x1800743b0  js      short loc_1800743CD
0x1800743b2  mov     eax, [rbp+arg_20]
0x1800743b5  test    al, 10h
0x1800743b7  jz      short loc_1800743C1
0x1800743b9  mov     dword ptr [rsi], 5
0x1800743bf  jmp     short loc_1800743CD
0x1800743c1  and     al, 0Fh
0x1800743c3  neg     al
0x1800743c5  sbb     eax, eax
0x1800743c7  neg     eax
0x1800743c9  inc     eax
0x1800743cb  mov     [rsi], eax
0x1800743cd  lea     rcx, [rbp+var_18]
0x1800743d1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800743d6  nop
0x1800743d7  lea     rcx, [rbp+var_38]
0x1800743db  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800743e0  nop
0x1800743e1  lea     rcx, [rbp+var_30]
0x1800743e5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800743ea  nop
0x1800743eb  lea     rcx, [rbp+var_40]
0x1800743ef  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800743f4  mov     eax, ebx
0x1800743f6  add     rsp, 70h
0x1800743fa  pop     r15
0x1800743fc  pop     r14
0x1800743fe  pop     r12
0x180074400  pop     rdi
0x180074401  pop     rsi
0x180074402  pop     rbx
0x180074403  pop     rbp
0x180074404  retn
```
