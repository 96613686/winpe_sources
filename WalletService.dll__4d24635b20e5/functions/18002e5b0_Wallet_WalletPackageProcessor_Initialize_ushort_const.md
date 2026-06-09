# Wallet::WalletPackageProcessor::Initialize(ushort const *)

- ea: `0x18002e5b0`
- end: `0x18002edb4`
- name: `?Initialize@WalletPackageProcessor@Wallet@@UEAAJPEBG@Z`
- size: `2052`
- prototype: `__int64 __fastcall(struct IUnknown **this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002214`
- `0x180003ae4`
- `0x180003b40`
- `0x1800056c0`
- `0x18000bcd4`
- `0x18000d3fc`
- `0x18000d8d8`
- `0x18000de7c`
- `0x18001108c`
- `0x18001188c`
- `0x180013f78`
- `0x18001869c`
- `0x18001aa30`
- `0x18001d5a0`
- `0x18001e870`
- `0x180020140`
- `0x18002ce40`
- `0x18002ce74`
- `0x18002d048`
- `0x18002d168`
- `0x18002d3f0`
- `0x18002e5b0`
- `0x18002edbc`
- `0x1800306b0`
- `0x180031d8c`
- `0x180031db4`
- `0x180032628`
- `0x180037ce0`
- `0x18003a010`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb9f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002e93c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002e94b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002eb91`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002e93c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002e94b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002eb91`
- `dsclient!DSCopyFromSharedFile` at `0x18002e75d`
- `dsclient!DSCopyFromSharedFile` at `0x18002e75d`
- `dsclient!DSOpenSharedFile` at `0x18002e702`
- `dsclient!DSOpenSharedFile` at `0x18002e723`
- `dsclient!DSOpenSharedFile` at `0x18002e85b`
- `dsclient!DSOpenSharedFile` at `0x18002e702`
- `dsclient!DSOpenSharedFile` at `0x18002e723`
- `dsclient!DSOpenSharedFile` at `0x18002e85b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ec21`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ec75`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ec21`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ec75`

## string_xrefs

- `0x18002eb39`: `WalletItemPackage-%s.png`
- `0x18002e6c8`: `WalletItemXmlDssToken`
- `0x18002e98d`: `WalletItem.xml`

## pseudocode

```c
__int64 __fastcall Wallet::WalletPackageProcessor::Initialize(struct IUnknown **this, const unsigned __int16 *a2)
{
  int v4; // r15d
  int v5; // r14d
  struct IUnknown **v6; // rdi
  struct IUnknown *v7; // rdx
  struct IUnknown *v8; // r8
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int v11; // esi
  int v12; // r15d
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int TemporaryFilename; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  int PrivateInstance; // ebx
  struct TheWallet *v20; // rbx
  __int64 (__fastcall *v21)(_QWORD); // rax
  int v22; // eax
  int v23; // edx
  int v24; // r8d
  int v25; // r9d
  struct IUnknown *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  _QWORD *v29; // rdi
  struct TheWallet *v30; // r12
  _QWORD *v31; // rbx
  struct IUnknown *v32; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, __int64); // rbx
  __int64 v38; // rax
  unsigned int i; // r15d
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // r14
  struct IUnknown *v43; // rdi
  HRESULT (__stdcall *v44)(IUnknown *, const IID *const, void **); // rbx
  __int64 v45; // rax
  struct IUnknown *v46; // rdi
  HRESULT (__stdcall *v47)(IUnknown *, const IID *const, void **); // rbx
  __int64 v48; // rax
  int v49; // eax
  int v50; // eax
  signed int LastError; // eax
  __int64 v52; // r14
  signed int v53; // ebx
  int v54; // ebx
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // r8
  int v59; // [rsp+20h] [rbp-E0h]
  struct TheWallet *v60; // [rsp+28h] [rbp-D8h]
  int v61; // [rsp+40h] [rbp-C0h]
  char v62[4]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v63[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown **v64; // [rsp+50h] [rbp-B0h]
  struct TheWallet *v65; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v66; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v67; // [rsp+68h] [rbp-98h] BYREF
  __int64 v68; // [rsp+70h] [rbp-90h] BYREF
  int v69; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v70[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v72[3]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v74; // [rsp+C8h] [rbp-38h]
  LPCWSTR v75[4]; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+100h] [rbp+0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v78; // [rsp+130h] [rbp+30h]
  unsigned __int16 v79[264]; // [rsp+140h] [rbp+40h] BYREF

  v71 = 0;
  v62[0] = 0;
  v66 = 0;
  v68 = 0;
  v67 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  v4 = 0;
  v61 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v75);
  v5 = 0;
  v6 = this + 2;
  v64 = this + 2;
  if ( this[2] )
    ATL::AtlComPtrAssign(this + 2, 0);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v73);
  v69 = 0;
  v7 = this[9];
  v8 = this[10];
  this[10] = v7;
  utl::_RangeDestroyApc<utl::allocator<ATL::CComPtr<IWalletItem>>>(v9, v7, v8 - v7);
  memset(v72, 0, sizeof(v72));
  v63[0] = 260;
  if ( (Microsoft_Windows_WalletEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(MICROSOFT_WINDOWS_WALLET_Context, Core_ProcessPackage_Start, v10, 1, pvar);
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)v72,
                        HKEY_LOCAL_MACHINE,
                        L"Software\\Microsoft\\Wallet\\PackageProcessor",
                        0x20019u)
    && !(unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v72, L"WalletItemXmlDssToken", v79, v63) )
  {
    v11 = 0;
    v12 = 1;
    goto LABEL_26;
  }
  *(_QWORD *)v63 = 0;
  v13 = tlx::replace<tlx::file_handle_traits>(v63);
  v14 = DSOpenSharedFile(a2, 2, v13);
  v11 = v14;
  if ( v14 == -1055719414 )
  {
    v15 = tlx::replace<tlx::file_handle_traits>(v63);
    TemporaryFilename = DSOpenSharedFile(a2, 0, v15);
    if ( TemporaryFilename < 0 )
    {
LABEL_10:
      v11 = TemporaryFilename;
LABEL_11:
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(v63);
      goto LABEL_34;
    }
  }
  else if ( v14 < 0 )
  {
    goto LABEL_11;
  }
  TemporaryFilename = Wallet::Utils::GenerateTemporaryFilename((Wallet::Utils *)L"%s.mswallet", (__int64)lpFileName);
  if ( TemporaryFilename < 0 )
    goto LABEL_10;
  TemporaryFilename = DSCopyFromSharedFile(a2, lpFileName[0]);
  if ( TemporaryFilename < 0 )
    goto LABEL_10;
  v4 = 1;
  v61 = 1;
  v65 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v65);
  PrivateInstance = TheWallet::GetPrivateInstance(&v65);
  if ( PrivateInstance >= 0 )
  {
    v20 = v65;
    Wallet::DynamicLoader::TryInitialize((struct TheWallet *)((char *)v65 + 104));
    v21 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)v20 + 17);
    if ( v21 )
    {
      v22 = v21(0);
      PrivateInstance = 0;
      if ( v22 < 0 )
        PrivateInstance = v22;
    }
    else
    {
      PrivateInstance = -2147467263;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v65);
  if ( PrivateInstance < 0 )
  {
    v62[0] = 0;
    v11 = PrivateInstance;
    goto LABEL_11;
  }
  v62[0] = 1;
  v26 = v66;
  if ( v66 )
  {
    v66 = 0;
    ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
  }
  TemporaryFilename = ZipContainerCreateArchiveOnFile((int)lpFileName[0], v23, v24, v25, v59, v60, (__int64)&v66);
  if ( TemporaryFilename < 0 )
    goto LABEL_10;
  TemporaryFilename = Wallet::WalletPackageProcessor::FindLocalizedContent(this, &v66, &v73);
  if ( TemporaryFilename < 0 )
    goto LABEL_10;
  v12 = 0;
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(v63);
LABEL_26:
  *(_QWORD *)v63 = 0;
  if ( v12 )
  {
    v65 = 0;
    v27 = tlx::replace<tlx::file_handle_traits>(&v65);
    v28 = DSOpenSharedFile(v79, 0, v27);
    if ( v28 < 0 )
    {
      v11 = v28;
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v65);
      ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(v63);
      goto LABEL_33;
    }
    v29 = (_QWORD *)ce::pointerTo<IZipItem>(v63);
    v30 = v65;
    v31 = operator new(0x18u);
    pvar[0] = v31;
    if ( !v31 )
    {
      v11 = -2147024882;
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v65);
      ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(v63);
      goto LABEL_32;
    }
    *v31 = &CFileReadStream::`vftable';
    v31[1] = 0;
    *((_DWORD *)v31 + 4) = 0;
    Wallet::WalletXTransactionManager::AddRef((Wallet::WalletXTransactionManager *)v31);
    tlx::unique_any<tlx::file_handle_traits>::reset(v31 + 1, v30);
    *v29 = v31;
    v65 = 0;
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v65);
  }
  else
  {
    v32 = v66;
    QueryInterface = v66->lpVtbl[1].QueryInterface;
    v34 = ce::pointerTo<IZipItem>(&v68);
    v35 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, __int64))QueryInterface)(
            v32,
            L"WalletItem.xml",
            v34);
    if ( v35 < 0 )
      goto LABEL_44;
    v36 = v68;
    v37 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 32LL);
    v38 = ce::pointerTo<IZipItem>(v63);
    v35 = v37(v36, v38);
    if ( v35 < 0 )
      goto LABEL_44;
  }
  v35 = Wallet::WalletPackageProcessor::ProcessWalletItemXml(this, v63, &v67, &v69);
  if ( v35 < 0 )
  {
LABEL_44:
    v11 = v35;
    ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(v63);
    goto LABEL_32;
  }
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(v63);
  if ( v12 )
    goto LABEL_32;
  for ( i = 0; ; ++i )
  {
    v5 = 0;
    if ( i >= 8 )
      goto LABEL_32;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v70);
    v40 = v73;
    v41 = v74;
    if ( v73 == v74 )
    {
      v42 = i;
    }
    else
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v70,
                               v73,
                               (v74 - v73) >> 1)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v70,
                               L"\\",
                               1)
        || (v42 = i,
            !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v70,
                                (&off_1800479F0)[2 * i])) )
      {
        v11 = -2147024882;
        goto LABEL_81;
      }
      v41 = v74;
      v40 = v73;
    }
    if ( v40 == v41
      || (v43 = v66,
          v44 = v66->lpVtbl[1].QueryInterface,
          v45 = ce::pointerTo<IZipItem>(&v68),
          ((int (__fastcall *)(struct IUnknown *, _QWORD, __int64))v44)(v43, v70[0], v45) < 0) )
    {
      v46 = v66;
      v47 = v66->lpVtbl[1].QueryInterface;
      v48 = ce::pointerTo<IZipItem>(&v68);
      if ( ((int (__fastcall *)(struct IUnknown *, wchar_t *, __int64))v47)(v46, (&off_1800479F0)[2 * v42], v48) < 0 )
      {
        if ( *((_DWORD *)&off_1800479F0 + 4 * v42 + 3) )
        {
          v11 = -2143682459;
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v70);
          goto LABEL_82;
        }
      }
    }
    if ( !v68 )
    {
      v52 = 2 * v42;
      if ( *((_DWORD *)&off_1800479F0 + 2 * v52 + 2) == 204 )
      {
        *(_OWORD *)pvar = 0;
        v78 = 0;
        if ( v67 )
        {
          v53 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, PROPVARIANT *))v67->lpVtbl[2].QueryInterface)(
                  v67,
                  155,
                  pvar);
          if ( v53 >= 0 )
            v53 = LOWORD(pvar[0]) != 22 ? 0x8000FFFF : 0;
        }
        else
        {
          v53 = -2147467261;
        }
        PropVariantClear(pvar);
        if ( v53 != -2143682560 )
          goto LABEL_79;
      }
      *(_OWORD *)pvar = 0;
      v78 = 0;
      if ( v67 )
      {
        v55 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, PROPVARIANT *))v67->lpVtbl[2].AddRef)(
                v67,
                *((unsigned int *)&off_1800479F0 + 2 * v52 + 2),
                pvar);
        v54 = 0;
        if ( v55 < 0 )
          v54 = v55;
      }
      else
      {
        v54 = -2147467261;
      }
      PropVariantClear(pvar);
      if ( v54 >= 0 )
        goto LABEL_79;
      v11 = v54;
LABEL_81:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v70);
LABEL_82:
      v5 = 0;
      goto LABEL_32;
    }
    v49 = Wallet::Utils::GenerateTemporaryFilename((Wallet::Utils *)L"WalletItemPackage-%s.png", (__int64)v75);
    if ( v49 < 0 || (v49 = (*(__int64 (__fastcall **)(__int64, LPCWSTR))(*(_QWORD *)v68 + 64LL))(v68, v75[0]), v49 < 0) )
    {
      v11 = v49;
      goto LABEL_81;
    }
    v5 = 1;
    v50 = Wallet::Utils::SetItemImageProperty(v67, *((unsigned int *)&off_1800479F0 + 4 * i + 2), v75[0]);
    if ( v50 < 0 )
    {
      v11 = v50;
      goto LABEL_85;
    }
    if ( !DeleteFileW(v75[0]) )
      break;
LABEL_79:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v70);
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v11 = -2143748092;
  }
LABEL_85:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v70);
LABEL_32:
  v6 = v64;
LABEL_33:
  v4 = v61;
LABEL_34:
  if ( v66 )
    ATL::AtlComPtrAssign(&v66, 0);
  if ( v4 )
    DeleteFileW(lpFileName[0]);
  if ( v5 )
    DeleteFileW(v75[0]);
  if ( (v11 & 0x80000000) != 0 )
  {
    if ( v69 )
      Wallet::WalletPackageProcessor::LogPackageErrorWithService(v17, &v67, v11);
  }
  else if ( *v6 != v67 )
  {
    ATL::AtlComPtrAssign(v6, v67);
  }
  if ( (Microsoft_Windows_WalletEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(MICROSOFT_WINDOWS_WALLET_Context, Core_ProcessPackage_Stop, v18, 1, pvar);
  ATL::CRegKey::Close((ATL::CRegKey *)v72);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v73);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v75);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v67, v56, v57);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v68);
  ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(&v66);
  ZipContainerInit::~ZipContainerInit((ZipContainerInit *)v62);
  tlx::unique_any<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>::~unique_any<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>(&v71);
  return v11;
}

```

## disassembly

```asm
0x18002e5b0  mov     [rsp-8+arg_10], rbx
0x18002e5b5  push    rbp
0x18002e5b6  push    rsi
0x18002e5b7  push    rdi
0x18002e5b8  push    r12
0x18002e5ba  push    r13
0x18002e5bc  push    r14
0x18002e5be  push    r15
0x18002e5c0  lea     rbp, [rsp-260h]
0x18002e5c8  sub     rsp, 360h
0x18002e5cf  mov     rax, cs:__security_cookie
0x18002e5d6  xor     rax, rsp
0x18002e5d9  mov     [rbp+290h+var_40], rax
0x18002e5e0  mov     rbx, rdx
0x18002e5e3  mov     r13, rcx
0x18002e5e6  xor     r12d, r12d
0x18002e5e9  mov     [rbp+290h+var_2F0], r12
0x18002e5ed  mov     [rsp+390h+var_34C], r12b
0x18002e5f2  mov     [rsp+390h+var_330], r12
0x18002e5f7  mov     [rsp+390h+var_320], r12
0x18002e5fc  mov     [rsp+390h+var_328], r12
0x18002e601  lea     rcx, [rbp+290h+lpFileName]
0x18002e605  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002e60a  nop
0x18002e60b  mov     r15d, r12d
0x18002e60e  mov     [rsp+390h+var_350], r12d
0x18002e613  lea     rcx, [rbp+290h+var_2B0]
0x18002e617  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002e61c  nop
0x18002e61d  mov     r14d, r12d
0x18002e620  lea     rdi, [r13+10h]
0x18002e624  mov     [rsp+390h+var_340], rdi
0x18002e629  cmp     [rdi], r12
0x18002e62c  jz      short loc_18002E638
0x18002e62e  xor     edx, edx; struct IUnknown *
0x18002e630  mov     rcx, rdi; struct IUnknown **
0x18002e633  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002e638  lea     rcx, [rbp+290h+var_2D0]
0x18002e63c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002e641  nop
0x18002e642  mov     [rsp+390h+var_318], r12d
0x18002e647  mov     rdx, [r13+48h]
0x18002e64b  mov     r8, [r13+50h]
0x18002e64f  mov     [r13+50h], rdx
0x18002e653  sub     r8, rdx
0x18002e656  sar     r8, 3
0x18002e65a  call    ??$_RangeDestroyApc@V?$allocator@V?$CComPtr@UIWalletItem@@@ATL@@@utl@@@utl@@YAXAEAV?$allocator@V?$CComPtr@UIWalletItem@@@ATL@@@0@PEAV?$CComPtr@UIWalletItem@@@ATL@@_K@Z; utl::_RangeDestroyApc<utl::allocator<ATL::CComPtr<IWalletItem>>>(utl::allocator<ATL::CComPtr<IWalletItem>> &,ATL::CComPtr<IWalletItem> *,unsigned __int64)
0x18002e65f  mov     [rbp+290h+var_2E8], r12
0x18002e663  mov     [rbp+290h+var_2E0], r12
0x18002e667  mov     [rbp+290h+var_2D8], r12
0x18002e66b  mov     [rsp+390h+var_348], 104h
0x18002e673  test    cs:Microsoft_Windows_WalletEnableBits, 1
0x18002e67a  jz      short loc_18002E69E
0x18002e67c  lea     rax, [rbp+290h+pvar]
0x18002e680  mov     qword ptr [rsp+390h+var_370], rax; int
0x18002e685  mov     r9d, 1
0x18002e68b  lea     rdx, Core_ProcessPackage_Start
0x18002e692  lea     rcx, MICROSOFT_WINDOWS_WALLET_Context
0x18002e699  call    McGenEventWrite_EventWriteTransfer
0x18002e69e  mov     r9d, 20019h; unsigned int
0x18002e6a4  lea     r8, ?sc_szWalletPackageProcessorXmlRegKey@WalletPackageProcessor@Wallet@@0QBGB; "Software\\Microsoft\\Wallet\\PackagePro"...
0x18002e6ab  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002e6b2  lea     rcx, [rbp+290h+var_2E8]; this
0x18002e6b6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002e6bb  test    eax, eax
0x18002e6bd  jnz     short loc_18002E6E8
0x18002e6bf  lea     r9, [rsp+390h+var_348]; unsigned int *
0x18002e6c4  lea     r8, [rbp+290h+var_250]; unsigned __int16 *
0x18002e6c8  lea     rdx, ?sc_szWalletItemXmlDssTokenRegKeyName@WalletPackageProcessor@Wallet@@0QBGB; "WalletItemXmlDssToken"
0x18002e6cf  lea     rcx, [rbp+290h+var_2E8]; this
0x18002e6d3  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18002e6d8  test    eax, eax
0x18002e6da  jnz     short loc_18002E6E8
0x18002e6dc  mov     esi, r12d
0x18002e6df  lea     r15d, [rax+1]
0x18002e6e3  jmp     loc_18002E835
0x18002e6e8  mov     qword ptr [rsp+390h+var_348], r12
0x18002e6ed  lea     rcx, [rsp+390h+var_348]
0x18002e6f2  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18002e6f7  mov     r8, rax
0x18002e6fa  mov     edx, 2
0x18002e6ff  mov     rcx, rbx
0x18002e702  call    cs:__imp_DSOpenSharedFile
0x18002e708  mov     esi, eax
0x18002e70a  cmp     eax, 0C113000Ah
0x18002e70f  jnz     short loc_18002E73E
0x18002e711  lea     rcx, [rsp+390h+var_348]
0x18002e716  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18002e71b  mov     r8, rax
0x18002e71e  xor     edx, edx
0x18002e720  mov     rcx, rbx
0x18002e723  call    cs:__imp_DSOpenSharedFile
0x18002e729  test    eax, eax
0x18002e72b  jns     short loc_18002E742
0x18002e72d  mov     esi, eax
0x18002e72f  lea     rcx, [rsp+390h+var_348]
0x18002e734  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002e739  jmp     loc_18002E920
0x18002e73e  test    eax, eax
0x18002e740  js      short loc_18002E72F
0x18002e742  lea     rdx, [rbp+290h+lpFileName]
0x18002e746  lea     rcx, aSMswallet; "%s.mswallet"
0x18002e74d  call    ?GenerateTemporaryFilename@Utils@Wallet@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::GenerateTemporaryFilename(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18002e752  test    eax, eax
0x18002e754  js      short loc_18002E72D
0x18002e756  mov     rdx, [rbp+290h+lpFileName]
0x18002e75a  mov     rcx, rbx
0x18002e75d  call    cs:__imp_DSCopyFromSharedFile
0x18002e763  test    eax, eax
0x18002e765  js      short loc_18002E72D
0x18002e767  mov     r15d, 1
0x18002e76d  mov     [rsp+390h+var_350], r15d
0x18002e772  mov     [rsp+390h+var_338], r12
0x18002e777  lea     rcx, [rsp+390h+var_338]
0x18002e77c  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x18002e781  lea     rcx, [rsp+390h+var_338]; struct TheWallet **
0x18002e786  call    ?GetPrivateInstance@TheWallet@@SAJPEAPEAV1@@Z; TheWallet::GetPrivateInstance(TheWallet * *)
0x18002e78b  mov     ebx, eax
0x18002e78d  test    eax, eax
0x18002e78f  js      short loc_18002E7C1
0x18002e791  mov     rbx, [rsp+390h+var_338]
0x18002e796  lea     rcx, [rbx+68h]; this
0x18002e79a  call    ?TryInitialize@DynamicLoader@Wallet@@IEAAXXZ; Wallet::DynamicLoader::TryInitialize(void)
0x18002e79f  mov     rax, [rbx+88h]
0x18002e7a6  test    rax, rax
0x18002e7a9  jnz     short loc_18002E7B2
0x18002e7ab  mov     ebx, 80004001h
0x18002e7b0  jmp     short loc_18002E7C1
0x18002e7b2  xor     ecx, ecx
0x18002e7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7b9  mov     ebx, r12d
0x18002e7bc  test    eax, eax
0x18002e7be  cmovs   ebx, eax
0x18002e7c1  lea     rcx, [rsp+390h+var_338]
0x18002e7c6  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x18002e7cb  test    ebx, ebx
0x18002e7cd  js      loc_18002ECDF
0x18002e7d3  mov     [rsp+390h+var_34C], r15b
0x18002e7d8  mov     rcx, [rsp+390h+var_330]
0x18002e7dd  test    rcx, rcx
0x18002e7e0  jz      short loc_18002E7F4
0x18002e7e2  mov     [rsp+390h+var_330], r12
0x18002e7e7  mov     rax, [rcx]
0x18002e7ea  mov     rax, [rax+10h]
0x18002e7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7f3  nop
0x18002e7f4  lea     rax, [rsp+390h+var_330]
0x18002e7f9  mov     [rsp+390h+var_360], rax; __int64
0x18002e7fe  mov     rcx, [rbp+290h+lpFileName]; int
0x18002e802  call    ZipContainerCreateArchiveOnFile
0x18002e807  test    eax, eax
0x18002e809  js      loc_18002E72D
0x18002e80f  lea     r8, [rbp+290h+var_2D0]
0x18002e813  lea     rdx, [rsp+390h+var_330]
0x18002e818  mov     rcx, r13
0x18002e81b  call    ?FindLocalizedContent@WalletPackageProcessor@Wallet@@AEAAJAEBV?$CComPtr@UIZipArchive@@@ATL@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::WalletPackageProcessor::FindLocalizedContent(ATL::CComPtr<IZipArchive> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18002e820  test    eax, eax
0x18002e822  js      loc_18002E72D
0x18002e828  mov     r15d, r12d
0x18002e82b  lea     rcx, [rsp+390h+var_348]
0x18002e830  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002e835  mov     qword ptr [rsp+390h+var_348], r12
0x18002e83a  test    r15d, r15d
0x18002e83d  jz      loc_18002E974
0x18002e843  mov     [rsp+390h+var_338], r12
0x18002e848  lea     rcx, [rsp+390h+var_338]
0x18002e84d  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18002e852  mov     r8, rax
0x18002e855  xor     edx, edx
0x18002e857  lea     rcx, [rbp+290h+var_250]
0x18002e85b  call    cs:__imp_DSOpenSharedFile
0x18002e861  test    eax, eax
0x18002e863  jns     short loc_18002E881
0x18002e865  mov     esi, eax
0x18002e867  lea     rcx, [rsp+390h+var_338]
0x18002e86c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002e871  nop
0x18002e872  lea     rcx, [rsp+390h+var_348]
0x18002e877  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002e87c  jmp     loc_18002E91B
0x18002e881  lea     rcx, [rsp+390h+var_348]
0x18002e886  call    ??$pointerTo@UIZipItem@@@ce@@YAPEAPEAUIZipItem@@AEAV?$CComPtr@UIZipItem@@@ATL@@@Z; ce::pointerTo<IZipItem>(ATL::CComPtr<IZipItem> &)
0x18002e88b  mov     rdi, rax
0x18002e88e  mov     r12, [rsp+390h+var_338]
0x18002e893  mov     ecx, 18h; Size
0x18002e898  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e89d  mov     rbx, rax
0x18002e8a0  mov     [rbp+290h+pvar], rax
0x18002e8a4  test    rax, rax
0x18002e8a7  jz      short loc_18002E8F9
0x18002e8a9  lea     rax, ??_7CFileReadStream@@6B@; const CFileReadStream::`vftable'
0x18002e8b0  mov     [rbx], rax
0x18002e8b3  mov     qword ptr [rbx+8], 0
0x18002e8bb  mov     dword ptr [rbx+10h], 0
0x18002e8c2  test    rbx, rbx
0x18002e8c5  jz      short loc_18002E8F9
0x18002e8c7  mov     rax, [rax+8]
0x18002e8cb  mov     rcx, rbx
0x18002e8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8d3  lea     rcx, [rbx+8]
0x18002e8d7  mov     rdx, r12
0x18002e8da  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18002e8df  mov     [rdi], rbx
0x18002e8e2  xor     r12d, r12d
0x18002e8e5  mov     [rsp+390h+var_338], r12
0x18002e8ea  lea     rcx, [rsp+390h+var_338]
0x18002e8ef  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002e8f4  jmp     loc_18002E9DC
0x18002e8f9  mov     esi, 8007000Eh
0x18002e8fe  lea     rcx, [rsp+390h+var_338]
0x18002e903  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002e908  nop
0x18002e909  lea     rcx, [rsp+390h+var_348]
0x18002e90e  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002e913  xor     r12d, r12d
0x18002e916  mov     rdi, [rsp+390h+var_340]
0x18002e91b  mov     r15d, [rsp+390h+var_350]
0x18002e920  cmp     [rsp+390h+var_330], r12
0x18002e925  jz      short loc_18002E933
0x18002e927  xor     edx, edx; struct IUnknown *
0x18002e929  lea     rcx, [rsp+390h+var_330]; struct IUnknown **
0x18002e92e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002e933  test    r15d, r15d
0x18002e936  jz      short loc_18002E942
0x18002e938  mov     rcx, [rbp+290h+lpFileName]; lpFileName
0x18002e93c  call    cs:__imp_DeleteFileW
0x18002e942  test    r14d, r14d
0x18002e945  jz      short loc_18002E951
0x18002e947  mov     rcx, [rbp+290h+var_2B0]; lpFileName
0x18002e94b  call    cs:__imp_DeleteFileW
0x18002e951  test    esi, esi
0x18002e953  js      loc_18002ECEB
0x18002e959  mov     rdx, [rsp+390h+var_328]; struct IUnknown *
0x18002e95e  cmp     [rdi], rdx
0x18002e961  jz      loc_18002ECFF
0x18002e967  mov     rcx, rdi; struct IUnknown **
0x18002e96a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002e96f  jmp     loc_18002ECFF
0x18002e974  mov     rdi, [rsp+390h+var_330]
0x18002e979  mov     rax, [rdi]
0x18002e97c  mov     rbx, [rax+18h]
0x18002e980  lea     rcx, [rsp+390h+var_320]
0x18002e985  call    ??$pointerTo@UIZipItem@@@ce@@YAPEAPEAUIZipItem@@AEAV?$CComPtr@UIZipItem@@@ATL@@@Z; ce::pointerTo<IZipItem>(ATL::CComPtr<IZipItem> &)
0x18002e98a  mov     r8, rax
0x18002e98d  lea     rdx, aWalletitemXml; "WalletItem.xml"
0x18002e994  mov     rcx, rdi
0x18002e997  mov     rax, rbx
0x18002e99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e99f  test    eax, eax
0x18002e9a1  jns     short loc_18002E9B4
0x18002e9a3  mov     esi, eax
0x18002e9a5  lea     rcx, [rsp+390h+var_348]
0x18002e9aa  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002e9af  jmp     loc_18002E916
0x18002e9b4  mov     rdi, [rsp+390h+var_320]
0x18002e9b9  mov     rax, [rdi]
0x18002e9bc  mov     rbx, [rax+20h]
0x18002e9c0  lea     rcx, [rsp+390h+var_348]
0x18002e9c5  call    ??$pointerTo@UIZipItem@@@ce@@YAPEAPEAUIZipItem@@AEAV?$CComPtr@UIZipItem@@@ATL@@@Z; ce::pointerTo<IZipItem>(ATL::CComPtr<IZipItem> &)
0x18002e9ca  mov     rdx, rax
0x18002e9cd  mov     rcx, rdi
0x18002e9d0  mov     rax, rbx
0x18002e9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9d8  test    eax, eax
0x18002e9da  js      short loc_18002E9A3
0x18002e9dc  lea     r9, [rsp+390h+var_318]
0x18002e9e1  lea     r8, [rsp+390h+var_328]
0x18002e9e6  lea     rdx, [rsp+390h+var_348]
0x18002e9eb  mov     rcx, r13
0x18002e9ee  call    ?ProcessWalletItemXml@WalletPackageProcessor@Wallet@@AEAAJAEAV?$CComPtr@UIReadStream@@@ATL@@AEAV?$CComPtr@UIWalletItem@@@4@PEAH@Z; Wallet::WalletPackageProcessor::ProcessWalletItemXml(ATL::CComPtr<IReadStream> &,ATL::CComPtr<IWalletItem> &,int *)
0x18002e9f3  test    eax, eax
0x18002e9f5  js      short loc_18002E9A3
0x18002e9f7  lea     rcx, [rsp+390h+var_348]
0x18002e9fc  call    ??1?$CComPtrBase@UIWalletWebServiceManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWalletWebServiceManager>::~CComPtrBase<IWalletWebServiceManager>(void)
0x18002ea01  test    r15d, r15d
0x18002ea04  jnz     loc_18002E916
0x18002ea0a  mov     r15d, r12d
0x18002ea0d  lea     rbx, off_1800479F0; "Logo99x99.png"
0x18002ea14  mov     r13d, 1
0x18002ea1a  mov     r14d, r12d
0x18002ea1d  cmp     r15d, 8
0x18002ea21  jnb     loc_18002E916
0x18002ea27  lea     rcx, [rbp+290h+var_310]
0x18002ea2b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18002ea30  nop
0x18002ea31  mov     rcx, [rbp+290h+var_2D0]
0x18002ea35  mov     rax, [rbp+290h+var_2C8]
0x18002ea39  cmp     rcx, rax
0x18002ea3c  jz      short loc_18002EA9E
0x18002ea3e  sub     rax, rcx
0x18002ea41  sar     rax, 1
0x18002ea44  mov     r8, rax
0x18002ea47  mov     rdx, rcx
0x18002ea4a  lea     rcx, [rbp+290h+var_310]
0x18002ea4e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18002ea53  test    al, al
0x18002ea55  jz      loc_18002EC97
0x18002ea5b  mov     r8, r13
0x18002ea5e  lea     rdx, asc_180049A9C; "\\"
0x18002ea65  lea     rcx, [rbp+290h+var_310]
  ... truncated ...
```
