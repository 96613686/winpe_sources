# IDownloader::GetMetaDataFromUrl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong &,bool &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool)

- ea: `0x180014110`
- end: `0x1800145d5`
- name: `?GetMetaDataFromUrl@IDownloader@@UEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEAV23@AEAKAEA_N22_N@Z`
- size: `1221`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x180006998`
- `0x1800070a4`
- `0x180009e20`
- `0x180009fb0`
- `0x18000a3c0`
- `0x180011098`
- `0x1800130d0`
- `0x180013138`
- `0x18001316c`
- `0x180014110`
- `0x180014c90`
- `0x18001f420`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800143bf`
- `msvcrt!_wcsnicmp` at `0x18001441e`
- `msvcrt!_wcsnicmp` at `0x1800143bf`
- `msvcrt!_wcsnicmp` at `0x18001441e`
- `msvcrt!wcstol` at `0x180014539`
- `msvcrt!wcstol` at `0x180014539`
- `ole32!CoCreateGuid` at `0x18001425b`
- `ole32!CoCreateGuid` at `0x18001425b`
- `ole32!StringFromGUID2` at `0x180014275`
- `ole32!StringFromGUID2` at `0x180014275`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18001418e`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18001418e`
- `SHELL32!SHCreateDirectoryExW` at `0x1800141e0`
- `SHELL32!SHCreateDirectoryExW` at `0x1800141e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall IDownloader::GetMetaDataFromUrl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        int *a5,
        char *a6,
        __int64 a7,
        __int64 a8,
        char a9)
{
  __int64 v11; // r14
  unsigned int Error; // ebx
  const WCHAR *v13; // rdx
  int v14; // eax
  LPCWSTR *v15; // rdx
  LPCWSTR *v16; // r9
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  _BYTE *v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  const wchar_t *v33; // rcx
  int v34; // eax
  const wchar_t *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdx
  char v38; // al
  int v39; // ecx
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // rax
  __int64 v47; // r15
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // rax
  __int64 v56; // r15
  const wchar_t *v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rdx
  wchar_t *String1[3]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v62; // [rsp+58h] [rbp-A8h]
  LPCWSTR v63[3]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v64; // [rsp+78h] [rbp-88h]
  _BYTE v65[32]; // [rsp+80h] [rbp-80h] BYREF
  GUID pguid; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v67[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v68[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v69[32]; // [rsp+F0h] [rbp-10h] BYREF
  OLECHAR sz[40]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR pszPath[264]; // [rsp+160h] [rbp+60h] BYREF

  v11 = a2;
  if ( a3 )
  {
    if ( !SHGetSpecialFolderPathW(0, pszPath, 28, 1) )
    {
      Error = ResultFromLastError();
      goto LABEL_35;
    }
    std::wstring::wstring(v63, pszPath);
    std::wstring::append(v63, L"\\mdm");
    v13 = (const WCHAR *)v63;
    if ( v64 >= 8 )
      v13 = v63[0];
    v14 = SHCreateDirectoryExW(0, v13, 0);
    if ( v14 && v14 != 183 )
    {
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v16 = v63;
        if ( v64 >= 8 )
          LODWORD(v16) = v63[0];
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_14cd5ff906c03b036d9c08ef2443ee7b_Traceguids,
          (_DWORD)v16,
          v14);
      }
      Error = -2147467259;
      goto LABEL_34;
    }
    pguid = 0;
    CoCreateGuid(&pguid);
    StringFromGUID2(&pguid, sz, 39);
    if ( a9 )
    {
      v17 = std::wstring::wstring(v65, sz);
      v18 = std::operator+<unsigned short>(v69, v63);
      v19 = std::operator+<unsigned short>(v68, v18, v17);
      v20 = std::operator+<unsigned short>(v67, v19, L".appxbundle");
      std::wstring::operator=(a8, v20);
      LOBYTE(v21) = 1;
      std::wstring::_Tidy(v67, v21, 0);
      LOBYTE(v22) = 1;
      std::wstring::_Tidy(v68, v22, 0);
      LOBYTE(v23) = 1;
      std::wstring::_Tidy(v69, v23, 0);
      v25 = v65;
    }
    else
    {
      v26 = std::wstring::wstring(v67, sz);
      v27 = std::operator+<unsigned short>(v68, v63);
      v28 = std::operator+<unsigned short>(v69, v27, v26);
      v29 = std::operator+<unsigned short>(v65, v28, L".appx");
      std::wstring::operator=(a8, v29);
      LOBYTE(v30) = 1;
      std::wstring::_Tidy(v65, v30, 0);
      LOBYTE(v31) = 1;
      std::wstring::_Tidy(v69, v31, 0);
      LOBYTE(v32) = 1;
      std::wstring::_Tidy(v68, v32, 0);
      v25 = v67;
    }
    LOBYTE(v24) = 1;
    std::wstring::_Tidy(v25, v24, 0);
    std::wstring::wstring(String1, a3);
    v33 = (const wchar_t *)String1;
    if ( v62 >= 8 )
      v33 = String1[0];
    v34 = _wcsnicmp(v33, L"http://", 7u);
    v35 = (const wchar_t *)String1;
    if ( v34 )
    {
      if ( v62 >= 8 )
        v35 = String1[0];
      if ( _wcsnicmp(v35, L"https://", 8u) )
        goto LABEL_32;
      v41 = std::wstring::substr(String1, v65, 8, -1);
      std::wstring::operator=(String1, v41);
      LOBYTE(v42) = 1;
      std::wstring::_Tidy(v65, v42, 0);
      v38 = 1;
      v39 = 443;
    }
    else
    {
      v36 = std::wstring::substr(String1, v65, 7, -1);
      std::wstring::operator=(String1, v36);
      LOBYTE(v37) = 1;
      std::wstring::_Tidy(v65, v37, 0);
      v38 = 0;
      v39 = 80;
    }
    *a5 = v39;
    *a6 = v38;
    v43 = std::char_traits<unsigned short>::length(L"/");
    v46 = std::wstring::find(String1, v44, v45, v43);
    v47 = v46;
    if ( v46 != -1 )
    {
      Error = 0;
      v48 = std::wstring::substr(String1, v65, 0, v46);
      std::wstring::operator=(a4, v48);
      LOBYTE(v49) = 1;
      std::wstring::_Tidy(v65, v49, 0);
      v50 = std::wstring::substr(String1, v65, v47 + 1, -1);
      std::wstring::operator=(a7, v50);
      LOBYTE(v51) = 1;
      std::wstring::_Tidy(v65, v51, 0);
      v52 = std::char_traits<unsigned short>::length(L":");
      v55 = std::wstring::find(a4, v53, v54, v52);
      v56 = v55;
      if ( v55 != -1 )
      {
        if ( *((_QWORD *)a4 + 3) < 8u )
          v57 = a4;
        else
          v57 = *(const wchar_t **)a4;
        *a5 = wcstol(&v57[v55 + 1], 0, 0);
        v58 = std::wstring::substr(a4, v65, 0, v56);
        std::wstring::operator=(a4, v58);
        LOBYTE(v59) = 1;
        std::wstring::_Tidy(v65, v59, 0);
      }
      goto LABEL_33;
    }
LABEL_32:
    Error = -2147024809;
LABEL_33:
    LOBYTE(v40) = 1;
    std::wstring::_Tidy(String1, v40, 0);
LABEL_34:
    LOBYTE(v15) = 1;
    std::wstring::_Tidy(v63, v15, 0);
    goto LABEL_35;
  }
  Error = -2147024809;
LABEL_35:
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(v11, a2, 0);
  return Error;
}

```

## disassembly

```asm
0x180014110  mov     [rsp-8+arg_0], rbx
0x180014115  push    rbp
0x180014116  push    rsi
0x180014117  push    rdi
0x180014118  push    r12
0x18001411a  push    r13
0x18001411c  push    r14
0x18001411e  push    r15
0x180014120  lea     rbp, [rsp-280h]
0x180014128  sub     rsp, 380h
0x18001412f  mov     rax, cs:__security_cookie
0x180014136  xor     rax, rsp
0x180014139  mov     [rbp+2B0h+var_40], rax
0x180014140  mov     rdi, r9
0x180014143  mov     rsi, r8
0x180014146  mov     r14, rdx
0x180014149  mov     [rsp+3B0h+var_378], rdx
0x18001414e  mov     r12, [rbp+2B0h+arg_20]
0x180014155  mov     r13, [rbp+2B0h+arg_28]
0x18001415c  mov     rax, [rbp+2B0h+arg_30]
0x180014163  mov     [rsp+3B0h+var_380], rax
0x180014168  mov     r15, [rbp+2B0h+arg_38]
0x18001416f  test    r8, r8
0x180014172  jnz     short loc_18001417E
0x180014174  mov     ebx, 80070057h
0x180014179  jmp     loc_18001459B
0x18001417e  mov     r9d, 1; fCreate
0x180014184  lea     r8d, [r9+1Bh]; csidl
0x180014188  lea     rdx, [rbp+2B0h+pszPath]; pszPath
0x18001418c  xor     ecx, ecx; hwnd
0x18001418e  call    cs:__imp_SHGetSpecialFolderPathW
0x180014195  nop     dword ptr [rax+rax+00h]
0x18001419a  test    eax, eax
0x18001419c  jnz     short loc_1800141AA
0x18001419e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800141a3  mov     ebx, eax
0x1800141a5  jmp     loc_18001459B
0x1800141aa  lea     rdx, [rbp+2B0h+pszPath]
0x1800141ae  lea     rcx, [rsp+3B0h+var_350]
0x1800141b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800141b8  nop
0x1800141b9  lea     rdx, aMdm; "\\mdm"
0x1800141c0  lea     rcx, [rsp+3B0h+var_350]
0x1800141c5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800141ca  lea     rdx, [rsp+3B0h+var_350]
0x1800141cf  cmp     [rsp+3B0h+var_338], 8
0x1800141d5  cmovnb  rdx, [rsp+3B0h+var_350]; pszPath
0x1800141db  xor     r8d, r8d; psa
0x1800141de  xor     ecx, ecx; hwnd
0x1800141e0  call    cs:__imp_SHCreateDirectoryExW
0x1800141e7  nop     dword ptr [rax+rax+00h]
0x1800141ec  test    eax, eax
0x1800141ee  jz      short loc_180014250
0x1800141f0  cmp     eax, 0B7h
0x1800141f5  jz      short loc_180014250
0x1800141f7  lea     rdx, WPP_GLOBAL_Control
0x1800141fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014205  cmp     rcx, rdx
0x180014208  jz      short loc_180014246
0x18001420a  test    byte ptr [rcx+1Ch], 4
0x18001420e  jz      short loc_180014246
0x180014210  test    eax, eax
0x180014212  jle     short loc_18001421C
0x180014214  movzx   eax, ax
0x180014217  or      eax, 80070000h
0x18001421c  lea     r9, [rsp+3B0h+var_350]
0x180014221  cmp     [rsp+3B0h+var_338], 8
0x180014227  cmovnb  r9, [rsp+3B0h+var_350]
0x18001422d  mov     edx, 0Bh
0x180014232  mov     [rsp+3B0h+var_390], eax
0x180014236  lea     r8, WPP_14cd5ff906c03b036d9c08ef2443ee7b_Traceguids
0x18001423d  mov     rcx, [rcx+10h]
0x180014241  call    WPP_SF_Sd
0x180014246  mov     ebx, 80004005h
0x18001424b  jmp     loc_18001458B
0x180014250  xorps   xmm0, xmm0
0x180014253  movups  xmmword ptr [rbp+2B0h+pguid.Data1], xmm0
0x180014257  lea     rcx, [rbp+2B0h+pguid]; pguid
0x18001425b  call    cs:__imp_CoCreateGuid
0x180014262  nop     dword ptr [rax+rax+00h]
0x180014267  mov     r8d, 27h ; '''; cchMax
0x18001426d  lea     rdx, [rbp+2B0h+sz]; lpsz
0x180014271  lea     rcx, [rbp+2B0h+pguid]; rguid
0x180014275  call    cs:__imp_StringFromGUID2
0x18001427c  nop     dword ptr [rax+rax+00h]
0x180014281  lea     rdx, [rbp+2B0h+sz]
0x180014285  cmp     [rbp+2B0h+arg_40], 0
0x18001428c  jz      short loc_18001430A
0x18001428e  lea     rcx, [rbp+2B0h+var_330]
0x180014292  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014297  mov     rbx, rax
0x18001429a  lea     rdx, [rsp+3B0h+var_350]
0x18001429f  lea     rcx, [rbp+2B0h+var_2C0]
0x1800142a3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x1800142a8  nop
0x1800142a9  mov     r8, rbx
0x1800142ac  mov     rdx, rax
0x1800142af  lea     rcx, [rbp+2B0h+var_2E0]
0x1800142b3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800142b8  nop
0x1800142b9  lea     r8, aAppxbundle; ".appxbundle"
0x1800142c0  mov     rdx, rax
0x1800142c3  lea     rcx, [rbp+2B0h+var_300]
0x1800142c7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x1800142cc  mov     rdx, rax
0x1800142cf  mov     rcx, r15
0x1800142d2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800142d7  xor     r8d, r8d
0x1800142da  mov     dl, 1
0x1800142dc  lea     rcx, [rbp+2B0h+var_300]
0x1800142e0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800142e5  nop
0x1800142e6  xor     r8d, r8d
0x1800142e9  mov     dl, 1
0x1800142eb  lea     rcx, [rbp+2B0h+var_2E0]
0x1800142ef  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800142f4  nop
0x1800142f5  xor     r8d, r8d
0x1800142f8  mov     dl, 1
0x1800142fa  lea     rcx, [rbp+2B0h+var_2C0]
0x1800142fe  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014303  nop
0x180014304  lea     rcx, [rbp+2B0h+var_330]
0x180014308  jmp     short loc_180014384
0x18001430a  lea     rcx, [rbp+2B0h+var_300]
0x18001430e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014313  mov     rbx, rax
0x180014316  lea     rdx, [rsp+3B0h+var_350]
0x18001431b  lea     rcx, [rbp+2B0h+var_2E0]
0x18001431f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x180014324  nop
0x180014325  mov     r8, rbx
0x180014328  mov     rdx, rax
0x18001432b  lea     rcx, [rbp+2B0h+var_2C0]
0x18001432f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180014334  nop
0x180014335  lea     r8, aAppx; ".appx"
0x18001433c  mov     rdx, rax
0x18001433f  lea     rcx, [rbp+2B0h+var_330]
0x180014343  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180014348  mov     rdx, rax
0x18001434b  mov     rcx, r15
0x18001434e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180014353  xor     r8d, r8d
0x180014356  mov     dl, 1
0x180014358  lea     rcx, [rbp+2B0h+var_330]
0x18001435c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014361  nop
0x180014362  xor     r8d, r8d
0x180014365  mov     dl, 1
0x180014367  lea     rcx, [rbp+2B0h+var_2C0]
0x18001436b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014370  nop
0x180014371  xor     r8d, r8d
0x180014374  mov     dl, 1
0x180014376  lea     rcx, [rbp+2B0h+var_2E0]
0x18001437a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001437f  nop
0x180014380  lea     rcx, [rbp+2B0h+var_300]
0x180014384  xor     r8d, r8d
0x180014387  mov     dl, 1
0x180014389  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001438e  mov     rdx, rsi
0x180014391  lea     rcx, [rsp+3B0h+String1]
0x180014396  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001439b  nop
0x18001439c  lea     rcx, [rsp+3B0h+String1]
0x1800143a1  mov     ebx, 8
0x1800143a6  cmp     [rsp+3B0h+var_358], rbx
0x1800143ab  cmovnb  rcx, [rsp+3B0h+String1]; String1
0x1800143b1  lea     r15d, [rbx-1]
0x1800143b5  mov     r8d, r15d; MaxCount
0x1800143b8  lea     rdx, aHttp; "http://"
0x1800143bf  call    cs:__imp__wcsnicmp
0x1800143c6  nop     dword ptr [rax+rax+00h]
0x1800143cb  lea     rcx, [rsp+3B0h+String1]
0x1800143d0  test    eax, eax
0x1800143d2  jnz     short loc_180014409
0x1800143d4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800143d8  mov     r9, rsi
0x1800143db  mov     r8d, r15d
0x1800143de  lea     rdx, [rbp+2B0h+var_330]
0x1800143e2  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800143e7  mov     rdx, rax
0x1800143ea  lea     rcx, [rsp+3B0h+String1]
0x1800143ef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800143f4  xor     r8d, r8d
0x1800143f7  mov     dl, 1
0x1800143f9  lea     rcx, [rbp+2B0h+var_330]
0x1800143fd  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014402  xor     al, al
0x180014404  lea     ecx, [rbx+48h]
0x180014407  jmp     short loc_18001446C
0x180014409  cmp     [rsp+3B0h+var_358], rbx
0x18001440e  cmovnb  rcx, [rsp+3B0h+String1]; String1
0x180014414  mov     r8, rbx; MaxCount
0x180014417  lea     rdx, aHttps; "https://"
0x18001441e  call    cs:__imp__wcsnicmp
0x180014425  nop     dword ptr [rax+rax+00h]
0x18001442a  test    eax, eax
0x18001442c  jnz     loc_180014576
0x180014432  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180014436  mov     r9, rsi
0x180014439  mov     r8, rbx
0x18001443c  lea     rdx, [rbp+2B0h+var_330]
0x180014440  lea     rcx, [rsp+3B0h+String1]
0x180014445  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18001444a  mov     rdx, rax
0x18001444d  lea     rcx, [rsp+3B0h+String1]
0x180014452  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180014457  xor     r8d, r8d
0x18001445a  mov     dl, 1
0x18001445c  lea     rcx, [rbp+2B0h+var_330]
0x180014460  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014465  mov     al, 1
0x180014467  mov     ecx, 1BBh
0x18001446c  mov     [r12], ecx
0x180014470  mov     [r13+0], al
0x180014474  lea     rcx, asc_180023710; "/"
0x18001447b  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180014480  mov     r9, rax
0x180014483  mov     rdx, rcx
0x180014486  lea     rcx, [rsp+3B0h+String1]
0x18001448b  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x180014490  mov     r15, rax
0x180014493  cmp     rax, rsi
0x180014496  jz      loc_180014576
0x18001449c  xor     ebx, ebx
0x18001449e  mov     r9, rax
0x1800144a1  xor     r8d, r8d
0x1800144a4  lea     rdx, [rbp+2B0h+var_330]
0x1800144a8  lea     rcx, [rsp+3B0h+String1]
0x1800144ad  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800144b2  mov     rdx, rax
0x1800144b5  mov     rcx, rdi
0x1800144b8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800144bd  xor     r8d, r8d
0x1800144c0  mov     dl, 1
0x1800144c2  lea     rcx, [rbp+2B0h+var_330]
0x1800144c6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800144cb  lea     r8, [r15+1]
0x1800144cf  mov     r9, rsi
0x1800144d2  lea     rdx, [rbp+2B0h+var_330]
0x1800144d6  lea     rcx, [rsp+3B0h+String1]
0x1800144db  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800144e0  mov     rdx, rax
0x1800144e3  mov     rcx, [rsp+3B0h+var_380]
0x1800144e8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800144ed  xor     r8d, r8d
0x1800144f0  mov     dl, 1
0x1800144f2  lea     rcx, [rbp+2B0h+var_330]
0x1800144f6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800144fb  lea     rcx, asc_180023C94; ":"
0x180014502  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180014507  mov     r9, rax
0x18001450a  mov     rdx, rcx
0x18001450d  mov     rcx, rdi
0x180014510  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x180014515  mov     r15, rax
0x180014518  cmp     rax, rsi
0x18001451b  jz      short loc_18001457B
0x18001451d  cmp     qword ptr [rdi+18h], 8
0x180014522  jb      short loc_180014529
0x180014524  mov     rcx, [rdi]
0x180014527  jmp     short loc_18001452C
0x180014529  mov     rcx, rdi
0x18001452c  lea     rcx, [rcx+rax*2]
0x180014530  add     rcx, 2; String
0x180014534  xor     r8d, r8d; Radix
0x180014537  xor     edx, edx; EndPtr
0x180014539  call    cs:__imp_wcstol
0x180014540  nop     dword ptr [rax+rax+00h]
0x180014545  mov     [r12], eax
0x180014549  mov     r9, r15
0x18001454c  xor     r8d, r8d
0x18001454f  lea     rdx, [rbp+2B0h+var_330]
0x180014553  mov     rcx, rdi
0x180014556  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18001455b  mov     rdx, rax
0x18001455e  mov     rcx, rdi
0x180014561  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180014566  xor     r8d, r8d
0x180014569  mov     dl, 1
0x18001456b  lea     rcx, [rbp+2B0h+var_330]
0x18001456f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014574  jmp     short loc_18001457B
0x180014576  mov     ebx, 80070057h
0x18001457b  xor     r8d, r8d
0x18001457e  mov     dl, 1
0x180014580  lea     rcx, [rsp+3B0h+String1]
0x180014585  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001458a  nop
0x18001458b  xor     r8d, r8d
0x18001458e  mov     dl, 1
0x180014590  lea     rcx, [rsp+3B0h+var_350]
0x180014595  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001459a  nop
0x18001459b  xor     r8d, r8d
0x18001459e  mov     dl, 1
0x1800145a0  mov     rcx, r14
  ... truncated ...
```
