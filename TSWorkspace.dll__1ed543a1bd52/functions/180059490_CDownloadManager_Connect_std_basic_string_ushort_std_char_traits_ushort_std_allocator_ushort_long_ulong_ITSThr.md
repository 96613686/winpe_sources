# CDownloadManager::Connect(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,long,ulong,ITSThread *,HWND__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,int,ulong)

- ea: `0x180059490`
- end: `0x180059a88`
- name: `?Connect@CDownloadManager@@UEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JKPEAVITSThread@@PEAUHWND__@@0HK@Z`
- size: `1528`
- prototype: `void __fastcall(__int64, __int64, int, int, __int64, __int64, __int64, int, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800034b8`
- `0x18000b1d8`
- `0x18000c3d0`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000feb4`
- `0x18001e974`
- `0x18004c7a8`
- `0x18004f09c`
- `0x180059490`
- `0x18006ca18`
- `0x1800794ac`
- `0x1800a3010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180059a68`
- `msvcrt!??3@YAXPEAX@Z` at `0x180059a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800596fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800597cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800599cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800596fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800597cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800599cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a08`
- `WINHTTP!WinHttpOpen` at `0x1800596ea`
- `WINHTTP!WinHttpOpen` at `0x1800596ea`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800597c1`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800597c1`
- `WINHTTP!WinHttpSetTimeouts` at `0x180059886`
- `WINHTTP!WinHttpSetTimeouts` at `0x180059886`

## string_xrefs

- `0x180059632`: `URLCompareScheme failed`
- `0x1800596a9`: `UpdateDownloadPaths failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=22 #try_helpers=2
void __fastcall CDownloadManager::Connect(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        unsigned int a9)
{
  _QWORD *v12; // r14
  __int64 v13; // r12
  __int64 v14; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const WCHAR *v16; // rax
  const unsigned __int16 *v17; // rdx
  signed int LastError; // ebx
  unsigned int v19; // eax
  unsigned int v20; // eax
  HINTERNET v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  const unsigned __int16 *v28; // rbx
  const unsigned __int16 *v29; // rax
  signed int v30; // eax
  unsigned int v31; // ebx
  unsigned int v32; // eax
  signed int v33; // eax
  void (*dwFlags)(unsigned __int64, void *, struct _WINHTTP_PROXY_INFO *, int); // [rsp+20h] [rbp-58h]
  unsigned __int64 v35; // [rsp+28h] [rbp-50h]

  v12 = 0;
  v13 = a1 + 152;
  std::wstring::operator=(a1 + 152, a2);
  std::wstring::operator=(a1 + 184, a2);
  if ( a5 != *(_QWORD *)(a1 + 136) )
  {
    TCntPtr<ITSThread>::SafeRelease(a1 + 136);
    *(_QWORD *)(a1 + 136) = a5;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(a1 + 136);
  }
  *(_DWORD *)(a1 + 144) = a8;
  *(_QWORD *)(a1 + 128) = a6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
      CurrentThreadActivityIdPrefix,
      v14,
      a8);
  }
  *(_DWORD *)(a1 + 2056) = a3;
  *(_DWORD *)(a1 + 2060) = a4;
  *(_DWORD *)(a1 + 2016) = a9;
  if ( a9 >= 3 )
    *(_DWORD *)(a1 + 2016) = 2;
  std::wstring::operator=(a1 + 1984, a7);
  if ( *(_QWORD *)(a7 + 16) )
    *(_DWORD *)(a1 + 424) = 1;
  v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  LastError = URLCompareScheme(v16, v17, (int *)(a1 + 2020));
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v35) = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v19,
        (__int64)"URLCompareScheme failed",
        v35,
        LastError,
        0,
        -2);
    }
    goto LABEL_71;
  }
  LastError = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, a2, a2, 0);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v35) = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v20,
        (__int64)"UpdateDownloadPaths failed",
        v35,
        LastError,
        0,
        -2);
    }
    goto LABEL_71;
  }
  v21 = WinHttpOpen(L"TSWorkspace/2.0", 1u, 0, 0, 0x10000000u);
  *(_QWORD *)(a1 + 384) = v21;
  if ( !v21 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v22,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_71;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v23 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v23);
  }
  if ( WinHttpSetStatusCallback(*(HINTERNET *)(a1 + 384), CDownloadManager::WinHttpCallbackFn, 0x97F4C00u, 0) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v24,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_71;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v25 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v25);
  }
  if ( !WinHttpSetTimeouts(*(HINTERNET *)(a1 + 384), 0, 180000, 180000, 300000) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v26,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_71;
  }
  v12 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v12 )
  {
    *v12 = g_dwDMObjectContext;
    v12[1] = a1;
    v28 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 184);
    v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 320);
    if ( TSWWinHttpConnectAsync(*(void **)(a1 + 384), v29, v28, *(_WORD *)(a1 + 252), dwFlags, (unsigned __int64)v12) )
      return;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v30 = GetLastError();
      v31 = v30;
      if ( v30 > 0 )
        v31 = (unsigned __int16)v30 | 0x80070000;
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v32, v31);
    }
    v33 = GetLastError();
    LastError = v33;
    if ( v33 > 0 )
      LastError = (unsigned __int16)v33 | 0x80070000;
LABEL_71:
    if ( LastError >= 0 )
      return;
    goto LABEL_72;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v27 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
      v27,
      -2147024882);
  }
  LastError = -2147024882;
LABEL_72:
  CConfigManager::OnConnected(*(CConfigManager **)(a1 + 120), LastError);
  if ( v12 )
    operator delete(v12);
}

```

## disassembly

```asm
0x180059490  mov     rax, rsp
0x180059493  mov     [rax+18h], r8d
0x180059497  mov     [rax+8], rcx
0x18005949b  push    rdi
0x18005949c  push    r12
0x18005949e  push    r13
0x1800594a0  push    r14
0x1800594a2  push    r15
0x1800594a4  sub     rsp, 50h
0x1800594a8  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1800594b0  mov     [rax+10h], rbx
0x1800594b4  mov     [rax+20h], rsi
0x1800594b8  mov     r13d, r9d
0x1800594bb  mov     r15, rdx
0x1800594be  mov     rdi, rcx
0x1800594c1  xor     r14d, r14d
0x1800594c4  mov     [rax-40h], r14
0x1800594c8  lea     r12, [rcx+98h]
0x1800594cf  mov     rcx, r12
0x1800594d2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800594d7  lea     rcx, [rdi+0B8h]
0x1800594de  mov     rdx, r15
0x1800594e1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800594e6  lea     rbx, [rdi+88h]
0x1800594ed  mov     rsi, [rsp+78h+arg_20]
0x1800594f5  cmp     rsi, [rbx]
0x1800594f8  jz      short loc_18005950D
0x1800594fa  mov     rcx, rbx
0x1800594fd  call    ?SafeRelease@?$TCntPtr@VITSThread@@@@AEAAXXZ; TCntPtr<ITSThread>::SafeRelease(void)
0x180059502  mov     [rbx], rsi
0x180059505  mov     rcx, rbx
0x180059508  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18005950d  mov     esi, [rsp+78h+arg_38]
0x180059514  mov     [rdi+90h], esi
0x18005951a  mov     rax, [rsp+78h+arg_28]
0x180059522  mov     [rdi+80h], rax
0x180059529  lea     rcx, WPP_GLOBAL_Control
0x180059530  mov     rax, cs:WPP_GLOBAL_Control
0x180059537  cmp     rax, rcx
0x18005953a  jz      short loc_180059585
0x18005953c  test    byte ptr [rax+1Ch], 1
0x180059540  jz      short loc_180059585
0x180059542  cmp     byte ptr [rax+19h], 4
0x180059546  jb      short loc_180059585
0x180059548  mov     rcx, r15
0x18005954b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180059550  mov     rbx, rax
0x180059553  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180059558  mov     edx, 0Fh
0x18005955d  mov     dword ptr [rsp+78h+var_50], esi
0x180059561  mov     qword ptr [rsp+78h+dwFlags], rbx
0x180059566  mov     r9d, eax
0x180059569  lea     rsi, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x180059570  mov     r8, rsi
0x180059573  mov     rcx, cs:WPP_GLOBAL_Control
0x18005957a  mov     rcx, [rcx+10h]
0x18005957e  call    WPP_SF_DSD
0x180059583  jmp     short loc_18005958C
0x180059585  lea     rsi, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005958c  mov     eax, [rsp+78h+arg_10]
0x180059593  mov     [rdi+808h], eax
0x180059599  mov     [rdi+80Ch], r13d
0x1800595a0  mov     eax, [rsp+78h+arg_40]
0x1800595a7  mov     [rdi+7E0h], eax
0x1800595ad  cmp     eax, 3
0x1800595b0  jb      short loc_1800595BC
0x1800595b2  mov     dword ptr [rdi+7E0h], 2
0x1800595bc  lea     rcx, [rdi+7C0h]
0x1800595c3  mov     rbx, [rsp+78h+arg_30]
0x1800595cb  mov     rdx, rbx
0x1800595ce  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800595d3  cmp     qword ptr [rbx+10h], 0
0x1800595d8  jbe     short loc_1800595E4
0x1800595da  mov     dword ptr [rdi+1A8h], 1
0x1800595e4  mov     rcx, r12
0x1800595e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800595ec  lea     r8, [rdi+7E4h]; int *
0x1800595f3  mov     rcx, rax; lpszUrl
0x1800595f6  call    ?URLCompareScheme@@YAJPEBG0PEAH@Z; URLCompareScheme(ushort const *,ushort const *,int *)
0x1800595fb  mov     ebx, eax
0x1800595fd  mov     [rsp+78h+var_48], eax
0x180059601  test    eax, eax
0x180059603  jns     short loc_18005965A
0x180059605  mov     rax, cs:WPP_GLOBAL_Control
0x18005960c  lea     rcx, WPP_GLOBAL_Control
0x180059613  cmp     rax, rcx
0x180059616  jz      short loc_180059655
0x180059618  test    byte ptr [rax+1Ch], 8
0x18005961c  jz      short loc_180059655
0x18005961e  cmp     byte ptr [rax+19h], 2
0x180059622  jb      short loc_180059655
0x180059624  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180059629  mov     edx, 10h
0x18005962e  mov     dword ptr [rsp+78h+var_50], ebx
0x180059632  lea     rcx, aUrlcomparesche; "URLCompareScheme failed"
0x180059639  mov     qword ptr [rsp+78h+dwFlags], rcx
0x18005963e  mov     r9d, eax
0x180059641  mov     r8, rsi
0x180059644  mov     rcx, cs:WPP_GLOBAL_Control
0x18005964b  mov     rcx, [rcx+10h]
0x18005964f  call    WPP_SF_DsD
0x180059654  nop
0x180059655  jmp     loc_180059A51
0x18005965a  mov     rax, [rdi]
0x18005965d  xor     r9d, r9d
0x180059660  mov     r8, r15
0x180059663  mov     rdx, r15
0x180059666  mov     rcx, rdi
0x180059669  mov     rax, [rax+48h]
0x18005966d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059672  mov     ebx, eax
0x180059674  mov     [rsp+78h+var_48], eax
0x180059678  test    eax, eax
0x18005967a  jns     short loc_1800596D1
0x18005967c  mov     rax, cs:WPP_GLOBAL_Control
0x180059683  lea     rcx, WPP_GLOBAL_Control
0x18005968a  cmp     rax, rcx
0x18005968d  jz      short loc_1800596CC
0x18005968f  test    byte ptr [rax+1Ch], 8
0x180059693  jz      short loc_1800596CC
0x180059695  cmp     byte ptr [rax+19h], 2
0x180059699  jb      short loc_1800596CC
0x18005969b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800596a0  mov     edx, 11h
0x1800596a5  mov     dword ptr [rsp+78h+var_50], ebx
0x1800596a9  lea     rcx, aUpdatedownload; "UpdateDownloadPaths failed"
0x1800596b0  mov     qword ptr [rsp+78h+dwFlags], rcx
0x1800596b5  mov     r9d, eax
0x1800596b8  mov     r8, rsi
0x1800596bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800596c2  mov     rcx, [rcx+10h]
0x1800596c6  call    WPP_SF_DsD
0x1800596cb  nop
0x1800596cc  jmp     loc_180059A51
0x1800596d1  mov     [rsp+78h+dwFlags], 10000000h; dwFlags
0x1800596d9  xor     r9d, r9d; pszProxyBypassW
0x1800596dc  xor     r8d, r8d; pszProxyW
0x1800596df  lea     edx, [r9+1]; dwAccessType
0x1800596e3  lea     rcx, pszAgentW; "TSWorkspace/2.0"
0x1800596ea  call    cs:__imp_WinHttpOpen
0x1800596f0  mov     [rdi+180h], rax
0x1800596f7  test    rax, rax
0x1800596fa  jnz     short loc_18005976B
0x1800596fc  call    cs:__imp_GetLastError
0x180059702  mov     ebx, eax
0x180059704  mov     rax, cs:WPP_GLOBAL_Control
0x18005970b  lea     rcx, WPP_GLOBAL_Control
0x180059712  cmp     rax, rcx
0x180059715  jz      short loc_180059747
0x180059717  test    byte ptr [rax+1Ch], 8
0x18005971b  jz      short loc_180059747
0x18005971d  cmp     byte ptr [rax+19h], 2
0x180059721  jb      short loc_180059747
0x180059723  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180059728  mov     edx, 12h
0x18005972d  mov     [rsp+78h+dwFlags], ebx
0x180059731  mov     r9d, eax
0x180059734  mov     r8, rsi
0x180059737  mov     rcx, cs:WPP_GLOBAL_Control
0x18005973e  mov     rcx, [rcx+10h]
0x180059742  call    WPP_SF_Dd
0x180059747  test    ebx, ebx
0x180059749  jle     short loc_180059754
0x18005974b  movzx   ebx, bx
0x18005974e  or      ebx, 80070000h
0x180059754  mov     [rsp+78h+var_48], ebx
0x180059758  mov     eax, 80004005h
0x18005975d  test    ebx, ebx
0x18005975f  cmovns  ebx, eax
0x180059762  mov     [rsp+78h+var_48], ebx
0x180059766  jmp     loc_180059A51
0x18005976b  mov     rax, cs:WPP_GLOBAL_Control
0x180059772  lea     r15, WPP_GLOBAL_Control
0x180059779  cmp     rax, r15
0x18005977c  jz      short loc_1800597AA
0x18005977e  test    byte ptr [rax+1Ch], 1
0x180059782  jz      short loc_1800597AA
0x180059784  cmp     byte ptr [rax+19h], 4
0x180059788  jb      short loc_1800597AA
0x18005978a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005978f  mov     edx, 13h
0x180059794  mov     r9d, eax
0x180059797  mov     r8, rsi
0x18005979a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800597a1  mov     rcx, [rcx+10h]
0x1800597a5  call    WPP_SF_D
0x1800597aa  xor     r9d, r9d; dwReserved
0x1800597ad  mov     r8d, 97F4C00h; dwNotificationFlags
0x1800597b3  lea     rdx, ?WinHttpCallbackFn@CDownloadManager@@KAXPEAX_KK0K@Z; lpfnInternetCallback
0x1800597ba  mov     rcx, [rdi+180h]; hInternet
0x1800597c1  call    cs:__imp_WinHttpSetStatusCallback
0x1800597c7  test    rax, rax
0x1800597ca  jz      short loc_180059834
0x1800597cc  call    cs:__imp_GetLastError
0x1800597d2  mov     ebx, eax
0x1800597d4  mov     rax, cs:WPP_GLOBAL_Control
0x1800597db  cmp     rax, r15
0x1800597de  jz      short loc_180059810
0x1800597e0  test    byte ptr [rax+1Ch], 8
0x1800597e4  jz      short loc_180059810
0x1800597e6  cmp     byte ptr [rax+19h], 2
0x1800597ea  jb      short loc_180059810
0x1800597ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800597f1  mov     edx, 14h
0x1800597f6  mov     [rsp+78h+dwFlags], ebx
0x1800597fa  mov     r9d, eax
0x1800597fd  mov     r8, rsi
0x180059800  mov     rcx, cs:WPP_GLOBAL_Control
0x180059807  mov     rcx, [rcx+10h]
0x18005980b  call    WPP_SF_Dd
0x180059810  test    ebx, ebx
0x180059812  jle     short loc_18005981D
0x180059814  movzx   ebx, bx
0x180059817  or      ebx, 80070000h
0x18005981d  mov     [rsp+78h+var_48], ebx
0x180059821  mov     eax, 80004005h
0x180059826  test    ebx, ebx
0x180059828  cmovns  ebx, eax
0x18005982b  mov     [rsp+78h+var_48], ebx
0x18005982f  jmp     loc_180059A51
0x180059834  mov     rax, cs:WPP_GLOBAL_Control
0x18005983b  cmp     rax, r15
0x18005983e  jz      short loc_18005986C
0x180059840  test    byte ptr [rax+1Ch], 1
0x180059844  jz      short loc_18005986C
0x180059846  cmp     byte ptr [rax+19h], 4
0x18005984a  jb      short loc_18005986C
0x18005984c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180059851  mov     edx, 15h
0x180059856  mov     r9d, eax
0x180059859  mov     r8, rsi
0x18005985c  mov     rcx, cs:WPP_GLOBAL_Control
0x180059863  mov     rcx, [rcx+10h]
0x180059867  call    WPP_SF_D
0x18005986c  mov     [rsp+78h+dwFlags], 493E0h; void (*)(unsigned __int64, void *, struct _WINHTTP_PROXY_INFO *, int)
0x180059874  mov     r8d, 2BF20h; nConnectTimeout
0x18005987a  mov     r9d, r8d; nSendTimeout
0x18005987d  xor     edx, edx; nResolveTimeout
0x18005987f  mov     rcx, [rdi+180h]; hInternet
0x180059886  call    cs:__imp_WinHttpSetTimeouts
0x18005988c  test    eax, eax
0x18005988e  jnz     short loc_1800598F8
0x180059890  call    cs:__imp_GetLastError
0x180059896  mov     ebx, eax
0x180059898  mov     rax, cs:WPP_GLOBAL_Control
0x18005989f  cmp     rax, r15
0x1800598a2  jz      short loc_1800598D4
0x1800598a4  test    byte ptr [rax+1Ch], 8
0x1800598a8  jz      short loc_1800598D4
0x1800598aa  cmp     byte ptr [rax+19h], 2
0x1800598ae  jb      short loc_1800598D4
0x1800598b0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800598b5  mov     edx, 16h
0x1800598ba  mov     [rsp+78h+dwFlags], ebx
0x1800598be  mov     r9d, eax
0x1800598c1  mov     r8, rsi
0x1800598c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800598cb  mov     rcx, [rcx+10h]
0x1800598cf  call    WPP_SF_Dd
0x1800598d4  test    ebx, ebx
0x1800598d6  jle     short loc_1800598E1
0x1800598d8  movzx   ebx, bx
0x1800598db  or      ebx, 80070000h
0x1800598e1  mov     [rsp+78h+var_48], ebx
0x1800598e5  mov     eax, 80004005h
0x1800598ea  test    ebx, ebx
0x1800598ec  cmovns  ebx, eax
0x1800598ef  mov     [rsp+78h+var_48], ebx
0x1800598f3  jmp     loc_180059A51
0x1800598f8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800598ff  mov     ecx, 10h; unsigned __int64
0x180059904  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180059909  mov     r14, rax
0x18005990c  mov     [rsp+78h+var_40], rax
0x180059911  test    rax, rax
0x180059914  jnz     short loc_180059963
0x180059916  mov     rax, cs:WPP_GLOBAL_Control
0x18005991d  cmp     rax, r15
0x180059920  jz      short loc_180059955
0x180059922  test    byte ptr [rax+1Ch], 8
0x180059926  jz      short loc_180059955
0x180059928  cmp     byte ptr [rax+19h], 2
0x18005992c  jb      short loc_180059955
0x18005992e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180059933  lea     edx, [r14+17h]
0x180059937  mov     [rsp+78h+dwFlags], 8007000Eh
0x18005993f  mov     r9d, eax
0x180059942  mov     r8, rsi
0x180059945  mov     rcx, cs:WPP_GLOBAL_Control
0x18005994c  mov     rcx, [rcx+10h]
0x180059950  call    WPP_SF_Dd
0x180059955  mov     ebx, 8007000Eh
0x18005995a  mov     [rsp+78h+var_48], ebx
0x18005995e  jmp     loc_180059A55
0x180059963  mov     eax, cs:?g_dwDMObjectContext@@3KA; ulong g_dwDMObjectContext
0x180059969  mov     [r14], eax
0x18005996c  mov     dword ptr [r14+4], 0
0x180059974  mov     [r14+8], rdi
0x180059978  lea     rcx, [rdi+0B8h]
0x18005997f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
  ... truncated ...
```
