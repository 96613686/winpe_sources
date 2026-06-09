# CStartMenuPathCompleteRowset::_GetPropertyStoreForMRU(ushort const *,ushort const *,_GUID const &,void * *)

- ea: `0x180035a7c`
- end: `0x180035d26`
- name: `?_GetPropertyStoreForMRU@CStartMenuPathCompleteRowset@@AEAAJPEBG0AEBU_GUID@@PEAPEAX@Z`
- size: `682`
- prototype: `__int64 __fastcall(CStartMenuPathCompleteRowset *this, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037494`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x18002dc04`
- `0x180035a7c`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180035ce9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180035cf4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180035cff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180035ce9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180035cf4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180035cff`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180035abc`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180035abc`

## pseudocode

```c
__int64 __fastcall CStartMenuPathCompleteRowset::_GetPropertyStoreForMRU(
        CStartMenuPathCompleteRowset *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _GUID *a4,
        void **a5)
{
  void **v7; // r14
  HRESULT inited; // ebx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v11; // [rsp+30h] [rbp-40h]
  struct tagPROPVARIANT v12; // [rsp+38h] [rbp-38h] BYREF
  struct tagPROPVARIANT v13; // [rsp+50h] [rbp-20h] BYREF
  void *ppv; // [rsp+A8h] [rbp+38h] BYREF

  ppv = a4;
  v7 = a5;
  *a5 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
  inited = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( inited >= 0 )
  {
    memset(&v13, 0, sizeof(v13));
    memset(&v12, 0, sizeof(v12));
    *(_OWORD *)pvar = 0;
    v11 = 0;
    LOWORD(pvar[0]) = 1;
    inited = InitPropVariantFromString(a2, &v12);
    if ( inited >= 0 )
    {
      inited = InitPropVariantFromString(a3, &v13);
      if ( inited >= 0 )
      {
        inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                   ppv,
                   &PKEY_FileAttributes,
                   pvar);
        if ( inited >= 0 )
        {
          inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                     ppv,
                     &PKEY_ItemNameDisplay,
                     &v13);
          if ( inited >= 0 )
          {
            inited = (*(__int64 (__fastcall **)(void *, __int128 *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                       ppv,
                       &PKEY_ItemId,
                       &v12);
            if ( inited >= 0 )
            {
              inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                         ppv,
                         &PKEY_ParsingPath,
                         &v12);
              if ( inited >= 0 )
              {
                inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                           ppv,
                           &PKEY_ParsingName,
                           &v13);
                if ( inited >= 0 )
                {
                  inited = (*(__int64 (__fastcall **)(void *, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                             ppv,
                             PKEY_StartMenu_RunCommand,
                             &v12);
                  if ( inited >= 0 )
                  {
                    inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                               ppv,
                               &PKEY_DateModified,
                               pvar);
                    if ( inited >= 0 )
                    {
                      inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                 ppv,
                                 &PKEY_DateCreated,
                                 pvar);
                      if ( inited >= 0 )
                      {
                        inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                   ppv,
                                   &PKEY_DateAccessed,
                                   pvar);
                        if ( inited >= 0 )
                        {
                          inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                     ppv,
                                     &PKEY_Size,
                                     pvar);
                          if ( inited >= 0 )
                          {
                            inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                       ppv,
                                       &PKEY_ItemType,
                                       pvar);
                            if ( inited >= 0 )
                            {
                              inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                         ppv,
                                         &PKEY_FileFRN,
                                         pvar);
                              if ( inited >= 0 )
                                inited = (**(__int64 (__fastcall ***)(void *, GUID *, void **))ppv)(
                                           ppv,
                                           &GUID_3017056d_9a91_4e90_937d_746c72abbf4f,
                                           v7);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    PropVariantClear(pvar);
    PropVariantClear((PROPVARIANT *)&v12);
    PropVariantClear((PROPVARIANT *)&v13);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180035a7c  mov     [rsp-18h+arg_0], rbx
0x180035a81  mov     [rsp-18h+arg_8], rsi
0x180035a86  mov     [rsp-18h+ppv], r9
0x180035a8b  push    rbp
0x180035a8c  push    rdi
0x180035a8d  push    r14
0x180035a8f  mov     rbp, rsp
0x180035a92  sub     rsp, 70h
0x180035a96  mov     rdi, r8
0x180035a99  mov     rsi, rdx
0x180035a9c  mov     r14, [rbp+arg_20]
0x180035aa0  mov     qword ptr [r14], 0
0x180035aa7  lea     rcx, [rbp+ppv]; void *
0x180035aab  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180035ab0  nop
0x180035ab1  lea     rdx, [rbp+ppv]; ppv
0x180035ab5  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180035abc  call    cs:__imp_PSCreateMemoryPropertyStore
0x180035ac2  mov     ebx, eax
0x180035ac4  test    eax, eax
0x180035ac6  js      loc_180035D06
0x180035acc  xorps   xmm0, xmm0
0x180035acf  xor     eax, eax
0x180035ad1  movups  xmmword ptr [rbp+var_20], xmm0
0x180035ad5  mov     [rbp+var_10], rax
0x180035ad9  movups  xmmword ptr [rbp+var_38], xmm0
0x180035add  mov     [rbp+var_28], rax
0x180035ae1  movups  xmmword ptr [rbp+pvar], xmm0
0x180035ae5  mov     [rbp+var_40], rax
0x180035ae9  mov     eax, 1
0x180035aee  mov     word ptr [rbp+pvar], ax
0x180035af2  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x180035af6  mov     rcx, rsi; Source
0x180035af9  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180035afe  mov     ebx, eax
0x180035b00  test    eax, eax
0x180035b02  js      loc_180035CE5
0x180035b08  lea     rdx, [rbp+var_20]; struct tagPROPVARIANT *
0x180035b0c  mov     rcx, rdi; Source
0x180035b0f  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180035b14  mov     ebx, eax
0x180035b16  test    eax, eax
0x180035b18  js      loc_180035CE5
0x180035b1e  mov     rcx, [rbp+ppv]
0x180035b22  mov     rax, [rcx]
0x180035b25  lea     r8, [rbp+pvar]
0x180035b29  lea     rdx, PKEY_FileAttributes
0x180035b30  mov     rax, [rax+30h]
0x180035b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b39  mov     ebx, eax
0x180035b3b  test    eax, eax
0x180035b3d  js      loc_180035CE5
0x180035b43  mov     rcx, [rbp+ppv]
0x180035b47  mov     rax, [rcx]
0x180035b4a  lea     r8, [rbp+var_20]
0x180035b4e  lea     rdx, PKEY_ItemNameDisplay
0x180035b55  mov     rax, [rax+30h]
0x180035b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b5e  mov     ebx, eax
0x180035b60  test    eax, eax
0x180035b62  js      loc_180035CE5
0x180035b68  mov     rcx, [rbp+ppv]
0x180035b6c  mov     rax, [rcx]
0x180035b6f  lea     r8, [rbp+var_38]
0x180035b73  lea     rdx, PKEY_ItemId
0x180035b7a  mov     rax, [rax+30h]
0x180035b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b83  mov     ebx, eax
0x180035b85  test    eax, eax
0x180035b87  js      loc_180035CE5
0x180035b8d  mov     rcx, [rbp+ppv]
0x180035b91  mov     rax, [rcx]
0x180035b94  lea     r8, [rbp+var_38]
0x180035b98  lea     rdx, PKEY_ParsingPath
0x180035b9f  mov     rax, [rax+30h]
0x180035ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ba8  mov     ebx, eax
0x180035baa  test    eax, eax
0x180035bac  js      loc_180035CE5
0x180035bb2  mov     rcx, [rbp+ppv]
0x180035bb6  mov     rax, [rcx]
0x180035bb9  lea     r8, [rbp+var_20]
0x180035bbd  lea     rdx, PKEY_ParsingName
0x180035bc4  mov     rax, [rax+30h]
0x180035bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bcd  mov     ebx, eax
0x180035bcf  test    eax, eax
0x180035bd1  js      loc_180035CE5
0x180035bd7  mov     rcx, [rbp+ppv]
0x180035bdb  mov     rax, [rcx]
0x180035bde  lea     r8, [rbp+var_38]
0x180035be2  lea     rdx, PKEY_StartMenu_RunCommand
0x180035be9  mov     rax, [rax+30h]
0x180035bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bf2  mov     ebx, eax
0x180035bf4  test    eax, eax
0x180035bf6  js      loc_180035CE5
0x180035bfc  mov     rcx, [rbp+ppv]
0x180035c00  mov     rax, [rcx]
0x180035c03  lea     r8, [rbp+pvar]
0x180035c07  lea     rdx, PKEY_DateModified
0x180035c0e  mov     rax, [rax+30h]
0x180035c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c17  mov     ebx, eax
0x180035c19  test    eax, eax
0x180035c1b  js      loc_180035CE5
0x180035c21  mov     rcx, [rbp+ppv]
0x180035c25  mov     rax, [rcx]
0x180035c28  lea     r8, [rbp+pvar]
0x180035c2c  lea     rdx, PKEY_DateCreated
0x180035c33  mov     rax, [rax+30h]
0x180035c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c3c  mov     ebx, eax
0x180035c3e  test    eax, eax
0x180035c40  js      loc_180035CE5
0x180035c46  mov     rcx, [rbp+ppv]
0x180035c4a  mov     rax, [rcx]
0x180035c4d  lea     r8, [rbp+pvar]
0x180035c51  lea     rdx, PKEY_DateAccessed
0x180035c58  mov     rax, [rax+30h]
0x180035c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c61  mov     ebx, eax
0x180035c63  test    eax, eax
0x180035c65  js      short loc_180035CE5
0x180035c67  mov     rcx, [rbp+ppv]
0x180035c6b  mov     rax, [rcx]
0x180035c6e  lea     r8, [rbp+pvar]
0x180035c72  lea     rdx, PKEY_Size
0x180035c79  mov     rax, [rax+30h]
0x180035c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c82  mov     ebx, eax
0x180035c84  test    eax, eax
0x180035c86  js      short loc_180035CE5
0x180035c88  mov     rcx, [rbp+ppv]
0x180035c8c  mov     rax, [rcx]
0x180035c8f  lea     r8, [rbp+pvar]
0x180035c93  lea     rdx, PKEY_ItemType
0x180035c9a  mov     rax, [rax+30h]
0x180035c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ca3  mov     ebx, eax
0x180035ca5  test    eax, eax
0x180035ca7  js      short loc_180035CE5
0x180035ca9  mov     rcx, [rbp+ppv]
0x180035cad  mov     rax, [rcx]
0x180035cb0  lea     r8, [rbp+pvar]
0x180035cb4  lea     rdx, PKEY_FileFRN
0x180035cbb  mov     rax, [rax+30h]
0x180035cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cc4  mov     ebx, eax
0x180035cc6  test    eax, eax
0x180035cc8  js      short loc_180035CE5
0x180035cca  mov     rcx, [rbp+ppv]
0x180035cce  mov     rax, [rcx]
0x180035cd1  mov     r8, r14
0x180035cd4  lea     rdx, _GUID_3017056d_9a91_4e90_937d_746c72abbf4f
0x180035cdb  mov     rax, [rax]
0x180035cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ce3  mov     ebx, eax
0x180035ce5  lea     rcx, [rbp+pvar]; pvar
0x180035ce9  call    cs:__imp_PropVariantClear
0x180035cef  nop
0x180035cf0  lea     rcx, [rbp+var_38]; pvar
0x180035cf4  call    cs:__imp_PropVariantClear
0x180035cfa  nop
0x180035cfb  lea     rcx, [rbp+var_20]; pvar
0x180035cff  call    cs:__imp_PropVariantClear
0x180035d05  nop
0x180035d06  lea     rcx, [rbp+ppv]
0x180035d0a  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180035d0f  mov     eax, ebx
0x180035d11  lea     r11, [rsp+70h+var_s0]
0x180035d16  mov     rbx, [r11+20h]
0x180035d1a  mov     rsi, [r11+28h]
0x180035d1e  mov     rsp, r11
0x180035d21  pop     r14
0x180035d23  pop     rdi
0x180035d24  pop     rbp
0x180035d25  retn
```
