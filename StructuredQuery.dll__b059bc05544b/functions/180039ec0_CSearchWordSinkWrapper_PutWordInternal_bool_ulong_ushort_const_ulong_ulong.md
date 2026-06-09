# CSearchWordSinkWrapper::_PutWordInternal(bool,ulong,ushort const *,ulong,ulong)

- ea: `0x180039ec0`
- end: `0x18003ab91`
- name: `?_PutWordInternal@CSearchWordSinkWrapper@@QEAAJ_NKPEBGKK@Z`
- size: `3281`
- prototype: `__int64 __fastcall(CSearchWordSinkWrapper *this, char, unsigned int, unsigned __int16 *, int cchCount2, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180039e60`
- `0x180039e90`

## callees

- `0x180039ec0`
- `0x18003ab98`
- `0x18003ad50`
- `0x18003ae2c`
- `0x18003ae94`
- `0x18005bd2c`
- `0x18005ef6b`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!GetStringTypeW` at `0x18003a94c`
- `api-ms-win-core-string-l1-1-0!GetStringTypeW` at `0x18003a94c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a71a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a71a`

## pseudocode

```c
__int64 __fastcall CSearchWordSinkWrapper::_PutWordInternal(
        CSearchWordSinkWrapper *this,
        char a2,
        unsigned int a3,
        unsigned __int16 *a4,
        int cchCount2,
        unsigned int a6)
{
  unsigned int v6; // r13d
  char v7; // di
  int v8; // r15d
  unsigned __int64 v9; // r14
  const unsigned __int16 *v10; // rbx
  char v11; // r12
  CSearchWordSinkWrapper *v12; // rsi
  __int64 v13; // r8
  __int16 v14; // dx
  unsigned int i; // ebx
  int v16; // edx
  unsigned int v17; // r10d
  __int64 v18; // r9
  unsigned int v19; // edx
  unsigned __int16 v20; // cx
  __int16 v21; // cx
  unsigned int v22; // r11d
  __int64 v23; // rdi
  unsigned int v24; // ebx
  unsigned __int16 v25; // cx
  __int16 v26; // cx
  unsigned int v27; // ebx
  __int64 *v28; // rcx
  __int64 v29; // rax
  __int64 v31; // rax
  unsigned __int64 v32; // r8
  __int16 *v33; // rdx
  unsigned __int16 *v34; // rax
  unsigned int v35; // edi
  int v36; // r10d
  unsigned __int8 v37; // bl
  const unsigned __int16 *v38; // r9
  unsigned __int16 v39; // ax
  __int16 v40; // cx
  unsigned int v41; // ebx
  void *v42; // rbx
  __int64 v43; // r8
  __int16 v44; // dx
  __int64 v45; // rdx
  __int64 v46; // rbx
  __int64 v47; // rdx
  __int64 *v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rax
  int v51; // eax
  void *v52; // rdi
  __int64 *v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rax
  __int64 *v56; // rcx
  unsigned int v57; // ebx
  __int64 v58; // r11
  __int64 v59; // r8
  __int64 v60; // r9
  int v61; // eax
  char v62; // [rsp+30h] [rbp-38h]
  WORD CharType[2]; // [rsp+34h] [rbp-34h] BYREF
  wchar_t SrcStr[4]; // [rsp+38h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  __int64 v66; // [rsp+48h] [rbp-20h]
  __int64 v67; // [rsp+50h] [rbp-18h]

  v6 = a6;
  v7 = 0;
  v8 = 0;
  v9 = a3;
  v62 = 0;
  v10 = a4;
  v11 = a2;
  v12 = this;
  if ( a3 >= 3
    && *a4 == 78
    && a4[1] == 78
    && cchCount2
    && (v31 = a6 + cchCount2 - 1, (unsigned int)v31 < *((_DWORD *)this + 10))
    && ((v32 = *((_QWORD *)this + 4), v33 = (__int16 *)(v32 + 2 * v31), *v33 == 48) || *v33 == -240) )
  {
    v34 = a4;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = &a4[(unsigned int)(v9 - 1)];
    while ( v38 >= v34 && (unsigned __int64)v33 >= v32 )
    {
      v39 = *v38;
      if ( (*v38 == 48 || v39 == 0xFF10) && (*v33 == 48 || *v33 == -240) )
      {
        v34 = a4;
        ++v36;
        --v38;
        --v33;
      }
      else
      {
        if ( v39 == 0xFF10 || v39 == 48 || *v33 != -240 && *v33 != 48 )
        {
          v40 = *v33;
          if ( v39 != *v33
            && v39 != 68
            && (v40 == 46 || v40 == 44 || v40 == 183 || v40 == -242 || v40 == -24866 || v40 == 28857) )
          {
            v35 += v36;
            v37 = 1;
          }
          break;
        }
        v34 = a4;
        ++v35;
        --v33;
      }
    }
    if ( v35 )
    {
      pv = 0;
      v66 = 0;
      v67 = 0;
      v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
             (__int64)&pv,
             (unsigned int)v9 + v35 + v37);
      if ( v8 >= 0 )
      {
        v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
               (__int64)&pv,
               a4,
               v9);
        if ( v8 >= 0 )
        {
          if ( v37 )
            v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                   (__int64)&pv,
                   L"D",
                   1u);
          v41 = 0;
          if ( v8 >= 0 )
          {
            while ( v41 < v35 )
            {
              ++v41;
              v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                     (__int64)&pv,
                     L"0",
                     1u);
              if ( v8 < 0 )
                goto LABEL_93;
            }
            v48 = (__int64 *)*((_QWORD *)v12 + 2);
            v42 = pv;
            v49 = v66;
            v50 = *v48;
            if ( v11 )
            {
              if ( v66 == -1 )
              {
                if ( pv )
                {
                  v49 = -1;
                  do
                    ++v49;
                  while ( *((_WORD *)pv + v49) );
                }
                else
                {
                  v49 = 0;
                }
              }
              v51 = (*(__int64 (__fastcall **)(__int64 *, __int64, LPVOID, _QWORD, unsigned int))(v50 + 32))(
                      v48,
                      v49,
                      pv,
                      (unsigned int)cchCount2,
                      a6);
            }
            else
            {
              if ( v66 == -1 )
              {
                if ( pv )
                {
                  v49 = -1;
                  do
                    ++v49;
                  while ( *((_WORD *)pv + v49) );
                }
                else
                {
                  v49 = 0;
                }
              }
              v51 = (*(__int64 (__fastcall **)(__int64 *, __int64, LPVOID, _QWORD, unsigned int))(v50 + 24))(
                      v48,
                      v49,
                      pv,
                      (unsigned int)cchCount2,
                      a6);
            }
            v7 = 1;
            v8 = v51;
            v62 = 1;
            goto LABEL_95;
          }
        }
      }
LABEL_93:
      v7 = 0;
      goto LABEL_94;
    }
LABEL_150:
    v10 = a4;
    v7 = 0;
  }
  else if ( v11 )
  {
    if ( (unsigned int)v9 >= 2 )
    {
      v13 = *((_QWORD *)this + 4);
      v14 = *(_WORD *)(v13 + 2LL * a6);
      if ( (v14 == 46 || v14 == 44 || v14 == 183 || v14 == -242 || v14 == -24866 || v14 == 28857)
        && (!a6 || IsSpace(*(_WORD *)(v13 + 2LL * (a6 - 1)))) )
      {
        for ( i = 1; i < (unsigned int)v9; ++i )
        {
          SrcStr[0] = a4[i];
          CharType[0] = 0;
          GetStringTypeW(1u, SrcStr, 1, CharType);
          if ( (CharType[0] & 4) == 0 )
            goto LABEL_150;
        }
        v10 = a4;
        v7 = 1;
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD, unsigned int))(**((_QWORD **)v12 + 2)
                                                                                                 + 32LL))(
               *((_QWORD *)v12 + 2),
               (unsigned int)(v9 - 1),
               a4 + 1,
               (unsigned int)cchCount2,
               a6);
        v62 = 1;
        goto LABEL_98;
      }
    }
  }
  else if ( (unsigned int)v9 >= 5 && *a4 == 78 && a4[1] == 78 && a4[2] == 48 && a4[3] == 68 )
  {
    v43 = *((_QWORD *)this + 4);
    v44 = *(_WORD *)(v43 + 2LL * a6);
    if ( (v44 == 46 || v44 == 44 || v44 == 183 || v44 == -242 || v44 == -24866 || v44 == 28857)
      && (!a6 || IsSpace(*(_WORD *)(v43 + 2LL * (a6 - 1)))) )
    {
      pv = 0;
      v66 = 0;
      v67 = 0;
      v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
             (__int64)&pv,
             (unsigned int)(v9 - 2));
      if ( v8 >= 0 )
      {
        v45 = v66;
        if ( v66 == -1 )
        {
          if ( pv )
          {
            v45 = -1;
            do
              ++v45;
            while ( *((_WORD *)pv + v45) );
          }
          else
          {
            v45 = 0;
          }
          v66 = v45;
        }
        v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
               (__int64)&pv,
               v45 + 2);
        if ( v8 >= 0 )
        {
          v46 = v66;
          StringCchCopyNW((unsigned __int16 *)pv + v66, 3u, L"NN", 2u);
          v66 = v46 + 2;
          v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                 (__int64)&pv,
                 a4 + 4,
                 (unsigned int)(v9 - 4));
          if ( v8 >= 0 )
          {
            v47 = v66;
            v42 = pv;
            if ( v66 == -1 )
            {
              if ( pv )
              {
                v47 = -1;
                do
                  ++v47;
                while ( *((_WORD *)pv + v47) );
              }
              else
              {
                v47 = 0;
              }
            }
            v7 = 1;
            v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID, _QWORD, unsigned int))(**((_QWORD **)v12 + 2) + 24LL))(
                   *((_QWORD *)v12 + 2),
                   v47,
                   pv,
                   (unsigned int)cchCount2,
                   a6);
            v62 = 1;
            goto LABEL_95;
          }
        }
      }
LABEL_94:
      v42 = pv;
LABEL_95:
      if ( v42 )
        CoTaskMemFree_0(v42);
      v10 = a4;
LABEL_98:
      if ( v8 < 0 )
        return (unsigned int)v8;
      if ( v7 )
        return (unsigned int)v8;
    }
  }
  v16 = *((_DWORD *)v12 + 14);
  if ( v16 == 1054 )
  {
    if ( !v11 && (unsigned int)v9 > 3 && *v10 == 3585 && v10[1] == 3634 && v10[2] == 3619 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, unsigned int))(**((_QWORD **)v12 + 2) + 32LL))(
             *((_QWORD *)v12 + 2),
             (unsigned int)v9,
             v10,
             (unsigned int)cchCount2,
             a6);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 *))(**((_QWORD **)v12 + 2) + 24LL))(
               *((_QWORD *)v12 + 2),
               3,
               v10);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, unsigned int))(**((_QWORD **)v12 + 2) + 24LL))(
                 *((_QWORD *)v12 + 2),
                 (unsigned int)(v9 - 3),
                 v10 + 3,
                 (unsigned int)(cchCount2 - 3),
                 a6 + 3);
          v7 = 1;
          goto LABEL_56;
        }
      }
      goto LABEL_127;
    }
  }
  else
  {
    if ( ((v16 - 1028) & 0xFFFFE7FF) == 0
      && v16 != 7172
      && (_DWORD)v9
      && *v10 == 24230
      && a6
      && *(_WORD *)(*((_QWORD *)v12 + 4) + 2LL * (a6 - 1)) == 24180 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)v12 + 2) + 32LL))(
             *((_QWORD *)v12 + 2),
             2,
             &qword_18009BA28);
      goto LABEL_56;
    }
    if ( ((v16 - 2052) & 0xFFFFFBFF) != 0 )
      goto LABEL_20;
    if ( !v11
      && (_DWORD)v9 == 4
      && cchCount2 == 4
      && *v10 == 22825
      && v10[1] == 28079
      && v10[2] == 28023
      && a4[3] == 0x89D2 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 *, __int64, unsigned int))(**((_QWORD **)v12 + 2)
                                                                                                 + 32LL))(
             *((_QWORD *)v12 + 2),
             4,
             a4,
             4,
             a6);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**((_QWORD **)v12 + 2) + 24LL))(
               *((_QWORD *)v12 + 2),
               2,
               a4);
        if ( v8 >= 0 )
          v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 *))(**((_QWORD **)v12 + 2) + 24LL))(
                 *((_QWORD *)v12 + 2),
                 2,
                 v10 + 2);
      }
      goto LABEL_138;
    }
    if ( v16 != 2052 )
    {
LABEL_20:
      if ( v16 != 3076 )
        goto LABEL_21;
    }
    if ( v11 )
    {
LABEL_21:
      v10 = a4;
    }
    else
    {
      v10 = a4;
      if ( (unsigned int)v9 >= 2 && *a4 == 26032 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD, unsigned int))(**((_QWORD **)v12 + 2)
                                                                                                 + 32LL))(
               *((_QWORD *)v12 + 2),
               (unsigned int)v9,
               a4,
               (unsigned int)cchCount2,
               a6);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**((_QWORD **)v12 + 2) + 24LL))(
                 *((_QWORD *)v12 + 2),
                 1,
                 a4);
          if ( v8 >= 0 )
            v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD, unsigned int))(**((_QWORD **)v12 + 2) + 24LL))(
                   *((_QWORD *)v12 + 2),
                   (unsigned int)(v9 - 1),
                   a4 + 1,
                   (unsigned int)(cchCount2 - 1),
                   a6 + 1);
        }
LABEL_127:
        v7 = 1;
        goto LABEL_56;
      }
    }
  }
  if ( (*((_WORD *)v12 + 28) & 0x3FF) == 1
    && !v11
    && (_DWORD)v9
    && IsArabicScript(*v10)
    && CompareStringOrdinal(a4, v9, (LPCWCH)(2LL * a6 + *((_QWORD *)v12 + 4)), cchCount2, 0) != 2 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD, unsigned int))(**((_QWORD **)v12 + 2)
                                                                                             + 32LL))(
           *((_QWORD *)v12 + 2),
           (unsigned int)v9,
           a4,
           (unsigned int)cchCount2,
           a6);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, unsigned int))(**((_QWORD **)v12 + 2) + 24LL))(
             *((_QWORD *)v12 + 2),
             (unsigned int)cchCount2,
             2LL * a6 + *((_QWORD *)v12 + 4),
             (unsigned int)cchCount2,
             a6);
      v7 = 1;
      goto LABEL_55;
    }
    goto LABEL_138;
  }
  v17 = *((_DWORD *)v12 + 10);
  v18 = *((_QWORD *)v12 + 4);
  v19 = a6;
  wcscpy(SrcStr, L"ᦵ");
  if ( a6 < v17 )
  {
    while ( 1 )
    {
      if ( v19 <= v17 - 2
        && *(_WORD *)(v18 + 2LL * v19) == 0xDB40
        && (unsigned __int16)(*(_WORD *)(v18 + 2LL * (v19 + 1)) + 8960) <= 0xEFu )
      {
        goto LABEL_33;
      }
      if ( v19 && v19 <= v17 - 1 )
      {
        if ( *(_WORD *)(v18 + 2LL * (v19 - 1)) != 0xDB40 )
          goto LABEL_32;
        v20 = *(_WORD *)(v18 + 2LL * v19);
        if ( v20 < 0xDD00u )
          goto LABEL_32;
        if ( v20 <= 0xDDEFu )
          goto LABEL_33;
      }
      if ( v19 > v17 - 1 )
        goto LABEL_36;
LABEL_32:
      v21 = *(_WORD *)(v18 + 2LL * v19);
      if ( (unsigned __int16)(v21 - 6581) > 2u && v21 != 6586 )
      {
LABEL_36:
        LODWORD(v9) = a3;
        v6 = a6;
        v11 = a2;
        break;
      }
LABEL_33:
      if ( ++v19 >= v17 )
        goto LABEL_36;
    }
  }
  v22 = v19 - v6;
  v23 = v6 + cchCount2;
  *(_DWORD *)CharType = v19 - v6;
  v24 = v23;
  if ( (unsigned int)v23 >= v17 )
    goto LABEL_51;
  while ( 1 )
  {
    if ( v24 <= v17 - 2
      && *(_WORD *)(v18 + 2LL * v24) == 0xDB40
      && (unsigned __int16)(*(_WORD *)(v18 + 2LL * (v24 + 1)) + 8960) <= 0xEFu )
    {
      goto LABEL_47;
    }
    if ( !v24 || v24 > v17 - 1 )
      break;
    if ( *(_WORD *)(v18 + 2LL * (v24 - 1)) != 0xDB40 )
      goto LABEL_46;
    v25 = *(_WORD *)(v18 + 2LL * v24);
    if ( v25 < 0xDD00u )
      goto LABEL_46;
    if ( v25 > 0xDDEFu )
      break;
LABEL_47:
    if ( ++v24 >= v17 )
      goto LABEL_50;
  }
  if ( v24 > v17 - 1 )
    goto LABEL_50;
LABEL_46:
  v26 = *(_WORD *)(v18 + 2LL * v24);
  if ( (unsigned __int16)(v26 - SrcStr[0]) <= 2u || v26 == 6586 )
    goto LABEL_47;
LABEL_50:
  v22 = *(_DWORD *)CharType;
  v12 = this;
  LODWORD(v9) = a3;
  v6 = a6;
  v11 = a2;
LABEL_51:
  if ( v22 >= (unsigned int)v9 )
  {
    v7 = 1;
    goto LABEL_55;
  }
  v27 = v24 - v23;
  if ( !v22 )
  {
    if ( !v27 )
      goto LABEL_54;
    pv = 0;
    v66 = 0;
    v67 = 0;
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
           (__int64)&pv,
           v27 + (unsigned int)v9);
    if ( v8 < 0
      || (v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                 (__int64)&pv,
                 a4,
                 (unsigned int)v9),
          v8 < 0)
      || (v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                 (__int64)&pv,
                 (_WORD *)(*((_QWORD *)v12 + 4) + 2 * v23),
                 v27),
          v8 < 0) )
    {
      v52 = pv;
    }
    else
    {
      v53 = (__int64 *)*((_QWORD *)v12 + 2);
      v52 = pv;
      v54 = v66;
      v55 = *v53;
      if ( v11 )
      {
        if ( v66 == -1 )
        {
          if ( pv )
          {
            v54 = -1;
            do
              ++v54;
            while ( *((_WORD *)pv + v54) );
          }
          else
          {
            v54 = 0;
          }
        }
        v8 = (*(__int64 (__fastcall **)(__int64 *, __int64, LPVOID, _QWORD, unsigned int))(v55 + 32))(
               v53,
               v54,
               pv,
               v27 + cchCount2,
               v6);
      }
      else
      {
        if ( v66 == -1 )
        {
          if ( pv )
          {
            v54 = -1;
            do
              ++v54;
            while ( *((_WORD *)pv + v54) );
          }
          else
          {
            v54 = 0;
          }
        }
        v8 = (*(__int64 (__fastcall **)(__int64 *, __int64, LPVOID, _QWORD, unsigned int))(v55 + 24))(
               v53,
               v54,
               pv,
               v27 + cchCount2,
               v6);
      }
    }
    v62 = 1;
    if ( v52 )
    {
      CoTaskMemFree_0(v52);
LABEL_54:
      v7 = v62;
LABEL_55:
      v10 = a4;
      goto LABEL_56;
    }
LABEL_138:
    v7 = 1;
    goto LABEL_55;
  }
  if ( v27 )
  {
    v56 = (__int64 *)*((_QWORD *)v12 + 2);
    v57 = v27 - v22;
    v58 = *v56;
    v59 = v18 + 2LL * v19;
    v60 = v57 + (unsigned int)v9;
    if ( v11 )
      v61 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, unsigned int))(v58 + 32))(
              v56,
              v60,
              v59,
              v60,
              v19);
    else
      v61 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, unsigned int))(v58 + 24))(
              v56,
              v60,
              v59,
              v60,
              v19);
    v8 = v61;
    v7 = 1;
    goto LABEL_55;
  }
  LODWORD(v9) = v9 - v22;
  v7 = v62;
  v10 = &a4[v22];
LABEL_56:
  if ( v8 < 0 || v7 )
    return (unsigned int)v8;
  v28 = (__int64 *)*((_QWORD *)v12 + 2);
  v29 = *v28;
  if ( v11 )
    return (*(__int64 (__fastcall **)(__int64 *, _QWORD, const unsigned __int16 *, _QWORD, unsigned int))(v29 + 32))(
             v28,
             (unsigned int)v9,
             v10,
             (unsigned int)cchCount2,
             v6);
  else
    return (*(__int64 (__fastcall **)(__int64 *, _QWORD, const unsigned __int16 *, _QWORD, unsigned int))(v29 + 24))(
             v28,
             (unsigned int)v9,
             v10,
             (unsigned int)cchCount2,
             v6);
}

```

## disassembly

```asm
0x180039ec0  mov     [rsp-40h+lpString1], r9
0x180039ec5  mov     [rsp-40h+arg_10], r8d
0x180039eca  mov     [rsp-40h+arg_8], dl
0x180039ece  mov     [rsp-40h+arg_0], rcx
0x180039ed3  push    rbp
0x180039ed4  push    rbx
0x180039ed5  push    rsi
0x180039ed6  push    rdi
0x180039ed7  push    r12
0x180039ed9  push    r13
0x180039edb  push    r14
0x180039edd  push    r15
0x180039edf  mov     rbp, rsp
0x180039ee2  sub     rsp, 68h
0x180039ee6  mov     r13d, [rbp+arg_28]
0x180039eea  xor     dil, dil
0x180039eed  xor     r15d, r15d
0x180039ef0  mov     r14d, r8d
0x180039ef3  mov     [rbp+var_38], dil
0x180039ef7  mov     rbx, r9
0x180039efa  movzx   r12d, dl
0x180039efe  mov     rsi, rcx
0x180039f01  cmp     r8d, 3
0x180039f05  jb      short loc_180039F12
0x180039f07  cmp     word ptr [r9], 4Eh ; 'N'
0x180039f0c  jz      loc_18003A2A2
0x180039f12  test    r12b, r12b
0x180039f15  jz      loc_180039FBF
0x180039f1b  cmp     r14d, 2
0x180039f1f  jb      loc_180039FC9
0x180039f25  mov     r8, [rcx+20h]
0x180039f29  movzx   edx, word ptr [r8+r13*2]
0x180039f2e  cmp     dx, 2Eh ; '.'
0x180039f32  jz      short loc_180039F62
0x180039f34  cmp     dx, 2Ch ; ','
0x180039f38  jz      short loc_180039F62
0x180039f3a  mov     eax, 0B7h
0x180039f3f  cmp     dx, ax
0x180039f42  jz      short loc_180039F62
0x180039f44  mov     eax, 0FF0Eh
0x180039f49  cmp     dx, ax
0x180039f4c  jz      short loc_180039F62
0x180039f4e  mov     eax, 9EDEh
0x180039f53  cmp     dx, ax
0x180039f56  jz      short loc_180039F62
0x180039f58  mov     eax, 70B9h
0x180039f5d  cmp     dx, ax
0x180039f60  jnz     short loc_180039FC9
0x180039f62  test    r13d, r13d
0x180039f65  jz      short loc_180039F79
0x180039f67  lea     eax, [r13-1]
0x180039f6b  movzx   ecx, word ptr [r8+rax*2]; unsigned __int16
0x180039f70  call    ?IsSpace@@YA_NG@Z; IsSpace(ushort)
0x180039f75  test    al, al
0x180039f77  jz      short loc_180039FC9
0x180039f79  mov     rdi, [rbp+lpString1]
0x180039f7d  mov     ebx, 1
0x180039f82  cmp     ebx, r14d
0x180039f85  jb      loc_18003A92B
0x180039f8b  mov     rcx, [rsi+10h]
0x180039f8f  lea     edx, [r14-1]
0x180039f93  mov     rbx, [rbp+lpString1]
0x180039f97  mov     r9d, [rbp+cchCount2]
0x180039f9b  mov     [rsp+68h+bIgnoreCase], r13d
0x180039fa0  mov     rax, [rcx]
0x180039fa3  lea     r8, [rbx+2]
0x180039fa7  mov     rax, [rax+20h]
0x180039fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039fb0  mov     dil, 1
0x180039fb3  mov     r15d, eax
0x180039fb6  mov     [rbp+var_38], dil
0x180039fba  jmp     loc_18003A3DC
0x180039fbf  cmp     r14d, 5
0x180039fc3  jnb     loc_18003A3ED
0x180039fc9  mov     edx, [rsi+38h]
0x180039fcc  cmp     edx, 41Eh
0x180039fd2  jz      loc_18003A855
0x180039fd8  lea     eax, [rdx-404h]
0x180039fde  test    eax, 0FFFFE7FFh
0x180039fe3  jz      loc_18003A230
0x180039fe9  lea     eax, [rdx-804h]
0x180039fef  test    eax, 0FFFFFBFFh
0x180039ff4  jz      loc_18003A563
0x180039ffa  cmp     edx, 0C04h
0x18003a000  jz      loc_18003A574
0x18003a006  mov     rbx, [rbp+lpString1]
0x18003a00a  movzx   eax, word ptr [rsi+38h]
0x18003a00e  mov     ecx, 3FFh
0x18003a013  and     ax, cx
0x18003a016  cmp     ax, 1
0x18003a01a  jz      loc_18003A6D3
0x18003a020  mov     r10d, [rsi+28h]
0x18003a024  mov     r11d, 19B5h
0x18003a02a  mov     r9, [rsi+20h]
0x18003a02e  mov     edx, r13d
0x18003a031  mov     dword ptr [rbp+SrcStr], r11d
0x18003a035  mov     edi, 0EFh
0x18003a03a  mov     ebx, 19BAh
0x18003a03f  cmp     r13d, r10d
0x18003a042  jnb     loc_18003A0D2
0x18003a048  lea     r8d, [r10-2]
0x18003a04c  mov     r13d, 0DB40h
0x18003a052  mov     r12d, 0DD00h
0x18003a058  mov     r14d, 0DDEFh
0x18003a05e  xchg    ax, ax
0x18003a060  cmp     edx, r8d
0x18003a063  ja      short loc_18003A072
0x18003a065  mov     eax, edx
0x18003a067  cmp     [r9+rax*2], r13w
0x18003a06c  jz      loc_18003A1F9
0x18003a072  test    edx, edx
0x18003a074  jz      short loc_18003A09B
0x18003a076  lea     eax, [r10-1]
0x18003a07a  cmp     edx, eax
0x18003a07c  ja      short loc_18003A09B
0x18003a07e  lea     eax, [rdx-1]
0x18003a081  cmp     [r9+rax*2], r13w
0x18003a086  jnz     short loc_18003A0A3
0x18003a088  mov     eax, edx
0x18003a08a  movzx   ecx, word ptr [r9+rax*2]
0x18003a08f  cmp     r12w, cx
0x18003a093  ja      short loc_18003A0A3
0x18003a095  cmp     cx, r14w
0x18003a099  jbe     short loc_18003A0B7
0x18003a09b  lea     eax, [r10-1]
0x18003a09f  cmp     edx, eax
0x18003a0a1  ja      short loc_18003A0C5
0x18003a0a3  mov     eax, edx
0x18003a0a5  movzx   ecx, word ptr [r9+rax*2]
0x18003a0aa  movzx   eax, cx
0x18003a0ad  sub     ax, r11w
0x18003a0b1  cmp     ax, 2
0x18003a0b5  ja      short loc_18003A0C0
0x18003a0b7  inc     edx
0x18003a0b9  cmp     edx, r10d
0x18003a0bc  jb      short loc_18003A060
0x18003a0be  jmp     short loc_18003A0C5
0x18003a0c0  cmp     cx, bx
0x18003a0c3  jz      short loc_18003A0B7
0x18003a0c5  mov     r14d, [rbp+arg_10]
0x18003a0c9  mov     r13d, [rbp+arg_28]
0x18003a0cd  movzx   r12d, [rbp+arg_8]
0x18003a0d2  mov     edi, [rbp+cchCount2]
0x18003a0d5  mov     r11d, edx
0x18003a0d8  sub     r11d, r13d
0x18003a0db  add     edi, r13d
0x18003a0de  mov     dword ptr [rbp+CharType], r11d
0x18003a0e2  mov     ebx, edi
0x18003a0e4  cmp     edi, r10d
0x18003a0e7  jnb     loc_18003A18A
0x18003a0ed  lea     r8d, [r10-2]
0x18003a0f1  mov     esi, 0DD00h
0x18003a0f6  mov     r13d, 0DB40h
0x18003a0fc  mov     r12d, 19BAh
0x18003a102  mov     r14d, 0EFh
0x18003a108  mov     r11d, 0DDEFh
0x18003a10e  xchg    ax, ax
0x18003a110  cmp     ebx, r8d
0x18003a113  ja      short loc_18003A122
0x18003a115  mov     eax, ebx
0x18003a117  cmp     [r9+rax*2], r13w
0x18003a11c  jz      loc_18003A214
0x18003a122  test    ebx, ebx
0x18003a124  jz      short loc_18003A14A
0x18003a126  lea     eax, [r10-1]
0x18003a12a  cmp     ebx, eax
0x18003a12c  ja      short loc_18003A14A
0x18003a12e  lea     eax, [rbx-1]
0x18003a131  cmp     [r9+rax*2], r13w
0x18003a136  jnz     short loc_18003A152
0x18003a138  mov     eax, ebx
0x18003a13a  movzx   ecx, word ptr [r9+rax*2]
0x18003a13f  cmp     si, cx
0x18003a142  ja      short loc_18003A152
0x18003a144  cmp     cx, r11w
0x18003a148  jbe     short loc_18003A166
0x18003a14a  lea     eax, [r10-1]
0x18003a14e  cmp     ebx, eax
0x18003a150  ja      short loc_18003A175
0x18003a152  mov     eax, ebx
0x18003a154  movzx   ecx, word ptr [r9+rax*2]
0x18003a159  movzx   eax, cx
0x18003a15c  sub     ax, [rbp+SrcStr]
0x18003a160  cmp     ax, 2
0x18003a164  ja      short loc_18003A16F
0x18003a166  inc     ebx
0x18003a168  cmp     ebx, r10d
0x18003a16b  jb      short loc_18003A110
0x18003a16d  jmp     short loc_18003A175
0x18003a16f  cmp     cx, r12w
0x18003a173  jz      short loc_18003A166
0x18003a175  mov     r11d, dword ptr [rbp+CharType]
0x18003a179  mov     rsi, [rbp+arg_0]
0x18003a17d  mov     r14d, [rbp+arg_10]
0x18003a181  mov     r13d, [rbp+arg_28]
0x18003a185  movzx   r12d, [rbp+arg_8]
0x18003a18a  cmp     r11d, r14d
0x18003a18d  jnb     loc_18003A55B
0x18003a193  sub     ebx, edi
0x18003a195  test    r11d, r11d
0x18003a198  jnz     loc_18003AB48
0x18003a19e  test    ebx, ebx
0x18003a1a0  jnz     loc_18003A9CF
0x18003a1a6  movzx   edi, [rbp+var_38]
0x18003a1aa  mov     rbx, [rbp+lpString1]
0x18003a1ae  test    r15d, r15d
0x18003a1b1  js      loc_18003A3E5
0x18003a1b7  test    dil, dil
0x18003a1ba  jnz     loc_18003A3E5
0x18003a1c0  mov     rcx, [rsi+10h]
0x18003a1c4  mov     r8, rbx
0x18003a1c7  mov     r9d, [rbp+cchCount2]
0x18003a1cb  mov     edx, r14d
0x18003a1ce  mov     [rsp+68h+bIgnoreCase], r13d
0x18003a1d3  mov     rax, [rcx]
0x18003a1d6  test    r12b, r12b
0x18003a1d9  jnz     loc_18003A5CD
0x18003a1df  mov     rax, [rax+18h]
0x18003a1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1e8  add     rsp, 68h
0x18003a1ec  pop     r15
0x18003a1ee  pop     r14
0x18003a1f0  pop     r13
0x18003a1f2  pop     r12
0x18003a1f4  pop     rdi
0x18003a1f5  pop     rsi
0x18003a1f6  pop     rbx
0x18003a1f7  pop     rbp
0x18003a1f8  retn
0x18003a1f9  lea     ecx, [rdx+1]
0x18003a1fc  mov     eax, 2300h
0x18003a201  add     ax, [r9+rcx*2]
0x18003a206  cmp     ax, di
0x18003a209  jbe     loc_18003A0B7
0x18003a20f  jmp     loc_18003A072
0x18003a214  lea     ecx, [rbx+1]
0x18003a217  mov     eax, 2300h
0x18003a21c  add     ax, [r9+rcx*2]
0x18003a221  cmp     ax, r14w
0x18003a225  jbe     loc_18003A166
0x18003a22b  jmp     loc_18003A122
0x18003a230  cmp     edx, 1C04h
0x18003a236  jz      loc_180039FE9
0x18003a23c  test    r14d, r14d
0x18003a23f  jz      loc_180039FE9
0x18003a245  mov     eax, 5EA6h
0x18003a24a  cmp     [rbx], ax
0x18003a24d  jnz     loc_180039FE9
0x18003a253  test    r13d, r13d
0x18003a256  jz      loc_180039FE9
0x18003a25c  mov     rax, [rsi+20h]
0x18003a260  lea     r8d, [r13-1]
0x18003a264  mov     r9d, 5E74h
0x18003a26a  cmp     [rax+r8*2], r9w
0x18003a26f  jnz     loc_180039FE9
0x18003a275  mov     rcx, [rsi+10h]
0x18003a279  mov     r9d, 2
0x18003a27f  mov     [rsp+68h+bIgnoreCase], r8d
0x18003a284  mov     edx, r9d
0x18003a287  lea     r8, qword_18009BA28
0x18003a28e  mov     rax, [rcx]
0x18003a291  mov     rax, [rax+20h]
0x18003a295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a29a  mov     r15d, eax
0x18003a29d  jmp     loc_18003A1AE
0x18003a2a2  cmp     word ptr [r9+2], 4Eh ; 'N'
0x18003a2a8  jnz     loc_180039F12
0x18003a2ae  mov     eax, [rbp+cchCount2]
0x18003a2b1  test    eax, eax
0x18003a2b3  jz      loc_180039F12
0x18003a2b9  dec     eax
0x18003a2bb  add     eax, r13d
0x18003a2be  cmp     eax, [rcx+28h]
0x18003a2c1  jnb     loc_180039F12
0x18003a2c7  mov     r8, [rcx+20h]
0x18003a2cb  mov     r11d, 0FF10h
0x18003a2d1  lea     rdx, [r8+rax*2]
0x18003a2d5  movzx   eax, word ptr [r8+rax*2]
0x18003a2da  cmp     ax, 30h ; '0'
0x18003a2de  jnz     loc_18003A6C4
0x18003a2e4  mov     rax, [rbp+lpString1]
0x18003a2e8  lea     ecx, [r14-1]
0x18003a2ec  xor     edi, edi
0x18003a2ee  xor     r10d, r10d
0x18003a2f1  xor     bl, bl
0x18003a2f3  lea     r9, [rax+rcx*2]
0x18003a2f7  cmp     r9, rax
0x18003a2fa  jb      short loc_18003A359
0x18003a2fc  cmp     rdx, r8
0x18003a2ff  jb      short loc_18003A359
0x18003a301  movzx   eax, word ptr [r9]
0x18003a305  cmp     ax, 30h ; '0'
0x18003a309  jz      loc_18003A6A3
0x18003a30f  cmp     ax, r11w
0x18003a313  jz      loc_18003A6A3
0x18003a319  cmp     ax, r11w
0x18003a31d  jz      short loc_18003A33C
0x18003a31f  cmp     ax, 30h ; '0'
0x18003a323  jz      short loc_18003A33C
0x18003a325  movzx   ecx, word ptr [rdx]
  ... truncated ...
```
