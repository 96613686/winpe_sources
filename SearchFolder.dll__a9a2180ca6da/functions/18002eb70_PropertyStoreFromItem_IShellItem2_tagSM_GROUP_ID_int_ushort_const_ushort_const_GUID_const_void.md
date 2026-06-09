# PropertyStoreFromItem(IShellItem2 *,tagSM_GROUP_ID,int,ushort const *,ushort const *,_GUID const &,void * *)

- ea: `0x18002eb70`
- end: `0x18002ef02`
- name: `?PropertyStoreFromItem@@YAJPEAUIShellItem2@@W4tagSM_GROUP_ID@@HPEBG2AEBU_GUID@@PEAPEAX@Z`
- size: `914`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002c070`
- `0x18003489c`
- `0x180034dc8`
- `0x1800357b8`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x1800129c0`
- `0x1800129ec`
- `0x18002eb70`
- `0x18003d8ac`
- `0x180041060`
- `0x180041618`
- `0x180041658`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ed5d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002edc1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ed5d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002edc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ee67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ee9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ee67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ee9e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002ec2e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002ec2e`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x18002ec09`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x18002ec09`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PropertyStoreFromItem(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7)
{
  unsigned int v10; // edi
  HRESULT v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  int (__fastcall *v16)(__int64, __int64, LPVOID *); // rbx
  void *ppv; // [rsp+30h] [rbp-71h] BYREF
  int v19; // [rsp+38h] [rbp-69h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-61h] BYREF
  __int64 v21; // [rsp+50h] [rbp-51h]
  __int64 v22; // [rsp+58h] [rbp-49h] BYREF
  __int64 v23; // [rsp+60h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-39h] BYREF
  __int64 v25; // [rsp+70h] [rbp-31h]
  __int128 v26; // [rsp+78h] [rbp-29h] BYREF
  int v27; // [rsp+88h] [rbp-19h]
  __int128 v28; // [rsp+90h] [rbp-11h] BYREF
  int v29; // [rsp+A0h] [rbp-1h]

  v25 = a6;
  v10 = 0;
  *a7 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v23);
  v11 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)a1 + 64LL))(
          a1,
          8,
          &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
          &v23);
  if ( v11 >= 0 )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v22);
    v11 = PSCreatePropertyKeyStore(&xmmword_18006A770, 11, &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b, &v22);
    if ( v11 >= 0 )
    {
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
      v11 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
      if ( v11 >= 0 )
      {
        v19 = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 24LL))(v22, &v19);
        if ( v11 >= 0 )
        {
          if ( v19 > 0 )
          {
            while ( 1 )
            {
              if ( v11 < 0 )
                goto LABEL_28;
              v26 = 0;
              v27 = 0;
              v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v22 + 32LL))(v22, v10, &v26);
              if ( v11 >= 0 )
              {
                v28 = v26;
                v29 = v27;
                if ( (unsigned int)operator==(&v28, &PKEY_ItemNameDisplay) )
                {
                  if ( a2 == 500 )
                  {
                    v12 = *(_QWORD *)ppv;
                    LOWORD(pvar[0]) = 31;
                    pvar[1] = a4;
                    v11 = (*(__int64 (__fastcall **)(void *, __int128 *, PROPVARIANT *))(v12 + 48))(ppv, &v26, pvar);
                    goto LABEL_20;
                  }
                }
                else if ( (unsigned int)operator==(&v28, &PKEY_ItemId) )
                {
                  *(_OWORD *)pvar = 0;
                  v21 = 0;
                  v11 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v23 + 40LL))(
                          v23,
                          &PKEY_ParsingPath,
                          pvar);
                  if ( v11 >= 0 )
                    goto LABEL_18;
                  PropVariantClear(pvar);
                }
                if ( v11 >= 0 )
                {
                  *(_OWORD *)pvar = 0;
                  v21 = 0;
                  v11 = (*(__int64 (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v23 + 40LL))(
                          v23,
                          &v28,
                          pvar);
                  if ( v11 >= 0 )
                  {
                    if ( !LOWORD(pvar[0]) )
                      LOWORD(pvar[0]) = 1;
LABEL_18:
                    v11 = (*(__int64 (__fastcall **)(void *, __int128 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                            ppv,
                            &v26,
                            pvar);
                  }
                  PropVariantClear(pvar);
                }
              }
LABEL_20:
              if ( (int)++v10 >= v19 )
              {
                if ( v11 < 0 )
                  goto LABEL_28;
                break;
              }
            }
          }
          IPropertyStore_SetInt(ppv, PKEY_Order, a2);
          v13 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&ppv);
          IPropertyStore_SetItem(v13, PKEY_DelegateIDList, a1);
          v14 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&ppv);
          IPropertyStore_SetUInt32(v14, PKEY_AppUserModel_HostEnvironment, 0);
          if ( a5 )
          {
            IPropertyStore_SetString(ppv, PKEY_StartMenu_RunCommand, a5);
            v15 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&ppv);
            IPropertyStore_SetString(v15, &PKEY_AppUserModel_ID, a5);
          }
          else
          {
            pv = 0;
            v16 = *(int (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)a1 + 40LL);
            CoTaskMemFree(0);
            if ( v16(a1, 2147647488LL, &pv) >= 0 )
              IPropertyStore_SetString(ppv, &PKEY_AppUserModel_ID, pv);
            CoTaskMemFree(pv);
          }
          v11 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))ppv)(ppv, v25, a7);
        }
      }
LABEL_28:
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
    }
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v22);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v23);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002eb70  mov     [rsp-8+arg_10], rbx
0x18002eb75  push    rbp
0x18002eb76  push    rsi
0x18002eb77  push    rdi
0x18002eb78  push    r12
0x18002eb7a  push    r13
0x18002eb7c  push    r14
0x18002eb7e  push    r15
0x18002eb80  lea     rbp, [rsp-0Fh]
0x18002eb85  sub     rsp, 0B0h
0x18002eb8c  mov     rax, cs:__security_cookie
0x18002eb93  xor     rax, rsp
0x18002eb96  mov     [rbp+3Fh+var_38], rax
0x18002eb9a  mov     r13, r9
0x18002eb9d  mov     r15d, edx
0x18002eba0  mov     rsi, rcx
0x18002eba3  mov     r14, [rbp+3Fh+arg_20]
0x18002eba7  mov     rax, [rbp+3Fh+arg_28]
0x18002ebab  mov     [rbp+3Fh+var_70], rax
0x18002ebaf  mov     r12, [rbp+3Fh+arg_30]
0x18002ebb3  xor     edi, edi
0x18002ebb5  mov     [r12], rdi
0x18002ebb9  lea     rcx, [rbp+3Fh+var_80]; void *
0x18002ebbd  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18002ebc2  nop
0x18002ebc3  mov     rax, [rsi]
0x18002ebc6  lea     r9, [rbp+3Fh+var_80]
0x18002ebca  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18002ebd1  lea     edx, [rdi+8]
0x18002ebd4  mov     rcx, rsi
0x18002ebd7  mov     rax, [rax+40h]
0x18002ebdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebe0  mov     ebx, eax
0x18002ebe2  test    eax, eax
0x18002ebe4  js      loc_18002EED0
0x18002ebea  lea     rcx, [rbp+3Fh+var_88]; void *
0x18002ebee  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18002ebf3  nop
0x18002ebf4  lea     r9, [rbp+3Fh+var_88]
0x18002ebf8  lea     r8, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x18002ebff  lea     edx, [rdi+0Bh]
0x18002ec02  lea     rcx, xmmword_18006A770
0x18002ec09  call    cs:__imp_PSCreatePropertyKeyStore
0x18002ec0f  mov     ebx, eax
0x18002ec11  test    eax, eax
0x18002ec13  js      loc_18002EEC6
0x18002ec19  lea     rcx, [rbp+3Fh+ppv]; void *
0x18002ec1d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18002ec22  nop
0x18002ec23  lea     rdx, [rbp+3Fh+ppv]; ppv
0x18002ec27  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18002ec2e  call    cs:__imp_PSCreateMemoryPropertyStore
0x18002ec34  mov     ebx, eax
0x18002ec36  test    eax, eax
0x18002ec38  js      loc_18002EEBC
0x18002ec3e  mov     [rbp+3Fh+var_A8], edi
0x18002ec41  mov     rcx, [rbp+3Fh+var_88]
0x18002ec45  mov     rax, [rcx]
0x18002ec48  lea     rdx, [rbp+3Fh+var_A8]
0x18002ec4c  mov     rax, [rax+18h]
0x18002ec50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec55  mov     ebx, eax
0x18002ec57  test    eax, eax
0x18002ec59  js      loc_18002EEBC
0x18002ec5f  xor     r8d, r8d
0x18002ec62  cmp     [rbp+3Fh+var_A8], r8d
0x18002ec66  jle     loc_18002EDDA
0x18002ec6c  test    ebx, ebx
0x18002ec6e  js      loc_18002EEBC
0x18002ec74  xorps   xmm0, xmm0
0x18002ec77  xor     eax, eax
0x18002ec79  movups  [rbp+3Fh+var_68], xmm0
0x18002ec7d  mov     [rbp+3Fh+var_58], eax
0x18002ec80  mov     rcx, [rbp+3Fh+var_88]
0x18002ec84  mov     rax, [rcx]
0x18002ec87  lea     r8, [rbp+3Fh+var_68]
0x18002ec8b  mov     edx, edi
0x18002ec8d  mov     rax, [rax+20h]
0x18002ec91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec96  mov     ebx, eax
0x18002ec98  test    eax, eax
0x18002ec9a  js      loc_18002EDC7
0x18002eca0  movups  xmm0, [rbp+3Fh+var_68]
0x18002eca4  movups  [rbp+3Fh+var_50], xmm0
0x18002eca8  mov     eax, [rbp+3Fh+var_58]
0x18002ecab  mov     [rbp+3Fh+var_40], eax
0x18002ecae  lea     rdx, PKEY_ItemNameDisplay
0x18002ecb5  lea     rcx, [rbp+3Fh+var_50]
0x18002ecb9  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18002ecbe  test    eax, eax
0x18002ecc0  jz      short loc_18002ECFB
0x18002ecc2  cmp     r15d, 1F4h
0x18002ecc9  jnz     loc_18002ED63
0x18002eccf  mov     rcx, [rbp+3Fh+ppv]
0x18002ecd3  mov     rax, [rcx]
0x18002ecd6  mov     edx, 1Fh
0x18002ecdb  mov     word ptr [rbp+3Fh+pvar], dx
0x18002ecdf  mov     [rbp+3Fh+pvar+8], r13
0x18002ece3  lea     r8, [rbp+3Fh+pvar]
0x18002ece7  lea     rdx, [rbp+3Fh+var_68]
0x18002eceb  mov     rax, [rax+30h]
0x18002ecef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecf4  mov     ebx, eax
0x18002ecf6  jmp     loc_18002EDC7
0x18002ecfb  lea     rdx, PKEY_ItemId
0x18002ed02  lea     rcx, [rbp+3Fh+var_50]
0x18002ed06  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18002ed0b  test    eax, eax
0x18002ed0d  jz      short loc_18002ED63
0x18002ed0f  xorps   xmm0, xmm0
0x18002ed12  xor     eax, eax
0x18002ed14  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x18002ed18  mov     [rbp+3Fh+var_90], rax
0x18002ed1c  mov     rcx, [rbp+3Fh+var_80]
0x18002ed20  mov     rax, [rcx]
0x18002ed23  lea     r8, [rbp+3Fh+pvar]
0x18002ed27  lea     rdx, PKEY_ParsingPath
0x18002ed2e  mov     rax, [rax+28h]
0x18002ed32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed37  mov     ebx, eax
0x18002ed39  test    eax, eax
0x18002ed3b  js      short loc_18002ED59
0x18002ed3d  mov     rcx, [rbp+3Fh+ppv]
0x18002ed41  mov     rax, [rcx]
0x18002ed44  lea     r8, [rbp+3Fh+pvar]
0x18002ed48  lea     rdx, [rbp+3Fh+var_68]
0x18002ed4c  mov     rax, [rax+30h]
0x18002ed50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed55  mov     ebx, eax
0x18002ed57  jmp     short loc_18002EDBD
0x18002ed59  lea     rcx, [rbp+3Fh+pvar]; pvar
0x18002ed5d  call    cs:__imp_PropVariantClear
0x18002ed63  test    ebx, ebx
0x18002ed65  js      short loc_18002EDC7
0x18002ed67  xorps   xmm0, xmm0
0x18002ed6a  xor     eax, eax
0x18002ed6c  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x18002ed70  mov     [rbp+3Fh+var_90], rax
0x18002ed74  mov     rcx, [rbp+3Fh+var_80]
0x18002ed78  mov     rax, [rcx]
0x18002ed7b  lea     r8, [rbp+3Fh+pvar]
0x18002ed7f  lea     rdx, [rbp+3Fh+var_50]
0x18002ed83  mov     rax, [rax+28h]
0x18002ed87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed8c  mov     ebx, eax
0x18002ed8e  xor     eax, eax
0x18002ed90  test    ebx, ebx
0x18002ed92  js      short loc_18002EDBD
0x18002ed94  cmp     word ptr [rbp+3Fh+pvar], ax
0x18002ed98  jnz     short loc_18002EDA3
0x18002ed9a  mov     eax, 1
0x18002ed9f  mov     word ptr [rbp+3Fh+pvar], ax
0x18002eda3  mov     rcx, [rbp+3Fh+ppv]
0x18002eda7  mov     rax, [rcx]
0x18002edaa  lea     r8, [rbp+3Fh+pvar]
0x18002edae  lea     rdx, [rbp+3Fh+var_68]
0x18002edb2  mov     rax, [rax+30h]
0x18002edb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002edbb  mov     ebx, eax
0x18002edbd  lea     rcx, [rbp+3Fh+pvar]; pvar
0x18002edc1  call    cs:__imp_PropVariantClear
0x18002edc7  inc     edi
0x18002edc9  cmp     edi, [rbp+3Fh+var_A8]
0x18002edcc  jl      loc_18002EC6C
0x18002edd2  test    ebx, ebx
0x18002edd4  js      loc_18002EEBC
0x18002edda  mov     r8d, r15d
0x18002eddd  lea     rdx, PKEY_Order
0x18002ede4  mov     rcx, [rbp+3Fh+ppv]
0x18002ede8  call    IPropertyStore_SetInt
0x18002eded  lea     rcx, [rbp+3Fh+ppv]
0x18002edf1  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x18002edf6  mov     rcx, rax
0x18002edf9  mov     r8, rsi
0x18002edfc  lea     rdx, PKEY_DelegateIDList
0x18002ee03  call    IPropertyStore_SetItem
0x18002ee08  lea     rcx, [rbp+3Fh+ppv]
0x18002ee0c  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x18002ee11  mov     rcx, rax
0x18002ee14  xor     r8d, r8d
0x18002ee17  lea     rdx, PKEY_AppUserModel_HostEnvironment
0x18002ee1e  call    IPropertyStore_SetUInt32
0x18002ee23  xor     edi, edi
0x18002ee25  test    r14, r14
0x18002ee28  jz      short loc_18002EE5A
0x18002ee2a  mov     r8, r14
0x18002ee2d  lea     rdx, PKEY_StartMenu_RunCommand
0x18002ee34  mov     rcx, [rbp+3Fh+ppv]
0x18002ee38  call    IPropertyStore_SetString
0x18002ee3d  lea     rcx, [rbp+3Fh+ppv]
0x18002ee41  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x18002ee46  mov     rcx, rax
0x18002ee49  mov     r8, r14
0x18002ee4c  lea     rdx, PKEY_AppUserModel_ID
0x18002ee53  call    IPropertyStore_SetString
0x18002ee58  jmp     short loc_18002EEA4
0x18002ee5a  mov     [rbp+3Fh+pv], rdi
0x18002ee5e  mov     rax, [rsi]
0x18002ee61  mov     rbx, [rax+28h]
0x18002ee65  xor     ecx, ecx; pv
0x18002ee67  call    cs:__imp_CoTaskMemFree
0x18002ee6d  lea     r8, [rbp+3Fh+pv]
0x18002ee71  mov     edx, 80028000h
0x18002ee76  mov     rcx, rsi
0x18002ee79  mov     rax, rbx
0x18002ee7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee81  test    eax, eax
0x18002ee83  js      short loc_18002EE9A
0x18002ee85  mov     r8, [rbp+3Fh+pv]
0x18002ee89  lea     rdx, PKEY_AppUserModel_ID
0x18002ee90  mov     rcx, [rbp+3Fh+ppv]
0x18002ee94  call    IPropertyStore_SetString
0x18002ee99  nop
0x18002ee9a  mov     rcx, [rbp+3Fh+pv]; pv
0x18002ee9e  call    cs:__imp_CoTaskMemFree
0x18002eea4  mov     rcx, [rbp+3Fh+ppv]
0x18002eea8  mov     rax, [rcx]
0x18002eeab  mov     r8, r12
0x18002eeae  mov     rdx, [rbp+3Fh+var_70]
0x18002eeb2  mov     rax, [rax]
0x18002eeb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeba  mov     ebx, eax
0x18002eebc  lea     rcx, [rbp+3Fh+ppv]
0x18002eec0  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18002eec5  nop
0x18002eec6  lea     rcx, [rbp+3Fh+var_88]
0x18002eeca  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18002eecf  nop
0x18002eed0  lea     rcx, [rbp+3Fh+var_80]
0x18002eed4  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18002eed9  mov     eax, ebx
0x18002eedb  mov     rcx, [rbp+3Fh+var_38]
0x18002eedf  xor     rcx, rsp; StackCookie
0x18002eee2  call    __security_check_cookie
0x18002eee7  mov     rbx, [rsp+0E0h+arg_10]
0x18002eeef  add     rsp, 0B0h
0x18002eef6  pop     r15
0x18002eef8  pop     r14
0x18002eefa  pop     r13
0x18002eefc  pop     r12
0x18002eefe  pop     rdi
0x18002eeff  pop     rsi
0x18002ef00  pop     rbp
0x18002ef01  retn
```
