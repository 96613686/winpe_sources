# I_s_RPC_SCardLocateCards

- ea: `0x180007910`
- end: `0x180008f6c`
- name: `I_s_RPC_SCardLocateCards`
- size: `5724`
- prototype: `__int64 __fastcall(int, int, int, int, int, unsigned __int16 *, unsigned __int8, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800074b0`

## callees

- `0x1800075d0`
- `0x180007910`
- `0x180008f80`
- `0x180009190`
- `0x180009b30`
- `0x180009d80`
- `0x18000a2c0`
- `0x18000c250`
- `0x18000c640`
- `0x18000cf60`
- `0x18000d190`
- `0x18000fb50`
- `0x180012380`
- `0x1800125e0`
- `0x180019bc4`
- `0x18001c330`
- `0x18001c370`
- `0x180023168`
- `0x180023174`
- `0x180023276`
- `0x180028b78`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008184`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008233`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008184`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008233`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007d03`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800082fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008349`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007d03`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800082fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008349`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007c89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007c89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f22`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007ce9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008132`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800081e1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008979`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000899e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007ce9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008132`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800081e1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008979`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000899e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800079f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007a09`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800079f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007a09`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800087f1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800087f1`
- `KERNEL32!lstrcmpiW` at `0x180007f95`
- `KERNEL32!lstrcmpiW` at `0x180007f95`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall I_s_RPC_SCardLocateCards(
        __int64 a1,
        unsigned __int8 *a2,
        int a3,
        unsigned __int8 *a4,
        int a5,
        unsigned __int16 *a6,
        __int16 a7,
        __int64 a8,
        unsigned int a9,
        _QWORD *a10,
        unsigned int *a11)
{
  unsigned int v15; // ebx
  signed int v16; // r13d
  int v17; // ecx
  __int64 v18; // rbx
  unsigned int v19; // r14d
  __int64 v20; // r13
  unsigned __int8 *v21; // rdi
  unsigned __int8 *v22; // r15
  unsigned int v23; // edx
  __int64 v24; // rsi
  int v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rsi
  int v28; // eax
  __int64 v29; // rsi
  int v30; // eax
  int v31; // r14d
  unsigned int v32; // ebx
  const WCHAR *String; // rax
  const WCHAR *v34; // r13
  void *v35; // rdi
  unsigned int v36; // esi
  HANDLE ProcessHeap; // rax
  void *v38; // rax
  _DWORD *v39; // rsi
  bool v40; // zf
  _DWORD *v42; // rcx
  unsigned int v43; // r8d
  unsigned int n; // r9d
  _QWORD *v45; // rsi
  unsigned int v46; // r8d
  unsigned int i; // ecx
  _DWORD *v48; // rcx
  void *v49; // r14
  struct CCriticalSectionObject *v50; // rbx
  unsigned int v51; // eax
  unsigned int v52; // edi
  const WCHAR *v53; // r15
  CReader *v54; // rsi
  const WCHAR *v55; // rdx
  _DWORD *v56; // r8
  unsigned int v57; // edx
  unsigned int k; // r9d
  char *v59; // rax
  const unsigned __int8 *v60; // rcx
  const unsigned __int16 *v61; // r9
  __int64 **v62; // r13
  __int64 *v63; // r14
  int v64; // ebx
  __int64 v65; // rcx
  __int64 v66; // rdi
  __int64 v67; // r14
  __int64 v68; // rbx
  size_t v69; // r15
  const WCHAR *v70; // r14
  unsigned __int8 *v71; // rsi
  unsigned __int8 *v72; // rcx
  unsigned int v73; // edi
  unsigned int v74; // ebx
  unsigned int v75; // ecx
  _BYTE *v76; // rax
  _BYTE *v77; // rdi
  _BYTE *v78; // rdx
  _DWORD *v79; // rcx
  unsigned int v80; // r8d
  unsigned int m; // r9d
  unsigned int v82; // r15d
  unsigned int v83; // ebx
  void *v84; // rax
  _BYTE *v85; // rdi
  unsigned int v86; // edi
  unsigned __int8 *v87; // rsi
  unsigned int *v88; // r9
  unsigned __int8 *v89; // r8
  unsigned int v90; // ebx
  _BYTE *v91; // rax
  _BYTE *v92; // rdi
  _BYTE *v93; // rdi
  int v94; // edx
  unsigned int v95; // ebx
  unsigned __int8 *v96; // rax
  unsigned int v97; // edi
  __int64 v98; // rsi
  const unsigned __int8 *v99; // r15
  const unsigned __int8 *v100; // r14
  unsigned int *v101; // r8
  unsigned int *v102; // r9
  unsigned int v103; // r8d
  unsigned int ii; // edx
  unsigned int jj; // edx
  int v106; // ecx
  void *v107; // rax
  unsigned int dwBytes; // [rsp+30h] [rbp-188h]
  unsigned int dwBytes_4; // [rsp+34h] [rbp-184h]
  int dwBytes_4a; // [rsp+34h] [rbp-184h]
  void *Src; // [rsp+40h] [rbp-178h]
  unsigned int v112; // [rsp+4Ch] [rbp-16Ch]
  unsigned int v113[2]; // [rsp+50h] [rbp-168h] BYREF
  unsigned int v114[2]; // [rsp+58h] [rbp-160h] BYREF
  _DWORD *v115; // [rsp+60h] [rbp-158h]
  int v116; // [rsp+68h] [rbp-150h]
  unsigned int v117; // [rsp+6Ch] [rbp-14Ch]
  void **v118; // [rsp+70h] [rbp-148h]
  unsigned int v119; // [rsp+78h] [rbp-140h]
  unsigned int v120; // [rsp+7Ch] [rbp-13Ch]
  void *v121; // [rsp+80h] [rbp-138h]
  int v122; // [rsp+88h] [rbp-130h]
  void **v123; // [rsp+90h] [rbp-128h]
  unsigned __int8 *v124; // [rsp+98h] [rbp-120h]
  _QWORD v125[2]; // [rsp+A0h] [rbp-118h]
  unsigned int v126; // [rsp+B0h] [rbp-108h]
  unsigned int v127; // [rsp+B4h] [rbp-104h]
  void *v128; // [rsp+B8h] [rbp-100h]
  __int64 **v129; // [rsp+C0h] [rbp-F8h]
  void **v130; // [rsp+C8h] [rbp-F0h]
  signed int v131; // [rsp+D0h] [rbp-E8h]
  unsigned int v132; // [rsp+D4h] [rbp-E4h]
  void *Block; // [rsp+D8h] [rbp-E0h]
  ulong v134; // [rsp+E0h] [rbp-D8h] BYREF
  ulong v135; // [rsp+E4h] [rbp-D4h] BYREF
  ulong v136; // [rsp+E8h] [rbp-D0h] BYREF
  ulong v137; // [rsp+ECh] [rbp-CCh] BYREF
  ulong v138; // [rsp+F0h] [rbp-C8h] BYREF
  ulong v139; // [rsp+F4h] [rbp-C4h] BYREF
  ulong v140; // [rsp+F8h] [rbp-C0h] BYREF
  ulong v141; // [rsp+FCh] [rbp-BCh] BYREF
  ulong v142; // [rsp+100h] [rbp-B8h] BYREF
  ulong v143; // [rsp+104h] [rbp-B4h] BYREF
  ulong LastError; // [rsp+108h] [rbp-B0h] BYREF
  ulong v145; // [rsp+10Ch] [rbp-ACh] BYREF
  ulong v146; // [rsp+110h] [rbp-A8h] BYREF
  ulong v147; // [rsp+114h] [rbp-A4h] BYREF
  ulong v148; // [rsp+118h] [rbp-A0h] BYREF
  ulong v149; // [rsp+11Ch] [rbp-9Ch] BYREF
  ulong v150; // [rsp+120h] [rbp-98h] BYREF
  ulong v151; // [rsp+124h] [rbp-94h] BYREF
  ulong v152; // [rsp+128h] [rbp-90h] BYREF
  ulong v153; // [rsp+12Ch] [rbp-8Ch] BYREF
  ulong v154; // [rsp+130h] [rbp-88h] BYREF
  ulong v155; // [rsp+134h] [rbp-84h] BYREF
  ulong pExceptionObject; // [rsp+138h] [rbp-80h] BYREF
  ulong v157; // [rsp+13Ch] [rbp-7Ch] BYREF
  ulong v158; // [rsp+140h] [rbp-78h] BYREF
  LPCWSTR lpString1; // [rsp+148h] [rbp-70h]
  ulong v160; // [rsp+150h] [rbp-68h] BYREF
  ulong v161; // [rsp+154h] [rbp-64h] BYREF
  ulong v162; // [rsp+158h] [rbp-60h] BYREF
  ulong v163; // [rsp+15Ch] [rbp-5Ch] BYREF
  ulong v164; // [rsp+160h] [rbp-58h] BYREF
  __int64 v165; // [rsp+168h] [rbp-50h]
  __int64 v166; // [rsp+170h] [rbp-48h]
  _DWORD *v167; // [rsp+180h] [rbp-38h]
  __int64 v168; // [rsp+188h] [rbp-30h]
  int v170; // [rsp+1E0h] [rbp+28h]
  unsigned int j; // [rsp+1F0h] [rbp+38h]
  int v172; // [rsp+1F0h] [rbp+38h]

  v165 = a1;
  v117 = 0;
  Src = 0;
  dwBytes = 0;
  v112 = 0;
  v123 = &CBuffer::`vftable';
  v124 = 0;
  v125[0] = 0;
  v125[1] = &CDynamicArray<CServiceThread>::`vftable';
  v127 = 0;
  dwBytes_4 = 0;
  v126 = 0;
  v128 = 0;
  v118 = &CDynamicArray<CServiceThread>::`vftable';
  v120 = 0;
  j = 0;
  v119 = 0;
  v121 = 0;
  v130 = &CDynamicArray<CServiceThread>::`vftable';
  v15 = 0;
  v132 = 0;
  v16 = 0;
  v114[0] = 0;
  v131 = 0;
  Block = 0;
  if ( !TlsSetValue(dwTlsIndex, *(LPVOID *)(a1 + 72)) || !TlsSetValue(dword_18004B240, *(LPVOID *)a1) )
    GetLastError();
  _InterlockedExchange(&g_fExtendShutdownTimer, 1);
  v167 = (_DWORD *)(a1 + 80);
  CMutex::Grab((CMutex *)(a1 + 80));
  v166 = a1;
  if ( !*(_BYTE *)a6 )
  {
    v157 = -2146435063;
    throw &v157;
  }
  if ( !a3 || (v17 = a5) == 0 || !a9 )
  {
    pExceptionObject = -2146435055;
    throw &pExceptionObject;
  }
  while ( a3 )
  {
    if ( v15 >= v16 )
    {
      if ( !v16 )
        v16 = 4;
      for ( v114[0] = v16; (int)v15 >= v16; v114[0] = v16 )
        v16 *= 2;
      v45 = operator new[](saturated_mul(v16, 8u));
      if ( !v45 )
      {
        v158 = 14;
        throw &v158;
      }
      v46 = 0;
      for ( i = v132; v46 < i; ++v46 )
        v45[v46] = *((_QWORD *)Block + v46);
      if ( Block )
        operator delete[](Block);
      Block = v45;
      v131 = v16;
      v17 = a5;
    }
    v132 = v15 + 1;
    *((_QWORD *)Block + v15) = a2;
    v18 = *a2;
    v19 = a3 - 1;
    if ( (unsigned int)v18 > v19 )
    {
      v160 = -2146435053;
      throw &v160;
    }
    if ( (unsigned int)v18 > 0x21 )
    {
      v161 = -2146435051;
      throw &v161;
    }
    if ( !v17 )
    {
      v136 = -2146435055;
      throw &v136;
    }
    v20 = *a4;
    v170 = v17 - 1;
    if ( (unsigned int)v20 > v17 - 1 )
    {
      v162 = -2146435053;
      throw &v162;
    }
    v21 = a2 + 1;
    v22 = a4 + 1;
    if ( (_DWORD)v20 )
    {
      if ( (_DWORD)v18 != (_DWORD)v20 )
      {
        v164 = -2146435051;
        throw &v164;
      }
      if ( (_DWORD)v18 )
      {
        v23 = 0;
        if ( (unsigned int)v18 < 8 || v21 <= &v22[(unsigned int)(v18 - 1)] && &v21[(unsigned int)(v18 - 1)] >= v22 )
          goto LABEL_280;
        do
        {
          *(_QWORD *)&v21[v23] &= *(_QWORD *)&v22[v23];
          v23 += 8;
        }
        while ( v23 < ((unsigned __int8)v18 & 0x38u) );
        if ( v23 < (unsigned int)v18 )
        {
LABEL_280:
          do
          {
            v21[v23] &= v22[v23];
            ++v23;
          }
          while ( v23 < (unsigned int)v18 );
        }
      }
      v24 = v120;
      v25 = j;
      if ( v120 >= j )
      {
        if ( !j )
          v25 = 4;
        for ( j = v25; (int)v120 >= v25; j = v25 )
          v25 *= 2;
        v56 = operator new[](saturated_mul(v25, 8u));
        v115 = v56;
        if ( !v56 )
        {
          v134 = 14;
          throw &v134;
        }
        v57 = 0;
        for ( k = v120; v57 < k; ++v57 )
          *(_QWORD *)&v56[2 * v57] = *((_QWORD *)v121 + v57);
        if ( v121 )
        {
          operator delete[](v121);
          v56 = v115;
        }
        v26 = v56;
        v121 = v56;
        v119 = j;
      }
      else
      {
        v26 = v121;
      }
      v120 = v24 + 1;
      v26[v24] = v22;
    }
    else
    {
      v29 = v120;
      v30 = j;
      if ( v120 >= j )
      {
        if ( !j )
          v30 = 4;
        for ( j = v30; (int)v120 >= v30; j = v30 )
          v30 *= 2;
        v79 = operator new[](saturated_mul(v30, 8u));
        v115 = v79;
        if ( !v79 )
        {
          v163 = 14;
          throw &v163;
        }
        v80 = 0;
        for ( m = v120; v80 < m; ++v80 )
          *(_QWORD *)&v79[2 * v80] = *((_QWORD *)v121 + v80);
        if ( v121 )
        {
          operator delete[](v121);
          v79 = v115;
        }
        v121 = v79;
        v119 = j;
        v120 = v29 + 1;
        *(_QWORD *)&v79[2 * v29] = 0;
      }
      else
      {
        ++v120;
        *((_QWORD *)v121 + v29) = 0;
      }
    }
    v27 = v127;
    v28 = dwBytes_4;
    if ( v127 >= dwBytes_4 )
    {
      if ( !dwBytes_4 )
        v28 = 4;
      for ( dwBytes_4 = v28; (int)v127 >= v28; dwBytes_4 = v28 )
        v28 *= 2;
      v42 = operator new[](saturated_mul(v28, 8u));
      v115 = v42;
      if ( !v42 )
      {
        v135 = 14;
        throw &v135;
      }
      v43 = 0;
      for ( n = v127; v43 < n; ++v43 )
        *(_QWORD *)&v42[2 * v43] = *((_QWORD *)v128 + v43);
      if ( v128 )
      {
        operator delete[](v128);
        v42 = v115;
      }
      v128 = v42;
      v126 = dwBytes_4;
    }
    v127 = v27 + 1;
    *((_QWORD *)v128 + v27) = v21;
    a3 = v19 - v18;
    a2 = &v21[v18];
    v17 = v170 - v20;
    a5 = v170 - v20;
    a4 = &v22[v20];
    v16 = v114[0];
    v15 = v132;
  }
  if ( v17 )
  {
    v137 = -2146435053;
    throw &v137;
  }
  v129 = 0;
  v31 = 0;
  dwBytes_4a = 0;
  v32 = 0;
  v122 = 0;
  String = FirstString(a6);
  v34 = &Data;
  v35 = 0;
  v36 = 0;
  while ( 1 )
  {
    lpString1 = String;
    if ( !String || v32 >= a9 )
      break;
    v48 = (_DWORD *)(a8 + 4LL * v32);
    v115 = v48;
    if ( (*v48 & 1) != 0 )
    {
      *v48 = 1;
      v82 = dwBytes;
      v83 = dwBytes + 1;
      if ( dwBytes )
      {
        if ( v36 < v83 )
        {
          v84 = operator new[](v83);
          v35 = v84;
          if ( !v84 )
          {
            v138 = 14;
            throw &v138;
          }
          memcpy_0(v84, Src, dwBytes);
          operator delete[](Src);
          Src = v35;
          v112 = dwBytes + 1;
          v36 = dwBytes + 1;
        }
      }
      else
      {
        if ( v36 < v83 )
        {
          v35 = operator new[](v83);
          if ( !v35 )
          {
            v139 = 14;
            throw &v139;
          }
          if ( Src )
            operator delete[](Src);
          Src = v35;
          v36 = dwBytes + 1;
          v112 = dwBytes + 1;
        }
        v82 = 0;
      }
      *((_BYTE *)v35 + v82) = 0;
      dwBytes = v82 + 1;
    }
    else
    {
      v49 = *(void **)(a1 + 176);
      v50 = g_pcsControlLocks;
      *(_QWORD *)v113 = g_pcsControlLocks;
      (**(void (__fastcall ***)(struct CCriticalSectionObject *, _QWORD, _QWORD))g_pcsControlLocks)(
        g_pcsControlLocks,
        0,
        0);
      v51 = HIDWORD(qword_18004B0C8);
      v52 = HIDWORD(qword_18004B0C8);
      v53 = lpString1;
      while ( 1 )
      {
        do
        {
          if ( !v52 )
          {
            v153 = -2146435063;
            throw &v153;
          }
          --v52;
        }
        while ( v51 <= v52 );
        _mm_lfence();
        v54 = (CReader *)*((_QWORD *)qword_18004B0D0 + (int)v52);
        if ( v54 )
        {
          v55 = *((_DWORD *)v54 + 7) ? (const WCHAR *)*((_QWORD *)v54 + 2) : &Data;
          if ( !lstrcmpiW(v53, v55) )
            break;
        }
        v51 = HIDWORD(qword_18004B0C8);
      }
      if ( (*(__int64 (__fastcall **)(CReader *))(*(_QWORD *)v54 + 56LL))(v54) )
      {
        if ( v49 )
        {
          v107 = (void *)(*(__int64 (__fastcall **)(CReader *))(*(_QWORD *)v54 + 56LL))(v54);
          if ( !EqualSid(v107, v49) )
          {
            v140 = -2146435063;
            throw &v140;
          }
        }
      }
      v59 = (char *)operator new(0x20u);
      v62 = (__int64 **)v59;
      *(_QWORD *)v114 = v59;
      if ( v59 )
      {
        *(_OWORD *)(v59 + 8) = 0;
        *((_DWORD *)v59 + 6) = 0;
        *(_QWORD *)v59 = CReader::ReaderProxy(v54);
      }
      else
      {
        v62 = 0;
      }
      if ( !v62 )
      {
        CalaisError(v60, 0xCBu, 0, v61);
        v141 = -2146435066;
        throw &v141;
      }
      (*(void (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v50 + 8LL))(v50);
      v129 = v62;
      v63 = *v62;
      v64 = CReaderProxy::AvailabilityStatus(*v62);
      LOWORD(v116) = CReaderProxy::ActivityHash((CReaderProxy *)v63);
      if ( v64 == 1 )
      {
        v172 = 16;
      }
      else if ( v64 == 2 )
      {
        v172 = 1056;
      }
      else
      {
        switch ( v64 )
        {
          case 0:
            v172 = 5;
            LOWORD(v116) = 0;
            break;
          case 3:
          case 4:
            v172 = 544;
            break;
          case 5:
            v172 = 32;
            break;
          case 6:
            v172 = 288;
            break;
          case 7:
            v172 = 416;
            break;
          case 8:
            v172 = 8;
            break;
          case 9:
          case 10:
          case 11:
            WppTraceIndent(v65, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                WPP_8fae02f726263adb5326c29facded416_Traceguids,
                WPP_pszIndent);
            }
            v172 = 9;
            v116 = 0;
            break;
          default:
            WppTraceIndent(v65, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                WPP_8fae02f726263adb5326c29facded416_Traceguids,
                WPP_pszIndent);
            }
            v142 = -2146435071;
            throw &v142;
        }
      }
      (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))v63[1])(v63 + 1, 0, 0);
      if ( !*v63 )
      {
        (*(void (__fastcall **)(__int64 *))(v63[1] + 8))(v63 + 1);
        v143 = -2146435049;
        throw &v143;
      }
      v66 = *v63 + 512;
      *(_QWORD *)v114 = v66;
      *(_QWORD *)v113 = v66;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v66)(v66, 0, 0);
      if ( *(LPVOID *)(v66 + 104) == TlsGetValue(dwTlsIndex) )
      {
        ++*(_DWORD *)(v66 + 56);
        CAccessLock::UnsignalNoReaders((CAccessLock *)v66);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 8LL))(v66);
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 8LL))(v66);
        while ( 1 )
        {
          CAccessLock::WaitOnWriters((CAccessLock *)v66);
          *(_QWORD *)v113 = v66;
          (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v66)(v66, 0, 0);
          if ( !*(_DWORD *)(v66 + 60) || *(LPVOID *)(v66 + 104) == TlsGetValue(dwTlsIndex) )
            break;
          COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)v113);
        }
        ++*(_DWORD *)(v66 + 56);
        if ( !ResetEvent(*(HANDLE *)(v66 + 72)) )
        {
          LastError = GetLastError();
          throw &LastError;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 8LL))(v66);
      }
      (*(void (__fastcall **)(__int64 *))(v63[1] + 8))(v63 + 1);
      v67 = *v63;
      v68 = v67 + 56;
      v168 = v67 + 56;
      *(_QWORD *)v113 = v67 + 56;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))(v67 + 56))(v67 + 56, 0, 0);
      if ( *(LPVOID *)(v67 + 160) == TlsGetValue(dwTlsIndex) )
      {
        ++*(_DWORD *)(v67 + 112);
        CAccessLock::UnsignalNoReaders((CAccessLock *)(v67 + 56));
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v67 + 56);
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v67 + 56);
        while ( 1 )
        {
          CAccessLock::WaitOnWriters((CAccessLock *)(v67 + 56));
          *(_QWORD *)v113 = v67 + 56;
          (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v68)(v67 + 56, 0, 0);
          if ( !*(_DWORD *)(v67 + 116) || *(LPVOID *)(v67 + 160) == TlsGetValue(dwTlsIndex) )
            break;
          COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)v113);
        }
        ++*(_DWORD *)(v67 + 112);
        if ( !ResetEvent(*(HANDLE *)(v67 + 128)) )
        {
          v145 = GetLastError();
          throw &v145;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v67 + 56);
      }
      v69 = *(unsigned int *)(v67 + 184);
      if ( *(_DWORD *)(v67 + 188) )
        v70 = *(const WCHAR **)(v67 + 176);
      else
        v70 = &Data;
      if ( HIDWORD(v125[0]) >= (unsigned int)v69 )
      {
        v72 = v124;
      }
      else
      {
        v71 = (unsigned __int8 *)operator new[](v69);
        if ( !v71 )
        {
          v146 = 14;
          throw &v146;
        }
        if ( v124 )
          operator delete[](v124);
        v72 = v71;
        v124 = v71;
        HIDWORD(v125[0]) = v69;
      }
      if ( (_DWORD)v69 )
        memcpy_0(v72, v70, v69);
      LODWORD(v125[0]) = v69;
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68) )
      {
        (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v68)(v68, 0, 0);
        v40 = (*(_DWORD *)(v68 + 56))-- == 1;
        if ( v40 && !SetEvent(*(HANDLE *)(v68 + 72)) )
        {
          v147 = GetLastError();
          throw &v147;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v68);
      }
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66) )
      {
        (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v66)(v66, 0, 0);
        v40 = (*(_DWORD *)(v66 + 56))-- == 1;
        if ( v40 && !SetEvent(*(HANDLE *)(v66 + 72)) )
        {
          v148 = GetLastError();
          throw &v148;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 8LL))(v66);
      }
      v31 = ++dwBytes_4a;
      CReaderProxy::Release((CReaderProxy *)*v62);
      operator delete(v62);
      v129 = 0;
      v73 = dwBytes;
      v74 = dwBytes + 1;
      v75 = v112;
      if ( dwBytes )
      {
        if ( v112 >= v74 )
        {
          v78 = Src;
        }
        else
        {
          v76 = operator new[](v74);
          v77 = v76;
          if ( !v76 )
          {
            v149 = 14;
            throw &v149;
          }
          memcpy_0(v76, Src, dwBytes);
          operator delete[](Src);
          v78 = v77;
          Src = v77;
          v75 = dwBytes + 1;
          v112 = dwBytes + 1;
          v73 = dwBytes;
        }
      }
      else
      {
        if ( v112 >= v74 )
        {
          v78 = Src;
        }
        else
        {
          v85 = operator new[](v74);
          if ( !v85 )
          {
            v150 = 14;
            throw &v150;
          }
          if ( Src )
            operator delete[](Src);
          v78 = v85;
          Src = v85;
          v75 = dwBytes + 1;
          v112 = dwBytes + 1;
        }
        v73 = 0;
      }
      v78[v73] = v69;
      v86 = v73 + 1;
      dwBytes = v86;
      v34 = &Data;
      v87 = (unsigned __int8 *)&Data;
      v88 = (unsigned int *)HIDWORD(v125[0]);
      v89 = v124;
      if ( HIDWORD(v125[0]) )
        v87 = v124;
      if ( (_DWORD)v69 )
      {
        v90 = v69 + v86;
        if ( v86 )
        {
          if ( v75 < v90 )
          {
            v91 = operator new[](v90);
            v92 = v91;
            if ( !v91 )
            {
              v151 = 14;
              throw &v151;
            }
            memcpy_0(v91, Src, dwBytes);
            operator delete[](Src);
            v78 = v92;
            Src = v92;
            v112 = v90;
            v86 = dwBytes;
          }
        }
        else
        {
          if ( v75 < v90 )
          {
            v93 = operator new[](v90);
            if ( !v93 )
            {
              v152 = 14;
              throw &v152;
            }
            if ( Src )
              operator delete[](Src);
            v78 = v93;
            Src = v93;
            v112 = v90;
          }
          v86 = 0;
        }
        memcpy_0(&v78[v86], v87, v69);
        dwBytes = v69 + v86;
        v89 = v124;
        v88 = (unsigned int *)HIDWORD(v125[0]);
      }
      v94 = v172;
      if ( (v172 & 0x220) == 0x20 )
      {
        v95 = 0;
        while ( v95 < v127 )
        {
          if ( v132 <= v95 )
            v96 = 0;
          else
            v96 = (unsigned __int8 *)*((_QWORD *)Block + (int)v95);
          v97 = *v96;
          if ( v120 <= v95 )
            v98 = 0;
          else
            v98 = *((_QWORD *)v121 + (int)v95);
          if ( v127 <= v95 )
            v99 = 0;
          else
            v99 = (const unsigned __int8 *)*((_QWORD *)v128 + (int)v95);
          v100 = (const unsigned __int8 *)&Data;
          if ( (_DWORD)v88 )
            v100 = v89;
          v113[0] = 0;
          v114[0] = 0;
          if ( (unsigned int)ParseAtr(v100, v113, (unsigned int *)v89, v88, 0x21u) )
          {
            if ( v98 && v97 )
            {
              v103 = v97;
              if ( v113[0] == v97 )
                goto LABEL_181;
            }
            else if ( (unsigned int)ParseAtr(v99, v114, v101, v102, 0x21u) )
            {
              v103 = v114[0];
              if ( (!v97 || v114[0] == v97) && v113[0] == v114[0] )
              {
                if ( v98 )
                {
LABEL_181:
                  for ( ii = 0; ii < v103; ++ii )
                  {
                    if ( (v100[ii] & *(_BYTE *)(ii + v98)) != v99[ii] )
                      goto LABEL_189;
                  }
                }
                else
                {
                  for ( jj = 0; jj < v114[0]; ++jj )
                  {
                    if ( v100[jj] != v99[jj] )
                      goto LABEL_189;
                  }
                }
                v94 = v172 | 0x40;
                break;
              }
            }
          }
LABEL_189:
          ++v95;
          v94 = v172;
          v89 = v124;
          v88 = (unsigned int *)HIDWORD(v125[0]);
        }
        v31 = dwBytes_4a;
      }
      v106 = v94 | 2;
      if ( v94 == (*v115 & 0x1FC) )
        v106 = v94;
      *v115 = ((unsigned __int16)v116 << 16) + v106;
      v36 = v112;
      v35 = Src;
    }
    v32 = ++v122;
    String = NextString(lpString1);
  }
  if ( !v31 )
  {
    v154 = -2146435026;
    throw &v154;
  }
  *a11 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v38 = HeapAlloc(ProcessHeap, 8u, dwBytes);
  *a10 = v38;
  if ( !v38 )
  {
    v155 = -2146435066;
    throw &v155;
  }
  if ( v36 )
    v34 = (const WCHAR *)Src;
  memcpy_0(v38, v34, *a11);
  if ( v166 )
  {
    v39 = v167;
    (**(void (__fastcall ***)(_DWORD *, _QWORD, _QWORD))v167)(v167, 0, 0);
    if ( *((LPVOID *)v39 + 7) == TlsGetValue(dwTlsIndex) )
    {
      v40 = v39[16]-- == 1;
      if ( v40 )
      {
        *((_QWORD *)v39 + 7) = 0;
        if ( !SetEvent(*((HANDLE *)v39 + 9)) )
          GetLastError();
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v39 + 8LL))(v39);
  }
  if ( Block )
    operator delete[](Block);
  if ( v121 )
    operator delete[](v121);
  if ( v128 )
    operator delete[](v128);
  if ( v124 )
    operator delete[](v124);
  if ( Src )
    operator delete[](Src);
  return v117;
}

```

## disassembly

```asm
0x180007910  mov     r11, rsp
0x180007913  mov     [r11+10h], rbx
0x180007917  mov     [r11+18h], rsi
0x18000791b  mov     [r11+8], rcx
0x18000791f  push    rdi
0x180007920  push    r12
0x180007922  push    r13
0x180007924  push    r14
0x180007926  push    r15
0x180007928  sub     rsp, 190h
0x18000792f  mov     r15, r9
0x180007932  mov     r14d, r8d
0x180007935  mov     rdi, rdx
0x180007938  mov     rsi, rcx
0x18000793b  mov     [rsp+1B8h+var_50], rcx
0x180007943  xor     r12d, r12d
0x180007946  mov     [rsp+1B8h+var_14C], r12d
0x18000794b  lea     rcx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180007952  mov     [rsp+1B8h+var_180], rcx
0x180007957  mov     [rsp+1B8h+Src], r12
0x18000795c  mov     eax, r12d
0x18000795f  mov     dword ptr [rsp+1B8h+dwBytes], eax
0x180007963  mov     [rsp+1B8h+var_170], eax
0x180007967  mov     [rsp+1B8h+var_16C], r12d
0x18000796c  mov     [r11-128h], rcx
0x180007973  mov     [r11-120h], r12
0x18000797a  mov     [r11-118h], r12
0x180007981  lea     rcx, ??_7?$CDynamicArray@VCServiceThread@@@@6B@; const CDynamicArray<CServiceThread>::`vftable'
0x180007988  mov     [r11-110h], rcx
0x18000798f  mov     [r11-104h], r12d
0x180007996  mov     dword ptr [rsp+1B8h+dwBytes+4], eax
0x18000799a  mov     [rsp+1B8h+var_108], eax
0x1800079a1  mov     [r11-100h], r12
0x1800079a8  mov     [rsp+1B8h+var_148], rcx
0x1800079ad  mov     [rsp+1B8h+var_13C], r12d
0x1800079b2  mov     [r11+38h], eax
0x1800079b6  mov     [rsp+1B8h+var_140], eax
0x1800079ba  mov     [r11-138h], r12
0x1800079c1  mov     [r11-0F0h], rcx
0x1800079c8  mov     ebx, r12d
0x1800079cb  mov     [rsp+1B8h+var_E4], ebx
0x1800079d2  mov     r13d, r12d
0x1800079d5  mov     [rsp+1B8h+var_160], r12d
0x1800079da  mov     [r11-0E8h], r12d
0x1800079e1  mov     [r11-0E0h], r12
0x1800079e8  mov     rdx, [rsi+48h]; lpTlsValue
0x1800079ec  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800079f2  call    cs:__imp_TlsSetValue
0x1800079f8  test    eax, eax
0x1800079fa  jz      loc_180008510
0x180007a00  mov     rdx, [rsi]; lpTlsValue
0x180007a03  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x180007a09  call    cs:__imp_TlsSetValue
0x180007a0f  test    eax, eax
0x180007a11  jz      loc_180008510
0x180007a17  mov     eax, 1
0x180007a1c  xchg    eax, cs:?g_fExtendShutdownTimer@@3JA; long g_fExtendShutdownTimer
0x180007a22  add     rsi, 50h ; 'P'
0x180007a26  mov     [rsp+1B8h+var_38], rsi
0x180007a2e  mov     rcx, rsi; this
0x180007a31  call    ?Grab@CMutex@@QEAAXXZ; CMutex::Grab(void)
0x180007a36  mov     rax, [rsp+1B8h+arg_0]
0x180007a3e  mov     [rsp+1B8h+var_48], rax
0x180007a46  mov     rax, [rsp+1B8h+arg_28]
0x180007a4e  cmp     byte ptr [rax], 0
0x180007a51  jz      loc_1800089BD
0x180007a57  test    r14d, r14d
0x180007a5a  jnz     short loc_180007A7B
0x180007a5c  mov     [rsp+1B8h+pExceptionObject], 80100011h
0x180007a67  lea     rdx, _TI1K; pThrowInfo
0x180007a6e  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x180007a76  call    _CxxThrowException_0
0x180007a7b  mov     ecx, [rsp+1B8h+arg_20]
0x180007a82  test    ecx, ecx
0x180007a84  jz      short loc_180007A5C
0x180007a86  cmp     [rsp+1B8h+arg_40], 0
0x180007a8e  jz      short loc_180007A5C
0x180007a90  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180007a97  mov     r8d, 4
0x180007a9d  test    r14d, r14d
0x180007aa0  jz      loc_180007C11
0x180007aa6  cmp     ebx, r13d
0x180007aa9  jnb     loc_180007E51
0x180007aaf  lea     eax, [rbx+1]
0x180007ab2  mov     [rsp+1B8h+var_E4], eax
0x180007ab9  mov     eax, ebx
0x180007abb  mov     rdx, [rsp+1B8h+Block]
0x180007ac3  mov     [rdx+rax*8], rdi
0x180007ac7  movzx   ebx, byte ptr [rdi]
0x180007aca  dec     r14d
0x180007acd  cmp     ebx, r14d
0x180007ad0  ja      loc_1800089FB
0x180007ad6  cmp     ebx, 21h ; '!'
0x180007ad9  ja      loc_180008A1A
0x180007adf  test    ecx, ecx
0x180007ae1  jz      loc_180008AD4
0x180007ae7  movzx   r13d, byte ptr [r15]
0x180007aeb  dec     ecx
0x180007aed  mov     [rsp+1B8h+arg_20], ecx
0x180007af4  cmp     r13d, ecx
0x180007af7  ja      loc_180008A39
0x180007afd  inc     rdi
0x180007b00  inc     r15
0x180007b03  test    r13d, r13d
0x180007b06  jz      loc_180007BE9
0x180007b0c  cmp     ebx, r13d
0x180007b0f  jnz     loc_180008A77
0x180007b15  test    ebx, ebx
0x180007b17  jz      short loc_180007B6F
0x180007b19  mov     edx, r12d
0x180007b1c  cmp     ebx, 8
0x180007b1f  jb      short loc_180007B5C
0x180007b21  lea     eax, [rbx-1]
0x180007b24  mov     ecx, eax
0x180007b26  add     rax, r15
0x180007b29  cmp     rdi, rax
0x180007b2c  ja      short loc_180007B37
0x180007b2e  lea     rax, [rcx+rdi]
0x180007b32  cmp     rax, r15
0x180007b35  jnb     short loc_180007B5C
0x180007b37  mov     ecx, ebx
0x180007b39  and     ecx, 0FFFFFFF8h
0x180007b3c  mov     eax, edx
0x180007b3e  movq    xmm1, qword ptr [r15+rax]
0x180007b44  movq    xmm0, qword ptr [rdi+rax]
0x180007b49  andps   xmm1, xmm0
0x180007b4c  movq    qword ptr [rdi+rax], xmm1
0x180007b51  add     edx, 8
0x180007b54  cmp     edx, ecx
0x180007b56  jb      short loc_180007B3C
0x180007b58  cmp     edx, ebx
0x180007b5a  jnb     short loc_180007B6F
0x180007b5c  mov     eax, edx
0x180007b5e  lea     rcx, [rdi+rax]
0x180007b62  movzx   eax, byte ptr [r15+rax]
0x180007b67  and     [rcx], al
0x180007b69  inc     edx
0x180007b6b  cmp     edx, ebx
0x180007b6d  jb      short loc_180007B5C
0x180007b6f  mov     esi, [rsp+1B8h+var_13C]
0x180007b73  mov     eax, dword ptr [rsp+1B8h+arg_30]
0x180007b7a  cmp     esi, eax
0x180007b7c  jnb     loc_180007FAB
0x180007b82  mov     rcx, [rsp+1B8h+var_138]
0x180007b8a  lea     eax, [rsi+1]
0x180007b8d  mov     [rsp+1B8h+var_13C], eax
0x180007b91  mov     [rcx+rsi*8], r15
0x180007b95  mov     esi, [rsp+1B8h+var_104]
0x180007b9c  mov     eax, dword ptr [rsp+1B8h+dwBytes+4]
0x180007ba0  cmp     esi, eax
0x180007ba2  jnb     loc_180007DA7
0x180007ba8  lea     eax, [rsi+1]
0x180007bab  mov     [rsp+1B8h+var_104], eax
0x180007bb2  mov     rcx, [rsp+1B8h+var_100]
0x180007bba  mov     [rcx+rsi*8], rdi
0x180007bbe  sub     r14d, ebx
0x180007bc1  add     rdi, rbx
0x180007bc4  mov     ecx, [rsp+1B8h+arg_20]
0x180007bcb  sub     ecx, r13d
0x180007bce  mov     [rsp+1B8h+arg_20], ecx
0x180007bd5  add     r15, r13
0x180007bd8  mov     r13d, [rsp+1B8h+var_160]
0x180007bdd  mov     ebx, [rsp+1B8h+var_E4]
0x180007be4  jmp     loc_180007A90
0x180007be9  mov     esi, [rsp+1B8h+var_13C]
0x180007bed  mov     eax, dword ptr [rsp+1B8h+arg_30]
0x180007bf4  cmp     esi, eax
0x180007bf6  jnb     loc_1800083F4
0x180007bfc  mov     rcx, [rsp+1B8h+var_138]
0x180007c04  lea     edx, [rsi+1]
0x180007c07  mov     [rsp+1B8h+var_13C], edx
0x180007c0b  mov     [rcx+rsi*8], r12
0x180007c0f  jmp     short loc_180007B95
0x180007c11  test    ecx, ecx
0x180007c13  jnz     loc_180008AF3
0x180007c19  mov     [rsp+1B8h+var_F8], r12
0x180007c21  mov     r14d, r12d
0x180007c24  mov     dword ptr [rsp+1B8h+dwBytes+4], r12d
0x180007c29  mov     ebx, r12d
0x180007c2c  mov     [rsp+1B8h+var_130], ebx
0x180007c33  mov     rcx, [rsp+1B8h+arg_28]; unsigned __int16 *
0x180007c3b  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x180007c40  lea     r13, Data
0x180007c47  mov     rdi, [rsp+1B8h+Src]
0x180007c4c  mov     esi, [rsp+1B8h+var_16C]
0x180007c50  mov     [rsp+1B8h+lpString1], rax
0x180007c58  test    rax, rax
0x180007c5b  jnz     loc_180007EF8
0x180007c61  test    r14d, r14d
0x180007c64  jz      loc_180008EE3
0x180007c6a  mov     ebx, dword ptr [rsp+1B8h+dwBytes]
0x180007c6e  mov     rdi, [rsp+1B8h+arg_50]
0x180007c76  mov     [rdi], ebx
0x180007c78  call    cs:__imp_GetProcessHeap
0x180007c7e  mov     rcx, rax; hHeap
0x180007c81  mov     r8d, ebx; dwBytes
0x180007c84  mov     edx, 8; dwFlags
0x180007c89  call    cs:__imp_HeapAlloc
0x180007c8f  mov     rcx, [rsp+1B8h+arg_48]
0x180007c97  mov     [rcx], rax
0x180007c9a  test    rax, rax
0x180007c9d  jz      loc_180008F02
0x180007ca3  test    esi, esi
0x180007ca5  mov     rbx, [rsp+1B8h+Src]
0x180007caa  cmovnz  r13, rbx
0x180007cae  mov     r8d, [rdi]; Size
0x180007cb1  mov     rdx, r13; Src
0x180007cb4  mov     rcx, rax; void *
0x180007cb7  call    memcpy_0
0x180007cbc  nop
0x180007cbd  cmp     [rsp+1B8h+var_48], 0
0x180007cc6  jz      short loc_180007D21
0x180007cc8  mov     rsi, [rsp+1B8h+var_38]
0x180007cd0  mov     rax, [rsi]
0x180007cd3  xor     r8d, r8d
0x180007cd6  xor     edx, edx
0x180007cd8  mov     rcx, rsi
0x180007cdb  mov     rax, [rax]
0x180007cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce3  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180007ce9  call    cs:__imp_TlsGetValue
0x180007cef  cmp     [rsi+38h], rax
0x180007cf3  jnz     short loc_180007D11
0x180007cf5  add     dword ptr [rsi+40h], 0FFFFFFFFh
0x180007cf9  jnz     short loc_180007D11
0x180007cfb  mov     [rsi+38h], r12
0x180007cff  mov     rcx, [rsi+48h]; hEvent
0x180007d03  call    cs:__imp_SetEvent
0x180007d09  test    eax, eax
0x180007d0b  jz      loc_180008F22
0x180007d11  mov     rax, [rsi]
0x180007d14  mov     rcx, rsi
0x180007d17  mov     rax, [rax+8]
0x180007d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d20  nop
0x180007d21  mov     rax, [rsp+1B8h+Block]
0x180007d29  test    rax, rax
0x180007d2c  jz      short loc_180007D37
0x180007d2e  mov     rcx, rax; Block
0x180007d31  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180007d36  nop
0x180007d37  mov     rax, [rsp+1B8h+var_138]
0x180007d3f  test    rax, rax
0x180007d42  jz      short loc_180007D4D
0x180007d44  mov     rcx, rax; Block
0x180007d47  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180007d4c  nop
0x180007d4d  mov     rax, [rsp+1B8h+var_100]
0x180007d55  test    rax, rax
0x180007d58  jz      short loc_180007D63
0x180007d5a  mov     rcx, rax; Block
0x180007d5d  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180007d62  nop
0x180007d63  mov     rax, [rsp+1B8h+var_120]
0x180007d6b  test    rax, rax
0x180007d6e  jz      short loc_180007D79
0x180007d70  mov     rcx, rax; Block
0x180007d73  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180007d78  nop
0x180007d79  test    rbx, rbx
0x180007d7c  jz      short loc_180007D86
0x180007d7e  mov     rcx, rbx; Block
0x180007d81  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180007d86  mov     eax, [rsp+1B8h+var_14C]
0x180007d8a  lea     r11, [rsp+1B8h+var_28]
0x180007d92  mov     rbx, [r11+38h]
0x180007d96  mov     rsi, [r11+40h]
0x180007d9a  mov     rsp, r11
0x180007d9d  pop     r15
0x180007d9f  pop     r14
0x180007da1  pop     r13
0x180007da3  pop     r12
0x180007da5  pop     rdi
0x180007da6  retn
0x180007da7  test    eax, eax
0x180007da9  mov     ecx, 4
0x180007dae  cmovz   eax, ecx
0x180007db1  mov     dword ptr [rsp+1B8h+dwBytes+4], eax
0x180007db5  cmp     esi, eax
0x180007db7  jge     loc_1800088C0
0x180007dbd  movsxd  rcx, eax
0x180007dc0  mov     eax, 8
0x180007dc5  mul     rcx
0x180007dc8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007dcf  cmovb   rax, rcx
0x180007dd3  mov     rcx, rax; unsigned __int64
0x180007dd6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007ddb  mov     rcx, rax
0x180007dde  mov     [rsp+1B8h+var_158], rax
0x180007de3  test    rax, rax
0x180007de6  jz      loc_180008AB5
0x180007dec  mov     r8d, r12d
0x180007def  mov     r9d, [rsp+1B8h+var_104]
0x180007df7  test    r9d, r9d
0x180007dfa  jz      short loc_180007E1F
0x180007dfc  mov     eax, r8d
0x180007dff  lea     rdx, ds:0[rax*8]
0x180007e07  mov     rax, [rsp+1B8h+var_100]
0x180007e0f  mov     rax, [rax+rdx]
0x180007e13  mov     [rcx+rdx], rax
  ... truncated ...
```
