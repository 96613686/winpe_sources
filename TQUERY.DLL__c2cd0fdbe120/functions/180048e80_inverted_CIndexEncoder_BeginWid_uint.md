# inverted::CIndexEncoder::BeginWid(uint)

- ea: `0x180048e80`
- end: `0x18004a76e`
- name: `?BeginWid@CIndexEncoder@inverted@@UEAAXI@Z`
- size: `6382`
- prototype: `void __fastcall(inverted::CIndexEncoder *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18002aafc`
- `0x180038f08`
- `0x180038f28`
- `0x180047e78`
- `0x180048dcc`
- `0x180048e48`
- `0x180048e80`
- `0x18004afb0`
- `0x18004b014`
- `0x18004b088`
- `0x18004d308`
- `0x18004d754`
- `0x18004d9d8`
- `0x180050858`
- `0x1801183f0`
- `0x1801470d4`
- `0x180147190`
- `0x18015708c`
- `0x180189280`
- `0x180189cce`
- `0x18018e79c`
- `0x18018e8cb`
- `0x1802c0010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18004a4bd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18004a4bd`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180049224`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180049224`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180049bd8`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180049bd8`

## string_xrefs

- `0x180049bfa`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x18004a500`: `onecoreuap\base\appmodel\Search\tquery\include\IncrementalCompressor.h`
- `0x18004a51f`: `onecoreuap\base\appmodel\Search\tquery\include\IncrementalCompressor.h`
- `0x18004a53c`: `onecoreuap\base\appmodel\Search\tquery\include\IncrementalCompressor.h`
- `0x18004a55b`: `onecoreuap\base\appmodel\Search\tquery\include\IncrementalCompressor.h`
- `0x18004a578`: `onecoreuap\base\appmodel\Search\tquery\include\IncrementalCompressor.h`
- `0x18004a597`: `onecoreuap\base\appmodel\Search\tquery\include\IncrementalCompressor.h`
- `0x18004a701`: `onecoreuap\base\appmodel\Search\tquery\include\IncrementalCompressor.h`
- `0x18004a720`: `onecoreuap\base\appmodel\Search\tquery\include\IncrementalCompressor.h`
- `0x18004a73d`: `onecoreuap\base\appmodel\Search\tquery\include\IncrementalCompressor.h`
- `0x18004a75c`: `onecoreuap\base\appmodel\Search\tquery\include\IncrementalCompressor.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall inverted::CIndexEncoder::BeginWid(inverted::CIndexEncoder *this, __int64 a2, __int64 a3)
{
  unsigned __int64 v3; // rsi
  char *v5; // rbp
  int *v6; // r15
  _DWORD *v7; // r12
  _BYTE *v8; // r13
  int v9; // r14d
  int v10; // edi
  int v11; // r15d
  __int64 v12; // rax
  char *v13; // rdi
  __int64 v14; // rax
  int v15; // ecx
  int v16; // r14d
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // rdx
  unsigned int v20; // eax
  unsigned int v21; // ecx
  __int64 v22; // r8
  __int64 v23; // rax
  int v24; // ecx
  int v25; // ecx
  unsigned int v26; // r11d
  __int64 v27; // rcx
  unsigned int v28; // r9d
  __int64 v29; // rcx
  unsigned int v30; // r10d
  __int64 v31; // rcx
  unsigned int v32; // r8d
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  char *v38; // r14
  Concurrency::details::platform *v39; // rcx
  unsigned int v40; // edx
  unsigned int v41; // eax
  _QWORD *v42; // r15
  __int64 v43; // rbp
  unsigned __int64 CurrentThreadId; // r12
  __int64 v45; // r13
  signed __int64 k; // rdi
  __int64 v47; // rax
  __int64 v48; // r11
  __int64 v49; // r11
  signed __int64 v50; // rax
  __int64 v51; // rax
  void **v52; // rax
  _BYTE *v53; // r12
  _QWORD *v54; // r8
  char v55; // si
  char *v56; // r13
  int v57; // ecx
  int v58; // eax
  int v59; // ecx
  int v60; // r12d
  int v61; // ecx
  _DWORD *v62; // r14
  int v63; // r15d
  int v64; // ecx
  inverted::CIncrementalCompressor *v65; // rcx
  int v66; // r14d
  int v67; // ecx
  int v68; // eax
  int v69; // ecx
  int v70; // r14d
  __int64 v71; // rcx
  _DWORD *v72; // r12
  _BYTE *v73; // r15
  int v74; // eax
  int v75; // r14d
  int v76; // edi
  __int64 v77; // rax
  _DWORD *v78; // rdi
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // r8
  unsigned int v92; // eax
  __int64 v93; // rdx
  __int64 v94; // r8
  int v95; // ecx
  __int64 v96; // rdi
  _QWORD *v97; // r14
  __int64 v98; // r15
  _QWORD *j; // rdi
  _QWORD *v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // rcx
  __int64 v105; // rdx
  __int64 v106; // r8
  int v107; // edi
  __int64 v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // rcx
  __int64 v111; // r8
  int v112; // edi
  __int64 v113; // rax
  int v114; // edi
  __int64 v115; // rax
  __int64 v116; // rdx
  unsigned int v117; // eax
  const char *v118; // r9
  int v119; // eax
  int v120; // eax
  int v121; // ecx
  __int64 v122; // rdx
  unsigned int v123; // r8d
  int v124; // ecx
  __int64 v125; // rdx
  int v126; // r8d
  int v127; // ecx
  int v128; // ecx
  int v129; // ecx
  int v130; // ecx
  int v131; // ecx
  int v132; // ecx
  _QWORD *v133; // rax
  _QWORD *v134; // rdx
  unsigned __int64 v135; // rcx
  int v136; // [rsp+20h] [rbp-98h]
  _BYTE v137[136]; // [rsp+30h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  _BYTE *i; // [rsp+C0h] [rbp+8h] BYREF
  int v140; // [rsp+C8h] [rbp+10h] BYREF
  _DWORD *v141; // [rsp+D0h] [rbp+18h]
  char *v142; // [rsp+D8h] [rbp+20h]

  v3 = (unsigned int)a2;
  v5 = (char *)this + 186288;
  v6 = (int *)((char *)this + 252148);
  v142 = (char *)this + 252148;
  v7 = (_DWORD *)((char *)this + 219100);
  v8 = (char *)this + 219089;
  for ( i = (char *)this + 219089; ; v8 = i )
  {
    if ( *((_DWORD *)this + 63036) == *((_DWORD *)this + 63033) )
    {
      v119 = *v6;
      if ( (unsigned int)v3 < *v6 )
        v9 = (2 * (v119 - v3)) | 1;
      else
        v9 = 2 * (v3 - v119);
      *v6 = v3;
      v8 = v5 + 32801;
      i = v5 + 32801;
    }
    else
    {
      v9 = v3 - *((_DWORD *)this + 63038) - 1;
      *((_DWORD *)v5 + 8202) = *v7;
    }
    *((_DWORD *)this + 63038) = v3;
    v10 = *((_DWORD *)this + 63033);
    v11 = *((_DWORD *)this + 63036);
    if ( *((_DWORD *)v5 + 8202) == 0x2000 )
    {
      if ( !*v8 )
        inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIncrementalCompressor *)v5);
      inverted::CIncrementalCompressor::RestartInternalBuffer((inverted::CIncrementalCompressor *)v5);
      if ( *v8 && (unsigned int)(*((_DWORD *)v5 + 8202) + 1) >= 0x2000 )
      {
        inverted::CIncrementalCompressor::EncodeRemainingInternalBuffer((inverted::CIncrementalCompressor *)v5);
        inverted::CIncrementalCompressor::RestartInternalBuffer((inverted::CIncrementalCompressor *)v5);
      }
    }
    v12 = *((unsigned int *)v5 + 8202);
    if ( (unsigned int)v12 >= 0x2000 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
      inverted::CorruptionCallback::ReportCorruption(
        2147942413LL,
        "onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IncrementalCompressor.h",
        141);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IncrementalCompressor.h",
        (const char *)0x8007000DLL,
        v136);
    }
    v141 = v7;
    *v7 = v12;
    *(_DWORD *)&v5[4 * v12 + 32] = v10 - v11;
    ++*((_DWORD *)v5 + 8202);
    v13 = (char *)this + 219112;
    if ( *((_DWORD *)this + 62980) == 0x2000 )
    {
      if ( !*((_BYTE *)this + 251913) )
        inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 219112));
      inverted::CIncrementalCompressor::RestartInternalBuffer((inverted::CIndexEncoder *)((char *)this + 219112));
      if ( *((_BYTE *)this + 251913) && (unsigned int)(*((_DWORD *)this + 62980) + 1) >= 0x2000 )
      {
        inverted::CIncrementalCompressor::EncodeRemainingInternalBuffer((inverted::CIndexEncoder *)((char *)this + 219112));
        inverted::CIncrementalCompressor::RestartInternalBuffer((inverted::CIndexEncoder *)((char *)this + 219112));
      }
    }
    v14 = *((unsigned int *)this + 62980);
    if ( (unsigned int)v14 >= 0x2000 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
      inverted::CorruptionCallback::ReportCorruption(
        2147942413LL,
        "onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IncrementalCompressor.h",
        141);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IncrementalCompressor.h",
        (const char *)0x8007000DLL,
        v136);
    }
    *((_DWORD *)this + 62981) = v14;
    *(_DWORD *)&v13[4 * v14 + 32] = v9;
    ++*((_DWORD *)this + 62980);
    v15 = *((_DWORD *)this + 63030);
    if ( !v15 )
      goto LABEL_19;
    v121 = v15 - 1;
    if ( !v121 )
    {
      a2 = *((unsigned int *)this + 62982);
      a3 = *((unsigned int *)this + 62981);
      if ( (int)a2 + *((_DWORD *)this + 62979) <= (unsigned int)a3 && !*((_BYTE *)this + 251913) )
      {
        v140 = 0;
        (*(void (__fastcall **)(_QWORD, char *, _QWORD, int *))(**((_QWORD **)this + 27391) + 40LL))(
          *((_QWORD *)this + 27391),
          (char *)this + 4 * a2 + 219144,
          (unsigned int)(a3 - a2),
          &v140);
        *((_DWORD *)this + 62982) += v140;
        *((_BYTE *)this + 251912) = 1;
        (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 27391) + 64LL))(
          *((_QWORD *)this + 27391),
          (char *)this + 251932);
      }
LABEL_19:
      v16 = *((_DWORD *)this + 62980) + *((_DWORD *)this + 62983) - *((_DWORD *)this + 62982);
      goto LABEL_20;
    }
    if ( v121 == 1 )
    {
      v122 = *((unsigned int *)this + 62982);
      v123 = *((_DWORD *)this + 62981);
      if ( (int)v122 + *((_DWORD *)this + 62979) <= v123 && !*((_BYTE *)this + 251913) )
      {
        v140 = 0;
        (*(void (__fastcall **)(_QWORD, char *, _QWORD, int *))(**((_QWORD **)this + 27391) + 40LL))(
          *((_QWORD *)this + 27391),
          (char *)this + 4 * v122 + 219144,
          v123 - (unsigned int)v122,
          &v140);
        *((_DWORD *)this + 62982) += v140;
        *((_BYTE *)this + 251912) = 1;
        (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 27391) + 64LL))(
          *((_QWORD *)this + 27391),
          (char *)this + 251932);
      }
      *((_BYTE *)this + 251913) = 1;
      v16 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 27391) + 32LL))(
              *((_QWORD *)this + 27391),
              &v13[4 * *((unsigned int *)this + 62982) + 32],
              (unsigned int)(*((_DWORD *)this + 62980) - *((_DWORD *)this + 62982)))
          + *((_DWORD *)this + 62983);
    }
    else
    {
      v16 = 0;
    }
LABEL_20:
    v17 = *((_DWORD *)this + 63030);
    if ( !v17 )
      goto LABEL_21;
    v124 = v17 - 1;
    if ( !v124 )
    {
      a2 = *((unsigned int *)v5 + 8204);
      a3 = (unsigned int)*v7;
      if ( (int)a2 + *((_DWORD *)v5 + 8201) <= (unsigned int)a3 && !*v8 )
      {
        v140 = 0;
        (*(void (__fastcall **)(_QWORD, char *, _QWORD, int *))(**((_QWORD **)v5 + 2) + 40LL))(
          *((_QWORD *)v5 + 2),
          &v5[4 * a2 + 32],
          (unsigned int)(a3 - a2),
          &v140);
        *((_DWORD *)v5 + 8204) += v140;
        v5[32800] = 1;
        (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)v5 + 2) + 64LL))(*((_QWORD *)v5 + 2), v5 + 32820);
      }
LABEL_21:
      v18 = *((_DWORD *)v5 + 8202) + *((_DWORD *)v5 + 8205) - *((_DWORD *)v5 + 8204);
      goto LABEL_22;
    }
    if ( v124 == 1 )
    {
      v125 = *((unsigned int *)v5 + 8204);
      v126 = *v7;
      if ( (unsigned int)(v125 + *((_DWORD *)v5 + 8201)) <= *v7 && !*v8 )
      {
        v140 = 0;
        (*(void (__fastcall **)(_QWORD, char *, _QWORD, int *))(**((_QWORD **)v5 + 2) + 40LL))(
          *((_QWORD *)v5 + 2),
          &v5[4 * v125 + 32],
          (unsigned int)(v126 - v125),
          &v140);
        *((_DWORD *)v5 + 8204) += v140;
        v5[32800] = 1;
        (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)v5 + 2) + 64LL))(*((_QWORD *)v5 + 2), v5 + 32820);
      }
      *v8 = 1;
      v18 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)v5 + 2) + 32LL))(
              *((_QWORD *)v5 + 2),
              &v5[4 * *((unsigned int *)v5 + 8204) + 32],
              (unsigned int)(*((_DWORD *)v5 + 8202) - *((_DWORD *)v5 + 8204)))
          + *((_DWORD *)v5 + 8205);
    }
    else
    {
      v18 = 0;
    }
LABEL_22:
    if ( (unsigned int)(v16 + v18 + *((_DWORD *)this + 63042)) <= *((_DWORD *)this + 63041) )
      break;
    v56 = (char *)this + 22168;
    while ( 1 )
    {
      v57 = *((_DWORD *)this + 63030);
      if ( !v57 )
        goto LABEL_66;
      v127 = v57 - 1;
      if ( !v127 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 46567) + *((_DWORD *)this + 46570)) <= *((_DWORD *)this + 46569)
          && !*((_BYTE *)this + 186265) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 153464));
        }
LABEL_66:
        v58 = *((_DWORD *)this + 46568) + *((_DWORD *)this + 46571) - *((_DWORD *)this + 46570);
LABEL_67:
        v140 = v58;
        goto LABEL_68;
      }
      if ( v127 == 1 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 46570) + *((_DWORD *)this + 46567)) <= *((_DWORD *)this + 46569)
          && !*((_BYTE *)this + 186265) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 153464));
        }
        *((_BYTE *)this + 186265) = 1;
        v58 = *((_DWORD *)this + 46571)
            + (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 19185) + 32LL))(
                *((_QWORD *)this + 19185),
                (char *)this + 4 * *((unsigned int *)this + 46570) + 153496,
                (unsigned int)(*((_DWORD *)this + 46568) - *((_DWORD *)this + 46570)));
        goto LABEL_67;
      }
      v140 = 0;
LABEL_68:
      v59 = *((_DWORD *)this + 63030);
      if ( !v59 )
        goto LABEL_69;
      v128 = v59 - 1;
      if ( !v128 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 38361) + *((_DWORD *)this + 38364)) <= *((_DWORD *)this + 38363)
          && !*((_BYTE *)this + 153441) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 120640));
        }
LABEL_69:
        v60 = *((_DWORD *)this + 38362) + *((_DWORD *)this + 38365) - *((_DWORD *)this + 38364);
        goto LABEL_70;
      }
      if ( v128 == 1 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 38364) + *((_DWORD *)this + 38361)) <= *((_DWORD *)this + 38363)
          && !*((_BYTE *)this + 153441) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 120640));
        }
        *((_BYTE *)this + 153441) = 1;
        v60 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 15082) + 32LL))(
                *((_QWORD *)this + 15082),
                (char *)this + 4 * *((unsigned int *)this + 38364) + 120672,
                (unsigned int)(*((_DWORD *)this + 38362) - *((_DWORD *)this + 38364)))
            + *((_DWORD *)this + 38365);
      }
      else
      {
        v60 = 0;
      }
LABEL_70:
      v61 = *((_DWORD *)this + 63030);
      if ( !v61 )
      {
        v62 = (_DWORD *)((char *)this + 87816);
LABEL_72:
        v63 = v62[8202] + v62[8205] - v62[8204];
        goto LABEL_73;
      }
      v129 = v61 - 1;
      if ( !v129 )
      {
        v62 = (_DWORD *)((char *)this + 87816);
        if ( (unsigned int)(*((_DWORD *)this + 30155) + *((_DWORD *)this + 30158)) <= *((_DWORD *)this + 30157)
          && !*((_BYTE *)this + 120617) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 87816));
        }
        goto LABEL_72;
      }
      if ( v129 == 1 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 30158) + *((_DWORD *)this + 30155)) <= *((_DWORD *)this + 30157)
          && !*((_BYTE *)this + 120617) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 87816));
        }
        *((_BYTE *)this + 120617) = 1;
        v63 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 10979) + 32LL))(
                *((_QWORD *)this + 10979),
                (char *)this + 4 * *((unsigned int *)this + 30158) + 87848,
                (unsigned int)(*((_DWORD *)this + 30156) - *((_DWORD *)this + 30158)))
            + *((_DWORD *)this + 30159);
      }
      else
      {
        v63 = 0;
      }
LABEL_73:
      v64 = *((_DWORD *)this + 63030);
      if ( !v64 )
        goto LABEL_74;
      v130 = v64 - 1;
      if ( !v130 )
      {
        v65 = (inverted::CIndexEncoder *)((char *)this + 54992);
        if ( (unsigned int)(*((_DWORD *)this + 21949) + *((_DWORD *)this + 21952)) <= *((_DWORD *)this + 21951)
          && !*((_BYTE *)this + 87793) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer(v65);
LABEL_74:
          v65 = (inverted::CIndexEncoder *)((char *)this + 54992);
        }
        v66 = *((_DWORD *)v65 + 8202) + *((_DWORD *)v65 + 8205) - *((_DWORD *)v65 + 8204);
        goto LABEL_76;
      }
      if ( v130 == 1 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 21952) + *((_DWORD *)this + 21949)) <= *((_DWORD *)this + 21951)
          && !*((_BYTE *)this + 87793) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 54992));
        }
        *((_BYTE *)this + 87793) = 1;
        v66 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 6876) + 32LL))(
                *((_QWORD *)this + 6876),
                (char *)this + 4 * *((unsigned int *)this + 21952) + 55024,
                (unsigned int)(*((_DWORD *)this + 21950) - *((_DWORD *)this + 21952)))
            + *((_DWORD *)this + 21953);
      }
      else
      {
        v66 = 0;
      }
LABEL_76:
      v67 = *((_DWORD *)this + 63030);
      if ( !v67 )
        goto LABEL_77;
      v131 = v67 - 1;
      if ( !v131 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 13743) + *((_DWORD *)this + 13746)) <= *((_DWORD *)this + 13745)
          && !*((_BYTE *)this + 54969) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 22168));
        }
LABEL_77:
        v68 = *((_DWORD *)this + 13744) + *((_DWORD *)this + 13747) - *((_DWORD *)this + 13746);
        goto LABEL_78;
      }
      if ( v131 == 1 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 13746) + *((_DWORD *)this + 13743)) <= *((_DWORD *)this + 13745)
          && !*((_BYTE *)this + 54969) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 22168));
        }
        *((_BYTE *)this + 54969) = 1;
        v68 = *((_DWORD *)this + 13747)
            + (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 2773) + 32LL))(
                *((_QWORD *)this + 2773),
                &v56[4 * *((unsigned int *)this + 13746) + 32],
                (unsigned int)(*((_DWORD *)this + 13744) - *((_DWORD *)this + 13746)));
      }
      else
      {
        v68 = 0;
      }
LABEL_78:
      *((_DWORD *)this + 63042) = v140 + v60 + v63 + v66 + v68;
      v69 = *((_DWORD *)this + 63030);
      if ( !v69 )
        goto LABEL_79;
      v132 = v69 - 1;
      if ( !v132 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 62979) + *((_DWORD *)this + 62982)) <= *((_DWORD *)this + 62981)
          && !*((_BYTE *)this + 251913) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 219112));
        }
LABEL_79:
        v70 = *((_DWORD *)this + 62980) + *((_DWORD *)this + 62983) - *((_DWORD *)this + 62982);
        goto LABEL_80;
      }
      if ( v132 == 1 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 62982) + *((_DWORD *)this + 62979)) <= *((_DWORD *)this + 62981)
          && !*((_BYTE *)this + 251913) )
        {
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIndexEncoder *)((char *)this + 219112));
        }
        *((_BYTE *)this + 251913) = 1;
        v70 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 27391) + 32LL))(
                *((_QWORD *)this + 27391),
                &v13[4 * *((unsigned int *)this + 62982) + 32],
                (unsigned int)(*((_DWORD *)this + 62980) - *((_DWORD *)this + 62982)))
            + *((_DWORD *)this + 62983);
      }
      else
      {
        v70 = 0;
      }
LABEL_80:
      v71 = *((unsigned int *)this + 63030);
      v72 = v141;
      v73 = i;
      if ( !(_DWORD)v71 )
        goto LABEL_81;
      v71 = (unsigned int)(v71 - 1);
      if ( !(_DWORD)v71 )
      {
        if ( (unsigned int)(*((_DWORD *)v5 + 8201) + *((_DWORD *)v5 + 8204)) <= *v141 && !*i )
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIncrementalCompressor *)v5);
LABEL_81:
        v74 = *((_DWORD *)v5 + 8202) + *((_DWORD *)v5 + 8205) - *((_DWORD *)v5 + 8204);
        goto LABEL_82;
      }
      if ( (_DWORD)v71 == 1 )
      {
        if ( (unsigned int)(*((_DWORD *)v5 + 8204) + *((_DWORD *)v5 + 8201)) <= *v141 && !*i )
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIncrementalCompressor *)v5);
        *v73 = 1;
        v74 = *((_DWORD *)v5 + 8205)
            + (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)v5 + 2) + 32LL))(
                *((_QWORD *)v5 + 2),
                &v5[4 * *((unsigned int *)v5 + 8204) + 32],
                (unsigned int)(*((_DWORD *)v5 + 8202) - *((_DWORD *)v5 + 8204)));
      }
      else
      {
        v74 = 0;
      }
LABEL_82:
      if ( (unsigned int)(*((_DWORD *)this + 63042) + v70 + v74) <= *((_DWORD *)this + 63041) )
        break;
      v120 = *((_DWORD *)this + 63030);
      if ( v120 == 2 )
        goto LABEL_84;
      *((_DWORD *)this + 63030) = v120 + 1;
    }
    *((_DWORD *)this + 63030) = 0;
    if ( !*((_DWORD *)this + 63039) )
      break;
LABEL_84:
    *((_DWORD *)v5 + 8202) = *v72;
    *((_DWORD *)this + 62980) = *((_DWORD *)this + 62981);
    v75 = *((_DWORD *)this + 63036);
    v76 = *((_DWORD *)this + 63033);
    if ( v75 != v76 )
    {
      if ( *((_DWORD *)v5 + 8202) == 0x2000 )
      {
        if ( !*v73 )
          inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIncrementalCompressor *)v5);
        inverted::CIncrementalCompressor::RestartInternalBuffer((inverted::CIncrementalCompressor *)v5);
        if ( *v73 && (unsigned int)(*((_DWORD *)v5 + 8202) + 1) >= 0x2000 )
        {
          inverted::CIncrementalCompressor::EncodeRemainingInternalBuffer((inverted::CIncrementalCompressor *)v5);
          inverted::CIncrementalCompressor::RestartInternalBuffer((inverted::CIncrementalCompressor *)v5);
        }
      }
      v77 = *((unsigned int *)v5 + 8202);
      if ( (unsigned int)v77 >= 0x2000 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v71, a2, a3);
        inverted::CorruptionCallback::ReportCorruption(
          2147942413LL,
          "onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IncrementalCompressor.h",
          141);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IncrementalCompressor.h",
          (const char *)0x8007000DLL,
          v136);
      }
      *v72 = v77;
      *(_DWORD *)&v5[4 * v77 + 32] = v76 - v75 - 1;
      ++*((_DWORD *)v5 + 8202);
      v56 = (char *)this + 22168;
    }
    inverted::CIndexEncoder::CommitKeyPage(this, 1);
    v78 = (_DWORD *)((char *)this + 6820);
    inverted::CIndexEncoder::AddKeyInfo(this, (inverted::CIndexEncoder *)((char *)this + 6820), v3);
    *((_WORD *)v56 + 16400) = 0;
    *((_QWORD *)v56 + 4101) = 0;
    *((_QWORD *)v56 + 4102) = 0;
    v81 = *((_QWORD *)v56 + 2);
    if ( v81 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)v56 + 2) + 64LL))(*((_QWORD *)v56 + 2), v56 + 32820);
    }
    *((_WORD *)this + 43896) = 0;
    *((_QWORD *)this + 10975) = 0;
    *((_QWORD *)this + 10976) = 0;
    v82 = *((_QWORD *)this + 6876);
    if ( v82 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6876) + 64LL))(
        *((_QWORD *)this + 6876),
        (char *)this + 87812);
    }
    *((_WORD *)this + 60308) = 0;
    *((_QWORD *)this + 15078) = 0;
    *((_QWORD *)this + 15079) = 0;
    v83 = *((_QWORD *)this + 10979);
    if ( v83 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 10979) + 64LL))(
        *((_QWORD *)this + 10979),
        (char *)this + 120636);
    }
    *((_WORD *)this + 76720) = 0;
    *((_QWORD *)this + 19181) = 0;
    *((_QWORD *)this + 19182) = 0;
    v84 = *((_QWORD *)this + 15082);
    if ( v84 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 15082) + 64LL))(
        *((_QWORD *)this + 15082),
        (char *)this + 153460);
    }
    *((_WORD *)this + 93132) = 0;
    *((_QWORD *)this + 23284) = 0;
    *((_QWORD *)this + 23285) = 0;
    v85 = *((_QWORD *)this + 19185);
    if ( v85 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 19185) + 64LL))(
        *((_QWORD *)this + 19185),
        (char *)this + 186284);
    }
    *((_BYTE *)this + 219088) = 0;
    i = (char *)this + 219089;
    *((_BYTE *)this + 219089) = 0;
    *((_QWORD *)this + 27387) = 0;
    *((_QWORD *)this + 27388) = 0;
    v86 = *((_QWORD *)this + 23288);
    if ( v86 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 23288) + 64LL))(
        *((_QWORD *)this + 23288),
        (char *)this + 219108);
    }
    *((_WORD *)this + 125956) = 0;
    *((_QWORD *)this + 31490) = 0;
    *((_QWORD *)this + 31491) = 0;
    v87 = *((_QWORD *)this + 27391);
    if ( v87 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 27391) + 64LL))(
        *((_QWORD *)this + 27391),
        (char *)this + 251932);
    }
    *((_DWORD *)this + 1286) = *v78;
    v88 = *((unsigned __int16 *)this + 3413);
    *((_WORD *)this + 2575) = v88;
    *((_WORD *)this + 2574) = *((_WORD *)this + 3412);
    if ( (unsigned __int16)v88 > 0x680u )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v88, v79, v80);
      inverted::CorruptionCallback::ReportCorruption(
        2147942413LL,
        "onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
        317);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
        (const char *)0x8007000DLL,
        v136);
    }
    memcpy_0((char *)this + 5152, (char *)this + 6828, (unsigned int)v88);
    *((_DWORD *)this + 1704) = v3;
    *((_DWORD *)this + 1705) = *v78;
    v92 = *((unsigned __int16 *)this + 3413);
    *((_WORD *)this + 3413) = v92;
    if ( (unsigned __int16)v92 > 0x680u )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v90, v89, v91);
      inverted::CorruptionCallback::ReportCorruption(
        2147942413LL,
        "onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
        317);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
        (const char *)0x8007000DLL,
        v136);
    }
    v6 = (int *)v142;
    memcpy_0((char *)this + 6828, (char *)this + 6828, v92);
    v95 = *((_DWORD *)this + 63018);
    if ( v95 != -1 )
    {
      v96 = (unsigned int)(*((_DWORD *)this + 63019) - v95);
      v97 = (_QWORD *)*((_QWORD *)this + 31510);
      v98 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*((_QWORD *)this + 31508) + 48LL);
      for ( j = &v97[v96]; v97 < j; ++v97 )
      {
        if ( *v97 )
        {
          v100 = *(_QWORD **)(v98 + 24);
          if ( v100 == *(_QWORD **)(v98 + 32) )
          {
            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
              v98 + 16,
              v100,
              v97);
          }
          else
          {
            *v100 = *v97;
            *(_QWORD *)(v98 + 24) += 8LL;
          }
          *v97 = 0;
        }
      }
      operator delete(*((void **)this + 31510));
      *((_QWORD *)this + 31510) = 0;
      *((_DWORD *)this + 63018) = -1;
      v6 = (int *)v142;
    }
    *(_OWORD *)((char *)this + 252088) = 0;
    *(_OWORD *)((char *)this + 252104) = 0;
    *((_DWORD *)this + 63030) = 0;
    *((_DWORD *)this + 63031) = *((_DWORD *)this + 19);
    *((_QWORD *)this + 31516) = 0;
    *((_QWORD *)this + 31517) = 0;
    *((_DWORD *)this + 63036) = 0;
    *v6 = 0;
    *((_QWORD *)this + 31519) = 0;
    *((_DWORD *)this + 63040) = 0;
    *((_DWORD *)this + 63042) = 0;
    *((_DWORD *)this + 3820) = *((_DWORD *)this + 2123);
    *((_DWORD *)this + 3821) = *((_DWORD *)this + 79457);
    *((_DWORD *)this + 3822) = *((_DWORD *)this + 79459);
    *((_DWORD *)this + 3823) = *((_DWORD *)this + 79460);
    *((_DWORD *)this + 3824) = *((_DWORD *)this + 79461);
    *((_DWORD *)this + 2124) = *((_DWORD *)this + 10);
    *((_DWORD *)this + 2125) = *((_DWORD *)this + 11);
    *((_DWORD *)this + 2126) = *((_DWORD *)this + 12);
    *((_DWORD *)this + 2127) = *((_DWORD *)this + 13);
    *((_DWORD *)this + 2128) = *((_DWORD *)this + 14);
    *((_DWORD *)this + 2129) = *((_DWORD *)this + 15);
    *((_DWORD *)this + 2130) = *((_DWORD *)this + 16);
    *((_DWORD *)this + 2131) = *((_DWORD *)this + 17);
    *((_DWORD *)this + 2132) = *((_DWORD *)this + 18);
    *((_DWORD *)this + 2133) = *((_DWORD *)this + 19);
    *((_DWORD *)this + 2134) = *((_DWORD *)this + 20);
    *((_DWORD *)this + 2135) = *((_DWORD *)this + 21);
    *((_DWORD *)this + 2136) = *((_DWORD *)this + 22);
    v101 = *((unsigned __int16 *)this + 47);
    *((_WORD *)this + 4275) = v101;
    *((_WORD *)this + 4274) = *((_WORD *)this + 46);
    if ( (unsigned __int16)v101 > 0x680u )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v101, v93, v94);
      inverted::CorruptionCallback::ReportCorruption(
        2147942413LL,
        "onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
        317);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
        (const char *)0x8007000DLL,
        v136);
    }
    memcpy_0((char *)this + 8552, (char *)this + 96, (unsigned int)v101);
    *((_DWORD *)this + 2554) = *((_DWORD *)this + 440);
    v104 = *((unsigned __int16 *)this + 883);
    *((_WORD *)this + 5111) = v104;
    *((_WORD *)this + 5110) = *((_WORD *)this + 882);
    if ( (unsigned __int16)v104 > 0x680u )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v104, v102, v103);
      inverted::CorruptionCallback::ReportCorruption(
        2147942413LL,
        "onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
        317);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
        (const char *)0x8007000DLL,
        v136);
    }
    memcpy_0((char *)this + 10224, (char *)this + 1768, (unsigned int)v104);
    *((_OWORD *)this + 743) = *(_OWORD *)((char *)this + 3432);
    *((_OWORD *)this + 744) = *(_OWORD *)((char *)this + 3448);
    v107 = *((_DWORD *)this + 1284);
    *((_DWORD *)this + 2980) = *((_DWORD *)this + 866);
    v108 = *((unsigned __int16 *)this + 1735);
    *((_WORD *)this + 5963) = v108;
    *((_WORD *)this + 5962) = *((_WORD *)this + 1734);
    if ( (unsigned __int16)v108 > 0x680u )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v108, v105, v106);
      inverted::CorruptionCallback::ReportCorruption(
        2147942413LL,
        "onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
        317);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IndexDefinition.h",
        (const char *)0x8007000DLL,
        v136);
    }
    memcpy_0((char *)this + 11928, (char *)this + 3472, (unsigned int)v108);
    *((_DWORD *)this + 3398) = v107;
    v112 = *((_DWORD *)this + 2123);
    if ( *((_DWORD *)v56 + 8202) == 0x2000 )
    {
      if ( !v56[32801] )
        inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIncrementalCompressor *)v56);
      inverted::CIncrementalCompressor::RestartInternalBuffer((inverted::CIncrementalCompressor *)v56);
      if ( v56[32801] && (unsigned int)(*((_DWORD *)v56 + 8202) + 1) >= 0x2000 )
      {
        inverted::CIncrementalCompressor::EncodeRemainingInternalBuffer((inverted::CIncrementalCompressor *)v56);
        inverted::CIncrementalCompressor::RestartInternalBuffer((inverted::CIncrementalCompressor *)v56);
      }
    }
    v113 = *((unsigned int *)v56 + 8202);
    if ( (unsigned int)v113 >= 0x2000 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v110, v109, v111);
      inverted::CorruptionCallback::ReportCorruption(
        2147942413LL,
        "onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IncrementalCompressor.h",
        141);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IncrementalCompressor.h",
        (const char *)0x8007000DLL,
        v136);
    }
    *((_DWORD *)v56 + 8203) = v113;
    *(_DWORD *)&v56[4 * v113 + 32] = v112;
    ++*((_DWORD *)v56 + 8202);
    v114 = *((_DWORD *)this + 79457);
    if ( *((_DWORD *)v56 + 8202) == 0x2000 )
    {
      if ( !v56[32801] )
        inverted::CIncrementalCompressor::EncodeInternalBuffer((inverted::CIncrementalCompressor *)v56);
      inverted::CIncrementalCompressor::RestartInternalBuffer((inverted::CIncrementalCompressor *)v56);
      if ( v56[32801] && (unsigned int)(*((_DWORD *)v56 + 8202) + 1) >= 0x2000 )
      {
        inverted::CIncrementalCompressor::EncodeRemainingInternalBuffer((inverted::CIncrementalCompressor *)v56);
        inverted::CIncrementalCompressor::RestartInternalBuffer((inverted::CIncrementalCompressor *)v56);
      }
    }
    v115 = *((unsigned int *)v56 + 8202);
    if ( (unsigned int)v115 >= 0x2000 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v110, v109, v111);
      inverted::CorruptionCallback::ReportCorruption(
        2147942413LL,
        "onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IncrementalCompressor.h",
        141);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\IncrementalCompressor.h",
        (const char *)0x8007000DLL,
        v136);
    }
    *((_DWORD *)v56 + 8203) = v115;
    *(_DWORD *)&v56[4 * v115 + 32] = v114;
    ++*((_DWORD *)v56 + 8202);
    (*(void (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 3) + 64LL))(
      *((_QWORD *)this + 3),
      (char *)this + 5144,
      (char *)this + 252164);
    *((_DWORD *)this + 63041) = (unsigned int)(*((_DWORD *)this + 63041) - 40) >> 3;
    v7 = v141;
  }
  ++*((_DWORD *)this + 63033);
  *((_DWORD *)this + 79458) = 0;
  v19 = *((_QWORD *)this + 31508);
  v20 = (unsigned int)v3 >> *(_DWORD *)(v19 + 20);
  v21 = *((_DWORD *)this + 63018);
  if ( v20 < v21
    || v20 >= *((_DWORD *)this + 63019)
    || (v22 = *(_QWORD *)(*((_QWORD *)this + 31510) + 8LL * (v20 - v21))) == 0
    || (v23 = *(_QWORD *)(v22 + 8 * ((v3 >> 6) & *(unsigned int *)(v19 + 16))), !_bittest64(&v23, v3 & 0x3F)) )
  {
    v24 = v3;
    if ( *((_DWORD *)this + 20) < (unsigned int)v3 )
      v24 = *((_DWORD *)this + 20);
    *((_DWORD *)this + 20) = v24;
    v25 = v3;
    if ( *((_DWORD *)this + 21) > (unsigned int)v3 )
      v25 = *((_DWORD *)this + 21);
    *((_DWORD *)this + 21) = v25;
    v26 = (unsigned int)v3 / 0x64;
    if ( (unsigned int)v3 / 0x64 < 0x40 )
    {
      v27 = *((_QWORD *)this + 429);
      _bittestandset64(&v27, v26);
      *((_QWORD *)this + 429) = v27;
    }
    v28 = (unsigned int)v3 / 0x3E8;
    if ( (unsigned int)v3 / 0x3E8 < 0x40 )
    {
      v29 = *((_QWORD *)this + 430);
      _bittestandset64(&v29, v28);
      *((_QWORD *)this + 430) = v29;
    }
    v30 = (unsigned int)v3 / 0x2710;
    if ( (unsigned int)v3 / 0x2710 < 0x40 )
    {
      v31 = *((_QWORD *)this + 431);
      _bittestandset64(&v31, v30);
      *((_QWORD *)this + 431) = v31;
    }
    v32 = (unsigned int)v3 / 0x186A0;
    if ( (unsigned int)v3 / 0x186A0 < 0x40 )
    {
      v33 = *((_QWORD *)this + 432);
      _bittestandset64(&v33, v32);
      *((_QWORD *)this + 432) = v33;
    }
    if ( v26 < 0x40 )
    {
      v34 = *((_QWORD *)this + 31511);
      _bittestandset64(&v34, v26);
      *((_QWORD *)this + 31511) = v34;
    }
    if ( v28 < 0x40 )
    {
      v35 = *((_QWORD *)this + 31512);
      _bittestandset64(&v35, v28);
      *((_QWORD *)this + 31512) = v35;
    }
    if ( v30 < 0x40 )
    {
      v36 = *((_QWORD *)this + 31513);
      _bittestandset64(&v36, v30);
      *((_QWORD *)this + 31513) = v36;
    }
    if ( v32 < 0x40 )
    {
      v37 = *((_QWORD *)this + 31514);
      _bittestandset64(&v37, v32);
      *((_QWORD *)this + 31514) = v37;
    }
    v38 = (char *)this + 252064;
    v39 = (Concurrency::details::platform *)*(unsigned int *)(*((_QWORD *)this + 31508) + 20LL);
    v40 = (unsigned int)v3 >> (char)v39;
    v41 = *((_DWORD *)this + 63018);
    if ( (unsigned int)v3 >> (char)v39 < v41 )
    {
      v42 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)this + 252064);
    }
    else if ( v40 >= *((_DWORD *)this + 63019) )
    {
      v42 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)this + 252064);
    }
    else
    {
      v42 = (_QWORD *)(*((_QWORD *)this + 31510) + 8LL * (v40 - v41));
    }
    if ( !*v42 )
    {
      v43 = *(_QWORD *)v38;
      CurrentThreadId = (unsigned int)Concurrency::details::platform::GetCurrentThreadId(v39);
      v45 = 8 * (CurrentThreadId % *(_QWORD *)(v43 + 56));
      for ( k = *(_QWORD *)(*(_QWORD *)(v43 + 48) + v45); k; k = *(_QWORD *)(k + 72) )
      {
        if ( *(_DWORD *)k == (_DWORD)CurrentThreadId )
          goto LABEL_58;
      }
      k = operator new(128, 64);
      i = (_BYTE *)k;
      if ( k )
      {
        v47 = std::_Func_class<inverted::COccReferences,>::operator()(v43 + 64, v137);
        *(_DWORD *)k = CurrentThreadId;
        *(_QWORD *)(k + 8) = *(_QWORD *)v47;
        *(_DWORD *)(k + 16) = *(_DWORD *)(v47 + 8);
        std::vector<std::vector<inverted::SOccStorage>>::vector<std::vector<inverted::SOccStorage>>(k + 24, v47 + 16);
        std::vector<std::vector<inverted::SOccStorage>>::vector<std::vector<inverted::SOccStorage>>(k + 48, v48 + 40);
        *(_QWORD *)(k + 72) = 0;
        sparse_bit_allocator<unsigned __int64>::CAllocatorState::~CAllocatorState(v49);
      }
      else
      {
        k = 0;
      }
      do
      {
        v50 = *(_QWORD *)(*(_QWORD *)(v43 + 48) + v45);
        *(_QWORD *)(k + 72) = v50;
      }
      while ( v50 != _InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(v43 + 48) + v45), k, v50) );
LABEL_58:
      v51 = *(_QWORD *)(k + 32);
      if ( *(_QWORD *)(k + 24) == v51 )
      {
        v116 = *(unsigned int *)(k + 16);
        v117 = *(_DWORD *)(v43 + 28);
        if ( (unsigned int)v116 < v117 )
        {
          v53 = (_BYTE *)(*(_QWORD *)(k + 8) + 8 * v116);
          *(_DWORD *)(k + 16) = v116 + *(_DWORD *)(v43 + 8);
        }
        else
        {
          v53 = _aligned_malloc(8LL * v117, *(unsigned int *)(v43 + 32));
          i = v53;
          if ( !v53 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x430,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
              v118);
          v133 = (_QWORD *)(k + 48);
          v134 = *(_QWORD **)(k + 56);
          if ( v134 == *(_QWORD **)(k + 64) )
          {
            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
              v133,
              v134,
              &i);
            v53 = i;
            v133 = (_QWORD *)(k + 48);
          }
          else
          {
            *v134 = v53;
            *(_QWORD *)(k + 56) += 8LL;
          }
          v135 = *(unsigned int *)(v43 + 24) * ((__int64)(v133[1] - *v133) >> 3);
          i = (_BYTE *)v135;
          if ( v135 > (__int64)(*(_QWORD *)(k + 40) - *(_QWORD *)(k + 24)) >> 3 )
          {
            if ( v135 > 0x1FFFFFFFFFFFFFFFLL )
              std::_Xlength_error("vector too long");
            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(k + 24, &i);
          }
          *(_QWORD *)(k + 8) = v53;
          *(_DWORD *)(k + 16) = *(_DWORD *)(v43 + 8);
        }
      }
      else
      {
        v52 = (void **)(v51 - 8);
        v53 = *v52;
        *(_QWORD *)(k + 32) = v52;
      }
      *v42 = v53;
      memset_0(v53, 0, *(unsigned int *)(v43 + 4));
    }
    v54 = (_QWORD *)(*v42 + 8 * (*(unsigned int *)(*(_QWORD *)v38 + 16LL) & (v3 >> 6)));
    v55 = v3 & 0x3F;
    if ( (*v54 & (1LL << v55)) == 0 )
      *v54 |= 1LL << v55;
    ++*((_DWORD *)this + 63034);
  }
}

```

## disassembly

```asm
0x180048e80  push    rbx
0x180048e82  push    rbp
0x180048e83  push    rsi
0x180048e84  push    rdi
0x180048e85  push    r12
0x180048e87  push    r13
0x180048e89  push    r14
0x180048e8b  push    r15
0x180048e8d  sub     rsp, 78h
0x180048e91  mov     esi, edx
0x180048e93  mov     rbx, rcx
0x180048e96  lea     rbp, [rcx+2D7B0h]
0x180048e9d  lea     r15, [rcx+3D8F4h]
0x180048ea4  mov     [rsp+0B8h+arg_18], r15
0x180048eac  lea     r12, [rbp+802Ch]
0x180048eb3  lea     r13, [rbp+8021h]
0x180048eba  mov     [rsp+0B8h+arg_0], r13
0x180048ec2  mov     eax, [rbx+3D8E4h]
0x180048ec8  cmp     [rbx+3D8F0h], eax
0x180048ece  jz      loc_180049C0C
0x180048ed4  mov     r14d, esi
0x180048ed7  sub     r14d, [rbx+3D8F8h]
0x180048ede  dec     r14d
0x180048ee1  mov     eax, [r12]
0x180048ee5  mov     [rbp+8028h], eax
0x180048eeb  mov     [rbx+3D8F8h], esi
0x180048ef1  mov     edi, [rbx+3D8E4h]
0x180048ef7  mov     r15d, [rbx+3D8F0h]
0x180048efe  cmp     dword ptr [rbp+8028h], 2000h
0x180048f08  jnz     short loc_180048F47
0x180048f0a  cmp     byte ptr [r13+0], 0
0x180048f0f  jnz     short loc_180048F19
0x180048f11  mov     rcx, rbp; this
0x180048f14  call    ?EncodeInternalBuffer@CIncrementalCompressor@inverted@@AEAAXXZ; inverted::CIncrementalCompressor::EncodeInternalBuffer(void)
0x180048f19  mov     rcx, rbp; this
0x180048f1c  call    ?RestartInternalBuffer@CIncrementalCompressor@inverted@@AEAAXXZ; inverted::CIncrementalCompressor::RestartInternalBuffer(void)
0x180048f21  cmp     byte ptr [r13+0], 0
0x180048f26  jz      short loc_180048F47
0x180048f28  mov     eax, [rbp+8028h]
0x180048f2e  inc     eax
0x180048f30  cmp     eax, 2000h
0x180048f35  jb      short loc_180048F47
0x180048f37  mov     rcx, rbp; this
0x180048f3a  call    ?EncodeRemainingInternalBuffer@CIncrementalCompressor@inverted@@AEAAXXZ; inverted::CIncrementalCompressor::EncodeRemainingInternalBuffer(void)
0x180048f3f  mov     rcx, rbp; this
0x180048f42  call    ?RestartInternalBuffer@CIncrementalCompressor@inverted@@AEAAXXZ; inverted::CIncrementalCompressor::RestartInternalBuffer(void)
0x180048f47  mov     eax, [rbp+8028h]
0x180048f4d  cmp     eax, 2000h
0x180048f52  jnb     loc_18004A732
0x180048f58  mov     [rsp+0B8h+arg_10], r12
0x180048f60  mov     [r12], eax
0x180048f64  sub     edi, r15d
0x180048f67  mov     [rbp+rax*4+20h], edi
0x180048f6b  inc     dword ptr [rbp+8028h]
0x180048f71  lea     rdi, [rbx+357E8h]
0x180048f78  cmp     dword ptr [rdi+8028h], 2000h
0x180048f82  jnz     short loc_180048FC5
0x180048f84  cmp     byte ptr [rdi+8021h], 0
0x180048f8b  jnz     short loc_180048F95
0x180048f8d  mov     rcx, rdi; this
0x180048f90  call    ?EncodeInternalBuffer@CIncrementalCompressor@inverted@@AEAAXXZ; inverted::CIncrementalCompressor::EncodeInternalBuffer(void)
0x180048f95  mov     rcx, rdi; this
0x180048f98  call    ?RestartInternalBuffer@CIncrementalCompressor@inverted@@AEAAXXZ; inverted::CIncrementalCompressor::RestartInternalBuffer(void)
0x180048f9d  cmp     byte ptr [rdi+8021h], 0
0x180048fa4  jz      short loc_180048FC5
0x180048fa6  mov     eax, [rdi+8028h]
0x180048fac  inc     eax
0x180048fae  cmp     eax, 2000h
0x180048fb3  jb      short loc_180048FC5
0x180048fb5  mov     rcx, rdi; this
0x180048fb8  call    ?EncodeRemainingInternalBuffer@CIncrementalCompressor@inverted@@AEAAXXZ; inverted::CIncrementalCompressor::EncodeRemainingInternalBuffer(void)
0x180048fbd  mov     rcx, rdi; this
0x180048fc0  call    ?RestartInternalBuffer@CIncrementalCompressor@inverted@@AEAAXXZ; inverted::CIncrementalCompressor::RestartInternalBuffer(void)
0x180048fc5  mov     eax, [rdi+8028h]
0x180048fcb  cmp     eax, 2000h
0x180048fd0  jnb     loc_18004A6F6
0x180048fd6  mov     [rdi+802Ch], eax
0x180048fdc  mov     [rdi+rax*4+20h], r14d
0x180048fe1  inc     dword ptr [rdi+8028h]
0x180048fe7  mov     ecx, [rbx+3D8D8h]
0x180048fed  test    ecx, ecx
0x180048fef  jnz     loc_180049C53
0x180048ff5  mov     r14d, [rdi+8034h]
0x180048ffc  sub     r14d, [rdi+8030h]
0x180049003  add     r14d, [rdi+8028h]
0x18004900a  mov     ecx, [rbx+3D8D8h]
0x180049010  test    ecx, ecx
0x180049012  jnz     loc_180049D1F
0x180049018  mov     ecx, [rbp+8034h]
0x18004901e  sub     ecx, [rbp+8030h]
0x180049024  add     ecx, [rbp+8028h]
0x18004902a  mov     eax, [rbx+3D908h]
0x180049030  add     eax, ecx
0x180049032  add     eax, r14d
0x180049035  cmp     eax, [rbx+3D904h]
0x18004903b  ja      loc_180049349
0x180049041  inc     dword ptr [rbx+3D8E4h]
0x180049047  mov     dword ptr [rbx+4D988h], 0
0x180049051  mov     rdx, [rbx+3D8A0h]
0x180049058  mov     ecx, [rdx+14h]
0x18004905b  mov     eax, esi
0x18004905d  shr     eax, cl
0x18004905f  mov     ecx, [rbx+3D8A8h]
0x180049065  cmp     eax, ecx
0x180049067  jb      short loc_1800490B5
0x180049069  cmp     eax, [rbx+3D8ACh]
0x18004906f  jnb     short loc_1800490B5
0x180049071  sub     eax, ecx
0x180049073  mov     ecx, eax
0x180049075  mov     rax, [rbx+3D8B0h]
0x18004907c  mov     r8, [rax+rcx*8]
0x180049080  test    r8, r8
0x180049083  jz      short loc_1800490B5
0x180049085  mov     edx, [rdx+10h]
0x180049088  mov     rax, rsi
0x18004908b  shr     rax, 6
0x18004908f  and     rdx, rax
0x180049092  mov     eax, esi
0x180049094  and     eax, 3Fh
0x180049097  movzx   ecx, al
0x18004909a  mov     rax, [r8+rdx*8]
0x18004909e  bt      rax, rcx
0x1800490a2  jnb     short loc_1800490B5
0x1800490a4  add     rsp, 78h
0x1800490a8  pop     r15
0x1800490aa  pop     r14
0x1800490ac  pop     r13
0x1800490ae  pop     r12
0x1800490b0  pop     rdi
0x1800490b1  pop     rsi
0x1800490b2  pop     rbp
0x1800490b3  pop     rbx
0x1800490b4  retn
0x1800490b5  mov     ecx, esi
0x1800490b7  cmp     [rbx+50h], esi
0x1800490ba  cmovb   ecx, [rbx+50h]
0x1800490be  mov     [rbx+50h], ecx
0x1800490c1  mov     ecx, esi
0x1800490c3  cmp     [rbx+54h], esi
0x1800490c6  cmova   ecx, [rbx+54h]
0x1800490ca  mov     [rbx+54h], ecx
0x1800490cd  mov     eax, 51EB851Fh
0x1800490d2  mul     esi
0x1800490d4  mov     r11d, edx
0x1800490d7  shr     r11d, 5
0x1800490db  cmp     r11d, 40h ; '@'
0x1800490df  jnb     short loc_1800490F6
0x1800490e1  mov     eax, r11d
0x1800490e4  mov     rcx, [rbx+0D68h]
0x1800490eb  bts     rcx, rax
0x1800490ef  mov     [rbx+0D68h], rcx
0x1800490f6  mov     eax, 10624DD3h
0x1800490fb  mul     esi
0x1800490fd  mov     r9d, edx
0x180049100  shr     r9d, 6
0x180049104  cmp     r9d, 40h ; '@'
0x180049108  jnb     short loc_18004911F
0x18004910a  mov     eax, r9d
0x18004910d  mov     rcx, [rbx+0D70h]
0x180049114  bts     rcx, rax
0x180049118  mov     [rbx+0D70h], rcx
0x18004911f  mov     eax, 0D1B71759h
0x180049124  mul     esi
0x180049126  mov     r10d, edx
0x180049129  shr     r10d, 0Dh
0x18004912d  cmp     r10d, 40h ; '@'
0x180049131  jnb     short loc_180049148
0x180049133  mov     eax, r10d
0x180049136  mov     rcx, [rbx+0D78h]
0x18004913d  bts     rcx, rax
0x180049141  mov     [rbx+0D78h], rcx
0x180049148  mov     eax, 4F8B588Fh
0x18004914d  mul     esi
0x18004914f  mov     r8d, esi
0x180049152  sub     r8d, edx
0x180049155  shr     r8d, 1
0x180049158  add     r8d, edx
0x18004915b  shr     r8d, 10h
0x18004915f  cmp     r8d, 40h ; '@'
0x180049163  jnb     short loc_18004917A
0x180049165  mov     eax, r8d
0x180049168  mov     rcx, [rbx+0D80h]
0x18004916f  bts     rcx, rax
0x180049173  mov     [rbx+0D80h], rcx
0x18004917a  cmp     r11d, 40h ; '@'
0x18004917e  jnb     short loc_180049195
0x180049180  mov     eax, r11d
0x180049183  mov     rcx, [rbx+3D8B8h]
0x18004918a  bts     rcx, rax
0x18004918e  mov     [rbx+3D8B8h], rcx
0x180049195  cmp     r9d, 40h ; '@'
0x180049199  jnb     short loc_1800491B0
0x18004919b  mov     eax, r9d
0x18004919e  mov     rcx, [rbx+3D8C0h]
0x1800491a5  bts     rcx, rax
0x1800491a9  mov     [rbx+3D8C0h], rcx
0x1800491b0  cmp     r10d, 40h ; '@'
0x1800491b4  jnb     short loc_1800491CB
0x1800491b6  mov     eax, r10d
0x1800491b9  mov     rcx, [rbx+3D8C8h]
0x1800491c0  bts     rcx, rax
0x1800491c4  mov     [rbx+3D8C8h], rcx
0x1800491cb  cmp     r8d, 40h ; '@'
0x1800491cf  jnb     short loc_1800491E6
0x1800491d1  mov     eax, r8d
0x1800491d4  mov     rcx, [rbx+3D8D0h]
0x1800491db  bts     rcx, rax
0x1800491df  mov     [rbx+3D8D0h], rcx
0x1800491e6  lea     r14, [rbx+3D8A0h]
0x1800491ed  mov     rcx, [r14]
0x1800491f0  mov     ecx, [rcx+14h]
0x1800491f3  mov     edx, esi
0x1800491f5  shr     edx, cl
0x1800491f7  mov     eax, [r14+8]
0x1800491fb  cmp     edx, eax
0x1800491fd  jb      loc_18004A3F5
0x180049203  cmp     edx, [r14+0Ch]
0x180049207  jnb     loc_18004A405
0x18004920d  sub     edx, eax
0x18004920f  mov     rax, [r14+10h]
0x180049213  lea     r15, [rax+rdx*8]
0x180049217  cmp     qword ptr [r15], 0
0x18004921b  jnz     loc_18004930A
0x180049221  mov     rbp, [r14]
0x180049224  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18004922a  mov     r12d, eax
0x18004922d  mov     eax, eax
0x18004922f  xor     edx, edx
0x180049231  div     qword ptr [rbp+38h]
0x180049235  lea     r13, ds:0[rdx*8]
0x18004923d  mov     rcx, [rbp+30h]
0x180049241  mov     rdi, [rcx+r13]
0x180049245  test    rdi, rdi
0x180049248  jz      short loc_180049259
0x18004924a  cmp     [rdi], r12d
0x18004924d  jz      loc_1800492E0
0x180049253  mov     rdi, [rdi+48h]
0x180049257  jmp     short loc_180049245
0x180049259  mov     edx, 40h ; '@'
0x18004925e  mov     ecx, 80h
0x180049263  call    ??2@YAPEAX_KW4align_val_t@std@@@Z; operator new(unsigned __int64,std::align_val_t)
0x180049268  mov     rdi, rax
0x18004926b  mov     [rsp+0B8h+arg_0], rax
0x180049273  test    rax, rax
0x180049276  jz      loc_18004A453
0x18004927c  lea     rcx, [rbp+40h]
0x180049280  lea     rdx, [rsp+0B8h+var_88]
0x180049285  call    ??R?$_Func_class@VCOccReferences@inverted@@$$V@std@@QEBA?AVCOccReferences@inverted@@XZ; std::_Func_class<inverted::COccReferences,>::operator()(void)
0x18004928a  mov     r11, rax
0x18004928d  mov     [rdi], r12d
0x180049290  mov     rcx, [rax]
0x180049293  mov     [rdi+8], rcx
0x180049297  mov     ecx, [rax+8]
0x18004929a  mov     [rdi+10h], ecx
0x18004929d  lea     rdx, [rax+10h]
0x1800492a1  lea     rcx, [rdi+18h]
0x1800492a5  call    ??0?$vector@V?$vector@USOccStorage@inverted@@V?$allocator@USOccStorage@inverted@@@std@@@std@@V?$allocator@V?$vector@USOccStorage@inverted@@V?$allocator@USOccStorage@inverted@@@std@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::vector<std::vector<inverted::SOccStorage>>::vector<std::vector<inverted::SOccStorage>>(std::vector<std::vector<inverted::SOccStorage>> &&)
0x1800492aa  lea     rdx, [r11+28h]
0x1800492ae  lea     rcx, [rdi+30h]
0x1800492b2  call    ??0?$vector@V?$vector@USOccStorage@inverted@@V?$allocator@USOccStorage@inverted@@@std@@@std@@V?$allocator@V?$vector@USOccStorage@inverted@@V?$allocator@USOccStorage@inverted@@@std@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::vector<std::vector<inverted::SOccStorage>>::vector<std::vector<inverted::SOccStorage>>(std::vector<std::vector<inverted::SOccStorage>> &&)
0x1800492b7  mov     qword ptr [rdi+48h], 0
0x1800492bf  mov     rcx, r11
0x1800492c2  call    ??1CAllocatorState@?$sparse_bit_allocator@_K@@QEAA@XZ; sparse_bit_allocator<unsigned __int64>::CAllocatorState::~CAllocatorState(void)
0x1800492c7  nop
0x1800492c8  mov     rax, [rbp+30h]
0x1800492cc  mov     rax, [rax+r13]
0x1800492d0  mov     [rdi+48h], rax
0x1800492d4  mov     rcx, [rbp+30h]
0x1800492d8  lock cmpxchg [rcx+r13], rdi
0x1800492de  jnz     short loc_1800492C8
0x1800492e0  mov     rax, [rdi+20h]
0x1800492e4  cmp     [rdi+18h], rax
0x1800492e8  jz      loc_180049BC1
0x1800492ee  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800492f2  mov     r12, [rax]
0x1800492f5  mov     [rdi+20h], rax
0x1800492f9  mov     [r15], r12
0x1800492fc  mov     r8d, [rbp+4]; Size
0x180049300  xor     edx, edx; Val
0x180049302  mov     rcx, r12; void *
0x180049305  call    memset_0
0x18004930a  mov     rdx, rsi
0x18004930d  shr     rdx, 6
0x180049311  mov     rax, [r14]
0x180049314  mov     ecx, [rax+10h]
0x180049317  and     rdx, rcx
0x18004931a  mov     rax, [r15]
0x18004931d  lea     r8, [rax+rdx*8]
0x180049321  and     esi, 3Fh
0x180049324  mov     edx, 1
0x180049329  movzx   ecx, sil
0x18004932d  shl     rdx, cl
0x180049330  mov     rax, [r8]
0x180049333  test    rdx, rax
0x180049336  jnz     short loc_18004933E
0x180049338  or      rax, rdx
0x18004933b  mov     [r8], rax
0x18004933e  inc     dword ptr [rbx+3D8E8h]
0x180049344  jmp     loc_1800490A4
0x180049349  lea     r13, [rbx+5698h]
  ... truncated ...
```
