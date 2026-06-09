# LookupSidInTable

- ea: `0x18001c000`
- end: `0x18001c882`
- name: `LookupSidInTable`
- size: `2178`
- prototype: `__int64 __usercall@<rax>(wchar_t *String1@<rcx>, PSID Sid2@<rdx>, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180019550`
- `0x180019ed0`
- `0x18001b630`
- `0x18001b744`
- `0x18001cfb8`
- `0x18001e38c`
- `0x18001f4ac`

## callees

- `0x18001c000`
- `0x18001c890`
- `0x18001ce40`
- `0x18001d86c`
- `0x18001d8c4`
- `0x18005e0d0`
- `0x180072042`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001c0da`
- `msvcrt!_wcsnicmp` at `0x18001c0fa`
- `msvcrt!_wcsnicmp` at `0x18001c11e`
- `msvcrt!_wcsnicmp` at `0x18001c13e`
- `msvcrt!_wcsnicmp` at `0x18001c1c3`
- `msvcrt!_wcsnicmp` at `0x18001c225`
- `msvcrt!_wcsnicmp` at `0x18001c5f5`
- `msvcrt!_wcsnicmp` at `0x18001c0da`
- `msvcrt!_wcsnicmp` at `0x18001c0fa`
- `msvcrt!_wcsnicmp` at `0x18001c11e`
- `msvcrt!_wcsnicmp` at `0x18001c13e`
- `msvcrt!_wcsnicmp` at `0x18001c1c3`
- `msvcrt!_wcsnicmp` at `0x18001c225`
- `msvcrt!_wcsnicmp` at `0x18001c5f5`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c3de`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c447`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c45f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c50c`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c692`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c848`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c3de`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c447`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c45f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c50c`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c692`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001c848`
- `ntdll!RtlEqualSid` at `0x18001c29a`
- `ntdll!RtlEqualSid` at `0x18001c6f5`
- `ntdll!RtlEqualSid` at `0x18001c29a`
- `ntdll!RtlEqualSid` at `0x18001c6f5`
- `ntdll!RtlLengthSid` at `0x18001c314`
- `ntdll!RtlLengthSid` at `0x18001c3a0`
- `ntdll!RtlLengthSid` at `0x18001c4dd`
- `ntdll!RtlLengthSid` at `0x18001c54e`
- `ntdll!RtlLengthSid` at `0x18001c66d`
- `ntdll!RtlLengthSid` at `0x18001c7fc`
- `ntdll!RtlLengthSid` at `0x18001c314`
- `ntdll!RtlLengthSid` at `0x18001c3a0`
- `ntdll!RtlLengthSid` at `0x18001c4dd`
- `ntdll!RtlLengthSid` at `0x18001c54e`
- `ntdll!RtlLengthSid` at `0x18001c66d`
- `ntdll!RtlLengthSid` at `0x18001c7fc`
- `ntdll!RtlValidSid` at `0x18001c2e3`
- `ntdll!RtlValidSid` at `0x18001c768`
- `ntdll!RtlValidSid` at `0x18001c2e3`
- `ntdll!RtlValidSid` at `0x18001c768`
- `ntdll!RtlSubAuthoritySid` at `0x18001c3f6`
- `ntdll!RtlSubAuthoritySid` at `0x18001c473`
- `ntdll!RtlSubAuthoritySid` at `0x18001c51f`
- `ntdll!RtlSubAuthoritySid` at `0x18001c6a5`
- `ntdll!RtlSubAuthoritySid` at `0x18001c85c`
- `ntdll!RtlSubAuthoritySid` at `0x18001c3f6`
- `ntdll!RtlSubAuthoritySid` at `0x18001c473`
- `ntdll!RtlSubAuthoritySid` at `0x18001c51f`
- `ntdll!RtlSubAuthoritySid` at `0x18001c6a5`
- `ntdll!RtlSubAuthoritySid` at `0x18001c85c`
- `KERNELBASE!LocalAlloc` at `0x18001c812`
- `KERNELBASE!LocalAlloc` at `0x18001c812`

## pseudocode

```c
__int64 *__fastcall LookupSidInTable(
        wchar_t *String1,
        PSID Sid2,
        _BYTE *a3,
        _BYTE *a4,
        __int64 a5,
        __int64 a6,
        PSID *a7)
{
  __int64 v7; // r14
  _BYTE *v9; // rbx
  PSID v10; // r15
  __int64 *result; // rax
  __int64 *v13; // r14
  unsigned int v14; // edi
  int v15; // ebp
  char v16; // si
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // r14d
  void *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rbx
  ULONG v27; // eax
  __int64 *v28; // rcx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 *v33; // rcx
  int v34; // eax
  ULONG v35; // eax
  __int64 v36; // rax
  PSID v37; // rcx
  PUCHAR v38; // rax
  PULONG v39; // rax
  PUCHAR v40; // rax
  ULONG v41; // eax
  PUCHAR v42; // rax
  PULONG v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  ULONG v48; // eax
  __int64 v49; // rax
  unsigned int i; // r14d
  __int64 v51; // rbx
  int v52; // eax
  int v53; // eax
  unsigned __int8 *v54; // rbx
  int v55; // eax
  _BYTE *v56; // r15
  ULONG v57; // eax
  PUCHAR v58; // rax
  PULONG v59; // rax
  __int64 *v60; // rbx
  ULONG v61; // edi
  HLOCAL v62; // rax
  PUCHAR v63; // rax
  __int64 v64; // [rsp+20h] [rbp-48h]
  int v65; // [rsp+20h] [rbp-48h]
  __int64 *v66; // [rsp+28h] [rbp-40h]
  __int64 v67; // [rsp+30h] [rbp-38h]
  char v68; // [rsp+70h] [rbp+8h]

  v9 = a3;
  v10 = Sid2;
  if ( __PAIR128__((unsigned __int64)String1, (unsigned __int64)Sid2) == 0 )
    return 0;
  v14 = 0;
  v67 = v7;
  v15 = 0;
  v66 = 0;
  HIDWORD(v64) = 0;
  *a7 = 0;
  if ( !String1 )
  {
    v16 = 1;
    v68 = 1;
    if ( *RtlSubAuthorityCountSid(Sid2) )
    {
      v40 = RtlSubAuthorityCountSid(v10);
      v18 = *RtlSubAuthoritySid(v10, (unsigned int)*v40 - 1);
      if ( (unsigned int)(v18 - 498) <= 0x1D )
      {
        v17 = 540016641;
        if ( _bittest((const int *)&v17, v18 - 498) )
        {
          v15 = 1;
          HIDWORD(v64) = v18 == 518;
        }
      }
    }
    goto LABEL_13;
  }
  v16 = 0;
  v68 = 0;
  if ( _wcsnicmp(String1, L"EA", 2u) )
  {
    if ( !_wcsnicmp(String1, L"SA", 2u) )
    {
      v15 = 1;
      HIDWORD(v64) = 1;
      goto LABEL_13;
    }
    if ( _wcsnicmp(String1, L"RO", 2u) && _wcsnicmp(String1, L"EK", 2u) )
      goto LABEL_13;
  }
  v15 = 1;
LABEL_13:
  if ( !a4 )
    goto LABEL_14;
  v20 = a5;
  for ( i = 0; i < 0xF; ++i )
  {
    v19 = i;
    v51 = 104LL * i;
    if ( v16 )
    {
      v52 = 0;
    }
    else
    {
      v53 = _wcsnicmp(String1, (const wchar_t *)(v51 + v20 + 2), *(unsigned int *)(v51 + v20 + 12));
      v20 = a5;
      if ( v53 )
        continue;
      v52 = 1;
      v19 = i;
    }
    v54 = (unsigned __int8 *)(v20 + v51);
    v65 = v52;
    v18 = *v54;
    if ( !(_BYTE)v18 || !*((_QWORD *)v54 + 2) )
    {
      v55 = *((_DWORD *)v54 + 7);
      if ( v55 )
      {
        if ( v55 != 7 || !a3 )
        {
          v14 = 0;
          break;
        }
        v56 = a3;
      }
      else
      {
        v56 = a4;
      }
      *((_QWORD *)v54 + 2) = v54 + 32;
      if ( v56[1] < 0xFu )
      {
        v57 = RtlLengthSid(v56);
        memcpy_0(*((void **)v54 + 2), v56, v57);
        ++*(_BYTE *)(*((_QWORD *)v54 + 2) + 1LL);
        v58 = RtlSubAuthorityCountSid(v56);
        v59 = RtlSubAuthoritySid(*((PSID *)v54 + 2), *v58);
        v20 = a5;
        v19 = i;
        v18 = 104LL * i;
        v17 = *(unsigned int *)(v18 + a5 + 24);
        LOBYTE(v18) = 1;
        *v59 = v17;
        *(_BYTE *)(104LL * i + a5) = 1;
      }
      v10 = Sid2;
      v52 = v65;
    }
    if ( v16 )
    {
      if ( (_BYTE)v18 == 1 )
      {
        v18 = *(_QWORD *)(104 * v19 + v20 + 16);
        if ( v18 )
        {
          if ( RtlEqualSid((PSID)v18, v10) )
            return (__int64 *)v54;
          v20 = a5;
        }
      }
    }
    else if ( v52 )
    {
      result = 0;
      if ( (_BYTE)v18 == 1 )
        return (__int64 *)v54;
      return result;
    }
    v14 = 0;
  }
  v9 = a3;
LABEL_14:
  v21 = 68;
  LOBYTE(v18) = 1;
  LODWORD(v64) = 68;
  InitializeSidLookupTable(v18, v17, v19, v20);
  if ( v15 && !v9 && !(_BYTE)a6 && (!RootDomInited || !RtlValidSid(RootDomSidBuf)) )
    SddlpGetRootDomainSid();
  while ( 2 )
  {
    if ( !v15 )
    {
      if ( a4 )
      {
        v23 = 104LL * v14;
        if ( !*(_DWORD *)((char *)&qword_1800AEDD0[3] + v23 + 4) )
          goto LABEL_29;
      }
    }
    v26 = &qword_1800AEDD0[13 * v14];
    if ( *(_BYTE *)v26 )
    {
      v22 = (void *)v26[2];
      if ( v22 )
      {
LABEL_19:
        if ( !v16 )
          goto LABEL_20;
        v10 = Sid2;
        if ( RtlEqualSid(Sid2, v22) )
          goto LABEL_5;
LABEL_28:
        v21 = v64;
        goto LABEL_29;
      }
    }
    if ( *((_DWORD *)v26 + 7) == 7 && v15 )
    {
      if ( a3 )
      {
        if ( a3[1] < 0xFu )
        {
          EnterWaitSddlSidLookup();
          v41 = RtlLengthSid(a3);
          memcpy_0((void *)v26[2], a3, v41);
          v28 = (__int64 *)a3;
LABEL_66:
          ++*(_BYTE *)(v26[2] + 1);
          v42 = RtlSubAuthorityCountSid(v28);
          v43 = RtlSubAuthoritySid((PSID)v26[2], *v42);
          v44 = *((unsigned int *)v26 + 6);
          *v43 = v44;
          *(_BYTE *)v26 = 1;
          LeaveWaitSddlSidLookup(v44, v45, v46, v47, v64, v66, v67);
        }
      }
      else if ( !(_BYTE)a6 && RootDomInited && RtlValidSid(RootDomSidBuf) && (!*(_BYTE *)v26 || !v26[2]) )
      {
        EnterWaitSddlSidLookup();
        v27 = RtlLengthSid(RootDomSidBuf);
        memcpy_0((void *)v26[2], RootDomSidBuf, v27);
        v28 = RootDomSidBuf;
        goto LABEL_66;
      }
    }
    if ( v16 )
    {
      if ( *(_BYTE *)v26 )
      {
        v22 = (void *)v26[2];
        if ( v22 )
          goto LABEL_19;
      }
      goto LABEL_22;
    }
LABEL_20:
    if ( !_wcsnicmp(String1, (const wchar_t *)v26 + 1, *((unsigned int *)v26 + 3)) )
    {
      if ( *(_BYTE *)v26 && v26[2] )
      {
LABEL_5:
        v13 = &qword_1800AEDD0[13 * v14];
        goto LABEL_6;
      }
      v29 = *((_DWORD *)v26 + 7);
      if ( v29 && v29 != 3 )
        goto LABEL_22;
      EnterWaitSddlSidLookup();
      v33 = qword_1800AEDD0;
      if ( LOBYTE(qword_1800AEDD0[13 * v14]) && v26[2] )
        goto LABEL_55;
      CacheDomainAndDnsDomainSids(qword_1800AEDD0, v30, v31, v32, v64, v66, v67);
      v26[2] = (__int64)(v26 + 4);
      v34 = *((_DWORD *)v26 + 7);
      if ( v34 )
      {
        if ( v34 != 3 || !gbDomainSidCached )
        {
LABEL_55:
          LeaveWaitSddlSidLookup(v33, v30, v31, v32, v64, v66, v67);
          if ( LOBYTE(qword_1800AEDD0[13 * v14]) && qword_1800AEDD0[13 * v14 + 2] )
            goto LABEL_5;
          goto LABEL_22;
        }
        v35 = RtlLengthSid(Sid);
        memcpy_0((void *)qword_1800AEDD0[13 * v14 + 2], Sid, v35);
        v36 = qword_1800AEDD0[13 * v14 + 2];
        ++*(_BYTE *)(v36 + 1);
        v37 = Sid;
      }
      else
      {
        if ( !gbDnsDomainSidCached )
          goto LABEL_55;
        v48 = RtlLengthSid(Src);
        memcpy_0((void *)qword_1800AEDD0[13 * v14 + 2], Src, v48);
        v49 = qword_1800AEDD0[13 * v14 + 2];
        ++*(_BYTE *)(v49 + 1);
        v37 = Src;
      }
      v38 = RtlSubAuthorityCountSid(v37);
      v39 = RtlSubAuthoritySid((PSID)qword_1800AEDD0[13 * v14 + 2], *v38);
      v33 = (__int64 *)LODWORD(qword_1800AEDD0[13 * v14 + 3]);
      *v39 = (unsigned int)v33;
      LOBYTE(qword_1800AEDD0[13 * v14]) = 1;
      goto LABEL_55;
    }
    if ( !v15 || !(_BYTE)a6 || a3 || (v23 = (__int64)qword_1800AEDD0, !LOBYTE(qword_1800AEDD0[13 * v14])) || !v26[2] )
    {
LABEL_22:
      v10 = Sid2;
      goto LABEL_28;
    }
    v10 = Sid2;
    if ( _wcsnicmp(L"DA", (const wchar_t *)v26 + 1, *((unsigned int *)v26 + 3)) )
      goto LABEL_28;
    v21 = v14;
    LODWORD(v64) = v14;
LABEL_29:
    if ( ++v14 < 0x44 )
    {
      v16 = v68;
      continue;
    }
    break;
  }
  if ( !v15 || !(_BYTE)a6 || a3 || v21 >= 0x44 )
    goto LABEL_31;
  if ( HIDWORD(v64) )
  {
    if ( v68 )
    {
      *a7 = v10;
    }
    else
    {
      v60 = &qword_1800AEDD0[13 * v21];
      v23 = v60[2];
      if ( v23 )
      {
        v61 = RtlLengthSid((PSID)v23);
        v62 = LocalAlloc(0x40u, v61 + 1);
        *a7 = v62;
        if ( v62 )
        {
          _mm_lfence();
          memcpy_0(v62, (const void *)v60[2], v61);
          v63 = RtlSubAuthorityCountSid((PSID)v60[2]);
          *RtlSubAuthoritySid(*a7, (unsigned int)*v63 - 1) = 518;
        }
      }
    }
LABEL_31:
    v13 = v66;
  }
  else
  {
    v13 = &qword_1800AEDD0[13 * v21];
  }
LABEL_6:
  LOBYTE(v23) = 2;
  InitializeSidLookupTable(v23, (__int64)v22, v24, v25);
  return v13;
}

```

## disassembly

```asm
0x18001c000  mov     [rsp+Sid], r8
0x18001c005  mov     [rsp+Sid1], rdx
0x18001c00a  push    rbx
0x18001c00b  push    r12
0x18001c00d  push    r13
0x18001c00f  push    r15
0x18001c011  sub     rsp, 48h
0x18001c015  mov     r12, r9
0x18001c018  mov     rbx, r8
0x18001c01b  mov     r15, rdx
0x18001c01e  mov     r13, rcx
0x18001c021  test    rcx, rcx
0x18001c024  jnz     short loc_18001C08D
0x18001c026  test    rdx, rdx
0x18001c029  jnz     short loc_18001C08D
0x18001c02b  xor     eax, eax
0x18001c02d  add     rsp, 48h
0x18001c031  pop     r15
0x18001c033  pop     r13
0x18001c035  pop     r12
0x18001c037  pop     rbx
0x18001c038  retn
0x18001c03a  cmp     byte ptr [r14], 0
0x18001c03e  jz      loc_18001C33F
0x18001c044  cmp     qword ptr [rbx+10h], 0
0x18001c049  jz      loc_18001C33F
0x18001c04f  lea     rbx, qword_1800AEDD0
0x18001c056  mov     eax, edi
0x18001c058  imul    r14, rax, 68h ; 'h'
0x18001c05c  add     r14, rbx
0x18001c05f  mov     cl, 2
0x18001c061  call    InitializeSidLookupTable
0x18001c066  mov     rax, r14
0x18001c069  mov     rdi, [rsp+68h+var_30]
0x18001c06e  mov     rsi, [rsp+68h+var_28]
0x18001c073  mov     rbp, [rsp+68h+arg_18]
0x18001c07b  mov     r14, [rsp+68h+var_38]
0x18001c080  add     rsp, 48h
0x18001c084  pop     r15
0x18001c086  pop     r13
0x18001c088  pop     r12
0x18001c08a  pop     rbx
0x18001c08b  retn
0x18001c08d  mov     [rsp+68h+arg_18], rbp
0x18001c095  mov     [rsp+68h+var_28], rsi
0x18001c09a  mov     [rsp+68h+var_30], rdi
0x18001c09f  xor     edi, edi
0x18001c0a1  mov     [rsp+68h+var_38], r14
0x18001c0a6  mov     ebp, edi
0x18001c0a8  mov     r14, [rsp+68h+arg_30]
0x18001c0b0  mov     [rsp+68h+var_40], rdi
0x18001c0b5  mov     [rsp+68h+var_44], edi
0x18001c0b9  mov     [r14], rdi
0x18001c0bc  test    r13, r13
0x18001c0bf  jz      loc_18001C43C
0x18001c0c5  xor     sil, sil
0x18001c0c8  lea     rdx, aEa; "EA"
0x18001c0cf  mov     r8d, 2; MaxCount
0x18001c0d5  mov     [rsp+68h+arg_0], sil
0x18001c0da  call    cs:__imp__wcsnicmp
0x18001c0e1  nop     dword ptr [rax+rax+00h]
0x18001c0e6  test    eax, eax
0x18001c0e8  jz      short loc_18001C14E
0x18001c0ea  mov     r8d, 2; MaxCount
0x18001c0f0  lea     rdx, aSa; "SA"
0x18001c0f7  mov     rcx, r13; String1
0x18001c0fa  call    cs:__imp__wcsnicmp
0x18001c101  nop     dword ptr [rax+rax+00h]
0x18001c106  test    eax, eax
0x18001c108  jz      loc_18001C5A7
0x18001c10e  mov     r8d, 2; MaxCount
0x18001c114  lea     rdx, aRo; "RO"
0x18001c11b  mov     rcx, r13; String1
0x18001c11e  call    cs:__imp__wcsnicmp
0x18001c125  nop     dword ptr [rax+rax+00h]
0x18001c12a  test    eax, eax
0x18001c12c  jz      short loc_18001C14E
0x18001c12e  mov     r8d, 2; MaxCount
0x18001c134  lea     rdx, aEk; "EK"
0x18001c13b  mov     rcx, r13; String1
0x18001c13e  call    cs:__imp__wcsnicmp
0x18001c145  nop     dword ptr [rax+rax+00h]
0x18001c14a  test    eax, eax
0x18001c14c  jnz     short loc_18001C153
0x18001c14e  mov     ebp, 1
0x18001c153  test    r12, r12
0x18001c156  jnz     loc_18001C5C1
0x18001c15c  mov     r14d, 44h ; 'D'
0x18001c162  mov     cl, 1
0x18001c164  mov     [rsp+68h+var_48], r14d
0x18001c169  call    InitializeSidLookupTable
0x18001c16e  test    ebp, ebp
0x18001c170  jnz     loc_18001C743
0x18001c176  lea     rbx, qword_1800AEDD0
0x18001c17d  test    ebp, ebp
0x18001c17f  jnz     short loc_18001C18A
0x18001c181  test    r12, r12
0x18001c184  jnz     loc_18001C591
0x18001c18a  mov     r15d, edi
0x18001c18d  imul    rax, r15, 68h ; 'h'
0x18001c191  lea     r14, [rax+rbx]
0x18001c195  add     rbx, rax
0x18001c198  cmp     byte ptr [r14], 0
0x18001c19c  jz      loc_18001C267
0x18001c1a2  mov     rdx, [rbx+10h]; Sid2
0x18001c1a6  test    rdx, rdx
0x18001c1a9  jz      loc_18001C267
0x18001c1af  test    sil, sil
0x18001c1b2  jnz     loc_18001C292
0x18001c1b8  mov     r8d, [rbx+0Ch]; MaxCount
0x18001c1bc  lea     rdx, [r14+2]; String2
0x18001c1c0  mov     rcx, r13; String1
0x18001c1c3  call    cs:__imp__wcsnicmp
0x18001c1ca  nop     dword ptr [rax+rax+00h]
0x18001c1cf  test    eax, eax
0x18001c1d1  jz      loc_18001C03A
0x18001c1d7  test    ebp, ebp
0x18001c1d9  jnz     short loc_18001C1E9
0x18001c1db  lea     rbx, qword_1800AEDD0
0x18001c1e2  mov     r15, [rsp+68h+Sid1]
0x18001c1e7  jmp     short loc_18001C245
0x18001c1e9  cmp     byte ptr [rsp+68h+arg_28], 0
0x18001c1f1  jz      short loc_18001C1DB
0x18001c1f3  cmp     [rsp+68h+Sid], 0
0x18001c1fc  jnz     short loc_18001C1DB
0x18001c1fe  imul    rax, r15, 68h ; 'h'
0x18001c202  lea     rcx, qword_1800AEDD0
0x18001c209  cmp     byte ptr [rax+rcx], 0
0x18001c20d  jz      short loc_18001C1DB
0x18001c20f  cmp     qword ptr [rbx+10h], 0
0x18001c214  jz      short loc_18001C1DB
0x18001c216  mov     r8d, [rbx+0Ch]; MaxCount
0x18001c21a  lea     rdx, [r14+2]; String2
0x18001c21e  lea     rcx, aDa; "DA"
0x18001c225  call    cs:__imp__wcsnicmp
0x18001c22c  nop     dword ptr [rax+rax+00h]
0x18001c231  mov     r15, [rsp+68h+Sid1]
0x18001c236  lea     rbx, qword_1800AEDD0
0x18001c23d  test    eax, eax
0x18001c23f  jz      loc_18001C786
0x18001c245  mov     r14d, [rsp+68h+var_48]
0x18001c24a  inc     edi
0x18001c24c  cmp     edi, 44h ; 'D'
0x18001c24f  jb      loc_18001C792
0x18001c255  test    ebp, ebp
0x18001c257  jnz     loc_18001C79C
0x18001c25d  mov     r14, [rsp+68h+var_40]
0x18001c262  jmp     loc_18001C05F
0x18001c267  cmp     dword ptr [rbx+1Ch], 7
0x18001c26b  jz      short loc_18001C2B6
0x18001c26d  test    sil, sil
0x18001c270  jz      loc_18001C1B8
0x18001c276  cmp     byte ptr [r14], 0
0x18001c27a  jz      loc_18001C1DB
0x18001c280  mov     rdx, [rbx+10h]
0x18001c284  test    rdx, rdx
0x18001c287  jnz     loc_18001C1AF
0x18001c28d  jmp     loc_18001C1DB
0x18001c292  mov     r15, [rsp+68h+Sid1]
0x18001c297  mov     rcx, r15; Sid1
0x18001c29a  call    cs:__imp_RtlEqualSid
0x18001c2a1  nop     dword ptr [rax+rax+00h]
0x18001c2a6  lea     rbx, qword_1800AEDD0
0x18001c2ad  test    al, al
0x18001c2af  jz      short loc_18001C245
0x18001c2b1  jmp     loc_18001C056
0x18001c2b6  test    ebp, ebp
0x18001c2b8  jz      short loc_18001C26D
0x18001c2ba  mov     rax, [rsp+68h+Sid]
0x18001c2c2  test    rax, rax
0x18001c2c5  jnz     loc_18001C4C6
0x18001c2cb  cmp     byte ptr [rsp+68h+arg_28], al
0x18001c2d2  jnz     short loc_18001C26D
0x18001c2d4  cmp     cs:RootDomInited, eax
0x18001c2da  jz      short loc_18001C26D
0x18001c2dc  lea     rcx, RootDomSidBuf; Sid
0x18001c2e3  call    cs:__imp_RtlValidSid
0x18001c2ea  nop     dword ptr [rax+rax+00h]
0x18001c2ef  test    al, al
0x18001c2f1  jz      loc_18001C26D
0x18001c2f7  cmp     byte ptr [r14], 0
0x18001c2fb  jz      short loc_18001C308
0x18001c2fd  cmp     qword ptr [rbx+10h], 0
0x18001c302  jnz     loc_18001C26D
0x18001c308  call    EnterWaitSddlSidLookup
0x18001c30d  lea     rcx, RootDomSidBuf; Sid
0x18001c314  call    cs:__imp_RtlLengthSid
0x18001c31b  nop     dword ptr [rax+rax+00h]
0x18001c320  mov     rcx, [rbx+10h]; void *
0x18001c324  lea     rdx, RootDomSidBuf; Src
0x18001c32b  mov     r8d, eax; Size
0x18001c32e  call    memcpy_0
0x18001c333  lea     rcx, RootDomSidBuf
0x18001c33a  jmp     loc_18001C505
0x18001c33f  mov     eax, [rbx+1Ch]
0x18001c342  test    eax, eax
0x18001c344  jnz     loc_18001C4B8
0x18001c34a  call    EnterWaitSddlSidLookup
0x18001c34f  imul    rax, r15, 68h ; 'h'
0x18001c353  lea     rcx, qword_1800AEDD0
0x18001c35a  cmp     byte ptr [rax+rcx], 0
0x18001c35e  jz      short loc_18001C36B
0x18001c360  cmp     qword ptr [rbx+10h], 0
0x18001c365  jnz     loc_18001C5B5
0x18001c36b  call    CacheDomainAndDnsDomainSids
0x18001c370  lea     rax, [r14+20h]
0x18001c374  mov     [rbx+10h], rax
0x18001c378  mov     eax, [rbx+1Ch]
0x18001c37b  test    eax, eax
0x18001c37d  jz      loc_18001C53E
0x18001c383  cmp     eax, 3
0x18001c386  jnz     loc_18001C5B5
0x18001c38c  cmp     cs:gbDomainSidCached, 0
0x18001c393  jz      loc_18001C5B5
0x18001c399  mov     rcx, cs:Sid; Sid
0x18001c3a0  call    cs:__imp_RtlLengthSid
0x18001c3a7  nop     dword ptr [rax+rax+00h]
0x18001c3ac  mov     rdx, cs:Sid; Src
0x18001c3b3  lea     rbx, qword_1800AEDD0
0x18001c3ba  imul    rcx, r15, 68h ; 'h'
0x18001c3be  mov     r8d, eax; Size
0x18001c3c1  mov     rcx, [rcx+rbx+10h]; void *
0x18001c3c6  call    memcpy_0
0x18001c3cb  imul    rax, r15, 68h ; 'h'
0x18001c3cf  mov     rax, [rax+rbx+10h]
0x18001c3d4  inc     byte ptr [rax+1]
0x18001c3d7  mov     rcx, cs:Sid; Sid
0x18001c3de  call    cs:__imp_RtlSubAuthorityCountSid
0x18001c3e5  nop     dword ptr [rax+rax+00h]
0x18001c3ea  imul    rcx, r15, 68h ; 'h'
0x18001c3ee  movzx   edx, byte ptr [rax]; SubAuthority
0x18001c3f1  mov     rcx, [rcx+rbx+10h]; Sid
0x18001c3f6  call    cs:__imp_RtlSubAuthoritySid
0x18001c3fd  nop     dword ptr [rax+rax+00h]
0x18001c402  imul    rcx, r15, 68h ; 'h'
0x18001c406  mov     ecx, [rcx+rbx+18h]
0x18001c40a  mov     [rax], ecx
0x18001c40c  imul    rax, r15, 68h ; 'h'
0x18001c410  mov     byte ptr [rax+rbx], 1
0x18001c414  call    LeaveWaitSddlSidLookup
0x18001c419  imul    rax, r15, 68h ; 'h'
0x18001c41d  cmp     byte ptr [rax+rbx], 0
0x18001c421  jz      loc_18001C1E2
0x18001c427  imul    rax, r15, 68h ; 'h'
0x18001c42b  cmp     qword ptr [rax+rbx+10h], 0
0x18001c431  jz      loc_18001C1E2
0x18001c437  jmp     loc_18001C056
0x18001c43c  mov     sil, 1
0x18001c43f  mov     rcx, r15; Sid
0x18001c442  mov     [rsp+68h+arg_0], sil
0x18001c447  call    cs:__imp_RtlSubAuthorityCountSid
0x18001c44e  nop     dword ptr [rax+rax+00h]
0x18001c453  cmp     [rax], dil
0x18001c456  jbe     loc_18001C153
0x18001c45c  mov     rcx, r15; Sid
0x18001c45f  call    cs:__imp_RtlSubAuthorityCountSid
0x18001c466  nop     dword ptr [rax+rax+00h]
0x18001c46b  mov     rcx, r15; Sid
0x18001c46e  movzx   edx, byte ptr [rax]
0x18001c471  dec     edx; SubAuthority
0x18001c473  call    cs:__imp_RtlSubAuthoritySid
0x18001c47a  nop     dword ptr [rax+rax+00h]
0x18001c47f  mov     ecx, [rax]
0x18001c481  lea     eax, [rcx-1F2h]
0x18001c487  cmp     eax, 1Dh
0x18001c48a  ja      loc_18001C153
0x18001c490  mov     edx, 20300001h
0x18001c495  bt      edx, eax
0x18001c498  jnb     loc_18001C153
0x18001c49e  mov     ebp, 1
0x18001c4a3  cmp     ecx, 206h
0x18001c4a9  jnz     loc_18001C153
0x18001c4af  mov     [rsp+68h+var_44], ebp
0x18001c4b3  jmp     loc_18001C153
0x18001c4b8  cmp     eax, 3
0x18001c4bb  jnz     loc_18001C1DB
0x18001c4c1  jmp     loc_18001C34A
0x18001c4c6  cmp     byte ptr [rax+1], 0Fh
0x18001c4ca  jnb     loc_18001C26D
0x18001c4d0  call    EnterWaitSddlSidLookup
0x18001c4d5  mov     rcx, [rsp+68h+Sid]; Sid
0x18001c4dd  call    cs:__imp_RtlLengthSid
0x18001c4e4  nop     dword ptr [rax+rax+00h]
0x18001c4e9  mov     rdx, [rsp+68h+Sid]; Src
0x18001c4f1  mov     rcx, [rbx+10h]; void *
0x18001c4f5  mov     r8d, eax; Size
0x18001c4f8  call    memcpy_0
0x18001c4fd  mov     rcx, [rsp+68h+Sid]; Sid
0x18001c505  mov     rax, [rbx+10h]
0x18001c509  inc     byte ptr [rax+1]
0x18001c50c  call    cs:__imp_RtlSubAuthorityCountSid
0x18001c513  nop     dword ptr [rax+rax+00h]
0x18001c518  mov     rcx, [rbx+10h]; Sid
0x18001c51c  movzx   edx, byte ptr [rax]; SubAuthority
0x18001c51f  call    cs:__imp_RtlSubAuthoritySid
0x18001c526  nop     dword ptr [rax+rax+00h]
0x18001c52b  mov     ecx, [rbx+18h]
0x18001c52e  mov     [rax], ecx
0x18001c530  mov     byte ptr [r14], 1
0x18001c534  call    LeaveWaitSddlSidLookup
  ... truncated ...
```
