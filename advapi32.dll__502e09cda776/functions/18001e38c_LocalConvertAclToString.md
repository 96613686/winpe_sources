# LocalConvertAclToString

- ea: `0x18001e38c`
- end: `0x18001f4a6`
- name: `LocalConvertAclToString`
- size: `4378`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001cfb8`

## callees

- `0x18001c000`
- `0x18001d900`
- `0x18001e38c`
- `0x180020264`
- `0x180020a1c`
- `0x18005efa4`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001e6fc`
- `msvcrt!wcscpy_s` at `0x18001e7fd`
- `msvcrt!wcscpy_s` at `0x18001eb43`
- `msvcrt!wcscpy_s` at `0x18001f14b`
- `msvcrt!wcscpy_s` at `0x18001f190`
- `msvcrt!wcscpy_s` at `0x18001f1ce`
- `msvcrt!wcscpy_s` at `0x18001f20f`
- `msvcrt!wcscpy_s` at `0x18001f2d3`
- `msvcrt!wcscpy_s` at `0x18001f3ed`
- `msvcrt!wcscpy_s` at `0x18001f44a`
- `msvcrt!wcscpy_s` at `0x18001e6fc`
- `msvcrt!wcscpy_s` at `0x18001e7fd`
- `msvcrt!wcscpy_s` at `0x18001eb43`
- `msvcrt!wcscpy_s` at `0x18001f14b`
- `msvcrt!wcscpy_s` at `0x18001f190`
- `msvcrt!wcscpy_s` at `0x18001f1ce`
- `msvcrt!wcscpy_s` at `0x18001f20f`
- `msvcrt!wcscpy_s` at `0x18001f2d3`
- `msvcrt!wcscpy_s` at `0x18001f3ed`
- `msvcrt!wcscpy_s` at `0x18001f44a`
- `msvcrt!_ultow_s` at `0x18001e71d`
- `msvcrt!_ultow_s` at `0x18001e71d`
- `ntdll!RtlLengthSid` at `0x18001e8bb`
- `ntdll!RtlLengthSid` at `0x18001ea4f`
- `ntdll!RtlLengthSid` at `0x18001eae2`
- `ntdll!RtlLengthSid` at `0x18001eed9`
- `ntdll!RtlLengthSid` at `0x18001ef04`
- `ntdll!RtlLengthSid` at `0x18001ef7f`
- `ntdll!RtlLengthSid` at `0x18001f276`
- `ntdll!RtlLengthSid` at `0x18001f388`
- `ntdll!RtlLengthSid` at `0x18001e8bb`
- `ntdll!RtlLengthSid` at `0x18001ea4f`
- `ntdll!RtlLengthSid` at `0x18001eae2`
- `ntdll!RtlLengthSid` at `0x18001eed9`
- `ntdll!RtlLengthSid` at `0x18001ef04`
- `ntdll!RtlLengthSid` at `0x18001ef7f`
- `ntdll!RtlLengthSid` at `0x18001f276`
- `ntdll!RtlLengthSid` at `0x18001f388`
- `KERNELBASE!LocalAlloc` at `0x18001e413`
- `KERNELBASE!LocalAlloc` at `0x18001e437`
- `KERNELBASE!LocalAlloc` at `0x18001e45f`
- `KERNELBASE!LocalAlloc` at `0x18001e50c`
- `KERNELBASE!LocalAlloc` at `0x18001eaa5`
- `KERNELBASE!LocalAlloc` at `0x18001f2ae`
- `KERNELBASE!LocalAlloc` at `0x18001e413`
- `KERNELBASE!LocalAlloc` at `0x18001e437`
- `KERNELBASE!LocalAlloc` at `0x18001e45f`
- `KERNELBASE!LocalAlloc` at `0x18001e50c`
- `KERNELBASE!LocalAlloc` at `0x18001eaa5`
- `KERNELBASE!LocalAlloc` at `0x18001f2ae`
- `KERNEL32!LocalFree` at `0x18001e914`
- `KERNEL32!LocalFree` at `0x18001e935`
- `KERNEL32!LocalFree` at `0x18001e945`
- `KERNEL32!LocalFree` at `0x18001e955`
- `KERNEL32!LocalFree` at `0x18001e965`
- `KERNEL32!LocalFree` at `0x18001eba5`
- `KERNEL32!LocalFree` at `0x18001ef6b`
- `KERNEL32!LocalFree` at `0x18001f24a`
- `KERNEL32!LocalFree` at `0x18001f259`
- `KERNEL32!LocalFree` at `0x18001f486`
- `KERNEL32!LocalFree` at `0x18001e914`
- `KERNEL32!LocalFree` at `0x18001e935`
- `KERNEL32!LocalFree` at `0x18001e945`
- `KERNEL32!LocalFree` at `0x18001e955`
- `KERNEL32!LocalFree` at `0x18001e965`
- `KERNEL32!LocalFree` at `0x18001eba5`
- `KERNEL32!LocalFree` at `0x18001ef6b`
- `KERNEL32!LocalFree` at `0x18001f24a`
- `KERNEL32!LocalFree` at `0x18001f259`
- `KERNEL32!LocalFree` at `0x18001f486`
- `KERNEL32!GetLastError` at `0x18001f2f2`
- `KERNEL32!GetLastError` at `0x18001f2f2`
- `RPCRT4!RpcStringFreeW` at `0x18001f404`
- `RPCRT4!RpcStringFreeW` at `0x18001f461`
- `RPCRT4!RpcStringFreeW` at `0x18001f404`
- `RPCRT4!RpcStringFreeW` at `0x18001f461`

## string_xrefs

- `0x18001eabd`: `NO_ACCESS_CONTROL`

## pseudocode

```c
__int64 __fastcall LocalConvertAclToString(
        __int64 a1,
        char a2,
        char a3,
        wchar_t **a4,
        _DWORD *a5,
        _BYTE *a6,
        _BYTE *a7,
        __int64 a8,
        __int64 a9)
{
  unsigned int v9; // r12d
  int v12; // esi
  unsigned __int8 *v13; // r14
  DWORD LastError; // edi
  unsigned int v15; // ebx
  unsigned int v16; // edx
  unsigned int v17; // ecx
  HLOCAL *v18; // rsi
  wchar_t *v19; // r15
  unsigned __int8 *v20; // rdx
  unsigned __int64 v21; // r14
  unsigned int v22; // esi
  int v23; // r10d
  unsigned int v24; // ecx
  wchar_t *v25; // r15
  rsize_t v26; // r14
  unsigned __int8 *v27; // rsi
  unsigned int v28; // edi
  wchar_t *v29; // r15
  rsize_t v30; // r14
  unsigned int v31; // esi
  unsigned __int8 *v32; // rbx
  unsigned __int8 *v33; // r13
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // eax
  unsigned __int8 *v42; // r12
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  bool v48; // cc
  int v49; // ecx
  wchar_t *v50; // r15
  __int64 v51; // r12
  rsize_t v52; // r14
  wchar_t *v53; // rbx
  size_t v54; // r14
  __int64 v55; // rax
  int v56; // edx
  unsigned int v57; // ecx
  rsize_t v58; // r14
  wchar_t *v59; // rsi
  unsigned __int8 *v60; // rax
  wchar_t *v61; // rsi
  rsize_t v62; // r14
  HLOCAL *v63; // r13
  wchar_t *v64; // rsi
  const wchar_t *v65; // rbx
  rsize_t v66; // r14
  __int64 v67; // rax
  unsigned __int64 v68; // r14
  wchar_t *v69; // r15
  unsigned __int8 *v70; // rdx
  unsigned int v71; // r9d
  __int64 v72; // r8
  unsigned int v73; // r10d
  int v74; // esi
  unsigned int v75; // ebx
  _BYTE *v76; // rsi
  int v77; // eax
  __int64 result; // rax
  __int64 k; // rdx
  unsigned __int8 *v80; // r12
  unsigned int v81; // esi
  unsigned int v82; // eax
  int v83; // r9d
  unsigned int v84; // ecx
  ULONG v85; // eax
  DWORD StringForCondition; // eax
  wchar_t *v87; // rax
  ULONG v88; // eax
  int v89; // r9d
  rsize_t v90; // r14
  __int64 v91; // rax
  unsigned int v92; // edx
  unsigned int v93; // edx
  unsigned int v94; // edx
  unsigned int v95; // edx
  unsigned int v96; // edx
  unsigned int v97; // edx
  unsigned int v98; // eax
  unsigned __int8 *v99; // rsi
  int v100; // ecx
  _DWORD *v101; // r11
  int v102; // r9d
  int v103; // r8d
  unsigned int v104; // ecx
  int v105; // r11d
  unsigned int j; // r10d
  unsigned int v107; // ecx
  __int64 *v108; // rax
  wchar_t **v109; // rbx
  __int64 v110; // rax
  wchar_t **v111; // rax
  wchar_t *v112; // rcx
  __int64 v113; // rax
  unsigned int v114; // edx
  unsigned int v115; // edx
  unsigned int v116; // edx
  unsigned int v117; // edx
  unsigned int v118; // edx
  int v119; // r8d
  unsigned int v120; // edx
  __int64 v121; // r9
  int v122; // esi
  ULONG v123; // eax
  DWORD StringForRelativeAttribute; // eax
  __int64 v125; // rax
  ULONG v126; // eax
  int v127; // r9d
  __int16 *v128; // rcx
  __int64 v129; // rax
  int v130; // r15d
  wchar_t **v131; // rax
  wchar_t *v132; // rcx
  __int64 v133; // rax
  unsigned int v134; // edi
  int v135; // ecx
  unsigned int v136; // r10d
  __int64 v137; // r9
  unsigned int v138; // r11d
  __int64 i; // r8
  wchar_t **v140; // rax
  wchar_t *v141; // rcx
  __int64 v142; // rax
  wchar_t **v143; // rbx
  __int64 v144; // rax
  __int16 *v145; // rbx
  __int64 v146; // rax
  wchar_t **v147; // rbx
  __int64 v148; // rax
  wchar_t **v149; // rbx
  __int64 v150; // rax
  HLOCAL v151; // rcx
  int v152; // ebx
  ULONG v153; // eax
  int v154; // esi
  wchar_t *v155; // rax
  int v156; // edx
  __int64 v157; // r8
  int v158; // r9d
  int v159; // ebx
  ULONG v160; // eax
  int v161; // esi
  __int64 v162; // rbx
  __int64 v163; // rbx
  __int64 v164; // [rsp+30h] [rbp-91h]
  int v165; // [rsp+48h] [rbp-79h]
  int v166; // [rsp+4Ch] [rbp-75h]
  unsigned int Value; // [rsp+50h] [rbp-71h]
  char *hMem; // [rsp+58h] [rbp-69h]
  unsigned int v169; // [rsp+60h] [rbp-61h]
  HLOCAL v170; // [rsp+68h] [rbp-59h] BYREF
  PSID Sid; // [rsp+70h] [rbp-51h]
  unsigned __int8 *v172; // [rsp+78h] [rbp-49h]
  DWORD v173; // [rsp+80h] [rbp-41h]
  wchar_t *Source; // [rsp+88h] [rbp-39h] BYREF
  HLOCAL v175; // [rsp+90h] [rbp-31h]
  unsigned __int8 *v176; // [rsp+98h] [rbp-29h]
  unsigned __int8 *v177; // [rsp+A0h] [rbp-21h]
  HLOCAL v178; // [rsp+A8h] [rbp-19h]
  __int64 v179; // [rsp+B0h] [rbp-11h] BYREF
  __int64 v180; // [rsp+B8h] [rbp-9h]

  v9 = 0;
  Source = 0;
  v179 = 0;
  v170 = 0;
  if ( !a4 || !a5 )
    return 87;
  if ( !a2 )
  {
    *a4 = 0;
    *a5 = 0;
    return 0;
  }
  if ( !a1 )
  {
    *a4 = 0;
    *a5 = 36;
    v87 = (wchar_t *)LocalAlloc(0x40u, 0x24u);
    *a4 = v87;
    if ( !v87 )
    {
      result = 8;
      goto LABEL_126;
    }
    wcscpy(v87, L"NO_ACCESS_CONTROL");
    return 0;
  }
  if ( !*(_WORD *)(a1 + 4) )
  {
    *a4 = 0;
    result = 0;
LABEL_126:
    *a5 = 0;
    return result;
  }
  v12 = 2 - (a3 != 0);
  v166 = v12;
  hMem = (char *)LocalAlloc(0x40u, 8LL * *(unsigned __int16 *)(a1 + 4));
  if ( !hMem )
    return 8;
  v178 = LocalAlloc(0x40u, *(unsigned __int16 *)(a1 + 4));
  if ( !v178 )
  {
    v151 = hMem;
LABEL_235:
    LocalFree(v151);
    return 8;
  }
  v175 = LocalAlloc(0x40u, 4LL * *(unsigned __int16 *)(a1 + 4));
  if ( !v175 )
  {
    LocalFree(hMem);
    v151 = v178;
    goto LABEL_235;
  }
  Value = 0;
  v172 = (unsigned __int8 *)(a1 + 8);
  v13 = (unsigned __int8 *)(a1 + 8);
  Sid = 0;
  LastError = 0;
  v15 = 0;
  while ( 1 )
  {
    v165 = v15;
    if ( v9 >= *(unsigned __int16 *)(a1 + 4) )
      break;
    v16 = *v13;
    v15 += 2;
    v17 = 0;
    v165 = v15;
    while ( (v12 & dword_1800AE490[6 * v17]) != v12 || v16 != dword_1800AE48C[6 * v17] )
    {
      if ( ++v17 >= 0x11 )
        goto LABEL_15;
    }
    v131 = &(&off_1800AE480)[3 * v17];
    if ( !v131 )
    {
LABEL_15:
      LastError = 1336;
      break;
    }
    v132 = *v131;
    v133 = -1;
    do
      ++v133;
    while ( v132[v133] );
    v134 = 0;
    v130 = v15 + 2 * v133 + 2;
    do
    {
      if ( (v13[1] & (1 << v134)) != 0 )
      {
        v135 = v166;
        v136 = 0;
        while ( 1 )
        {
          v137 = 4LL * v136;
          if ( (v135 & qword_1800AE0C8[v137 + 1]) == v135 )
          {
            v138 = HIDWORD(qword_1800AE0C8[v137 + 1]);
            if ( v138 )
            {
              for ( i = 0; ; i = (unsigned int)(i + 1) )
              {
                if ( (unsigned int)i >= v138 )
                {
                  v135 = v166;
                  goto LABEL_211;
                }
                if ( *(_BYTE *)(i + qword_1800AE0C8[v137 + 2]) == (_BYTE)v16 )
                  break;
              }
              v135 = v166;
            }
            if ( 1 << v134 == HIDWORD(qword_1800AE0C8[v137]) )
              break;
          }
LABEL_211:
          if ( ++v136 >= 9 )
            goto LABEL_205;
        }
        v128 = &_ImageBase[16 * v136 + 356448];
        if ( v128 )
        {
          v129 = -1;
          do
            ++v129;
          while ( *(_WORD *)(*(_QWORD *)v128 + 2 * v129) );
          v130 += 2 * v129;
        }
      }
LABEL_205:
      ++v134;
    }
    while ( v134 < 8 );
    v15 = v130 + 2;
    v165 = v130 + 2;
    if ( v16 <= 9 )
    {
      if ( v16 == 9 )
        goto LABEL_138;
      if ( !*v13 )
        goto LABEL_138;
      v114 = v16 - 1;
      if ( !v114 )
        goto LABEL_138;
      v115 = v114 - 1;
      if ( !v115 )
        goto LABEL_138;
      v116 = v115 - 1;
      if ( !v116 )
        goto LABEL_138;
      v117 = v116 - 2;
      if ( v117 )
      {
        v118 = v117 - 1;
        if ( v118 )
        {
          if ( v118 - 1 > 1 )
            goto LABEL_15;
        }
      }
    }
    else
    {
      v92 = v16 - 10;
      if ( !v92 )
        goto LABEL_138;
      v93 = v92 - 1;
      if ( v93 )
      {
        v94 = v93 - 2;
        if ( v94 )
        {
          v95 = v94 - 4;
          if ( v95 )
          {
            v96 = v95 - 1;
            if ( v96 )
            {
              v97 = v96 - 1;
              if ( v97 )
              {
                if ( v97 - 1 > 1 )
                  goto LABEL_15;
              }
            }
          }
        }
LABEL_138:
        v98 = *((_DWORD *)v13 + 1);
        v99 = v13 + 8;
        Sid = v13 + 8;
        Value = v98;
        goto LABEL_139;
      }
    }
    v119 = *((_DWORD *)v13 + 2) & 2;
    v120 = *((_DWORD *)v13 + 2) & 1;
    v121 = 16LL * v120;
    Value = *((_DWORD *)v13 + 1);
    v99 = &v13[v121 + (v119 != 0 ? 28LL : 12LL)];
    Sid = v99;
    if ( v120 && v13 != (unsigned __int8 *)-12LL )
    {
      v15 = v130 + 74;
      v165 = v130 + 74;
    }
    if ( v119 && &v13[v121 + 12] )
    {
      v15 += 72;
      v165 = v15;
    }
LABEL_139:
    if ( v170 )
      LocalFree(v170);
    v170 = 0;
    LastError = 0;
    if ( *v13 <= 0x12u )
    {
      v100 = 271872;
      if ( _bittest(&v100, *v13) )
        goto LABEL_187;
    }
    if ( *v13 != 11 )
    {
      if ( *v13 != 21 )
        goto LABEL_145;
LABEL_187:
      v122 = *((unsigned __int16 *)v13 + 1) - RtlLengthSid(v99) - 8;
      goto LABEL_188;
    }
    v152 = *((_DWORD *)v13 + 2);
    v153 = RtlLengthSid(v99);
    v154 = *((unsigned __int16 *)v13 + 1) - 16 * (v152 & 1) - 8 * (v152 & 2);
    v15 = v165;
    v122 = v154 - v153 - 12;
LABEL_188:
    if ( v122 )
    {
      if ( *v13 == 18 )
      {
        v123 = RtlLengthSid(Sid);
        LOBYTE(v164) = a9;
        StringForRelativeAttribute = LocalGetStringForRelativeAttribute(
                                       (unsigned int)Sid + v123,
                                       v122,
                                       (_DWORD)a6,
                                       (_DWORD)a7,
                                       a8,
                                       v164,
                                       (__int64)&v170);
      }
      else
      {
        v126 = RtlLengthSid(Sid);
        StringForRelativeAttribute = LocalpGetStringForCondition(
                                       (unsigned int)Sid + v126,
                                       v122,
                                       (unsigned int)&v170,
                                       v127,
                                       (__int64)a6,
                                       (__int64)a7,
                                       a8,
                                       a9);
      }
      LastError = StringForRelativeAttribute;
      if ( StringForRelativeAttribute )
        break;
      v125 = -1;
      do
        ++v125;
      while ( *((_WORD *)v170 + v125) );
      v15 += 2 * v125 + 2;
    }
LABEL_145:
    v101 = v175;
    v102 = v166;
    v103 = v166;
    *((_DWORD *)v175 + v9) = 0;
    if ( *v13 == 17 )
      v103 = 4;
    v104 = 0;
    while ( (v103 & dword_1800AE1F0[6 * v104]) != v103 || Value != dword_1800AE1EC[6 * v104] )
    {
      if ( ++v104 >= 0x1C )
        goto LABEL_151;
    }
    v140 = &(&off_1800AE1E0)[3 * v104];
    if ( v140 )
    {
      v101[v9] = 1;
      v141 = *v140;
      v142 = -1;
      do
        ++v142;
      while ( v141[v142] );
      v105 = 2 * v142;
      goto LABEL_160;
    }
LABEL_151:
    v105 = 0;
    for ( j = 0; j < 0x20; ++j )
    {
      if ( (Value & (1 << j)) != 0 )
      {
        v107 = 0;
        if ( *v13 == 17 )
          v102 = 4;
        while ( (v102 & dword_1800AE1F0[6 * v107]) != v102 || (Value & (1 << j)) != dword_1800AE1EC[6 * v107] )
        {
          if ( ++v107 >= 0x1C )
            goto LABEL_159;
        }
        v111 = &(&off_1800AE1E0)[3 * v107];
        if ( !v111 )
        {
LABEL_159:
          v105 = 20;
          *((_DWORD *)v175 + v9) = 2;
          break;
        }
        v112 = *v111;
        v113 = -1;
        do
          ++v113;
        while ( v112[v113] );
        v102 = v166;
        v105 += 2 * v113;
      }
    }
LABEL_160:
    LOBYTE(v164) = a9;
    v165 = v105 + 6 + v15;
    v108 = LookupSidInTable(0, Sid, a6, a7, a8, v164, (PSID *)&v179);
    v109 = (wchar_t **)&hMem[8 * v9];
    if ( v108 )
    {
      *v109 = (wchar_t *)v108 + 1;
    }
    else
    {
      if ( v179 )
      {
        v155 = (wchar_t *)LocalAlloc(0x40u, 6u);
        *v109 = v155;
        if ( !v155 )
        {
          v15 = v165;
          LastError = 8;
          break;
        }
        wcscpy_s(v155, 3u, L"SA");
      }
      else if ( !ConvertSidToStringSidW(Sid, (LPWSTR *)&hMem[8 * v9]) )
      {
        v15 = v165;
        LastError = GetLastError();
        break;
      }
      *((_BYTE *)v178 + v9) = 1;
    }
    v110 = -1;
    do
      ++v110;
    while ( (*v109)[v110] );
    ++v9;
    v12 = v166;
    v15 = v165 + 2 * v110 + 4;
    v13 += *((unsigned __int16 *)v13 + 1);
  }
  if ( v15 )
  {
    if ( !LastError )
    {
      if ( (v15 & 1) != 0 )
        v165 = ++v15;
      v18 = (HLOCAL *)a4;
      v19 = (wchar_t *)LocalAlloc(0x40u, v15);
      *a4 = v19;
      if ( v19 )
      {
        v20 = v172;
        v21 = (unsigned __int64)v15 >> 1;
        v22 = 0;
        while ( 1 )
        {
          v169 = v22;
          if ( v22 >= *(unsigned __int16 *)(a1 + 4) )
            goto LABEL_103;
          if ( !v21 )
            goto LABEL_258;
          v23 = v166;
          *v19 = 40;
          v24 = 0;
          v25 = v19 + 1;
          v26 = v21 - 1;
          while ( (v166 & dword_1800AE490[6 * v24]) != v166 || *v20 != dword_1800AE48C[6 * v24] )
          {
            if ( ++v24 >= 0x11 )
              goto LABEL_28;
          }
          v143 = &(&off_1800AE480)[3 * v24];
          if ( v143 )
          {
            wcscpy_s(v25, v26, *v143);
            v144 = *((unsigned int *)v143 + 2);
            v23 = v166;
            v26 -= v144;
            v25 += v144;
          }
LABEL_28:
          if ( !v26 )
            goto LABEL_258;
          v27 = v172;
          v28 = 0;
          *v25 = 59;
          v29 = v25 + 1;
          v30 = v26 - 1;
          do
          {
            if ( ((unsigned __int8)(1 << v28) & v27[1]) == 0 )
              goto LABEL_31;
            v71 = 0;
            while ( 1 )
            {
              v72 = 4LL * v71;
              if ( (v23 & qword_1800AE0C8[v72 + 1]) == v23 )
                break;
LABEL_84:
              if ( ++v71 >= 9 )
                goto LABEL_31;
            }
            v73 = HIDWORD(qword_1800AE0C8[v72 + 1]);
            if ( v73 )
            {
              for ( k = 0; (unsigned int)k < v73; k = (unsigned int)(k + 1) )
              {
                if ( *(_BYTE *)(k + qword_1800AE0C8[v72 + 2]) == *v27 )
                  goto LABEL_82;
              }
LABEL_83:
              v23 = v166;
              goto LABEL_84;
            }
LABEL_82:
            if ( 1 << v28 != HIDWORD(qword_1800AE0C8[v72]) )
              goto LABEL_83;
            v145 = &_ImageBase[16 * v71 + 356448];
            if ( v145 )
            {
              wcscpy_s(v29, v30, *(const wchar_t **)v145);
              v146 = *((unsigned int *)v145 + 2);
              v30 -= v146;
              v29 += v146;
            }
LABEL_31:
            v23 = v166;
            ++v28;
          }
          while ( v28 < 8 );
          v31 = v169;
          if ( !v30 )
            goto LABEL_258;
          v32 = v172;
          v33 = 0;
          *v29 = 59;
          v176 = 0;
          v177 = 0;
          v34 = *v32;
          if ( v34 <= 9 )
          {
            if ( v34 == 9 || !*v32 || (v43 = v34 - 1) == 0 || (v44 = v43 - 1) == 0 || (v45 = v44 - 1) == 0 )
            {
LABEL_41:
              v41 = *((_DWORD *)v32 + 1);
              v42 = v32 + 8;
              Sid = v32 + 8;
              Value = v41;
              goto LABEL_51;
            }
            v46 = v45 - 2;
            if ( v46 )
            {
              v47 = v46 - 1;
              if ( v47 )
              {
                if ( v47 - 1 >= 2 )
                  goto LABEL_50;
              }
            }
LABEL_243:
            v156 = *((_DWORD *)v32 + 2) & 2;
            v157 = 16LL * (*((_DWORD *)v32 + 2) & 1);
            v158 = *((_DWORD *)v32 + 2) & 1;
            Value = *((_DWORD *)v32 + 1);
            v42 = &v32[(v156 != 0 ? 0x10 : 0) + 12 + v157];
            Sid = v42;
            if ( v156 )
              v177 = &v32[v157 + 12];
            else
              v177 = 0;
            if ( v158 )
            {
              v33 = v32 + 12;
              v176 = v32 + 12;
            }
            else
            {
              v176 = 0;
            }
            goto LABEL_51;
          }
          v35 = v34 - 10;
          if ( !v35 )
            goto LABEL_41;
          v36 = v35 - 1;
          if ( !v36 )
            goto LABEL_243;
          v37 = v36 - 2;
          if ( !v37 )
            goto LABEL_41;
          v38 = v37 - 4;
          if ( !v38 )
            goto LABEL_41;
          v39 = v38 - 1;
          if ( !v39 )
            goto LABEL_41;
          v40 = v39 - 1;
          if ( !v40 || v40 - 1 <= 1 )
            goto LABEL_41;
LABEL_50:
          v42 = (unsigned __int8 *)Sid;
LABEL_51:
          if ( v170 )
            LocalFree(v170);
          v170 = 0;
          LastError = 0;
          v48 = *v32 <= 0x12u;
          v173 = 0;
          if ( v48 )
          {
            v49 = 271872;
            if ( _bittest(&v49, *v32) )
              goto LABEL_86;
          }
          if ( *v32 == 11 )
          {
            v159 = *((_DWORD *)v32 + 2);
            v160 = RtlLengthSid(v42);
            v161 = *((unsigned __int16 *)v172 + 1) - 16 * (v159 & 1) - 8 * (v159 & 2);
            v32 = v172;
            v74 = v161 - v160 - 12;
          }
          else
          {
            if ( *v32 != 21 )
              goto LABEL_57;
LABEL_86:
            v74 = *((unsigned __int16 *)v32 + 1) - RtlLengthSid(v42) - 8;
          }
          if ( v74 )
          {
            if ( *v32 == 18 )
            {
              v85 = RtlLengthSid(v42);
              LOBYTE(v164) = a9;
              StringForCondition = LocalGetStringForRelativeAttribute(
                                     (unsigned int)v42 + v85,
                                     v74,
                                     (_DWORD)a6,
                                     (_DWORD)a7,
                                     a8,
                                     v164,
                                     (__int64)&v170);
            }
            else
            {
              v88 = RtlLengthSid(v42);
              StringForCondition = LocalpGetStringForCondition(
                                     (unsigned int)v42 + v88,
                                     v74,
                                     (unsigned int)&v170,
                                     v89,
                                     (__int64)a6,
                                     (__int64)a7,
                                     a8,
                                     a9);
            }
            v173 = StringForCondition;
            LastError = StringForCondition;
          }
          v31 = v169;
LABEL_57:
          if ( LastError )
            goto LABEL_103;
          v50 = v29 + 1;
          v51 = v31;
          v52 = v30 - 1;
          v180 = v31;
          if ( *((_DWORD *)v175 + v31) == 2 )
          {
            wcscpy_s(v50, v52, L"0x");
            v53 = v50 + 2;
            v54 = v52 - 2;
            _ultow_s(Value, v50 + 2, v54, 16);
            v55 = -1;
            do
              ++v55;
            while ( v53[v55] );
            v50 = &v53[v55];
            v52 = v54 - v55;
          }
          else if ( *((_DWORD *)v175 + v31) == 1 )
          {
            v56 = v166;
            if ( *v32 == 17 )
              v56 = 4;
            v57 = 0;
            while ( (v56 & dword_1800AE1F0[6 * v57]) != v56 || Value != dword_1800AE1EC[6 * v57] )
            {
              if ( ++v57 >= 0x1C )
                goto LABEL_69;
            }
            v147 = &(&off_1800AE1E0)[3 * v57];
            if ( v147 )
            {
              wcscpy_s(v50, v52, *v147);
              v148 = *((unsigned int *)v147 + 2);
              v52 -= v148;
              v50 += v148;
            }
          }
          else
          {
            v80 = v172;
            v81 = 0;
            v82 = Value;
            do
            {
              if ( (v82 & (1 << v81)) != 0 )
              {
                v83 = v166;
                v84 = 0;
                if ( *v80 == 17 )
                  v83 = 4;
                while ( (v83 & dword_1800AE1F0[6 * v84]) != v83 || (v82 & (1 << v81)) != dword_1800AE1EC[6 * v84] )
                {
                  if ( ++v84 >= 0x1C )
                    goto LABEL_114;
                }
                v149 = &(&off_1800AE1E0)[3 * v84];
                if ( v149 )
                {
                  wcscpy_s(v50, v52, *v149);
                  v150 = *((unsigned int *)v149 + 2);
                  v52 -= v150;
                  v50 += v150;
                }
LABEL_114:
                v82 = Value;
              }
              ++v81;
            }
            while ( v81 < 0x20 );
            LastError = v173;
            v51 = v180;
            v33 = v176;
          }
LABEL_69:
          if ( !v52 )
            goto LABEL_258;
          v58 = v52 - 1;
          v59 = v50 + 1;
          *v50 = 59;
          if ( !v33 )
            goto LABEL_71;
          if ( !(unsigned int)SddlpUuidToString(v33, &Source) )
            goto LABEL_103;
          v162 = -1;
          do
            ++v162;
          while ( Source[v162] );
          wcscpy_s(v59, v58, Source);
          v58 -= v162;
          v59 += v162;
          RpcStringFreeW(&Source);
LABEL_71:
          if ( !v58 )
            goto LABEL_258;
          v60 = v177;
          *v59 = 59;
          v61 = v59 + 1;
          v62 = v58 - 1;
          if ( !v60 )
            goto LABEL_73;
          if ( !(unsigned int)SddlpUuidToString(v60, &Source) )
            goto LABEL_103;
          v163 = -1;
          do
            ++v163;
          while ( Source[v163] );
          wcscpy_s(v61, v62, Source);
          v62 -= v163;
          v61 += v163;
          RpcStringFreeW(&Source);
LABEL_73:
          v63 = (HLOCAL *)hMem;
          if ( !v62 )
            goto LABEL_90;
          *v61 = 59;
          v64 = v61 + 1;
          v65 = *(const wchar_t **)&hMem[8 * v51];
          v66 = v62 - 1;
          wcscpy_s(v64, v66, v65);
          v67 = -1;
          do
            ++v67;
          while ( v65[v67] );
          v68 = v66 - v67;
          v69 = &v64[v67];
          if ( v170 )
          {
            if ( v68 )
            {
              *v69 = 59;
              v90 = v68 - 1;
              wcscpy_s(v69 + 1, v90, (const wchar_t *)v170);
              v91 = -1;
              do
                ++v91;
              while ( *((_WORD *)v170 + v91) );
              v69 += v91 + 1;
              v68 = v90 - v91;
              goto LABEL_77;
            }
LABEL_90:
            v18 = (HLOCAL *)a4;
            LastError = 1336;
            goto LABEL_91;
          }
LABEL_77:
          if ( v68 <= 1 )
            goto LABEL_90;
          v70 = v172;
          v21 = v68 - 1;
          *v69 = 41;
          v22 = v169 + 1;
          v19 = v69 + 1;
          *v19 = 0;
          v20 = &v70[*((unsigned __int16 *)v70 + 1)];
          v172 = v20;
        }
      }
      LastError = 8;
      goto LABEL_104;
    }
  }
  else
  {
LABEL_258:
    LastError = 1336;
  }
LABEL_103:
  v18 = (HLOCAL *)a4;
LABEL_104:
  v63 = (HLOCAL *)hMem;
LABEL_91:
  v75 = 0;
  if ( *(_WORD *)(a1 + 4) )
  {
    v76 = v178;
    do
    {
      if ( v76[v75] )
        LocalFree(v63[v75]);
      ++v75;
    }
    while ( v75 < *(unsigned __int16 *)(a1 + 4) );
    v18 = (HLOCAL *)a4;
  }
  LocalFree(v63);
  LocalFree(v178);
  LocalFree(v175);
  LocalFree(v170);
  if ( LastError )
  {
    LocalFree(*v18);
    v77 = 0;
    *v18 = 0;
  }
  else
  {
    v77 = v165;
  }
  *a5 = v77;
  return LastError;
}

```

## disassembly

```asm
0x18001e38c  mov     rax, rsp
0x18001e38f  mov     [rax+10h], rbx
0x18001e393  mov     [rax+20h], r9
0x18001e397  mov     [rax+8], rcx
0x18001e39b  push    rbp
0x18001e39c  push    rsi
0x18001e39d  push    rdi
0x18001e39e  push    r12
0x18001e3a0  push    r13
0x18001e3a2  push    r14
0x18001e3a4  push    r15
0x18001e3a6  lea     rbp, [rax-3Fh]
0x18001e3aa  sub     rsp, 0C0h
0x18001e3b1  xor     r12d, r12d
0x18001e3b4  mov     rsi, r9
0x18001e3b7  mov     [rbp+37h+Source], r12
0x18001e3bb  mov     r14, rcx
0x18001e3be  mov     [rbp+37h+var_48], r12
0x18001e3c2  mov     [rbp+37h+var_90], r12
0x18001e3c6  test    r9, r9
0x18001e3c9  jz      loc_18001F49C
0x18001e3cf  mov     rbx, [rbp+37h+arg_20]
0x18001e3d3  test    rbx, rbx
0x18001e3d6  jz      loc_18001F49C
0x18001e3dc  test    dl, dl
0x18001e3de  jz      loc_18001F22D
0x18001e3e4  test    rcx, rcx
0x18001e3e7  jz      loc_18001EA98
0x18001e3ed  cmp     [rcx+4], r12w
0x18001e3f2  jz      loc_18001EB70
0x18001e3f8  movzx   edx, word ptr [rcx+4]
0x18001e3fc  lea     r15d, [r12+40h]
0x18001e401  neg     r8b
0x18001e404  mov     ecx, r15d; uFlags
0x18001e407  sbb     esi, esi
0x18001e409  shl     rdx, 3; uBytes
0x18001e40d  add     esi, 2
0x18001e410  mov     [rbp+37h+var_AC], esi
0x18001e413  call    cs:__imp_LocalAlloc
0x18001e41a  nop     dword ptr [rax+rax+00h]
0x18001e41f  mov     [rbp+37h+hMem], rax
0x18001e423  mov     rbx, rax
0x18001e426  test    rax, rax
0x18001e429  jz      loc_18001F265
0x18001e42f  movzx   edx, word ptr [r14+4]; uBytes
0x18001e434  mov     ecx, r15d; uFlags
0x18001e437  call    cs:__imp_LocalAlloc
0x18001e43e  nop     dword ptr [rax+rax+00h]
0x18001e443  mov     [rbp+37h+var_50], rax
0x18001e447  mov     rdi, rax
0x18001e44a  test    rax, rax
0x18001e44d  jz      loc_18001F242
0x18001e453  movzx   edx, word ptr [r14+4]
0x18001e458  mov     ecx, r15d; uFlags
0x18001e45b  shl     rdx, 2; uBytes
0x18001e45f  call    cs:__imp_LocalAlloc
0x18001e466  nop     dword ptr [rax+rax+00h]
0x18001e46b  xor     r11d, r11d
0x18001e46e  mov     [rbp+37h+var_68], rax
0x18001e472  test    rax, rax
0x18001e475  jz      loc_18001F247
0x18001e47b  lea     rax, [r14+8]
0x18001e47f  mov     [rbp+37h+Value], r11d
0x18001e483  mov     [rbp+37h+var_80], rax
0x18001e487  lea     r13d, [r12+8]
0x18001e48c  mov     r14, rax
0x18001e48f  mov     [rbp+37h+Sid], r11
0x18001e493  mov     edi, r11d
0x18001e496  mov     ebx, r11d
0x18001e499  mov     rax, [rbp+37h+arg_0]
0x18001e49d  mov     [rbp+37h+var_B0], ebx
0x18001e4a0  movzx   eax, word ptr [rax+4]
0x18001e4a4  cmp     r12d, eax
0x18001e4a7  jnb     short loc_18001E4EB
0x18001e4a9  movzx   edx, byte ptr [r14]
0x18001e4ad  lea     r9, __ImageBase
0x18001e4b4  add     ebx, 2
0x18001e4b7  mov     ecx, r11d
0x18001e4ba  mov     [rbp+37h+var_B0], ebx
0x18001e4bd  mov     eax, ecx
0x18001e4bf  lea     r8, [rax+rax*2]
0x18001e4c3  mov     eax, rva dword_1800AE490[r9+r8*8]
0x18001e4cb  and     eax, esi
0x18001e4cd  cmp     eax, esi
0x18001e4cf  jnz     short loc_18001E4DF
0x18001e4d1  cmp     edx, rva dword_1800AE48C[r9+r8*8]
0x18001e4d9  jz      loc_18001EFF3
0x18001e4df  inc     ecx
0x18001e4e1  cmp     ecx, 11h
0x18001e4e4  jb      short loc_18001E4BD
0x18001e4e6  mov     edi, 538h
0x18001e4eb  test    ebx, ebx
0x18001e4ed  jz      loc_18001F479
0x18001e4f3  test    edi, edi
0x18001e4f5  jnz     loc_18001E9B9
0x18001e4fb  test    bl, 1
0x18001e4fe  jnz     loc_18001F30B
0x18001e504  mov     edx, ebx; uBytes
0x18001e506  mov     ecx, r15d; uFlags
0x18001e509  mov     r14d, ebx
0x18001e50c  call    cs:__imp_LocalAlloc
0x18001e513  nop     dword ptr [rax+rax+00h]
0x18001e518  mov     rsi, [rbp+37h+arg_18]
0x18001e51c  xor     r11d, r11d
0x18001e51f  mov     r15, rax
0x18001e522  mov     [rsi], rax
0x18001e525  test    rax, rax
0x18001e528  jz      loc_18001F315
0x18001e52e  mov     rdx, [rbp+37h+var_80]
0x18001e532  lea     r12d, [r11+3Bh]
0x18001e536  shr     r14, 1
0x18001e539  mov     esi, r11d
0x18001e53c  mov     rax, [rbp+37h+arg_0]
0x18001e540  mov     [rbp+37h+var_98], esi
0x18001e543  movzx   eax, word ptr [rax+4]
0x18001e547  cmp     esi, eax
0x18001e549  jnb     loc_18001E9B9
0x18001e54f  test    r14, r14
0x18001e552  jz      loc_18001F479
0x18001e558  mov     r10d, [rbp+37h+var_AC]
0x18001e55c  lea     r9, __ImageBase
0x18001e563  mov     word ptr [r15], 28h ; '('
0x18001e569  mov     ecx, r11d
0x18001e56c  movzx   r8d, byte ptr [rdx]
0x18001e570  add     r15, 2
0x18001e574  dec     r14
0x18001e577  mov     eax, ecx
0x18001e579  lea     rdx, [rax+rax*2]
0x18001e57d  mov     eax, rva dword_1800AE490[r9+rdx*8]
0x18001e585  and     eax, r10d
0x18001e588  cmp     eax, r10d
0x18001e58b  jnz     short loc_18001E59B
0x18001e58d  cmp     r8d, rva dword_1800AE48C[r9+rdx*8]
0x18001e595  jz      loc_18001F121
0x18001e59b  inc     ecx
0x18001e59d  cmp     ecx, 11h
0x18001e5a0  jb      short loc_18001E577
0x18001e5a2  lea     rdx, __ImageBase
0x18001e5a9  test    r14, r14
0x18001e5ac  jz      loc_18001F479
0x18001e5b2  mov     rsi, [rbp+37h+var_80]
0x18001e5b6  mov     edi, r11d
0x18001e5b9  mov     [r15], r12w
0x18001e5bd  add     r15, 2
0x18001e5c1  dec     r14
0x18001e5c4  mov     ecx, edi
0x18001e5c6  mov     r11d, 1
0x18001e5cc  shl     r11d, cl
0x18001e5cf  test    [rsi+1], r11b
0x18001e5d3  jnz     loc_18001E86A
0x18001e5d9  xor     r11d, r11d
0x18001e5dc  mov     r10d, [rbp+37h+var_AC]
0x18001e5e0  lea     rdx, __ImageBase
0x18001e5e7  inc     edi
0x18001e5e9  cmp     edi, r13d
0x18001e5ec  jb      short loc_18001E5C4
0x18001e5ee  mov     esi, [rbp+37h+var_98]
0x18001e5f1  test    r14, r14
0x18001e5f4  jz      loc_18001F479
0x18001e5fa  mov     rbx, [rbp+37h+var_80]
0x18001e5fe  mov     r13, r11
0x18001e601  mov     [r15], r12w
0x18001e605  mov     [rbp+37h+var_60], r11
0x18001e609  mov     [rbp+37h+var_58], r11
0x18001e60d  movzx   ecx, byte ptr [rbx]
0x18001e610  cmp     ecx, 9
0x18001e613  jbe     short loc_18001E651
0x18001e615  sub     ecx, 0Ah
0x18001e618  jz      short loc_18001E641
0x18001e61a  sub     ecx, 1
0x18001e61d  jz      loc_18001F31D
0x18001e623  sub     ecx, 2
0x18001e626  jz      short loc_18001E641
0x18001e628  sub     ecx, 4
0x18001e62b  jz      short loc_18001E641
0x18001e62d  sub     ecx, 1
0x18001e630  jz      short loc_18001E641
0x18001e632  sub     ecx, 1
0x18001e635  jz      short loc_18001E641
0x18001e637  sub     ecx, 1
0x18001e63a  jz      short loc_18001E641
0x18001e63c  cmp     ecx, 1
0x18001e63f  jnz     short loc_18001E68A
0x18001e641  mov     eax, [rbx+4]
0x18001e644  lea     r12, [rbx+8]
0x18001e648  mov     [rbp+37h+Sid], r12
0x18001e64c  mov     [rbp+37h+Value], eax
0x18001e64f  jmp     short loc_18001E68E
0x18001e651  jz      short loc_18001E641
0x18001e653  test    ecx, ecx
0x18001e655  jz      short loc_18001E641
0x18001e657  sub     ecx, 1
0x18001e65a  jz      short loc_18001E641
0x18001e65c  sub     ecx, 1
0x18001e65f  jz      short loc_18001E641
0x18001e661  sub     ecx, 1
0x18001e664  jz      short loc_18001E641
0x18001e666  sub     ecx, 2
0x18001e669  jz      loc_18001F31D
0x18001e66f  sub     ecx, 1
0x18001e672  jz      loc_18001F31D
0x18001e678  sub     ecx, 1
0x18001e67b  jz      loc_18001F31D
0x18001e681  cmp     ecx, 1
0x18001e684  jz      loc_18001F31D
0x18001e68a  mov     r12, [rbp+37h+Sid]
0x18001e68e  mov     rcx, [rbp+37h+var_90]; hMem
0x18001e692  test    rcx, rcx
0x18001e695  jnz     loc_18001EBA5
0x18001e69b  mov     [rbp+37h+var_90], r11
0x18001e69f  mov     edi, r11d
0x18001e6a2  cmp     byte ptr [rbx], 12h
0x18001e6a5  mov     [rbp+37h+var_78], r11d
0x18001e6a9  ja      short loc_18001E6BC
0x18001e6ab  movzx   eax, byte ptr [rbx]
0x18001e6ae  mov     ecx, 42600h
0x18001e6b3  bt      ecx, eax
0x18001e6b6  jb      loc_18001E8B8
0x18001e6bc  cmp     byte ptr [rbx], 0Bh
0x18001e6bf  jz      loc_18001F382
0x18001e6c5  cmp     byte ptr [rbx], 15h
0x18001e6c8  jz      loc_18001E8B8
0x18001e6ce  test    edi, edi
0x18001e6d0  jnz     loc_18001E9B9
0x18001e6d6  mov     rax, [rbp+37h+var_68]
0x18001e6da  add     r15, 2
0x18001e6de  mov     r12d, esi
0x18001e6e1  dec     r14
0x18001e6e4  mov     [rbp+37h+var_40], r12
0x18001e6e8  cmp     dword ptr [rax+r12*4], 2
0x18001e6ed  jnz     short loc_18001E743
0x18001e6ef  lea     r8, a0x; "0x"
0x18001e6f6  mov     rdx, r14; SizeInWords
0x18001e6f9  mov     rcx, r15; Destination
0x18001e6fc  call    cs:__imp_wcscpy_s
0x18001e703  nop     dword ptr [rax+rax+00h]
0x18001e708  mov     ecx, [rbp+37h+Value]; Value
0x18001e70b  lea     rbx, [r15+4]
0x18001e70f  add     r14, 0FFFFFFFFFFFFFFFEh
0x18001e713  lea     r9d, [rdi+10h]; Radix
0x18001e717  mov     r8, r14; BufferCount
0x18001e71a  mov     rdx, rbx; Buffer
0x18001e71d  call    cs:__imp__ultow_s
0x18001e724  nop     dword ptr [rax+rax+00h]
0x18001e729  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e72d  xor     r11d, r11d
0x18001e730  inc     rax
0x18001e733  cmp     [rbx+rax*2], r11w
0x18001e738  jnz     short loc_18001E730
0x18001e73a  lea     r15, [rbx+rax*2]
0x18001e73e  sub     r14, rax
0x18001e741  jmp     short loc_18001E792
0x18001e743  cmp     dword ptr [rax+r12*4], 1
0x18001e748  jnz     loc_18001E9C6
0x18001e74e  cmp     byte ptr [rbx], 11h
0x18001e751  lea     r10, __ImageBase
0x18001e758  mov     edx, [rbp+37h+var_AC]
0x18001e75b  mov     eax, 4
0x18001e760  cmovz   edx, eax
0x18001e763  mov     ecx, r11d
0x18001e766  mov     eax, ecx
0x18001e768  lea     r8, [rax+rax*2]
0x18001e76c  mov     eax, rva dword_1800AE1F0[r10+r8*8]
0x18001e774  and     eax, edx
0x18001e776  cmp     eax, edx
0x18001e778  jnz     short loc_18001E78B
0x18001e77a  mov     eax, [rbp+37h+Value]
0x18001e77d  cmp     eax, rva dword_1800AE1EC[r10+r8*8]
0x18001e785  jz      loc_18001F1AB
0x18001e78b  inc     ecx
0x18001e78d  cmp     ecx, 1Ch
0x18001e790  jb      short loc_18001E766
0x18001e792  test    r14, r14
0x18001e795  jz      loc_18001F479
0x18001e79b  dec     r14
0x18001e79e  lea     rsi, [r15+2]
0x18001e7a2  mov     ecx, 3Bh ; ';'
0x18001e7a7  mov     [r15], cx
0x18001e7ab  test    r13, r13
0x18001e7ae  jnz     loc_18001F3BB
0x18001e7b4  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001e7b8  test    r14, r14
0x18001e7bb  jz      loc_18001F479
0x18001e7c1  mov     rax, [rbp+37h+var_58]
0x18001e7c5  mov     [rsi], cx
0x18001e7c8  add     rsi, 2
0x18001e7cc  dec     r14
0x18001e7cf  test    rax, rax
0x18001e7d2  jnz     loc_18001F41C
0x18001e7d8  mov     r13, [rbp+37h+hMem]
0x18001e7dc  test    r14, r14
0x18001e7df  jz      loc_18001E8EC
0x18001e7e5  mov     [rsi], cx
0x18001e7e8  add     rsi, 2
0x18001e7ec  mov     rbx, [r13+r12*8+0]
0x18001e7f1  dec     r14
0x18001e7f4  mov     rdx, r14; SizeInWords
0x18001e7f7  mov     r8, rbx; Source
0x18001e7fa  mov     rcx, rsi; Destination
0x18001e7fd  call    cs:__imp_wcscpy_s
  ... truncated ...
```
