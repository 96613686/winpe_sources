# FrameWindow::FrameWindow(IScriptHostFactory *,ulong,ulong,HWND__ *,HWND__ *,ushort const *,bool,LaunchMode,ushort const *)

- ea: `0x18001f024`
- end: `0x18001f9ec`
- name: `??0FrameWindow@@QEAA@PEAUIScriptHostFactory@@KKPEAUHWND__@@1PEBG_NW4LaunchMode@@2@Z`
- size: `2504`
- prototype: `__int64 __fastcall(__int64, __int64, DWORD, int, __int64, __int64, __int64, char, int, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016710`

## callees

- `0x180001800`
- `0x18000193c`
- `0x180002678`
- `0x180002684`
- `0x180002dd4`
- `0x180002ef4`
- `0x180003858`
- `0x180003880`
- `0x1800042a4`
- `0x1800045b4`
- `0x18001f024`
- `0x180021680`
- `0x18002c6c4`
- `0x18002ee90`
- `0x18002fac0`
- `0x18002fda4`
- `0x180032a50`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f5a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f5a2`
- `GDI32!GetDeviceCaps` at `0x18001f741`
- `GDI32!GetDeviceCaps` at `0x18001f741`
- `KERNEL32!EnterCriticalSection` at `0x18001f1b1`
- `KERNEL32!EnterCriticalSection` at `0x18001f1b1`
- `KERNEL32!LeaveCriticalSection` at `0x18001f1d8`
- `KERNEL32!LeaveCriticalSection` at `0x18001f1d8`
- `KERNEL32!GetProcAddress` at `0x18001f64b`
- `KERNEL32!GetProcAddress` at `0x18001f64b`
- `KERNEL32!LoadLibraryExW` at `0x18001f63b`
- `KERNEL32!LoadLibraryExW` at `0x18001f63b`
- `KERNEL32!OpenProcess` at `0x18001f46a`
- `KERNEL32!OpenProcess` at `0x18001f46a`
- `KERNEL32!K32EnumProcessModulesEx` at `0x18001f494`
- `KERNEL32!K32EnumProcessModulesEx` at `0x18001f494`
- `KERNEL32!K32GetModuleFileNameExW` at `0x18001f521`
- `KERNEL32!K32GetModuleFileNameExW` at `0x18001f521`
- `USER32!DefWindowProcW` at `0x18001f095`
- `USER32!DefWindowProcW` at `0x18001f0e1`
- `USER32!DefWindowProcW` at `0x18001f14e`
- `USER32!LoadCursorW` at `0x18001f1c7`
- `USER32!LoadCursorW` at `0x18001f1c7`
- `USER32!ReleaseDC` at `0x18001f764`
- `USER32!ReleaseDC` at `0x18001f764`
- `USER32!GetDC` at `0x18001f727`
- `USER32!GetDC` at `0x18001f727`
- `USER32!SetRectEmpty` at `0x18001f197`
- `USER32!SetRectEmpty` at `0x18001f197`
- `iertutil!__imp_GetValue` at `0x18001f91d`
- `iertutil!__imp_GetValue` at `0x18001f91d`

## string_xrefs

- `0x18001f401`: `F12\F12Platform.dll`
- `0x18001f41a`: `F12\F12Platform.dll`
- `0x18001f593`: `edgehtml.dll`
- `0x18001f61a`: `F12\F12Platform2.dll`
- `0x18001f641`: `CreatePlatform`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall FrameWindow::FrameWindow(
        __int64 a1,
        __int64 a2,
        DWORD a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        char a8,
        int a9,
        __int64 a10)
{
  char v13; // r14
  _QWORD *v14; // rbx
  struct ATL::CAtlModule *v15; // rdi
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // r13
  _QWORD *v19; // rax
  int v20; // eax
  DWORD v21; // ebx
  HANDLE v22; // rax
  void *v23; // rdi
  DWORD v24; // r13d
  DWORD v25; // r12d
  __int64 v26; // rax
  WCHAR *v27; // r15
  DWORD ModuleFileName; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rdi
  LPCWSTR v33; // rdi
  HMODULE Library; // rax
  FARPROC ProcAddress; // r12
  int v36; // eax
  __int64 v37; // r15
  __int64 *v38; // rax
  int v39; // eax
  HDC DC; // rax
  HDC v41; // r15
  double v42; // xmm2_8
  int v43; // eax
  enum PluginId *v44; // rdx
  _DWORD *i; // rax
  DWORD cbNeeded; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v48; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR *v49; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpLibFileName; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v51[4]; // [rsp+60h] [rbp-A0h] BYREF
  HMODULE hModule[1024]; // [rsp+80h] [rbp-80h] BYREF

  cbNeeded = a3;
  v51[2] = a1;
  v48 = (HANDLE)a7;
  v51[0] = a10;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = DefWindowProcW;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)a1 = &FrameWindow::`vftable'{for `WTL::CFrameWindowImpl<FrameWindow,ATL::CWindow,ATL::CWinTraits<0,262144>>'};
  *(_QWORD *)(a1 + 104) = &FrameWindow::`vftable'{for `WTL::CMessageFilter'};
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_DWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = DefWindowProcW;
  *(_QWORD *)(a1 + 144) = &CDragOverlayWindow::`vftable';
  *(_QWORD *)(a1 + 224) = 0;
  v13 = 1;
  *(_BYTE *)(a1 + 232) = 1;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  v14 = (_QWORD *)(a1 + 280);
  v49 = (WCHAR *)(a1 + 280);
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 320) = 0;
  *(_QWORD *)(a1 + 328) = 0;
  *(_DWORD *)(a1 + 336) = 0;
  *(_QWORD *)(a1 + 344) = DefWindowProcW;
  *(_QWORD *)(a1 + 384) = -1;
  *(_QWORD *)(a1 + 392) = 0;
  *(_DWORD *)(a1 + 400) = 0;
  *(_BYTE *)(a1 + 404) = 1;
  *(_QWORD *)(a1 + 408) = 0;
  *(_BYTE *)(a1 + 416) = 1;
  *(_DWORD *)(a1 + 420) = 1;
  *(_DWORD *)(a1 + 424) = -1;
  *(_OWORD *)(a1 + 352) = 0;
  SetRectEmpty((LPRECT)(a1 + 368));
  if ( !WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::m_hCursor )
  {
    v15 = ATL::_pAtlModule;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
    if ( !WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::m_hCursor )
      WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::m_hCursor = LoadCursorW(0, (LPCWSTR)0x7F85);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 24));
  }
  *v14 = &CF12SplitterWindowT<0>::`vftable';
  *(_DWORD *)(a1 + 432) = 0;
  *(_WORD *)(a1 + 437) = 0;
  *(_BYTE *)(a1 + 439) = 0;
  *(_BYTE *)(a1 + 440) = a9 == 1;
  *(_BYTE *)(a1 + 441) = 0;
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 456) = 0;
  v16 = operator new(0x38u);
  *v16 = v16;
  v16[1] = v16;
  v16[2] = v16;
  *((_WORD *)v16 + 12) = 257;
  *(_QWORD *)(a1 + 448) = v16;
  *(_QWORD *)(a1 + 464) = 0;
  *(_QWORD *)(a1 + 472) = 0;
  v17 = operator new(0x40u);
  *v17 = v17;
  v17[1] = v17;
  v17[2] = v17;
  *((_WORD *)v17 + 12) = 257;
  *(_QWORD *)(a1 + 464) = v17;
  *(_QWORD *)(a1 + 480) = 0;
  *(_QWORD *)(a1 + 488) = 0;
  *(_QWORD *)(a1 + 496) = 0;
  v18 = a1 + 504;
  *(_QWORD *)(a1 + 504) = 0;
  *(_QWORD *)(a1 + 512) = 0;
  *(_QWORD *)(a1 + 520) = 0;
  *(_QWORD *)(a1 + 528) = 0;
  *(_QWORD *)(a1 + 536) = 0;
  v19 = operator new(0x10u);
  v19[1] = 0;
  *(_QWORD *)(a1 + 504) = v19;
  *v19 = a1 + 504;
  *(_DWORD *)(a1 + 544) = -1;
  *(_DWORD *)(a1 + 548) = -1;
  *(_DWORD *)(a1 + 552) = -1;
  *(_DWORD *)(a1 + 556) = -1;
  *(_DWORD *)(a1 + 560) = a9;
  *(_QWORD *)(a1 + 568) = 0;
  *(_QWORD *)(a1 + 576) = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  *(_DWORD *)(a1 + 584) = cbNeeded;
  *(_DWORD *)(a1 + 588) = a4;
  *(_QWORD *)(a1 + 592) = a5;
  *(_QWORD *)(a1 + 600) = a6;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)(a1 + 608),
    (__int64)v48);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)(a1 + 616),
    v51[0]);
  *(_QWORD *)(a1 + 624) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_DWORD *)(a1 + 632) = 1;
  *(_DWORD *)(a1 + 636) = 2;
  *(_DWORD *)(a1 + 640) = 116;
  *(_DWORD *)(a1 + 644) = 22;
  *(_DWORD *)(a1 + 648) = 44;
  *(_DWORD *)(a1 + 652) = 400;
  *(_QWORD *)(a1 + 656) = 60;
  *(_BYTE *)(a1 + 672) = a8;
  *(_WORD *)(a1 + 673) = 0;
  *(_DWORD *)(a1 + 676) = 0;
  *(_BYTE *)(a1 + 689) = 0;
  *(_QWORD *)(a1 + 712) = 0;
  *(_QWORD *)(a1 + 720) = 0;
  lpLibFileName = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &lpLibFileName,
                           L"F12\\F12Platform.dll") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&lpLibFileName, L"F12\\F12Platform.dll", 19);
  v20 = *(_DWORD *)(a1 + 560);
  v21 = 3;
  if ( !v20 || v20 == 3 )
  {
    memset_0(hModule, 0, sizeof(hModule));
    cbNeeded = 0;
    v22 = OpenProcess(0x410u, 0, *(_DWORD *)(a1 + 584));
    v23 = v22;
    v48 = v22;
    if ( v22 && K32EnumProcessModulesEx(v22, hModule, 0x2000u, &cbNeeded, 3u) )
    {
      v24 = 0;
      if ( cbNeeded > 0x2000 )
      {
        v25 = 1024;
        goto LABEL_16;
      }
      v25 = cbNeeded >> 3;
      if ( cbNeeded >> 3 )
      {
        do
        {
LABEL_16:
          v26 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
          v27 = (WCHAR *)(v26 + 24);
          v49 = (WCHAR *)(v26 + 24);
          if ( ((*(_DWORD *)(v26 + 12) - 260) | (1 - *(_DWORD *)(v26 + 16))) < 0 )
          {
            ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v49);
            v27 = v49;
          }
          ModuleFileName = K32GetModuleFileNameExW(v23, hModule[v24], v27, 0x104u);
          if ( v27 )
          {
            v30 = -1;
            do
              ++v30;
            while ( v27[v30] );
            if ( (int)v30 < 0 )
LABEL_76:
              ATL::AtlThrowImpl(-2147024809);
          }
          else
          {
            LODWORD(v30) = 0;
          }
          if ( (int)v30 > *((_DWORD *)v27 - 3) )
            goto LABEL_76;
          *((_DWORD *)v27 - 4) = v30;
          v27[(unsigned int)v30] = 0;
          if ( ModuleFileName )
          {
            v51[0] = ((__int64 (__fastcall *)(void ***, __int64, _QWORD))ATL::g_strmgr[3])(&ATL::g_strmgr, v29, 0) + 24;
            LOBYTE(v31) = 1;
            Win32Helpers::GetNameFromPath(v27, v31, v51);
            v32 = v51[0];
            if ( !(unsigned int)_o__wcsicmp(v51[0], L"edgehtml.dll") )
            {
              *(_BYTE *)(a1 + 689) = 1;
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32 - 24 + 16), 0xFFFFFFFF) <= 1 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v32 - 24) + 8LL))(*(_QWORD *)(v32 - 24));
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 - 2, 0xFFFFFFFF) <= 1 )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 - 3) + 8LL))(*((_QWORD *)v27 - 3));
              break;
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32 - 24 + 16), 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v32 - 24) + 8LL))(*(_QWORD *)(v32 - 24));
            v23 = v48;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 - 2, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 - 3) + 8LL))(*((_QWORD *)v27 - 3));
          ++v24;
        }
        while ( v24 < v25 );
      }
      v18 = a1 + 504;
    }
    else
    {
      *(_BYTE *)(a1 + 689) = 1;
    }
    if ( *(_BYTE *)(a1 + 689) )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&lpLibFileName, L"F12\\F12Platform2.dll", 20);
  }
  v33 = lpLibFileName;
  Library = LoadLibraryExW(lpLibFileName, 0, 0x800u);
  ProcAddress = GetProcAddress(Library, "CreatePlatform");
  if ( !ProcAddress )
    ATL::AtlThrowImpl(-2147024893);
  v48 = 0;
  v36 = ATL::CComObject<AppUtilities>::CreateInstance(&v48);
  if ( v36 )
  {
    if ( v36 >= 0 )
      v36 = -2147467259;
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&cbNeeded, v36);
    throw (ATL::CAtlException *)&cbNeeded;
  }
  v37 = (__int64)v48;
  v38 = (__int64 *)(a1 + 720);
  if ( *(HANDLE *)(a1 + 720) != v48 )
  {
    if ( v48 )
    {
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v48 + 8LL))(v48);
      v38 = (__int64 *)(a1 + 720);
    }
    if ( *v38 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*v38 + 16LL))(*v38);
      v38 = (__int64 *)(a1 + 720);
    }
    *v38 = v37;
  }
  if ( ((unsigned int (__fastcall *)(__int64, __int64 *, const OLECHAR *, _QWORD, __int64))ProcAddress)(
         a1 + 576,
         v38,
         &String,
         *(unsigned int *)(a1 + 560),
         a1 + 568) )
  {
    ATL::AtlThrowImpl(-2147418113);
  }
  v39 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 568) + 56LL))(*(_QWORD *)(a1 + 568), a1 + 712);
  if ( v39 )
  {
    if ( v39 >= 0 )
      v39 = -2147467259;
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&cbNeeded, v39);
    throw (ATL::CAtlException *)&cbNeeded;
  }
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 712) + 72LL))(*(_QWORD *)(a1 + 712));
  DC = GetDC(0);
  v41 = DC;
  if ( DC )
  {
    *(double *)(a1 + 680) = (double)GetDeviceCaps(DC, 88) / 96.0;
    ReleaseDC(0, v41);
  }
  else
  {
    *(_QWORD *)(a1 + 680) = 0x3FF0000000000000LL;
  }
  v42 = *(double *)(a1 + 680);
  v43 = (int)((double)*(int *)(a1 + 652) * v42);
  *(_DWORD *)(a1 + 652) = v43;
  *(_DWORD *)(a1 + 656) = (int)((double)v43 * v42);
  *(_DWORD *)(a1 + 640) = (int)((double)*(int *)(a1 + 640) * v42);
  *(_DWORD *)(a1 + 644) = (int)((double)*(int *)(a1 + 644) * v42);
  *(_DWORD *)(a1 + 648) = (int)((double)*(int *)(a1 + 648) * v42);
  F12::GetEnabledPlugins(a1 + 480);
  cbNeeded = -1;
  if ( !*(_BYTE *)(a1 + 672) )
  {
    if ( *(int *)(*(_QWORD *)(a1 + 608) - 16LL) <= 0 )
    {
      if ( *(int *)(*(_QWORD *)(a1 + 616) - 16LL) <= 0 )
      {
        if ( !(unsigned int)F12::GetInitialPluginInfo((F12 *)&cbNeeded, v44) )
        {
          v21 = cbNeeded;
          goto LABEL_57;
        }
        v21 = -1;
      }
    }
    else
    {
      v21 = 2;
    }
  }
  cbNeeded = v21;
LABEL_57:
  for ( i = *(_DWORD **)(a1 + 480); i != *(_DWORD **)(a1 + 488); ++i )
  {
    if ( *i == v21 )
      goto LABEL_66;
  }
  v21 = 2;
  cbNeeded = 2;
LABEL_66:
  *(_DWORD *)(a1 + 552) = v21;
  std::deque<enum PluginId>::push_back(v18, &cbNeeded);
  *(_QWORD *)(a1 + 664) = 0;
  cbNeeded = 0;
  if ( (int)GetValue((__int64 *)SettingStore::IEVALUE_F12_DockStateChanged, 0, 1, &cbNeeded, 4, 0, 0) < 0 || !cbNeeded )
    v13 = 0;
  *(_BYTE *)(a1 + 441) = v13;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v33 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v33 - 3) + 8LL))(*((_QWORD *)v33 - 3));
  return a1;
}

```

## disassembly

```asm
0x18001f024  push    rbp
0x18001f026  push    rbx
0x18001f027  push    rsi
0x18001f028  push    rdi
0x18001f029  push    r12
0x18001f02b  push    r13
0x18001f02d  push    r14
0x18001f02f  push    r15
0x18001f031  lea     rbp, [rsp-1F98h]
0x18001f039  mov     eax, 2098h
0x18001f03e  call    _alloca_probe
0x18001f043  sub     rsp, rax
0x18001f046  mov     rax, cs:__security_cookie
0x18001f04d  xor     rax, rsp
0x18001f050  mov     [rbp+1FD0h+var_50], rax
0x18001f057  mov     r12d, r9d
0x18001f05a  mov     [rsp+20D0h+cbNeeded], r8d
0x18001f05f  mov     r15, rdx
0x18001f062  mov     rsi, rcx
0x18001f065  mov     [rsp+20D0h+var_2060], rcx
0x18001f06a  mov     rax, [rbp+1FD0h+arg_30]
0x18001f071  mov     [rsp+20D0h+var_2088], rax
0x18001f076  mov     rax, [rbp+1FD0h+arg_48]
0x18001f07d  mov     [rsp+20D0h+var_2070], rax
0x18001f082  xor     r13d, r13d
0x18001f085  mov     [rcx+8], r13
0x18001f089  mov     [rcx+28h], r13
0x18001f08d  mov     [rcx+30h], r13
0x18001f091  mov     [rcx+38h], r13d
0x18001f095  mov     rax, cs:__imp_DefWindowProcW
0x18001f09c  mov     [rcx+40h], rax
0x18001f0a0  mov     [rcx+48h], r13
0x18001f0a4  mov     [rcx+50h], r13
0x18001f0a8  mov     [rcx+58h], r13
0x18001f0ac  mov     [rcx+60h], r13
0x18001f0b0  lea     rax, ??_7FrameWindow@@6B?$CFrameWindowImpl@VFrameWindow@@VCWindow@ATL@@V?$CWinTraits@$0A@$0EAAAA@@3@@WTL@@@; const FrameWindow::`vftable'{for `WTL::CFrameWindowImpl<FrameWindow,ATL::CWindow,ATL::CWinTraits<0,262144>>'}
0x18001f0b7  mov     [rcx], rax
0x18001f0ba  lea     rax, ??_7FrameWindow@@6BCMessageFilter@WTL@@@; const FrameWindow::`vftable'{for `WTL::CMessageFilter'}
0x18001f0c1  mov     [rcx+68h], rax
0x18001f0c5  mov     [rcx+98h], r13
0x18001f0cc  mov     [rcx+0B8h], r13
0x18001f0d3  mov     [rcx+0C0h], r13
0x18001f0da  mov     [rcx+0C8h], r13d
0x18001f0e1  mov     rax, cs:__imp_DefWindowProcW
0x18001f0e8  mov     [rcx+0D0h], rax
0x18001f0ef  lea     rax, ??_7CDragOverlayWindow@@6B@; const CDragOverlayWindow::`vftable'
0x18001f0f6  mov     [rcx+90h], rax
0x18001f0fd  mov     [rcx+0E0h], r13
0x18001f104  lea     r14d, [r13+1]
0x18001f108  mov     [rcx+0E8h], r14b
0x18001f10f  mov     [rcx+0F0h], r13
0x18001f116  mov     [rcx+0F8h], r13
0x18001f11d  mov     [rcx+100h], r13
0x18001f124  mov     [rcx+108h], r13
0x18001f12b  mov     [rcx+110h], r13
0x18001f132  lea     rbx, [rcx+118h]
0x18001f139  mov     [rsp+20D0h+var_2080], rbx
0x18001f13e  mov     [rbx+8], r13
0x18001f142  mov     [rbx+28h], r13
0x18001f146  mov     [rbx+30h], r13
0x18001f14a  mov     [rbx+38h], r13d
0x18001f14e  mov     rax, cs:__imp_DefWindowProcW
0x18001f155  mov     [rbx+40h], rax
0x18001f159  mov     qword ptr [rbx+68h], 0FFFFFFFFFFFFFFFFh
0x18001f161  mov     [rbx+70h], r13
0x18001f165  mov     [rbx+78h], r13d
0x18001f169  mov     [rbx+7Ch], r14b
0x18001f16d  mov     [rbx+80h], r13
0x18001f174  mov     [rbx+88h], r14b
0x18001f17b  mov     [rbx+8Ch], r14d
0x18001f182  mov     dword ptr [rbx+90h], 0FFFFFFFFh
0x18001f18c  xorps   xmm0, xmm0
0x18001f18f  movups  xmmword ptr [rbx+48h], xmm0
0x18001f193  lea     rcx, [rbx+58h]; lprc
0x18001f197  call    cs:__imp_SetRectEmpty
0x18001f19d  cmp     cs:?m_hCursor@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@2PEAUHICON__@@EA, r13; HICON__ * WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::m_hCursor
0x18001f1a4  jnz     short loc_18001F1DF
0x18001f1a6  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001f1ad  lea     rcx, [rdi+18h]; lpCriticalSection
0x18001f1b1  call    cs:__imp_EnterCriticalSection
0x18001f1b7  cmp     cs:?m_hCursor@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@2PEAUHICON__@@EA, r13; HICON__ * WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::m_hCursor
0x18001f1be  jnz     short loc_18001F1D4
0x18001f1c0  mov     edx, 7F85h; lpCursorName
0x18001f1c5  xor     ecx, ecx; hInstance
0x18001f1c7  call    cs:__imp_LoadCursorW
0x18001f1cd  mov     cs:?m_hCursor@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@2PEAUHICON__@@EA, rax; HICON__ * WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::m_hCursor
0x18001f1d4  lea     rcx, [rdi+18h]; lpCriticalSection
0x18001f1d8  call    cs:__imp_LeaveCriticalSection
0x18001f1de  nop
0x18001f1df  lea     rax, ??_7?$CF12SplitterWindowT@$0A@@@6B@; const CF12SplitterWindowT<0>::`vftable'
0x18001f1e6  mov     [rbx], rax
0x18001f1e9  mov     [rsi+1B0h], r13d
0x18001f1f0  mov     [rsi+1B5h], r13w
0x18001f1f8  mov     [rsi+1B7h], r13b
0x18001f1ff  mov     edi, [rbp+1FD0h+arg_40]
0x18001f205  cmp     edi, r14d
0x18001f208  setz    al
0x18001f20b  mov     [rsi+1B8h], al
0x18001f211  mov     [rsi+1B9h], r13b
0x18001f218  lea     rbx, [rsi+1C0h]
0x18001f21f  mov     [rbx], r13
0x18001f222  mov     [rbx+8], r13
0x18001f226  mov     ecx, 38h ; '8'; Size
0x18001f22b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f230  mov     [rax], rax
0x18001f233  mov     [rax+8], rax
0x18001f237  mov     [rax+10h], rax
0x18001f23b  mov     word ptr [rax+18h], 101h
0x18001f241  mov     [rbx], rax
0x18001f244  lea     rbx, [rsi+1D0h]
0x18001f24b  mov     [rbx], r13
0x18001f24e  mov     [rbx+8], r13
0x18001f252  mov     ecx, 40h ; '@'; Size
0x18001f257  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f25c  mov     [rax], rax
0x18001f25f  mov     [rax+8], rax
0x18001f263  mov     [rax+10h], rax
0x18001f267  mov     word ptr [rax+18h], 101h
0x18001f26d  mov     [rbx], rax
0x18001f270  lea     rax, [rsi+1E0h]
0x18001f277  mov     [rax], r13
0x18001f27a  mov     [rax+8], r13
0x18001f27e  mov     [rax+10h], r13
0x18001f282  lea     r13, [rsi+1F8h]
0x18001f289  xor     ebx, ebx
0x18001f28b  mov     [r13+0], rbx
0x18001f28f  mov     [r13+8], rbx
0x18001f293  mov     [r13+10h], rbx
0x18001f297  mov     [r13+18h], rbx
0x18001f29b  mov     [r13+20h], rbx
0x18001f29f  lea     ecx, [rbx+10h]; Size
0x18001f2a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f2a7  mov     [rax+8], rbx
0x18001f2ab  mov     [r13+0], rax
0x18001f2af  mov     [rax], r13
0x18001f2b2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f2b6  mov     [rsi+220h], eax
0x18001f2bc  mov     [rsi+224h], eax
0x18001f2c2  mov     [rsi+228h], eax
0x18001f2c8  mov     [rsi+22Ch], eax
0x18001f2ce  mov     [rsi+230h], edi
0x18001f2d4  mov     [rsi+238h], rbx
0x18001f2db  mov     [rsi+240h], r15
0x18001f2e2  test    r15, r15
0x18001f2e5  jz      short loc_18001F2F7
0x18001f2e7  mov     rax, [r15]
0x18001f2ea  mov     rcx, r15
0x18001f2ed  mov     rax, [rax+8]
0x18001f2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2f6  nop
0x18001f2f7  mov     eax, [rsp+20D0h+cbNeeded]
0x18001f2fb  mov     [rsi+248h], eax
0x18001f301  mov     [rsi+24Ch], r12d
0x18001f308  mov     rax, [rbp+1FD0h+arg_20]
0x18001f30f  mov     [rsi+250h], rax
0x18001f316  mov     rax, [rbp+1FD0h+arg_28]
0x18001f31d  mov     [rsi+258h], rax
0x18001f324  lea     rcx, [rsi+260h]
0x18001f32b  mov     rdx, [rsp+20D0h+var_2088]
0x18001f330  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001f335  nop
0x18001f336  lea     rcx, [rsi+268h]
0x18001f33d  mov     rdx, [rsp+20D0h+var_2070]
0x18001f342  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001f347  nop
0x18001f348  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f34f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f356  mov     rax, [rax+18h]
0x18001f35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f35f  add     rax, 18h
0x18001f363  mov     [rsi+270h], rax
0x18001f36a  mov     [rsi+278h], r14d
0x18001f371  mov     dword ptr [rsi+27Ch], 2
0x18001f37b  mov     dword ptr [rsi+280h], 74h ; 't'
0x18001f385  mov     dword ptr [rsi+284h], 16h
0x18001f38f  mov     dword ptr [rsi+288h], 2Ch ; ','
0x18001f399  mov     dword ptr [rsi+28Ch], 190h
0x18001f3a3  mov     qword ptr [rsi+290h], 3Ch ; '<'
0x18001f3ae  xor     r15d, r15d
0x18001f3b1  mov     al, [rbp+1FD0h+arg_38]
0x18001f3b7  mov     [rsi+2A0h], al
0x18001f3bd  mov     [rsi+2A1h], r15w
0x18001f3c5  mov     [rsi+2A4h], r15d
0x18001f3cc  mov     [rsi+2B1h], r15b
0x18001f3d3  mov     [rsi+2C8h], r15
0x18001f3da  mov     [rsi+2D0h], r15
0x18001f3e1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f3e8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f3ef  mov     rax, [rax+18h]
0x18001f3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3f8  add     rax, 18h
0x18001f3fc  mov     [rsp+20D0h+lpLibFileName], rax
0x18001f401  lea     rdx, aF12F12platform_0; "F12\\F12Platform.dll"
0x18001f408  lea     rcx, [rsp+20D0h+lpLibFileName]
0x18001f40d  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18001f412  test    al, al
0x18001f414  jnz     short loc_18001F42C
0x18001f416  lea     r8d, [r15+13h]
0x18001f41a  lea     rdx, aF12F12platform_0; "F12\\F12Platform.dll"
0x18001f421  lea     rcx, [rsp+20D0h+lpLibFileName]
0x18001f426  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001f42b  nop
0x18001f42c  mov     eax, [rsi+230h]
0x18001f432  mov     ebx, 3
0x18001f437  test    eax, eax
0x18001f439  jz      short loc_18001F443
0x18001f43b  cmp     eax, ebx
0x18001f43d  jnz     loc_18001F62B
0x18001f443  mov     r12d, 2000h
0x18001f449  mov     r8d, r12d; Size
0x18001f44c  xor     edx, edx; Val
0x18001f44e  lea     rcx, [rbp+1FD0h+hModule]; void *
0x18001f452  call    memset_0
0x18001f457  mov     [rsp+20D0h+cbNeeded], r15d
0x18001f45c  mov     r8d, [rsi+248h]; dwProcessId
0x18001f463  xor     edx, edx; bInheritHandle
0x18001f465  mov     ecx, 410h; dwDesiredAccess
0x18001f46a  call    cs:__imp_OpenProcess
0x18001f470  mov     rdi, rax
0x18001f473  mov     [rsp+20D0h+var_2088], rax
0x18001f478  test    rax, rax
0x18001f47b  jz      loc_18001F7C0
0x18001f481  mov     [rsp+20D0h+dwFilterFlag], ebx; dwFilterFlag
0x18001f485  lea     r9, [rsp+20D0h+cbNeeded]; lpcbNeeded
0x18001f48a  mov     r8d, r12d; cb
0x18001f48d  lea     rdx, [rbp+1FD0h+hModule]; lphModule
0x18001f491  mov     rcx, rax; hProcess
0x18001f494  call    cs:__imp_K32EnumProcessModulesEx
0x18001f49a  test    eax, eax
0x18001f49c  jz      loc_18001F7C0
0x18001f4a2  mov     r12d, [rsp+20D0h+cbNeeded]
0x18001f4a7  mov     r13d, r15d
0x18001f4aa  cmp     r12d, 2000h
0x18001f4b1  jbe     short loc_18001F4BB
0x18001f4b3  mov     r12d, 400h
0x18001f4b9  jmp     short loc_18001F4C8
0x18001f4bb  shr     r12d, 3
0x18001f4bf  test    r12d, r12d
0x18001f4c2  jz      loc_18001F604
0x18001f4c8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f4cf  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f4d6  mov     rax, [rax+18h]
0x18001f4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4df  lea     r15, [rax+18h]
0x18001f4e3  mov     [rsp+20D0h+var_2080], r15
0x18001f4e8  mov     ecx, r14d
0x18001f4eb  sub     ecx, [r15-8]
0x18001f4ef  mov     eax, [r15-0Ch]
0x18001f4f3  mov     edx, 104h
0x18001f4f8  sub     eax, edx
0x18001f4fa  or      ecx, eax
0x18001f4fc  jge     short loc_18001F50D
0x18001f4fe  lea     rcx, [rsp+20D0h+var_2080]
0x18001f503  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001f508  mov     r15, [rsp+20D0h+var_2080]
0x18001f50d  mov     edx, r13d
0x18001f510  mov     r9d, 104h; nSize
0x18001f516  mov     r8, r15; lpFilename
0x18001f519  mov     rdx, [rbp+rdx*8+1FD0h+hModule]; hModule
0x18001f51e  mov     rcx, rdi; hProcess
0x18001f521  call    cs:__imp_K32GetModuleFileNameExW
0x18001f527  xor     r8d, r8d
0x18001f52a  test    r15, r15
0x18001f52d  jnz     short loc_18001F534
0x18001f52f  mov     ecx, r8d
0x18001f532  jmp     short loc_18001F54A
0x18001f534  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f538  inc     rcx
0x18001f53b  cmp     [r15+rcx*2], r8w
0x18001f540  jnz     short loc_18001F538
0x18001f542  test    ecx, ecx
0x18001f544  js      loc_18001F9B0
0x18001f54a  cmp     ecx, [r15-0Ch]
0x18001f54e  jg      loc_18001F9B0
0x18001f554  mov     [r15-10h], ecx
0x18001f558  mov     ecx, ecx
0x18001f55a  mov     [r15+rcx*2], r8w
0x18001f55f  test    eax, eax
0x18001f561  jz      short loc_18001F5D5
0x18001f563  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f56a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f571  mov     rax, [rax+18h]
0x18001f575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f57a  add     rax, 18h
0x18001f57e  mov     [rsp+20D0h+var_2070], rax
0x18001f583  lea     r8, [rsp+20D0h+var_2070]
0x18001f588  mov     dl, r14b
0x18001f58b  mov     rcx, r15
0x18001f58e  call    ?GetNameFromPath@Win32Helpers@@YAJPEBG_NAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Win32Helpers::GetNameFromPath(ushort const *,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001f593  lea     rdx, aEdgehtmlDll; "edgehtml.dll"
0x18001f59a  mov     rdi, [rsp+20D0h+var_2070]
0x18001f59f  mov     rcx, rdi
0x18001f5a2  call    cs:__imp__o__wcsicmp
0x18001f5a8  test    eax, eax
0x18001f5aa  jz      loc_18001F76C
0x18001f5b0  lea     rdx, [rdi-18h]
0x18001f5b4  or      eax, 0FFFFFFFFh
0x18001f5b7  lock xadd [rdx+10h], eax
0x18001f5bc  sub     eax, 1
0x18001f5bf  jg      short loc_18001F5D0
  ... truncated ...
```
