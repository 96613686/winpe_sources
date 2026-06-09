# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetVirtualPrinterInfo(winrt::Windows::Devices::Printers::VirtualPrinterInstallationParameters const &,ushort const *,ushort const *)

- ea: `0x1800288d8`
- end: `0x180029101`
- name: `?GetVirtualPrinterInfo@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CA?AUVirtualPrinterInfo@VirtualMon@@AEBUVirtualPrinterInstallationParameters@Printers@Devices@78@PEBG1@Z`
- size: `2089`
- prototype: `__int64 __fastcall(__int64, __int64 *, const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800293fc`
- `0x1800296a0`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x180005eb4`
- `0x180007a58`
- `0x180008838`
- `0x18000e568`
- `0x18000f8a8`
- `0x18000f97c`
- `0x18000fa2c`
- `0x18000fa48`
- `0x18000fb60`
- `0x180012498`
- `0x18001c08c`
- `0x18001cfb4`
- `0x18001d058`
- `0x180023a20`
- `0x18002434c`
- `0x180026248`
- `0x1800266b8`
- `0x180027160`
- `0x180027440`
- `0x180027640`
- `0x180027940`
- `0x180027cf4`
- `0x1800288d8`
- `0x18002b22c`
- `0x18002b2cc`
- `0x18002b388`
- `0x180048010`

## import_xrefs

- `KERNELBASE!GetStagedPackagePathByFullName` at `0x180028947`
- `KERNELBASE!GetStagedPackagePathByFullName` at `0x180028947`

## string_xrefs

- `0x180028c25`: `virtual-printer:default-uri`
- `0x180028976`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x1800289bc`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x1800290ef`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180028966`: `GetStagedPackagePathByFullName failed for %ws with error %d`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetVirtualPrinterInfo(
        __int64 a1,
        __int64 *a2,
        const WCHAR *a3,
        __int64 a4)
{
  unsigned int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rsi
  unsigned int v18; // edi
  unsigned int v19; // r14d
  unsigned int v20; // eax
  int v21; // edi
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rbx
  unsigned int v23; // eax
  const unsigned __int16 *v24; // rax
  __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned int v32; // eax
  const wchar_t *v33; // rdx
  int v34; // edi
  unsigned int v35; // eax
  __int64 v36; // rbx
  __int64 v37; // rax
  unsigned int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  unsigned int StagedPackagePathByFullName; // [rsp+38h] [rbp-C8h]
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h]
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  int v47; // [rsp+68h] [rbp-98h] BYREF
  __int128 v48; // [rsp+70h] [rbp-90h]
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v50[8]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v51; // [rsp+90h] [rbp-70h]
  UINT32 pathLength; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v53; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v54[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v56[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  _BYTE Src[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v59; // [rsp+F0h] [rbp-10h] BYREF
  __m128i si128; // [rsp+100h] [rbp+0h]
  _OWORD v61[2]; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v62[2]; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v63[2]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v64; // [rsp+170h] [rbp+70h] BYREF
  __int64 v65; // [rsp+180h] [rbp+80h]
  __int64 v66; // [rsp+188h] [rbp+88h]
  _OWORD v67[2]; // [rsp+190h] [rbp+90h] BYREF
  _OWORD v68[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  _OWORD v69[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v70[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v71[2]; // [rsp+210h] [rbp+110h] BYREF
  __int128 v72; // [rsp+230h] [rbp+130h] BYREF
  __int64 v73; // [rsp+240h] [rbp+140h]
  __int64 v74; // [rsp+248h] [rbp+148h]
  _BYTE v75[16]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR path[264]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v57 = a4;
  v55 = a1;
  v51 = 0;
  memset_0(path, 0, 0x208u);
  pathLength = 260;
  StagedPackagePathByFullName = GetStagedPackagePathByFullName(a3, &pathLength, path);
  LOBYTE(v39) = StagedPackagePathByFullName != 0;
  wil::details::in1diag3::Throw_Win32IfMsg(
    retaddr,
    (void *)0x147,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
    (const char *)StagedPackagePathByFullName,
    v39,
    (bool)"GetStagedPackagePathByFullName failed for %ws with error %d",
    (const char *)a3,
    StagedPackagePathByFullName);
  v7 = StringCchCatW(path, 0x104u, L"\\");
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x148,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
    (const char *)v7,
    (int)"StringCchCat failed for %ws",
    (const char *)path);
  v59 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v59) = 0;
  v61[0] = 0;
  v61[1] = si128;
  LOWORD(v61[0]) = 0;
  v62[0] = 0;
  v62[1] = si128;
  LOWORD(v62[0]) = 0;
  v63[0] = 0;
  v63[1] = si128;
  LOWORD(v63[0]) = 0;
  v64 = 0;
  v65 = 0;
  v66 = 7;
  LOWORD(v64) = 0;
  v67[0] = 0;
  v67[1] = si128;
  LOWORD(v67[0]) = 0;
  v68[0] = 0;
  v68[1] = si128;
  LOWORD(v68[0]) = 0;
  v69[0] = 0;
  v69[1] = si128;
  LOWORD(v69[0]) = 0;
  v70[0] = 0;
  v70[1] = si128;
  LOWORD(v70[0]) = 0;
  v71[0] = 0;
  v71[1] = si128;
  LOWORD(v71[0]) = 0;
  v72 = 0;
  v73 = 0;
  v74 = 7;
  LOWORD(v72) = 0;
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v75);
  v42 = 0;
  v8 = *a2;
  v47 = 0;
  v48 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 144LL))(v8, &v42);
  winrt::check_hresult(&v43, v9, &v47);
  winrt::hstring::operator std::basic_string_view<unsigned short>(&v42, &v44);
  std::wstring::_Assign<unsigned short>(v61, v44);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v42);
  v42 = 0;
  v10 = *a2;
  v47 = 0;
  v48 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 48LL))(v10, &v42);
  winrt::check_hresult(&v43, v11, &v47);
  winrt::hstring::operator std::basic_string_view<unsigned short>(&v42, &v44);
  std::wstring::_Assign<unsigned short>(v62, v44);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v42);
  v42 = 0;
  v12 = *a2;
  v47 = 0;
  v48 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 128LL))(v12, &v42);
  winrt::check_hresult(&v43, v13, &v47);
  v54[0] = v42;
  if ( v42 )
  {
    v14 = winrt::impl::consume_Windows_Foundation_IStringable<winrt::Windows::Foundation::Uri>::ToString(v54, &v42);
    winrt::hstring::operator std::basic_string_view<unsigned short>(v14, &v44);
    std::wstring::_Assign<unsigned short>(&v64, v44);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v42);
  }
  else
  {
    std::wstring::_Assign<unsigned short>(&v64, L"virtual-printer:default-uri");
  }
  std::wstring::_Assign<unsigned short>(v63, &qword_18004B9D0);
  v42 = 0;
  v15 = *a2;
  v47 = 0;
  v48 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 64LL))(v15, &v42);
  winrt::check_hresult(&v43, v16, &v47);
  v17 = v42;
  v55 = v42;
  v18 = 30;
  v19 = 0;
  v43 = 0;
  v47 = 0;
  v48 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 56LL))(v42, &v43);
  winrt::check_hresult(v50, v20, &v47);
  while ( v19 != v43 )
  {
    v46 = 0;
    v21 = v18 | 0x40;
    v51 = v21;
    v47 = 0;
    v48 = 0;
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 48LL);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v46);
    v23 = v22(v17, v19, &v46);
    winrt::check_hresult(v50, v23, &v47);
    v51 = v21 & 0xFFFFFFBF;
    v18 = v21 & 0xFFFFFF9F | 0x20;
    if ( v73 )
      std::wstring::append(&v72, L";");
    v24 = winrt::hstring::c_str((winrt::hstring *)&v46);
    std::wstring::append(&v72, v24);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v46);
    ++v19;
  }
  v42 = 0;
  v25 = *a2;
  v47 = 0;
  v48 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 80LL))(v25, &v42);
  winrt::check_hresult(v50, v26, &v47);
  if ( !v42 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      (const char *)0x80070057LL,
      v40);
  winrt::hstring::operator std::basic_string_view<unsigned short>(&v42, &v44);
  std::wstring::_Assign<unsigned short>(v67, v44);
  v27 = winrt::operator+(&v49, path, &v42);
  winrt::hstring::operator std::basic_string_view<unsigned short>(v27, &v44);
  std::wstring::_Assign<unsigned short>(v68, v44);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v49);
  v49 = 0;
  v28 = *a2;
  v47 = 0;
  v48 = 0;
  v29 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 96LL))(v28, &v49);
  winrt::check_hresult(v50, v29, &v47);
  if ( v49 )
  {
    v30 = winrt::operator+(&v46, path, &v49);
    winrt::hstring::operator std::basic_string_view<unsigned short>(v30, &v44);
    std::wstring::_Assign<unsigned short>(v70, v44);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v46);
    winrt::hstring::operator std::basic_string_view<unsigned short>(&v49, &v44);
    std::wstring::_Assign<unsigned short>(v69, v44);
  }
  v43 = 0;
  v31 = *a2;
  v47 = 0;
  v48 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 112LL))(v31, &v43);
  winrt::check_hresult(v50, v32, &v47);
  if ( v43 == 1 )
    v33 = L"application/postscript";
  else
    v33 = L"application/oxps";
  std::wstring::_Assign<unsigned short>(v71, v33);
  winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterInstallationParameters<winrt::Windows::Devices::Printers::IVirtualPrinterInstallationParameters>::SupportedInputFormats(
    a2,
    &v53);
  v44 = &v53;
  v34 = 0;
  LODWORD(v45) = 0;
  v43 = 0;
  v47 = 0;
  v48 = 0;
  v35 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v53 + 56LL))(v53, &v43);
  winrt::check_hresult(v50, v35, &v47);
  while ( v34 != v43 )
  {
    winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Devices::Printers::VirtualPrinterSupportedFormat>>::operator*(
      &v44,
      &v46);
    v36 = winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterSupportedFormat<winrt::Windows::Devices::Printers::IVirtualPrinterSupportedFormat>::MaxSupportedVersion(
            &v46,
            v56);
    v37 = winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterSupportedFormat<winrt::Windows::Devices::Printers::IVirtualPrinterSupportedFormat>::ContentType(
            &v46,
            v50);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<winrt::hstring,winrt::hstring>(
      v75,
      &v47,
      v37,
      v36);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v50);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v56);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v46);
    LODWORD(v45) = ++v34;
  }
  std::wstring::wstring(Src, a3);
  std::wstring::append(Src, L"_");
  if ( v65 )
  {
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::append(Src, L"_");
  }
  std::wstring::append(Src, v57);
  std::wstring::operator=(&v59, Src);
  VirtualMon::VirtualPrinterInfo::VirtualPrinterInfo(a1, &v59);
  std::wstring::_Tidy_deallocate(Src);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v53);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v49);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v42);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v55);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v54);
  VirtualMon::VirtualPrinterInfo::~VirtualPrinterInfo((VirtualMon::VirtualPrinterInfo *)&v59);
  return a1;
}

```

## disassembly

```asm
0x1800288d8  push    rbp
0x1800288da  push    rbx
0x1800288db  push    rsi
0x1800288dc  push    rdi
0x1800288dd  push    r12
0x1800288df  push    r13
0x1800288e1  push    r14
0x1800288e3  push    r15
0x1800288e5  lea     rbp, [rsp-388h]
0x1800288ed  sub     rsp, 488h
0x1800288f4  mov     rax, cs:__security_cookie
0x1800288fb  xor     rax, rsp
0x1800288fe  mov     [rbp+3C0h+var_50], rax
0x180028905  mov     [rbp+3C0h+var_3F8], r9
0x180028909  mov     r13, r8
0x18002890c  mov     r15, rdx
0x18002890f  mov     r12, rcx
0x180028912  mov     [rbp+3C0h+var_410], rcx
0x180028916  mov     [rbp+3C0h+var_430], 0
0x18002891d  xor     edx, edx; Val
0x18002891f  mov     r8d, 208h; Size
0x180028925  lea     rcx, [rbp+3C0h+path]; void *
0x18002892c  call    memset_0
0x180028931  mov     ebx, 104h
0x180028936  mov     [rbp+3C0h+pathLength], ebx
0x180028939  lea     r8, [rbp+3C0h+path]; path
0x180028940  lea     rdx, [rbp+3C0h+pathLength]; pathLength
0x180028944  mov     rcx, r13; packageFullName
0x180028947  call    cs:__imp_GetStagedPackagePathByFullName
0x18002894d  mov     r9d, eax; char *
0x180028950  test    eax, eax
0x180028952  setnz   al
0x180028955  mov     rcx, [rbp+3C8h]; this
0x18002895c  mov     [rsp+4C0h+var_488], r9d
0x180028961  mov     [rsp+4C0h+var_490], r13; char *
0x180028966  lea     rdx, aGetstagedpacka; "GetStagedPackagePathByFullName failed f"...
0x18002896d  mov     [rsp+4C0h+var_498], rdx; bool
0x180028972  mov     byte ptr [rsp+4C0h+var_4A0], al; unsigned int
0x180028976  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002897d  lea     edx, [rbx+43h]; void *
0x180028980  call    ?Throw_Win32IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDK_N1ZZ; wil::details::in1diag3::Throw_Win32IfMsg(void *,uint,char const *,ulong,bool,char const *,...)
0x180028985  lea     r8, asc_18004B9C8; "\\"
0x18002898c  mov     edx, ebx; unsigned __int64
0x18002898e  lea     rcx, [rbp+3C0h+path]; unsigned __int16 *
0x180028995  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002899a  mov     rcx, [rbp+3C8h]; this
0x1800289a1  lea     rdx, [rbp+3C0h+path]
0x1800289a8  mov     [rsp+4C0h+var_498], rdx; char *
0x1800289ad  lea     rdx, aStringcchcatFa; "StringCchCat failed for %ws"
0x1800289b4  mov     qword ptr [rsp+4C0h+var_4A0], rdx; int
0x1800289b9  mov     r9d, eax; char *
0x1800289bc  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x1800289c3  lea     edx, [rbx+44h]; void *
0x1800289c6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800289cb  xorps   xmm0, xmm0
0x1800289ce  movups  [rbp+3C0h+var_3D0], xmm0
0x1800289d2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800289da  movdqa  [rbp+3C0h+var_3C0], xmm1
0x1800289df  xor     ebx, ebx
0x1800289e1  mov     word ptr [rbp+3C0h+var_3D0], bx
0x1800289e5  movups  [rbp+3C0h+var_3B0], xmm0
0x1800289e9  movdqa  [rbp+3C0h+var_3A0], xmm1
0x1800289ee  mov     word ptr [rbp+3C0h+var_3B0], bx
0x1800289f2  movups  [rbp+3C0h+var_390], xmm0
0x1800289f6  movdqa  [rbp+3C0h+var_380], xmm1
0x1800289fb  mov     word ptr [rbp+3C0h+var_390], bx
0x1800289ff  movups  [rbp+3C0h+var_370], xmm0
0x180028a03  movdqa  [rbp+3C0h+var_360], xmm1
0x180028a08  mov     word ptr [rbp+3C0h+var_370], bx
0x180028a0c  movups  [rbp+3C0h+var_350], xmm0
0x180028a10  mov     [rbp+3C0h+var_340], rbx
0x180028a17  lea     ecx, [rbx+7]
0x180028a1a  mov     [rbp+3C0h+var_338], rcx
0x180028a21  mov     word ptr [rbp+3C0h+var_350], bx
0x180028a25  movups  [rbp+3C0h+var_330], xmm0
0x180028a2c  movdqa  [rbp+3C0h+var_320], xmm1
0x180028a34  mov     word ptr [rbp+3C0h+var_330], bx
0x180028a3b  movups  [rbp+3C0h+var_310], xmm0
0x180028a42  movdqa  [rbp+3C0h+var_300], xmm1
0x180028a4a  mov     word ptr [rbp+3C0h+var_310], bx
0x180028a51  movups  [rbp+3C0h+var_2F0], xmm0
0x180028a58  movdqa  [rbp+3C0h+var_2E0], xmm1
0x180028a60  mov     word ptr [rbp+3C0h+var_2F0], bx
0x180028a67  movups  [rbp+3C0h+var_2D0], xmm0
0x180028a6e  movdqa  [rbp+3C0h+var_2C0], xmm1
0x180028a76  mov     word ptr [rbp+3C0h+var_2D0], bx
0x180028a7d  movups  [rbp+3C0h+var_2B0], xmm0
0x180028a84  movdqa  [rbp+3C0h+var_2A0], xmm1
0x180028a8c  mov     word ptr [rbp+3C0h+var_2B0], bx
0x180028a93  movups  [rbp+3C0h+var_290], xmm0
0x180028a9a  mov     [rbp+3C0h+var_280], rbx
0x180028aa1  mov     [rbp+3C0h+var_278], rcx
0x180028aa8  mov     word ptr [rbp+3C0h+var_290], bx
0x180028aaf  lea     rcx, [rbp+3C0h+var_270]
0x180028ab6  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x180028abb  nop
0x180028abc  mov     [rsp+4C0h+var_480], rbx
0x180028ac1  mov     rcx, [r15]
0x180028ac4  mov     [rsp+4C0h+var_458], ebx
0x180028ac8  xorps   xmm0, xmm0
0x180028acb  movdqu  [rsp+4C0h+var_450], xmm0
0x180028ad1  mov     rax, [rcx]
0x180028ad4  lea     rdx, [rsp+4C0h+var_480]
0x180028ad9  mov     rax, [rax+90h]
0x180028ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ae5  lea     r8, [rsp+4C0h+var_458]
0x180028aea  mov     edx, eax
0x180028aec  lea     rcx, [rsp+4C0h+var_478]
0x180028af1  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028af6  mov     rax, [rsp+4C0h+var_480]
0x180028afb  mov     [rsp+4C0h+var_480], rax
0x180028b00  lea     rdx, [rsp+4C0h+var_470]
0x180028b05  lea     rcx, [rsp+4C0h+var_480]
0x180028b0a  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180028b0f  mov     r8, [rsp+4C0h+var_468]
0x180028b14  mov     rdx, [rsp+4C0h+var_470]
0x180028b19  lea     rcx, [rbp+3C0h+var_3B0]
0x180028b1d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028b22  nop
0x180028b23  lea     rcx, [rsp+4C0h+var_480]
0x180028b28  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180028b2d  mov     [rsp+4C0h+var_480], rbx
0x180028b32  mov     rcx, [r15]
0x180028b35  mov     [rsp+4C0h+var_458], ebx
0x180028b39  xorps   xmm0, xmm0
0x180028b3c  movdqu  [rsp+4C0h+var_450], xmm0
0x180028b42  mov     rax, [rcx]
0x180028b45  lea     rdx, [rsp+4C0h+var_480]
0x180028b4a  mov     rax, [rax+30h]
0x180028b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b53  lea     r8, [rsp+4C0h+var_458]
0x180028b58  mov     edx, eax
0x180028b5a  lea     rcx, [rsp+4C0h+var_478]
0x180028b5f  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028b64  mov     rax, [rsp+4C0h+var_480]
0x180028b69  mov     [rsp+4C0h+var_480], rax
0x180028b6e  lea     rdx, [rsp+4C0h+var_470]
0x180028b73  lea     rcx, [rsp+4C0h+var_480]
0x180028b78  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180028b7d  mov     r8, [rsp+4C0h+var_468]
0x180028b82  mov     rdx, [rsp+4C0h+var_470]
0x180028b87  lea     rcx, [rbp+3C0h+var_390]
0x180028b8b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028b90  nop
0x180028b91  lea     rcx, [rsp+4C0h+var_480]
0x180028b96  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180028b9b  mov     [rsp+4C0h+var_480], rbx
0x180028ba0  mov     rcx, [r15]
0x180028ba3  mov     [rsp+4C0h+var_458], ebx
0x180028ba7  xorps   xmm0, xmm0
0x180028baa  movdqu  [rsp+4C0h+var_450], xmm0
0x180028bb0  mov     rax, [rcx]
0x180028bb3  lea     rdx, [rsp+4C0h+var_480]
0x180028bb8  mov     rax, [rax+80h]
0x180028bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bc4  lea     r8, [rsp+4C0h+var_458]
0x180028bc9  mov     edx, eax
0x180028bcb  lea     rcx, [rsp+4C0h+var_478]
0x180028bd0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028bd5  mov     rax, [rsp+4C0h+var_480]
0x180028bda  mov     [rbp+3C0h+var_420], rax
0x180028bde  test    rax, rax
0x180028be1  jz      short loc_180028C1F
0x180028be3  lea     rdx, [rsp+4C0h+var_480]
0x180028be8  lea     rcx, [rbp+3C0h+var_420]
0x180028bec  call    ?ToString@?$consume_Windows_Foundation_IStringable@UUri@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IStringable<winrt::Windows::Foundation::Uri>::ToString(void)
0x180028bf1  nop
0x180028bf2  lea     rdx, [rsp+4C0h+var_470]
0x180028bf7  mov     rcx, rax
0x180028bfa  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180028bff  mov     r8, [rsp+4C0h+var_468]
0x180028c04  mov     rdx, [rsp+4C0h+var_470]
0x180028c09  lea     rcx, [rbp+3C0h+var_350]
0x180028c0d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028c12  nop
0x180028c13  lea     rcx, [rsp+4C0h+var_480]
0x180028c18  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180028c1d  jmp     short loc_180028C35
0x180028c1f  mov     r8d, 1Bh
0x180028c25  lea     rdx, aVirtualPrinter; "virtual-printer:default-uri"
0x180028c2c  lea     rcx, [rbp+3C0h+var_350]
0x180028c30  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028c35  xor     r8d, r8d
0x180028c38  lea     rdx, qword_18004B9D0
0x180028c3f  lea     rcx, [rbp+3C0h+var_370]
0x180028c43  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028c48  mov     [rsp+4C0h+var_480], rbx
0x180028c4d  mov     rcx, [r15]
0x180028c50  mov     [rsp+4C0h+var_458], ebx
0x180028c54  xorps   xmm0, xmm0
0x180028c57  movdqu  [rsp+4C0h+var_450], xmm0
0x180028c5d  mov     rax, [rcx]
0x180028c60  lea     rdx, [rsp+4C0h+var_480]
0x180028c65  mov     rax, [rax+40h]
0x180028c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c6e  lea     r8, [rsp+4C0h+var_458]
0x180028c73  mov     edx, eax
0x180028c75  lea     rcx, [rsp+4C0h+var_478]
0x180028c7a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028c7f  mov     rsi, [rsp+4C0h+var_480]
0x180028c84  mov     [rbp+3C0h+var_410], rsi
0x180028c88  mov     edi, 1Eh
0x180028c8d  mov     r14d, ebx
0x180028c90  mov     [rsp+4C0h+var_478], ebx
0x180028c94  mov     [rsp+4C0h+var_458], ebx
0x180028c98  xorps   xmm0, xmm0
0x180028c9b  movdqu  [rsp+4C0h+var_450], xmm0
0x180028ca1  mov     rax, [rsi]
0x180028ca4  lea     rdx, [rsp+4C0h+var_478]
0x180028ca9  mov     rcx, rsi
0x180028cac  mov     rax, [rax+38h]
0x180028cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cb5  lea     r8, [rsp+4C0h+var_458]
0x180028cba  mov     edx, eax
0x180028cbc  lea     rcx, [rbp+3C0h+var_438]
0x180028cc0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028cc5  cmp     r14d, [rsp+4C0h+var_478]
0x180028cca  jz      loc_180028D6F
0x180028cd0  mov     [rsp+4C0h+var_460], rbx
0x180028cd5  or      edi, 40h
0x180028cd8  mov     [rbp+3C0h+var_430], edi
0x180028cdb  mov     [rsp+4C0h+var_458], ebx
0x180028cdf  xorps   xmm0, xmm0
0x180028ce2  movdqu  [rsp+4C0h+var_450], xmm0
0x180028ce8  mov     rax, [rsi]
0x180028ceb  mov     rbx, [rax+30h]
0x180028cef  lea     rcx, [rsp+4C0h+var_460]
0x180028cf4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180028cf9  lea     r8, [rsp+4C0h+var_460]
0x180028cfe  mov     edx, r14d
0x180028d01  mov     rcx, rsi
0x180028d04  mov     rax, rbx
0x180028d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d0c  lea     r8, [rsp+4C0h+var_458]
0x180028d11  mov     edx, eax
0x180028d13  lea     rcx, [rbp+3C0h+var_438]
0x180028d17  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028d1c  and     edi, 0FFFFFFBFh
0x180028d1f  mov     [rbp+3C0h+var_430], edi
0x180028d22  or      edi, 20h
0x180028d25  xor     ebx, ebx
0x180028d27  cmp     [rbp+3C0h+var_280], rbx
0x180028d2e  jz      short loc_180028D43
0x180028d30  lea     rdx, asc_18004E370; ";"
0x180028d37  lea     rcx, [rbp+3C0h+var_290]
0x180028d3e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180028d43  lea     rcx, [rsp+4C0h+var_460]; this
0x180028d48  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180028d4d  mov     rdx, rax
0x180028d50  lea     rcx, [rbp+3C0h+var_290]
0x180028d57  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180028d5c  nop
0x180028d5d  lea     rcx, [rsp+4C0h+var_460]
0x180028d62  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180028d67  inc     r14d
0x180028d6a  jmp     loc_180028CC5
0x180028d6f  mov     [rsp+4C0h+var_480], rbx
0x180028d74  mov     rcx, [r15]
0x180028d77  mov     [rsp+4C0h+var_458], ebx
0x180028d7b  xorps   xmm0, xmm0
0x180028d7e  movdqu  [rsp+4C0h+var_450], xmm0
0x180028d84  mov     rax, [rcx]
0x180028d87  lea     rdx, [rsp+4C0h+var_480]
0x180028d8c  mov     rax, [rax+50h]
0x180028d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d95  lea     r8, [rsp+4C0h+var_458]
0x180028d9a  mov     edx, eax
0x180028d9c  lea     rcx, [rbp+3C0h+var_438]
0x180028da0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028da5  mov     rax, [rsp+4C0h+var_480]
0x180028daa  mov     [rsp+4C0h+var_480], rax
0x180028daf  test    rax, rax
0x180028db2  setz    al
0x180028db5  mov     rcx, [rbp+3C8h]; this
0x180028dbc  test    al, al
0x180028dbe  jnz     loc_1800290E9
0x180028dc4  lea     rdx, [rsp+4C0h+var_470]
0x180028dc9  lea     rcx, [rsp+4C0h+var_480]
0x180028dce  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180028dd3  mov     r8, [rsp+4C0h+var_468]
0x180028dd8  mov     rdx, [rsp+4C0h+var_470]
0x180028ddd  lea     rcx, [rbp+3C0h+var_330]
0x180028de4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028de9  lea     r8, [rsp+4C0h+var_480]
0x180028dee  lea     rdx, [rbp+3C0h+path]
0x180028df5  lea     rcx, [rbp+3C0h+var_440]
0x180028df9  call    ??Hwinrt@@YA?AUhstring@0@PEBGAEBU10@@Z; winrt::operator+(ushort const *,winrt::hstring const &)
0x180028dfe  nop
0x180028dff  lea     rdx, [rsp+4C0h+var_470]
0x180028e04  mov     rcx, rax
0x180028e07  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180028e0c  mov     r8, [rsp+4C0h+var_468]
0x180028e11  mov     rdx, [rsp+4C0h+var_470]
0x180028e16  lea     rcx, [rbp+3C0h+var_310]
0x180028e1d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028e22  nop
0x180028e23  lea     rcx, [rbp+3C0h+var_440]
0x180028e27  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180028e2c  mov     [rbp+3C0h+var_440], rbx
0x180028e30  mov     rcx, [r15]
  ... truncated ...
```
