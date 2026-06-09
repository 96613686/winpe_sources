# CUrlConverter::IndexedVolumeIdUrlFromCurrentUrl(wchar_t const *,wchar_t *,uint)

- ea: `0x180028660`
- end: `0x180028f52`
- name: `?IndexedVolumeIdUrlFromCurrentUrl@CUrlConverter@@UEAAJPEB_WPEA_WI@Z`
- size: `2290`
- prototype: `int(CUrlConverter *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000f880`
- `0x180028660`
- `0x180028f58`
- `0x180029348`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isupper` at `0x180028db8`
- `api-ms-win-crt-private-l1-1-0!_o_isupper` at `0x180028db8`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800289ef`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180028ef6`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800289ef`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180028ef6`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180028dcd`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180028dcd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800286a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800286a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028a3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028a4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028a5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028ae8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028e1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028a3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028a4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028a5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028ae8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028e1d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028716`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028742`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028855`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028888`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800288b7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800288ea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028b2e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028b5d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028e6e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028ea4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028716`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028742`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028855`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028888`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800288b7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800288ea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028b2e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028b5d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028e6e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028ea4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028d68`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028d94`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028d68`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028d94`

## string_xrefs

- `0x180028815`: `onecoreuap\base\appmodel\search\common\volumeidurl\urlconverter.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CUrlConverter::IndexedVolumeIdUrlFromCurrentUrl(
        RTL_SRWLOCK *this,
        const wchar_t *a2,
        wchar_t *a3,
        unsigned int a4)
{
  unsigned __int64 v4; // r14
  unsigned int v7; // r8d
  __int64 v8; // rbx
  const wchar_t *v9; // rsi
  unsigned __int64 v10; // rax
  wchar_t v11; // ax
  __int64 v12; // rbx
  const wchar_t *v13; // rsi
  unsigned __int64 v14; // rax
  const wchar_t *v15; // rbx
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  wchar_t v18; // ax
  const wchar_t *v19; // rsi
  __int64 v20; // rcx
  const wchar_t *v21; // rax
  const wchar_t *v22; // rdx
  int v23; // eax
  unsigned int v24; // r12d
  wchar_t v25; // ax
  unsigned __int16 v26; // ax
  _QWORD *Ptr; // rdx
  _QWORD *v28; // rcx
  _QWORD *i; // r13
  int v31; // ecx
  wchar_t *v32; // rsi
  int v33; // edi
  wchar_t *v34; // rbx
  const wchar_t *v35; // rsi
  __int64 v36; // rax
  unsigned __int64 v37; // rax
  wchar_t *v38; // r11
  wchar_t v39; // ax
  unsigned __int64 v40; // rcx
  __int64 v41; // r10
  unsigned __int64 v42; // rdx
  wchar_t *v43; // r8
  WCHAR v44; // ax
  wchar_t *v45; // rcx
  unsigned __int64 v46; // rcx
  wchar_t *v47; // rax
  unsigned __int64 v48; // rax
  __int64 v49; // rcx
  unsigned __int64 v50; // rdx
  wchar_t *v51; // r8
  wchar_t v52; // ax
  int v53; // ebx
  wchar_t *v54; // rcx
  unsigned __int64 v55; // rcx
  wchar_t *v56; // rax
  unsigned __int64 v57; // r9
  wchar_t *v58; // rdx
  wchar_t v59; // ax
  wchar_t *v60; // rcx
  unsigned __int16 *v61; // rdi
  unsigned __int16 *v62; // rbx
  unsigned __int16 *v63; // rax
  char v64; // bl
  int v65; // eax
  __int64 v66; // rcx
  wint_t v67; // ax
  wint_t v68; // di
  unsigned __int64 v69; // rcx
  __int64 v70; // rax
  wchar_t v71; // ax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-68h]
  RTL_SRWLOCK *SRWLock; // [rsp+38h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = a4;
  *a3 = 0;
  SRWLock = this + 5;
  AcquireSRWLockExclusive(this + 5);
  CUrlConverter::_UpdateDirtyDriveLetters((CUrlConverter *)this);
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( (unsigned int)v8 >= 8 && CompareStringOrdinal(L"file:///", 8, a2, 8, 1) == 2 )
  {
    v9 = a2 + 8;
  }
  else
  {
    v9 = a2;
    if ( (unsigned int)v8 >= 5 && CompareStringOrdinal(L"file:", 5, a2, 5, 1) == 2 )
      v9 = a2 + 5;
  }
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  if ( v10 < 3 || (unsigned __int16)(*v9 - 97) > 0x19u && (unsigned __int16)(*v9 - 65) > 0x19u )
    goto LABEL_55;
  if ( v9[1] != 58 )
    goto LABEL_55;
  v11 = v9[2];
  if ( v11 != 47 && v11 != 92 )
    goto LABEL_55;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  if ( (unsigned int)v12 >= 8 && CompareStringOrdinal(L"file:///", 8, a2, 8, 1) == 2 )
  {
    v13 = a2 + 8;
  }
  else
  {
    v13 = a2;
    if ( (unsigned int)v12 >= 5 && CompareStringOrdinal(L"file:", 5, a2, 5, 1) == 2 )
      v13 = a2 + 5;
  }
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  if ( v14 >= 3 && ((unsigned __int16)(*v13 - 97) <= 0x19u || (unsigned __int16)(*v13 - 65) <= 0x19u) && v13[1] == 58 )
  {
    v18 = v13[2];
    if ( v18 == 47 || v18 == 92 )
    {
      v19 = v13 + 3;
      if ( v19 )
      {
        v20 = 0x7FFF;
        v21 = v19;
        while ( *v21 )
        {
          ++v21;
          if ( !--v20 )
          {
            v22 = 0;
            v23 = -2147024809;
            goto LABEL_52;
          }
        }
        v22 = (const wchar_t *)(0x7FFF - v20);
        v23 = 0;
LABEL_52:
        if ( v23 >= 0 && (unsigned __int64)v22 >= 0x26 && _MatchesFormat(v19, v22, v7) )
        {
LABEL_55:
          if ( SRWLock )
            ReleaseSRWLockExclusive(SRWLock);
          return 2147942487LL;
        }
      }
    }
  }
  v15 = a2;
  v16 = -1;
  do
    ++v16;
  while ( a2[v16] );
  if ( (unsigned int)v16 >= 8 )
  {
    if ( CompareStringOrdinal(L"file:///", 8, a2, 8, 1) == 2 )
    {
      v15 = a2 + 8;
      goto LABEL_29;
    }
  }
  else if ( (unsigned int)v16 < 5 )
  {
    goto LABEL_29;
  }
  if ( CompareStringOrdinal(L"file:", 5, a2, 5, 1) == 2 )
    v15 = a2 + 5;
LABEL_29:
  v17 = -1;
  do
    ++v17;
  while ( v15[v17] );
  if ( v17 >= 3
    && ((v24 = *v15, (unsigned __int16)(v24 - 97) <= 0x19u) || (unsigned __int16)(v24 - 65) <= 0x19u)
    && v15[1] == 58
    && ((v25 = v15[2], v25 == 47) || v25 == 92)
    && (_WORD)v24 )
  {
    v26 = _o_towlower((unsigned __int16)v24);
    Ptr = this[6].Ptr;
    v28 = (_QWORD *)Ptr[1];
    for ( i = Ptr; !*((_BYTE *)v28 + 25); v28 = (_QWORD *)*v28 )
    {
      if ( *((_WORD *)v28 + 16) < v26 )
        v28 += 2;
      else
        i = v28;
    }
    if ( !*((_BYTE *)i + 25) && v26 >= *((_WORD *)i + 16) && i != Ptr )
    {
      v34 = (wchar_t *)i[6];
      v35 = a2;
      v36 = -1;
      do
        ++v36;
      while ( a2[v36] );
      if ( (unsigned int)v36 >= 8 )
      {
        if ( CompareStringOrdinal(L"file:///", 8, a2, 8, 1) == 2 )
        {
          v35 = a2 + 8;
          goto LABEL_84;
        }
      }
      else if ( (unsigned int)v36 < 5 )
      {
        goto LABEL_84;
      }
      if ( CompareStringOrdinal(L"file:", 5, a2, 5, 1) == 2 )
        v35 = a2 + 5;
LABEL_84:
      v37 = -1;
      do
        ++v37;
      while ( v35[v37] );
      if ( v37 >= 3
        && ((unsigned __int16)(*v35 - 97) <= 0x19u || (unsigned __int16)(*v35 - 65) <= 0x19u)
        && v35[1] == 58 )
      {
        v38 = (wchar_t *)(v35 + 2);
        v39 = v35[2];
        if ( v39 == 47 || v39 == 92 )
        {
          if ( (_DWORD)v4 )
          {
            if ( v4 > 0x7FFFFFFF )
            {
              v31 = -2147024809;
              v32 = a3;
              *a3 = 0;
            }
            else
            {
              v40 = v35 - a2 + 3;
              v41 = 2147483646;
              v32 = a3;
              if ( v40 > 0x7FFFFFFE )
              {
                v31 = -2147024809;
                *a3 = 0;
              }
              else
              {
                v42 = v4;
                v43 = a3;
                do
                {
                  if ( !v40 )
                    break;
                  v44 = *a2;
                  if ( !*a2 )
                    break;
                  ++a2;
                  *v43++ = v44;
                  --v40;
                  --v42;
                }
                while ( v42 );
                v45 = v43 - 1;
                if ( v42 )
                  v45 = v43;
                *v45 = 0;
                v33 = -2147024774;
                v31 = -2147024774;
                if ( v42 )
                {
                  v46 = v4;
                  v47 = a3;
                  do
                  {
                    if ( !*v47 )
                      break;
                    ++v47;
                    --v46;
                  }
                  while ( v46 );
                  if ( v46 )
                  {
                    v48 = v4 - v46;
                    v49 = 2147483646;
                    v50 = v4 - v48;
                    v51 = &a3[v48];
                    if ( v4 != v48 )
                    {
                      do
                      {
                        if ( !v49 )
                          break;
                        v52 = *v34;
                        if ( !*v34 )
                          break;
                        ++v34;
                        *v51++ = v52;
                        --v49;
                        --v50;
                      }
                      while ( v50 );
                    }
                    v53 = -2147024774;
                    if ( v50 )
                      v53 = 0;
                    v54 = v51 - 1;
                    if ( v50 )
                      v54 = v51;
                    *v54 = 0;
                    if ( v50 )
                    {
                      v55 = v4;
                      v56 = a3;
                      do
                      {
                        if ( !*v56 )
                          break;
                        ++v56;
                        --v55;
                      }
                      while ( v55 );
                      if ( v55 )
                      {
                        v57 = v55;
                        v58 = &a3[v4 - v55];
                        do
                        {
                          if ( !v41 )
                            break;
                          v59 = *v38;
                          if ( !*v38 )
                            break;
                          ++v38;
                          *v58++ = v59;
                          --v41;
                          --v57;
                        }
                        while ( v57 );
                        v60 = v58 - 1;
                        if ( v57 )
                          v60 = v58;
                        *v60 = 0;
                        if ( v57 )
                          v33 = 0;
                      }
                      else
                      {
                        v33 = -2147024809;
                      }
LABEL_136:
                      if ( v33 >= 0 )
                      {
                        v61 = (unsigned __int16 *)this[8].Ptr;
                        v62 = (unsigned __int16 *)*((_QWORD *)v61 + 1);
                        if ( *((_BYTE *)v62 + 25) )
                        {
                          v63 = (unsigned __int16 *)this[8].Ptr;
                        }
                        else
                        {
                          do
                          {
                            if ( lstrcmpW(*((LPCWSTR *)v62 + 5), (LPCWSTR)i[6]) < 0 )
                              v62 += 8;
                            else
                              v61 = v62;
                            v62 = *(unsigned __int16 **)v62;
                          }
                          while ( !*((_BYTE *)v62 + 25) );
                          v63 = (unsigned __int16 *)this[8].Ptr;
                        }
                        if ( !*((_BYTE *)v61 + 25) )
                        {
                          if ( lstrcmpW((LPCWSTR)i[6], *((LPCWSTR *)v61 + 5)) >= 0 )
                            goto LABEL_146;
                          v63 = (unsigned __int16 *)this[8].Ptr;
                        }
                        v61 = v63;
LABEL_146:
                        if ( v61 == this[8].Ptr )
                        {
                          v64 = 0;
LABEL_155:
                          if ( this != (RTL_SRWLOCK *)-40LL )
                            ReleaseSRWLockExclusive(this + 5);
                          return v64 == 0;
                        }
                        v64 = 1;
                        v65 = _o_isupper(v24);
                        v66 = v61[224];
                        if ( v65 )
                          v67 = towupper(v66);
                        else
                          v67 = _o_towlower(v66);
                        v68 = v67;
                        v69 = -1;
                        v70 = -1;
                        do
                          ++v70;
                        while ( v32[v70] );
                        if ( (unsigned int)v70 >= 8 )
                        {
                          if ( CompareStringOrdinal(L"file:///", 8, v32, 8, 1) == 2 )
                          {
                            v32 += 8;
LABEL_163:
                            v69 = -1;
                            do
LABEL_153:
                              ++v69;
                            while ( v32[v69] );
                            if ( v69 >= 3
                              && ((unsigned __int16)(*v32 - 97) <= 0x19u || (unsigned __int16)(*v32 - 65) <= 0x19u)
                              && v32[1] == 58 )
                            {
                              v71 = v32[2];
                              if ( v71 == 47 || v71 == 92 )
                                *v32 = v68;
                            }
                            goto LABEL_155;
                          }
                        }
                        else if ( (unsigned int)v70 < 5 )
                        {
                          goto LABEL_153;
                        }
                        if ( CompareStringOrdinal(L"file:", 5, v32, 5, 1) == 2 )
                          v32 += 5;
                        goto LABEL_163;
                      }
                      goto LABEL_88;
                    }
                    v33 = v53;
                  }
                  else
                  {
                    v33 = -2147024809;
                  }
LABEL_88:
                  if ( SRWLock )
                    ReleaseSRWLockExclusive(SRWLock);
                  return (unsigned int)v33;
                }
              }
            }
          }
          else
          {
            v31 = -2147024809;
            v32 = a3;
          }
          v33 = v31;
          goto LABEL_136;
        }
      }
      v33 = -2147467259;
      goto LABEL_88;
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 2147942415LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\volumeidurl\\urlconverter.cxx",
      (const char *)0x80004005LL,
      bIgnoreCase);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180028660  mov     [rsp+arg_8], rbx
0x180028665  mov     [rsp+arg_18], rsi
0x18002866a  mov     [rsp+lpString2], r8
0x18002866f  mov     [rsp+arg_0], rcx
0x180028674  push    rdi
0x180028675  push    r12
0x180028677  push    r13
0x180028679  push    r14
0x18002867b  push    r15
0x18002867d  sub     rsp, 60h
0x180028681  mov     r14d, r9d
0x180028684  mov     rdi, rdx
0x180028687  mov     r13, rcx
0x18002868a  mov     [rsp+88h+var_54], 0
0x180028692  xor     eax, eax
0x180028694  mov     [r8], ax
0x180028698  mov     [rsp+88h+var_58], al
0x18002869c  lea     rbx, [rcx+28h]
0x1800286a0  mov     [rsp+88h+SRWLock], rbx
0x1800286a5  mov     rcx, rbx; SRWLock
0x1800286a8  call    cs:__imp_AcquireSRWLockExclusive
0x1800286ae  mov     [rsp+88h+var_48], rbx
0x1800286b3  mov     rcx, r13; this
0x1800286b6  call    ?_UpdateDirtyDriveLetters@CUrlConverter@@AEAAXXZ; CUrlConverter::_UpdateDirtyDriveLetters(void)
0x1800286bb  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800286c2  mov     rbx, r12
0x1800286c5  inc     rbx
0x1800286c8  cmp     word ptr [rdi+rbx*2], 0
0x1800286cd  jnz     short loc_1800286C5
0x1800286cf  cmp     ebx, 8
0x1800286d2  jnb     short loc_1800286FB
0x1800286d4  mov     rsi, rdi
0x1800286d7  cmp     ebx, 5
0x1800286da  jnb     short loc_180028727
0x1800286dc  mov     rax, r12
0x1800286df  nop
0x1800286e0  inc     rax
0x1800286e3  cmp     word ptr [rsi+rax*2], 0
0x1800286e8  jnz     short loc_1800286E0
0x1800286ea  cmp     rax, 3
0x1800286ee  jnb     short loc_180028753
0x1800286f0  mov     r15d, 80070057h
0x1800286f6  jmp     loc_180028991
0x1800286fb  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x180028703  mov     r9d, 8; cchCount2
0x180028709  mov     r8, rdi; lpString2
0x18002870c  mov     edx, r9d; cchCount1
0x18002870f  lea     rcx, String1; "file:///"
0x180028716  call    cs:__imp_CompareStringOrdinal
0x18002871c  cmp     eax, 2
0x18002871f  jnz     short loc_1800286D4
0x180028721  lea     rsi, [rdi+10h]
0x180028725  jmp     short loc_1800286DC
0x180028727  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x18002872f  mov     r9d, 5; cchCount2
0x180028735  mov     r8, rdi; lpString2
0x180028738  mov     edx, r9d; cchCount1
0x18002873b  lea     rcx, aFile_8; "file:"
0x180028742  call    cs:__imp_CompareStringOrdinal
0x180028748  cmp     eax, 2
0x18002874b  jnz     short loc_1800286DC
0x18002874d  lea     rsi, [rdi+0Ah]
0x180028751  jmp     short loc_1800286DC
0x180028753  movzx   ecx, word ptr [rsi]
0x180028756  lea     eax, [rcx-61h]
0x180028759  cmp     ax, 19h
0x18002875d  jbe     short loc_180028769
0x18002875f  sub     cx, 41h ; 'A'
0x180028763  cmp     cx, 19h
0x180028767  ja      short loc_1800286F0
0x180028769  cmp     word ptr [rsi+2], 3Ah ; ':'
0x18002876e  jnz     short loc_1800286F0
0x180028770  movzx   eax, word ptr [rsi+4]
0x180028774  cmp     ax, 2Fh ; '/'
0x180028778  jz      short loc_180028784
0x18002877a  cmp     ax, 5Ch ; '\'
0x18002877e  jnz     loc_1800286F0
0x180028784  mov     rbx, r12
0x180028787  nop     word ptr [rax+rax+00000000h]
0x180028790  inc     rbx
0x180028793  cmp     word ptr [rdi+rbx*2], 0
0x180028798  jnz     short loc_180028790
0x18002879a  cmp     ebx, 8
0x18002879d  jnb     loc_18002883A
0x1800287a3  mov     rsi, rdi
0x1800287a6  cmp     ebx, 5
0x1800287a9  jnb     loc_18002889C
0x1800287af  mov     rax, r12
0x1800287b2  inc     rax
0x1800287b5  cmp     word ptr [rsi+rax*2], 0
0x1800287ba  jnz     short loc_1800287B2
0x1800287bc  cmp     rax, 3
0x1800287c0  jnb     loc_180028902
0x1800287c6  mov     r15d, 80070057h
0x1800287cc  mov     rbx, rdi
0x1800287cf  mov     rax, r12
0x1800287d2  inc     rax
0x1800287d5  cmp     word ptr [rdi+rax*2], 0
0x1800287da  jnz     short loc_1800287D2
0x1800287dc  cmp     eax, 8
0x1800287df  jnb     loc_18002886D
0x1800287e5  cmp     eax, 5
0x1800287e8  jnb     loc_1800288CF
0x1800287ee  mov     rax, r12
0x1800287f1  inc     rax
0x1800287f4  cmp     word ptr [rbx+rax*2], 0
0x1800287f9  jnz     short loc_1800287F1
0x1800287fb  cmp     rax, 3
0x1800287ff  jnb     loc_1800289A4
0x180028805  mov     rcx, [rsp+88h]; this
0x18002880d  mov     edi, 80004005h
0x180028812  mov     r9d, edi; char *
0x180028815  lea     r8, aOnecoreuapBase_264; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002881c  mov     edx, 0D3h; void *
0x180028821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028826  nop
0x180028827  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x18002882c  test    rcx, rcx
0x18002882f  jnz     loc_180028A4D
0x180028835  jmp     loc_180028A53
0x18002883a  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x180028842  mov     r9d, 8; cchCount2
0x180028848  mov     r8, rdi; lpString2
0x18002884b  mov     edx, r9d; cchCount1
0x18002884e  lea     rcx, String1; "file:///"
0x180028855  call    cs:__imp_CompareStringOrdinal
0x18002885b  cmp     eax, 2
0x18002885e  jnz     loc_1800287A3
0x180028864  lea     rsi, [rdi+10h]
0x180028868  jmp     loc_1800287AF
0x18002886d  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x180028875  mov     r9d, 8; cchCount2
0x18002887b  mov     r8, rdi; lpString2
0x18002887e  mov     edx, r9d; cchCount1
0x180028881  lea     rcx, String1; "file:///"
0x180028888  call    cs:__imp_CompareStringOrdinal
0x18002888e  cmp     eax, 2
0x180028891  jnz     short loc_1800288CF
0x180028893  lea     rbx, [rdi+10h]
0x180028897  jmp     loc_1800287EE
0x18002889c  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x1800288a4  mov     r9d, 5; cchCount2
0x1800288aa  mov     r8, rdi; lpString2
0x1800288ad  mov     edx, r9d; cchCount1
0x1800288b0  lea     rcx, aFile_8; "file:"
0x1800288b7  call    cs:__imp_CompareStringOrdinal
0x1800288bd  cmp     eax, 2
0x1800288c0  jnz     loc_1800287AF
0x1800288c6  lea     rsi, [rdi+0Ah]
0x1800288ca  jmp     loc_1800287AF
0x1800288cf  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x1800288d7  mov     r9d, 5; cchCount2
0x1800288dd  mov     r8, rdi; lpString2
0x1800288e0  mov     edx, r9d; cchCount1
0x1800288e3  lea     rcx, aFile_8; "file:"
0x1800288ea  call    cs:__imp_CompareStringOrdinal
0x1800288f0  cmp     eax, 2
0x1800288f3  jnz     loc_1800287EE
0x1800288f9  lea     rbx, [rdi+0Ah]
0x1800288fd  jmp     loc_1800287EE
0x180028902  movzx   ecx, word ptr [rsi]
0x180028905  lea     eax, [rcx-61h]
0x180028908  cmp     ax, 19h
0x18002890c  jbe     short loc_18002891C
0x18002890e  sub     cx, 41h ; 'A'
0x180028912  cmp     cx, 19h
0x180028916  ja      loc_1800287C6
0x18002891c  cmp     word ptr [rsi+2], 3Ah ; ':'
0x180028921  jnz     loc_1800287C6
0x180028927  movzx   eax, word ptr [rsi+4]
0x18002892b  cmp     ax, 2Fh ; '/'
0x18002892f  jz      short loc_18002893B
0x180028931  cmp     ax, 5Ch ; '\'
0x180028935  jnz     loc_1800287C6
0x18002893b  add     rsi, 6
0x18002893f  jz      loc_1800287C6
0x180028945  mov     edx, 7FFFh
0x18002894a  mov     ecx, edx
0x18002894c  mov     rax, rsi
0x18002894f  nop
0x180028950  cmp     word ptr [rax], 0
0x180028954  jz      loc_180028A83
0x18002895a  add     rax, 2
0x18002895e  sub     rcx, 1
0x180028962  jnz     short loc_180028950
0x180028964  xor     edx, edx; wchar_t *
0x180028966  mov     r15d, 80070057h
0x18002896c  mov     eax, r15d
0x18002896f  test    eax, eax
0x180028971  js      loc_1800287CC
0x180028977  cmp     rdx, 26h ; '&'
0x18002897b  jb      loc_1800287CC
0x180028981  mov     rcx, rsi; wchar_t *
0x180028984  call    ?_MatchesFormat@@YA_NPEB_W0I@Z; _MatchesFormat(wchar_t const *,wchar_t const *,uint)
0x180028989  test    al, al
0x18002898b  jz      loc_1800287CC
0x180028991  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x180028996  test    rcx, rcx
0x180028999  jnz     loc_180028A5A
0x18002899f  jmp     loc_180028A60
0x1800289a4  movzx   r12d, word ptr [rbx]
0x1800289a8  lea     eax, [r12-61h]
0x1800289ad  cmp     ax, 19h
0x1800289b1  jbe     short loc_1800289C2
0x1800289b3  lea     eax, [r12-41h]
0x1800289b8  cmp     ax, 19h
0x1800289bc  ja      loc_180028805
0x1800289c2  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800289c7  jnz     loc_180028805
0x1800289cd  movzx   eax, word ptr [rbx+4]
0x1800289d1  cmp     ax, 2Fh ; '/'
0x1800289d5  jz      short loc_1800289E1
0x1800289d7  cmp     ax, 5Ch ; '\'
0x1800289db  jnz     loc_180028805
0x1800289e1  test    r12w, r12w
0x1800289e5  jz      loc_180028805
0x1800289eb  movzx   ecx, r12w
0x1800289ef  call    cs:__imp__o_towlower
0x1800289f5  mov     rdx, [r13+30h]
0x1800289f9  mov     rcx, [rdx+8]
0x1800289fd  xor     r8d, r8d
0x180028a00  mov     [rsp+88h+var_34], r8d
0x180028a05  mov     r13, rdx
0x180028a08  cmp     [rcx+19h], r8b
0x180028a0c  jnz     short loc_180028A26
0x180028a0e  xchg    ax, ax
0x180028a10  cmp     [rcx+20h], ax
0x180028a14  jb      loc_180028B0A
0x180028a1a  mov     r13, rcx
0x180028a1d  mov     rcx, [rcx]
0x180028a20  cmp     [rcx+19h], r8b
0x180028a24  jz      short loc_180028A10
0x180028a26  cmp     [r13+19h], r8b
0x180028a2a  jnz     short loc_180028A33
0x180028a2c  cmp     ax, [r13+20h]
0x180028a31  jnb     short loc_180028A93
0x180028a33  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x180028a38  test    rcx, rcx
0x180028a3b  jz      short loc_180028A43
0x180028a3d  call    cs:__imp_ReleaseSRWLockExclusive
0x180028a43  mov     eax, 8007000Fh
0x180028a48  jmp     loc_180028AF0
0x180028a4d  call    cs:__imp_ReleaseSRWLockExclusive
0x180028a53  mov     eax, edi
0x180028a55  jmp     loc_180028AF0
0x180028a5a  call    cs:__imp_ReleaseSRWLockExclusive
0x180028a60  mov     eax, r15d
0x180028a63  jmp     loc_180028AF0
0x180028a68  mov     ecx, r15d
0x180028a6b  test    r14d, r14d
0x180028a6e  jnz     loc_180028F04
0x180028a74  mov     rsi, [rsp+88h+lpString2]
0x180028a7c  mov     edi, ecx
0x180028a7e  jmp     loc_180028D38
0x180028a83  sub     rdx, rcx
0x180028a86  xor     eax, eax
0x180028a88  mov     r15d, 80070057h
0x180028a8e  jmp     loc_18002896F
0x180028a93  cmp     r13, rdx
0x180028a96  jz      short loc_180028A33
0x180028a98  mov     rbx, [r13+30h]
0x180028a9c  mov     rsi, rdi
0x180028a9f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028aa6  inc     rax
0x180028aa9  cmp     [rdi+rax*2], r8w
0x180028aae  jnz     short loc_180028AA6
0x180028ab0  cmp     eax, 8
0x180028ab3  jnb     short loc_180028B13
0x180028ab5  cmp     eax, 5
0x180028ab8  jnb     loc_180028B42
0x180028abe  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028ac5  inc     rax
0x180028ac8  cmp     word ptr [rsi+rax*2], 0
0x180028acd  jnz     short loc_180028AC5
0x180028acf  cmp     rax, 3
0x180028ad3  jnb     loc_180028B75
0x180028ad9  mov     edi, 80004005h
0x180028ade  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x180028ae3  test    rcx, rcx
0x180028ae6  jz      short loc_180028AEE
0x180028ae8  call    cs:__imp_ReleaseSRWLockExclusive
0x180028aee  mov     eax, edi
0x180028af0  lea     r11, [rsp+88h+var_28]
0x180028af5  mov     rbx, [r11+38h]
0x180028af9  mov     rsi, [r11+48h]
0x180028afd  mov     rsp, r11
0x180028b00  pop     r15
0x180028b02  pop     r14
0x180028b04  pop     r13
0x180028b06  pop     r12
0x180028b08  pop     rdi
0x180028b09  retn
0x180028b0a  add     rcx, 10h
0x180028b0e  jmp     loc_180028A1D
0x180028b13  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x180028b1b  mov     r9d, 8; cchCount2
0x180028b21  mov     r8, rdi; lpString2
0x180028b24  mov     edx, r9d; cchCount1
0x180028b27  lea     rcx, String1; "file:///"
0x180028b2e  call    cs:__imp_CompareStringOrdinal
  ... truncated ...
```
