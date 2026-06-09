# BrowserToolThreadWindow::FireJsonMessage(std::shared_ptr<PluginPendingMessage> &)

- ea: `0x180007f08`
- end: `0x180008502`
- name: `?FireJsonMessage@BrowserToolThreadWindow@@AEAAJAEAV?$shared_ptr@UPluginPendingMessage@@@std@@@Z`
- size: `1530`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008990`

## callees

- `0x18000193c`
- `0x180003858`
- `0x180003880`
- `0x1800045b4`
- `0x1800071b4`
- `0x1800073f4`
- `0x180007f08`
- `0x18000d66c`
- `0x18002dec0`
- `0x18002e3e0`
- `0x18002e4c8`
- `0x18002e948`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180008035`
- `OLEAUT32!__imp_SysAllocString` at `0x18000847e`
- `OLEAUT32!__imp_SysAllocString` at `0x180008035`
- `OLEAUT32!__imp_SysAllocString` at `0x18000847e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008285`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180008470`
- `OLEAUT32!__imp_SysFreeString` at `0x180008285`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180008470`
- `OLEAUT32!__imp_VariantInit` at `0x180008161`
- `OLEAUT32!__imp_VariantInit` at `0x180008224`
- `OLEAUT32!__imp_VariantInit` at `0x180008161`
- `OLEAUT32!__imp_VariantInit` at `0x180008224`
- `OLEAUT32!__imp_VariantClear` at `0x180008023`
- `OLEAUT32!__imp_VariantClear` at `0x180008152`
- `OLEAUT32!__imp_VariantClear` at `0x180008290`
- `OLEAUT32!__imp_VariantClear` at `0x18000829b`
- `OLEAUT32!__imp_VariantClear` at `0x1800082f6`
- `OLEAUT32!__imp_VariantClear` at `0x180008301`
- `OLEAUT32!__imp_VariantClear` at `0x180008351`
- `OLEAUT32!__imp_VariantClear` at `0x18000835c`
- `OLEAUT32!__imp_VariantClear` at `0x1800083ac`
- `OLEAUT32!__imp_VariantClear` at `0x180008023`
- `OLEAUT32!__imp_VariantClear` at `0x180008152`
- `OLEAUT32!__imp_VariantClear` at `0x180008290`
- `OLEAUT32!__imp_VariantClear` at `0x18000829b`
- `OLEAUT32!__imp_VariantClear` at `0x1800082f6`
- `OLEAUT32!__imp_VariantClear` at `0x180008301`
- `OLEAUT32!__imp_VariantClear` at `0x180008351`
- `OLEAUT32!__imp_VariantClear` at `0x18000835c`
- `OLEAUT32!__imp_VariantClear` at `0x1800083ac`
- `OLEAUT32!__imp_VariantCopy` at `0x1800080de`
- `OLEAUT32!__imp_VariantCopy` at `0x18000812f`
- `OLEAUT32!__imp_VariantCopy` at `0x1800081ee`
- `OLEAUT32!__imp_VariantCopy` at `0x1800080de`
- `OLEAUT32!__imp_VariantCopy` at `0x18000812f`
- `OLEAUT32!__imp_VariantCopy` at `0x1800081ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall BrowserToolThreadWindow::FireJsonMessage(__int64 a1, __int64 *a2)
{
  __int64 v5; // rax
  const OLECHAR *v6; // rcx
  _QWORD *v7; // rdx
  int HtmlDocument; // ebx
  struct IDispatchEx **v9; // r8
  _QWORD *v10; // rax
  VARIANTARG *v11; // rbx
  BSTR v12; // rax
  BSTR v13; // rdx
  const VARIANTARG *v14; // rdi
  VARIANTARG *v15; // rax
  VARIANTARG *v16; // rbx
  HRESULT v17; // eax
  BSTR v18; // rdx
  const VARIANTARG **v19; // rsi
  VARIANTARG *v20; // rbx
  const VARIANTARG *v21; // r15
  const VARIANTARG *i; // rdi
  HRESULT v23; // eax
  VARIANTARG *v24; // rbx
  HRESULT v25; // eax
  BSTR v26; // rdx
  struct ATL::CComBSTR *v27; // r9
  int v28; // edi
  struct IHTMLDocument2Vtbl *v29; // rbx
  __int128 v30; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-30h] BYREF
  VARIANTARG v32; // [rsp+48h] [rbp-18h] BYREF
  IHTMLDocument2 v33; // [rsp+A0h] [rbp+40h] BYREF
  ScriptHelpers *v34; // [rsp+B0h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp+58h] BYREF

  if ( !*(_QWORD *)(a1 + 96) )
    return 2147947423LL;
  v5 = *a2;
  if ( !*a2 )
    return 2147942487LL;
  v6 = *(const OLECHAR **)(v5 + 8);
  if ( *((_DWORD *)v6 - 4) )
  {
    if ( v6 )
    {
      v29 = (struct IHTMLDocument2Vtbl *)SysAllocString(v6);
      v33.lpVtbl = v29;
      if ( !v29 )
        ATL::AtlThrowImpl(-2147024882);
    }
    else
    {
      v29 = 0;
      v33.lpVtbl = 0;
    }
    v28 = (*(__int64 (__fastcall **)(_QWORD, struct IHTMLDocument2Vtbl *))(**(_QWORD **)(a1 + 152) + 168LL))(
            *(_QWORD *)(a1 + 152),
            v29);
    SysFreeString((BSTR)v29);
    goto LABEL_75;
  }
  v7 = *(_QWORD **)(v5 + 16);
  if ( !v7 || *v7 == v7[1] )
    return 0;
  v34 = 0;
  HtmlDocument = BrowserToolWindow::GetHtmlDocument(*(_QWORD *)(a1 + 96), &v34);
  if ( HtmlDocument )
  {
    if ( HtmlDocument >= 0 )
      HtmlDocument = -2147467259;
    if ( v34 )
      (*(void (__fastcall **)(ScriptHelpers *))(*(_QWORD *)v34 + 16LL))(v34);
    return (unsigned int)HtmlDocument;
  }
  v33.lpVtbl = 0;
  HtmlDocument = ScriptHelpers::GetGlobalNamespaceFromBrowser(v34, &v33, v9);
  if ( HtmlDocument )
  {
    if ( HtmlDocument >= 0 )
      HtmlDocument = -2147467259;
    if ( v33.lpVtbl )
      (*((void (__fastcall **)(struct IHTMLDocument2Vtbl *))v33.lpVtbl->QueryInterface + 2))(v33.lpVtbl);
    if ( v34 )
      (*(void (__fastcall **)(ScriptHelpers *))(*(_QWORD *)v34 + 16LL))(v34);
    return (unsigned int)HtmlDocument;
  }
  v30 = 0;
  v10 = operator new(0x40u);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  *(_QWORD *)&v30 = v10;
  bstrString = (BSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          &bstrString,
          (__int64)L"id") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&bstrString, L"id", (unsigned int)(HtmlDocument + 2));
  v11 = (VARIANTARG *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant>::operator[](
                        (__int64 *)&v30,
                        (__int64 *)&bstrString);
  VariantClear(v11);
  v11->vt = 8;
  v12 = SysAllocString(L"HOST|0");
  v11->llVal = (LONGLONG)v12;
  if ( !v12 )
  {
    v11->vt = 10;
    v11->lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v13 = bstrString - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)bstrString - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
  v14 = **(const VARIANTARG ***)(*a2 + 16);
  bstrString = (BSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          &bstrString,
          (__int64)L"method") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&bstrString, L"method", 6);
  v15 = (VARIANTARG *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant>::operator[](
                        (__int64 *)&v30,
                        (__int64 *)&bstrString);
  v16 = v15;
  if ( v15 != v14 )
  {
    v17 = VariantCopy(v15, v14);
    if ( v17 < 0 )
    {
      v16->vt = 10;
      v16->lVal = v17;
      ATL::AtlThrowImpl(v17);
    }
  }
  v18 = bstrString - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)bstrString - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
  v19 = *(const VARIANTARG ***)(*a2 + 16);
  v20 = (VARIANTARG *)*v19;
  v21 = v19[1];
  for ( i = *v19 + 1; i != v21; ++i )
  {
    if ( v20 != i )
    {
      v23 = VariantCopy(v20, i);
      if ( v23 < 0 )
      {
        v20->vt = 10;
        v20->lVal = v23;
        ATL::AtlThrowImpl(v23);
      }
    }
    ++v20;
  }
  VariantClear((VARIANTARG *)&v19[1][-1]);
  --v19[1];
  VariantInit(&pvarg);
  HtmlDocument = ScriptHelpers::CreateJScriptArray((__int64)v33.lpVtbl, *(_QWORD **)(*a2 + 16), &pvarg);
  if ( HtmlDocument )
  {
    if ( HtmlDocument >= 0 )
      HtmlDocument = -2147467259;
    VariantClear(&pvarg);
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>((void **)&v30);
    if ( v33.lpVtbl )
      (*((void (__fastcall **)(struct IHTMLDocument2Vtbl *))v33.lpVtbl->QueryInterface + 2))(v33.lpVtbl);
    if ( v34 )
      (*(void (__fastcall **)(ScriptHelpers *))(*(_QWORD *)v34 + 16LL))(v34);
    return (unsigned int)HtmlDocument;
  }
  bstrString = (BSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          &bstrString,
          (__int64)L"params") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&bstrString, L"params", (unsigned int)(HtmlDocument + 6));
  v24 = (VARIANTARG *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant>::operator[](
                        (__int64 *)&v30,
                        (__int64 *)&bstrString);
  if ( v24 != &pvarg )
  {
    v25 = VariantCopy(v24, &pvarg);
    if ( v25 < 0 )
    {
      v24->vt = 10;
      v24->lVal = v25;
      ATL::AtlThrowImpl(v25);
    }
  }
  v26 = bstrString - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)bstrString - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26);
  VariantInit(&v32);
  HtmlDocument = ScriptHelpers::CreateJScriptObject(v33.lpVtbl, (__int64)&v30, &v32);
  if ( HtmlDocument )
  {
    if ( HtmlDocument >= 0 )
      HtmlDocument = -2147467259;
    VariantClear(&v32);
    VariantClear(&pvarg);
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>((void **)&v30);
    if ( v33.lpVtbl )
      (*((void (__fastcall **)(struct IHTMLDocument2Vtbl *))v33.lpVtbl->QueryInterface + 2))(v33.lpVtbl);
    if ( v34 )
      (*(void (__fastcall **)(ScriptHelpers *))(*(_QWORD *)v34 + 16LL))(v34);
    return (unsigned int)HtmlDocument;
  }
  bstrString = 0;
  HtmlDocument = ScriptHelpers::JSONStringify(
                   (ScriptHelpers *)v33.lpVtbl,
                   (struct IDispatchEx *)&v32,
                   (struct ATL::CComVariant *)&bstrString,
                   v27);
  if ( HtmlDocument )
  {
    if ( HtmlDocument >= 0 )
      HtmlDocument = -2147467259;
    SysFreeString(bstrString);
    VariantClear(&v32);
    VariantClear(&pvarg);
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>((void **)&v30);
    if ( v33.lpVtbl )
      (*((void (__fastcall **)(struct IHTMLDocument2Vtbl *))v33.lpVtbl->QueryInterface + 2))(v33.lpVtbl);
    if ( v34 )
      (*(void (__fastcall **)(ScriptHelpers *))(*(_QWORD *)v34 + 16LL))(v34);
    return (unsigned int)HtmlDocument;
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(**(_QWORD **)(a1 + 152) + 168LL))(*(_QWORD *)(a1 + 152), bstrString);
  SysFreeString(bstrString);
  VariantClear(&v32);
  VariantClear(&pvarg);
  std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>((void **)&v30);
  if ( v33.lpVtbl )
    (*((void (__fastcall **)(struct IHTMLDocument2Vtbl *))v33.lpVtbl->QueryInterface + 2))(v33.lpVtbl);
  if ( v34 )
    (*(void (__fastcall **)(ScriptHelpers *))(*(_QWORD *)v34 + 16LL))(v34);
LABEL_75:
  if ( !v28 )
    return 0;
  if ( v28 >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x180007f08  push    rbp
0x180007f0a  push    rbx
0x180007f0b  push    rsi
0x180007f0c  push    rdi
0x180007f0d  push    r13
0x180007f0f  push    r14
0x180007f11  push    r15
0x180007f13  mov     rbp, rsp
0x180007f16  sub     rsp, 60h
0x180007f1a  mov     r14, rdx
0x180007f1d  mov     r13, rcx
0x180007f20  cmp     qword ptr [rcx+60h], 0
0x180007f25  jnz     short loc_180007F31
0x180007f27  mov     eax, 8007139Fh
0x180007f2c  jmp     loc_1800084A5
0x180007f31  mov     rax, [rdx]
0x180007f34  test    rax, rax
0x180007f37  jz      loc_1800084A0
0x180007f3d  mov     rcx, [rax+8]; psz
0x180007f41  cmp     dword ptr [rcx-10h], 0
0x180007f45  jnz     loc_180008447
0x180007f4b  mov     rdx, [rax+10h]
0x180007f4f  test    rdx, rdx
0x180007f52  jz      loc_18000847A
0x180007f58  mov     rax, [rdx+8]
0x180007f5c  cmp     [rdx], rax
0x180007f5f  jz      loc_18000847A
0x180007f65  mov     [rbp+arg_10], 0
0x180007f6d  lea     rdx, [rbp+arg_10]
0x180007f71  mov     rcx, [r13+60h]
0x180007f75  call    ?GetHtmlDocument@BrowserToolWindow@@QEBAJAEAV?$CComPtr@UIHTMLDocument2@@@ATL@@@Z; BrowserToolWindow::GetHtmlDocument(ATL::CComPtr<IHTMLDocument2> &)
0x180007f7a  mov     ebx, eax
0x180007f7c  test    eax, eax
0x180007f7e  jnz     loc_180008423
0x180007f84  mov     [rbp+arg_0.lpVtbl], 0
0x180007f8c  lea     rdx, [rbp+arg_0]; struct IHTMLDocument2 *
0x180007f90  mov     rcx, [rbp+arg_10]; this
0x180007f94  call    ?GetGlobalNamespaceFromBrowser@ScriptHelpers@@YAJPEAUIHTMLDocument2@@PEAPEAUIDispatchEx@@@Z; ScriptHelpers::GetGlobalNamespaceFromBrowser(IHTMLDocument2 *,IDispatchEx * *)
0x180007f99  mov     ebx, eax
0x180007f9b  test    eax, eax
0x180007f9d  jnz     loc_1800083EB
0x180007fa3  xorps   xmm0, xmm0
0x180007fa6  movdqu  [rbp+var_40], xmm0
0x180007fab  lea     ecx, [rax+40h]; Size
0x180007fae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007fb3  mov     [rax], rax
0x180007fb6  mov     [rax+8], rax
0x180007fba  mov     [rax+10h], rax
0x180007fbe  mov     word ptr [rax+18h], 101h
0x180007fc4  mov     qword ptr [rbp+var_40], rax
0x180007fc8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180007fcf  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180007fd6  mov     rax, [rax+18h]
0x180007fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fdf  add     rax, 18h
0x180007fe3  mov     [rbp+bstrString], rax
0x180007fe7  lea     rdx, aId; "id"
0x180007fee  lea     rcx, [rbp+bstrString]
0x180007ff2  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180007ff7  test    al, al
0x180007ff9  jnz     short loc_180008010
0x180007ffb  lea     r8d, [rbx+2]
0x180007fff  lea     rdx, aId; "id"
0x180008006  lea     rcx, [rbp+bstrString]
0x18000800a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000800f  nop
0x180008010  lea     rdx, [rbp+bstrString]
0x180008014  lea     rcx, [rbp+var_40]
0x180008018  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@@std@@QEAAAEAVCComVariant@ATL@@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x18000801d  mov     rbx, rax
0x180008020  mov     rcx, rax; pvarg
0x180008023  call    cs:__imp_VariantClear
0x180008029  mov     word ptr [rbx], 8
0x18000802e  lea     rcx, aHost0; "HOST|0"
0x180008035  call    cs:__imp_SysAllocString
0x18000803b  mov     [rbx+8], rax
0x18000803f  test    rax, rax
0x180008042  jz      loc_1800084CF
0x180008048  mov     rdx, [rbp+bstrString]
0x18000804c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180008050  or      esi, 0FFFFFFFFh
0x180008053  mov     eax, esi
0x180008055  lock xadd [rdx+10h], eax
0x18000805a  add     eax, esi
0x18000805c  test    eax, eax
0x18000805e  jg      short loc_18000806F
0x180008060  mov     rcx, [rdx]
0x180008063  mov     rax, [rcx]
0x180008066  mov     rax, [rax+8]
0x18000806a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000806f  mov     rax, [r14]
0x180008072  mov     rcx, [rax+10h]
0x180008076  mov     rdi, [rcx]
0x180008079  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008080  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008087  mov     rax, [rax+18h]
0x18000808b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008090  add     rax, 18h
0x180008094  mov     [rbp+bstrString], rax
0x180008098  lea     rdx, aMethod; "method"
0x18000809f  lea     rcx, [rbp+bstrString]
0x1800080a3  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1800080a8  test    al, al
0x1800080aa  jnz     short loc_1800080C3
0x1800080ac  mov     r8d, 6
0x1800080b2  lea     rdx, aMethod; "method"
0x1800080b9  lea     rcx, [rbp+bstrString]
0x1800080bd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800080c2  nop
0x1800080c3  lea     rdx, [rbp+bstrString]
0x1800080c7  lea     rcx, [rbp+var_40]
0x1800080cb  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@@std@@QEAAAEAVCComVariant@ATL@@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x1800080d0  mov     rbx, rax
0x1800080d3  cmp     rax, rdi
0x1800080d6  jz      short loc_1800080EC
0x1800080d8  mov     rdx, rdi; pvargSrc
0x1800080db  mov     rcx, rax; pvargDest
0x1800080de  call    cs:__imp_VariantCopy
0x1800080e4  test    eax, eax
0x1800080e6  js      loc_1800084E2
0x1800080ec  mov     rdx, [rbp+bstrString]
0x1800080f0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800080f4  mov     eax, esi
0x1800080f6  lock xadd [rdx+10h], eax
0x1800080fb  add     eax, esi
0x1800080fd  test    eax, eax
0x1800080ff  jg      short loc_180008110
0x180008101  mov     rcx, [rdx]
0x180008104  mov     rax, [rcx]
0x180008107  mov     rax, [rax+8]
0x18000810b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008110  mov     rax, [r14]
0x180008113  mov     rsi, [rax+10h]
0x180008117  mov     rbx, [rsi]
0x18000811a  mov     r15, [rsi+8]
0x18000811e  lea     rdi, [rbx+18h]
0x180008122  jmp     short loc_180008145
0x180008124  cmp     rbx, rdi
0x180008127  jz      short loc_18000813D
0x180008129  mov     rdx, rdi; pvargSrc
0x18000812c  mov     rcx, rbx; pvargDest
0x18000812f  call    cs:__imp_VariantCopy
0x180008135  test    eax, eax
0x180008137  js      loc_1800084B4
0x18000813d  add     rbx, 18h
0x180008141  add     rdi, 18h
0x180008145  cmp     rdi, r15
0x180008148  jnz     short loc_180008124
0x18000814a  mov     rcx, [rsi+8]
0x18000814e  sub     rcx, 18h; pvarg
0x180008152  call    cs:__imp_VariantClear
0x180008158  add     qword ptr [rsi+8], 0FFFFFFFFFFFFFFE8h
0x18000815d  lea     rcx, [rbp+pvarg]; pvarg
0x180008161  call    cs:__imp_VariantInit
0x180008167  nop
0x180008168  mov     rdx, [r14]
0x18000816b  lea     r8, [rbp+pvarg]
0x18000816f  mov     rdx, [rdx+10h]
0x180008173  mov     rcx, [rbp+arg_0.lpVtbl]
0x180008177  call    ?CreateJScriptArray@ScriptHelpers@@YAJPEAUIUnknown@@AEBV?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAVCComVariant@ATL@@@Z; ScriptHelpers::CreateJScriptArray(IUnknown *,std::vector<ATL::CComVariant> const &,ATL::CComVariant &)
0x18000817c  mov     ebx, eax
0x18000817e  test    eax, eax
0x180008180  jnz     loc_18000839E
0x180008186  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000818d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008194  mov     rax, [rax+18h]
0x180008198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000819d  add     rax, 18h
0x1800081a1  mov     [rbp+bstrString], rax
0x1800081a5  lea     rdx, aParams; "params"
0x1800081ac  lea     rcx, [rbp+bstrString]
0x1800081b0  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1800081b5  test    al, al
0x1800081b7  jnz     short loc_1800081CE
0x1800081b9  lea     r8d, [rbx+6]
0x1800081bd  lea     rdx, aParams; "params"
0x1800081c4  lea     rcx, [rbp+bstrString]
0x1800081c8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800081cd  nop
0x1800081ce  lea     rdx, [rbp+bstrString]
0x1800081d2  lea     rcx, [rbp+var_40]
0x1800081d6  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@@std@@QEAAAEAVCComVariant@ATL@@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x1800081db  mov     rbx, rax
0x1800081de  lea     rax, [rbp+pvarg]
0x1800081e2  cmp     rbx, rax
0x1800081e5  jz      short loc_1800081FC
0x1800081e7  lea     rdx, [rbp+pvarg]; pvargSrc
0x1800081eb  mov     rcx, rbx; pvargDest
0x1800081ee  call    cs:__imp_VariantCopy
0x1800081f4  test    eax, eax
0x1800081f6  js      loc_1800084F2
0x1800081fc  mov     rdx, [rbp+bstrString]
0x180008200  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180008204  or      eax, 0FFFFFFFFh
0x180008207  lock xadd [rdx+10h], eax
0x18000820c  sub     eax, 1
0x18000820f  jg      short loc_180008220
0x180008211  mov     rcx, [rdx]
0x180008214  mov     rax, [rcx]
0x180008217  mov     rax, [rax+8]
0x18000821b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008220  lea     rcx, [rbp+var_18]; pvarg
0x180008224  call    cs:__imp_VariantInit
0x18000822a  nop
0x18000822b  lea     r8, [rbp+var_18]
0x18000822f  lea     rdx, [rbp+var_40]
0x180008233  mov     rcx, [rbp+arg_0.lpVtbl]
0x180008237  call    ?CreateJScriptObject@ScriptHelpers@@YAJPEAUIUnknown@@AEBV?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@@std@@AEAVCComVariant@ATL@@@Z; ScriptHelpers::CreateJScriptObject(IUnknown *,std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant> const &,ATL::CComVariant &)
0x18000823c  mov     ebx, eax
0x18000823e  test    eax, eax
0x180008240  jnz     loc_180008343
0x180008246  mov     [rbp+bstrString], 0
0x18000824e  lea     r8, [rbp+bstrString]; struct ATL::CComVariant *
0x180008252  lea     rdx, [rbp+var_18]; struct IDispatchEx *
0x180008256  mov     rcx, [rbp+arg_0.lpVtbl]; this
0x18000825a  call    ?JSONStringify@ScriptHelpers@@YAJPEAUIDispatchEx@@AEAVCComVariant@ATL@@AEAVCComBSTR@4@@Z; ScriptHelpers::JSONStringify(IDispatchEx *,ATL::CComVariant &,ATL::CComBSTR &)
0x18000825f  mov     ebx, eax
0x180008261  test    eax, eax
0x180008263  jnz     short loc_1800082DD
0x180008265  mov     rcx, [r13+98h]
0x18000826c  mov     rax, [rcx]
0x18000826f  mov     rdx, [rbp+bstrString]
0x180008273  mov     rax, [rax+0A8h]
0x18000827a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000827f  mov     edi, eax
0x180008281  mov     rcx, [rbp+bstrString]; bstrString
0x180008285  call    cs:__imp_SysFreeString
0x18000828b  nop
0x18000828c  lea     rcx, [rbp+var_18]; pvarg
0x180008290  call    cs:__imp_VariantClear
0x180008296  nop
0x180008297  lea     rcx, [rbp+pvarg]; pvarg
0x18000829b  call    cs:__imp_VariantClear
0x1800082a1  nop
0x1800082a2  lea     rcx, [rbp+var_40]
0x1800082a6  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>(void)
0x1800082ab  nop
0x1800082ac  mov     rcx, [rbp+arg_0.lpVtbl]
0x1800082b0  test    rcx, rcx
0x1800082b3  jz      short loc_1800082C2
0x1800082b5  mov     rax, [rcx]
0x1800082b8  mov     rax, [rax+10h]
0x1800082bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082c1  nop
0x1800082c2  mov     rcx, [rbp+arg_10]
0x1800082c6  test    rcx, rcx
0x1800082c9  jz      short loc_1800082D8
0x1800082cb  mov     rax, [rcx]
0x1800082ce  mov     rax, [rax+10h]
0x1800082d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082d7  nop
0x1800082d8  jmp     loc_180008476
0x1800082dd  mov     eax, 80004005h
0x1800082e2  test    ebx, ebx
0x1800082e4  cmovns  ebx, eax
0x1800082e7  mov     rcx, [rbp+bstrString]; bstrString
0x1800082eb  call    cs:__imp_SysFreeString
0x1800082f1  nop
0x1800082f2  lea     rcx, [rbp+var_18]; pvarg
0x1800082f6  call    cs:__imp_VariantClear
0x1800082fc  nop
0x1800082fd  lea     rcx, [rbp+pvarg]; pvarg
0x180008301  call    cs:__imp_VariantClear
0x180008307  nop
0x180008308  lea     rcx, [rbp+var_40]
0x18000830c  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>(void)
0x180008311  nop
0x180008312  mov     rcx, [rbp+arg_0.lpVtbl]
0x180008316  test    rcx, rcx
0x180008319  jz      short loc_180008328
0x18000831b  mov     rax, [rcx]
0x18000831e  mov     rax, [rax+10h]
0x180008322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008327  nop
0x180008328  mov     rcx, [rbp+arg_10]
0x18000832c  test    rcx, rcx
0x18000832f  jz      short loc_18000833E
0x180008331  mov     rdx, [rcx]
0x180008334  mov     rax, [rdx+10h]
0x180008338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000833d  nop
0x18000833e  jmp     loc_180008443
0x180008343  mov     eax, 80004005h
0x180008348  test    ebx, ebx
0x18000834a  cmovns  ebx, eax
0x18000834d  lea     rcx, [rbp+var_18]; pvarg
0x180008351  call    cs:__imp_VariantClear
0x180008357  nop
0x180008358  lea     rcx, [rbp+pvarg]; pvarg
0x18000835c  call    cs:__imp_VariantClear
0x180008362  nop
0x180008363  lea     rcx, [rbp+var_40]
0x180008367  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>(void)
0x18000836c  nop
0x18000836d  mov     rcx, [rbp+arg_0.lpVtbl]
0x180008371  test    rcx, rcx
0x180008374  jz      short loc_180008383
0x180008376  mov     rax, [rcx]
0x180008379  mov     rax, [rax+10h]
0x18000837d  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
