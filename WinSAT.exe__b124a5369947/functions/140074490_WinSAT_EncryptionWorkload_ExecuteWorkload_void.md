# WinSAT::EncryptionWorkload::ExecuteWorkload(void)

- ea: `0x140074490`
- end: `0x140076166`
- name: `?ExecuteWorkload@EncryptionWorkload@WinSAT@@MEAAKXZ`
- size: `7382`
- prototype: `unsigned int __fastcall(WinSAT::EncryptionWorkload *__hidden this)`
- caller_count: `0`
- callee_count: `30`
- tags: ``

## callees

- `0x140003560`
- `0x140004170`
- `0x140004348`
- `0x14000449c`
- `0x140005cf4`
- `0x140005f4c`
- `0x14000695c`
- `0x140008178`
- `0x1400083a4`
- `0x1400085b4`
- `0x140011f58`
- `0x140015ccc`
- `0x140016588`
- `0x140016d04`
- `0x140017af0`
- `0x140019a1c`
- `0x14002093c`
- `0x14003a150`
- `0x140058488`
- `0x1400584b0`
- `0x140058818`
- `0x140059010`
- `0x14005cc74`
- `0x14005ed80`
- `0x140074340`
- `0x140074490`
- `0x14007616c`
- `0x1400761b4`
- `0x140079b30`
- `0x140118008`

## import_xrefs

- `ADVAPI32!CryptEncrypt` at `0x140074704`
- `ADVAPI32!CryptEncrypt` at `0x140074704`
- `ADVAPI32!CryptDecrypt` at `0x140074737`
- `ADVAPI32!CryptDecrypt` at `0x140074737`
- `ADVAPI32!CryptCreateHash` at `0x140074772`
- `ADVAPI32!CryptCreateHash` at `0x140074772`
- `ADVAPI32!CryptHashData` at `0x14007478e`
- `ADVAPI32!CryptHashData` at `0x14007478e`
- `ADVAPI32!CryptDestroyHash` at `0x1400747a1`
- `ADVAPI32!CryptDestroyHash` at `0x1400747a1`
- `KERNEL32!GetTickCount` at `0x1400744ec`
- `KERNEL32!GetTickCount` at `0x1400745e2`
- `KERNEL32!GetTickCount` at `0x140074991`
- `KERNEL32!GetTickCount` at `0x1400749e2`
- `KERNEL32!GetTickCount` at `0x140074a12`
- `KERNEL32!GetTickCount` at `0x1400744ec`
- `KERNEL32!GetTickCount` at `0x1400745e2`
- `KERNEL32!GetTickCount` at `0x140074991`
- `KERNEL32!GetTickCount` at `0x1400749e2`
- `KERNEL32!GetTickCount` at `0x140074a12`
- `KERNEL32!EnterCriticalSection` at `0x1400747dd`
- `KERNEL32!EnterCriticalSection` at `0x1400748ca`
- `KERNEL32!EnterCriticalSection` at `0x140074dde`
- `KERNEL32!EnterCriticalSection` at `0x140076018`
- `KERNEL32!EnterCriticalSection` at `0x1400747dd`
- `KERNEL32!EnterCriticalSection` at `0x1400748ca`
- `KERNEL32!EnterCriticalSection` at `0x140074dde`
- `KERNEL32!EnterCriticalSection` at `0x140076018`
- `KERNEL32!LeaveCriticalSection` at `0x14007484a`
- `KERNEL32!LeaveCriticalSection` at `0x140074937`
- `KERNEL32!LeaveCriticalSection` at `0x140076009`
- `KERNEL32!LeaveCriticalSection` at `0x14007611f`
- `KERNEL32!LeaveCriticalSection` at `0x14007484a`
- `KERNEL32!LeaveCriticalSection` at `0x140074937`
- `KERNEL32!LeaveCriticalSection` at `0x140076009`
- `KERNEL32!LeaveCriticalSection` at `0x14007611f`
- `KERNEL32!GetLastError` at `0x140074a35`
- `KERNEL32!GetLastError` at `0x140074a35`
- `KERNEL32!Sleep` at `0x140074987`
- `KERNEL32!Sleep` at `0x140074987`
- `KERNEL32!SetLastError` at `0x140076132`
- `KERNEL32!SetLastError` at `0x140076132`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
DWORD __fastcall WinSAT::EncryptionWorkload::ExecuteWorkload(WinSAT::EncryptionWorkload *this)
{
  __int64 v2; // r15
  _DWORD *v3; // rax
  DWORD v4; // r13d
  DWORD TickCount; // eax
  __int64 v6; // rdx
  char v7; // di
  __int64 v8; // r14
  unsigned __int64 v9; // rsi
  __int64 PerformanceCounter64; // r12
  unsigned __int64 v11; // rcx
  DWORD i; // eax
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // rax
  int v15; // ecx
  int v16; // r8d
  unsigned __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  DWORD v25; // eax
  DWORD LastError; // eax
  mlib *v28; // rcx
  __int64 v29; // rdi
  mlib *v30; // rcx
  __int64 PerformanceFrequency64; // rax
  double v32; // xmm1_8
  double v33; // xmm0_8
  double v34; // xmm0_8
  __int64 v35; // rdi
  double v36; // xmm6_8
  double v37; // xmm6_8
  __int64 v38; // rcx
  double v39; // xmm2_8
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  double v43; // xmm7_8
  double v44; // xmm7_8
  __int64 v45; // rsi
  double v46; // xmm0_8
  double v47; // xmm3_8
  double v48; // xmm3_8
  __int64 v49; // rcx
  double v50; // xmm0_8
  __int64 v51; // rax
  double v52; // xmm4_8
  __int64 v53; // rcx
  double v54; // xmm8_8
  __int64 v55; // rax
  double v56; // xmm8_8
  __int64 v57; // rcx
  double v58; // xmm9_8
  __int64 v59; // rax
  double v60; // xmm5_8
  __int64 v61; // rcx
  double v62; // xmm1_8
  __int64 v63; // rax
  __int64 v64; // rcx
  double v65; // xmm0_8
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rax
  const wchar_t *v106; // rdx
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
  __int64 v132; // rax
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
  __int64 v143; // rcx
  __int64 v144; // r15
  __int64 v145; // rsi
  __int64 v146; // r14
  unsigned __int64 v147; // rdi
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // r8
  __int64 v152; // rax
  int v153; // r8d
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // r8
  __int64 v158; // rax
  int v159; // r8d
  __int64 v160; // rax
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // r8
  __int64 v164; // rax
  int v165; // r8d
  __int64 v166; // rax
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // r8
  __int64 v170; // rax
  __int64 v171; // r8
  __int64 v172; // rax
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  const wchar_t *v177; // rdx
  __int64 v178; // rax
  __int64 v179; // rax
  _DWORD *v180; // rdi
  __int64 *v181; // rcx
  __int64 v182; // rax
  __int64 v183; // rdx
  __int64 v184; // rax
  DWORD v185; // ebx
  DWORD pdwDataLen[2]; // [rsp+48h] [rbp-C0h] BYREF
  HCRYPTHASH phHash; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v188; // [rsp+58h] [rbp-B0h]
  unsigned int v189; // [rsp+5Ch] [rbp-ACh]
  unsigned int v190; // [rsp+60h] [rbp-A8h]
  unsigned int v191; // [rsp+64h] [rbp-A4h]
  int v192; // [rsp+68h] [rbp-A0h]
  unsigned int v193; // [rsp+6Ch] [rbp-9Ch]
  DWORD v194; // [rsp+70h] [rbp-98h]
  _BYTE v195[8]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v196[8]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v197; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v198; // [rsp+90h] [rbp-78h]
  __int64 v199; // [rsp+98h] [rbp-70h] BYREF
  __int64 v200; // [rsp+A0h] [rbp-68h]
  __int64 v201; // [rsp+A8h] [rbp-60h]
  _BYTE v202[112]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v203; // [rsp+168h] [rbp+60h] BYREF
  __int64 v204; // [rsp+170h] [rbp+68h] BYREF
  char v205; // [rsp+178h] [rbp+70h]
  unsigned __int64 v206; // [rsp+180h] [rbp+78h]

  v2 = 0;
  v3 = (_DWORD *)*((_QWORD *)this + 106);
  v193 = v3[2091];
  v4 = v3[2092];
  v191 = v3[2093];
  pdwDataLen[0] = 0;
  TickCount = GetTickCount();
  v6 = *((_QWORD *)this + 106);
  v200 = TickCount + (int)(*(double *)(v6 + 8344) * 1000.0);
  v201 = TickCount + (int)(*(double *)(v6 + 8352) * 1000.0);
  v7 = *(_BYTE *)(v6 + 8360);
  LOBYTE(v204) = v7;
  v8 = 0;
  LOBYTE(v203) = 0;
  v9 = 0;
  v189 = -1;
  v190 = 0;
  v188 = 0;
  v205 = *(_BYTE *)(v6 + 8378);
  PerformanceCounter64 = mlib::QueryPerformanceCounter64(0);
  *((_QWORD *)this + 99) = __rdtsc();
  while ( !WinSAT::MPWorkload::ExitLoop(this) && !v7 )
  {
    v11 = (__int64)(*((_QWORD *)this + 83) - *((_QWORD *)this + 81)) >> 3;
    if ( v11 < *((_QWORD *)this + 95) && (__int64)(*((_QWORD *)this + 82) - *((_QWORD *)this + 81)) >> 3 >= v11 )
      SampleManager::GrowSizeBy((WinSAT::EncryptionWorkload *)((char *)this + 648), v193);
    if ( !WinSAT::MPWorkload::Rendevous(this) )
      break;
    v194 = GetTickCount();
    for ( i = 0; ; i = pdwDataLen[1] + 1 )
    {
      pdwDataLen[1] = i;
      if ( i >= v4 )
        goto LABEL_38;
      pdwDataLen[0] = *((_DWORD *)this + 244);
      if ( **((_DWORD **)this + 4) || **((_DWORD **)this + 8) )
        goto LABEL_38;
      v13 = RotatingBuffer::RotateBuffer((WinSAT::EncryptionWorkload *)((char *)this + 856));
      *((_QWORD *)this + 123) = v13;
      if ( !v13
        || (v14 = RotatingBuffer::RotateBuffer((WinSAT::EncryptionWorkload *)((char *)this + 904)),
            (*((_QWORD *)this + 124) = v14) == 0) )
      {
        LastError = GetLastError();
        return WinSAT::EncryptionWorkload::DumpRotateBufferError(this, LastError);
      }
      LODWORD(phHash) = 0;
      v192 = 0;
      memcpy_0(v14, *((const void **)this + 123), *((unsigned int *)this + 244));
      v15 = *((_DWORD *)this + 238);
      if ( v15 == 2 )
      {
        pdwDataLen[0] = *((_DWORD *)this + 252);
        v198 = __rdtsc();
        XpressCrc32(*((_QWORD *)this + 124), *((unsigned int *)this + 252));
        v16 = 1;
        LODWORD(phHash) = 1;
        goto LABEL_27;
      }
      v198 = __rdtsc();
      if ( v15 )
      {
        if ( v15 == 1 )
        {
          phHash = 0;
          CryptCreateHash(*((_QWORD *)this + 120), 0x8004u, 0, 0, &phHash);
          LODWORD(v206) = CryptHashData(phHash, *((const BYTE **)this + 124), *((_DWORD *)this + 252), 0);
          if ( phHash )
            CryptDestroyHash(phHash);
          LODWORD(phHash) = 1;
        }
        else
        {
          LODWORD(v206) = 0;
        }
      }
      else
      {
        LODWORD(v206) = CryptEncrypt(
                          *((_QWORD *)this + 121),
                          0,
                          1,
                          0,
                          *((BYTE **)this + 124),
                          pdwDataLen,
                          *((_DWORD *)this + 252));
        if ( !(_DWORD)v206 )
        {
          v16 = 0;
          goto LABEL_27;
        }
        LODWORD(phHash) = CryptDecrypt(*((_QWORD *)this + 121), 0, 1, 0, *((BYTE **)this + 124), pdwDataLen);
      }
      v16 = v206;
LABEL_27:
      v17 = __rdtsc();
      v206 = v17;
      v8 += pdwDataLen[0];
      if ( !v16 )
      {
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        v18 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v202, 0x217u);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          &v197,
          v18);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v195,
          1024);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
          v195,
          *(_QWORD *)(v197 + 24),
          pdwDataLen[1],
          *((unsigned int *)this + 22));
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          *((_QWORD *)this + 2) + 240LL,
          v195);
        std::endl(v19);
        LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        v192 = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v195);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v197);
        v17 = v206;
      }
      if ( !(_DWORD)phHash )
        break;
      if ( v192 )
        goto LABEL_37;
      if ( !(_BYTE)v203 )
      {
        v206 = v17 - v198;
        SampleManager::AddSample((WinSAT::EncryptionWorkload *)((char *)this + 648), v17 - v198);
        v2 += v206;
      }
      if ( **((_DWORD **)this + 4) || **((_DWORD **)this + 8) )
        goto LABEL_38;
    }
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
    v20 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v202, 0x218u);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v199,
      v20);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v196,
      1024);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
      v196,
      *(_QWORD *)(v199 + 24),
      pdwDataLen[1],
      *((unsigned int *)this + 22));
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      *((_QWORD *)this + 2) + 240LL,
      v196);
    std::endl(v21);
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v196);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v199);
LABEL_37:
    _InterlockedIncrement(*((volatile signed __int32 **)this + 4));
LABEL_38:
    if ( **((_DWORD **)this + 4) || **((_DWORD **)this + 8) )
      break;
    if ( !v205 )
      Sleep(*(_DWORD *)(*((_QWORD *)this + 106) + 8332LL));
    ++v188;
    v22 = GetTickCount() - v194;
    v23 = v190;
    if ( v22 > v190 )
      v23 = v22;
    v190 = v23;
    v24 = v189;
    if ( v22 < v189 )
      v24 = v22;
    v189 = v24;
    if ( v22 >= 0xA )
    {
      if ( v22 < 0x4B )
        v4 += v4 >> 1;
    }
    else
    {
      v4 *= 2;
    }
    if ( (_BYTE)v203 )
      goto LABEL_2;
    SampleManager::Process((WinSAT::EncryptionWorkload *)((char *)this + 648), v191);
    if ( GetTickCount() >= (unsigned int)v200 && *((_BYTE *)this + 752) )
    {
      v9 = __rdtsc();
      LOBYTE(v203) = 1;
      _InterlockedIncrement(*((volatile signed __int32 **)this + 7));
LABEL_2:
      v7 = v204;
      continue;
    }
    v25 = GetTickCount();
    v7 = v204;
    if ( v25 >= (unsigned int)v201 )
    {
      LOBYTE(v203) = 1;
      _InterlockedIncrement(*((volatile signed __int32 **)this + 7));
    }
  }
  if ( !**((_DWORD **)this + 4) )
  {
    v28 = (mlib *)**((unsigned int **)this + 8);
    if ( !(_DWORD)v28 )
    {
      if ( !*((_BYTE *)this + 753) )
        SampleManager::Process((WinSAT::EncryptionWorkload *)((char *)this + 648), v191);
      v29 = mlib::QueryPerformanceCounter64(v28);
      *((_QWORD *)this + 100) = __rdtsc();
      PerformanceFrequency64 = mlib::QueryPerformanceFrequency64(v30);
      if ( PerformanceFrequency64 < 0 )
        v32 = (double)(int)(PerformanceFrequency64 & 1 | ((unsigned __int64)PerformanceFrequency64 >> 1))
            + (double)(int)(PerformanceFrequency64 & 1 | ((unsigned __int64)PerformanceFrequency64 >> 1));
      else
        v32 = (double)(int)PerformanceFrequency64;
      if ( PerformanceCounter64 < 0 )
        v33 = (double)(int)(PerformanceCounter64 & 1 | ((unsigned __int64)PerformanceCounter64 >> 1))
            + (double)(int)(PerformanceCounter64 & 1 | ((unsigned __int64)PerformanceCounter64 >> 1));
      else
        v33 = (double)(int)PerformanceCounter64;
      *((double *)this + 135) = v33 / v32;
      if ( v29 < 0 )
        v34 = (double)(int)(v29 & 1 | ((unsigned __int64)v29 >> 1))
            + (double)(int)(v29 & 1 | ((unsigned __int64)v29 >> 1));
      else
        v34 = (double)(int)v29;
      *((double *)this + 136) = v34 / v32;
      v35 = v29 - PerformanceCounter64;
      if ( v35 < 0 )
        v36 = (double)(int)(v35 & 1 | ((unsigned __int64)v35 >> 1))
            + (double)(int)(v35 & 1 | ((unsigned __int64)v35 >> 1));
      else
        v36 = (double)(int)v35;
      v37 = v36 / v32;
      *((double *)this + 137) = v37;
      v38 = *((_QWORD *)this + 105);
      if ( v38 < 0 )
      {
        v40 = *((_QWORD *)this + 105) & 1LL | ((unsigned __int64)v38 >> 1);
        v39 = (double)(int)v40 + (double)(int)v40;
      }
      else
      {
        v39 = (double)(int)v38;
      }
      v41 = *((_QWORD *)this + 99);
      v42 = *((_QWORD *)this + 100) - v41;
      if ( v42 < 0 )
        v43 = (double)(int)(v42 & 1 | ((unsigned __int64)v42 >> 1))
            + (double)(int)(v42 & 1 | ((unsigned __int64)v42 >> 1));
      else
        v43 = (double)(int)v42;
      v44 = v43 / v39;
      *((double *)this + 138) = v44;
      if ( v9 )
      {
        v45 = v9 - v41;
        if ( v45 < 0 )
          v46 = (double)(int)(v45 & 1 | ((unsigned __int64)v45 >> 1))
              + (double)(int)(v45 & 1 | ((unsigned __int64)v45 >> 1));
        else
          v46 = (double)(int)v45;
        *((double *)this + 139) = v46 / v39;
      }
      *((_BYTE *)this + 808) = COERCE_DOUBLE(COERCE_UNSIGNED_INT64(v44 - v37) & _xmm) > v37 / 1000.0 * 5.0;
      if ( v2 < 0 )
        v47 = (double)(int)(v2 & 1 | ((unsigned __int64)v2 >> 1)) + (double)(int)(v2 & 1 | ((unsigned __int64)v2 >> 1));
      else
        v47 = (double)(int)v2;
      v48 = v47 / v39;
      *((double *)this + 129) = v48;
      v49 = (__int64)(*((_QWORD *)this + 82) - *((_QWORD *)this + 81)) >> 3;
      if ( v49 < 0 )
      {
        v51 = ((__int64)(*((_QWORD *)this + 82) - *((_QWORD *)this + 81)) >> 3) & 1 | ((unsigned __int64)v49 >> 1);
        v50 = (double)(int)v51 + (double)(int)v51;
      }
      else
      {
        v50 = (double)(int)v49;
      }
      *((double *)this + 130) = v50;
      if ( v8 < 0 )
        v52 = (double)(int)(v8 & 1 | ((unsigned __int64)v8 >> 1)) + (double)(int)(v8 & 1 | ((unsigned __int64)v8 >> 1));
      else
        v52 = (double)(int)v8;
      *((double *)this + 131) = v52;
      v53 = *((_QWORD *)this + 87);
      if ( v53 < 0 )
      {
        v55 = *((_QWORD *)this + 87) & 1LL | ((unsigned __int64)v53 >> 1);
        v54 = (double)(int)v55 + (double)(int)v55;
      }
      else
      {
        v54 = (double)(int)v53;
      }
      v56 = v54 / v39;
      v57 = *((_QWORD *)this + 91);
      if ( v57 < 0 )
      {
        v59 = *((_QWORD *)this + 91) & 1LL | ((unsigned __int64)v57 >> 1);
        v58 = (double)(int)v59 + (double)(int)v59;
      }
      else
      {
        v58 = (double)(int)v57;
      }
      v60 = (double)*((int *)this + 252);
      *((double *)this + 103) = v60 / (v58 / v39);
      *((double *)this + 132) = v60 / v56;
      v61 = *((_QWORD *)this + 85);
      if ( v61 < 0 )
      {
        v63 = *((_QWORD *)this + 85) & 1LL | ((unsigned __int64)v61 >> 1);
        v62 = (double)(int)v63 + (double)(int)v63;
      }
      else
      {
        v62 = (double)(int)v61;
      }
      *((double *)this + 133) = v60 / (v62 / v39);
      v64 = *((_QWORD *)this + 86);
      if ( v64 < 0 )
      {
        v66 = *((_QWORD *)this + 86) & 1LL | ((unsigned __int64)v64 >> 1);
        v65 = (double)(int)v66 + (double)(int)v66;
      }
      else
      {
        v65 = (double)(int)v64;
      }
      *((double *)this + 104) = v60 / (v65 / v39);
      *((double *)this + 134) = v52 / v48;
      if ( *((_BYTE *)this + 24) )
      {
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*((_QWORD *)this + 1) + 240LL, L"> CPU(");
        v68 = std::basic_ostream<unsigned short>::operator<<(v67, *((unsigned int *)this + 22));
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v68, L")\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          v69,
          L"  --                     elapsed ticks : ");
        LODWORD(v203) = 12;
        v71 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v70, &v203);
        v72 = std::basic_ostream<unsigned short>::operator<<(v71, v2);
        *(_DWORD *)(*(int *)(*(_QWORD *)v72 + 4LL) + v72 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v72 + 4LL) + v72 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v72 + 4LL) + v72 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v72, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --               cummulative seconds : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v73 + 4LL) + v73 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v73 + 4LL) + v73 + 32) = 9;
        *(_QWORD *)(*(int *)(*(_QWORD *)v73 + 4LL) + v73 + 40) = 0;
        v74 = std::basic_ostream<unsigned short>::operator<<(v73);
        *(_DWORD *)(*(int *)(*(_QWORD *)v74 + 4LL) + v74 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v74 + 4LL) + v74 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v74 + 4LL) + v74 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v74, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --               good data duration  : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v75 + 4LL) + v75 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v75 + 4LL) + v75 + 32) = 9;
        *(_QWORD *)(*(int *)(*(_QWORD *)v75 + 4LL) + v75 + 40) = 0;
        v76 = std::basic_ostream<unsigned short>::operator<<(v75);
        *(_DWORD *)(*(int *)(*(_QWORD *)v76 + 4LL) + v76 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v76 + 4LL) + v76 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v76 + 4LL) + v76 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v76, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                      cipher size  : ");
        LODWORD(v203) = 12;
        v78 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v77, &v203);
        v79 = std::basic_ostream<unsigned short>::operator<<(v78, *((unsigned int *)this + 252));
        *(_DWORD *)(*(int *)(*(_QWORD *)v79 + 4LL) + v79 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v79 + 4LL) + v79 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v79 + 4LL) + v79 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v79, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --               Measured Value Secs : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v80 + 4LL) + v80 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v80 + 4LL) + v80 + 32) = 9;
        *(_QWORD *)(*(int *)(*(_QWORD *)v80 + 4LL) + v80 + 40) = 0;
        v81 = std::basic_ostream<unsigned short>::operator<<(v80);
        *(_DWORD *)(*(int *)(*(_QWORD *)v81 + 4LL) + v81 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v81 + 4LL) + v81 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v81 + 4LL) + v81 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v81, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                       min seconds : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v82 + 4LL) + v82 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v82 + 4LL) + v82 + 32) = 9;
        *(_QWORD *)(*(int *)(*(_QWORD *)v82 + 4LL) + v82 + 40) = 0;
        v83 = std::basic_ostream<unsigned short>::operator<<(v82);
        *(_DWORD *)(*(int *)(*(_QWORD *)v83 + 4LL) + v83 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v83 + 4LL) + v83 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v83 + 4LL) + v83 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v83, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                 buffer pass count : ");
        LODWORD(v203) = 12;
        v85 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v84, &v203);
        v86 = std::basic_ostream<unsigned short>::operator<<(v85);
        *(_DWORD *)(*(int *)(*(_QWORD *)v86 + 4LL) + v86 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v86 + 4LL) + v86 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v86 + 4LL) + v86 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v86, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --             total bytes processed : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v87 + 4LL) + v87 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v87 + 4LL) + v87 + 32) = 0;
        *(_QWORD *)(*(int *)(*(_QWORD *)v87 + 4LL) + v87 + 40) = 0;
        v88 = std::basic_ostream<unsigned short>::operator<<(v87);
        *(_DWORD *)(*(int *)(*(_QWORD *)v88 + 4LL) + v88 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v88 + 4LL) + v88 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v88 + 4LL) + v88 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v88, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                               B/s : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v89 + 4LL) + v89 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v89 + 4LL) + v89 + 32) = 0;
        *(_QWORD *)(*(int *)(*(_QWORD *)v89 + 4LL) + v89 + 40) = 0;
        v90 = std::basic_ostream<unsigned short>::operator<<(v89);
        *(_DWORD *)(*(int *)(*(_QWORD *)v90 + 4LL) + v90 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v90 + 4LL) + v90 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v90 + 4LL) + v90 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v90, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                      B/s (median) : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v91 + 4LL) + v91 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v91 + 4LL) + v91 + 32) = 0;
        *(_QWORD *)(*(int *)(*(_QWORD *)v91 + 4LL) + v91 + 40) = 0;
        v92 = std::basic_ostream<unsigned short>::operator<<(v91);
        *(_DWORD *)(*(int *)(*(_QWORD *)v92 + 4LL) + v92 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v92 + 4LL) + v92 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v92 + 4LL) + v92 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v92, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                         B/s(mean) : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v93 + 4LL) + v93 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v93 + 4LL) + v93 + 32) = 0;
        *(_QWORD *)(*(int *)(*(_QWORD *)v93 + 4LL) + v93 + 40) = 0;
        v94 = std::basic_ostream<unsigned short>::operator<<(v93);
        *(_DWORD *)(*(int *)(*(_QWORD *)v94 + 4LL) + v94 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v94 + 4LL) + v94 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v94 + 4LL) + v94 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v94, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                       B/s (mean2) : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v95 + 4LL) + v95 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v95 + 4LL) + v95 + 32) = 0;
        *(_QWORD *)(*(int *)(*(_QWORD *)v95 + 4LL) + v95 + 40) = 0;
        v96 = std::basic_ostream<unsigned short>::operator<<(v95);
        *(_DWORD *)(*(int *)(*(_QWORD *)v96 + 4LL) + v96 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v96 + 4LL) + v96 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v96 + 4LL) + v96 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v96, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                      Elapsed Secs : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v97 + 4LL) + v97 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v97 + 4LL) + v97 + 32) = 9;
        *(_QWORD *)(*(int *)(*(_QWORD *)v97 + 4LL) + v97 + 40) = 0;
        v98 = std::basic_ostream<unsigned short>::operator<<(v97);
        *(_DWORD *)(*(int *)(*(_QWORD *)v98 + 4LL) + v98 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v98 + 4LL) + v98 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v98 + 4LL) + v98 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v98, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                RDTSC Elapsed Secs : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v99 + 4LL) + v99 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v99 + 4LL) + v99 + 32) = 9;
        *(_QWORD *)(*(int *)(*(_QWORD *)v99 + 4LL) + v99 + 40) = 0;
        v100 = std::basic_ostream<unsigned short>::operator<<(v99);
        *(_DWORD *)(*(int *)(*(_QWORD *)v100 + 4LL) + v100 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v100 + 4LL) + v100 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v100 + 4LL) + v100 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v100, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                         diff secs : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v101 + 4LL) + v101 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v101 + 4LL) + v101 + 32) = 9;
        *(_QWORD *)(*(int *)(*(_QWORD *)v101 + 4LL) + v101 + 40) = 0;
        v102 = std::basic_ostream<unsigned short>::operator<<(v101);
        *(_DWORD *)(*(int *)(*(_QWORD *)v102 + 4LL) + v102 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v102 + 4LL) + v102 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v102 + 4LL) + v102 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v102, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                  max allowed diff : ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v103 + 4LL) + v103 + 24) |= 0x2080u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v103 + 4LL) + v103 + 32) = 9;
        *(_QWORD *)(*(int *)(*(_QWORD *)v103 + 4LL) + v103 + 40) = 0;
        v104 = std::basic_ostream<unsigned short>::operator<<(v103);
        *(_DWORD *)(*(int *)(*(_QWORD *)v104 + 4LL) + v104 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v104 + 4LL) + v104 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v104 + 4LL) + v104 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v104, L"  - ");
        v106 = L"Delta VIOLATION!";
        if ( !*((_BYTE *)this + 808) )
          v106 = L"delta OK";
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v105, v106);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v107, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --             measurment loop count : ");
        v109 = std::basic_ostream<unsigned short>::operator<<(v108, v188);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v109, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                 sample block size : ");
        v111 = std::basic_ostream<unsigned short>::operator<<(v110, v4);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v111, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                 min loop duration : ");
        v113 = std::basic_ostream<unsigned short>::operator<<(v112, v189);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v113, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  --                 max loop duration : ");
        v115 = std::basic_ostream<unsigned short>::operator<<(v114, v190);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v115, L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"  -- Statistics --\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       + Total Samples : ");
        LODWORD(v203) = 12;
        v117 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v116, &v203);
        v118 = std::basic_ostream<unsigned short>::operator<<(
                 v117,
                 (__int64)(*((_QWORD *)this + 82) - *((_QWORD *)this + 81)) >> 3);
        *(_DWORD *)(*(int *)(*(_QWORD *)v118 + 4LL) + v118 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v118 + 4LL) + v118 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v118 + 4LL) + v118 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v118, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +           min : ");
        LODWORD(v203) = 12;
        v120 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v119, &v203);
        v121 = std::basic_ostream<unsigned short>::operator<<(v120, *((_QWORD *)this + 87));
        *(_DWORD *)(*(int *)(*(_QWORD *)v121 + 4LL) + v121 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v121 + 4LL) + v121 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v121 + 4LL) + v121 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v121, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +lower quartile : ");
        LODWORD(v203) = 12;
        v123 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v122, &v203);
        v124 = std::basic_ostream<unsigned short>::operator<<(v123, *((_QWORD *)this + 91));
        *(_DWORD *)(*(int *)(*(_QWORD *)v124 + 4LL) + v124 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v124 + 4LL) + v124 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v124 + 4LL) + v124 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v124, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +        median : ");
        LODWORD(v203) = 12;
        v126 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v125, &v203);
        v127 = std::basic_ostream<unsigned short>::operator<<(v126, *((_QWORD *)this + 85));
        *(_DWORD *)(*(int *)(*(_QWORD *)v127 + 4LL) + v127 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v127 + 4LL) + v127 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v127 + 4LL) + v127 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v127, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +          mean : ");
        LODWORD(v203) = 12;
        v129 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v128, &v203);
        v130 = std::basic_ostream<unsigned short>::operator<<(v129, *((_QWORD *)this + 86));
        *(_DWORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v130, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +upper quartile : ");
        LODWORD(v203) = 12;
        v132 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v131, &v203);
        v133 = std::basic_ostream<unsigned short>::operator<<(v132, *((_QWORD *)this + 90));
        *(_DWORD *)(*(int *)(*(_QWORD *)v133 + 4LL) + v133 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v133 + 4LL) + v133 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v133 + 4LL) + v133 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v133, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +           max : ");
        LODWORD(v203) = 12;
        v135 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v134, &v203);
        v136 = std::basic_ostream<unsigned short>::operator<<(v135, *((_QWORD *)this + 88));
        *(_DWORD *)(*(int *)(*(_QWORD *)v136 + 4LL) + v136 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v136 + 4LL) + v136 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v136 + 4LL) + v136 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v136, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +         range : ");
        LODWORD(v203) = 12;
        v138 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, &v203);
        v139 = std::basic_ostream<unsigned short>::operator<<(v138, *((_QWORD *)this + 89));
        *(_DWORD *)(*(int *)(*(_QWORD *)v139 + 4LL) + v139 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v139 + 4LL) + v139 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v139 + 4LL) + v139 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v139, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +      IQ range : ");
        LODWORD(v203) = 12;
        v141 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v140, &v203);
        v142 = std::basic_ostream<unsigned short>::operator<<(v141, *((_QWORD *)this + 92));
        *(_DWORD *)(*(int *)(*(_QWORD *)v142 + 4LL) + v142 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v142 + 4LL) + v142 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v142 + 4LL) + v142 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, "\n");
        v143 = *((_QWORD *)this + 87);
        v144 = *((_QWORD *)this + 85) - v143;
        v145 = *((_QWORD *)this + 91) - v143;
        v146 = *((_QWORD *)this + 85) - *((_QWORD *)this + 91);
        v147 = v143 * (unsigned __int64)v191 / 0x186A0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +    median-Min : ");
        LODWORD(v203) = 12;
        v149 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v148, &v203);
        v150 = std::basic_ostream<unsigned short>::operator<<(v149, v144);
        *(_DWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 40) = 0;
        v151 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v150, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v151 + 4LL) + v151 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v151 + 4LL) + v151 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v151 + 4LL) + v151 + 40) = 3;
        v152 = std::basic_ostream<unsigned short>::operator<<(v151);
        *(_DWORD *)(*(int *)(*(_QWORD *)v152 + 4LL) + v152 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v152 + 4LL) + v152 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v152 + 4LL) + v152 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v152, "% of min \n", v153);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +        lq-Min : ");
        LODWORD(v203) = 12;
        v155 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v154, &v203);
        v156 = std::basic_ostream<unsigned short>::operator<<(v155, v145);
        *(_DWORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 40) = 0;
        v157 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v156, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v157 + 4LL) + v157 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v157 + 4LL) + v157 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v157 + 4LL) + v157 + 40) = 3;
        v158 = std::basic_ostream<unsigned short>::operator<<(v157);
        *(_DWORD *)(*(int *)(*(_QWORD *)v158 + 4LL) + v158 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v158 + 4LL) + v158 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v158 + 4LL) + v158 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v158, "% of min \n", v159);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +     median-lq : ");
        LODWORD(v203) = 12;
        v161 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v160, &v203);
        v162 = std::basic_ostream<unsigned short>::operator<<(v161, v146);
        *(_DWORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 40) = 0;
        v163 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v162, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v163 + 4LL) + v163 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v163 + 4LL) + v163 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v163 + 4LL) + v163 + 40) = 3;
        v164 = std::basic_ostream<unsigned short>::operator<<(v163);
        *(_DWORD *)(*(int *)(*(_QWORD *)v164 + 4LL) + v164 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v164 + 4LL) + v164 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v164 + 4LL) + v164 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v164, "% of lq \n", v165);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +         Limit : ");
        LODWORD(v203) = 12;
        v167 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v166, &v203);
        v168 = std::basic_ostream<unsigned short>::operator<<(v167, v147);
        v169 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v168, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v169 + 4LL) + v169 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v169 + 4LL) + v169 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v169 + 4LL) + v169 + 40) = 3;
        v170 = std::basic_ostream<unsigned short>::operator<<(v169);
        *(_DWORD *)(*(int *)(*(_QWORD *)v170 + 4LL) + v170 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v170 + 4LL) + v170 + 88) = 32;
        v171 = *(int *)(*(_QWORD *)v170 + 4LL);
        *(_QWORD *)(v171 + v170 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v170, "% of min \n", v171);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +           Sum : ");
        LODWORD(v203) = 12;
        v173 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v172, &v203);
        v174 = std::basic_ostream<unsigned short>::operator<<(v173, *((_QWORD *)this + 84));
        *(_DWORD *)(*(int *)(*(_QWORD *)v174 + 4LL) + v174 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v174 + 4LL) + v174 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v174 + 4LL) + v174 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v174, "\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *((_QWORD *)this + 1) + 240LL,
          L"                       +        Status : ");
        LODWORD(v203) = 12;
        v176 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v175, &v203);
        v177 = L"GOOD";
        if ( !*((_BYTE *)this + 752) )
          v177 = L"BAD";
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v176, v177);
        *(_DWORD *)(*(int *)(*(_QWORD *)v178 + 4LL) + v178 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v178 + 4LL) + v178 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v178 + 4LL) + v178 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v178, "\n");
        std::endl(*((_QWORD *)this + 1) + 240LL);
        LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
      }
    }
  }
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  if ( **((int **)this + 4) > 0 )
  {
    v179 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v202, 0x1FDu);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v204,
      v179);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v203,
      1024);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
      &v203,
      *(_QWORD *)(v204 + 24),
      *((unsigned int *)this + 22));
    v180 = (_DWORD *)((char *)this + 96);
    WinSAT::OpStatus::SetResult((char *)this + 96, 5, *(_QWORD *)(v203 + 24), 0);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v203);
    v181 = &v204;
    goto LABEL_115;
  }
  if ( *((_BYTE *)this + 808) )
  {
    v182 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v202, 0x225u);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v203,
      v182);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
      &v203,
      v183,
      10);
    v184 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>::pfx(
      v184,
      *(_QWORD *)(v203 + 24),
      *((unsigned int *)this + 22));
    v180 = (_DWORD *)((char *)this + 96);
    *((_DWORD *)this + 24) = 6;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((char *)this + 104);
    *((_BYTE *)this + 112) = 0;
    v181 = &v203;
LABEL_115:
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v181);
  }
  else
  {
    v180 = (_DWORD *)((char *)this + 96);
    *((_DWORD *)this + 24) = 6;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((char *)this + 104);
    *((_BYTE *)this + 112) = 0;
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  v185 = *v180 != 6 ? 0xD : 0;
  SetLastError(v185);
  return v185;
}

```

## disassembly

```asm
0x140074490  mov     rax, rsp
0x140074493  push    rbp
0x140074494  push    rbx
0x140074495  push    rsi
0x140074496  push    rdi
0x140074497  push    r12
0x140074499  push    r13
0x14007449b  push    r14
0x14007449d  push    r15
0x14007449f  lea     rbp, [rax-58h]
0x1400744a3  sub     rsp, 118h
0x1400744aa  movaps  xmmword ptr [rax-58h], xmm6
0x1400744ae  movaps  xmmword ptr [rax-68h], xmm7
0x1400744b2  movaps  xmmword ptr [rax-78h], xmm8
0x1400744b7  movaps  xmmword ptr [rax-88h], xmm9
0x1400744bf  mov     rbx, rcx
0x1400744c2  xor     r15d, r15d
0x1400744c5  mov     rax, [rcx+350h]
0x1400744cc  mov     ecx, [rax+20ACh]
0x1400744d2  mov     dword ptr [rsp+150h+var_EC], ecx
0x1400744d6  mov     r13d, [rax+20B0h]
0x1400744dd  mov     eax, [rax+20B4h]
0x1400744e3  mov     [rsp+150h+var_F4], eax
0x1400744e7  mov     [rsp+150h+var_110], r15d
0x1400744ec  call    cs:__imp_GetTickCount
0x1400744f2  mov     rdx, [rbx+350h]
0x1400744f9  movsd   xmm0, qword ptr [rdx+2098h]
0x140074501  movsd   xmm8, cs:__real@408f400000000000
0x14007450a  mulsd   xmm0, xmm8
0x14007450f  cvttsd2si rcx, xmm0
0x140074514  add     ecx, eax
0x140074516  mov     [rbp+50h+var_B8], rcx
0x14007451a  movsd   xmm0, qword ptr [rdx+20A0h]
0x140074522  mulsd   xmm0, xmm8
0x140074527  cvttsd2si rcx, xmm0
0x14007452c  add     ecx, eax
0x14007452e  mov     [rbp+50h+var_B0], rcx
0x140074532  mov     dil, [rdx+20A8h]
0x140074539  mov     byte ptr [rbp+50h+arg_8], dil
0x14007453d  xor     r14d, r14d
0x140074540  mov     byte ptr [rbp+50h+arg_0], r14b
0x140074544  xor     esi, esi
0x140074546  or      ecx, 0FFFFFFFFh
0x140074549  mov     [rsp+150h+var_FC], ecx
0x14007454d  xor     r8d, r8d
0x140074550  mov     [rsp+150h+var_F8], r8d
0x140074555  xor     ecx, ecx; this
0x140074557  mov     [rsp+150h+var_100], ecx
0x14007455b  mov     al, [rdx+20BAh]
0x140074561  mov     [rbp+50h+arg_10], al
0x140074564  call    ?QueryPerformanceCounter64@mlib@@YA_KXZ; mlib::QueryPerformanceCounter64(void)
0x140074569  mov     r12, rax
0x14007456c  rdtsc
0x14007456e  shl     rdx, 20h
0x140074572  or      rax, rdx
0x140074575  mov     [rbx+318h], rax
0x14007457c  jmp     short loc_140074582
0x14007457e  mov     dil, byte ptr [rbp+50h+arg_8]
0x140074582  mov     rcx, rbx; this
0x140074585  call    ?ExitLoop@MPWorkload@WinSAT@@IEBA_NXZ; WinSAT::MPWorkload::ExitLoop(void)
0x14007458a  test    al, al
0x14007458c  jnz     loc_140074A4A
0x140074592  test    dil, dil
0x140074595  jnz     loc_140074A4A
0x14007459b  lea     rdi, [rbx+288h]
0x1400745a2  mov     rcx, [rdi+10h]
0x1400745a6  sub     rcx, [rdi]
0x1400745a9  sar     rcx, 3
0x1400745ad  cmp     rcx, [rdi+70h]
0x1400745b1  jnb     short loc_1400745D2
0x1400745b3  mov     rax, [rbx+290h]
0x1400745ba  sub     rax, [rdi]
0x1400745bd  sar     rax, 3
0x1400745c1  cmp     rax, rcx
0x1400745c4  jb      short loc_1400745D2
0x1400745c6  mov     edx, dword ptr [rsp+150h+var_EC]; unsigned __int64
0x1400745ca  mov     rcx, rdi; this
0x1400745cd  call    ?GrowSizeBy@SampleManager@@QEAAX_K@Z; SampleManager::GrowSizeBy(unsigned __int64)
0x1400745d2  mov     rcx, rbx; this
0x1400745d5  call    ?Rendevous@MPWorkload@WinSAT@@IEBA_NXZ; WinSAT::MPWorkload::Rendevous(void)
0x1400745da  test    al, al
0x1400745dc  jz      loc_140074A4A
0x1400745e2  call    cs:__imp_GetTickCount
0x1400745e8  mov     dword ptr [rsp+150h+var_EC+4], eax
0x1400745ec  xor     eax, eax
0x1400745ee  mov     [rsp+150h+var_110+4], eax
0x1400745f2  cmp     eax, r13d
0x1400745f5  jnb     loc_140074959
0x1400745fb  mov     ecx, [rbx+3D0h]
0x140074601  mov     [rsp+150h+var_110], ecx
0x140074605  mov     rcx, [rbx+20h]
0x140074609  mov     edx, [rcx]
0x14007460b  test    edx, edx
0x14007460d  jnz     loc_140074959
0x140074613  mov     rax, [rbx+40h]
0x140074617  mov     ecx, [rax]
0x140074619  test    ecx, ecx
0x14007461b  jnz     loc_140074959
0x140074621  lea     rcx, [rbx+358h]; this
0x140074628  call    ?RotateBuffer@RotatingBuffer@@QEAAPEAEXZ; RotatingBuffer::RotateBuffer(void)
0x14007462d  mov     [rbx+3D8h], rax
0x140074634  test    rax, rax
0x140074637  jz      loc_140074A35
0x14007463d  lea     rcx, [rbx+388h]; this
0x140074644  call    ?RotateBuffer@RotatingBuffer@@QEAAPEAEXZ; RotatingBuffer::RotateBuffer(void)
0x140074649  mov     [rbx+3E0h], rax
0x140074650  test    rax, rax
0x140074653  jz      loc_140074A35
0x140074659  mov     dword ptr [rsp+150h+phHash], 0
0x140074661  mov     [rsp+150h+var_F0], 0
0x140074669  mov     r8d, [rbx+3D0h]; Size
0x140074670  mov     rdx, [rbx+3D8h]; Src
0x140074677  mov     rcx, rax; void *
0x14007467a  call    memcpy_0
0x14007467f  mov     ecx, [rbx+3B8h]
0x140074685  cmp     ecx, 2
0x140074688  jnz     short loc_1400746C3
0x14007468a  mov     eax, [rbx+3F0h]
0x140074690  mov     [rsp+150h+var_110], eax
0x140074694  rdtsc
0x140074696  shl     rdx, 20h
0x14007469a  or      rax, rdx
0x14007469d  mov     [rbp+50h+var_C8], rax
0x1400746a1  mov     edx, [rbx+3F0h]
0x1400746a7  mov     rcx, [rbx+3E0h]
0x1400746ae  call    XpressCrc32
0x1400746b3  mov     r8d, 1
0x1400746b9  mov     dword ptr [rsp+150h+phHash], r8d
0x1400746be  jmp     loc_1400747BC
0x1400746c3  rdtsc
0x1400746c5  shl     rdx, 20h
0x1400746c9  or      rax, rdx
0x1400746cc  mov     [rbp+50h+var_C8], rax
0x1400746d0  test    ecx, ecx
0x1400746d2  jnz     short loc_140074748
0x1400746d4  mov     ecx, [rbx+3F0h]
0x1400746da  mov     [rsp+150h+dwBufLen], ecx; dwBufLen
0x1400746de  lea     rax, [rsp+150h+var_110]
0x1400746e3  mov     [rsp+150h+pdwDataLen], rax; pdwDataLen
0x1400746e8  mov     rcx, [rbx+3E0h]
0x1400746ef  mov     [rsp+150h+pbData], rcx; pbData
0x1400746f4  xor     r9d, r9d; dwFlags
0x1400746f7  xor     edx, edx; hHash
0x1400746f9  lea     r8d, [r9+1]; Final
0x1400746fd  mov     rcx, [rbx+3C8h]; hKey
0x140074704  call    cs:__imp_CryptEncrypt
0x14007470a  mov     dword ptr [rbp+50h+arg_18], eax
0x14007470d  test    eax, eax
0x14007470f  jz      short loc_140074743
0x140074711  lea     rax, [rsp+150h+var_110]
0x140074716  mov     [rsp+150h+pdwDataLen], rax; pdwDataLen
0x14007471b  mov     rcx, [rbx+3E0h]
0x140074722  mov     [rsp+150h+pbData], rcx; pbData
0x140074727  xor     r9d, r9d; dwFlags
0x14007472a  xor     edx, edx; hHash
0x14007472c  lea     r8d, [r9+1]; Final
0x140074730  mov     rcx, [rbx+3C8h]; hKey
0x140074737  call    cs:__imp_CryptDecrypt
0x14007473d  mov     dword ptr [rsp+150h+phHash], eax
0x140074741  jmp     short loc_1400747B8
0x140074743  mov     r8d, eax
0x140074746  jmp     short loc_1400747BC
0x140074748  cmp     ecx, 1
0x14007474b  jnz     short loc_1400747B1
0x14007474d  mov     [rsp+150h+phHash], 0
0x140074756  lea     rax, [rsp+150h+phHash]
0x14007475b  mov     [rsp+150h+pbData], rax; phHash
0x140074760  xor     r9d, r9d; dwFlags
0x140074763  xor     r8d, r8d; hKey
0x140074766  mov     edx, 8004h; Algid
0x14007476b  mov     rcx, [rbx+3C0h]; hProv
0x140074772  call    cs:__imp_CryptCreateHash
0x140074778  xor     r9d, r9d; dwFlags
0x14007477b  mov     r8d, [rbx+3F0h]; dwDataLen
0x140074782  mov     rdx, [rbx+3E0h]; pbData
0x140074789  mov     rcx, [rsp+150h+phHash]; hHash
0x14007478e  call    cs:__imp_CryptHashData
0x140074794  mov     dword ptr [rbp+50h+arg_18], eax
0x140074797  mov     rcx, [rsp+150h+phHash]; hHash
0x14007479c  test    rcx, rcx
0x14007479f  jz      short loc_1400747A7
0x1400747a1  call    cs:__imp_CryptDestroyHash
0x1400747a7  mov     dword ptr [rsp+150h+phHash], 1
0x1400747af  jmp     short loc_1400747B8
0x1400747b1  mov     dword ptr [rbp+50h+arg_18], 0
0x1400747b8  mov     r8d, dword ptr [rbp+50h+arg_18]
0x1400747bc  rdtsc
0x1400747be  shl     rdx, 20h
0x1400747c2  or      rax, rdx
0x1400747c5  mov     [rbp+50h+arg_18], rax
0x1400747c9  mov     ecx, [rsp+150h+var_110]
0x1400747cd  add     r14, rcx
0x1400747d0  test    r8d, r8d
0x1400747d3  jnz     loc_140074870
0x1400747d9  mov     rcx, [rbx+50h]; lpCriticalSection
0x1400747dd  call    cs:__imp_EnterCriticalSection
0x1400747e3  mov     edx, 217h; unsigned __int16
0x1400747e8  lea     rcx, [rbp+50h+var_A8]; this
0x1400747ec  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x1400747f1  mov     rdx, rax
0x1400747f4  lea     rcx, [rbp+50h+var_D0]
0x1400747f8  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x1400747fd  nop
0x1400747fe  mov     edx, 400h
0x140074803  lea     rcx, [rsp+150h+var_E0]
0x140074808  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x14007480d  nop
0x14007480e  mov     r9d, [rbx+58h]
0x140074812  mov     r8d, [rsp+150h+var_110+4]
0x140074817  mov     rdx, [rbp+50h+var_D0]
0x14007481b  mov     rdx, [rdx+18h]
0x14007481f  lea     rcx, [rsp+150h+var_E0]
0x140074824  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x140074829  mov     rcx, [rbx+10h]
0x14007482d  add     rcx, 0F0h
0x140074834  lea     rdx, [rsp+150h+var_E0]
0x140074839  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007483e  mov     rcx, rax
0x140074841  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140074846  mov     rcx, [rbx+50h]; lpCriticalSection
0x14007484a  call    cs:__imp_LeaveCriticalSection
0x140074850  mov     [rsp+150h+var_F0], 1
0x140074858  lea     rcx, [rsp+150h+var_E0]
0x14007485d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140074862  nop
0x140074863  lea     rcx, [rbp+50h+var_D0]
0x140074867  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14007486c  mov     rax, [rbp+50h+arg_18]
0x140074870  cmp     dword ptr [rsp+150h+phHash], 0
0x140074875  jz      short loc_1400748C6
0x140074877  cmp     [rsp+150h+var_F0], 0
0x14007487c  jnz     loc_140074952
0x140074882  cmp     byte ptr [rbp+50h+arg_0], 0
0x140074886  jnz     short loc_14007489F
0x140074888  sub     rax, [rbp+50h+var_C8]
0x14007488c  mov     [rbp+50h+arg_18], rax
0x140074890  mov     rdx, rax; unsigned __int64
0x140074893  mov     rcx, rdi; this
0x140074896  call    ?AddSample@SampleManager@@QEAAX_K@Z; SampleManager::AddSample(unsigned __int64)
0x14007489b  add     r15, [rbp+50h+arg_18]
0x14007489f  mov     rax, [rbx+20h]
0x1400748a3  mov     ecx, [rax]
0x1400748a5  test    ecx, ecx
0x1400748a7  jnz     loc_140074959
0x1400748ad  mov     rax, [rbx+40h]
0x1400748b1  mov     ecx, [rax]
0x1400748b3  test    ecx, ecx
0x1400748b5  jnz     loc_140074959
0x1400748bb  mov     eax, [rsp+150h+var_110+4]
0x1400748bf  inc     eax
0x1400748c1  jmp     loc_1400745EE
0x1400748c6  mov     rcx, [rbx+50h]; lpCriticalSection
0x1400748ca  call    cs:__imp_EnterCriticalSection
0x1400748d0  mov     edx, 218h; unsigned __int16
0x1400748d5  lea     rcx, [rbp+50h+var_A8]; this
0x1400748d9  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x1400748de  mov     rdx, rax
0x1400748e1  lea     rcx, [rbp+50h+var_C0]
0x1400748e5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x1400748ea  nop
0x1400748eb  mov     edx, 400h
0x1400748f0  lea     rcx, [rsp+150h+var_D8]
0x1400748f5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x1400748fa  nop
0x1400748fb  mov     r9d, [rbx+58h]
0x1400748ff  mov     r8d, [rsp+150h+var_110+4]
0x140074904  mov     rdx, [rbp+50h+var_C0]
0x140074908  mov     rdx, [rdx+18h]
0x14007490c  lea     rcx, [rsp+150h+var_D8]
0x140074911  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x140074916  mov     rcx, [rbx+10h]
0x14007491a  add     rcx, 0F0h
0x140074921  lea     rdx, [rsp+150h+var_D8]
0x140074926  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007492b  mov     rcx, rax
0x14007492e  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140074933  mov     rcx, [rbx+50h]; lpCriticalSection
0x140074937  call    cs:__imp_LeaveCriticalSection
0x14007493d  nop
0x14007493e  lea     rcx, [rsp+150h+var_D8]
0x140074943  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140074948  nop
0x140074949  lea     rcx, [rbp+50h+var_C0]
0x14007494d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140074952  mov     rax, [rbx+20h]
0x140074956  lock inc dword ptr [rax]
0x140074959  mov     rax, [rbx+20h]
0x14007495d  mov     ecx, [rax]
0x14007495f  test    ecx, ecx
0x140074961  jnz     loc_140074A4A
0x140074967  mov     rax, [rbx+40h]
0x14007496b  mov     ecx, [rax]
0x14007496d  test    ecx, ecx
0x14007496f  jnz     loc_140074A4A
0x140074975  cmp     [rbp+50h+arg_10], cl
0x140074978  jnz     short loc_14007498D
0x14007497a  mov     rcx, [rbx+350h]
0x140074981  mov     ecx, [rcx+208Ch]; dwMilliseconds
0x140074987  call    cs:__imp_Sleep
0x14007498d  inc     [rsp+150h+var_100]
  ... truncated ...
```
