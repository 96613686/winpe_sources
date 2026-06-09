# WinSAT::OpMem1Thread::DoOperation(void)

- ea: `0x140059ef4`
- end: `0x14005c142`
- name: `?DoOperation@OpMem1Thread@WinSAT@@QEAAKXZ`
- size: `8782`
- prototype: `unsigned int __fastcall(WinSAT::OpMem1Thread *__hidden this)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14005c150`

## callees

- `0x140003560`
- `0x1400040d0`
- `0x140004170`
- `0x140004348`
- `0x14000449c`
- `0x140007f14`
- `0x140008178`
- `0x1400083a4`
- `0x1400085b4`
- `0x14000a8d8`
- `0x140011f58`
- `0x140016588`
- `0x140016954`
- `0x140017af0`
- `0x14001827c`
- `0x14002093c`
- `0x1400219d0`
- `0x14003ec14`
- `0x14004fce4`
- `0x1400530a8`
- `0x140058488`
- `0x1400584b0`
- `0x140058818`
- `0x140059010`
- `0x140059158`
- `0x140059ef4`
- `0x14005c9b4`
- `0x14005cb00`
- `0x14005cc74`
- `0x14005ed80`
- `0x14005eecc`
- `0x14005ef98`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14005a606`
- `KERNEL32!GetTickCount` at `0x14005a701`
- `KERNEL32!GetTickCount` at `0x14005a8aa`
- `KERNEL32!GetTickCount` at `0x14005a924`
- `KERNEL32!GetTickCount` at `0x14005a954`
- `KERNEL32!GetTickCount` at `0x14005a606`
- `KERNEL32!GetTickCount` at `0x14005a701`
- `KERNEL32!GetTickCount` at `0x14005a8aa`
- `KERNEL32!GetTickCount` at `0x14005a924`
- `KERNEL32!GetTickCount` at `0x14005a954`
- `KERNEL32!EnterCriticalSection` at `0x140059fc7`
- `KERNEL32!EnterCriticalSection` at `0x14005a2a7`
- `KERNEL32!EnterCriticalSection` at `0x14005acea`
- `KERNEL32!EnterCriticalSection` at `0x14005c00c`
- `KERNEL32!EnterCriticalSection` at `0x140059fc7`
- `KERNEL32!EnterCriticalSection` at `0x14005a2a7`
- `KERNEL32!EnterCriticalSection` at `0x14005acea`
- `KERNEL32!EnterCriticalSection` at `0x14005c00c`
- `KERNEL32!LeaveCriticalSection` at `0x14005a00c`
- `KERNEL32!LeaveCriticalSection` at `0x14005a4bb`
- `KERNEL32!LeaveCriticalSection` at `0x14005bf6f`
- `KERNEL32!LeaveCriticalSection` at `0x14005a00c`
- `KERNEL32!LeaveCriticalSection` at `0x14005a4bb`
- `KERNEL32!LeaveCriticalSection` at `0x14005bf6f`
- `KERNEL32!GetCurrentThreadId` at `0x14005a2f7`
- `KERNEL32!GetCurrentThreadId` at `0x14005a2f7`
- `KERNEL32!GetThreadPriority` at `0x14005a050`
- `KERNEL32!GetThreadPriority` at `0x14005a050`
- `KERNEL32!GetCurrentThread` at `0x140059f50`
- `KERNEL32!GetCurrentThread` at `0x14005a047`
- `KERNEL32!GetCurrentThread` at `0x140059f50`
- `KERNEL32!GetCurrentThread` at `0x14005a047`
- `KERNEL32!GetLastError` at `0x140059f7d`
- `KERNEL32!GetLastError` at `0x14005a0ed`
- `KERNEL32!GetLastError` at `0x14005a150`
- `KERNEL32!GetLastError` at `0x14005a1c8`
- `KERNEL32!GetLastError` at `0x14005bfc1`
- `KERNEL32!GetLastError` at `0x140059f7d`
- `KERNEL32!GetLastError` at `0x14005a0ed`
- `KERNEL32!GetLastError` at `0x14005a150`
- `KERNEL32!GetLastError` at `0x14005a1c8`
- `KERNEL32!GetLastError` at `0x14005bfc1`
- `KERNEL32!Sleep` at `0x14005a078`
- `KERNEL32!Sleep` at `0x14005a8a0`
- `KERNEL32!Sleep` at `0x14005a078`
- `KERNEL32!Sleep` at `0x14005a8a0`
- `KERNEL32!VirtualLock` at `0x14005a138`
- `KERNEL32!VirtualLock` at `0x14005a1b0`
- `KERNEL32!VirtualLock` at `0x14005a138`
- `KERNEL32!VirtualLock` at `0x14005a1b0`
- `KERNEL32!VirtualAlloc` at `0x14005a0d1`
- `KERNEL32!VirtualAlloc` at `0x14005a0d1`
- `KERNEL32!VirtualFree` at `0x14005a185`
- `KERNEL32!VirtualFree` at `0x14005a1fd`
- `KERNEL32!VirtualFree` at `0x14005bfb7`
- `KERNEL32!VirtualFree` at `0x14005a185`
- `KERNEL32!VirtualFree` at `0x14005a1fd`
- `KERNEL32!VirtualFree` at `0x14005bfb7`
- `KERNEL32!SetThreadPriority` at `0x140059f5d`
- `KERNEL32!SetThreadPriority` at `0x140059f5d`
- `KERNEL32!SetLastError` at `0x14005a035`
- `KERNEL32!SetLastError` at `0x14005bfa6`
- `KERNEL32!SetLastError` at `0x14005c0f8`
- `KERNEL32!SetLastError` at `0x14005a035`
- `KERNEL32!SetLastError` at `0x14005bfa6`
- `KERNEL32!SetLastError` at `0x14005c0f8`

## string_xrefs

- `0x14005a477`: `  -- Copy Routine = `
- `0x14005a059`: `Adjusted the priority of the Memory copy thread to %d`
- `0x14005ada2`: `  --          cummulative copy seconds : `
- `0x14005af3c`: `  --                 buffer copy count : `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinSAT::OpMem1Thread::DoOperation(WinSAT::OpMem1Thread *this)
{
  HANDLE CurrentThread; // rax
  int v3; // r8d
  __int64 v4; // rdx
  const unsigned __int16 *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  HANDLE v11; // rax
  int ThreadPriority; // eax
  int v13; // r9d
  char *v14; // rax
  char *v15; // r15
  SIZE_T v16; // rbx
  __int64 v17; // r14
  BOOL v18; // eax
  __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  const wchar_t *v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  unsigned __int64 v38; // r12
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rdx
  int v49; // ebx
  __int64 v50; // rbx
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rcx
  DWORD TickCount; // eax
  __int64 v55; // rcx
  __int64 v56; // r8
  unsigned __int64 v57; // rdx
  unsigned __int64 v58; // rax
  unsigned __int64 v59; // rbx
  unsigned int v60; // eax
  unsigned int v61; // r9d
  unsigned int v62; // r8d
  mlib *v63; // rcx
  __int64 v64; // rbx
  mlib *v65; // rcx
  __int64 PerformanceFrequency64; // rax
  double v67; // xmm1_8
  __int64 v68; // rdx
  double v69; // xmm0_8
  double v70; // xmm0_8
  __int64 v71; // rbx
  double v72; // xmm6_8
  double v73; // xmm6_8
  __int64 v74; // rcx
  double v75; // xmm4_8
  __int64 v76; // rdx
  __int64 v77; // rcx
  double v78; // xmm7_8
  double v79; // xmm7_8
  __int64 v80; // r12
  double v81; // xmm0_8
  SIZE_T v82; // rbx
  double v83; // xmm5_8
  double v84; // xmm5_8
  __int64 v85; // rcx
  __int64 v86; // rdx
  double v87; // xmm2_8
  double v88; // xmm3_8
  double v89; // xmm3_8
  __int64 v90; // rcx
  double v91; // xmm8_8
  double v92; // xmm8_8
  double v93; // xmm2_8
  __int64 v94; // rcx
  double v95; // xmm1_8
  __int64 v96; // rcx
  double v97; // xmm1_8
  __int64 v98; // rcx
  double v99; // xmm0_8
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // rax
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  const wchar_t *v132; // rdx
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rax
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rax
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // rax
  __int64 v160; // rax
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // rax
  __int64 v166; // rax
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rcx
  __int64 v170; // r8
  __int64 v171; // rax
  unsigned __int64 v172; // r12
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // r8
  __int64 v177; // rax
  int v178; // r8d
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rax
  __int64 v182; // r8
  __int64 v183; // rax
  int v184; // r8d
  __int64 v185; // rax
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // r8
  __int64 v189; // rax
  int v190; // r8d
  __int64 v191; // rax
  __int64 v192; // rax
  __int64 v193; // rax
  __int64 v194; // r8
  __int64 v195; // rax
  __int64 v196; // r8
  __int64 v197; // rax
  __int64 v198; // rax
  __int64 v199; // rax
  __int64 v200; // rax
  __int64 v201; // rax
  const wchar_t *v202; // rdx
  __int64 v203; // rax
  bool v204; // bl
  int v205; // r8d
  __int64 v206; // rdx
  _DWORD *v207; // rbx
  const unsigned __int16 *v208; // rax
  __int64 v209; // rbx
  const unsigned __int16 *v210; // rax
  __int64 v211; // rax
  DWORD v212; // ebx
  __int64 v213; // rdi
  const unsigned __int16 *v214; // rbx
  __int64 v215; // rax
  __int64 v216; // rax
  __int64 v217; // rax
  DWORD v218; // [rsp+30h] [rbp-2F8h] BYREF
  bool v219; // [rsp+34h] [rbp-2F4h]
  char v220; // [rsp+35h] [rbp-2F3h]
  char v221; // [rsp+36h] [rbp-2F2h]
  int v222; // [rsp+38h] [rbp-2F0h]
  unsigned int v223; // [rsp+3Ch] [rbp-2ECh] BYREF
  char v224; // [rsp+40h] [rbp-2E8h]
  unsigned int v225; // [rsp+44h] [rbp-2E4h]
  unsigned __int64 v226; // [rsp+48h] [rbp-2E0h]
  SIZE_T v227; // [rsp+50h] [rbp-2D8h]
  unsigned int v228; // [rsp+58h] [rbp-2D0h]
  unsigned int v229; // [rsp+5Ch] [rbp-2CCh]
  unsigned int v230; // [rsp+60h] [rbp-2C8h]
  void (__fastcall *v231)(char *, void *, _QWORD, __int64); // [rsp+68h] [rbp-2C0h] BYREF
  void (__fastcall *v232)(char *, void *, _QWORD, __int64, unsigned __int64); // [rsp+70h] [rbp-2B8h] BYREF
  unsigned int v233; // [rsp+78h] [rbp-2B0h]
  void *v234; // [rsp+80h] [rbp-2A8h]
  void (__fastcall *v235)(char *, void *, _QWORD); // [rsp+88h] [rbp-2A0h] BYREF
  __int64 PerformanceCounter64; // [rsp+90h] [rbp-298h]
  unsigned __int64 v237; // [rsp+98h] [rbp-290h]
  __int64 v238; // [rsp+A0h] [rbp-288h]
  __int64 v239; // [rsp+A8h] [rbp-280h]
  WCHAR Buffer[256]; // [rsp+B0h] [rbp-278h] BYREF
  DWORD dwErrCode; // [rsp+2B0h] [rbp-78h]
  char v242; // [rsp+2B4h] [rbp-74h]
  __int64 v243; // [rsp+2B8h] [rbp-70h]

  PerformanceCounter64 = (__int64)this;
  if ( !*(_BYTE *)(*((_QWORD *)this + 18) + 737LL) )
  {
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, 15) )
    {
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 18) + 772LL), 1u);
      dwErrCode = GetLastError();
      v242 = 1;
      v243 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      v3 = 624;
      v4 = 600;
LABEL_4:
      v5 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)v4, v3, *(_DWORD *)this);
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
      v6 = *((_QWORD *)this + 17) + 240LL;
LABEL_5:
      v7 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v6, v5);
      v8 = std::basic_ostream<unsigned short>::operator<<(v7, 10);
      v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, Buffer);
      std::endl(v9);
      LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
      WinSAT::OpStatus::SetResult((char *)this + 400, 5, v5, Buffer);
      SetLastError(dwErrCode);
      return dwErrCode;
    }
    v11 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v11);
    Log_Text_F(
      "base\\winsat\\memory\\memat.cpp",
      610,
      "Adjusted the priority of the Memory copy thread to %d",
      ThreadPriority);
  }
  Sleep(1u);
  try
  {
    SampleManager::ClearAndReserve((WinSAT::OpMem1Thread *)((char *)this + 152), 0x4000u);
  }
  catch ( ... )
  {
    v213 = PerformanceCounter64;
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(PerformanceCounter64 + 144) + 772LL));
    dwErrCode = 8;
    v242 = 1;
    v243 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v214 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x279, 625, *(_DWORD *)v213);
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(v213 + 120));
    v215 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)(v213 + 136) + 240LL, v214);
    v216 = std::basic_ostream<unsigned short>::operator<<(v215, 10);
    v217 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v216, Buffer);
    std::endl(v217);
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v213 + 120));
    WinSAT::OpStatus::SetResult(v213 + 400, 5, v214, Buffer);
    SetLastError(dwErrCode);
    return dwErrCode;
  }
  v227 = *((_QWORD *)this + 2) + 2LL * *((_QWORD *)this + 1);
  v13 = *(_BYTE *)(*((_QWORD *)this + 18) + 736LL) != 0 ? 0x200 : 0;
  v222 = 4;
  v14 = (char *)VirtualAlloc(0, v227, 0x1000u, v13 + 4);
  v15 = v14;
  if ( !v14 )
  {
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 18) + 772LL), 1u);
    dwErrCode = GetLastError();
    v242 = 1;
    v243 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v3 = 626;
    v4 = 668;
    goto LABEL_4;
  }
  *((_QWORD *)this + 3) = v14;
  v16 = *((_QWORD *)this + 1);
  v17 = *((_QWORD *)this + 2);
  if ( !VirtualLock(v14, v16) )
  {
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 18) + 772LL), 1u);
    dwErrCode = GetLastError();
    v242 = 1;
    v243 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    VirtualFree(v15, 0, 0x8000u);
    v3 = 627;
    v4 = 702;
    goto LABEL_4;
  }
  v234 = &v15[v17 + v16];
  v18 = VirtualLock(v234, *((_QWORD *)this + 1));
  v19 = *((_QWORD *)this + 18);
  if ( !v18 )
  {
    _InterlockedAdd((volatile signed __int32 *)(v19 + 772), 1u);
    dwErrCode = GetLastError();
    v242 = 1;
    v243 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    VirtualFree(v15, 0, 0x8000u);
    v3 = 628;
    v4 = 724;
    goto LABEL_4;
  }
  v20 = *(unsigned int *)(v19 + 716);
  v225 = *(_DWORD *)(v19 + 744);
  v233 = *(_DWORD *)(v19 + 748);
  v231 = 0;
  v232 = 0;
  v235 = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  GetFuncPtr(v19 + 728, &v231, &v232, &v235);
  *((_QWORD *)this + 5) = *(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(*((_QWORD *)this + 18) + 40LL);
  v21 = *((_QWORD *)this + 1);
  if ( v20 <= v21 )
    v21 = v20;
  v237 = v21;
  if ( *(_BYTE *)(*((_QWORD *)this + 18) + 33LL) )
  {
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
    v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*((_QWORD *)this + 16) + 240LL, L"> CPU(");
    v23 = std::basic_ostream<unsigned short>::operator<<(v22, *(unsigned int *)this);
    v24 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v23, L")  TID: ");
    v223 = 4;
    v25 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, &v223);
    CurrentThreadId = GetCurrentThreadId();
    v27 = std::basic_ostream<unsigned short>::operator<<(v25, CurrentThreadId);
    *(_DWORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v27 + 4LL) + v27 + 40) = 0;
    v28 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, L"\n");
    v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v28, L"  -- Running at ");
    v30 = L"NORMAL";
    if ( !*(_BYTE *)(*((_QWORD *)this + 18) + 737LL) )
      v30 = L"HIGH";
    v31 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, v30);
    v32 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, L" priority\n");
    v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, L"  -- Allocated ");
    v34 = std::basic_ostream<unsigned short>::operator<<(v33, v227);
    v35 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, L" (0x");
    v223 = 4;
    v36 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, &v223);
    v37 = std::basic_ostream<unsigned short>::operator<<(v36, v227);
    *(_DWORD *)(*(int *)(*(_QWORD *)v37 + 4LL) + v37 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v37 + 4LL) + v37 + 88) = 32;
    v38 = 0;
    *(_QWORD *)(*(int *)(*(_QWORD *)v37 + 4LL) + v37 + 40) = 0;
    v39 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v37, L") bytes\n");
    v40 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v39, L"  -- Affinity Mask ");
    v223 = 8;
    v41 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v40, &v223);
    v42 = std::basic_ostream<unsigned short>::operator<<(v41, *((unsigned int *)this + 68));
    *(_DWORD *)(*(int *)(*(_QWORD *)v42 + 4LL) + v42 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v42 + 4LL) + v42 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v42 + 4LL) + v42 + 40) = 0;
    v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, "\n");
    v44 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v43, L"  -- Copy Routine = ");
    v45 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v44,
            *((_QWORD *)this + 18) + 728LL);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, "\n");
    std::basic_ostream<unsigned short>::flush(*((_QWORD *)this + 16) + 240LL);
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
  }
  else
  {
    v38 = 0;
  }
  if ( v235 )
  {
    v46 = *((_QWORD *)this + 18);
    v47 = mlib::m_traits<unsigned short>::CStrlen(L"memcpy", 0x10000);
    if ( !(unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei_str(
                          v46 + 728,
                          v48,
                          **(_QWORD **)(v46 + 728),
                          L"memcpy",
                          v47) )
    {
      v49 = 1;
LABEL_32:
      v222 = v49;
      goto LABEL_33;
    }
    v50 = *((_QWORD *)this + 18);
    v51 = mlib::m_traits<unsigned short>::CStrlen(L"memcpy_inl", 0x10000);
    if ( !(unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei_str(
                          v50 + 728,
                          v52,
                          **(_QWORD **)(v50 + 728),
                          L"memcpy_inl",
                          v51) )
    {
      v49 = 2;
      goto LABEL_32;
    }
  }
  if ( v232 )
  {
    v49 = 3;
    goto LABEL_32;
  }
  if ( !v231 )
  {
    if ( !v235 )
    {
      v204 = 0;
      WinSAT::OpStatus::SetResult((char *)this + 400, 5, L"Internal Error", 0);
      SetLastError(0xDu);
      goto LABEL_131;
    }
    v49 = 5;
    goto LABEL_32;
  }
  v49 = 4;
LABEL_33:
  v219 = 0;
  v227 = 0;
  v53 = *((_QWORD *)this + 18);
  *((_QWORD *)this + 43) = v53 + 764;
  *((_QWORD *)this + 44) = v53 + 768;
  *((_QWORD *)this + 45) = v53 + 772;
  *((_QWORD *)this + 46) = v53 + 776;
  *((_QWORD *)this + 47) = v53 + 780;
  *((_QWORD *)this + 48) = v53 + 760;
  *((_DWORD *)this + 98) = *(_DWORD *)(v53 + 68);
  TickCount = GetTickCount();
  v55 = *((_QWORD *)this + 18);
  v238 = TickCount + (int)(*(double *)(v55 + 680) * 1000.0);
  v239 = TickCount + (int)(*(double *)(v55 + 688) * 1000.0);
  v221 = *(_BYTE *)(v55 + 696);
  v220 = 0;
  PerformanceCounter64 = mlib::QueryPerformanceCounter64((mlib *)v55);
  v229 = -1;
  v230 = 0;
  v228 = 0;
  v224 = *(_BYTE *)(*((_QWORD *)this + 18) + 697LL);
  *((_QWORD *)this + 38) = __rdtsc();
  while ( !WinSAT::OpMem1Thread::ExitLoop(this) || v221 )
  {
    v56 = *((_QWORD *)this + 19);
    v57 = (*((_QWORD *)this + 21) - v56) >> 3;
    if ( v57 < *((_QWORD *)this + 33) && (*((_QWORD *)this + 20) - v56) >> 3 >= v57 )
      SampleManager::GrowSizeBy((WinSAT::OpMem1Thread *)((char *)this + 152), 0x4000u);
    if ( !WinSAT::OpMem1Thread::Rendevous(this) )
      break;
    v218 = GetTickCount();
    v223 = 0;
    if ( v225 )
    {
      while ( 1 )
      {
        if ( v49 == 1 || v49 == 2 )
        {
          v226 = __rdtsc();
          memcpy_0(v234, v15, *((_QWORD *)this + 1));
          goto LABEL_51;
        }
        if ( v49 == 3 )
        {
          v226 = __rdtsc();
          v232(v15, v234, *((_QWORD *)this + 1), 1, v237);
          goto LABEL_51;
        }
        if ( v49 == 4 )
          break;
        if ( v49 == 5 )
        {
          v226 = __rdtsc();
          v235(v15, v234, *((_QWORD *)this + 1));
LABEL_51:
          v59 = __rdtsc();
          v58 = v226;
          goto LABEL_52;
        }
        v58 = 0;
        v226 = 0;
        v59 = 0;
LABEL_52:
        if ( !v220 )
        {
          SampleManager::AddSample((WinSAT::OpMem1Thread *)((char *)this + 152), v59 - v58);
          v227 += v59 - v226;
        }
        if ( !**((_DWORD **)this + 46) && !**((_DWORD **)this + 45) )
        {
          ++v223;
          v49 = v222;
          if ( v223 < v225 )
            continue;
        }
        goto LABEL_57;
      }
      v226 = __rdtsc();
      v231(v15, v234, *((_QWORD *)this + 1), 1);
      goto LABEL_51;
    }
LABEL_57:
    if ( **((_DWORD **)this + 46) || **((_DWORD **)this + 45) )
      break;
    if ( !v224 )
      Sleep(*(_DWORD *)(*((_QWORD *)this + 18) + 704LL));
    ++v228;
    v60 = GetTickCount() - v218;
    v61 = v230;
    if ( v60 > v230 )
      v61 = v60;
    v230 = v61;
    v62 = v229;
    if ( v60 < v229 )
      v62 = v60;
    v229 = v62;
    if ( v60 >= 0xA )
    {
      if ( v60 < 0x4B )
        v225 += v225 >> 1;
    }
    else
    {
      v225 *= 2;
    }
    v49 = v222;
    if ( !v220 && !v221 )
    {
      SampleManager::Process((WinSAT::OpMem1Thread *)((char *)this + 152), v233);
      if ( GetTickCount() >= (unsigned int)v238 && *((_BYTE *)this + 256) )
      {
        v38 = __rdtsc();
        _InterlockedAdd(*((volatile signed __int32 **)this + 48), 1u);
        goto LABEL_76;
      }
      if ( GetTickCount() >= (unsigned int)v239 )
      {
        _InterlockedAdd(*((volatile signed __int32 **)this + 48), 1u);
LABEL_76:
        v220 = 1;
      }
    }
  }
  if ( **((_DWORD **)this + 46) )
    goto LABEL_129;
  v63 = (mlib *)**((unsigned int **)this + 45);
  if ( (_DWORD)v63 )
    goto LABEL_129;
  v64 = mlib::QueryPerformanceCounter64(v63);
  *((_QWORD *)this + 39) = __rdtsc();
  PerformanceFrequency64 = mlib::QueryPerformanceFrequency64(v65);
  if ( PerformanceFrequency64 < 0 )
    v67 = (double)(int)(PerformanceFrequency64 & 1 | ((unsigned __int64)PerformanceFrequency64 >> 1))
        + (double)(int)(PerformanceFrequency64 & 1 | ((unsigned __int64)PerformanceFrequency64 >> 1));
  else
    v67 = (double)(int)PerformanceFrequency64;
  v68 = PerformanceCounter64;
  if ( PerformanceCounter64 < 0 )
    v69 = (double)(int)(PerformanceCounter64 & 1 | ((unsigned __int64)PerformanceCounter64 >> 1))
        + (double)(int)(PerformanceCounter64 & 1 | ((unsigned __int64)PerformanceCounter64 >> 1));
  else
    v69 = (double)(int)PerformanceCounter64;
  *((double *)this + 35) = v69 / v67;
  if ( v64 < 0 )
    v70 = (double)(int)(v64 & 1 | ((unsigned __int64)v64 >> 1)) + (double)(int)(v64 & 1 | ((unsigned __int64)v64 >> 1));
  else
    v70 = (double)(int)v64;
  *((double *)this + 36) = v70 / v67;
  v71 = v64 - v68;
  if ( v71 < 0 )
    v72 = (double)(int)(v71 & 1 | ((unsigned __int64)v71 >> 1)) + (double)(int)(v71 & 1 | ((unsigned __int64)v71 >> 1));
  else
    v72 = (double)(int)v71;
  v73 = v72 / v67;
  *((double *)this + 37) = v73;
  v74 = *((_QWORD *)this + 5);
  if ( v74 < 0 )
    v75 = (double)(int)(v74 & 1 | ((unsigned __int64)v74 >> 1)) + (double)(int)(v74 & 1 | ((unsigned __int64)v74 >> 1));
  else
    v75 = (double)(int)v74;
  v76 = *((_QWORD *)this + 38);
  v77 = *((_QWORD *)this + 39) - v76;
  if ( v77 < 0 )
    v78 = (double)(int)(v77 & 1 | ((unsigned __int64)v77 >> 1)) + (double)(int)(v77 & 1 | ((unsigned __int64)v77 >> 1));
  else
    v78 = (double)(int)v77;
  v79 = v78 / v75;
  *((double *)this + 40) = v79;
  if ( v38 )
  {
    v80 = v38 - v76;
    if ( v80 < 0 )
      v81 = (double)(int)(v80 & 1 | ((unsigned __int64)v80 >> 1))
          + (double)(int)(v80 & 1 | ((unsigned __int64)v80 >> 1));
    else
      v81 = (double)(int)v80;
    *((double *)this + 8) = v81 / v75;
  }
  v219 = COERCE_DOUBLE(COERCE_UNSIGNED_INT64(v79 - v73) & _xmm) > v73 / 1000.0 * 5.0;
  v82 = v227;
  v83 = (v227 & 0x8000000000000000uLL) != 0LL
      ? (double)(int)(v227 & 1 | (v227 >> 1)) + (double)(int)(v227 & 1 | (v227 >> 1))
      : (double)(int)v227;
  v84 = v83 / v75;
  *((double *)this + 7) = v84;
  v85 = (__int64)(*((_QWORD *)this + 20) - *((_QWORD *)this + 19)) >> 3;
  *((_QWORD *)this + 4) = v85;
  v86 = *((_QWORD *)this + 1);
  v87 = v86 < 0
      ? (double)(int)(v86 & 1 | ((unsigned __int64)v86 >> 1)) + (double)(int)(v86 & 1 | ((unsigned __int64)v86 >> 1))
      : (double)(int)v86;
  v88 = v85 < 0
      ? (double)(int)(v85 & 1 | ((unsigned __int64)v85 >> 1)) + (double)(int)(v85 & 1 | ((unsigned __int64)v85 >> 1))
      : (double)(int)v85;
  v89 = v88 * v87;
  *((double *)this + 6) = v89;
  v90 = *((_QWORD *)this + 25);
  v91 = v90 < 0
      ? (double)(int)(v90 & 1 | ((unsigned __int64)v90 >> 1)) + (double)(int)(v90 & 1 | ((unsigned __int64)v90 >> 1))
      : (double)(int)v90;
  v92 = v91 / v75;
  v93 = v87 + v87;
  v94 = *((_QWORD *)this + 29);
  v95 = v94 < 0
      ? (double)(int)(v94 & 1 | ((unsigned __int64)v94 >> 1)) + (double)(int)(v94 & 1 | ((unsigned __int64)v94 >> 1))
      : (double)(int)v94;
  *((double *)this + 9) = v93 / (v95 / v75);
  *((double *)this + 10) = v93 / v92;
  v96 = *((_QWORD *)this + 23);
  v97 = v96 < 0
      ? (double)(int)(v96 & 1 | ((unsigned __int64)v96 >> 1)) + (double)(int)(v96 & 1 | ((unsigned __int64)v96 >> 1))
      : (double)(int)v96;
  *((double *)this + 11) = v93 / (v97 / v75);
  v98 = *((_QWORD *)this + 24);
  v99 = v98 < 0
      ? (double)(int)(v98 & 1 | ((unsigned __int64)v98 >> 1)) + (double)(int)(v98 & 1 | ((unsigned __int64)v98 >> 1))
      : (double)(int)v98;
  *((double *)this + 12) = v93 / (v99 / v75);
  *((double *)this + 13) = (v89 + v89) / v84;
  if ( !*(_BYTE *)(*((_QWORD *)this + 18) + 33LL) )
  {
LABEL_129:
    v204 = v219;
  }
  else
  {
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
    v100 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*((_QWORD *)this + 16) + 240LL, L"> CPU(");
    v101 = std::basic_ostream<unsigned short>::operator<<(v100, *(unsigned int *)this);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v101, L")\n");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(
      *((_QWORD *)this + 16) + 240LL,
      L"  --                     elapsed ticks : ");
    v218 = 12;
    v102 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*((_QWORD *)this + 16) + 240LL, &v218);
    v103 = std::basic_ostream<unsigned short>::operator<<(v102, v82);
    *(_DWORD *)(*(int *)(*(_QWORD *)v103 + 4LL) + v103 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v103 + 4LL) + v103 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v103 + 4LL) + v103 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v103, "\n");
    v104 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --          cummulative copy seconds : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v104 + 4LL) + v104 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v104 + 4LL) + v104 + 32) = 9;
    *(_QWORD *)(*(int *)(*(_QWORD *)v104 + 4LL) + v104 + 40) = 10;
    v105 = std::basic_ostream<unsigned short>::operator<<(v104);
    *(_DWORD *)(*(int *)(*(_QWORD *)v105 + 4LL) + v105 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v105 + 4LL) + v105 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v105 + 4LL) + v105 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v105, L"\n");
    v106 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --               good data duration  : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v106 + 4LL) + v106 + 24) |= 0x2080u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v106 + 4LL) + v106 + 32) = 9;
    *(_QWORD *)(*(int *)(*(_QWORD *)v106 + 4LL) + v106 + 40) = 0;
    v107 = std::basic_ostream<unsigned short>::operator<<(v106);
    *(_DWORD *)(*(int *)(*(_QWORD *)v107 + 4LL) + v107 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v107 + 4LL) + v107 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v107 + 4LL) + v107 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v107, L"\n");
    v108 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                       min seconds : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v108 + 4LL) + v108 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v108 + 4LL) + v108 + 32) = 9;
    *(_QWORD *)(*(int *)(*(_QWORD *)v108 + 4LL) + v108 + 40) = 10;
    v109 = std::basic_ostream<unsigned short>::operator<<(v108);
    *(_DWORD *)(*(int *)(*(_QWORD *)v109 + 4LL) + v109 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v109 + 4LL) + v109 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v109 + 4LL) + v109 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v109, "\n");
    v110 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                 buffer copy count : ");
    v218 = 12;
    v111 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v110, &v218);
    v112 = std::basic_ostream<unsigned short>::operator<<(v111, *((_QWORD *)this + 4));
    *(_DWORD *)(*(int *)(*(_QWORD *)v112 + 4LL) + v112 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v112 + 4LL) + v112 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v112 + 4LL) + v112 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v112, L"\n");
    v113 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                               B/s : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v113 + 4LL) + v113 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v113 + 4LL) + v113 + 32) = 1;
    *(_QWORD *)(*(int *)(*(_QWORD *)v113 + 4LL) + v113 + 40) = 13;
    v114 = std::basic_ostream<unsigned short>::operator<<(v113);
    *(_DWORD *)(*(int *)(*(_QWORD *)v114 + 4LL) + v114 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v114 + 4LL) + v114 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v114 + 4LL) + v114 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v114, L"\n");
    v115 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                         B/s (min) : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v115 + 4LL) + v115 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v115 + 4LL) + v115 + 32) = 1;
    *(_QWORD *)(*(int *)(*(_QWORD *)v115 + 4LL) + v115 + 40) = 13;
    v116 = std::basic_ostream<unsigned short>::operator<<(v115);
    *(_DWORD *)(*(int *)(*(_QWORD *)v116 + 4LL) + v116 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v116 + 4LL) + v116 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v116 + 4LL) + v116 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v116, L"\n");
    v117 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                       B/s (median): ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v117 + 4LL) + v117 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v117 + 4LL) + v117 + 32) = 1;
    *(_QWORD *)(*(int *)(*(_QWORD *)v117 + 4LL) + v117 + 40) = 13;
    v118 = std::basic_ostream<unsigned short>::operator<<(v117);
    *(_DWORD *)(*(int *)(*(_QWORD *)v118 + 4LL) + v118 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v118 + 4LL) + v118 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v118 + 4LL) + v118 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v118, L"\n");
    v119 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                         B/s(mean) : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v119 + 4LL) + v119 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v119 + 4LL) + v119 + 32) = 1;
    *(_QWORD *)(*(int *)(*(_QWORD *)v119 + 4LL) + v119 + 40) = 13;
    v120 = std::basic_ostream<unsigned short>::operator<<(v119);
    *(_DWORD *)(*(int *)(*(_QWORD *)v120 + 4LL) + v120 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v120 + 4LL) + v120 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v120 + 4LL) + v120 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v120, L"\n");
    v121 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                       B/s (mean2) : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v121 + 4LL) + v121 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v121 + 4LL) + v121 + 32) = 1;
    *(_QWORD *)(*(int *)(*(_QWORD *)v121 + 4LL) + v121 + 40) = 13;
    v122 = std::basic_ostream<unsigned short>::operator<<(v121);
    *(_DWORD *)(*(int *)(*(_QWORD *)v122 + 4LL) + v122 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v122 + 4LL) + v122 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v122 + 4LL) + v122 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v122, L"\n");
    v123 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                      Elapsed Secs : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v123 + 4LL) + v123 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v123 + 4LL) + v123 + 32) = 9;
    *(_QWORD *)(*(int *)(*(_QWORD *)v123 + 4LL) + v123 + 40) = 21;
    v124 = std::basic_ostream<unsigned short>::operator<<(v123);
    *(_DWORD *)(*(int *)(*(_QWORD *)v124 + 4LL) + v124 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v124 + 4LL) + v124 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v124 + 4LL) + v124 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v124, L"\n");
    v125 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                RDTSC Elapsed Secs : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v125 + 4LL) + v125 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v125 + 4LL) + v125 + 32) = 9;
    *(_QWORD *)(*(int *)(*(_QWORD *)v125 + 4LL) + v125 + 40) = 21;
    v126 = std::basic_ostream<unsigned short>::operator<<(v125);
    *(_DWORD *)(*(int *)(*(_QWORD *)v126 + 4LL) + v126 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v126 + 4LL) + v126 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v126 + 4LL) + v126 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v126, L"\n");
    v127 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                         diff secs : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v127 + 4LL) + v127 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v127 + 4LL) + v127 + 32) = 9;
    *(_QWORD *)(*(int *)(*(_QWORD *)v127 + 4LL) + v127 + 40) = 21;
    v128 = std::basic_ostream<unsigned short>::operator<<(v127);
    *(_DWORD *)(*(int *)(*(_QWORD *)v128 + 4LL) + v128 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v128 + 4LL) + v128 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v128 + 4LL) + v128 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v128, "\n");
    v129 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                  max allowed diff : ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v129 + 4LL) + v129 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v129 + 4LL) + v129 + 32) = 9;
    *(_QWORD *)(*(int *)(*(_QWORD *)v129 + 4LL) + v129 + 40) = 21;
    v130 = std::basic_ostream<unsigned short>::operator<<(v129);
    *(_DWORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 40) = 0;
    v131 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*((_QWORD *)this + 16) + 240LL, L"  - ");
    v132 = L"Delta VIOLATION!";
    if ( !v219 )
      v132 = L"delta OK";
    v133 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v131, v132);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v133, L"\n");
    v134 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --             measurment loop count : ");
    v135 = std::basic_ostream<unsigned short>::operator<<(v134, v228);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, L"\n");
    v136 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                 sample block size : ");
    v137 = std::basic_ostream<unsigned short>::operator<<(v136, v225);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, L"\n");
    v138 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                 min loop duration : ");
    v139 = std::basic_ostream<unsigned short>::operator<<(v138, v229);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v139, L"\n");
    v140 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"  --                 max loop duration : ");
    v141 = std::basic_ostream<unsigned short>::operator<<(v140, v230);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v141, L"\n");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(
      *((_QWORD *)this + 16) + 240LL,
      L"  -- Statistics --\n");
    v142 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       + Total Samples : ");
    v218 = 12;
    v143 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, &v218);
    v144 = std::basic_ostream<unsigned short>::operator<<(
             v143,
             (__int64)(*((_QWORD *)this + 20) - *((_QWORD *)this + 19)) >> 3);
    *(_DWORD *)(*(int *)(*(_QWORD *)v144 + 4LL) + v144 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v144 + 4LL) + v144 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v144 + 4LL) + v144 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v144, "\n");
    v145 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +           min : ");
    v218 = 12;
    v146 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v145, &v218);
    v147 = std::basic_ostream<unsigned short>::operator<<(v146, *((_QWORD *)this + 25));
    *(_DWORD *)(*(int *)(*(_QWORD *)v147 + 4LL) + v147 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v147 + 4LL) + v147 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v147 + 4LL) + v147 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v147, "\n");
    v148 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +lower quartile : ");
    v218 = 12;
    v149 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v148, &v218);
    v150 = std::basic_ostream<unsigned short>::operator<<(v149, *((_QWORD *)this + 29));
    *(_DWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v150, "\n");
    v151 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +        median : ");
    v218 = 12;
    v152 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v151, &v218);
    v153 = std::basic_ostream<unsigned short>::operator<<(v152, *((_QWORD *)this + 23));
    *(_DWORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v153, "\n");
    v154 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +          mean : ");
    v218 = 12;
    v155 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v154, &v218);
    v156 = std::basic_ostream<unsigned short>::operator<<(v155, *((_QWORD *)this + 24));
    *(_DWORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v156, "\n");
    v157 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +upper quartile : ");
    v218 = 12;
    v158 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v157, &v218);
    v159 = std::basic_ostream<unsigned short>::operator<<(v158, *((_QWORD *)this + 28));
    *(_DWORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v159, "\n");
    v160 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +           max : ");
    v218 = 12;
    v161 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v160, &v218);
    v162 = std::basic_ostream<unsigned short>::operator<<(v161, *((_QWORD *)this + 26));
    *(_DWORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v162, "\n");
    v163 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +         range : ");
    v218 = 12;
    v164 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v163, &v218);
    v165 = std::basic_ostream<unsigned short>::operator<<(v164, *((_QWORD *)this + 27));
    *(_DWORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v165, "\n");
    v166 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +      IQ range : ");
    v218 = 12;
    v167 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v166, &v218);
    v168 = std::basic_ostream<unsigned short>::operator<<(v167, *((_QWORD *)this + 30));
    *(_DWORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v168, "\n");
    v169 = *((_QWORD *)this + 25);
    v170 = *((_QWORD *)this + 23);
    v227 = v170 - v169;
    v171 = *((_QWORD *)this + 29);
    v232 = (void (__fastcall *)(char *, void *, _QWORD, __int64, unsigned __int64))(v171 - v169);
    v231 = (void (__fastcall *)(char *, void *, _QWORD, __int64))(v170 - v171);
    v172 = v169 * (unsigned __int64)v233 / 0x186A0;
    v173 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +    median-Min : ");
    v218 = 12;
    v174 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v173, &v218);
    v175 = std::basic_ostream<unsigned short>::operator<<(v174, v227);
    *(_DWORD *)(*(int *)(*(_QWORD *)v175 + 4LL) + v175 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v175 + 4LL) + v175 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v175 + 4LL) + v175 + 40) = 0;
    v176 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v175, " ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v176 + 4LL) + v176 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v176 + 4LL) + v176 + 32) = 2;
    *(_QWORD *)(*(int *)(*(_QWORD *)v176 + 4LL) + v176 + 40) = 3;
    v177 = std::basic_ostream<unsigned short>::operator<<(v176);
    *(_DWORD *)(*(int *)(*(_QWORD *)v177 + 4LL) + v177 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v177 + 4LL) + v177 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v177 + 4LL) + v177 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v177, "% of min \n", v178);
    v179 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +        lq-Min : ");
    v218 = 12;
    v180 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v179, &v218);
    v181 = std::basic_ostream<unsigned short>::operator<<(v180, v232);
    *(_DWORD *)(*(int *)(*(_QWORD *)v181 + 4LL) + v181 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v181 + 4LL) + v181 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v181 + 4LL) + v181 + 40) = 0;
    v182 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v181, " ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v182 + 4LL) + v182 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v182 + 4LL) + v182 + 32) = 2;
    *(_QWORD *)(*(int *)(*(_QWORD *)v182 + 4LL) + v182 + 40) = 3;
    v183 = std::basic_ostream<unsigned short>::operator<<(v182);
    *(_DWORD *)(*(int *)(*(_QWORD *)v183 + 4LL) + v183 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v183 + 4LL) + v183 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v183 + 4LL) + v183 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v183, "% of min \n", v184);
    v185 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +     median-lq : ");
    v218 = 12;
    v186 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v185, &v218);
    v187 = std::basic_ostream<unsigned short>::operator<<(v186, v231);
    *(_DWORD *)(*(int *)(*(_QWORD *)v187 + 4LL) + v187 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v187 + 4LL) + v187 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v187 + 4LL) + v187 + 40) = 0;
    v188 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v187, " ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v188 + 4LL) + v188 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v188 + 4LL) + v188 + 32) = 2;
    *(_QWORD *)(*(int *)(*(_QWORD *)v188 + 4LL) + v188 + 40) = 3;
    v189 = std::basic_ostream<unsigned short>::operator<<(v188);
    *(_DWORD *)(*(int *)(*(_QWORD *)v189 + 4LL) + v189 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v189 + 4LL) + v189 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v189 + 4LL) + v189 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v189, "% of lq \n", v190);
    v191 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +         Limit : ");
    v218 = 12;
    v192 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v191, &v218);
    v193 = std::basic_ostream<unsigned short>::operator<<(v192, v172);
    v194 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v193, " ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v194 + 4LL) + v194 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v194 + 4LL) + v194 + 32) = 2;
    *(_QWORD *)(*(int *)(*(_QWORD *)v194 + 4LL) + v194 + 40) = 3;
    v195 = std::basic_ostream<unsigned short>::operator<<(v194);
    *(_DWORD *)(*(int *)(*(_QWORD *)v195 + 4LL) + v195 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v195 + 4LL) + v195 + 88) = 32;
    v196 = *(int *)(*(_QWORD *)v195 + 4LL);
    *(_QWORD *)(v196 + v195 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v195, "% of min \n", v196);
    v197 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +           Sum : ");
    v218 = 12;
    v198 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v197, &v218);
    v199 = std::basic_ostream<unsigned short>::operator<<(v198, *((_QWORD *)this + 22));
    *(_DWORD *)(*(int *)(*(_QWORD *)v199 + 4LL) + v199 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v199 + 4LL) + v199 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v199 + 4LL) + v199 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v199, "\n");
    v200 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             *((_QWORD *)this + 16) + 240LL,
             L"                       +        Status : ");
    v218 = 12;
    v201 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v200, &v218);
    v202 = L"GOOD";
    if ( !*((_BYTE *)this + 256) )
      v202 = L"BAD";
    v203 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v201, v202);
    *(_DWORD *)(*(int *)(*(_QWORD *)v203 + 4LL) + v203 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v203 + 4LL) + v203 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v203 + 4LL) + v203 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v203, "\n");
    std::endl(*((_QWORD *)this + 16) + 240LL);
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
    v204 = v219;
  }
LABEL_131:
  if ( !VirtualFree(v15, 0, 0x8000u) )
  {
    dwErrCode = GetLastError();
    v242 = 1;
    v243 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v5 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x488, 630, *(_DWORD *)this);
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
    v6 = *((_QWORD *)this + 17) + 240LL;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 18) + 776LL) )
  {
    v205 = 631;
    v206 = 1179;
    goto LABEL_137;
  }
  if ( *(int *)(*((_QWORD *)this + 18) + 772LL) <= 0 )
  {
    if ( v204 )
    {
      v209 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw)
           + 240;
      v210 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x4A9, 663, *(_DWORD *)this);
      v211 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v209, v210);
      std::endl(v211);
      *((_BYTE *)this + 336) = 1;
    }
    v207 = (_DWORD *)((char *)this + 400);
    *((_DWORD *)this + 100) = 6;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((char *)this + 408);
    *((_BYTE *)this + 416) = 0;
  }
  else
  {
    v205 = 632;
    v206 = 1184;
LABEL_137:
    v207 = (_DWORD *)((char *)this + 400);
    v208 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)v206, v205, *(_DWORD *)this);
    WinSAT::OpStatus::SetResult((char *)this + 400, 5, v208, 0);
  }
  v212 = *v207 != 6 ? 0xD : 0;
  SetLastError(v212);
  return v212;
}

```

## disassembly

```asm
0x140059ef4  mov     rax, rsp
0x140059ef7  mov     [rax+10h], rbx
0x140059efb  mov     [rax+18h], rsi
0x140059eff  push    rdi
0x140059f00  push    r12
0x140059f02  push    r13
0x140059f04  push    r14
0x140059f06  push    r15
0x140059f08  sub     rsp, 300h
0x140059f0f  movaps  xmmword ptr [rax-38h], xmm6
0x140059f13  movaps  xmmword ptr [rax-48h], xmm7
0x140059f17  movaps  xmmword ptr [rax-58h], xmm8
0x140059f1c  mov     rax, cs:__security_cookie
0x140059f23  xor     rax, rsp
0x140059f26  mov     [rsp+328h+var_68], rax
0x140059f2e  mov     rdi, rcx
0x140059f31  mov     [rsp+328h+var_298], rcx
0x140059f39  mov     rax, [rcx+90h]
0x140059f40  xor     r13d, r13d
0x140059f43  cmp     [rax+2E1h], r13b
0x140059f4a  jnz     loc_14005A071
0x140059f50  call    cs:__imp_GetCurrentThread
0x140059f56  mov     rcx, rax; hThread
0x140059f59  lea     edx, [r13+0Fh]; nPriority
0x140059f5d  call    cs:__imp_SetThreadPriority
0x140059f63  test    eax, eax
0x140059f65  jnz     loc_14005A047
0x140059f6b  mov     rax, [rdi+90h]
0x140059f72  lea     esi, [r13+1]
0x140059f76  lock add [rax+304h], esi
0x140059f7d  call    cs:__imp_GetLastError
0x140059f83  mov     [rsp+328h+dwErrCode], eax
0x140059f8a  mov     [rsp+328h+var_74], sil
0x140059f92  mov     [rsp+328h+var_70], r13
0x140059f9a  lea     rcx, [rsp+328h+Buffer]; lpBuffer
0x140059fa2  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140059fa7  mov     r8d, 270h; int
0x140059fad  lea     edx, [r8-18h]; char *
0x140059fb1  mov     r9d, [rdi]; unsigned __int16
0x140059fb4  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x140059fbb  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x140059fc0  mov     rbx, rax
0x140059fc3  mov     rcx, [rdi+78h]; lpCriticalSection
0x140059fc7  call    cs:__imp_EnterCriticalSection
0x140059fcd  mov     rcx, [rdi+88h]
0x140059fd4  add     rcx, 0F0h
0x140059fdb  mov     rdx, rbx
0x140059fde  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140059fe3  mov     edx, 0Ah
0x140059fe8  mov     rcx, rax
0x140059feb  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140059ff0  lea     rdx, [rsp+328h+Buffer]
0x140059ff8  mov     rcx, rax
0x140059ffb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a000  mov     rcx, rax
0x14005a003  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005a008  mov     rcx, [rdi+78h]; lpCriticalSection
0x14005a00c  call    cs:__imp_LeaveCriticalSection
0x14005a012  lea     rcx, [rdi+190h]
0x14005a019  lea     r9, [rsp+328h+Buffer]
0x14005a021  mov     r8, rbx
0x14005a024  mov     edx, 5
0x14005a029  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGAEBV?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>> const &)
0x14005a02e  mov     ecx, [rsp+328h+dwErrCode]; dwErrCode
0x14005a035  call    cs:__imp_SetLastError
0x14005a03b  mov     eax, [rsp+328h+dwErrCode]
0x14005a042  jmp     loc_14005C106
0x14005a047  call    cs:__imp_GetCurrentThread
0x14005a04d  mov     rcx, rax; hThread
0x14005a050  call    cs:__imp_GetThreadPriority
0x14005a056  mov     r9d, eax
0x14005a059  lea     r8, aAdjustedThePri; "Adjusted the priority of the Memory cop"...
0x14005a060  mov     edx, 262h
0x14005a065  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x14005a06c  call    Log_Text_F
0x14005a071  mov     esi, 1
0x14005a076  mov     ecx, esi; dwMilliseconds
0x14005a078  call    cs:__imp_Sleep
0x14005a07e  nop
0x14005a07f  lea     rcx, [rdi+98h]; this
0x14005a086  mov     edx, 4000h; unsigned __int64
0x14005a08b  call    ?ClearAndReserve@SampleManager@@QEAAX_K@Z; SampleManager::ClearAndReserve(unsigned __int64)
0x14005a090  nop
0x14005a091  mov     rcx, [rdi+8]
0x14005a095  mov     rax, [rdi+10h]
0x14005a099  lea     rdx, [rax+rcx*2]; dwSize
0x14005a09d  mov     [rsp+328h+var_2D8], rdx
0x14005a0a2  mov     rax, [rdi+90h]
0x14005a0a9  mov     cl, [rax+2E0h]
0x14005a0af  neg     cl
0x14005a0b1  sbb     r9d, r9d
0x14005a0b4  and     r9d, 200h
0x14005a0bb  mov     r12d, 4
0x14005a0c1  mov     [rsp+328h+var_2F0], r12d
0x14005a0c6  add     r9d, r12d; flProtect
0x14005a0c9  xor     ecx, ecx; lpAddress
0x14005a0cb  mov     r8d, 1000h; flAllocationType
0x14005a0d1  call    cs:__imp_VirtualAlloc
0x14005a0d7  mov     r15, rax
0x14005a0da  test    rax, rax
0x14005a0dd  jnz     short loc_14005A126
0x14005a0df  mov     rax, [rdi+90h]
0x14005a0e6  lock add [rax+304h], esi
0x14005a0ed  call    cs:__imp_GetLastError
0x14005a0f3  mov     [rsp+328h+dwErrCode], eax
0x14005a0fa  mov     [rsp+328h+var_74], sil
0x14005a102  mov     [rsp+328h+var_70], r13
0x14005a10a  lea     rcx, [rsp+328h+Buffer]; lpBuffer
0x14005a112  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14005a117  mov     r8d, 272h
0x14005a11d  lea     edx, [r8+2Ah]
0x14005a121  jmp     loc_140059FB1
0x14005a126  mov     [rdi+18h], r15
0x14005a12a  mov     rbx, [rdi+8]
0x14005a12e  mov     r14, [rdi+10h]
0x14005a132  mov     rdx, rbx; dwSize
0x14005a135  mov     rcx, r15; lpAddress
0x14005a138  call    cs:__imp_VirtualLock
0x14005a13e  test    eax, eax
0x14005a140  jnz     short loc_14005A19A
0x14005a142  mov     rax, [rdi+90h]
0x14005a149  lock add [rax+304h], esi
0x14005a150  call    cs:__imp_GetLastError
0x14005a156  mov     [rsp+328h+dwErrCode], eax
0x14005a15d  mov     [rsp+328h+var_74], sil
0x14005a165  mov     [rsp+328h+var_70], r13
0x14005a16d  lea     rcx, [rsp+328h+Buffer]; lpBuffer
0x14005a175  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14005a17a  xor     edx, edx; dwSize
0x14005a17c  mov     r8d, 8000h; dwFreeType
0x14005a182  mov     rcx, r15; lpAddress
0x14005a185  call    cs:__imp_VirtualFree
0x14005a18b  mov     r8d, 273h
0x14005a191  lea     edx, [r8+4Bh]
0x14005a195  jmp     loc_140059FB1
0x14005a19a  lea     rax, [r14+rbx]
0x14005a19e  add     rax, r15
0x14005a1a1  mov     [rsp+328h+var_2A8], rax
0x14005a1a9  mov     rdx, [rdi+8]; dwSize
0x14005a1ad  mov     rcx, rax; lpAddress
0x14005a1b0  call    cs:__imp_VirtualLock
0x14005a1b6  mov     rcx, [rdi+90h]
0x14005a1bd  test    eax, eax
0x14005a1bf  jnz     short loc_14005A212
0x14005a1c1  lock add [rcx+304h], esi
0x14005a1c8  call    cs:__imp_GetLastError
0x14005a1ce  mov     [rsp+328h+dwErrCode], eax
0x14005a1d5  mov     [rsp+328h+var_74], sil
0x14005a1dd  mov     [rsp+328h+var_70], r13
0x14005a1e5  lea     rcx, [rsp+328h+Buffer]; lpBuffer
0x14005a1ed  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14005a1f2  xor     edx, edx; dwSize
0x14005a1f4  mov     r8d, 8000h; dwFreeType
0x14005a1fa  mov     rcx, r15; lpAddress
0x14005a1fd  call    cs:__imp_VirtualFree
0x14005a203  mov     r8d, 274h
0x14005a209  lea     edx, [r8+60h]
0x14005a20d  jmp     loc_140059FB1
0x14005a212  mov     ebx, [rcx+2CCh]
0x14005a218  mov     eax, [rcx+2E8h]
0x14005a21e  mov     [rsp+328h+var_2E4], eax
0x14005a222  mov     eax, [rcx+2ECh]
0x14005a228  mov     [rsp+328h+var_2B0], eax
0x14005a22c  mov     [rsp+328h+var_2C0], r13
0x14005a231  mov     [rsp+328h+var_2B8], r13
0x14005a236  mov     [rsp+328h+var_2A0], r13
0x14005a23e  mov     [rdi+38h], r13
0x14005a242  mov     [rdi+48h], r13
0x14005a246  mov     [rdi+50h], r13
0x14005a24a  add     rcx, 2D8h
0x14005a251  lea     r9, [rsp+328h+var_2A0]
0x14005a259  lea     r8, [rsp+328h+var_2B8]
0x14005a25e  lea     rdx, [rsp+328h+var_2C0]
0x14005a263  call    GetFuncPtr
0x14005a268  mov     rcx, [rdi+90h]
0x14005a26f  add     rcx, 28h ; '('
0x14005a273  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14005a278  mov     rax, [rax]
0x14005a27b  mov     [rdi+28h], rax
0x14005a27f  mov     rax, [rdi+8]
0x14005a283  cmp     rbx, rax
0x14005a286  cmovbe  rax, rbx
0x14005a28a  mov     [rsp+328h+var_290], rax
0x14005a292  mov     rax, [rdi+90h]
0x14005a299  cmp     [rax+21h], r13b
0x14005a29d  jz      loc_14005A4C3
0x14005a2a3  mov     rcx, [rdi+78h]; lpCriticalSection
0x14005a2a7  call    cs:__imp_EnterCriticalSection
0x14005a2ad  mov     rcx, [rdi+80h]
0x14005a2b4  mov     r14d, 0F0h
0x14005a2ba  add     rcx, r14
0x14005a2bd  lea     rdx, aCpu; "> CPU("
0x14005a2c4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a2c9  mov     edx, [rdi]
0x14005a2cb  mov     rcx, rax
0x14005a2ce  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005a2d3  mov     rcx, rax
0x14005a2d6  lea     rdx, aTid; ")  TID: "
0x14005a2dd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a2e2  mov     [rsp+328h+var_2EC], r12d
0x14005a2e7  lea     rdx, [rsp+328h+var_2EC]
0x14005a2ec  mov     rcx, rax
0x14005a2ef  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzrightobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzrightobj const &)
0x14005a2f4  mov     rbx, rax
0x14005a2f7  call    cs:__imp_GetCurrentThreadId
0x14005a2fd  mov     edx, eax
0x14005a2ff  mov     rcx, rbx
0x14005a302  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005a307  mov     rcx, [rax]
0x14005a30a  movsxd  rdx, dword ptr [rcx+4]
0x14005a30e  mov     r13d, 201h
0x14005a314  or      [rdx+rax+18h], r13d
0x14005a319  mov     rcx, [rax]
0x14005a31c  movsxd  rdx, dword ptr [rcx+4]
0x14005a320  mov     ebx, 20h ; ' '
0x14005a325  mov     [rdx+rax+58h], bx
0x14005a32a  mov     rcx, [rax]
0x14005a32d  movsxd  rdx, dword ptr [rcx+4]
0x14005a331  mov     qword ptr [rdx+rax+28h], 0
0x14005a33a  lea     rdx, asc_14012B970; "\n"
0x14005a341  mov     rcx, rax
0x14005a344  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a349  mov     rcx, rax
0x14005a34c  lea     rdx, aRunningAt; "  -- Running at "
0x14005a353  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a358  mov     rcx, [rdi+90h]
0x14005a35f  lea     r8, aHigh; "HIGH"
0x14005a366  lea     rdx, aNormal_1; "NORMAL"
0x14005a36d  cmp     byte ptr [rcx+2E1h], 0
0x14005a374  cmovz   rdx, r8
0x14005a378  mov     rcx, rax
0x14005a37b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a380  mov     rcx, rax
0x14005a383  lea     rdx, aPriority; " priority\n"
0x14005a38a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a38f  mov     rcx, rax
0x14005a392  lea     rdx, aAllocated; "  -- Allocated "
0x14005a399  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a39e  mov     rdx, [rsp+328h+var_2D8]
0x14005a3a3  mov     rcx, rax
0x14005a3a6  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x14005a3ab  mov     rcx, rax
0x14005a3ae  lea     rdx, a0x_0; " (0x"
0x14005a3b5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a3ba  mov     [rsp+328h+var_2EC], r12d
0x14005a3bf  lea     rdx, [rsp+328h+var_2EC]
0x14005a3c4  mov     rcx, rax
0x14005a3c7  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzhexobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzhexobj const &)
0x14005a3cc  mov     rdx, [rsp+328h+var_2D8]
0x14005a3d1  mov     rcx, rax
0x14005a3d4  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x14005a3d9  mov     rcx, [rax]
0x14005a3dc  movsxd  rdx, dword ptr [rcx+4]
0x14005a3e0  or      [rdx+rax+18h], r13d
0x14005a3e5  mov     rcx, [rax]
0x14005a3e8  movsxd  rdx, dword ptr [rcx+4]
0x14005a3ec  mov     [rdx+rax+58h], bx
0x14005a3f1  mov     rcx, [rax]
0x14005a3f4  movsxd  rdx, dword ptr [rcx+4]
0x14005a3f8  xor     r12d, r12d
0x14005a3fb  mov     [rdx+rax+28h], r12
0x14005a400  lea     rdx, aBytes_2; ") bytes\n"
0x14005a407  mov     rcx, rax
0x14005a40a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a40f  mov     rcx, rax
0x14005a412  lea     rdx, aAffinityMask_0; "  -- Affinity Mask "
0x14005a419  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a41e  mov     [rsp+328h+var_2EC], 8
0x14005a426  lea     rdx, [rsp+328h+var_2EC]
0x14005a42b  mov     rcx, rax
0x14005a42e  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzhexobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzhexobj const &)
0x14005a433  mov     edx, [rdi+110h]
0x14005a439  mov     rcx, rax
0x14005a43c  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005a441  mov     rcx, [rax]
0x14005a444  movsxd  rdx, dword ptr [rcx+4]
0x14005a448  or      [rdx+rax+18h], r13d
0x14005a44d  mov     rcx, [rax]
0x14005a450  movsxd  rdx, dword ptr [rcx+4]
0x14005a454  mov     [rdx+rax+58h], bx
0x14005a459  mov     rcx, [rax]
0x14005a45c  movsxd  rdx, dword ptr [rcx+4]
0x14005a460  mov     [rdx+rax+28h], r12
0x14005a465  lea     rdx, asc_14012B93C; "\n"
0x14005a46c  mov     rcx, rax
0x14005a46f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005a474  mov     rcx, rax
0x14005a477  lea     rdx, aCopyRoutine; "  -- Copy Routine = "
0x14005a47e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a483  mov     rdx, [rdi+90h]
0x14005a48a  add     rdx, 2D8h
0x14005a491  mov     rcx, rax
0x14005a494  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005a499  mov     rcx, rax
0x14005a49c  lea     rdx, asc_14012B93C; "\n"
0x14005a4a3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005a4a8  mov     rcx, [rdi+80h]
0x14005a4af  add     rcx, r14
0x14005a4b2  call    ?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x14005a4b7  mov     rcx, [rdi+78h]; lpCriticalSection
  ... truncated ...
```
