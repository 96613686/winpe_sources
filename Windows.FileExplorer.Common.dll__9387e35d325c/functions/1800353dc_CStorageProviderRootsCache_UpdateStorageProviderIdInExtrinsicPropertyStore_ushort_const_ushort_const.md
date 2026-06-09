# CStorageProviderRootsCache::_UpdateStorageProviderIdInExtrinsicPropertyStore(ushort const *,ushort const *)

- ea: `0x1800353dc`
- end: `0x18003568c`
- name: `?_UpdateStorageProviderIdInExtrinsicPropertyStore@CStorageProviderRootsCache@@AEAAXPEBG0@Z`
- size: `688`
- prototype: `void(CStorageProviderRootsCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180035010`
- `0x180068c80`

## callees

- `0x180004a54`
- `0x180006e78`
- `0x180007900`
- `0x18000b9b0`
- `0x180019680`
- `0x18001d320`
- `0x1800251fc`
- `0x1800353dc`
- `0x180037780`
- `0x180038708`
- `0x180044da8`
- `0x180045dd0`
- `0x180089010`

## import_xrefs

- `Windows.Storage!__imp_CreateExtrinsicPropertyStore` at `0x180035480`
- `Windows.Storage!__imp_CreateExtrinsicPropertyStore` at `0x180035480`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800355c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800355c6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180035444`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180035444`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035464`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035464`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CStorageProviderRootsCache::_UpdateStorageProviderIdInExtrinsicPropertyStore(
        CStorageProviderRootsCache *this,
        const unsigned __int16 *a2,
        Windows::Internal::SyncRootHelpers *a3)
{
  HANDLE FirstFileW; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned __int16 **v12; // r8
  int FailIf; // edi
  HANDLE v14; // rbx
  PROPVARIANT *v15; // r8
  HANDLE hFindFile; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+58h] [rbp-A8h]
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+70h] [rbp-90h]
  PROPERTYKEY v24; // [rsp+80h] [rbp-80h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  if ( a2 )
  {
    v18 = 0;
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    hFindFile = 0;
    FirstFileW = FindFirstFileW(a2, &FindFileData);
    if ( (int)ResultFromWin32Handle(FirstFileW, &hFindFile) >= 0 )
    {
      FindClose(hFindFile);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v18);
      if ( (int)CreateExtrinsicPropertyStore(&GUID_c3497c50_eaa0_4d39_8feb_05b03fbd87a1, &v18) >= 0
        && (*(int (__fastcall **)(__int64, const unsigned __int16 *, _WIN32_FIND_DATAW *, __int64))(*(_QWORD *)v18 + 24LL))(
             v18,
             a2,
             &FindFileData,
             2) >= 0 )
      {
        v17 = 0;
        CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(&v17, v6, v7, v8);
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
               v18,
               &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
               &v17) >= 0 )
        {
          hFindFile = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &hFindFile,
            0);
          if ( (int)Windows::Internal::SyncRootHelpers::ConvertFullIdentifierToProviderIdentifier(
                      a3,
                      (unsigned __int16 *)&hFindFile,
                      v12) >= 0 )
          {
            v19 = 0;
            v20 = 0;
            v21 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v19);
            v20 = -1;
            v21 = -1;
            v19 = 0;
            LOWORD(pvar[0]) = 0;
            v24 = PKEY_StorageProviderId;
            FailIf = CPropertyStoreHelperBase<IPropertyStore>::GetFailIfEmpty<_tagpropertykey>(&v17, &v24, pvar);
            if ( FailIf >= 0 )
            {
              v19 = 0;
              if ( LOWORD(pvar[0]) == 31 && pvar[1] )
              {
                v19 = pvar[1];
                *(_OWORD *)pvar = 0;
                v23 = 0;
              }
              else
              {
                FailIf = -2147352571;
              }
            }
            PropVariantClear(pvar);
            v14 = hFindFile;
            if ( FailIf < 0
              || (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                                 &v19,
                                 hFindFile,
                                 -1) != 2 )
            {
              if ( v14 )
              {
                LOWORD(pvar[0]) = 31;
                pvar[1] = v14;
                v15 = pvar;
              }
              else
              {
                LOWORD(v24.fmtid.Data1) = 0;
                v15 = (PROPVARIANT *)&v24;
              }
              if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v17 + 48LL))(
                     v17,
                     &PKEY_StorageProviderId,
                     v15) >= 0 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 56LL))(v17);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v19);
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&hFindFile);
        }
        CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(&v17, v9, v10, v11);
      }
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v18);
  }
}

```

## disassembly

```asm
0x1800353dc  test    rdx, rdx
0x1800353df  jz      locret_18003568B
0x1800353e5  mov     [rsp-8+arg_0], rbx
0x1800353ea  mov     [rsp-8+arg_18], rdi
0x1800353ef  push    rbp
0x1800353f0  push    r14
0x1800353f2  push    r15
0x1800353f4  lea     rbp, [rsp-200h]
0x1800353fc  sub     rsp, 300h
0x180035403  mov     rax, cs:__security_cookie
0x18003540a  xor     rax, rsp
0x18003540d  mov     [rbp+210h+var_20], rax
0x180035414  mov     rdi, r8
0x180035417  mov     rbx, rdx
0x18003541a  mov     [rsp+310h+var_2D0], 0
0x180035423  xor     edx, edx; Val
0x180035425  mov     r8d, 250h; Size
0x18003542b  lea     rcx, [rbp+210h+FindFileData]; void *
0x18003542f  call    memset_0
0x180035434  mov     [rsp+310h+hFindFile], 0
0x18003543d  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x180035441  mov     rcx, rbx; lpFileName
0x180035444  call    cs:__imp_FindFirstFileW
0x18003544a  mov     rcx, rax; void *
0x18003544d  lea     rdx, [rsp+310h+hFindFile]; void **
0x180035452  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x180035457  test    eax, eax
0x180035459  js      loc_18003565A
0x18003545f  mov     rcx, [rsp+310h+hFindFile]; hFindFile
0x180035464  call    cs:__imp_FindClose
0x18003546a  lea     rcx, [rsp+310h+var_2D0]
0x18003546f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180035474  lea     rdx, [rsp+310h+var_2D0]
0x180035479  lea     rcx, _GUID_c3497c50_eaa0_4d39_8feb_05b03fbd87a1
0x180035480  call    cs:__imp_CreateExtrinsicPropertyStore
0x180035486  test    eax, eax
0x180035488  js      loc_18003565A
0x18003548e  mov     rcx, [rsp+310h+var_2D0]
0x180035493  mov     rax, [rcx]
0x180035496  mov     r9d, 2
0x18003549c  lea     r8, [rbp+210h+FindFileData]
0x1800354a0  mov     rdx, rbx
0x1800354a3  mov     rax, [rax+18h]
0x1800354a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354ac  test    eax, eax
0x1800354ae  js      loc_18003565A
0x1800354b4  mov     [rsp+310h+var_2D8], 0
0x1800354bd  lea     rcx, [rsp+310h+var_2D8]
0x1800354c2  call    ?ClearPropertyStore@?$CPropertyStoreHelperBase@UINamedPropertyStore@@@@QEAAXXZ; CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(void)
0x1800354c7  nop
0x1800354c8  mov     rcx, [rsp+310h+var_2D0]
0x1800354cd  mov     rax, [rcx]
0x1800354d0  lea     r8, [rsp+310h+var_2D8]
0x1800354d5  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800354dc  mov     rax, [rax]
0x1800354df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354e4  nop
0x1800354e5  test    eax, eax
0x1800354e7  js      loc_18003564F
0x1800354ed  mov     [rsp+310h+hFindFile], 0
0x1800354f6  xor     edx, edx
0x1800354f8  lea     rcx, [rsp+310h+hFindFile]
0x1800354fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035502  lea     rdx, [rsp+310h+hFindFile]; unsigned __int16 *
0x180035507  mov     rcx, rdi; this
0x18003550a  call    ?ConvertFullIdentifierToProviderIdentifier@SyncRootHelpers@Internal@Windows@@YAJPEBGPEAPEAG@Z; Windows::Internal::SyncRootHelpers::ConvertFullIdentifierToProviderIdentifier(ushort const *,ushort * *)
0x18003550f  test    eax, eax
0x180035511  js      loc_180035644
0x180035517  mov     [rsp+310h+var_2C8], 0
0x180035520  mov     [rsp+310h+var_2C0], 0
0x180035529  mov     [rsp+310h+var_2B8], 0
0x180035532  lea     rcx, [rsp+310h+var_2C8]
0x180035537  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003553c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180035540  mov     [rsp+310h+var_2C0], r15
0x180035545  mov     [rsp+310h+var_2B8], r15
0x18003554a  movups  xmm0, xmmword ptr cs:PKEY_StorageProviderId.fmtid.Data1
0x180035551  mov     ecx, cs:PKEY_StorageProviderId.pid
0x180035557  mov     [rsp+310h+var_2C8], 0
0x180035560  xor     eax, eax
0x180035562  mov     word ptr [rsp+310h+pvar], ax
0x180035567  movaps  [rbp+210h+var_290], xmm0
0x18003556b  mov     [rbp+210h+var_280], ecx
0x18003556e  lea     r8, [rsp+310h+pvar]
0x180035573  lea     rdx, [rbp+210h+var_290]
0x180035577  lea     rcx, [rsp+310h+var_2D8]
0x18003557c  call    ??$GetFailIfEmpty@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CPropertyStoreHelperBase<IPropertyStore>::GetFailIfEmpty<_tagpropertykey>(_tagpropertykey,tagPROPVARIANT *)
0x180035581  mov     edi, eax
0x180035583  lea     r14d, [r15+20h]
0x180035587  test    eax, eax
0x180035589  js      short loc_1800355C1
0x18003558b  mov     [rsp+310h+var_2C8], 0
0x180035594  cmp     word ptr [rsp+310h+pvar], r14w
0x18003559a  jnz     short loc_1800355BC
0x18003559c  mov     rcx, [rsp+310h+pvar+8]
0x1800355a1  test    rcx, rcx
0x1800355a4  jz      short loc_1800355BC
0x1800355a6  mov     [rsp+310h+var_2C8], rcx
0x1800355ab  xorps   xmm0, xmm0
0x1800355ae  xor     eax, eax
0x1800355b0  movups  xmmword ptr [rsp+310h+pvar], xmm0
0x1800355b5  mov     [rsp+310h+var_2A0], rax
0x1800355ba  jmp     short loc_1800355C1
0x1800355bc  mov     edi, 80020005h
0x1800355c1  lea     rcx, [rsp+310h+pvar]; pvar
0x1800355c6  call    cs:__imp_PropVariantClear
0x1800355cc  mov     rbx, [rsp+310h+hFindFile]
0x1800355d1  test    edi, edi
0x1800355d3  js      short loc_1800355EA
0x1800355d5  mov     r8, r15
0x1800355d8  mov     rdx, rbx
0x1800355db  lea     rcx, [rsp+310h+var_2C8]
0x1800355e0  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800355e5  cmp     eax, 2
0x1800355e8  jz      short loc_180035639
0x1800355ea  test    rbx, rbx
0x1800355ed  jnz     short loc_1800355FB
0x1800355ef  xor     eax, eax
0x1800355f1  mov     word ptr [rbp+210h+var_290], ax
0x1800355f5  lea     r8, [rbp+210h+var_290]
0x1800355f9  jmp     short loc_18003560B
0x1800355fb  mov     word ptr [rsp+310h+pvar], r14w
0x180035601  mov     [rsp+310h+pvar+8], rbx
0x180035606  lea     r8, [rsp+310h+pvar]
0x18003560b  mov     rcx, [rsp+310h+var_2D8]
0x180035610  mov     rax, [rcx]
0x180035613  lea     rdx, PKEY_StorageProviderId
0x18003561a  mov     rax, [rax+30h]
0x18003561e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035623  test    eax, eax
0x180035625  js      short loc_180035639
0x180035627  mov     rcx, [rsp+310h+var_2D8]
0x18003562c  mov     rax, [rcx]
0x18003562f  mov     rax, [rax+38h]
0x180035633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035638  nop
0x180035639  lea     rcx, [rsp+310h+var_2C8]
0x18003563e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180035643  nop
0x180035644  lea     rcx, [rsp+310h+hFindFile]; void *
0x180035649  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18003564e  nop
0x18003564f  lea     rcx, [rsp+310h+var_2D8]
0x180035654  call    ?ClearPropertyStore@?$CPropertyStoreHelperBase@UINamedPropertyStore@@@@QEAAXXZ; CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(void)
0x180035659  nop
0x18003565a  lea     rcx, [rsp+310h+var_2D0]
0x18003565f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180035664  mov     rcx, [rbp+210h+var_20]
0x18003566b  xor     rcx, rsp; StackCookie
0x18003566e  call    __security_check_cookie
0x180035673  lea     r11, [rsp+310h+var_10]
0x18003567b  mov     rbx, [r11+20h]
0x18003567f  mov     rdi, [r11+38h]
0x180035683  mov     rsp, r11
0x180035686  pop     r15
0x180035688  pop     r14
0x18003568a  pop     rbp
0x18003568b  retn
```
