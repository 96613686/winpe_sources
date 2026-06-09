# PrintConfig::CConfigManager::FetchAndSaveVirtualPrinterFileExtensions(void)

- ea: `0x18004403c`
- end: `0x180044622`
- name: `?FetchAndSaveVirtualPrinterFileExtensions@CConfigManager@PrintConfig@@AEAAXXZ`
- size: `1510`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180044628`

## callees

- `0x180003400`
- `0x180003c20`
- `0x18000de1c`
- `0x18000fa4c`
- `0x18003c440`
- `0x18003d4e0`
- `0x18003e830`
- `0x18004001c`
- `0x1800403e4`
- `0x180040848`
- `0x1800409e0`
- `0x180041830`
- `0x18004403c`
- `0x18004a36c`
- `0x18004c604`
- `0x1800527f8`
- `0x1800ea340`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800445f2`
- `ole32!CoTaskMemFree` at `0x1800445f2`
- `WINSPOOL!SetPrinterDataExW` at `0x180044498`
- `WINSPOOL!SetPrinterDataExW` at `0x180044498`
- `WINSPOOL!SetPrinterDataW` at `0x18004450d`
- `WINSPOOL!SetPrinterDataW` at `0x180044591`
- `WINSPOOL!SetPrinterDataW` at `0x18004450d`
- `WINSPOOL!SetPrinterDataW` at `0x180044591`

## string_xrefs

- `0x180044502`: `DefaultSaveAsExtension`
- `0x1800444bf`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x180044534`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x1800445b3`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x18004409b`: `\Printer.VirtualPrinter:FileExtensions`
- `0x180044525`: `Failed to set default file extension %ws`
- `0x18004448d`: `PrinterDriverData\SaveAsExtensions`
- `0x1800444b0`: `Failed to set file extension %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall PrintConfig::CConfigManager::FetchAndSaveVirtualPrinterFileExtensions(HANDLE *this)
{
  void *v2; // r14
  unsigned __int64 v3; // r8
  __int128 *v4; // rcx
  char *v5; // rbx
  __int128 *v6; // rdi
  char *v7; // rax
  const __m128i *traits_4_0_unsigned_int; // rax
  char *v9; // rcx
  unsigned __int64 v10; // rcx
  char v11; // dl
  __int128 v12; // xmm0
  __int128 v13; // xmm0
  LPCWSTR v14; // rdx
  char v15; // r15
  LPCWSTR v16; // rdi
  LPCWSTR v17; // rbx
  const WCHAR *v18; // r8
  const char *v19; // rsi
  DWORD v20; // eax
  const char *v21; // rsi
  BYTE *v22; // r9
  DWORD v23; // eax
  DWORD v24; // eax
  const char *cbData; // [rsp+28h] [rbp-D8h]
  __int64 pData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE v27[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v28; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pValueName[2]; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v30; // [rsp+60h] [rbp-A0h]
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  __int128 *v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h]
  struct std::_Facet_base **v34; // [rsp+80h] [rbp-80h]
  int v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  char v37; // [rsp+98h] [rbp-68h]
  __int128 v38; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v39; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v40; // [rsp+C0h] [rbp-40h]
  char v41; // [rsp+C8h] [rbp-38h]
  __int128 v42; // [rsp+D0h] [rbp-30h]
  char v43; // [rsp+E0h] [rbp-20h]
  _QWORD v44[2]; // [rsp+E8h] [rbp-18h] BYREF
  char v45; // [rsp+F8h] [rbp-8h]
  __int128 v46; // [rsp+100h] [rbp+0h] BYREF
  char *v47; // [rsp+110h] [rbp+10h]
  char v48; // [rsp+118h] [rbp+18h]
  __int64 v49; // [rsp+120h] [rbp+20h]
  const __m128i *v50; // [rsp+128h] [rbp+28h] BYREF
  __int128 v51; // [rsp+130h] [rbp+30h]
  __int64 v52; // [rsp+140h] [rbp+40h]
  __int128 v53; // [rsp+150h] [rbp+50h]
  __int64 v54; // [rsp+160h] [rbp+60h]
  int v55; // [rsp+168h] [rbp+68h]
  __int64 v56; // [rsp+170h] [rbp+70h]
  char v57; // [rsp+178h] [rbp+78h]
  _OWORD v58[2]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v59; // [rsp+1A0h] [rbp+A0h]
  char v60; // [rsp+1A8h] [rbp+A8h]
  __int128 v61; // [rsp+1B0h] [rbp+B0h]
  char v62; // [rsp+1C0h] [rbp+C0h]
  __int64 v63; // [rsp+1C8h] [rbp+C8h]
  __int64 v64; // [rsp+1D0h] [rbp+D0h]
  char v65; // [rsp+1D8h] [rbp+D8h]
  __int128 v66; // [rsp+1E0h] [rbp+E0h]
  __int64 v67; // [rsp+1F0h] [rbp+F0h]
  char v68; // [rsp+1F8h] [rbp+F8h]
  __int64 v69; // [rsp+200h] [rbp+100h]
  char *v70; // [rsp+208h] [rbp+108h] BYREF
  __int128 v71; // [rsp+210h] [rbp+110h]
  struct std::_Facet_base *v72[5]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v73; // [rsp+248h] [rbp+148h] BYREF
  __int128 v74; // [rsp+258h] [rbp+158h]
  __int128 v75; // [rsp+268h] [rbp+168h] BYREF
  __int64 v76; // [rsp+278h] [rbp+178h]
  unsigned __int64 v77; // [rsp+280h] [rbp+180h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v52 = -2;
  pv = 0;
  PrintConfig::CConfigManager::RetrieveBidiData(
    (PrintConfig::CConfigManager *)this,
    L"\\Printer.VirtualPrinter:FileExtensions",
    0,
    4,
    (unsigned __int8 **)&pv,
    (unsigned int *)&pData);
  v2 = pv;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)pv + v3) );
  std::wstring::_Construct<1,unsigned short const *>(&v75, pv, v3);
  *(_OWORD *)pValueName = 0;
  v30 = 0;
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
    v72,
    (__int64)L";");
  v4 = &v75;
  if ( v77 > 7 )
    v4 = (__int128 *)v75;
  v5 = (char *)v4 + 2 * v76;
  v6 = &v75;
  if ( v77 > 7 )
    v6 = (__int128 *)v75;
  LODWORD(pData) = -1;
  *(_QWORD *)&v28 = &v32;
  v32 = v6;
  v33 = (__int64)v4 + 2 * v76;
  v34 = v72;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44[0] = 0;
  v44[1] = 0;
  v45 = 0;
  if ( !std::_Regex_search2<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>,unsigned short,std::regex_traits<unsigned short>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
          (__int64)v6,
          v33,
          (__int64)&v36,
          (__int64 *)v72,
          0,
          (__int64)v6) )
    v34 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v7 = (char *)operator new(4u);
  v50 = (const __m128i *)v7;
  *((_QWORD *)&v51 + 1) = v7 + 4;
  *(_DWORD *)v7 = pData;
  *(_QWORD *)&v51 = v7 + 4;
  *(_QWORD *)&v28 = 0;
  std::_Tidy_guard<std::vector<unsigned int>>::~_Tidy_guard<std::vector<unsigned int>>((char ***)&v28);
  if ( v34 )
  {
    if ( v50->m128i_i32[v49] == -1 )
    {
      v9 = (char *)&v39 + 8;
    }
    else
    {
      v10 = v50->m128i_i32[v49];
      if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v38 + 1) - v38) >> 3) > v10 )
        v9 = (char *)(v38 + 24 * v10);
      else
        v9 = (char *)v44;
    }
  }
  else
  {
    traits_4_0_unsigned_int = anonymous_namespace_::_Finding::_Find_impl__anonymous_namespace_::_Finding::_Find_traits_4_0_unsigned_int_(
                                v50,
                                (const __m128i *)v51,
                                0xFFFFFFFF);
    if ( traits_4_0_unsigned_int == (const __m128i *)v51 )
    {
      v9 = 0;
    }
    else
    {
      v48 = 1;
      *((_QWORD *)&v46 + 1) = v6;
      v47 = v5;
      v9 = (char *)&v46 + 8;
    }
  }
  *(_QWORD *)&v46 = v9;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  memset(v58, 0, sizeof(v58));
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  while ( v9 )
  {
    v11 = v9[16];
    if ( v11 )
      v12 = *(_OWORD *)v9;
    else
      v12 = 0;
    v28 = v12;
    if ( *((_QWORD *)&v12 + 1) != (_QWORD)v12 )
    {
      if ( v11 )
        v13 = *(_OWORD *)v9;
      else
        v13 = 0;
      v28 = v13;
      v73 = 0;
      v74 = 0u;
      if ( (_QWORD)v13 == *((_QWORD *)&v13 + 1) )
      {
        *(_QWORD *)&v74 = 0;
        *((_QWORD *)&v74 + 1) = 7;
        LOWORD(v73) = 0;
      }
      else
      {
        std::wstring::_Construct<1,unsigned short const *>(
          &v73,
          (const void *)v28,
          (__int64)(*((_QWORD *)&v28 + 1) - v28) >> 1);
      }
      v14 = pValueName[1];
      if ( pValueName[1] == v30 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(pValueName, (__int64)pValueName[1], &v73);
      }
      else
      {
        *(_OWORD *)pValueName[1] = v73;
        *((_OWORD *)v14 + 1) = v74;
        *(_QWORD *)&v74 = 0;
        *((_QWORD *)&v74 + 1) = 7;
        LOWORD(v73) = 0;
        pValueName[1] += 16;
      }
      std::wstring::~wstring((char **)&v73);
    }
    std::regex_token_iterator<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>>::operator++((__int64)&v32);
    v9 = (char *)v46;
  }
  std::vector<enum Print::Driver::Config::DataModel::DriverEventTransport::Type>::~vector<enum Print::Driver::Config::DataModel::DriverEventTransport::Type>(&v70);
  std::vector<std::sub_match<unsigned short const *>>::~vector<std::sub_match<unsigned short const *>>((char **)v58);
  std::vector<enum Print::Driver::Config::DataModel::DriverEventTransport::Type>::~vector<enum Print::Driver::Config::DataModel::DriverEventTransport::Type>((char **)&v50);
  std::vector<std::sub_match<unsigned short const *>>::~vector<std::sub_match<unsigned short const *>>((char **)&v38);
  v15 = 0;
  v16 = pValueName[1];
  v17 = pValueName[0];
  if ( pValueName[0] != pValueName[1] )
  {
    do
    {
      LODWORD(pData) = 0;
      if ( *((_QWORD *)v17 + 3) <= 7u )
      {
        v19 = (const char *)v17;
        v18 = v17;
      }
      else
      {
        v18 = *(const WCHAR **)v17;
        v19 = *(const char **)v17;
      }
      v20 = SetPrinterDataExW(this[8], L"PrinterDriverData\\SaveAsExtensions", v18, 4u, (LPBYTE)&pData, 4u);
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0x496,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v20,
        (unsigned int)"Failed to set file extension %ws",
        v19,
        pData);
      if ( !v15 )
      {
        if ( *((_QWORD *)v17 + 3) <= 7u )
          v21 = (const char *)v17;
        else
          v21 = *(const char **)v17;
        if ( *((_QWORD *)v17 + 3) <= 7u )
          v22 = (BYTE *)v17;
        else
          v22 = *(BYTE **)v17;
        v23 = SetPrinterDataW(this[8], (LPWSTR)L"DefaultSaveAsExtension", 1u, v22, 2 * *((_DWORD *)v17 + 4) + 2);
        wil::details::in1diag3::Throw_IfWin32ErrorMsg(
          retaddr,
          (void *)0x49F,
          (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
          (const char *)v23,
          (unsigned int)"Failed to set default file extension %ws",
          v21);
        v15 = 1;
      }
      v17 += 16;
    }
    while ( v17 != v16 );
    v16 = pValueName[1];
    v17 = pValueName[0];
  }
  *(_DWORD *)v27 = (((char *)v16 - (char *)v17) & 0xFFFFFFFFFFFFFFE0uLL) != 0;
  v24 = SetPrinterDataW(this[8], (LPWSTR)L"VirtualPrinterIsFilePrinter", 4u, v27, 4u);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x4AA,
    (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
    (const char *)v24,
    (unsigned int)"Failed to set virtual printer is file printer value",
    cbData);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>((__int64 *)v72);
  std::vector<std::wstring>::_Tidy((__int64)pValueName);
  std::wstring::~wstring((char **)&v75);
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x18004403c  push    rbp
0x18004403e  push    rbx
0x18004403f  push    rsi
0x180044040  push    rdi
0x180044041  push    r12
0x180044043  push    r13
0x180044045  push    r14
0x180044047  push    r15
0x180044049  lea     rbp, [rsp-198h]
0x180044051  sub     rsp, 298h
0x180044058  mov     [rbp+1D0h+var_190], 0FFFFFFFFFFFFFFFEh
0x180044060  mov     rax, cs:__security_cookie
0x180044067  xor     rax, rsp
0x18004406a  mov     [rbp+1D0h+var_48], rax
0x180044071  mov     r13, rcx
0x180044074  xor     r12d, r12d
0x180044077  mov     [rsp+2D0h+pv], r12
0x18004407c  lea     rax, [rsp+2D0h+var_2A0]
0x180044081  mov     qword ptr [rsp+2D0h+cbData], rax; unsigned int *
0x180044086  lea     rax, [rsp+2D0h+pv]
0x18004408b  mov     [rsp+2D0h+pData], rax; unsigned __int8 **
0x180044090  lea     r15d, [r12+4]
0x180044095  mov     r9d, r15d; unsigned int
0x180044098  xor     r8d, r8d; unsigned __int16 *
0x18004409b  lea     rdx, aPrinterVirtual_2; "\\Printer.VirtualPrinter:FileExtensions"
0x1800440a2  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x1800440a7  mov     r14, [rsp+2D0h+pv]
0x1800440ac  xorps   xmm0, xmm0
0x1800440af  movups  [rbp+1D0h+var_68], xmm0
0x1800440b6  mov     [rbp+1D0h+var_58], r12
0x1800440bd  mov     [rbp+1D0h+var_50], r12
0x1800440c4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800440c8  mov     r8, rsi
0x1800440cb  inc     r8
0x1800440ce  cmp     [r14+r8*2], r12w
0x1800440d3  jnz     short loc_1800440CB
0x1800440d5  mov     rdx, r14
0x1800440d8  lea     rcx, [rbp+1D0h+var_68]
0x1800440df  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800440e4  nop
0x1800440e5  xorps   xmm0, xmm0
0x1800440e8  movdqu  xmmword ptr [rsp+2D0h+pValueName], xmm0
0x1800440ee  mov     [rsp+2D0h+var_270], r12
0x1800440f3  lea     rdx, asc_1801F049C; ";"
0x1800440fa  lea     rcx, [rbp+1D0h+var_B0]
0x180044101  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x180044106  nop
0x180044107  lea     rcx, [rbp+1D0h+var_68]
0x18004410e  cmp     [rbp+1D0h+var_50], 7
0x180044116  cmova   rcx, qword ptr [rbp+1D0h+var_68]
0x18004411e  mov     rax, [rbp+1D0h+var_58]
0x180044125  lea     rbx, [rcx+rax*2]
0x180044129  lea     rdi, [rbp+1D0h+var_68]
0x180044130  cmova   rdi, qword ptr [rbp+1D0h+var_68]
0x180044138  mov     dword ptr [rsp+2D0h+var_2A0], esi
0x18004413c  lea     rax, [rsp+2D0h+var_260]
0x180044141  mov     qword ptr [rsp+2D0h+var_290], rax
0x180044146  mov     [rsp+2D0h+var_260], rdi
0x18004414b  mov     [rsp+2D0h+var_258], rbx
0x180044150  lea     rax, [rbp+1D0h+var_B0]
0x180044157  mov     [rbp+1D0h+var_250], rax
0x18004415b  mov     [rbp+1D0h+var_248], r12d
0x18004415f  mov     [rbp+1D0h+var_240], r12
0x180044163  mov     [rbp+1D0h+var_238], r12b
0x180044167  xorps   xmm0, xmm0
0x18004416a  movdqa  [rbp+1D0h+var_230], xmm0
0x18004416f  xorps   xmm1, xmm1
0x180044172  movdqa  [rbp+1D0h+var_220], xmm1
0x180044177  mov     [rbp+1D0h+var_210], r12
0x18004417b  mov     [rbp+1D0h+var_208], r12b
0x18004417f  movdqa  [rbp+1D0h+var_200], xmm0
0x180044184  mov     [rbp+1D0h+var_1F0], r12b
0x180044188  mov     [rbp+1D0h+var_1E8], r12
0x18004418c  mov     [rbp+1D0h+var_1E0], r12
0x180044190  mov     [rbp+1D0h+var_1D8], r12b
0x180044194  mov     qword ptr [rsp+2D0h+cbData], rdi
0x180044199  mov     dword ptr [rsp+2D0h+pData], r12d
0x18004419e  lea     r9, [rbp+1D0h+var_B0]
0x1800441a5  lea     r8, [rbp+1D0h+var_240]
0x1800441a9  mov     rdx, rbx
0x1800441ac  mov     rcx, rdi
0x1800441af  call    ??$_Regex_search2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@GV?$regex_traits@G@2@V12@@std@@YA_NV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@0PEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@0@Z; std::_Regex_search2<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>,ushort,std::regex_traits<ushort>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x1800441b4  test    al, al
0x1800441b6  jnz     short loc_1800441BC
0x1800441b8  mov     [rbp+1D0h+var_250], r12
0x1800441bc  xorps   xmm0, xmm0
0x1800441bf  movdqa  [rbp+1D0h+var_1D0], xmm0
0x1800441c4  mov     [rbp+1D0h+var_1C0], r12
0x1800441c8  mov     [rbp+1D0h+var_1B8], r12b
0x1800441cc  mov     [rbp+1D0h+var_1B0], r12
0x1800441d0  mov     [rbp+1D0h+var_1A8], r12
0x1800441d4  movdqa  [rbp+1D0h+var_1A0], xmm0
0x1800441d9  mov     rcx, r15; Size
0x1800441dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800441e1  mov     [rbp+1D0h+var_1A8], rax
0x1800441e5  lea     rdx, [rax+4]
0x1800441e9  mov     qword ptr [rbp+1D0h+var_1A0+8], rdx
0x1800441ed  mov     ecx, dword ptr [rsp+2D0h+var_2A0]
0x1800441f1  mov     [rax], ecx
0x1800441f3  mov     qword ptr [rbp+1D0h+var_1A0], rdx
0x1800441f7  mov     qword ptr [rsp+2D0h+var_290], r12
0x1800441fc  lea     rcx, [rsp+2D0h+var_290]
0x180044201  call    ??1?$_Tidy_guard@V?$vector@IV?$allocator@I@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uint>>::~_Tidy_guard<std::vector<uint>>(void)
0x180044206  cmp     [rbp+1D0h+var_250], r12
0x18004420a  jnz     short loc_18004423A
0x18004420c  or      r8d, 0FFFFFFFFh
0x180044210  mov     rdx, qword ptr [rbp+1D0h+var_1A0]
0x180044214  mov     rcx, [rbp+1D0h+var_1A8]
0x180044218  call    _anonymous_namespace____Finding___Find_impl__anonymous_namespace____Finding___Find_traits_4_0_unsigned_int_
0x18004421d  cmp     rax, qword ptr [rbp+1D0h+var_1A0]
0x180044221  jnz     short loc_180044228
0x180044223  mov     rcx, r12
0x180044226  jmp     short loc_180044283
0x180044228  mov     [rbp+1D0h+var_1B8], 1
0x18004422c  mov     qword ptr [rbp+1D0h+var_1D0+8], rdi
0x180044230  mov     [rbp+1D0h+var_1C0], rbx
0x180044234  lea     rcx, [rbp+1D0h+var_1D0+8]
0x180044238  jmp     short loc_180044283
0x18004423a  mov     rcx, [rbp+1D0h+var_1B0]
0x18004423e  mov     rax, [rbp+1D0h+var_1A8]
0x180044242  movsxd  rdx, dword ptr [rax+rcx*4]
0x180044246  cmp     edx, esi
0x180044248  jnz     short loc_180044250
0x18004424a  lea     rcx, [rbp+1D0h+var_220+8]
0x18004424e  jmp     short loc_180044283
0x180044250  mov     rcx, rdx
0x180044253  mov     rax, qword ptr [rbp+1D0h+var_230+8]
0x180044257  mov     rdx, qword ptr [rbp+1D0h+var_230]
0x18004425b  sub     rax, rdx
0x18004425e  sar     rax, 3
0x180044262  mov     r8, 0AAAAAAAAAAAAAAABh
0x18004426c  imul    rax, r8
0x180044270  cmp     rax, rcx
0x180044273  ja      short loc_18004427B
0x180044275  lea     rcx, [rbp+1D0h+var_1E8]
0x180044279  jmp     short loc_180044283
0x18004427b  lea     rax, [rcx+rcx*2]
0x18004427f  lea     rcx, [rdx+rax*8]
0x180044283  mov     qword ptr [rbp+1D0h+var_1D0], rcx
0x180044287  xorps   xmm0, xmm0
0x18004428a  movdqa  [rbp+1D0h+var_180], xmm0
0x18004428f  mov     [rbp+1D0h+var_170], r12
0x180044293  mov     [rbp+1D0h+var_168], r12d
0x180044297  mov     [rbp+1D0h+var_160], r12
0x18004429b  mov     [rbp+1D0h+var_158], r12b
0x18004429f  movdqa  [rbp+1D0h+var_150], xmm0
0x1800442a7  xorps   xmm1, xmm1
0x1800442aa  movdqa  [rbp+1D0h+var_140], xmm1
0x1800442b2  mov     [rbp+1D0h+var_130], r12
0x1800442b9  mov     [rbp+1D0h+var_128], r12b
0x1800442c0  movdqa  [rbp+1D0h+var_120], xmm0
0x1800442c8  mov     [rbp+1D0h+var_110], r12b
0x1800442cf  mov     [rbp+1D0h+var_108], r12
0x1800442d6  mov     [rbp+1D0h+var_100], r12
0x1800442dd  mov     [rbp+1D0h+var_F8], r12b
0x1800442e4  movdqa  [rbp+1D0h+var_F0], xmm0
0x1800442ec  mov     [rbp+1D0h+var_E0], r12
0x1800442f3  mov     [rbp+1D0h+var_D8], r12b
0x1800442fa  mov     [rbp+1D0h+var_D0], r12
0x180044301  mov     [rbp+1D0h+var_C8], r12
0x180044308  movdqa  [rbp+1D0h+var_C0], xmm0
0x180044310  test    rcx, rcx
0x180044313  jz      loc_18004441A
0x180044319  mov     dl, [rcx+10h]
0x18004431c  test    dl, dl
0x18004431e  jz      short loc_180044325
0x180044320  movups  xmm0, xmmword ptr [rcx]
0x180044323  jmp     short loc_180044328
0x180044325  xorps   xmm0, xmm0
0x180044328  movdqu  [rsp+2D0h+var_290], xmm0
0x18004432e  mov     rax, qword ptr [rsp+2D0h+var_290+8]
0x180044333  cmp     rax, qword ptr [rsp+2D0h+var_290]
0x180044338  jz      loc_180044407
0x18004433e  test    dl, dl
0x180044340  jz      short loc_180044347
0x180044342  movups  xmm0, xmmword ptr [rcx]
0x180044345  jmp     short loc_18004434A
0x180044347  xorps   xmm0, xmm0
0x18004434a  movdqu  [rsp+2D0h+var_290], xmm0
0x180044350  xorps   xmm0, xmm0
0x180044353  movups  [rbp+1D0h+var_88], xmm0
0x18004435a  mov     qword ptr [rbp+1D0h+var_78], r12
0x180044361  mov     qword ptr [rbp+1D0h+var_78+8], r12
0x180044368  mov     rdx, qword ptr [rsp+2D0h+var_290]
0x18004436d  mov     r8, qword ptr [rsp+2D0h+var_290+8]
0x180044372  cmp     rdx, r8
0x180044375  jnz     short loc_180044393
0x180044377  mov     qword ptr [rbp+1D0h+var_78], r12
0x18004437e  mov     qword ptr [rbp+1D0h+var_78+8], 7
0x180044389  mov     word ptr [rbp+1D0h+var_88], r12w
0x180044391  jmp     short loc_1800443A6
0x180044393  sub     r8, rdx
0x180044396  sar     r8, 1
0x180044399  lea     rcx, [rbp+1D0h+var_88]
0x1800443a0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800443a5  nop
0x1800443a6  mov     rdx, [rsp+2D0h+pValueName+8]
0x1800443ab  cmp     rdx, [rsp+2D0h+var_270]
0x1800443b0  jz      short loc_1800443E9
0x1800443b2  movups  xmm0, [rbp+1D0h+var_88]
0x1800443b9  movups  xmmword ptr [rdx], xmm0
0x1800443bc  movups  xmm1, [rbp+1D0h+var_78]
0x1800443c3  movups  xmmword ptr [rdx+10h], xmm1
0x1800443c7  mov     qword ptr [rbp+1D0h+var_78], r12
0x1800443ce  mov     qword ptr [rbp+1D0h+var_78+8], 7
0x1800443d9  mov     word ptr [rbp+1D0h+var_88], r12w
0x1800443e1  add     [rsp+2D0h+pValueName+8], 20h ; ' '
0x1800443e7  jmp     short loc_1800443FB
0x1800443e9  lea     r8, [rbp+1D0h+var_88]
0x1800443f0  lea     rcx, [rsp+2D0h+pValueName]
0x1800443f5  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800443fa  nop
0x1800443fb  lea     rcx, [rbp+1D0h+var_88]
0x180044402  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044407  lea     rcx, [rsp+2D0h+var_260]
0x18004440c  call    ??E?$regex_token_iterator@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@GV?$regex_traits@G@2@@std@@QEAAAEAV01@XZ; std::regex_token_iterator<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>>::operator++(void)
0x180044411  mov     rcx, qword ptr [rbp+1D0h+var_1D0]
0x180044415  jmp     loc_180044310
0x18004441a  lea     rcx, [rbp+1D0h+var_C8]
0x180044421  call    ??1?$vector@W4Type@DriverEventTransport@DataModel@Config@Driver@Print@@V?$allocator@W4Type@DriverEventTransport@DataModel@Config@Driver@Print@@@std@@@std@@QEAA@XZ; std::vector<Print::Driver::Config::DataModel::DriverEventTransport::Type>::~vector<Print::Driver::Config::DataModel::DriverEventTransport::Type>(void)
0x180044426  lea     rcx, [rbp+1D0h+var_150]
0x18004442d  call    ??1?$vector@V?$sub_match@PEBG@std@@V?$allocator@V?$sub_match@PEBG@std@@@2@@std@@QEAA@XZ; std::vector<std::sub_match<ushort const *>>::~vector<std::sub_match<ushort const *>>(void)
0x180044432  nop
0x180044433  lea     rcx, [rbp+1D0h+var_1A8]
0x180044437  call    ??1?$vector@W4Type@DriverEventTransport@DataModel@Config@Driver@Print@@V?$allocator@W4Type@DriverEventTransport@DataModel@Config@Driver@Print@@@std@@@std@@QEAA@XZ; std::vector<Print::Driver::Config::DataModel::DriverEventTransport::Type>::~vector<Print::Driver::Config::DataModel::DriverEventTransport::Type>(void)
0x18004443c  lea     rcx, [rbp+1D0h+var_230]
0x180044440  call    ??1?$vector@V?$sub_match@PEBG@std@@V?$allocator@V?$sub_match@PEBG@std@@@2@@std@@QEAA@XZ; std::vector<std::sub_match<ushort const *>>::~vector<std::sub_match<ushort const *>>(void)
0x180044445  mov     r15b, r12b
0x180044448  mov     rdi, [rsp+2D0h+pValueName+8]
0x18004444d  mov     rbx, [rsp+2D0h+pValueName]
0x180044452  cmp     rbx, rdi
0x180044455  jz      loc_18004455F
0x18004445b  mov     dword ptr [rsp+2D0h+var_2A0], r12d
0x180044460  cmp     qword ptr [rbx+18h], 7
0x180044465  jbe     short loc_18004446F
0x180044467  mov     r8, [rbx]
0x18004446a  mov     rsi, r8
0x18004446d  jmp     short loc_180044475
0x18004446f  mov     rsi, rbx
0x180044472  mov     r8, rbx; pValueName
0x180044475  mov     [rsp+2D0h+cbData], 4; cbData
0x18004447d  lea     rax, [rsp+2D0h+var_2A0]
0x180044482  mov     [rsp+2D0h+pData], rax; pData
0x180044487  mov     r9d, 4; Type
0x18004448d  lea     rdx, aPrinterdriverd_0; "PrinterDriverData\\SaveAsExtensions"
0x180044494  mov     rcx, [r13+40h]; hPrinter
0x180044498  call    cs:__imp_SetPrinterDataExW
0x18004449f  nop     dword ptr [rax+rax+00h]
0x1800444a4  mov     rcx, [rbp+1D8h]; this
0x1800444ab  mov     qword ptr [rsp+2D0h+cbData], rsi; char *
0x1800444b0  lea     rdx, aFailedToSetFil; "Failed to set file extension %ws"
0x1800444b7  mov     [rsp+2D0h+pData], rdx; unsigned int
0x1800444bc  mov     r9d, eax; char *
0x1800444bf  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x1800444c6  mov     edx, 496h; void *
0x1800444cb  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800444d0  test    r15b, r15b
0x1800444d3  jnz     short loc_180044548
0x1800444d5  cmp     qword ptr [rbx+18h], 7
0x1800444da  jbe     short loc_1800444E1
0x1800444dc  mov     rsi, [rbx]
0x1800444df  jmp     short loc_1800444E4
0x1800444e1  mov     rsi, rbx
0x1800444e4  mov     eax, [rbx+10h]
0x1800444e7  lea     eax, ds:2[rax*2]
0x1800444ee  jbe     short loc_1800444F5
0x1800444f0  mov     r9, [rbx]
0x1800444f3  jmp     short loc_1800444F8
0x1800444f5  mov     r9, rbx; pData
0x1800444f8  mov     dword ptr [rsp+2D0h+pData], eax; cbData
0x1800444fc  mov     r8d, 1; Type
0x180044502  lea     rdx, aDefaultsavease; "DefaultSaveAsExtension"
0x180044509  mov     rcx, [r13+40h]; hPrinter
0x18004450d  call    cs:__imp_SetPrinterDataW
0x180044514  nop     dword ptr [rax+rax+00h]
0x180044519  mov     rcx, [rbp+1D8h]; this
0x180044520  mov     qword ptr [rsp+2D0h+cbData], rsi; char *
0x180044525  lea     rdx, aFailedToSetDef; "Failed to set default file extension %w"...
0x18004452c  mov     [rsp+2D0h+pData], rdx; unsigned int
0x180044531  mov     r9d, eax; char *
0x180044534  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x18004453b  mov     edx, 49Fh; void *
0x180044540  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180044545  mov     r15b, 1
0x180044548  add     rbx, 20h ; ' '
0x18004454c  cmp     rbx, rdi
0x18004454f  jnz     loc_18004445B
0x180044555  mov     rdi, [rsp+2D0h+pValueName+8]
0x18004455a  mov     rbx, [rsp+2D0h+pValueName]
0x18004455f  sub     rdi, rbx
0x180044562  test    rdi, 0FFFFFFFFFFFFFFE0h
0x180044569  mov     eax, r12d
0x18004456c  setnz   al
0x18004456f  mov     dword ptr [rsp+2D0h+var_298], eax
0x180044573  mov     dword ptr [rsp+2D0h+pData], 4; cbData
0x18004457b  lea     r9, [rsp+2D0h+var_298]; pData
0x180044580  mov     r8d, 4; Type
0x180044586  lea     rdx, aVirtualprinter_5; "VirtualPrinterIsFilePrinter"
0x18004458d  mov     rcx, [r13+40h]; hPrinter
0x180044591  call    cs:__imp_SetPrinterDataW
  ... truncated ...
```
