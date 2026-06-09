# Wallet::WalletItemManager::GetFilteredList(ATL::CComPtr<IWalletItemList> &,Wallet::WalletItemManager::FilterCondition *,uint,ulong,Wallet::WalletItemList *)

- ea: `0x1800222bc`
- end: `0x1800227ad`
- name: `?GetFilteredList@WalletItemManager@Wallet@@AEAAJAEAV?$CComPtr@UIWalletItemList@@@ATL@@PEAUFilterCondition@12@IKPEAVWalletItemList@2@@Z`
- size: `1265`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180022928`
- `0x180022e80`

## callees

- `0x180003ae4`
- `0x1800043b8`
- `0x18000d8d8`
- `0x18000d928`
- `0x180013f78`
- `0x180013fa0`
- `0x180013fe4`
- `0x18001400c`
- `0x1800222bc`
- `0x180024830`
- `0x180037238`
- `0x180038488`
- `0x180038fe4`
- `0x180039058`
- `0x180045010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180022655`
- `msvcrt!_wcsicmp` at `0x180022655`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800225dc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180022611`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800225dc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180022611`
- `UserDataLanguageUtil!IsMatchingPrefix` at `0x18002245a`
- `UserDataLanguageUtil!IsMatchingPrefix` at `0x180022528`
- `UserDataLanguageUtil!IsMatchingPrefix` at `0x18002245a`
- `UserDataLanguageUtil!IsMatchingPrefix` at `0x180022528`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800226ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800226ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800226e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002277f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800226ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800226ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800226e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002277f`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItemManager::GetFilteredList(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        char a5,
        __int64 a6)
{
  _QWORD *v7; // rbx
  int v8; // esi
  unsigned int v9; // r12d
  unsigned int v10; // r15d
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  __int64 *v13; // rax
  int v14; // eax
  int v15; // r13d
  struct IWalletItem *v16; // rdx
  _WORD *v17; // rax
  __int64 i; // rbx
  const void *v19; // rdx
  __int64 v20; // r8
  unsigned int j; // r15d
  BOOL v22; // ebx
  int v23; // eax
  const struct tagPROPVARIANT *v24; // r8
  int v25; // ecx
  __int64 v26; // rcx
  int v27; // eax
  bool v28; // zf
  __int64 v29; // r8
  const WCHAR *bstrVal; // rcx
  __int64 v31; // rdx
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  bool v36; // zf
  __int64 v37; // rdx
  __int64 v38; // rdx
  const wchar_t *v39; // rcx
  const wchar_t *v40; // rdx
  int v41; // eax
  int v42; // eax
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, unsigned __int64, _QWORD); // rbx
  unsigned __int64 WalletItemId; // rax
  int v46; // eax
  Wallet::Utils *pvar; // [rsp+38h] [rbp-A9h] BYREF
  struct tagPROPVARIANT pvar_8; // [rsp+40h] [rbp-A1h] BYREF
  unsigned int v50; // [rsp+60h] [rbp-81h]
  _QWORD v51[3]; // [rsp+68h] [rbp-79h] BYREF
  void *v52[4]; // [rsp+80h] [rbp-61h] BYREF
  void *v53[4]; // [rsp+A0h] [rbp-41h] BYREF
  void *v54[13]; // [rsp+C0h] [rbp-21h] BYREF
  __int64 v55; // [rsp+138h] [rbp+57h] BYREF
  _QWORD *v56; // [rsp+140h] [rbp+5Fh]
  unsigned int v57; // [rsp+148h] [rbp+67h] BYREF
  unsigned int v58; // [rsp+150h] [rbp+6Fh]

  v58 = a4;
  v56 = a2;
  v55 = a1;
  v57 = 0;
  v7 = a2;
  if ( !a3 || !a6 )
    return (unsigned int)-2147467261;
  v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*a2 + 32LL))(*a2, &v57);
  if ( v8 >= 0 )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
LABEL_6:
    v50 = v10;
    if ( v10 < v57 )
    {
      pvar = 0;
      v11 = *v7;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*v7 + 40LL);
      v13 = ce::pointerTo<IWalletNotification>((__int64 *)&pvar);
      v14 = v12(v11, v10, v13);
      if ( v14 < 0 )
      {
        v8 = v14;
        goto LABEL_82;
      }
      v15 = 0;
      utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::vector<unsigned __int64,utl::allocator<unsigned __int64>>(v51);
      v17 = *(_WORD **)(a3 + 8);
      if ( v17 && *v17 == 8 && (int)Wallet::Utils::GetWalletItemCustomPropertyKeys(&pvar, v16, v51) >= 0 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((__int64)v54);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v54,
          *(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL));
        for ( i = v51[0]; i != v51[1]; i += 32 )
        {
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((__int64)v53);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((__int64)&pvar_8);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((__int64)v52);
          v19 = *(const void **)i;
          v20 = (__int64)(*(_QWORD *)(i + 8) - *(_QWORD *)i) >> 1;
          LODWORD(v55) = 0;
          if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                  v53,
                  v19,
                  v20) )
          {
            v8 = -2147024882;
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v52);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)&pvar_8);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v53);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v54);
            goto LABEL_78;
          }
          if ( (int)Wallet::Utils::GetItemCustomProperty(
                      (_DWORD)pvar,
                      v53[0],
                      (unsigned int)&pvar_8,
                      (unsigned int)v52,
                      (__int64)&v55) >= 0
            && ((_DWORD)v55 == 8 || (_DWORD)v55 == 2)
            && *(_QWORD *)&pvar_8.vt != pvar_8.hVal.QuadPart
            && IsMatchingPrefix((const unsigned __int16 *)v54[0], (const unsigned __int16 *)v52[0], 1u, 0) )
          {
            v15 = 1;
          }
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v52);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)&pvar_8);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v53);
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v54);
      }
      for ( j = 0; ; ++j )
      {
        if ( j >= v58 )
        {
          if ( !v15 )
            goto LABEL_76;
LABEL_75:
          v43 = a6;
          v44 = *(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)(a6 + 8) + 8LL);
          WalletItemId = Wallet::Utils::GetWalletItemId(pvar, v16);
          v46 = v44(v43 + 8, WalletItemId, v9);
          if ( v46 >= 0 )
            goto LABEL_76;
          v8 = v46;
LABEL_78:
          utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_Uninit(v51);
LABEL_82:
          ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&pvar);
          return (unsigned int)v8;
        }
        v22 = 0;
        memset(&pvar_8, 0, sizeof(pvar_8));
        v23 = (*(__int64 (__fastcall **)(Wallet::Utils *, _QWORD, struct tagPROPVARIANT *))(*(_QWORD *)pvar + 48LL))(
                pvar,
                *(unsigned int *)(a3 + 24LL * j),
                &pvar_8);
        v25 = *(_DWORD *)(a3 + 24LL * j + 16);
        if ( v23 < 0 )
        {
          if ( (v25 & 4) != 0 )
          {
LABEL_70:
            v42 = a5 & 1;
LABEL_66:
            if ( v42 || j == v58 - 1 )
            {
              PropVariantClear((PROPVARIANT *)&pvar_8);
              goto LABEL_75;
            }
            goto LABEL_72;
          }
        }
        else
        {
          if ( (v25 & 8) != 0 )
            goto LABEL_70;
          if ( (v25 & 1) != 0 )
          {
            v26 = *(_QWORD *)(a3 + 24LL * j + 8);
            if ( *(_WORD *)v26 != 8 || pvar_8.vt != 8 )
              goto LABEL_79;
            v27 = IsMatchingPrefix(*(const unsigned __int16 **)(v26 + 8), pvar_8.bstrVal, 1u, 0);
            if ( v27 )
              v9 = *(_DWORD *)(a3 + 24LL * j);
            v28 = v27 == 0;
LABEL_44:
            v22 = !v28;
            goto LABEL_65;
          }
          if ( (v25 & 2) != 0 )
          {
            v29 = *(_QWORD *)(a3 + 24LL * j + 8);
            if ( *(_WORD *)v29 != 8 || pvar_8.vt != 8 )
              goto LABEL_79;
            bstrVal = &sourceString;
            if ( pvar_8.hVal.QuadPart )
              bstrVal = pvar_8.bstrVal;
            v31 = -1;
            do
              ++v31;
            while ( bstrVal[v31] );
            v32 = *(_QWORD *)(v29 + 8);
            v33 = -1;
            do
              ++v33;
            while ( *(_WORD *)(v32 + 2 * v33) );
            v34 = utl::_StringTraits<tlx::transform_traits<unsigned short,tlx::ascii_toupper_transform>>::find(
                    (_DWORD)bstrVal,
                    v31,
                    v29,
                    v32,
                    v33);
            if ( v34 != -1 )
              v9 = *(_DWORD *)(a3 + 24LL * j);
            v28 = v34 == -1;
            goto LABEL_44;
          }
          if ( (v25 & 0x20) != 0 )
          {
            v35 = *(_QWORD *)(a3 + 24LL * j + 8);
            if ( *(_WORD *)v35 != 64 || pvar_8.vt != 64 )
              goto LABEL_79;
            v36 = CompareFileTime(&pvar_8.filetime, (const FILETIME *)(v35 + 8)) == 1;
LABEL_61:
            v22 = v36;
            goto LABEL_65;
          }
          if ( (v25 & 0x10) != 0 )
          {
            v37 = *(_QWORD *)(a3 + 24LL * j + 8);
            if ( *(_WORD *)v37 != 64 || pvar_8.vt != 64 )
              goto LABEL_79;
            v36 = CompareFileTime(&pvar_8.filetime, (const FILETIME *)(v37 + 8)) == -1;
            goto LABEL_61;
          }
          if ( (v25 & 0x40) != 0 )
          {
            v38 = *(_QWORD *)(a3 + 24LL * j + 8);
            if ( *(_WORD *)v38 != 8 || pvar_8.vt != 8 )
            {
LABEL_79:
              v8 = -2147418113;
              PropVariantClear((PROPVARIANT *)&pvar_8);
              goto LABEL_78;
            }
            v39 = &sourceString;
            v40 = *(const wchar_t **)(v38 + 8);
            if ( pvar_8.hVal.QuadPart )
              v39 = pvar_8.bstrVal;
            v41 = _wcsicmp(v39, v40);
            if ( !v41 )
              v9 = *(_DWORD *)(a3 + 24LL * j);
            v36 = v41 == 0;
            goto LABEL_61;
          }
          if ( (v25 & 4) == 0
            && (unsigned int)Wallet::Utils::ArePropVariantsEqual(*(Wallet::Utils **)(a3 + 24LL * j + 8), &pvar_8, v24) )
          {
            v9 = *(_DWORD *)(a3 + 24LL * j);
            v22 = 1;
          }
        }
LABEL_65:
        v42 = a5 & 1;
        if ( v22 )
          goto LABEL_66;
        if ( (a5 & 1) == 0 )
        {
          PropVariantClear((PROPVARIANT *)&pvar_8);
LABEL_76:
          utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_Uninit(v51);
          ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&pvar);
          v7 = v56;
          v10 = v50 + 1;
          goto LABEL_6;
        }
LABEL_72:
        PropVariantClear((PROPVARIANT *)&pvar_8);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800222bc  mov     rax, rsp
0x1800222bf  mov     [rax+20h], r9d
0x1800222c3  mov     [rax+10h], rdx
0x1800222c7  mov     [rax+8], rcx
0x1800222cb  push    rbp
0x1800222cc  push    rbx
0x1800222cd  push    rsi
0x1800222ce  push    rdi
0x1800222cf  push    r12
0x1800222d1  push    r13
0x1800222d3  push    r14
0x1800222d5  push    r15
0x1800222d7  lea     rbp, [rax-4Fh]
0x1800222db  sub     rsp, 0E8h
0x1800222e2  xor     edi, edi
0x1800222e4  mov     r14, r8
0x1800222e7  mov     [rbp+47h+arg_10], edi
0x1800222ea  mov     rbx, rdx
0x1800222ed  test    r8, r8
0x1800222f0  jnz     short loc_1800222FC
0x1800222f2  mov     esi, 80004003h
0x1800222f7  jmp     loc_180022797
0x1800222fc  cmp     [rbp+47h+arg_28], rdi
0x180022300  jz      short loc_1800222F2
0x180022302  mov     rcx, [rdx]
0x180022305  lea     rdx, [rbp+47h+arg_10]
0x180022309  mov     rax, [rcx]
0x18002230c  mov     rax, [rax+20h]
0x180022310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022315  mov     esi, eax
0x180022317  test    eax, eax
0x180022319  js      loc_180022797
0x18002231f  mov     esi, edi
0x180022321  mov     r12d, edi
0x180022324  mov     r15d, edi
0x180022327  mov     [rsp+120h+var_C8], r15d
0x18002232c  cmp     r15d, [rbp+47h+arg_10]
0x180022330  jnb     loc_180022797
0x180022336  mov     [rsp+120h+pvar], rdi
0x18002233b  lea     rcx, [rsp+120h+pvar]
0x180022340  mov     rdi, [rbx]
0x180022343  mov     rax, [rdi]
0x180022346  mov     rbx, [rax+28h]
0x18002234a  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x18002234f  mov     r8, rax
0x180022352  mov     edx, r15d
0x180022355  mov     rax, rbx
0x180022358  mov     rcx, rdi
0x18002235b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022360  xor     edi, edi
0x180022362  test    eax, eax
0x180022364  js      loc_18002278B
0x18002236a  lea     rcx, [rbp+47h+var_C0]
0x18002236e  mov     r13d, edi
0x180022371  call    ??0?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA@XZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::vector<unsigned __int64,utl::allocator<unsigned __int64>>(void)
0x180022376  mov     rax, [r14+8]
0x18002237a  test    rax, rax
0x18002237d  jz      loc_18002249A
0x180022383  lea     r15d, [rdi+8]
0x180022387  cmp     [rax], r15w
0x18002238b  jnz     loc_18002249A
0x180022391  lea     r8, [rbp+47h+var_C0]
0x180022395  lea     rcx, [rsp+120h+pvar]
0x18002239a  call    ?GetWalletItemCustomPropertyKeys@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletItem@@@ATL@@PEAW4__MIDL___MIDL_itf_iwalletcustomproperty_0000_0000_0002@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; Wallet::Utils::GetWalletItemCustomPropertyKeys(ATL::CComPtr<IWalletItem> &,__MIDL___MIDL_itf_iwalletcustomproperty_0000_0000_0002 *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x18002239f  test    eax, eax
0x1800223a1  js      loc_18002249A
0x1800223a7  lea     rcx, [rbp+47h+var_68]
0x1800223ab  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800223b0  mov     rdx, [r14+8]
0x1800223b4  lea     rcx, [rbp+47h+var_68]
0x1800223b8  mov     rdx, [rdx+8]
0x1800223bc  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800223c1  mov     rbx, [rbp+47h+var_C0]
0x1800223c5  cmp     rbx, [rbp+47h+var_B8]
0x1800223c9  jz      loc_180022491
0x1800223cf  lea     rcx, [rbp+47h+var_88]
0x1800223d3  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800223d8  lea     rcx, [rsp+120h+pvar+8]
0x1800223dd  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800223e2  lea     rcx, [rbp+47h+var_A8]
0x1800223e6  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800223eb  mov     r8, [rbx+8]
0x1800223ef  lea     rcx, [rbp+47h+var_88]
0x1800223f3  sub     r8, [rbx]
0x1800223f6  mov     rdx, [rbx]
0x1800223f9  sar     r8, 1
0x1800223fc  mov     dword ptr [rbp+47h+arg_0], edi
0x1800223ff  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180022404  test    al, al
0x180022406  jz      loc_180022740
0x18002240c  mov     rdx, [rbp+47h+var_88]
0x180022410  lea     rax, [rbp+47h+arg_0]
0x180022414  mov     rcx, [rsp+120h+pvar]
0x180022419  lea     r9, [rbp+47h+var_A8]
0x18002241d  lea     r8, [rsp+120h+pvar+8]
0x180022422  mov     [rsp+20h], rax
0x180022427  call    ?GetItemCustomProperty@Utils@Wallet@@YAJPEAUIWalletItem@@PEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@2AEAW4__MIDL___MIDL_itf_iwalletcustomproperty_0000_0000_0001@@@Z; Wallet::Utils::GetItemCustomProperty(IWalletItem *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,__MIDL___MIDL_itf_iwalletcustomproperty_0000_0000_0001 &)
0x18002242c  test    eax, eax
0x18002242e  js      short loc_18002246C
0x180022430  cmp     dword ptr [rbp+47h+arg_0], r15d
0x180022434  jz      short loc_18002243C
0x180022436  cmp     dword ptr [rbp+47h+arg_0], 2
0x18002243a  jnz     short loc_18002246C
0x18002243c  mov     rax, qword ptr [rsp+120h+FileTime1.dwLowDateTime]
0x180022441  cmp     [rsp+120h+pvar+8], rax
0x180022446  jz      short loc_18002246C
0x180022448  mov     rdx, [rbp+47h+var_A8]
0x18002244c  xor     r9d, r9d
0x18002244f  mov     rcx, [rbp+47h+var_68]
0x180022453  lea     r15d, [r9+1]
0x180022457  mov     r8d, r15d
0x18002245a  call    cs:__imp_?IsMatchingPrefix@@YAHPEBG0KPEAE@Z; IsMatchingPrefix(ushort const *,ushort const *,ulong,uchar *)
0x180022460  test    eax, eax
0x180022462  cmovnz  r13d, r15d
0x180022466  mov     r15d, 8
0x18002246c  lea     rcx, [rbp+47h+var_A8]
0x180022470  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180022475  lea     rcx, [rsp+120h+pvar+8]
0x18002247a  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002247f  lea     rcx, [rbp+47h+var_88]
0x180022483  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180022488  add     rbx, 20h ; ' '
0x18002248c  jmp     loc_1800223C5
0x180022491  lea     rcx, [rbp+47h+var_68]
0x180022495  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002249a  mov     r15d, edi
0x18002249d  cmp     r15d, [rbp+47h+arg_18]
0x1800224a1  jnb     loc_1800226E9
0x1800224a7  mov     rcx, [rsp+120h+pvar]
0x1800224ac  lea     r8, [rsp+120h+pvar+8]
0x1800224b1  xor     eax, eax
0x1800224b3  xorps   xmm0, xmm0
0x1800224b6  mov     [rsp+48h], rax
0x1800224bb  mov     ebx, edi
0x1800224bd  mov     eax, r15d
0x1800224c0  movups  xmmword ptr [rsp+120h+pvar+8], xmm0
0x1800224c5  lea     rdi, [rax+rax*2]
0x1800224c9  mov     rax, [rcx]
0x1800224cc  mov     edx, [r14+rdi*8]
0x1800224d0  mov     rax, [rax+30h]
0x1800224d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224d9  mov     ecx, [r14+rdi*8+10h]
0x1800224de  xor     r10d, r10d
0x1800224e1  test    eax, eax
0x1800224e3  js      loc_1800226B6
0x1800224e9  lea     r9d, [r10+8]
0x1800224ed  test    r9b, cl
0x1800224f0  jnz     loc_1800226BB
0x1800224f6  lea     eax, [r10+1]
0x1800224fa  test    al, cl
0x1800224fc  jz      short loc_18002253C
0x1800224fe  mov     rcx, [r14+rdi*8+8]
0x180022503  cmp     [rcx], r9w
0x180022507  jnz     loc_180022775
0x18002250d  cmp     word ptr [rsp+120h+pvar+8], r9w
0x180022513  jnz     loc_180022775
0x180022519  mov     rdx, qword ptr [rsp+120h+FileTime1.dwLowDateTime]
0x18002251e  xor     r9d, r9d
0x180022521  mov     rcx, [rcx+8]
0x180022525  mov     r8d, eax
0x180022528  call    cs:__imp_?IsMatchingPrefix@@YAHPEBG0KPEAE@Z; IsMatchingPrefix(ushort const *,ushort const *,ulong,uchar *)
0x18002252e  test    eax, eax
0x180022530  jz      short loc_180022536
0x180022532  mov     r12d, [r14+rdi*8]
0x180022536  xor     edi, edi
0x180022538  test    eax, eax
0x18002253a  jmp     short loc_1800225AA
0x18002253c  test    cl, 2
0x18002253f  jz      short loc_1800225B4
0x180022541  mov     r8, [r14+rdi*8+8]
0x180022546  cmp     [r8], r9w
0x18002254a  jnz     loc_180022775
0x180022550  cmp     word ptr [rsp+120h+pvar+8], r9w
0x180022556  jnz     loc_180022775
0x18002255c  mov     rax, qword ptr [rsp+120h+FileTime1.dwLowDateTime]
0x180022561  lea     rcx, sourceString
0x180022568  test    rax, rax
0x18002256b  cmovnz  rcx, rax
0x18002256f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022573  mov     rdx, rbx
0x180022576  inc     rdx
0x180022579  cmp     [rcx+rdx*2], r10w
0x18002257e  jnz     short loc_180022576
0x180022580  mov     r9, [r8+8]
0x180022584  mov     rax, rbx
0x180022587  inc     rax
0x18002258a  cmp     [r9+rax*2], r10w
0x18002258f  jnz     short loc_180022587
0x180022591  mov     [rsp+20h], rax
0x180022596  call    ?find@?$_StringTraits@U?$transform_traits@GUascii_toupper_transform@tlx@@@tlx@@@utl@@SA_KPEBG_K101@Z; utl::_StringTraits<tlx::transform_traits<ushort,tlx::ascii_toupper_transform>>::find(ushort const *,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x18002259b  cmp     rax, rbx
0x18002259e  jz      short loc_1800225A4
0x1800225a0  mov     r12d, [r14+rdi*8]
0x1800225a4  xor     edi, edi
0x1800225a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800225aa  mov     ebx, edi
0x1800225ac  setnz   bl
0x1800225af  jmp     loc_180022691
0x1800225b4  test    cl, 20h
0x1800225b7  jz      short loc_1800225E9
0x1800225b9  mov     rdx, [r14+rdi*8+8]
0x1800225be  cmp     word ptr [rdx], 40h ; '@'
0x1800225c2  jnz     loc_180022775
0x1800225c8  cmp     word ptr [rsp+120h+pvar+8], 40h ; '@'
0x1800225ce  jnz     loc_180022775
0x1800225d4  add     rdx, r9; lpFileTime2
0x1800225d7  lea     rcx, [rsp+120h+FileTime1]; lpFileTime1
0x1800225dc  call    cs:__imp_CompareFileTime
0x1800225e2  xor     edi, edi
0x1800225e4  cmp     eax, 1
0x1800225e7  jmp     short loc_180022667
0x1800225e9  test    cl, 10h
0x1800225ec  jz      short loc_18002261E
0x1800225ee  mov     rdx, [r14+rdi*8+8]
0x1800225f3  cmp     word ptr [rdx], 40h ; '@'
0x1800225f7  jnz     loc_180022775
0x1800225fd  cmp     word ptr [rsp+120h+pvar+8], 40h ; '@'
0x180022603  jnz     loc_180022775
0x180022609  add     rdx, r9; lpFileTime2
0x18002260c  lea     rcx, [rsp+120h+FileTime1]; lpFileTime1
0x180022611  call    cs:__imp_CompareFileTime
0x180022617  xor     edi, edi
0x180022619  cmp     eax, 0FFFFFFFFh
0x18002261c  jmp     short loc_180022667
0x18002261e  test    cl, 40h
0x180022621  jz      short loc_18002266E
0x180022623  mov     rdx, [r14+rdi*8+8]
0x180022628  cmp     [rdx], r9w
0x18002262c  jnz     loc_180022775
0x180022632  cmp     word ptr [rsp+120h+pvar+8], r9w
0x180022638  jnz     loc_180022775
0x18002263e  mov     rax, qword ptr [rsp+120h+FileTime1.dwLowDateTime]
0x180022643  lea     rcx, sourceString
0x18002264a  mov     rdx, [rdx+8]; String2
0x18002264e  test    rax, rax
0x180022651  cmovnz  rcx, rax; String1
0x180022655  call    cs:__imp__wcsicmp
0x18002265b  test    eax, eax
0x18002265d  jnz     short loc_180022663
0x18002265f  mov     r12d, [r14+rdi*8]
0x180022663  xor     edi, edi
0x180022665  test    eax, eax
0x180022667  mov     ebx, edi
0x180022669  setz    bl
0x18002266c  jmp     short loc_180022691
0x18002266e  test    cl, 4
0x180022671  jnz     short loc_18002268F
0x180022673  mov     rcx, [r14+rdi*8+8]; this
0x180022678  lea     rdx, [rsp+120h+pvar+8]; struct tagPROPVARIANT *
0x18002267d  call    ?ArePropVariantsEqual@Utils@Wallet@@YAHAEBUtagPROPVARIANT@@0@Z; Wallet::Utils::ArePropVariantsEqual(tagPROPVARIANT const &,tagPROPVARIANT const &)
0x180022682  test    eax, eax
0x180022684  jz      short loc_18002268F
0x180022686  mov     r12d, [r14+rdi*8]
0x18002268a  mov     ebx, 1
0x18002268f  xor     edi, edi
0x180022691  mov     eax, dword ptr [rbp+47h+arg_20]
0x180022694  and     eax, 1
0x180022697  test    ebx, ebx
0x180022699  jz      short loc_1800226C5
0x18002269b  test    eax, eax
0x18002269d  jnz     short loc_1800226A9
0x18002269f  mov     eax, [rbp+47h+arg_18]
0x1800226a2  dec     eax
0x1800226a4  cmp     r15d, eax
0x1800226a7  jnz     short loc_1800226C9
0x1800226a9  lea     rcx, [rsp+120h+pvar+8]; pvar
0x1800226ae  call    cs:__imp_PropVariantClear
0x1800226b4  jmp     short loc_1800226EE
0x1800226b6  test    cl, 4
0x1800226b9  jz      short loc_18002268F
0x1800226bb  mov     eax, dword ptr [rbp+47h+arg_20]
0x1800226be  and     eax, 1
0x1800226c1  xor     edi, edi
0x1800226c3  jmp     short loc_18002269B
0x1800226c5  test    eax, eax
0x1800226c7  jz      short loc_1800226DC
0x1800226c9  lea     rcx, [rsp+120h+pvar+8]; pvar
0x1800226ce  call    cs:__imp_PropVariantClear
0x1800226d4  inc     r15d
0x1800226d7  jmp     loc_18002249D
0x1800226dc  lea     rcx, [rsp+120h+pvar+8]; pvar
0x1800226e1  call    cs:__imp_PropVariantClear
0x1800226e7  jmp     short loc_18002271C
0x1800226e9  test    r13d, r13d
0x1800226ec  jz      short loc_18002271C
0x1800226ee  mov     rdi, [rbp+47h+arg_28]
0x1800226f2  mov     rcx, [rsp+120h+pvar]; this
0x1800226f7  mov     rax, [rdi+8]
0x1800226fb  mov     rbx, [rax+8]
0x1800226ff  call    ?GetWalletItemId@Utils@Wallet@@YA_KPEAUIWalletItem@@@Z; Wallet::Utils::GetWalletItemId(IWalletItem *)
0x180022704  mov     rdx, rax
0x180022707  lea     rcx, [rdi+8]
0x18002270b  mov     rax, rbx
0x18002270e  mov     r8d, r12d
0x180022711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022716  xor     edi, edi
0x180022718  test    eax, eax
0x18002271a  js      short loc_180022787
0x18002271c  lea     rcx, [rbp+47h+var_C0]
0x180022720  call    ?_Uninit@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_Uninit(void)
  ... truncated ...
```
