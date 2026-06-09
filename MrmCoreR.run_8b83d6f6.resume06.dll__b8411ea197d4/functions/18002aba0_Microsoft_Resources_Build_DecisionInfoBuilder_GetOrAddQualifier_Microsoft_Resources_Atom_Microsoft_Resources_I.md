# Microsoft::Resources::Build::DecisionInfoBuilder::GetOrAddQualifier(Microsoft::Resources::Atom,Microsoft::Resources::ICondition::ConditionOperator,ushort const *,ushort,double,Microsoft::Resources::QualifierResult *)

- ea: `0x18002aba0`
- end: `0x18002b367`
- name: `?GetOrAddQualifier@DecisionInfoBuilder@Build@Resources@Microsoft@@QEAAJUAtom@34@W4ConditionOperator@ICondition@34@PEBGGNPEAVQualifierResult@34@@Z`
- size: `1991`
- prototype: `int __high(struct Microsoft::Resources::Atom, enum Microsoft::Resources::ICondition::ConditionOperator, const unsigned __int16 *, unsigned __int16, double, struct Microsoft::Resources::QualifierResult *)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180029cc0`
- `0x180096fd0`

## callees

- `0x180019570`
- `0x180028ad0`
- `0x1800297e4`
- `0x18002aba0`
- `0x18002be90`
- `0x18002c8d0`
- `0x180058fc4`
- `0x18005a9b8`
- `0x1800862f0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002acc4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ae66`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b1e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b202`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002acc4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ae66`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b1e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b202`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Build::DecisionInfoBuilder::GetOrAddQualifier(
        __int64 a1,
        unsigned __int64 a2,
        const WCHAR *a3,
        const WCHAR *a4,
        unsigned __int16 a5,
        double a6,
        __int64 a7)
{
  const WCHAR *v7; // r15
  int v8; // r13d
  unsigned int v10; // ebp
  _QWORD *v11; // rax
  int v12; // r14d
  __int64 *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rsi
  int v16; // edi
  __int64 v17; // rdx
  unsigned int v18; // eax
  int v19; // edx
  const WCHAR *v20; // rcx
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  int v24; // r12d
  __int64 v25; // r12
  unsigned __int64 v26; // rbp
  __int64 v27; // rax
  __int64 v28; // rcx
  int v29; // r14d
  __int64 v31; // rbx
  void **v32; // r14
  __int64 v33; // r12
  int v34; // eax
  const WCHAR *v35; // r8
  int v36; // ecx
  int v37; // eax
  int v38; // ecx
  int v39; // eax
  int v40; // r12d
  unsigned int v41; // ecx
  unsigned int v42; // eax
  int v43; // ebp
  __int64 v44; // rcx
  unsigned int v45; // ebp
  __int64 v46; // rdx
  _WORD *v47; // r8
  _WORD *v48; // rax
  __int64 *v49; // r15
  __int64 v50; // r10
  unsigned __int16 v51; // si
  __int64 v52; // rcx
  __int64 v53; // rax
  _DWORD *v54; // rdi
  unsigned int v55; // ebp
  unsigned int v56; // ebx
  __int64 v57; // rsi
  __int64 *v58; // rdi
  __int64 v59; // rax
  int v60; // eax
  int v61; // eax
  unsigned int v62; // ebp
  int v63; // eax
  __int64 v64; // rax
  __int64 v65; // rdx
  int v66; // eax
  __int64 v67; // rcx
  int v68; // eax
  int v69; // eax
  int v70; // eax
  unsigned int v71; // esi
  int v72; // eax
  unsigned int v73; // ebx
  Microsoft::Resources::QualifierResult *v74; // r9
  __int64 v75; // r10
  int bIgnoreCase; // [rsp+20h] [rbp-98h]
  int v77; // [rsp+30h] [rbp-88h]
  __int16 v78; // [rsp+30h] [rbp-88h]
  unsigned int v79; // [rsp+34h] [rbp-84h]
  __int64 v80; // [rsp+38h] [rbp-80h] BYREF
  __int64 v81; // [rsp+40h] [rbp-78h] BYREF
  int v82[2]; // [rsp+48h] [rbp-70h]
  int v83[2]; // [rsp+50h] [rbp-68h]
  _QWORD v84[2]; // [rsp+58h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v79 = (unsigned int)a3;
  v7 = a4;
  v8 = (int)a3;
  v84[0] = a7;
  v80 = a1;
  if ( (_DWORD)a3 == 1 )
  {
    if ( a2 )
      return 2147957513LL;
    if ( !(unsigned __int8)DefString_IsEmpty(a4) )
      return 2147957514LL;
    if ( v74 )
      return Microsoft::Resources::QualifierResult::Set(
               v74,
               *(const struct Microsoft::Resources::IRawDecisionInfo **)(v75 + 8),
               0);
    return 0;
  }
  if ( !(_DWORD)a3 )
    return 2147957537LL;
  if ( (a2 & 0xFFFF8000FFFF8000uLL) != 0 )
    return 2147943044LL;
  v10 = 0;
  HIWORD(v77) = WORD2(a2);
  v11 = *(_QWORD **)(a1 + 8);
  LOWORD(v77) = a2;
  v12 = -1;
  v13 = (__int64 *)v11[3];
  v14 = v11[4];
  v15 = v11[8];
  v16 = v77;
  *(_QWORD *)v83 = v13;
  *(_QWORD *)v82 = v14;
  while ( v10 < *((_DWORD *)v13 + 3) )
  {
    v17 = *v13;
    if ( v77 == *(_DWORD *)(v17 + 12LL * v10)
      && !*(_WORD *)(v17 + 12LL * v10 + 4)
      && v8 == *(unsigned __int16 *)(v17 + 12LL * v10 + 6) )
    {
      v18 = *(_DWORD *)(v17 + 12LL * v10 + 8);
      if ( v18 < *(_DWORD *)(v15 + 20) )
      {
        v19 = *(_DWORD *)(v15 + 12);
        a3 = &word_1800DEF74;
        if ( v7 )
          a3 = v7;
        v20 = (const WCHAR *)(*(_QWORD *)(v15 + 24) + 2LL * v18);
        if ( v19 )
        {
          if ( v19 != 1 )
            goto LABEL_18;
          v21 = CompareStringOrdinal(v20, -1, a3, -1, 1);
          v22 = v21 - 2;
          if ( v21 == -2147483647 )
          {
            v23 = 0x7FFFFFFF;
          }
          else if ( v22 < 0 )
          {
            v23 = -1;
          }
          else
          {
            a3 = 0;
            v23 = v22 > 0;
          }
        }
        else
        {
          v69 = CompareStringOrdinal(v20, -1, a3, -1, 0);
          v23 = IntToComparison((unsigned int)(v69 - 2));
        }
        if ( !v23 )
        {
          v12 = v10;
          break;
        }
      }
    }
LABEL_18:
    v13 = *(__int64 **)v83;
    ++v10;
  }
  v24 = (int)(a6 * 1000.0);
  v78 = v24;
  if ( v12 >= 0 )
  {
    v50 = *(_QWORD *)v82;
    v56 = 0;
    v54 = (_DWORD *)(*(_QWORD *)v82 + 12LL);
    v51 = a5;
    while ( 1 )
    {
      if ( v56 >= *(_DWORD *)(*(_QWORD *)v82 + 12LL) )
        goto LABEL_61;
      v65 = *(_QWORD *)(**(_QWORD **)v82 + 8LL * v56);
      if ( (unsigned __int16)v65 == v12 && WORD2(v65) == (_WORD)v24 && WORD1(v65) == a5 )
        break;
      ++v56;
    }
    v55 = -2147024809;
    if ( (v56 & 0x80000000) == 0 )
    {
LABEL_64:
      v57 = v84[0];
      if ( v84[0] )
      {
        v58 = *(__int64 **)(v80 + 8);
        if ( v58 )
        {
          v80 = 0;
          v59 = *v58;
          memset(v84, 0, 12);
          v60 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v59 + 80))(v58, v56, &v80);
          v55 = v60;
          if ( v60 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x23A,
              (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\decisioninfo.cpp",
              (const char *)(unsigned int)v60,
              bIgnoreCase);
          }
          else
          {
            v61 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD *))(*v58 + 72))(v58, (unsigned __int16)v80, v84);
            v62 = v61;
            if ( v61 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x23B,
                (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\decisioninfo.cpp",
                (const char *)(unsigned int)v61,
                bIgnoreCase);
              return v62;
            }
            v63 = v84[1];
            v55 = 0;
            *(_QWORD *)(v57 + 16) = v84[0];
            *(_DWORD *)(v57 + 24) = v63;
            v64 = v80;
            *(_DWORD *)(v57 + 36) = (unsigned __int16)v80;
            *(_QWORD *)(v57 + 8) = v58;
            *(_QWORD *)(v57 + 28) = v64;
            *(_DWORD *)(v57 + 40) = v56;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x235,
            (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\decisioninfo.cpp",
            (const char *)0x80070057LL,
            bIgnoreCase);
        }
      }
      else
      {
        return 0;
      }
      return v55;
    }
LABEL_62:
    if ( *v54 >= *(_DWORD *)(v50 + 8) )
    {
      v72 = Microsoft::Resources::DynamicArray<_MRMFILE_QUALIFIER>::Extend(v50);
      v73 = v72;
      if ( v72 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DC,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\decisioninfobuilder.cpp",
          (const char *)(unsigned int)v72,
          bIgnoreCase);
        return v73;
      }
      v50 = *(_QWORD *)v82;
    }
    *(_QWORD *)(*(_QWORD *)v50 + 8LL * (unsigned int)*v54) = (unsigned __int16)v12
                                                           | ((v51 | ((unsigned __int64)(unsigned __int16)v24 << 16)) << 16);
    v56 = (*v54)++;
    goto LABEL_64;
  }
  v25 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v80 + 8) + 16LL) + 32LL);
  if ( (_DWORD)a2 == (*(unsigned int (__fastcall **)(_QWORD, __int64 *, const WCHAR *, _QWORD))(**(_QWORD **)(v25 + 8)
                                                                                              + 24LL))(
                       *(_QWORD *)(v25 + 8),
                       v13,
                       a3,
                       0)
    && (v26 = HIDWORD(a2),
        SHIDWORD(a2) < (*(int (__fastcall **)(_QWORD))(**(_QWORD **)(v25 + 8) + 128LL))(*(_QWORD *)(v25 + 8))) )
  {
    v27 = *(_QWORD *)(v25 + 24);
    v81 = 0;
    if ( HIDWORD(a2) < *(_DWORD *)(v27 + 12) )
    {
      v28 = *(_QWORD *)(*(_QWORD *)v27 + 8 * v26);
      v81 = v28;
      if ( v28 )
      {
LABEL_25:
        LOWORD(v8) = v79;
        v29 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, const WCHAR *))(*(_QWORD *)v28 + 32LL))(
                v28,
                a2,
                v79,
                v7);
        if ( v29 < 0 )
          goto LABEL_26;
        goto LABEL_31;
      }
    }
    v66 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, __int64 *))(**(_QWORD **)(v25 + 16) + 136LL))(
            *(_QWORD *)(v25 + 16),
            *(_QWORD *)v25,
            a2,
            &v81);
    v29 = v66;
    if ( v66 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managers.cpp",
        (const char *)(unsigned int)v66,
        bIgnoreCase);
      LOWORD(v8) = v79;
    }
    else
    {
      v67 = *(_QWORD *)(v25 + 24);
      if ( HIDWORD(a2) < *(_DWORD *)(v67 + 12) )
      {
        *(_QWORD *)(*(_QWORD *)v67 + 8 * v26) = v81;
        v28 = v81;
        goto LABEL_25;
      }
      v29 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managers.cpp",
        (const char *)0x80070057LL,
        bIgnoreCase);
      LOWORD(v8) = v79;
    }
  }
  else
  {
    v29 = -2147009783;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1DD,
    (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managers.cpp",
    (const char *)(unsigned int)v29,
    bIgnoreCase);
  if ( v29 < 0 )
  {
LABEL_26:
    if ( (*(_BYTE *)(v80 + 16) & 1) == 0 || (unsigned int)(v29 + 2147009783) > 1 )
      return (unsigned int)v29;
  }
LABEL_31:
  if ( !v7 || !*v7 )
  {
    LODWORD(v31) = 0;
LABEL_59:
    v49 = *(__int64 **)v83;
    if ( *(_DWORD *)(*(_QWORD *)v83 + 12LL) >= *(_DWORD *)(*(_QWORD *)v83 + 8LL) )
    {
      v70 = Microsoft::Resources::DynamicArray<_MRMFILE_BASE_QUALIFIER>::Extend(v83[0]);
      v71 = v70;
      if ( v70 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C1,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\decisioninfobuilder.cpp",
          (const char *)(unsigned int)v70,
          bIgnoreCase);
        return v71;
      }
    }
    v50 = *(_QWORD *)v82;
    v51 = a5;
    LOWORD(v24) = v78;
    v52 = 3LL * *((unsigned int *)v49 + 3);
    v53 = *v49;
    *(_DWORD *)(v53 + 4 * v52) = v16;
    v54 = (_DWORD *)(v50 + 12);
    *(_WORD *)(v53 + 4 * v52 + 4) = 0;
    *(_WORD *)(v53 + 4 * v52 + 6) = v8;
    *(_DWORD *)(v53 + 4 * v52 + 8) = v31;
    v12 = *((_DWORD *)v49 + 3);
    *((_DWORD *)v49 + 3) = v12 + 1;
LABEL_61:
    v55 = -2147024809;
    goto LABEL_62;
  }
  LODWORD(v31) = 1;
  v32 = (void **)(v15 + 24);
  v33 = -1;
  while ( 1 )
  {
    v34 = *(_DWORD *)(v15 + 16);
    if ( (int)v31 >= v34 )
      break;
    v32 = (void **)(v15 + 24);
    v35 = (const WCHAR *)(*(_QWORD *)(v15 + 24) + 2LL * (int)v31);
    if ( *v7 != *v35 )
      goto LABEL_36;
    v36 = *(_DWORD *)(v15 + 12);
    if ( v36 )
    {
      if ( v36 != 1 )
        goto LABEL_36;
      v37 = CompareStringOrdinal(v7, -1, v35, -1, 1);
      v38 = v37 - 2;
      if ( v37 == -2147483647 )
      {
        v39 = 0x7FFFFFFF;
      }
      else if ( v38 < 0 )
      {
        v39 = -1;
      }
      else
      {
        v39 = v38 > 0;
      }
    }
    else
    {
      v68 = CompareStringOrdinal(v7, -1, v35, -1, 0);
      v39 = IntToComparison((unsigned int)(v68 - 2));
    }
    if ( !v39 )
      goto LABEL_56;
LABEL_36:
    LODWORD(v31) = v31 + 1;
  }
  do
    ++v33;
  while ( v7[v33] );
  v40 = v33 + 1;
  v41 = v40 + v34;
  v42 = *(_DWORD *)(v15 + 20);
  if ( v41 > v42 )
  {
    if ( (*(_DWORD *)(v15 + 8) & 0x100) != 0 )
      return 2147549183LL;
    v43 = 2 * v42;
    v32 = (void **)(v15 + 24);
    if ( v41 > 2 * v42 )
      v43 = v41;
    if ( !(unsigned __int8)DefArray_TryEnsureSizeByElemSize(*v32, v15 + 24) )
      return 2147549183LL;
    *(_DWORD *)(v15 + 20) = v43;
  }
  else
  {
    v43 = *(_DWORD *)(v15 + 20);
  }
  v31 = *(int *)(v15 + 16);
  v44 = 2147483646;
  v45 = v43 - v31;
  v46 = v45;
  v47 = (char *)*v32 + 2 * v31;
  if ( v45 - 1 > 0x7FFFFFFE )
  {
    if ( v45 )
      *v47 = 0;
    return 2147549183LL;
  }
  do
  {
    if ( !v44 )
      break;
    if ( !*v7 )
      break;
    *v47++ = *v7++;
    --v44;
    --v46;
  }
  while ( v46 );
  v48 = v47 - 1;
  if ( v46 )
    v48 = v47;
  *v48 = 0;
  if ( !v46 )
    return 2147549183LL;
  *(_DWORD *)(v15 + 16) += v40;
LABEL_56:
  if ( (int)v31 >= 0 )
    goto LABEL_59;
  return 2147549183LL;
}

```

## disassembly

```asm
0x18002aba0  mov     [rsp+arg_8], rdx
0x18002aba5  mov     r11, rsp
0x18002aba8  push    rbx
0x18002aba9  push    r13
0x18002abab  push    r14
0x18002abad  push    r15
0x18002abaf  sub     rsp, 98h
0x18002abb6  mov     rax, cs:__security_cookie
0x18002abbd  xor     rax, rsp
0x18002abc0  mov     [rsp+0B8h+var_50], rax
0x18002abc5  mov     [rsp+0B8h+var_84], r8d
0x18002abca  mov     r15, r9
0x18002abcd  mov     r9, [rsp+0B8h+arg_30]
0x18002abd5  mov     r13d, r8d
0x18002abd8  mov     [rsp+0B8h+var_60], r9
0x18002abdd  mov     rbx, rdx
0x18002abe0  mov     [rsp+0B8h+var_80], rcx
0x18002abe5  mov     r10, rcx
0x18002abe8  cmp     r8d, 1
0x18002abec  jz      loc_18002B262
0x18002abf2  test    r8d, r8d
0x18002abf5  jz      loc_18002B275
0x18002abfb  mov     rax, 0FFFF8000FFFF8000h
0x18002ac05  test    rax, rdx
0x18002ac08  jnz     loc_18002AF52
0x18002ac0e  movzx   eax, word ptr [r11+14h]
0x18002ac13  xor     r9d, r9d
0x18002ac16  mov     [r11-28h], rbp
0x18002ac1a  mov     ebp, r9d
0x18002ac1d  mov     [r11-30h], rsi
0x18002ac21  mov     word ptr [rsp+0B8h+var_88+2], ax
0x18002ac26  mov     rax, [rcx+8]
0x18002ac2a  mov     [r11-38h], rdi
0x18002ac2e  mov     [r11-40h], r12
0x18002ac32  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18002ac39  mov     word ptr [rsp+0B8h+var_88], bx
0x18002ac3e  mov     r14d, r12d
0x18002ac41  mov     rdx, [rax+18h]
0x18002ac45  mov     rcx, [rax+20h]
0x18002ac49  mov     rsi, [rax+40h]
0x18002ac4d  mov     edi, [rsp+0B8h+var_88]
0x18002ac51  mov     qword ptr [rsp+0B8h+var_68], rdx
0x18002ac56  mov     qword ptr [rsp+0B8h+var_70], rcx
0x18002ac5b  nop     dword ptr [rax+rax+00h]
0x18002ac60  cmp     ebp, [rdx+0Ch]
0x18002ac63  jnb     loc_18002AD02
0x18002ac69  mov     rdx, [rdx]
0x18002ac6c  mov     eax, ebp
0x18002ac6e  lea     rcx, [rax+rax*2]
0x18002ac72  cmp     edi, [rdx+rcx*4]
0x18002ac75  jnz     short loc_18002ACF3
0x18002ac77  cmp     word ptr [rdx+rcx*4+4], 0
0x18002ac7d  jnz     short loc_18002ACF3
0x18002ac7f  movzx   eax, word ptr [rdx+rcx*4+6]
0x18002ac84  cmp     r13d, eax
0x18002ac87  jnz     short loc_18002ACF3
0x18002ac89  mov     eax, [rdx+rcx*4+8]
0x18002ac8d  cmp     eax, [rsi+14h]
0x18002ac90  jnb     short loc_18002ACF3
0x18002ac92  mov     edx, [rsi+0Ch]
0x18002ac95  lea     r8, word_1800DEF74
0x18002ac9c  mov     ecx, eax
0x18002ac9e  test    r15, r15
0x18002aca1  mov     rax, [rsi+18h]
0x18002aca5  cmovnz  r8, r15; lpString2
0x18002aca9  lea     rcx, [rax+rcx*2]; lpString1
0x18002acad  test    edx, edx
0x18002acaf  jz      loc_18002B1F7
0x18002acb5  cmp     edx, 1
0x18002acb8  jnz     short loc_18002ACF3
0x18002acba  mov     [rsp+0B8h+bIgnoreCase], edx; int
0x18002acbe  mov     r9d, r12d; cchCount2
0x18002acc1  mov     edx, r12d; cchCount1
0x18002acc4  call    cs:__imp_CompareStringOrdinal
0x18002acca  lea     ecx, [rax-2]
0x18002accd  cmp     ecx, 7FFFFFFFh
0x18002acd3  jz      loc_18002B27F
0x18002acd9  test    ecx, ecx
0x18002acdb  js      loc_18002ADD2
0x18002ace1  xor     r8d, r8d
0x18002ace4  test    ecx, ecx
0x18002ace6  mov     eax, r8d
0x18002ace9  setnle  al
0x18002acec  xor     r9d, r9d
0x18002acef  test    eax, eax
0x18002acf1  jz      short loc_18002ACFF
0x18002acf3  mov     rdx, qword ptr [rsp+0B8h+var_68]
0x18002acf8  inc     ebp
0x18002acfa  jmp     loc_18002AC60
0x18002acff  mov     r14d, ebp
0x18002ad02  movsd   xmm0, [rsp+0B8h+arg_28]
0x18002ad0b  mulsd   xmm0, cs:__real@408f400000000000
0x18002ad13  cvttsd2si r12d, xmm0
0x18002ad18  mov     [rsp+0B8h+var_88], r12d
0x18002ad1d  test    r14d, r14d
0x18002ad20  jns     loc_18002B097
0x18002ad26  mov     rax, [rsp+0B8h+var_80]
0x18002ad2b  mov     rax, [rax+8]
0x18002ad2f  mov     rcx, [rax+10h]
0x18002ad33  mov     r12, [rcx+20h]
0x18002ad37  mov     rcx, [r12+8]
0x18002ad3c  mov     rax, [rcx]
0x18002ad3f  mov     rax, [rax+18h]
0x18002ad43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad48  cmp     ebx, eax
0x18002ad4a  jnz     loc_18002ADDA
0x18002ad50  mov     rcx, [r12+8]
0x18002ad55  mov     rbp, rbx
0x18002ad58  shr     rbp, 20h
0x18002ad5c  mov     rax, [rcx]
0x18002ad5f  mov     rax, [rax+80h]
0x18002ad66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad6b  cmp     ebp, eax
0x18002ad6d  jge     short loc_18002ADDA
0x18002ad6f  mov     rax, [r12+18h]
0x18002ad74  xor     r8d, r8d
0x18002ad77  mov     [rsp+0B8h+var_78], r8
0x18002ad7c  cmp     ebp, [rax+0Ch]
0x18002ad7f  jnb     loc_18002B162
0x18002ad85  mov     rax, [rax]
0x18002ad88  mov     rcx, [rax+rbp*8]
0x18002ad8c  mov     [rsp+0B8h+var_78], rcx
0x18002ad91  test    rcx, rcx
0x18002ad94  jz      loc_18002B162
0x18002ad9a  mov     rax, [rcx]
0x18002ad9d  mov     r9, r15
0x18002ada0  mov     r13d, [rsp+0B8h+var_84]
0x18002ada5  mov     rdx, rbx
0x18002ada8  mov     r8d, r13d
0x18002adab  mov     rax, [rax+20h]
0x18002adaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adb4  mov     r14d, eax
0x18002adb7  test    eax, eax
0x18002adb9  jns     short loc_18002AE01
0x18002adbb  mov     rax, [rsp+0B8h+var_80]
0x18002adc0  test    byte ptr [rax+10h], 1
0x18002adc4  jnz     loc_18002B2B5
0x18002adca  mov     eax, r14d
0x18002adcd  jmp     loc_18002AF19
0x18002add2  mov     eax, r12d
0x18002add5  jmp     loc_18002ACEC
0x18002adda  mov     r14d, 80073B09h
0x18002ade0  mov     rcx, [rsp+0B8h]; this
0x18002ade8  lea     r8, aMinkernelMrtMr_30; "minkernel\\mrt\\mrm\\mrmmin\\managers.c"...
0x18002adef  mov     r9d, r14d; char *
0x18002adf2  mov     edx, 1DDh; void *
0x18002adf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002adfc  test    r14d, r14d
0x18002adff  js      short loc_18002ADBB
0x18002ae01  test    r15, r15
0x18002ae04  jz      loc_18002B2D4
0x18002ae0a  cmp     word ptr [r15], 0
0x18002ae0f  jz      loc_18002B2D4
0x18002ae15  mov     ebx, 1
0x18002ae1a  lea     r14, [rsi+18h]
0x18002ae1e  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18002ae25  mov     eax, [rsi+10h]
0x18002ae28  cmp     ebx, eax
0x18002ae2a  jge     short loc_18002AE94
0x18002ae2c  mov     rax, [rsi+18h]
0x18002ae30  lea     r14, [rsi+18h]
0x18002ae34  movsxd  rcx, ebx
0x18002ae37  lea     r8, [rax+rcx*2]; lpString2
0x18002ae3b  movzx   eax, word ptr [rax+rcx*2]
0x18002ae3f  cmp     [r15], ax
0x18002ae43  jz      short loc_18002AE49
0x18002ae45  inc     ebx
0x18002ae47  jmp     short loc_18002AE25
0x18002ae49  mov     ecx, [rsi+0Ch]
0x18002ae4c  test    ecx, ecx
0x18002ae4e  jz      loc_18002B1D3
0x18002ae54  cmp     ecx, 1
0x18002ae57  jnz     short loc_18002AE45
0x18002ae59  mov     [rsp+0B8h+bIgnoreCase], ecx; bIgnoreCase
0x18002ae5d  mov     r9d, r12d; cchCount2
0x18002ae60  mov     rcx, r15; lpString1
0x18002ae63  mov     edx, r12d; cchCount1
0x18002ae66  call    cs:__imp_CompareStringOrdinal
0x18002ae6c  lea     ecx, [rax-2]
0x18002ae6f  cmp     ecx, 7FFFFFFFh
0x18002ae75  jz      loc_18002B2CA
0x18002ae7b  test    ecx, ecx
0x18002ae7d  js      short loc_18002AE8F
0x18002ae7f  xor     eax, eax
0x18002ae81  test    ecx, ecx
0x18002ae83  setnle  al
0x18002ae86  test    eax, eax
0x18002ae88  jnz     short loc_18002AE45
0x18002ae8a  jmp     loc_18002AF10
0x18002ae8f  mov     eax, r12d
0x18002ae92  jmp     short loc_18002AE86
0x18002ae94  inc     r12
0x18002ae97  cmp     word ptr [r15+r12*2], 0
0x18002ae9d  jnz     short loc_18002AE94
0x18002ae9f  inc     r12d
0x18002aea2  lea     ecx, [r12+rax]
0x18002aea6  mov     eax, [rsi+14h]
0x18002aea9  cmp     ecx, eax
0x18002aeab  ja      loc_18002B0F6
0x18002aeb1  mov     ebp, eax
0x18002aeb3  movsxd  rbx, dword ptr [rsi+10h]
0x18002aeb7  mov     ecx, 7FFFFFFEh
0x18002aebc  mov     rax, [r14]
0x18002aebf  sub     ebp, ebx
0x18002aec1  mov     edx, ebp
0x18002aec3  lea     r8, [rax+rbx*2]
0x18002aec7  lea     eax, [rbp-1]
0x18002aeca  cmp     eax, ecx
0x18002aecc  ja      loc_18002B24F
0x18002aed2  test    rcx, rcx
0x18002aed5  jz      short loc_18002AEF5
0x18002aed7  movzx   eax, word ptr [r15]
0x18002aedb  test    ax, ax
0x18002aede  jz      short loc_18002AEF5
0x18002aee0  mov     [r8], ax
0x18002aee4  add     r15, 2
0x18002aee8  add     r8, 2
0x18002aeec  dec     rcx
0x18002aeef  sub     rdx, 1
0x18002aef3  jnz     short loc_18002AED2
0x18002aef5  test    rdx, rdx
0x18002aef8  lea     rax, [r8-2]
0x18002aefc  cmovnz  rax, r8
0x18002af00  xor     r8d, r8d
0x18002af03  mov     [rax], r8w
0x18002af07  test    rdx, rdx
0x18002af0a  jz      short loc_18002AF14
0x18002af0c  add     [rsi+10h], r12d
0x18002af10  test    ebx, ebx
0x18002af12  jns     short loc_18002AF59
0x18002af14  mov     eax, 8000FFFFh
0x18002af19  mov     rdi, [rsp+0B8h+var_38]
0x18002af21  mov     rsi, [rsp+0B8h+var_30]
0x18002af29  mov     rbp, [rsp+0B8h+var_28]
0x18002af31  mov     r12, [rsp+0B8h+var_40]
0x18002af36  mov     rcx, [rsp+0B8h+var_50]
0x18002af3b  xor     rcx, rsp; StackCookie
0x18002af3e  call    __security_check_cookie
0x18002af43  add     rsp, 98h
0x18002af4a  pop     r15
0x18002af4c  pop     r14
0x18002af4e  pop     r13
0x18002af50  pop     rbx
0x18002af51  retn
0x18002af52  mov     eax, 80070284h
0x18002af57  jmp     short loc_18002AF36
0x18002af59  xor     r9d, r9d
0x18002af5c  mov     r15, qword ptr [rsp+0B8h+var_68]
0x18002af61  mov     edx, [r15+0Ch]
0x18002af65  cmp     edx, [r15+8]
0x18002af69  jnb     loc_18002B215
0x18002af6f  mov     eax, [r15+0Ch]
0x18002af73  mov     r10, qword ptr [rsp+0B8h+var_70]
0x18002af78  movzx   esi, [rsp+0B8h+arg_20]
0x18002af80  mov     r12d, [rsp+0B8h+var_88]
0x18002af85  lea     rcx, [rax+rax*2]
0x18002af89  mov     rax, [r15]
0x18002af8c  mov     [rax+rcx*4], edi
0x18002af8f  lea     rdi, [r10+0Ch]
0x18002af93  mov     [rax+rcx*4+4], r9w
0x18002af99  mov     [rax+rcx*4+6], r13w
0x18002af9f  mov     [rax+rcx*4+8], ebx
0x18002afa3  mov     r14d, [r15+0Ch]
0x18002afa7  lea     eax, [r14+1]
0x18002afab  mov     [r15+0Ch], eax
0x18002afaf  mov     ebp, 80070057h
0x18002afb4  mov     edx, [rdi]
0x18002afb6  cmp     edx, [r10+8]
0x18002afba  jnb     loc_18002B231
0x18002afc0  mov     ecx, [rdi]
0x18002afc2  movzx   eax, si
0x18002afc5  movzx   edx, r12w
0x18002afc9  shl     rdx, 10h
0x18002afcd  or      rdx, rax
0x18002afd0  movzx   eax, r14w
0x18002afd4  shl     rdx, 10h
0x18002afd8  or      rdx, rax
0x18002afdb  mov     rax, [r10]
0x18002afde  xor     r9d, r9d
0x18002afe1  mov     [rax+rcx*8], rdx
0x18002afe5  mov     ebx, [rdi]
0x18002afe7  lea     eax, [rbx+1]
0x18002afea  mov     [rdi], eax
0x18002afec  mov     rsi, [rsp+0B8h+var_60]
0x18002aff1  test    rsi, rsi
0x18002aff4  jz      loc_18002B137
0x18002affa  mov     rax, [rsp+0B8h+var_80]
0x18002afff  mov     rdi, [rax+8]
0x18002b003  test    rdi, rdi
0x18002b006  jz      loc_18002B325
0x18002b00c  xor     eax, eax
0x18002b00e  mov     [rsp+0B8h+var_80], r9
0x18002b013  mov     [rsp+0B8h+var_60+2], rax
0x18002b018  lea     r8, [rsp+0B8h+var_80]
0x18002b01d  mov     [rsp+0B8h+var_56], ax
0x18002b022  mov     edx, ebx
0x18002b024  mov     rax, [rdi]
0x18002b027  mov     rcx, rdi
0x18002b02a  mov     word ptr [rsp+0B8h+var_60], r9w
0x18002b030  mov     rax, [rax+50h]
  ... truncated ...
```
