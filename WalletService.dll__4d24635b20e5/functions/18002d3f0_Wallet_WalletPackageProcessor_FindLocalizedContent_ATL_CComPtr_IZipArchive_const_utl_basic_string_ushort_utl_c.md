# Wallet::WalletPackageProcessor::FindLocalizedContent(ATL::CComPtr<IZipArchive> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x18002d3f0`
- end: `0x18002d93e`
- name: `?FindLocalizedContent@WalletPackageProcessor@Wallet@@AEAAJAEBV?$CComPtr@UIZipArchive@@@ATL@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1358`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002e5b0`

## callees

- `0x180002f70`
- `0x18000ac74`
- `0x18000d620`
- `0x18000d6c8`
- `0x18000d8d8`
- `0x18000d910`
- `0x180012e78`
- `0x180012fbc`
- `0x1800136dc`
- `0x180013f78`
- `0x180013fe4`
- `0x18001400c`
- `0x18002ce40`
- `0x18002d048`
- `0x18002d3f0`
- `0x18002de4c`
- `0x18002ef00`
- `0x180031d28`
- `0x180031db4`
- `0x180032148`
- `0x180037ce0`
- `0x180038a40`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `msvcrt!wcstok_s` at `0x18002d510`
- `msvcrt!wcstok_s` at `0x18002d510`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d854`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d854`

## string_xrefs

- `0x18002d782`: `WalletItemPackage-%s.txt`

## pseudocode

```c
__int64 __fastcall Wallet::WalletPackageProcessor::FindLocalizedContent(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v4; // rbx
  int v5; // r14d
  unsigned int v6; // esi
  int v7; // r15d
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64); // rbx
  __int64 v10; // rax
  wchar_t *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  PCWSTR v15; // rax
  __int64 v16; // rax
  int LocaleName; // eax
  __int64 v18; // r8
  PCWSTR v19; // rdi
  const WCHAR *v20; // r13
  void **v21; // rbx
  int v22; // esi
  int LanguagesClosenessScore; // eax
  void **v24; // rcx
  int v25; // esi
  __int64 v26; // rdi
  int (__fastcall *v27)(__int64, _QWORD, __int64); // rbx
  __int64 v28; // rax
  int TemporaryFilename; // eax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  _WORD *v33; // rcx
  char *v34; // rbx
  _QWORD *v35; // rdx
  __int64 v36; // rax
  __int64 v38; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v39; // [rsp+28h] [rbp-D8h] BYREF
  int v40; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v41; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v43[4]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v44; // [rsp+68h] [rbp-98h]
  _QWORD v45[4]; // [rsp+70h] [rbp-90h] BYREF
  void *v46[3]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h]
  wchar_t *Context; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v49; // [rsp+C0h] [rbp-40h]
  _QWORD v50[4]; // [rsp+C8h] [rbp-38h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+E8h] [rbp-18h] BYREF
  PCWSTR sourceString[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v53; // [rsp+118h] [rbp+18h]
  unsigned __int64 v54; // [rsp+120h] [rbp+20h]
  wchar_t String[264]; // [rsp+130h] [rbp+30h] BYREF

  v4 = a2;
  v44 = a2;
  v49 = a1;
  v42 = 0;
  v40 = 0;
  v41 = 0;
  utl::unordered_map<unsigned __int64,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>>>::unordered_map<unsigned __int64,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>>>(v46);
  Context = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v50);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v4 + 40LL))(*v4, &v40);
  if ( v5 < 0 )
    goto LABEL_58;
  v6 = 0;
  v7 = -1;
  while ( (int)v6 < v40 )
  {
    v8 = *v4;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*v4 + 32LL);
    v10 = ce::pointerTo<IZipItem>(&v42);
    v5 = v9(v8, v6, v10);
    if ( v5 < 0 )
      goto LABEL_58;
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v42 + 24LL))(v42, &v41);
    if ( v5 < 0 )
      goto LABEL_58;
    v5 = StringCchCopyW(String, 0x104u, v41);
    if ( v5 < 0 )
      goto LABEL_58;
    v11 = wcstok_s(String, L"\\", &Context);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v50,
                             v11) )
      goto LABEL_21;
    v12 = -1;
    do
      ++v12;
    while ( v41[v12] );
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(v50[0] + 2 * v13) );
    if ( v13 != v12
      && v46 == *(void ***)utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::_FindFirstFind,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(
                             v46,
                             &v39,
                             v50) )
    {
      utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>>,0>::_FindInsertPos(
        v46,
        sourceString,
        v50);
      if ( (_BYTE)v53 )
      {
        v15 = sourceString[0];
      }
      else
      {
        v16 = utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::_NewNodeConstruct<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const &>(
                v14,
                v50);
        v15 = v16
            ? *(PCWSTR *)utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::_InsertAt(
                           v46,
                           &v38,
                           sourceString,
                           v16)
            : 0LL;
      }
      if ( !v15 )
      {
LABEL_21:
        v5 = -2147024882;
        goto LABEL_58;
      }
    }
    ++v6;
    v4 = v44;
  }
  v5 = 0;
  if ( !v47 )
  {
    v33 = (_WORD *)*a3;
    a3[1] = *a3;
    *v33 = 0;
    goto LABEL_58;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v45);
  v54 = 7;
  v53 = 0;
  LOWORD(sourceString[0]) = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v43);
  v38 = 0;
  v39 = 0;
  LocaleName = Wallet::Utils::GetLocaleName(v45);
  if ( LocaleName < 0 )
  {
    v5 = LocaleName;
    goto LABEL_56;
  }
  if ( *(_WORD *)v45[0] )
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(v45[0] + 2 * v18) );
  }
  else
  {
    v18 = 0;
  }
  std::wstring::assign(sourceString, v45[0], v18);
  v19 = (PCWSTR)v46[0];
  v20 = (const WCHAR *)sourceString;
  if ( v54 >= 8 )
    v20 = sourceString[0];
  v21 = v46;
  while ( v19 != (PCWSTR)v46 )
  {
    v22 = v7;
    LanguagesClosenessScore = GetLanguagesClosenessScore(v20, *((PCWSTR *)v19 + 3));
    if ( LanguagesClosenessScore > v7 )
      v7 = LanguagesClosenessScore;
    v24 = (void **)v19;
    if ( LanguagesClosenessScore <= v22 )
      v24 = v21;
    v21 = v24;
    v19 = *(PCWSTR *)v19;
  }
  if ( v46 == v21 )
    v21 = (void **)v46[0];
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a3,
                           v21[3])
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v43,
                           *a3,
                           (__int64)(a3[1] - *a3) >> 1) )
  {
    v5 = -2147024882;
LABEL_56:
    ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v39);
    ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v38);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v43);
    LOBYTE(v32) = 1;
    std::wstring::_Tidy(sourceString, v32, 0);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v45);
    goto LABEL_58;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v43,
                           L"\\",
                           1)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v43,
                           L"strings.txt",
                           11) )
  {
    v5 = -2147024882;
    goto LABEL_56;
  }
  v25 = 0;
  v26 = *v44;
  v27 = *(int (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*v44 + 24LL);
  v28 = ce::pointerTo<IZipItem>(&v38);
  if ( v27(v26, v43[0], v28) >= 0 )
  {
    TemporaryFilename = Wallet::Utils::GenerateTemporaryFilename(
                          (Wallet::Utils *)L"WalletItemPackage-%s.txt",
                          (__int64)lpFileName);
    if ( TemporaryFilename < 0 )
    {
      v5 = TemporaryFilename;
      goto LABEL_56;
    }
    if ( (*(int (__fastcall **)(__int64, LPCWSTR))(*(_QWORD *)v38 + 64LL))(v38, lpFileName[0]) < 0 )
    {
      v5 = -2143682458;
      goto LABEL_56;
    }
    if ( (int)Wallet::WalletPackageProcessor::ParseStringsFile(v49, lpFileName) < 0 )
    {
      v5 = -2143682458;
      ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v39);
      ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v38);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v43);
      LOBYTE(v30) = 1;
      std::wstring::_Tidy(sourceString, v30, 0);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v45);
LABEL_53:
      DeleteFileW(lpFileName[0]);
      goto LABEL_58;
    }
    v25 = 1;
  }
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v39);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v38);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v43);
  LOBYTE(v31) = 1;
  std::wstring::_Tidy(sourceString, v31, 0);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v45);
  if ( v25 )
    goto LABEL_53;
LABEL_58:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v50);
  while ( 1 )
  {
    v34 = (char *)v46[0];
    if ( v46[0] == v46 )
      break;
    v35 = (_QWORD *)*((_QWORD *)v46[0] + 1);
    v36 = *(_QWORD *)v46[0];
    *v35 = *(_QWORD *)v46[0];
    *(_QWORD *)(v36 + 8) = v35;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v34 + 24);
    operator delete(v34, (const struct std::nothrow_t *)&std::nothrow);
  }
  v47 = 0;
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>>,0>::_FreeBuckets(v46);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v42);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002d3f0  mov     [rsp-8+arg_18], rbx
0x18002d3f5  push    rbp
0x18002d3f6  push    rsi
0x18002d3f7  push    rdi
0x18002d3f8  push    r12
0x18002d3fa  push    r13
0x18002d3fc  push    r14
0x18002d3fe  push    r15
0x18002d400  lea     rbp, [rsp-250h]
0x18002d408  sub     rsp, 350h
0x18002d40f  mov     rax, cs:__security_cookie
0x18002d416  xor     rax, rsp
0x18002d419  mov     [rbp+280h+var_40], rax
0x18002d420  mov     r12, r8
0x18002d423  mov     rbx, rdx
0x18002d426  mov     [rsp+380h+var_318], rdx
0x18002d42b  mov     [rbp+280h+var_2C0], rcx
0x18002d42f  xor     r13d, r13d
0x18002d432  mov     [rsp+380h+var_340], r13
0x18002d437  mov     [rsp+380h+var_350], r13d
0x18002d43c  mov     [rsp+380h+var_348], r13
0x18002d441  lea     rcx, [rbp+280h+var_2F0]
0x18002d445  call    ??0?$unordered_map@_KW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$hash@_K@utl@@U?$equal_to@_K@3@V?$allocator@U?$pair@$$CB_KW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@@3@@utl@@QEAA@XZ; utl::unordered_map<unsigned __int64,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>>>::unordered_map<unsigned __int64,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>>>(void)
0x18002d44a  nop
0x18002d44b  mov     [rbp+280h+Context], r13
0x18002d44f  lea     rcx, [rbp+280h+var_2B8]
0x18002d453  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002d458  nop
0x18002d459  lea     rcx, [rbp+280h+lpFileName]
0x18002d45d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002d462  nop
0x18002d463  mov     rcx, [rbx]
0x18002d466  mov     rax, [rcx]
0x18002d469  lea     rdx, [rsp+380h+var_350]
0x18002d46e  mov     rax, [rax+28h]
0x18002d472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d477  mov     r14d, eax
0x18002d47a  test    eax, eax
0x18002d47c  js      loc_18002D8B0
0x18002d482  mov     esi, r13d
0x18002d485  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002d489  cmp     esi, [rsp+380h+var_350]
0x18002d48d  jge     loc_18002D5D1
0x18002d493  mov     rdi, [rbx]
0x18002d496  mov     rax, [rdi]
0x18002d499  mov     rbx, [rax+20h]
0x18002d49d  lea     rcx, [rsp+380h+var_340]
0x18002d4a2  call    ??$pointerTo@UIZipItem@@@ce@@YAPEAPEAUIZipItem@@AEAV?$CComPtr@UIZipItem@@@ATL@@@Z; ce::pointerTo<IZipItem>(ATL::CComPtr<IZipItem> &)
0x18002d4a7  mov     r8, rax
0x18002d4aa  mov     edx, esi
0x18002d4ac  mov     rcx, rdi
0x18002d4af  mov     rax, rbx
0x18002d4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4b7  mov     r14d, eax
0x18002d4ba  test    eax, eax
0x18002d4bc  js      loc_18002D8B0
0x18002d4c2  mov     rcx, [rsp+380h+var_340]
0x18002d4c7  mov     rax, [rcx]
0x18002d4ca  lea     rdx, [rsp+380h+var_348]
0x18002d4cf  mov     rax, [rax+18h]
0x18002d4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4d8  mov     r14d, eax
0x18002d4db  test    eax, eax
0x18002d4dd  js      loc_18002D8B0
0x18002d4e3  mov     r8, [rsp+380h+var_348]; unsigned __int16 *
0x18002d4e8  mov     edx, 104h; unsigned __int64
0x18002d4ed  lea     rcx, [rbp+280h+String]; unsigned __int16 *
0x18002d4f1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d4f6  mov     r14d, eax
0x18002d4f9  test    eax, eax
0x18002d4fb  js      loc_18002D8B0
0x18002d501  lea     r8, [rbp+280h+Context]; Context
0x18002d505  lea     rdx, asc_180049A9C; "\\"
0x18002d50c  lea     rcx, [rbp+280h+String]; String
0x18002d510  call    cs:__imp_wcstok_s
0x18002d516  mov     rdx, rax
0x18002d519  lea     rcx, [rbp+280h+var_2B8]
0x18002d51d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18002d522  test    al, al
0x18002d524  jz      loc_18002D5C6
0x18002d52a  mov     rcx, [rsp+380h+var_348]
0x18002d52f  mov     rax, r15
0x18002d532  inc     rax
0x18002d535  cmp     [rcx+rax*2], r13w
0x18002d53a  jnz     short loc_18002D532
0x18002d53c  mov     rdx, [rbp+280h+var_2B8]
0x18002d540  mov     rcx, r15
0x18002d543  inc     rcx
0x18002d546  cmp     [rdx+rcx*2], r13w
0x18002d54b  jnz     short loc_18002D543
0x18002d54d  cmp     rcx, rax
0x18002d550  jz      short loc_18002D5BA
0x18002d552  lea     r8, [rbp+280h+var_2B8]
0x18002d556  lea     rdx, [rsp+380h+var_358]
0x18002d55b  lea     rcx, [rbp+280h+var_2F0]
0x18002d55f  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@3@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::_FindFirstFind,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18002d564  lea     rcx, [rbp+280h+var_2F0]
0x18002d568  cmp     rcx, [rax]
0x18002d56b  jnz     short loc_18002D5BA
0x18002d56d  lea     r8, [rbp+280h+var_2B8]
0x18002d571  lea     rdx, [rbp+280h+sourceString]
0x18002d575  lea     rcx, [rbp+280h+var_2F0]
0x18002d579  call    ?_FindInsertPos@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@2@$0A@@utl@@AEAA?AU_InsertPosResult@12@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>>,0>::_FindInsertPos(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18002d57e  cmp     byte ptr [rbp+280h+var_268], r13b
0x18002d582  jz      short loc_18002D58A
0x18002d584  mov     rax, [rbp+280h+sourceString]
0x18002d588  jmp     short loc_18002D5B5
0x18002d58a  lea     rdx, [rbp+280h+var_2B8]
0x18002d58e  call    ??$_NewNodeConstruct@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@AEAAPEAU?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@1@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::_NewNodeConstruct<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18002d593  test    rax, rax
0x18002d596  jnz     short loc_18002D59D
0x18002d598  mov     rax, r13
0x18002d59b  jmp     short loc_18002D5B5
0x18002d59d  mov     r9, rax
0x18002d5a0  lea     r8, [rbp+280h+sourceString]
0x18002d5a4  lea     rdx, [rsp+380h+var_360]
0x18002d5a9  lea     rcx, [rbp+280h+var_2F0]
0x18002d5ad  call    ?_InsertAt@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@AEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@@2@AEBU_InsertPosResult@12@PEAU?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::_InsertAt(utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::_InsertPosResult const &,utl::_HashNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *)
0x18002d5b2  mov     rax, [rax]
0x18002d5b5  test    rax, rax
0x18002d5b8  jz      short loc_18002D5C6
0x18002d5ba  inc     esi
0x18002d5bc  mov     rbx, [rsp+380h+var_318]
0x18002d5c1  jmp     loc_18002D489
0x18002d5c6  mov     r14d, 8007000Eh
0x18002d5cc  jmp     loc_18002D8B0
0x18002d5d1  mov     r14d, r13d
0x18002d5d4  cmp     [rbp+280h+var_2D8], r13
0x18002d5d8  jbe     loc_18002D8A3
0x18002d5de  lea     rcx, [rsp+380h+var_310]
0x18002d5e3  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002d5e8  nop
0x18002d5e9  mov     [rbp+280h+var_260], 7
0x18002d5f1  mov     [rbp+280h+var_268], r13
0x18002d5f5  mov     word ptr [rbp+280h+sourceString], r13w
0x18002d5fa  lea     rcx, [rsp+380h+var_338]
0x18002d5ff  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002d604  nop
0x18002d605  mov     [rsp+380h+var_360], r13
0x18002d60a  mov     [rsp+380h+var_358], r13
0x18002d60f  lea     rcx, [rsp+380h+var_310]
0x18002d614  call    ?GetLocaleName@Utils@Wallet@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::GetLocaleName(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18002d619  test    eax, eax
0x18002d61b  js      loc_18002D864
0x18002d621  mov     rdx, [rsp+380h+var_310]
0x18002d626  cmp     [rdx], r13w
0x18002d62a  jnz     short loc_18002D631
0x18002d62c  mov     r8, r13
0x18002d62f  jmp     short loc_18002D63E
0x18002d631  mov     r8, r15
0x18002d634  inc     r8
0x18002d637  cmp     [rdx+r8*2], r13w
0x18002d63c  jnz     short loc_18002D634
0x18002d63e  lea     rcx, [rbp+280h+sourceString]
0x18002d642  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002d647  mov     rdi, [rbp+280h+var_2F0]
0x18002d64b  lea     r13, [rbp+280h+sourceString]
0x18002d64f  cmp     [rbp+280h+var_260], 8
0x18002d654  cmovnb  r13, [rbp+280h+sourceString]
0x18002d659  lea     rbx, [rbp+280h+var_2F0]
0x18002d65d  lea     rax, [rbp+280h+var_2F0]
0x18002d661  cmp     rdi, rax
0x18002d664  jz      short loc_18002D68D
0x18002d666  mov     esi, r15d
0x18002d669  mov     rdx, [rdi+18h]; PCWSTR
0x18002d66d  mov     rcx, r13; sourceString
0x18002d670  call    ?GetLanguagesClosenessScore@@YAHQEBG0@Z; GetLanguagesClosenessScore(ushort const * const,ushort const * const)
0x18002d675  cmp     eax, r15d
0x18002d678  cmovg   r15d, eax
0x18002d67c  mov     rcx, rdi
0x18002d67f  cmp     eax, esi
0x18002d681  cmovle  rcx, rbx
0x18002d685  mov     rbx, rcx
0x18002d688  mov     rdi, [rdi]
0x18002d68b  jmp     short loc_18002D65D
0x18002d68d  lea     rax, [rbp+280h+var_2F0]
0x18002d691  cmp     rax, rbx
0x18002d694  cmovz   rbx, [rbp+280h+var_2F0]
0x18002d699  mov     rdx, [rbx+18h]
0x18002d69d  mov     r8, [rbx+20h]
0x18002d6a1  sub     r8, rdx
0x18002d6a4  sar     r8, 1
0x18002d6a7  mov     rcx, r12
0x18002d6aa  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18002d6af  xor     r13d, r13d
0x18002d6b2  test    al, al
0x18002d6b4  jnz     short loc_18002D6C1
0x18002d6b6  mov     r14d, 8007000Eh
0x18002d6bc  jmp     loc_18002D867
0x18002d6c1  mov     r8, [r12+8]
0x18002d6c6  sub     r8, [r12]
0x18002d6ca  sar     r8, 1
0x18002d6cd  mov     rdx, [r12]
0x18002d6d1  lea     rcx, [rsp+380h+var_338]
0x18002d6d6  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18002d6db  test    al, al
0x18002d6dd  jz      short loc_18002D6B6
0x18002d6df  mov     r15d, 1
0x18002d6e5  mov     r8d, r15d
0x18002d6e8  lea     rdx, asc_180049A9C; "\\"
0x18002d6ef  lea     rcx, [rsp+380h+var_338]
0x18002d6f4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18002d6f9  test    al, al
0x18002d6fb  jnz     short loc_18002D72C
0x18002d6fd  mov     r14d, 8007000Eh
0x18002d703  lea     rcx, [rsp+380h+var_358]
0x18002d708  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002d70d  nop
0x18002d70e  lea     rcx, [rsp+380h+var_360]
0x18002d713  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002d718  nop
0x18002d719  lea     rcx, [rsp+380h+var_338]
0x18002d71e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002d723  nop
0x18002d724  mov     dl, r15b
0x18002d727  jmp     loc_18002D88A
0x18002d72c  mov     r8d, 0Bh
0x18002d732  lea     rdx, aStringsTxt; "strings.txt"
0x18002d739  lea     rcx, [rsp+380h+var_338]
0x18002d73e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18002d743  test    al, al
0x18002d745  jz      short loc_18002D6FD
0x18002d747  mov     esi, r13d
0x18002d74a  mov     rdi, [rsp+380h+var_318]
0x18002d74f  mov     rdi, [rdi]
0x18002d752  mov     rax, [rdi]
0x18002d755  mov     rbx, [rax+18h]
0x18002d759  lea     rcx, [rsp+380h+var_360]
0x18002d75e  call    ??$pointerTo@UIZipItem@@@ce@@YAPEAPEAUIZipItem@@AEAV?$CComPtr@UIZipItem@@@ATL@@@Z; ce::pointerTo<IZipItem>(ATL::CComPtr<IZipItem> &)
0x18002d763  mov     r8, rax
0x18002d766  mov     rdx, [rsp+380h+var_338]
0x18002d76b  mov     rcx, rdi
0x18002d76e  mov     rax, rbx
0x18002d771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d776  test    eax, eax
0x18002d778  js      loc_18002D811
0x18002d77e  lea     rdx, [rbp+280h+lpFileName]
0x18002d782  lea     rcx, aWalletitempack_0; "WalletItemPackage-%s.txt"
0x18002d789  call    ?GenerateTemporaryFilename@Utils@Wallet@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::GenerateTemporaryFilename(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18002d78e  test    eax, eax
0x18002d790  js      loc_18002D85C
0x18002d796  mov     rcx, [rsp+380h+var_360]
0x18002d79b  mov     rax, [rcx]
0x18002d79e  mov     rdx, [rbp+280h+lpFileName]
0x18002d7a2  mov     rax, [rax+40h]
0x18002d7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7ab  test    eax, eax
0x18002d7ad  jns     short loc_18002D7BA
0x18002d7af  mov     r14d, 803A0066h
0x18002d7b5  jmp     loc_18002D703
0x18002d7ba  lea     rdx, [rbp+280h+lpFileName]
0x18002d7be  mov     rcx, [rbp+280h+var_2C0]
0x18002d7c2  call    ?ParseStringsFile@WalletPackageProcessor@Wallet@@AEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::WalletPackageProcessor::ParseStringsFile(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18002d7c7  test    eax, eax
0x18002d7c9  jns     short loc_18002D80E
0x18002d7cb  mov     r14d, 803A0066h
0x18002d7d1  lea     rcx, [rsp+380h+var_358]
0x18002d7d6  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002d7db  nop
0x18002d7dc  lea     rcx, [rsp+380h+var_360]
0x18002d7e1  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002d7e6  nop
0x18002d7e7  lea     rcx, [rsp+380h+var_338]
0x18002d7ec  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002d7f1  nop
0x18002d7f2  xor     r8d, r8d
0x18002d7f5  mov     dl, r15b
0x18002d7f8  lea     rcx, [rbp+280h+sourceString]
0x18002d7fc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002d801  nop
0x18002d802  lea     rcx, [rsp+380h+var_310]
0x18002d807  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002d80c  jmp     short loc_18002D850
0x18002d80e  mov     esi, r15d
0x18002d811  lea     rcx, [rsp+380h+var_358]
0x18002d816  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002d81b  nop
0x18002d81c  lea     rcx, [rsp+380h+var_360]
0x18002d821  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002d826  nop
0x18002d827  lea     rcx, [rsp+380h+var_338]
0x18002d82c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002d831  nop
0x18002d832  xor     r8d, r8d
0x18002d835  mov     dl, r15b
0x18002d838  lea     rcx, [rbp+280h+sourceString]
0x18002d83c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002d841  nop
0x18002d842  lea     rcx, [rsp+380h+var_310]
0x18002d847  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18002d84c  test    esi, esi
0x18002d84e  jz      short loc_18002D8B0
0x18002d850  mov     rcx, [rbp+280h+lpFileName]; lpFileName
0x18002d854  call    cs:__imp_DeleteFileW
0x18002d85a  jmp     short loc_18002D8B0
0x18002d85c  mov     r14d, eax
0x18002d85f  jmp     loc_18002D703
0x18002d864  mov     r14d, eax
0x18002d867  lea     rcx, [rsp+380h+var_358]
0x18002d86c  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
  ... truncated ...
```
