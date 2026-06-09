# Wallet::WalletItem::SaveImageFile(__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT const *,int)

- ea: `0x1800283c4`
- end: `0x180028712`
- name: `?SaveImageFile@WalletItem@Wallet@@AEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBUtagPROPVARIANT@@H@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800265ec`
- `0x180027578`
- `0x180028ba0`

## callees

- `0x180008cc0`
- `0x18000d8d8`
- `0x180013f78`
- `0x18001d438`
- `0x180025ad4`
- `0x180025c4c`
- `0x180026090`
- `0x180027434`
- `0x1800283c4`
- `0x180036948`
- `0x1800398f8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180028506`
- `OLEAUT32!__imp_SysAllocString` at `0x18002857f`
- `OLEAUT32!__imp_SysAllocString` at `0x180028506`
- `OLEAUT32!__imp_SysAllocString` at `0x18002857f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800286bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800286bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002840c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002840c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028421`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002842b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002842b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286da`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002864e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800286d0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002864e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800286d0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180028459`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180028459`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002867a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002867a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180028513`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180028513`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18002869d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18002869d`
- `dsclient!DSCopyFromSharedFile` at `0x1800285a8`
- `dsclient!DSCopyFromSharedFile` at `0x1800285a8`
- `dsclient!DSGetSharedFileName` at `0x1800284e6`
- `dsclient!DSGetSharedFileName` at `0x1800284e6`
- `dsclient!DSFreeString` at `0x180028695`
- `dsclient!DSFreeString` at `0x180028695`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028605`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028610`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028662`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800286ed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028605`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028610`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028662`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800286ed`

## string_xrefs

- `0x180028563`: `[Wallet, SaveImageFile] Attempting to save %S as %S`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItem::SaveImageFile(__int64 a1, unsigned int a2, __int64 a3, int a4)
{
  char v8; // r12
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int WalletPhotosPath; // edi
  __int64 v12; // rcx
  const OLECHAR *v13; // rbx
  const unsigned __int16 *v14; // rdx
  const WCHAR *v15; // rax
  LPWSTR ExtensionW; // rax
  __int64 v17; // rcx
  __int16 v18; // cx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // ebx
  LPCWSTR pszPath; // [rsp+40h] [rbp-69h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-61h] BYREF
  __int64 v25; // [rsp+58h] [rbp-51h]
  void *TokenHandle; // [rsp+60h] [rbp-49h] BYREF
  Wallet::FileUtils *v27[4]; // [rsp+68h] [rbp-41h] BYREF
  PROPVARIANT v28[2]; // [rsp+88h] [rbp-21h] BYREF
  __int64 v29; // [rsp+98h] [rbp-11h]
  OLECHAR *psz[12]; // [rsp+A0h] [rbp-9h] BYREF

  pszPath = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(psz);
  TokenHandle = 0;
  v29 = 0;
  v8 = 0;
  *(_OWORD *)v28 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    WalletPhotosPath = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        WalletPhotosPath = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      WalletPhotosPath = -2143748092;
    }
    goto LABEL_42;
  }
  if ( !ImpersonateLoggedOnUser(TokenHandle) )
  {
    WalletPhotosPath = -2147418113;
    goto LABEL_42;
  }
  if ( !*(_WORD *)a3 )
    goto LABEL_35;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v27);
  if ( *(_WORD *)a3 != 8 )
    __fastfail(5u);
  if ( a2 - 200 > 8 )
    goto LABEL_12;
  if ( *(_WORD *)a3 != 8 )
  {
    WalletPhotosPath = -2147024809;
    goto LABEL_13;
  }
  v13 = *(const OLECHAR **)(a3 + 8);
  WalletPhotosPath = Wallet::ServerUtils::GetWalletPhotosPath(v27);
  if ( WalletPhotosPath < 0 )
    goto LABEL_13;
  WalletPhotosPath = Wallet::FileUtils::RecursiveCreateDirectory(v27[0], v14);
  if ( WalletPhotosPath < 0 )
    goto LABEL_13;
  if ( !a4 )
  {
    v15 = SysAllocString(v13);
    pszPath = v15;
    goto LABEL_23;
  }
  WalletPhotosPath = DSGetSharedFileName(v13, &pszPath);
  if ( WalletPhotosPath >= 0 )
  {
    v15 = pszPath;
LABEL_23:
    ExtensionW = PathFindExtensionW(v15);
    if ( !*ExtensionW )
    {
LABEL_12:
      WalletPhotosPath = -2147024809;
LABEL_13:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v27);
      goto LABEL_42;
    }
    WalletPhotosPath = Wallet::WalletItem::GetUniqueImagePath(v17, psz, ExtensionW, 0);
    if ( WalletPhotosPath < 0 )
      goto LABEL_13;
    wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(
      5,
      "Wallet::WalletItem::SaveImageFile",
      895,
      a1,
      "[Wallet, SaveImageFile] Attempting to save %S as %S",
      pszPath,
      psz[0]);
    LOWORD(v28[0]) = v18 + 3;
    v28[1] = SysAllocString(psz[0]);
    if ( !v28[1] )
    {
      WalletPhotosPath = -2147024882;
      goto LABEL_13;
    }
    if ( a4 )
    {
      WalletPhotosPath = DSCopyFromSharedFile(v13, psz[0]);
      if ( WalletPhotosPath < 0 )
        goto LABEL_20;
      if ( (unsigned int)Wallet::Utils::IsStandardItemType(*(unsigned int *)(a1 + 168)) && a2 == 204 )
      {
        v25 = 0;
        *(_OWORD *)pvar = 0;
        LODWORD(pvar[1]) = 0;
        LOWORD(pvar[0]) = 22;
        WalletPhotosPath = Wallet::WalletItem::TSetPropertyValue<utl::unordered_map<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                             v19,
                             a1 + 88,
                             155,
                             pvar);
        if ( WalletPhotosPath < 0 )
        {
          PropVariantClear(pvar);
          goto LABEL_20;
        }
        PropVariantClear(pvar);
      }
    }
    else if ( !MoveFileW(v13, psz[0]) )
    {
      WalletPhotosPath = -2147418113;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v27);
      goto LABEL_46;
    }
    v8 = 1;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v27);
LABEL_35:
    v25 = 0;
    *(_OWORD *)pvar = 0;
    if ( (int)Wallet::WalletItem::TGetPropertyValue<utl::unordered_map<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                v12,
                a1 + 88,
                a2,
                pvar) >= 0
      && LOWORD(pvar[0])
      && !DeleteFileW((LPCWSTR)pvar[1]) )
    {
      GetLastError();
    }
    PropVariantClear(pvar);
    v21 = Wallet::WalletItem::TSetPropertyValue<utl::unordered_map<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
            v20,
            a1 + 88,
            a2,
            v28);
    if ( !RevertToSelf() )
      v21 = -2147418113;
    WalletPhotosPath = v21;
LABEL_42:
    if ( a4 )
      goto LABEL_43;
LABEL_46:
    SysFreeString((BSTR)pszPath);
    goto LABEL_47;
  }
LABEL_20:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v27);
LABEL_43:
  DSFreeString(pszPath);
LABEL_47:
  if ( WalletPhotosPath < 0 && v8 && !DeleteFileW(psz[0]) )
    GetLastError();
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  PropVariantClear(v28);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(psz);
  return (unsigned int)WalletPhotosPath;
}

```

## disassembly

```asm
0x1800283c4  push    rbp
0x1800283c6  push    rbx
0x1800283c7  push    rsi
0x1800283c8  push    rdi
0x1800283c9  push    r12
0x1800283cb  push    r13
0x1800283cd  push    r14
0x1800283cf  push    r15
0x1800283d1  lea     rbp, [rsp-1Fh]
0x1800283d6  sub     rsp, 0C8h
0x1800283dd  mov     r14, rcx
0x1800283e0  xor     r13d, r13d
0x1800283e3  lea     rcx, [rbp+57h+psz]
0x1800283e7  mov     [rbp+57h+pszPath], r13
0x1800283eb  mov     r15d, r9d
0x1800283ee  mov     rbx, r8
0x1800283f1  mov     esi, edx
0x1800283f3  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800283f8  xor     eax, eax
0x1800283fa  mov     [rbp+57h+TokenHandle], r13
0x1800283fe  xorps   xmm0, xmm0
0x180028401  mov     [rbp+57h+var_68], rax
0x180028405  mov     r12b, r13b
0x180028408  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18002840c  call    cs:__imp_GetCurrentThread
0x180028412  mov     rcx, rax; ThreadHandle
0x180028415  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180028419  lea     edx, [r13+0Ch]; DesiredAccess
0x18002841d  lea     r8d, [r13+1]; OpenAsSelf
0x180028421  call    cs:__imp_OpenThreadToken
0x180028427  test    eax, eax
0x180028429  jnz     short loc_180028455
0x18002842b  call    cs:__imp_GetLastError
0x180028431  mov     edi, eax
0x180028433  test    eax, eax
0x180028435  jz      short loc_18002844B
0x180028437  jle     loc_18002868C
0x18002843d  movzx   edi, ax
0x180028440  or      edi, 80070000h
0x180028446  jmp     loc_18002868C
0x18002844b  mov     edi, 80390004h
0x180028450  jmp     loc_18002868C
0x180028455  mov     rcx, [rbp+57h+TokenHandle]; hToken
0x180028459  call    cs:__imp_ImpersonateLoggedOnUser
0x18002845f  test    eax, eax
0x180028461  jnz     short loc_18002846D
0x180028463  mov     edi, 8000FFFFh
0x180028468  jmp     loc_18002868C
0x18002846d  cmp     [rbx], r13w
0x180028471  jz      loc_180028622
0x180028477  lea     rcx, [rbp+57h+var_98]
0x18002847b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180028480  mov     edx, 8
0x180028485  cmp     [rbx], dx
0x180028488  jz      short loc_18002848F
0x18002848a  lea     ecx, [rdx-3]
0x18002848d  int     29h; Win8: RtlFailFast(ecx)
0x18002848f  lea     eax, [rsi-0C8h]
0x180028495  cmp     eax, edx
0x180028497  jbe     short loc_1800284AC
0x180028499  mov     edi, 80070057h
0x18002849e  lea     rcx, [rbp+57h+var_98]
0x1800284a2  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800284a7  jmp     loc_18002868C
0x1800284ac  lea     rcx, [rbp+57h+var_98]
0x1800284b0  cmp     dx, [rbx]
0x1800284b3  jz      short loc_1800284BC
0x1800284b5  mov     edi, 80070057h
0x1800284ba  jmp     short loc_1800284A2
0x1800284bc  mov     rbx, [rbx+8]
0x1800284c0  call    ?GetWalletPhotosPath@ServerUtils@Wallet@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::ServerUtils::GetWalletPhotosPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800284c5  mov     edi, eax
0x1800284c7  test    eax, eax
0x1800284c9  js      short loc_18002849E
0x1800284cb  mov     rcx, [rbp+57h+var_98]; this
0x1800284cf  call    ?RecursiveCreateDirectory@FileUtils@Wallet@@YAJPEBG@Z; Wallet::FileUtils::RecursiveCreateDirectory(ushort const *)
0x1800284d4  mov     edi, eax
0x1800284d6  test    eax, eax
0x1800284d8  js      short loc_18002849E
0x1800284da  mov     rcx, rbx; psz
0x1800284dd  test    r15d, r15d
0x1800284e0  jz      short loc_180028506
0x1800284e2  lea     rdx, [rbp+57h+pszPath]
0x1800284e6  call    cs:__imp_DSGetSharedFileName
0x1800284ec  mov     edi, eax
0x1800284ee  test    eax, eax
0x1800284f0  jns     short loc_180028500
0x1800284f2  lea     rcx, [rbp+57h+var_98]
0x1800284f6  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800284fb  jmp     loc_180028691
0x180028500  mov     rax, [rbp+57h+pszPath]
0x180028504  jmp     short loc_180028510
0x180028506  call    cs:__imp_SysAllocString
0x18002850c  mov     [rbp+57h+pszPath], rax
0x180028510  mov     rcx, rax; pszPath
0x180028513  call    cs:__imp_PathFindExtensionW
0x180028519  cmp     r13w, [rax]
0x18002851d  jz      loc_180028499
0x180028523  xor     r9d, r9d
0x180028526  lea     rdx, [rbp+57h+psz]
0x18002852a  mov     r8, rax
0x18002852d  call    ?GetUniqueImagePath@WalletItem@Wallet@@AEAAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGH@Z; Wallet::WalletItem::GetUniqueImagePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,int)
0x180028532  mov     edi, eax
0x180028534  test    eax, eax
0x180028536  js      loc_18002849E
0x18002853c  mov     rax, [rbp+57h+psz]
0x180028540  lea     rdx, aWalletWalletit_0; "Wallet::WalletItem::SaveImageFile"
0x180028547  mov     [rsp+100h+var_D0], rax
0x18002854c  mov     r9, r14
0x18002854f  mov     rax, [rbp+57h+pszPath]
0x180028553  mov     r8d, 37Fh
0x180028559  mov     [rsp+100h+var_D8], rax
0x18002855e  mov     ecx, 5
0x180028563  lea     rax, aWalletSaveimag; "[Wallet, SaveImageFile] Attempting to s"...
0x18002856a  mov     [rsp+100h+var_E0], rax
0x18002856f  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180028574  lea     eax, [rcx+3]
0x180028577  mov     rcx, [rbp+57h+psz]; psz
0x18002857b  mov     word ptr [rbp+57h+var_78], ax
0x18002857f  call    cs:__imp_SysAllocString
0x180028585  mov     [rbp+57h+var_78+8], rax
0x180028589  test    rax, rax
0x18002858c  jnz     short loc_180028598
0x18002858e  mov     edi, 8007000Eh
0x180028593  jmp     loc_18002849E
0x180028598  mov     rdx, [rbp+57h+psz]; lpNewFileName
0x18002859c  mov     rcx, rbx; lpExistingFileName
0x18002859f  test    r15d, r15d
0x1800285a2  jz      loc_18002869D
0x1800285a8  call    cs:__imp_DSCopyFromSharedFile
0x1800285ae  mov     edi, eax
0x1800285b0  test    eax, eax
0x1800285b2  js      loc_1800284F2
0x1800285b8  mov     ecx, [r14+0A8h]
0x1800285bf  call    ?IsStandardItemType@Utils@Wallet@@YAHW4__MIDL___MIDL_itf_wallettypes_0000_0000_0001@@@Z; Wallet::Utils::IsStandardItemType(__MIDL___MIDL_itf_wallettypes_0000_0000_0001)
0x1800285c4  test    eax, eax
0x1800285c6  jz      short loc_180028616
0x1800285c8  cmp     esi, 0CCh
0x1800285ce  jnz     short loc_180028616
0x1800285d0  xor     eax, eax
0x1800285d2  lea     rdx, [r14+58h]
0x1800285d6  mov     [rbp+57h+var_A8], rax
0x1800285da  lea     r9, [rbp+57h+pvar]
0x1800285de  xorps   xmm0, xmm0
0x1800285e1  lea     r8d, [rsi-31h]
0x1800285e5  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800285e9  mov     eax, 16h
0x1800285ee  mov     dword ptr [rbp+57h+pvar+8], r13d
0x1800285f2  mov     word ptr [rbp+57h+pvar], ax
0x1800285f6  call    ??$TSetPropertyValue@V?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@WalletItem@Wallet@@QEAAJAEAV?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBUtagPROPVARIANT@@@Z; Wallet::WalletItem::TSetPropertyValue<utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>> &,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT const *)
0x1800285fb  lea     rcx, [rbp+57h+pvar]; pvar
0x1800285ff  mov     edi, eax
0x180028601  test    eax, eax
0x180028603  jns     short loc_180028610
0x180028605  call    cs:__imp_PropVariantClear
0x18002860b  jmp     loc_1800284F2
0x180028610  call    cs:__imp_PropVariantClear
0x180028616  lea     rcx, [rbp+57h+var_98]
0x18002861a  mov     r12b, 1
0x18002861d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180028622  xorps   xmm0, xmm0
0x180028625  lea     r9, [rbp+57h+pvar]
0x180028629  xor     eax, eax
0x18002862b  lea     rdx, [r14+58h]
0x18002862f  mov     r8d, esi
0x180028632  mov     [rbp+57h+var_A8], rax
0x180028636  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18002863a  call    ??$TGetPropertyValue@V?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@WalletItem@Wallet@@QEBAJAEBV?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAUtagPROPVARIANT@@@Z; Wallet::WalletItem::TGetPropertyValue<utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>> const &,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT *)
0x18002863f  test    eax, eax
0x180028641  js      short loc_18002865E
0x180028643  cmp     r13w, word ptr [rbp+57h+pvar]
0x180028648  jz      short loc_18002865E
0x18002864a  mov     rcx, [rbp+57h+pvar+8]; lpFileName
0x18002864e  call    cs:__imp_DeleteFileW
0x180028654  test    eax, eax
0x180028656  jnz     short loc_18002865E
0x180028658  call    cs:__imp_GetLastError
0x18002865e  lea     rcx, [rbp+57h+pvar]; pvar
0x180028662  call    cs:__imp_PropVariantClear
0x180028668  lea     r9, [rbp+57h+var_78]
0x18002866c  mov     r8d, esi
0x18002866f  lea     rdx, [r14+58h]
0x180028673  call    ??$TSetPropertyValue@V?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@WalletItem@Wallet@@QEAAJAEAV?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBUtagPROPVARIANT@@@Z; Wallet::WalletItem::TSetPropertyValue<utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>> &,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT const *)
0x180028678  mov     ebx, eax
0x18002867a  call    cs:__imp_RevertToSelf
0x180028680  mov     edi, 8000FFFFh
0x180028685  test    eax, eax
0x180028687  cmovz   ebx, edi
0x18002868a  mov     edi, ebx
0x18002868c  test    r15d, r15d
0x18002868f  jz      short loc_1800286B9
0x180028691  mov     rcx, [rbp+57h+pszPath]
0x180028695  call    cs:__imp_DSFreeString
0x18002869b  jmp     short loc_1800286C3
0x18002869d  call    cs:__imp_MoveFileW
0x1800286a3  test    eax, eax
0x1800286a5  jnz     loc_180028616
0x1800286ab  lea     rcx, [rbp+57h+var_98]
0x1800286af  mov     edi, 8000FFFFh
0x1800286b4  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800286b9  mov     rcx, [rbp+57h+pszPath]; bstrString
0x1800286bd  call    cs:__imp_SysFreeString
0x1800286c3  test    edi, edi
0x1800286c5  jns     short loc_1800286E0
0x1800286c7  test    r12b, r12b
0x1800286ca  jz      short loc_1800286E0
0x1800286cc  mov     rcx, [rbp+57h+psz]; lpFileName
0x1800286d0  call    cs:__imp_DeleteFileW
0x1800286d6  test    eax, eax
0x1800286d8  jnz     short loc_1800286E0
0x1800286da  call    cs:__imp_GetLastError
0x1800286e0  lea     rcx, [rbp+57h+TokenHandle]
0x1800286e4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800286e9  lea     rcx, [rbp+57h+var_78]; pvar
0x1800286ed  call    cs:__imp_PropVariantClear
0x1800286f3  lea     rcx, [rbp+57h+psz]
0x1800286f7  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800286fc  mov     eax, edi
0x1800286fe  add     rsp, 0C8h
0x180028705  pop     r15
0x180028707  pop     r14
0x180028709  pop     r13
0x18002870b  pop     r12
0x18002870d  pop     rdi
0x18002870e  pop     rsi
0x18002870f  pop     rbx
0x180028710  pop     rbp
0x180028711  retn
```
