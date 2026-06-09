# CRibbonCommandHandlerOnExplorerCommand::_GetUIImageFromExplorerCommandWithSize(IExplorerCommand *,IShellItemArray *,tagSIZE,GetUIImageIconSource,IUIImage * *)

- ea: `0x18006f02c`
- end: `0x18006f40e`
- name: `?_GetUIImageFromExplorerCommandWithSize@CRibbonCommandHandlerOnExplorerCommand@@IEAAJPEAUIExplorerCommand@@PEAUIShellItemArray@@UtagSIZE@@W4GetUIImageIconSource@@PEAPEAUIUIImage@@@Z`
- size: `994`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ef1c`
- `0x1801bd7f0`

## callees

- `0x18001b8d0`
- `0x18001c560`
- `0x18004062c`
- `0x18006d440`
- `0x18006f02c`
- `0x18006f414`
- `0x180070988`
- `0x1800749f0`
- `0x18008aa9c`
- `0x1800e61fc`
- `0x1800ee8b0`
- `0x1800fc17c`
- `0x1800fdcac`
- `0x180192040`
- `0x1801bdbb4`
- `0x1801be200`
- `0x1801be23c`
- `0x180210010`

## import_xrefs

- `SHELL32!Shell_GetCachedImageIndexW` at `0x18006f0d4`
- `SHELL32!Shell_GetCachedImageIndexW` at `0x18006f0d4`
- `SHELL32!__imp_SHDefExtractIconW` at `0x18006f262`
- `SHELL32!__imp_SHDefExtractIconW` at `0x18006f262`
- `SHELL32!__imp_SHCreateIconImageList` at `0x18006f15f`
- `SHELL32!__imp_SHCreateIconImageList` at `0x18006f211`
- `SHELL32!__imp_SHCreateIconImageList` at `0x18006f15f`
- `SHELL32!__imp_SHCreateIconImageList` at `0x18006f211`
- `SHLWAPI!PathParseIconLocationW` at `0x18006f098`
- `SHLWAPI!PathParseIconLocationW` at `0x18006f098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f074`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f3ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f074`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f3ee`
- `USER32!GetDpiForWindow` at `0x18006f0f4`
- `USER32!GetDpiForWindow` at `0x18006f1c4`
- `USER32!GetDpiForWindow` at `0x18006f0f4`
- `USER32!GetDpiForWindow` at `0x18006f1c4`
- `USER32!GetSystemMetricsForDpi` at `0x18006f101`
- `USER32!GetSystemMetricsForDpi` at `0x18006f1d1`
- `USER32!GetSystemMetricsForDpi` at `0x18006f101`
- `USER32!GetSystemMetricsForDpi` at `0x18006f1d1`
- `GDI32!DeleteObject` at `0x18006f2fd`
- `GDI32!DeleteObject` at `0x18006f3d7`
- `GDI32!DeleteObject` at `0x18006f2fd`
- `GDI32!DeleteObject` at `0x18006f3d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 CRibbonCommandHandlerOnExplorerCommand::_GetUIImageFromExplorerCommandWithSize(
        HIMAGELIST *a1,
        struct IExplorerCommand *a2,
        struct IShellItemArray *a3,
        ...)
{
  struct tagSIZE v3; // rdi
  _QWORD *v7; // r15
  HRESULT (__stdcall *GetIcon)(IExplorerCommand *, IShellItemArray *, LPWSTR *); // rbx
  int v9; // eax
  const WCHAR *v10; // rcx
  bool v11; // al
  bool v12; // zf
  UINT v13; // r15d
  int CachedImageIndexW; // r13d
  HWND Window; // rbx
  unsigned int DpiForWindow; // eax
  LONG SystemMetricsForDpi; // eax
  unsigned int v18; // r14d
  HIMAGELIST *v19; // rbx
  __int64 v20; // rax
  HICON Icon; // rbx
  unsigned int v22; // eax
  unsigned int v23; // r14d
  __int64 v24; // rax
  HRESULT v25; // eax
  int BitmapFromIconWithAlpha; // ebx
  HGDIOBJ v27; // rdi
  HICON phiconLarge; // [rsp+30h] [rbp-20h] BYREF
  HGDIOBJ v30; // [rsp+38h] [rbp-18h] BYREF
  LPWSTR pszIconFile; // [rsp+40h] [rbp-10h] BYREF
  HGDIOBJ ho; // [rsp+48h] [rbp-8h] BYREF
  int iIndex; // [rsp+98h] [rbp+48h] BYREF
  struct IShellItemArray *v34; // [rsp+A0h] [rbp+50h]
  struct tagSIZE v35; // [rsp+A8h] [rbp+58h] BYREF
  va_list va; // [rsp+A8h] [rbp+58h]
  __int64 v37; // [rsp+B0h] [rbp+60h]
  LPVOID v38; // [rsp+B8h] [rbp+68h] BYREF
  va_list va1; // [rsp+B8h] [rbp+68h]
  va_list va2; // [rsp+C0h] [rbp+70h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v35 = va_arg(va1, struct tagSIZE);
  v37 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v38 = va_arg(va2, LPVOID);
  v34 = a3;
  v3 = v35;
  v7 = v38;
  *(_QWORD *)v38 = 0;
  v30 = 0;
  pszIconFile = 0;
  GetIcon = a2->lpVtbl->GetIcon;
  CoTaskMemFree(0);
  if ( ((int (__fastcall *)(struct IExplorerCommand *, struct IShellItemArray *, LPWSTR *))GetIcon)(
         a2,
         a3,
         &pszIconFile) >= 0 )
  {
    v9 = PathParseIconLocationW(pszIconFile);
    iIndex = v9;
    v10 = pszIconFile;
    if ( pszIconFile
      && (*pszIconFile == 64
       || (v11 = IsSupportedImageFormatForExtractingIcons(pszIconFile), v10 = pszIconFile, v12 = !v11, v9 = iIndex, !v12)) )
    {
      v13 = 40;
    }
    else
    {
      v13 = 0;
    }
    phiconLarge = 0;
    CachedImageIndexW = Shell_GetCachedImageIndexW(v10, v9, v13);
    if ( CachedImageIndexW == -1 )
      goto LABEL_25;
    Window = CRibbonCommandHandlerOnExplorerCommand::_GetWindow((CRibbonCommandHandlerOnExplorerCommand *)a1);
    DpiForWindow = GetDpiForWindow(Window);
    SystemMetricsForDpi = GetSystemMetricsForDpi(49, DpiForWindow);
    v18 = SystemMetricsForDpi;
    if ( (_DWORD)v37 == 2 )
    {
      if ( v3.cx <= SystemMetricsForDpi && v35.cy <= SystemMetricsForDpi )
        goto LABEL_11;
    }
    else if ( (_DWORD)v37 )
    {
LABEL_11:
      v19 = a1 + 12;
      if ( SystemMetricsForDpi == *((_DWORD *)a1 + 28) )
        goto LABEL_17;
      if ( *v19 )
      {
        wil::details::unique_storage<wil::details::resource_policy<_IMAGELIST *,int (*)(_IMAGELIST *),&int ImageList_Destroy(_IMAGELIST *),wistd::integral_constant<unsigned __int64,0>,_IMAGELIST *,_IMAGELIST *,0,std::nullptr_t>>::reset(
          a1 + 12,
          0);
        *((_DWORD *)a1 + 28) = 0;
      }
      ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&ho);
      if ( (int)SHCreateIconImageList(v18, &GUID_46eb5926_582e_4017_9fdf_e8998daa0950, &ho) >= 0 )
      {
        v20 = ATL::CComPtrBase<IImageList>::Detach(&ho);
        wil::details::unique_storage<wil::details::resource_policy<_IMAGELIST *,int (*)(_IMAGELIST *),&int ImageList_Destroy(_IMAGELIST *),wistd::integral_constant<unsigned __int64,0>,_IMAGELIST *,_IMAGELIST *,0,std::nullptr_t>>::reset(
          a1 + 12,
          v20);
        *((_DWORD *)a1 + 28) = v18;
      }
      goto LABEL_16;
    }
    v22 = GetDpiForWindow(Window);
    v23 = GetSystemMetricsForDpi(11, v22);
    v19 = a1 + 13;
    if ( v23 == *((_DWORD *)a1 + 29) )
    {
LABEL_17:
      if ( *v19 )
      {
        Icon = ImageList_GetIcon(*v19, CachedImageIndexW, 1u);
        CTSmartObj<HICON__ *,CAutoHandle_Policy<HICON__ *>>::Release(&phiconLarge);
        phiconLarge = Icon;
        goto LABEL_26;
      }
LABEL_25:
      Icon = phiconLarge;
LABEL_26:
      if ( !Icon )
      {
        v25 = SHDefExtractIconW(pszIconFile, iIndex, v13, &phiconLarge, 0, LOWORD(v3.cx));
        BitmapFromIconWithAlpha = v25;
        if ( v25 == 1 )
        {
          BitmapFromIconWithAlpha = -2147467263;
LABEL_37:
          CTSmartObj<HICON__ *,CAutoHandle_Policy<HICON__ *>>::Release(&phiconLarge);
          v7 = v38;
          goto LABEL_42;
        }
        if ( v25 < 0 )
          goto LABEL_37;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53343352>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53343352>::GetImpl'::`2'::impl)
        || (iIndex = 0, (int)GetBackgroundColorFromExplorerCommand(a2, v34, (unsigned int *)&iIndex) < 0) )
      {
        BitmapFromIconWithAlpha = CreateBitmapFromIconWithAlpha(phiconLarge, v3.cx, (HBITMAP *)&v30);
      }
      else
      {
        ho = 0;
        BitmapFromIconWithAlpha = CreateBitmapFromIcon(phiconLarge, (__int64)&ho);
        v27 = ho;
        if ( BitmapFromIconWithAlpha >= 0 )
          BitmapFromIconWithAlpha = GDIHelpers::AddBackgroundForIcon(
                                      ho,
                                      (HBITMAP)&iIndex,
                                      (const unsigned int *)va,
                                      (const struct tagSIZE *)va,
                                      (const struct tagSIZE *)va,
                                      (const struct tagSIZE *)&v30,
                                      (HBITMAP *)phiconLarge);
        if ( v27 )
          DeleteObject(v27);
      }
      goto LABEL_37;
    }
    if ( *v19 )
    {
      wil::details::unique_storage<wil::details::resource_policy<_IMAGELIST *,int (*)(_IMAGELIST *),&int ImageList_Destroy(_IMAGELIST *),wistd::integral_constant<unsigned __int64,0>,_IMAGELIST *,_IMAGELIST *,0,std::nullptr_t>>::reset(
        a1 + 13,
        0);
      *((_DWORD *)a1 + 29) = 0;
    }
    ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&ho);
    if ( (int)SHCreateIconImageList(v23, &GUID_46eb5926_582e_4017_9fdf_e8998daa0950, &ho) >= 0 )
    {
      v24 = ATL::CComPtrBase<IImageList>::Detach(&ho);
      wil::details::unique_storage<wil::details::resource_policy<_IMAGELIST *,int (*)(_IMAGELIST *),&int ImageList_Destroy(_IMAGELIST *),wistd::integral_constant<unsigned __int64,0>,_IMAGELIST *,_IMAGELIST *,0,std::nullptr_t>>::reset(
        a1 + 13,
        v24);
      *((_DWORD *)a1 + 29) = v23;
    }
LABEL_16:
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&ho);
    goto LABEL_17;
  }
  ATL::CComQIPtr<IExplorerCommand2,&__s_GUID const _GUID_d51836b4_8b5a_4e11_8f97_d489bd4b28c0>::CComQIPtr<IExplorerCommand2,&__s_GUID const _GUID_d51836b4_8b5a_4e11_8f97_d489bd4b28c0>(
    (LPVOID *)va1,
    a2);
  if ( !v38
    || (BitmapFromIconWithAlpha = (*(__int64 (__fastcall **)(LPVOID, struct IShellItemArray *, struct tagSIZE, HGDIOBJ *))(*(_QWORD *)v38 + 104LL))(
                                    v38,
                                    a3,
                                    v3,
                                    &v30),
        BitmapFromIconWithAlpha < 0) )
  {
    BitmapFromIconWithAlpha = CRibbonCommandHandlerOnExplorerCommand::_CreateDefaultBitmap(
                                (CRibbonCommandHandlerOnExplorerCommand *)a1,
                                a2,
                                a3,
                                (const struct tagSIZE *)va,
                                (HBITMAP *)&v30);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(va1);
LABEL_42:
  if ( BitmapFromIconWithAlpha >= 0 )
  {
    ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(va1);
    BitmapFromIconWithAlpha = IECreateInstance(&CLSID_UIRibbonImageFromBitmapFactory, (LPVOID *)va1);
    if ( BitmapFromIconWithAlpha < 0
      || (BitmapFromIconWithAlpha = (*(__int64 (__fastcall **)(LPVOID, HGDIOBJ, _QWORD, _QWORD *))(*(_QWORD *)v38 + 24LL))(
                                      v38,
                                      v30,
                                      0,
                                      v7),
          BitmapFromIconWithAlpha < 0) )
    {
      DeleteObject(v30);
      *v7 = 0;
    }
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(va1);
  }
  CoTaskMemFree(pszIconFile);
  return (unsigned int)BitmapFromIconWithAlpha;
}

```

## disassembly

```asm
0x18006f02c  mov     [rsp-38h+arg_0], rbx
0x18006f031  mov     qword ptr [rsp-38h+arg_18.cx], r9
0x18006f036  mov     [rsp-38h+arg_10], r8
0x18006f03b  push    rbp
0x18006f03c  push    rsi
0x18006f03d  push    rdi
0x18006f03e  push    r12
0x18006f040  push    r13
0x18006f042  push    r14
0x18006f044  push    r15
0x18006f046  mov     rbp, rsp
0x18006f049  sub     rsp, 50h
0x18006f04d  mov     rdi, r9
0x18006f050  mov     r14, r8
0x18006f053  mov     r12, rdx
0x18006f056  mov     rsi, rcx
0x18006f059  xor     r13d, r13d
0x18006f05c  mov     r15, [rbp+arg_28]
0x18006f060  mov     [r15], r13
0x18006f063  mov     [rbp+var_18], r13
0x18006f067  mov     [rbp+pszIconFile], r13
0x18006f06b  mov     rax, [rdx]
0x18006f06e  mov     rbx, [rax+20h]
0x18006f072  xor     ecx, ecx; pv
0x18006f074  call    cs:__imp_CoTaskMemFree
0x18006f07a  lea     r8, [rbp+pszIconFile]
0x18006f07e  mov     rdx, r14
0x18006f081  mov     rcx, r12
0x18006f084  mov     rax, rbx
0x18006f087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f08c  test    eax, eax
0x18006f08e  js      loc_18006F325
0x18006f094  mov     rcx, [rbp+pszIconFile]; pszIconFile
0x18006f098  call    cs:__imp_PathParseIconLocationW
0x18006f09e  mov     [rbp+iIndex], eax
0x18006f0a1  mov     rcx, [rbp+pszIconFile]; unsigned __int16 *
0x18006f0a5  test    rcx, rcx
0x18006f0a8  jz      short loc_18006F0C8
0x18006f0aa  cmp     word ptr [rcx], 40h ; '@'
0x18006f0ae  jz      short loc_18006F0C0
0x18006f0b0  call    ?IsSupportedImageFormatForExtractingIcons@@YA_NPEBG@Z; IsSupportedImageFormatForExtractingIcons(ushort const *)
0x18006f0b5  mov     rcx, [rbp+pszIconFile]
0x18006f0b9  test    al, al
0x18006f0bb  mov     eax, [rbp+iIndex]
0x18006f0be  jz      short loc_18006F0C8
0x18006f0c0  mov     r15d, 28h ; '('
0x18006f0c6  jmp     short loc_18006F0CB
0x18006f0c8  mov     r15d, r13d
0x18006f0cb  mov     [rbp+phiconLarge], r13
0x18006f0cf  mov     r8d, r15d; uIconFlags
0x18006f0d2  mov     edx, eax; iIconIndex
0x18006f0d4  call    cs:__imp_Shell_GetCachedImageIndexW
0x18006f0da  mov     r13d, eax
0x18006f0dd  cmp     eax, 0FFFFFFFFh
0x18006f0e0  jz      loc_18006F23C
0x18006f0e6  mov     rcx, rsi; this
0x18006f0e9  call    ?_GetWindow@CRibbonCommandHandlerOnExplorerCommand@@IEAAPEAUHWND__@@XZ; CRibbonCommandHandlerOnExplorerCommand::_GetWindow(void)
0x18006f0ee  mov     rbx, rax
0x18006f0f1  mov     rcx, rax
0x18006f0f4  call    cs:__imp_GetDpiForWindow
0x18006f0fa  mov     edx, eax
0x18006f0fc  mov     ecx, 31h ; '1'
0x18006f101  call    cs:__imp_GetSystemMetricsForDpi
0x18006f107  mov     r14d, eax
0x18006f10a  mov     ecx, dword ptr [rbp+arg_20]
0x18006f10d  cmp     ecx, 2
0x18006f110  jnz     loc_18006F1B9
0x18006f116  cmp     edi, eax
0x18006f118  jg      loc_18006F1C1
0x18006f11e  cmp     [rbp+arg_18.cy], eax
0x18006f121  jg      loc_18006F1C1
0x18006f127  lea     rbx, [rsi+60h]
0x18006f12b  cmp     r14d, [rsi+70h]
0x18006f12f  jz      short loc_18006F18A
0x18006f131  cmp     qword ptr [rbx], 0
0x18006f135  jz      short loc_18006F148
0x18006f137  xor     edx, edx
0x18006f139  mov     rcx, rbx
0x18006f13c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_IMAGELIST@@P6AHPEAU1@@Z$1?ImageList_Destroy@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_IMAGELIST@@@Z; wil::details::unique_storage<wil::details::resource_policy<_IMAGELIST *,int (*)(_IMAGELIST *),&ImageList_Destroy(_IMAGELIST *),wistd::integral_constant<unsigned __int64,0>,_IMAGELIST *,_IMAGELIST *,0,std::nullptr_t>>::reset(_IMAGELIST *)
0x18006f141  mov     dword ptr [rsi+70h], 0
0x18006f148  lea     rcx, [rbp+ho]; void *
0x18006f14c  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x18006f151  lea     r8, [rbp+ho]
0x18006f155  lea     rdx, _GUID_46eb5926_582e_4017_9fdf_e8998daa0950
0x18006f15c  mov     ecx, r14d
0x18006f15f  call    cs:__imp_SHCreateIconImageList
0x18006f165  test    eax, eax
0x18006f167  js      short loc_18006F181
0x18006f169  lea     rcx, [rbp+ho]
0x18006f16d  call    ?Detach@?$CComPtrBase@UIImageList@@@ATL@@QEAAPEAUIImageList@@XZ; ATL::CComPtrBase<IImageList>::Detach(void)
0x18006f172  mov     rdx, rax
0x18006f175  mov     rcx, rbx
0x18006f178  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_IMAGELIST@@P6AHPEAU1@@Z$1?ImageList_Destroy@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_IMAGELIST@@@Z; wil::details::unique_storage<wil::details::resource_policy<_IMAGELIST *,int (*)(_IMAGELIST *),&ImageList_Destroy(_IMAGELIST *),wistd::integral_constant<unsigned __int64,0>,_IMAGELIST *,_IMAGELIST *,0,std::nullptr_t>>::reset(_IMAGELIST *)
0x18006f17d  mov     [rsi+70h], r14d
0x18006f181  lea     rcx, [rbp+ho]; void *
0x18006f185  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18006f18a  mov     rcx, [rbx]; himl
0x18006f18d  test    rcx, rcx
0x18006f190  jz      loc_18006F23C
0x18006f196  mov     r8d, 1; flags
0x18006f19c  mov     edx, r13d; i
0x18006f19f  call    ImageList_GetIcon
0x18006f1a4  mov     rbx, rax
0x18006f1a7  lea     rcx, [rbp+phiconLarge]
0x18006f1ab  call    ?Release@?$CTSmartObj@PEAUHICON__@@V?$CAutoHandle_Policy@PEAUHICON__@@@@@@QEAAXXZ; CTSmartObj<HICON__ *,CAutoHandle_Policy<HICON__ *>>::Release(void)
0x18006f1b0  mov     [rbp+phiconLarge], rbx
0x18006f1b4  jmp     loc_18006F240
0x18006f1b9  test    ecx, ecx
0x18006f1bb  jnz     loc_18006F127
0x18006f1c1  mov     rcx, rbx
0x18006f1c4  call    cs:__imp_GetDpiForWindow
0x18006f1ca  mov     edx, eax
0x18006f1cc  mov     ecx, 0Bh
0x18006f1d1  call    cs:__imp_GetSystemMetricsForDpi
0x18006f1d7  mov     r14d, eax
0x18006f1da  lea     rbx, [rsi+68h]
0x18006f1de  cmp     eax, [rsi+74h]
0x18006f1e1  jz      short loc_18006F18A
0x18006f1e3  cmp     qword ptr [rbx], 0
0x18006f1e7  jz      short loc_18006F1FA
0x18006f1e9  xor     edx, edx
0x18006f1eb  mov     rcx, rbx
0x18006f1ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_IMAGELIST@@P6AHPEAU1@@Z$1?ImageList_Destroy@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_IMAGELIST@@@Z; wil::details::unique_storage<wil::details::resource_policy<_IMAGELIST *,int (*)(_IMAGELIST *),&ImageList_Destroy(_IMAGELIST *),wistd::integral_constant<unsigned __int64,0>,_IMAGELIST *,_IMAGELIST *,0,std::nullptr_t>>::reset(_IMAGELIST *)
0x18006f1f3  mov     dword ptr [rsi+74h], 0
0x18006f1fa  lea     rcx, [rbp+ho]; void *
0x18006f1fe  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x18006f203  lea     r8, [rbp+ho]
0x18006f207  lea     rdx, _GUID_46eb5926_582e_4017_9fdf_e8998daa0950
0x18006f20e  mov     ecx, r14d
0x18006f211  call    cs:__imp_SHCreateIconImageList
0x18006f217  test    eax, eax
0x18006f219  js      loc_18006F181
0x18006f21f  lea     rcx, [rbp+ho]
0x18006f223  call    ?Detach@?$CComPtrBase@UIImageList@@@ATL@@QEAAPEAUIImageList@@XZ; ATL::CComPtrBase<IImageList>::Detach(void)
0x18006f228  mov     rdx, rax
0x18006f22b  mov     rcx, rbx
0x18006f22e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_IMAGELIST@@P6AHPEAU1@@Z$1?ImageList_Destroy@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_IMAGELIST@@@Z; wil::details::unique_storage<wil::details::resource_policy<_IMAGELIST *,int (*)(_IMAGELIST *),&ImageList_Destroy(_IMAGELIST *),wistd::integral_constant<unsigned __int64,0>,_IMAGELIST *,_IMAGELIST *,0,std::nullptr_t>>::reset(_IMAGELIST *)
0x18006f233  mov     [rsi+74h], r14d
0x18006f237  jmp     loc_18006F181
0x18006f23c  mov     rbx, [rbp+phiconLarge]
0x18006f240  xor     r13d, r13d
0x18006f243  test    rbx, rbx
0x18006f246  jnz     short loc_18006F281
0x18006f248  movzx   eax, di
0x18006f24b  mov     [rsp+50h+nIconSize], eax; nIconSize
0x18006f24f  mov     [rsp+50h+phiconSmall], r13; phiconSmall
0x18006f254  lea     r9, [rbp+phiconLarge]; phiconLarge
0x18006f258  mov     r8d, r15d; uFlags
0x18006f25b  mov     edx, [rbp+iIndex]; iIndex
0x18006f25e  mov     rcx, [rbp+pszIconFile]; pszIconFile
0x18006f262  call    cs:__imp_SHDefExtractIconW
0x18006f268  mov     ebx, eax
0x18006f26a  cmp     eax, 1
0x18006f26d  jnz     short loc_18006F279
0x18006f26f  mov     ebx, 80004001h
0x18006f274  jmp     loc_18006F316
0x18006f279  test    eax, eax
0x18006f27b  js      loc_18006F316
0x18006f281  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53343352@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53343352@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53343352> `wil::Feature<__WilFeatureTraits_Feature_53343352>::GetImpl(void)'::`2'::impl
0x18006f288  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53343352@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53343352>::__private_IsEnabled(void)
0x18006f28d  test    al, al
0x18006f28f  jnz     short loc_18006F305
0x18006f291  mov     [rbp+iIndex], r13d
0x18006f295  lea     r8, [rbp+iIndex]; unsigned int *
0x18006f299  mov     rdx, [rbp+arg_10]; struct IShellItemArray *
0x18006f29d  mov     rcx, r12; struct IExplorerCommand *
0x18006f2a0  call    ?GetBackgroundColorFromExplorerCommand@@YAJPEAUIExplorerCommand@@PEAUIShellItemArray@@PEAK@Z; GetBackgroundColorFromExplorerCommand(IExplorerCommand *,IShellItemArray *,ulong *)
0x18006f2a5  test    eax, eax
0x18006f2a7  js      short loc_18006F305
0x18006f2a9  mov     [rbp+ho], r13
0x18006f2ad  lea     rax, [rbp+ho]
0x18006f2b1  mov     [rsp+50h+phiconSmall], rax; __int64
0x18006f2b6  lea     r9, [rbp+arg_18]
0x18006f2ba  mov     rcx, [rbp+phiconLarge]; hicon
0x18006f2be  call    CreateBitmapFromIcon
0x18006f2c3  mov     ebx, eax
0x18006f2c5  mov     rdi, [rbp+ho]
0x18006f2c9  test    eax, eax
0x18006f2cb  js      short loc_18006F2F5
0x18006f2cd  lea     rax, [rbp+var_18]
0x18006f2d1  mov     qword ptr [rsp+50h+nIconSize], rax; struct tagSIZE *
0x18006f2d6  lea     rax, [rbp+arg_18]
0x18006f2da  mov     [rsp+50h+phiconSmall], rax; struct tagSIZE *
0x18006f2df  lea     r9, [rbp+arg_18]; struct tagSIZE *
0x18006f2e3  lea     r8, [rbp+arg_18]; unsigned int *
0x18006f2e7  lea     rdx, [rbp+iIndex]; HBITMAP
0x18006f2eb  mov     rcx, rdi; h
0x18006f2ee  call    ?AddBackgroundForIcon@GDIHelpers@@YAJPEAUHBITMAP__@@AEBKAEBUtagSIZE@@22PEAPEAU2@@Z; GDIHelpers::AddBackgroundForIcon(HBITMAP__ *,ulong const &,tagSIZE const &,tagSIZE const &,tagSIZE const &,HBITMAP__ * *)
0x18006f2f3  mov     ebx, eax
0x18006f2f5  test    rdi, rdi
0x18006f2f8  jz      short loc_18006F316
0x18006f2fa  mov     rcx, rdi; ho
0x18006f2fd  call    cs:__imp_DeleteObject
0x18006f303  jmp     short loc_18006F316
0x18006f305  lea     r8, [rbp+var_18]; HBITMAP *
0x18006f309  mov     edx, edi; unsigned int
0x18006f30b  mov     rcx, [rbp+phiconLarge]; hicon
0x18006f30f  call    ?CreateBitmapFromIconWithAlpha@@YAJPEAUHICON__@@HPEAPEAUHBITMAP__@@@Z; CreateBitmapFromIconWithAlpha(HICON__ *,int,HBITMAP__ * *)
0x18006f314  mov     ebx, eax
0x18006f316  lea     rcx, [rbp+phiconLarge]
0x18006f31a  call    ?Release@?$CTSmartObj@PEAUHICON__@@V?$CAutoHandle_Policy@PEAUHICON__@@@@@@QEAAXXZ; CTSmartObj<HICON__ *,CAutoHandle_Policy<HICON__ *>>::Release(void)
0x18006f31f  mov     r15, [rbp+arg_28]
0x18006f323  jmp     short loc_18006F37D
0x18006f325  mov     rdx, r12
0x18006f328  lea     rcx, [rbp+arg_28]
0x18006f32c  call    ??0?$CComQIPtr@UIExplorerCommand2@@$1?_GUID_d51836b4_8b5a_4e11_8f97_d489bd4b28c0@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IExplorerCommand2,&__s_GUID const _GUID_d51836b4_8b5a_4e11_8f97_d489bd4b28c0>::CComQIPtr<IExplorerCommand2,&__s_GUID const _GUID_d51836b4_8b5a_4e11_8f97_d489bd4b28c0>(IUnknown *)
0x18006f331  nop
0x18006f332  mov     rcx, [rbp+arg_28]
0x18006f336  test    rcx, rcx
0x18006f339  jz      short loc_18006F357
0x18006f33b  mov     rax, [rcx]
0x18006f33e  lea     r9, [rbp+var_18]
0x18006f342  mov     r8, rdi
0x18006f345  mov     rdx, r14
0x18006f348  mov     rax, [rax+68h]
0x18006f34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f351  mov     ebx, eax
0x18006f353  test    eax, eax
0x18006f355  jns     short loc_18006F374
0x18006f357  lea     rax, [rbp+var_18]
0x18006f35b  mov     [rsp+50h+phiconSmall], rax; HBITMAP *
0x18006f360  lea     r9, [rbp+arg_18]; struct tagSIZE *
0x18006f364  mov     r8, r14; struct IShellItemArray *
0x18006f367  mov     rdx, r12; struct IExplorerCommand *
0x18006f36a  mov     rcx, rsi; this
0x18006f36d  call    ?_CreateDefaultBitmap@CRibbonCommandHandlerOnExplorerCommand@@IEAAJPEAUIExplorerCommand@@PEAUIShellItemArray@@AEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z; CRibbonCommandHandlerOnExplorerCommand::_CreateDefaultBitmap(IExplorerCommand *,IShellItemArray *,tagSIZE const &,HBITMAP__ * *)
0x18006f372  mov     ebx, eax
0x18006f374  lea     rcx, [rbp+arg_28]; void *
0x18006f378  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18006f37d  test    ebx, ebx
0x18006f37f  js      short loc_18006F3EA
0x18006f381  lea     rcx, [rbp+arg_28]; void *
0x18006f385  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x18006f38a  nop
0x18006f38b  lea     rax, [rbp+arg_28]
0x18006f38f  mov     [rsp+50h+phiconSmall], rax; LPVOID *
0x18006f394  lea     r9, _GUID_18aba7f3_4c1c_4ba2_bf6c_f5c3326fa816
0x18006f39b  mov     r8d, 1
0x18006f3a1  lea     rcx, CLSID_UIRibbonImageFromBitmapFactory; rclsid
0x18006f3a8  call    IECreateInstance
0x18006f3ad  mov     ebx, eax
0x18006f3af  test    eax, eax
0x18006f3b1  js      short loc_18006F3D3
0x18006f3b3  mov     rcx, [rbp+arg_28]
0x18006f3b7  mov     rax, [rcx]
0x18006f3ba  mov     r9, r15
0x18006f3bd  xor     r8d, r8d
0x18006f3c0  mov     rdx, [rbp+var_18]
0x18006f3c4  mov     rax, [rax+18h]
0x18006f3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f3cd  mov     ebx, eax
0x18006f3cf  test    eax, eax
0x18006f3d1  jns     short loc_18006F3E0
0x18006f3d3  mov     rcx, [rbp+var_18]; ho
0x18006f3d7  call    cs:__imp_DeleteObject
0x18006f3dd  mov     [r15], r13
0x18006f3e0  lea     rcx, [rbp+arg_28]; void *
0x18006f3e4  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18006f3e9  nop
0x18006f3ea  mov     rcx, [rbp+pszIconFile]; pv
0x18006f3ee  call    cs:__imp_CoTaskMemFree
0x18006f3f4  mov     eax, ebx
0x18006f3f6  mov     rbx, [rsp+50h+arg_0]
0x18006f3fe  add     rsp, 50h
0x18006f402  pop     r15
0x18006f404  pop     r14
0x18006f406  pop     r13
0x18006f408  pop     r12
0x18006f40a  pop     rdi
0x18006f40b  pop     rsi
0x18006f40c  pop     rbp
0x18006f40d  retn
```
