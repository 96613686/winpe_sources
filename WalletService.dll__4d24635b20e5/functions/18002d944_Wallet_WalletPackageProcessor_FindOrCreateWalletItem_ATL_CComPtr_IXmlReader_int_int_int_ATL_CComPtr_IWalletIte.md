# Wallet::WalletPackageProcessor::FindOrCreateWalletItem(ATL::CComPtr<IXmlReader>,int,int &,int &,ATL::CComPtr<IWalletItem> &)

- ea: `0x18002d944`
- end: `0x18002de45`
- name: `?FindOrCreateWalletItem@WalletPackageProcessor@Wallet@@SAJV?$CComPtr@UIXmlReader@@@ATL@@HAEAH1AEAV?$CComPtr@UIWalletItem@@@4@@Z`
- size: `1281`
- prototype: `__int64 __fastcall(_QWORD *, __int64, _DWORD *, _DWORD *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800306b0`

## callees

- `0x180003ae4`
- `0x180003b40`
- `0x1800043b8`
- `0x180013f78`
- `0x180013fe4`
- `0x18002d048`
- `0x18002d2b0`
- `0x18002d944`
- `0x180036ec8`
- `0x1800381e4`
- `0x180038324`
- `0x1800386b8`
- `0x1800390b4`
- `0x1800397cc`
- `0x180039a7c`
- `0x180039f20`
- `0x180045010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002dabd`
- `msvcrt!_wcsicmp` at `0x18002dafd`
- `msvcrt!_wcsicmp` at `0x18002db1d`
- `msvcrt!_wcsicmp` at `0x18002db3d`
- `msvcrt!_wcsicmp` at `0x18002db5d`
- `msvcrt!_wcsicmp` at `0x18002dabd`
- `msvcrt!_wcsicmp` at `0x18002dafd`
- `msvcrt!_wcsicmp` at `0x18002db1d`
- `msvcrt!_wcsicmp` at `0x18002db3d`
- `msvcrt!_wcsicmp` at `0x18002db5d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dd7b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ddc0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dd7b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ddc0`

## string_xrefs

- `0x18002db36`: `WebServiceUrl`

## pseudocode

```c
__int64 __fastcall Wallet::WalletPackageProcessor::FindOrCreateWalletItem(
        _QWORD *a1,
        __int64 a2,
        _DWORD *a3,
        _DWORD *a4,
        struct IUnknown **a5)
{
  struct IUnknown *v8; // rdx
  OLECHAR *v9; // r8
  __int64 v10; // r9
  int v11; // esi
  wchar_t *v12; // rdx
  _QWORD *p_psz; // rcx
  int ItemByWebServiceUrlOrIssuer; // eax
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64); // rbx
  __int64 v18; // rax
  LPCOLESTR v19; // rbx
  int v20; // eax
  unsigned int v21; // edi
  __int64 i; // rbx
  __int64 v23; // rdx
  __int64 v25; // [rsp+28h] [rbp-91h] BYREF
  struct IUnknown *v26; // [rsp+30h] [rbp-89h] BYREF
  const wchar_t *v27; // [rsp+38h] [rbp-81h] BYREF
  wchar_t *String2; // [rsp+40h] [rbp-79h] BYREF
  LPCOLESTR lpsz; // [rsp+48h] [rbp-71h] BYREF
  const OLECHAR *v30; // [rsp+50h] [rbp-69h]
  _WORD v31[8]; // [rsp+58h] [rbp-61h] BYREF
  __int64 v32; // [rsp+68h] [rbp-51h] BYREF
  OLECHAR *psz; // [rsp+70h] [rbp-49h] BYREF
  OLECHAR *v34; // [rsp+78h] [rbp-41h]
  _WORD v35[8]; // [rsp+80h] [rbp-39h] BYREF
  PROPVARIANT pvar[2]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-19h]
  _QWORD v38[2]; // [rsp+A8h] [rbp-11h] BYREF
  _WORD v39[8]; // [rsp+B8h] [rbp-1h] BYREF
  _QWORD v40[2]; // [rsp+C8h] [rbp+Fh] BYREF
  _WORD v41[24]; // [rsp+D8h] [rbp+1Fh] BYREF
  unsigned int v42; // [rsp+120h] [rbp+67h] BYREF
  int v43; // [rsp+130h] [rbp+77h] BYREF

  v43 = 0;
  v27 = 0;
  String2 = 0;
  psz = v35;
  v34 = v35;
  v35[0] = 0;
  lpsz = v31;
  v30 = v31;
  v31[0] = 0;
  v40[0] = v41;
  v40[1] = v41;
  v41[0] = 0;
  v38[0] = v39;
  v38[1] = v39;
  v39[0] = 0;
  v42 = 0;
  v26 = 0;
  *a4 = 1;
  while ( !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 200LL))(*a1) )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a1 + 48LL))(*a1, &v43);
    if ( v11 < 0 )
      goto LABEL_70;
    switch ( v43 )
    {
      case 1:
        v11 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t **, _QWORD))(*(_QWORD *)*a1 + 112LL))(*a1, &v27, 0);
        if ( v11 < 0 )
          goto LABEL_70;
        break;
      case 3:
        if ( v27 )
        {
          LODWORD(v25) = 0;
          v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 192LL))(*a1, &v25);
          if ( v11 < 0 )
            goto LABEL_70;
          if ( (_DWORD)v25 == 2 )
          {
            v11 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(*(_QWORD *)*a1 + 128LL))(*a1, &String2, 0);
            if ( v11 < 0 )
              goto LABEL_70;
            v11 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t **, _QWORD))(*(_QWORD *)*a1 + 112LL))(*a1, &v27, 0);
            if ( v11 < 0 )
              goto LABEL_70;
            if ( !_wcsicmp(L"Id", v27) )
            {
              v12 = String2;
              if ( String2 )
                *a3 = 1;
              p_psz = &psz;
              goto LABEL_17;
            }
            if ( _wcsicmp(L"ProductId", v27) )
            {
              if ( !_wcsicmp(L"IssuerDisplayName", v27) )
              {
                v12 = String2;
                p_psz = v40;
                goto LABEL_17;
              }
              if ( !_wcsicmp(L"WebServiceUrl", v27) )
              {
                v12 = String2;
                p_psz = v38;
                goto LABEL_17;
              }
              if ( !_wcsicmp(L"Kind", v27)
                && (int)ConvertItemTypeElementValueToWalletItemType(
                          String2,
                          (enum __MIDL___MIDL_itf_wallettypes_0000_0000_0001 *)&v42) < 0 )
              {
                goto LABEL_27;
              }
            }
            else
            {
              v12 = String2;
              p_psz = &lpsz;
LABEL_17:
              if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                       p_psz,
                                       v12) )
              {
                v11 = -2147024882;
                goto LABEL_70;
              }
            }
          }
        }
        break;
      case 15:
        v27 = 0;
        break;
    }
  }
  if ( psz == v34
    || (lpsz == v30
      ? (ItemByWebServiceUrlOrIssuer = Wallet::Utils::GetItemByWebServiceUrlOrIssuer(psz))
      : (ItemByWebServiceUrlOrIssuer = Wallet::Utils::GetItemOwnedByApp((OLECHAR *)lpsz, psz)),
        v11 = ItemByWebServiceUrlOrIssuer,
        ItemByWebServiceUrlOrIssuer == -2143682560) )
  {
    v11 = 0;
LABEL_38:
    if ( *a4 )
    {
      v25 = 0;
      if ( !v42 )
      {
        v11 = -2143682477;
LABEL_41:
        ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v25, v8, v9);
        goto LABEL_70;
      }
      v15 = ((__int64 (__fastcall *)(__int64 *, struct IUnknown *, OLECHAR *, __int64))Wallet::Utils::GetWalletItemManager)(
              &v25,
              v8,
              v9,
              v10);
      if ( v15 < 0 )
        goto LABEL_43;
      v16 = v25;
      v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v25 + 40LL);
      v18 = ce::pointerTo<IWalletNotification>(&v26);
      v15 = v17(v16, v42, v18);
      if ( v15 < 0 )
        goto LABEL_43;
      v9 = psz;
      if ( psz != v34 )
      {
        v15 = Wallet::Utils::SetTStringProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                v26,
                3001,
                psz);
        if ( v15 < 0 )
          goto LABEL_43;
      }
      v19 = lpsz;
      if ( lpsz != v30 )
      {
        if ( Wallet::Utils::IsPhoneProductId(lpsz, (const unsigned __int16 *)v8) )
        {
          v32 = 0;
          Wallet::Utils::GetApplicationInfoFromAppProductId(v19, &v32);
          ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v32);
        }
        v15 = Wallet::Utils::SetTStringProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                v26,
                3000,
                lpsz);
        if ( v15 < 0 || (v15 = Wallet::Utils::LinkItemToApp(&v26), v15 < 0) )
        {
LABEL_43:
          v11 = v15;
          goto LABEL_41;
        }
      }
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v25, v8, v9);
    }
    else
    {
      LODWORD(v25) = 0;
      v20 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v26->lpVtbl[1].Release)(v26, &v25);
      if ( v20 < 0 )
        goto LABEL_54;
      v21 = v42;
      if ( (_DWORD)v25 != v42 )
      {
LABEL_27:
        v11 = -2143682477;
        goto LABEL_70;
      }
      for ( i = 0; i != 28; ++i )
      {
        v23 = *((unsigned int *)qword_180052550 + i);
        if ( (_DWORD)v23 != 3000 || lpsz == v30 )
        {
          *(_OWORD *)pvar = 0;
          v37 = 0;
          if ( v26 )
            ((void (__fastcall *)(struct IUnknown *, __int64, PROPVARIANT *))v26->lpVtbl[2].AddRef)(v26, v23, pvar);
          PropVariantClear(pvar);
        }
      }
      if ( v21 == 4 )
      {
        *(_OWORD *)pvar = 0;
        v37 = 0;
        if ( v26 )
          ((void (__fastcall *)(struct IUnknown *, __int64, PROPVARIANT *))v26->lpVtbl[2].AddRef)(v26, 500, pvar);
        PropVariantClear(pvar);
      }
      v20 = Wallet::Utils::SetItemFlag(&v26, 8);
      if ( v20 < 0 )
      {
LABEL_54:
        v11 = v20;
        goto LABEL_70;
      }
    }
    v8 = v26;
    if ( *a5 != v26 )
      ATL::AtlComPtrAssign(a5, v26);
    goto LABEL_70;
  }
  if ( ItemByWebServiceUrlOrIssuer >= 0 )
  {
    *a4 = 0;
    goto LABEL_38;
  }
LABEL_70:
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v26, v8, v9);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v38);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v40);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&lpsz);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&psz);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(a1);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002d944  mov     rax, rsp
0x18002d947  mov     [rax+18h], rbx
0x18002d94b  mov     [rax+10h], edx
0x18002d94e  mov     [rax+8], rcx
0x18002d952  push    rbp
0x18002d953  push    rsi
0x18002d954  push    rdi
0x18002d955  push    r12
0x18002d957  push    r15
0x18002d959  lea     rbp, [rax-57h]
0x18002d95d  sub     rsp, 0E0h
0x18002d964  mov     rbx, r9
0x18002d967  mov     rdi, r8
0x18002d96a  mov     r15, rcx
0x18002d96d  xor     r12d, r12d
0x18002d970  mov     [rbp+4Fh+arg_18], r12d
0x18002d974  mov     [rsp+100h+var_D0], r12
0x18002d979  mov     [rbp+4Fh+String2], r12
0x18002d97d  lea     rax, [rbp+4Fh+var_88]
0x18002d981  mov     [rbp+4Fh+psz], rax
0x18002d985  lea     rax, [rbp+4Fh+var_88]
0x18002d989  mov     [rbp+4Fh+var_90], rax
0x18002d98d  mov     [rbp+4Fh+var_88], r12w
0x18002d992  lea     rax, [rbp+4Fh+var_B0]
0x18002d996  mov     [rbp+4Fh+lpsz], rax
0x18002d99a  lea     rax, [rbp+4Fh+var_B0]
0x18002d99e  mov     [rbp+4Fh+var_B8], rax
0x18002d9a2  mov     [rbp+4Fh+var_B0], r12w
0x18002d9a7  lea     rax, [rbp+4Fh+var_30]
0x18002d9ab  mov     [rbp+4Fh+var_40], rax
0x18002d9af  lea     rax, [rbp+4Fh+var_30]
0x18002d9b3  mov     [rbp+4Fh+var_38], rax
0x18002d9b7  mov     [rbp+4Fh+var_30], r12w
0x18002d9bc  lea     rax, [rbp+4Fh+var_50]
0x18002d9c0  mov     [rbp+4Fh+var_60], rax
0x18002d9c4  lea     rax, [rbp+4Fh+var_50]
0x18002d9c8  mov     [rbp+4Fh+var_58], rax
0x18002d9cc  mov     [rbp+4Fh+var_50], r12w
0x18002d9d1  mov     [rbp+4Fh+arg_8], r12d
0x18002d9d5  mov     [rsp+100h+var_D8], r12
0x18002d9da  mov     dword ptr [r9], 1
0x18002d9e1  mov     rcx, [r15]
0x18002d9e4  mov     rax, [rcx]
0x18002d9e7  mov     rax, [rax+0C8h]
0x18002d9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9f3  test    eax, eax
0x18002d9f5  jnz     loc_18002DBB0
0x18002d9fb  mov     rcx, [r15]
0x18002d9fe  mov     rax, [rcx]
0x18002da01  lea     rdx, [rbp+4Fh+arg_18]
0x18002da05  mov     rax, [rax+30h]
0x18002da09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da0e  mov     esi, eax
0x18002da10  test    eax, eax
0x18002da12  js      loc_18002DDF1
0x18002da18  mov     ecx, [rbp+4Fh+arg_18]
0x18002da1b  sub     ecx, 1
0x18002da1e  jz      loc_18002DB8A
0x18002da24  sub     ecx, 2
0x18002da27  jz      short loc_18002DA35
0x18002da29  cmp     ecx, 0Ch
0x18002da2c  jnz     short loc_18002D9E1
0x18002da2e  mov     [rsp+100h+var_D0], r12
0x18002da33  jmp     short loc_18002D9E1
0x18002da35  cmp     [rsp+100h+var_D0], r12
0x18002da3a  jz      short loc_18002D9E1
0x18002da3c  mov     dword ptr [rsp+100h+var_E0], r12d
0x18002da41  mov     rcx, [r15]
0x18002da44  mov     rax, [rcx]
0x18002da47  lea     rdx, [rsp+100h+var_E0]
0x18002da4c  mov     rax, [rax+0C0h]
0x18002da53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da58  mov     esi, eax
0x18002da5a  test    eax, eax
0x18002da5c  js      loc_18002DDF1
0x18002da62  cmp     dword ptr [rsp+100h+var_E0], 2
0x18002da67  jnz     loc_18002D9E1
0x18002da6d  mov     rcx, [r15]
0x18002da70  mov     rax, [rcx]
0x18002da73  xor     r8d, r8d
0x18002da76  lea     rdx, [rbp+4Fh+String2]
0x18002da7a  mov     rax, [rax+80h]
0x18002da81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da86  mov     esi, eax
0x18002da88  test    eax, eax
0x18002da8a  js      loc_18002DDF1
0x18002da90  mov     rcx, [r15]
0x18002da93  mov     rax, [rcx]
0x18002da96  xor     r8d, r8d
0x18002da99  lea     rdx, [rsp+100h+var_D0]
0x18002da9e  mov     rax, [rax+70h]
0x18002daa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002daa7  mov     esi, eax
0x18002daa9  test    eax, eax
0x18002daab  js      loc_18002DDF1
0x18002dab1  mov     rdx, [rsp+100h+var_D0]; String2
0x18002dab6  lea     rcx, aId_1; "Id"
0x18002dabd  call    cs:__imp__wcsicmp
0x18002dac3  test    eax, eax
0x18002dac5  jnz     short loc_18002DAF1
0x18002dac7  mov     rdx, [rbp+4Fh+String2]
0x18002dacb  test    rdx, rdx
0x18002dace  jz      short loc_18002DAD6
0x18002dad0  mov     dword ptr [rdi], 1
0x18002dad6  lea     rcx, [rbp+4Fh+psz]
0x18002dada  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18002dadf  test    al, al
0x18002dae1  jnz     loc_18002D9E1
0x18002dae7  mov     esi, 8007000Eh
0x18002daec  jmp     loc_18002DDF1
0x18002daf1  mov     rdx, [rsp+100h+var_D0]; String2
0x18002daf6  lea     rcx, aProductid; "ProductId"
0x18002dafd  call    cs:__imp__wcsicmp
0x18002db03  test    eax, eax
0x18002db05  jnz     short loc_18002DB11
0x18002db07  mov     rdx, [rbp+4Fh+String2]
0x18002db0b  lea     rcx, [rbp+4Fh+lpsz]
0x18002db0f  jmp     short loc_18002DADA
0x18002db11  mov     rdx, [rsp+100h+var_D0]; String2
0x18002db16  lea     rcx, aIssuerdisplayn; "IssuerDisplayName"
0x18002db1d  call    cs:__imp__wcsicmp
0x18002db23  test    eax, eax
0x18002db25  jnz     short loc_18002DB31
0x18002db27  mov     rdx, [rbp+4Fh+String2]
0x18002db2b  lea     rcx, [rbp+4Fh+var_40]
0x18002db2f  jmp     short loc_18002DADA
0x18002db31  mov     rdx, [rsp+100h+var_D0]; String2
0x18002db36  lea     rcx, aWebserviceurl; "WebServiceUrl"
0x18002db3d  call    cs:__imp__wcsicmp
0x18002db43  test    eax, eax
0x18002db45  jnz     short loc_18002DB51
0x18002db47  mov     rdx, [rbp+4Fh+String2]
0x18002db4b  lea     rcx, [rbp+4Fh+var_60]
0x18002db4f  jmp     short loc_18002DADA
0x18002db51  mov     rdx, [rsp+100h+var_D0]; String2
0x18002db56  lea     rcx, aKind; "Kind"
0x18002db5d  call    cs:__imp__wcsicmp
0x18002db63  test    eax, eax
0x18002db65  jnz     loc_18002D9E1
0x18002db6b  lea     rdx, [rbp+4Fh+arg_8]; enum __MIDL___MIDL_itf_wallettypes_0000_0000_0001 *
0x18002db6f  mov     rcx, [rbp+4Fh+String2]; String2
0x18002db73  call    ?ConvertItemTypeElementValueToWalletItemType@@YAJPEBGAEAW4__MIDL___MIDL_itf_wallettypes_0000_0000_0001@@@Z; ConvertItemTypeElementValueToWalletItemType(ushort const *,__MIDL___MIDL_itf_wallettypes_0000_0000_0001 &)
0x18002db78  test    eax, eax
0x18002db7a  jns     loc_18002D9E1
0x18002db80  mov     esi, 803A0053h
0x18002db85  jmp     loc_18002DDF1
0x18002db8a  mov     rcx, [r15]
0x18002db8d  mov     rax, [rcx]
0x18002db90  xor     r8d, r8d
0x18002db93  lea     rdx, [rsp+100h+var_D0]
0x18002db98  mov     rax, [rax+70h]
0x18002db9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dba1  mov     esi, eax
0x18002dba3  test    eax, eax
0x18002dba5  jns     loc_18002D9E1
0x18002dbab  jmp     loc_18002DDF1
0x18002dbb0  mov     rcx, [rbp+4Fh+psz]; psz
0x18002dbb4  cmp     rcx, [rbp+4Fh+var_90]
0x18002dbb8  jz      short loc_18002DC0C
0x18002dbba  mov     rax, [rbp+4Fh+lpsz]
0x18002dbbe  lea     r9, [rsp+100h+var_D8]
0x18002dbc3  cmp     rax, [rbp+4Fh+var_B8]
0x18002dbc7  jz      short loc_18002DBD9
0x18002dbc9  xor     r8d, r8d
0x18002dbcc  mov     rdx, rcx; OLECHAR *
0x18002dbcf  mov     rcx, rax; psz
0x18002dbd2  call    ?GetItemOwnedByApp@Utils@Wallet@@YAJPEBG0HAEAV?$CComPtr@UIWalletItem@@@ATL@@@Z; Wallet::Utils::GetItemOwnedByApp(ushort const *,ushort const *,int,ATL::CComPtr<IWalletItem> &)
0x18002dbd7  jmp     short loc_18002DBF6
0x18002dbd9  mov     r8, [rbp+4Fh+var_40]
0x18002dbdd  cmp     r8, [rbp+4Fh+var_38]
0x18002dbe1  cmovz   r8, r12
0x18002dbe5  mov     rdx, [rbp+4Fh+var_60]
0x18002dbe9  cmp     rdx, [rbp+4Fh+var_58]
0x18002dbed  cmovz   rdx, r12
0x18002dbf1  call    ?GetItemByWebServiceUrlOrIssuer@Utils@Wallet@@YAJPEBG00AEAV?$CComPtr@UIWalletItem@@@ATL@@@Z; Wallet::Utils::GetItemByWebServiceUrlOrIssuer(ushort const *,ushort const *,ushort const *,ATL::CComPtr<IWalletItem> &)
0x18002dbf6  mov     esi, eax
0x18002dbf8  cmp     eax, 803A0000h
0x18002dbfd  jz      short loc_18002DC0C
0x18002dbff  test    eax, eax
0x18002dc01  js      loc_18002DDF1
0x18002dc07  mov     [rbx], r12d
0x18002dc0a  jmp     short loc_18002DC0F
0x18002dc0c  mov     esi, r12d
0x18002dc0f  cmp     [rbx], r12d
0x18002dc12  jz      loc_18002DCFD
0x18002dc18  mov     [rsp+100h+var_E0], r12
0x18002dc1d  cmp     [rbp+4Fh+arg_8], r12d
0x18002dc21  jnz     short loc_18002DC37
0x18002dc23  mov     esi, 803A0053h
0x18002dc28  lea     rcx, [rsp+100h+var_E0]
0x18002dc2d  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18002dc32  jmp     loc_18002DDF1
0x18002dc37  lea     rcx, [rsp+100h+var_E0]
0x18002dc3c  call    ?GetWalletItemManager@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletItemManager@@@ATL@@@Z; Wallet::Utils::GetWalletItemManager(ATL::CComPtr<IWalletItemManager> &)
0x18002dc41  test    eax, eax
0x18002dc43  jns     short loc_18002DC49
0x18002dc45  mov     esi, eax
0x18002dc47  jmp     short loc_18002DC28
0x18002dc49  mov     rdi, [rsp+100h+var_E0]
0x18002dc4e  mov     rax, [rdi]
0x18002dc51  mov     rbx, [rax+28h]
0x18002dc55  lea     rcx, [rsp+100h+var_D8]
0x18002dc5a  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x18002dc5f  mov     r8, rax
0x18002dc62  mov     edx, [rbp+4Fh+arg_8]
0x18002dc65  mov     rcx, rdi
0x18002dc68  mov     rax, rbx
0x18002dc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc70  test    eax, eax
0x18002dc72  js      short loc_18002DC45
0x18002dc74  mov     r8, [rbp+4Fh+psz]
0x18002dc78  cmp     r8, [rbp+4Fh+var_90]
0x18002dc7c  jz      short loc_18002DC91
0x18002dc7e  mov     edx, 0BB9h
0x18002dc83  mov     rcx, [rsp+100h+var_D8]
0x18002dc88  call    ??$SetTStringProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBG@Z; Wallet::Utils::SetTStringProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ushort const *)
0x18002dc8d  test    eax, eax
0x18002dc8f  js      short loc_18002DC45
0x18002dc91  mov     rbx, [rbp+4Fh+lpsz]
0x18002dc95  cmp     rbx, [rbp+4Fh+var_B8]
0x18002dc99  jz      short loc_18002DCEE
0x18002dc9b  mov     rcx, rbx; lpsz
0x18002dc9e  call    ?IsPhoneProductId@Utils@Wallet@@YA_NPEBG@Z; Wallet::Utils::IsPhoneProductId(ushort const *)
0x18002dca3  test    al, al
0x18002dca5  jz      short loc_18002DCC1
0x18002dca7  mov     [rbp+4Fh+var_A0], r12
0x18002dcab  lea     rdx, [rbp+4Fh+var_A0]
0x18002dcaf  mov     rcx, rbx
0x18002dcb2  call    ?GetApplicationInfoFromAppProductId@Utils@Wallet@@YAJPEBGAEAV?$CComPtr@UIPMApplicationInfo@@@ATL@@@Z; Wallet::Utils::GetApplicationInfoFromAppProductId(ushort const *,ATL::CComPtr<IPMApplicationInfo> &)
0x18002dcb7  nop
0x18002dcb8  lea     rcx, [rbp+4Fh+var_A0]
0x18002dcbc  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002dcc1  mov     r8, [rbp+4Fh+lpsz]
0x18002dcc5  mov     edx, 0BB8h
0x18002dcca  mov     rcx, [rsp+100h+var_D8]
0x18002dccf  call    ??$SetTStringProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBG@Z; Wallet::Utils::SetTStringProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ushort const *)
0x18002dcd4  test    eax, eax
0x18002dcd6  js      loc_18002DC45
0x18002dcdc  lea     rcx, [rsp+100h+var_D8]
0x18002dce1  call    ?LinkItemToApp@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletItem@@@ATL@@H@Z; Wallet::Utils::LinkItemToApp(ATL::CComPtr<IWalletItem> &,int)
0x18002dce6  test    eax, eax
0x18002dce8  js      loc_18002DC45
0x18002dcee  lea     rcx, [rsp+100h+var_E0]
0x18002dcf3  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18002dcf8  jmp     loc_18002DDDD
0x18002dcfd  mov     dword ptr [rsp+100h+var_E0], r12d
0x18002dd02  mov     rcx, [rsp+100h+var_D8]
0x18002dd07  mov     rax, [rcx]
0x18002dd0a  lea     rdx, [rsp+100h+var_E0]
0x18002dd0f  mov     rax, [rax+28h]
0x18002dd13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd18  test    eax, eax
0x18002dd1a  jns     short loc_18002DD23
0x18002dd1c  mov     esi, eax
0x18002dd1e  jmp     loc_18002DDF1
0x18002dd23  mov     edi, [rbp+4Fh+arg_8]
0x18002dd26  cmp     dword ptr [rsp+100h+var_E0], edi
0x18002dd2a  jnz     loc_18002DB80
0x18002dd30  mov     rbx, r12
0x18002dd33  lea     rdx, qword_180052550
0x18002dd3a  mov     edx, [rdx+rbx*4]
0x18002dd3d  cmp     edx, 0BB8h
0x18002dd43  jnz     short loc_18002DD4F
0x18002dd45  mov     rax, [rbp+4Fh+var_B8]
0x18002dd49  cmp     [rbp+4Fh+lpsz], rax
0x18002dd4d  jnz     short loc_18002DD81
0x18002dd4f  mov     rcx, [rsp+100h+var_D8]
0x18002dd54  xorps   xmm0, xmm0
0x18002dd57  xor     eax, eax
0x18002dd59  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x18002dd5d  mov     [rbp+4Fh+var_68], rax
0x18002dd61  test    rcx, rcx
0x18002dd64  jz      short loc_18002DD77
0x18002dd66  mov     rax, [rcx]
0x18002dd69  lea     r8, [rbp+4Fh+pvar]
0x18002dd6d  mov     rax, [rax+38h]
0x18002dd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd76  nop
0x18002dd77  lea     rcx, [rbp+4Fh+pvar]; pvar
0x18002dd7b  call    cs:__imp_PropVariantClear
0x18002dd81  inc     rbx
0x18002dd84  cmp     rbx, 1Ch
0x18002dd88  jnz     short loc_18002DD33
0x18002dd8a  cmp     edi, 4
0x18002dd8d  jnz     short loc_18002DDC6
0x18002dd8f  mov     rcx, [rsp+100h+var_D8]
0x18002dd94  xorps   xmm0, xmm0
0x18002dd97  xor     eax, eax
0x18002dd99  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x18002dd9d  mov     [rbp+4Fh+var_68], rax
0x18002dda1  test    rcx, rcx
0x18002dda4  jz      short loc_18002DDBC
0x18002dda6  mov     rax, [rcx]
0x18002dda9  lea     r8, [rbp+4Fh+pvar]
0x18002ddad  mov     edx, 1F4h
0x18002ddb2  mov     rax, [rax+38h]
0x18002ddb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddbb  nop
0x18002ddbc  lea     rcx, [rbp+4Fh+pvar]; pvar
0x18002ddc0  call    cs:__imp_PropVariantClear
  ... truncated ...
```
