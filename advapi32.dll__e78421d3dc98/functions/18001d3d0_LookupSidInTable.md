# LookupSidInTable

- ea: `0x18001d3d0`
- end: `0x18001db9e`
- name: `LookupSidInTable`
- size: `1998`
- prototype: `__int64 __usercall@<rax>(wchar_t *String1@<rcx>, PSID Sid2@<rdx>, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18001abc0`
- `0x18001b480`
- `0x18001ca94`
- `0x18001cbbc`
- `0x18001e218`
- `0x18001ea7c`
- `0x180020464`

## callees

- `0x18001d3d0`
- `0x18001dbb0`
- `0x18001e0bc`
- `0x18001ea04`
- `0x18001ea50`
- `0x180052738`
- `0x180065042`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001d4a8`
- `msvcrt!_wcsnicmp` at `0x18001d4c2`
- `msvcrt!_wcsnicmp` at `0x18001d4e0`
- `msvcrt!_wcsnicmp` at `0x18001d4fa`
- `msvcrt!_wcsnicmp` at `0x18001d579`
- `msvcrt!_wcsnicmp` at `0x18001d5d5`
- `msvcrt!_wcsnicmp` at `0x18001d94d`
- `msvcrt!_wcsnicmp` at `0x18001d4a8`
- `msvcrt!_wcsnicmp` at `0x18001d4c2`
- `msvcrt!_wcsnicmp` at `0x18001d4e0`
- `msvcrt!_wcsnicmp` at `0x18001d4fa`
- `msvcrt!_wcsnicmp` at `0x18001d579`
- `msvcrt!_wcsnicmp` at `0x18001d5d5`
- `msvcrt!_wcsnicmp` at `0x18001d94d`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001d76c`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001d7c9`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001d7db`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001d876`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001d9de`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001db70`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001d76c`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001d7c9`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001d7db`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001d876`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001d9de`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001db70`
- `ntdll!RtlEqualSid` at `0x18001d644`
- `ntdll!RtlEqualSid` at `0x18001da35`
- `ntdll!RtlEqualSid` at `0x18001d644`
- `ntdll!RtlEqualSid` at `0x18001da35`
- `ntdll!RtlLengthSid` at `0x18001d6ae`
- `ntdll!RtlLengthSid` at `0x18001d734`
- `ntdll!RtlLengthSid` at `0x18001d84d`
- `ntdll!RtlLengthSid` at `0x18001d8ac`
- `ntdll!RtlLengthSid` at `0x18001d9bf`
- `ntdll!RtlLengthSid` at `0x18001db30`
- `ntdll!RtlLengthSid` at `0x18001d6ae`
- `ntdll!RtlLengthSid` at `0x18001d734`
- `ntdll!RtlLengthSid` at `0x18001d84d`
- `ntdll!RtlLengthSid` at `0x18001d8ac`
- `ntdll!RtlLengthSid` at `0x18001d9bf`
- `ntdll!RtlLengthSid` at `0x18001db30`
- `ntdll!RtlValidSid` at `0x18001d687`
- `ntdll!RtlValidSid` at `0x18001daa2`
- `ntdll!RtlValidSid` at `0x18001d687`
- `ntdll!RtlValidSid` at `0x18001daa2`
- `ntdll!RtlSubAuthoritySid` at `0x18001d77e`
- `ntdll!RtlSubAuthoritySid` at `0x18001d7e9`
- `ntdll!RtlSubAuthoritySid` at `0x18001d883`
- `ntdll!RtlSubAuthoritySid` at `0x18001d9eb`
- `ntdll!RtlSubAuthoritySid` at `0x18001db7e`
- `ntdll!RtlSubAuthoritySid` at `0x18001d77e`
- `ntdll!RtlSubAuthoritySid` at `0x18001d7e9`
- `ntdll!RtlSubAuthoritySid` at `0x18001d883`
- `ntdll!RtlSubAuthoritySid` at `0x18001d9eb`
- `ntdll!RtlSubAuthoritySid` at `0x18001db7e`
- `KERNELBASE!LocalAlloc` at `0x18001db40`
- `KERNELBASE!LocalAlloc` at `0x18001db40`

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
        if ( !*(_DWORD *)((char *)&qword_18009FDE0[3] + v23 + 4) )
          goto LABEL_29;
      }
    }
    v26 = &qword_18009FDE0[13 * v14];
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
        v13 = &qword_18009FDE0[13 * v14];
        goto LABEL_6;
      }
      v29 = *((_DWORD *)v26 + 7);
      if ( v29 && v29 != 3 )
        goto LABEL_22;
      EnterWaitSddlSidLookup();
      v33 = qword_18009FDE0;
      if ( LOBYTE(qword_18009FDE0[13 * v14]) && v26[2] )
        goto LABEL_55;
      CacheDomainAndDnsDomainSids(qword_18009FDE0, v30, v31, v32, v64, v66, v67);
      v26[2] = (__int64)(v26 + 4);
      v34 = *((_DWORD *)v26 + 7);
      if ( v34 )
      {
        if ( v34 != 3 || !gbDomainSidCached )
        {
LABEL_55:
          LeaveWaitSddlSidLookup(v33, v30, v31, v32, v64, v66, v67);
          if ( LOBYTE(qword_18009FDE0[13 * v14]) && qword_18009FDE0[13 * v14 + 2] )
            goto LABEL_5;
          goto LABEL_22;
        }
        v35 = RtlLengthSid(Sid);
        memcpy_0((void *)qword_18009FDE0[13 * v14 + 2], Sid, v35);
        v36 = qword_18009FDE0[13 * v14 + 2];
        ++*(_BYTE *)(v36 + 1);
        v37 = Sid;
      }
      else
      {
        if ( !gbDnsDomainSidCached )
          goto LABEL_55;
        v48 = RtlLengthSid(Src);
        memcpy_0((void *)qword_18009FDE0[13 * v14 + 2], Src, v48);
        v49 = qword_18009FDE0[13 * v14 + 2];
        ++*(_BYTE *)(v49 + 1);
        v37 = Src;
      }
      v38 = RtlSubAuthorityCountSid(v37);
      v39 = RtlSubAuthoritySid((PSID)qword_18009FDE0[13 * v14 + 2], *v38);
      v33 = (__int64 *)LODWORD(qword_18009FDE0[13 * v14 + 3]);
      *v39 = (unsigned int)v33;
      LOBYTE(qword_18009FDE0[13 * v14]) = 1;
      goto LABEL_55;
    }
    if ( !v15 || !(_BYTE)a6 || a3 || (v23 = (__int64)qword_18009FDE0, !LOBYTE(qword_18009FDE0[13 * v14])) || !v26[2] )
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
      v60 = &qword_18009FDE0[13 * v21];
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
    v13 = &qword_18009FDE0[13 * v21];
  }
LABEL_6:
  LOBYTE(v23) = 2;
  InitializeSidLookupTable(v23, (__int64)v22, v24, v25);
  return v13;
}

```

## disassembly

```asm
0x18001d3d0  mov     [rsp+Sid], r8
0x18001d3d5  mov     [rsp+Sid1], rdx
0x18001d3da  push    rbx
0x18001d3db  push    r12
0x18001d3dd  push    r13
0x18001d3df  push    r15
0x18001d3e1  sub     rsp, 48h
0x18001d3e5  mov     r12, r9
0x18001d3e8  mov     rbx, r8
0x18001d3eb  mov     r15, rdx
0x18001d3ee  mov     r13, rcx
0x18001d3f1  test    rcx, rcx
0x18001d3f4  jnz     short loc_18001D45B
0x18001d3f6  test    rdx, rdx
0x18001d3f9  jnz     short loc_18001D45B
0x18001d3fb  xor     eax, eax
0x18001d3fd  add     rsp, 48h
0x18001d401  pop     r15
0x18001d403  pop     r13
0x18001d405  pop     r12
0x18001d407  pop     rbx
0x18001d408  retn
0x18001d409  cmp     byte ptr [r14], 0
0x18001d40d  jz      loc_18001D6D3
0x18001d413  cmp     qword ptr [rbx+10h], 0
0x18001d418  jz      loc_18001D6D3
0x18001d41e  lea     rbx, qword_18009FDE0
0x18001d425  mov     eax, edi
0x18001d427  imul    r14, rax, 68h ; 'h'
0x18001d42b  add     r14, rbx
0x18001d42e  mov     cl, 2
0x18001d430  call    InitializeSidLookupTable
0x18001d435  mov     rax, r14
0x18001d438  mov     rdi, [rsp+68h+var_30]
0x18001d43d  mov     rsi, [rsp+68h+var_28]
0x18001d442  mov     rbp, [rsp+68h+arg_18]
0x18001d44a  mov     r14, [rsp+68h+var_38]
0x18001d44f  add     rsp, 48h
0x18001d453  pop     r15
0x18001d455  pop     r13
0x18001d457  pop     r12
0x18001d459  pop     rbx
0x18001d45a  retn
0x18001d45b  mov     [rsp+68h+arg_18], rbp
0x18001d463  mov     [rsp+68h+var_28], rsi
0x18001d468  mov     [rsp+68h+var_30], rdi
0x18001d46d  xor     edi, edi
0x18001d46f  mov     [rsp+68h+var_38], r14
0x18001d474  mov     ebp, edi
0x18001d476  mov     r14, [rsp+68h+arg_30]
0x18001d47e  mov     [rsp+68h+var_40], rdi
0x18001d483  mov     [rsp+68h+var_44], edi
0x18001d487  mov     [r14], rdi
0x18001d48a  test    r13, r13
0x18001d48d  jz      loc_18001D7BE
0x18001d493  xor     sil, sil
0x18001d496  lea     rdx, aEa; "EA"
0x18001d49d  mov     r8d, 2; MaxCount
0x18001d4a3  mov     [rsp+68h+arg_0], sil
0x18001d4a8  call    cs:__imp__wcsnicmp
0x18001d4ae  test    eax, eax
0x18001d4b0  jz      short loc_18001D504
0x18001d4b2  mov     r8d, 2; MaxCount
0x18001d4b8  lea     rdx, aSa; "SA"
0x18001d4bf  mov     rcx, r13; String1
0x18001d4c2  call    cs:__imp__wcsnicmp
0x18001d4c8  test    eax, eax
0x18001d4ca  jz      loc_18001D8FF
0x18001d4d0  mov     r8d, 2; MaxCount
0x18001d4d6  lea     rdx, aRo; "RO"
0x18001d4dd  mov     rcx, r13; String1
0x18001d4e0  call    cs:__imp__wcsnicmp
0x18001d4e6  test    eax, eax
0x18001d4e8  jz      short loc_18001D504
0x18001d4ea  mov     r8d, 2; MaxCount
0x18001d4f0  lea     rdx, aEk; "EK"
0x18001d4f7  mov     rcx, r13; String1
0x18001d4fa  call    cs:__imp__wcsnicmp
0x18001d500  test    eax, eax
0x18001d502  jnz     short loc_18001D509
0x18001d504  mov     ebp, 1
0x18001d509  test    r12, r12
0x18001d50c  jnz     loc_18001D919
0x18001d512  mov     r14d, 44h ; 'D'
0x18001d518  mov     cl, 1
0x18001d51a  mov     [rsp+68h+var_48], r14d
0x18001d51f  call    InitializeSidLookupTable
0x18001d524  test    ebp, ebp
0x18001d526  jnz     loc_18001DA7D
0x18001d52c  lea     rbx, qword_18009FDE0
0x18001d533  test    ebp, ebp
0x18001d535  jnz     short loc_18001D540
0x18001d537  test    r12, r12
0x18001d53a  jnz     loc_18001D8E9
0x18001d540  mov     r15d, edi
0x18001d543  imul    rax, r15, 68h ; 'h'
0x18001d547  lea     r14, [rax+rbx]
0x18001d54b  add     rbx, rax
0x18001d54e  cmp     byte ptr [r14], 0
0x18001d552  jz      loc_18001D611
0x18001d558  mov     rdx, [rbx+10h]; Sid2
0x18001d55c  test    rdx, rdx
0x18001d55f  jz      loc_18001D611
0x18001d565  test    sil, sil
0x18001d568  jnz     loc_18001D63C
0x18001d56e  mov     r8d, [rbx+0Ch]; MaxCount
0x18001d572  lea     rdx, [r14+2]; String2
0x18001d576  mov     rcx, r13; String1
0x18001d579  call    cs:__imp__wcsnicmp
0x18001d57f  test    eax, eax
0x18001d581  jz      loc_18001D409
0x18001d587  test    ebp, ebp
0x18001d589  jnz     short loc_18001D599
0x18001d58b  lea     rbx, qword_18009FDE0
0x18001d592  mov     r15, [rsp+68h+Sid1]
0x18001d597  jmp     short loc_18001D5EF
0x18001d599  cmp     byte ptr [rsp+68h+arg_28], 0
0x18001d5a1  jz      short loc_18001D58B
0x18001d5a3  cmp     [rsp+68h+Sid], 0
0x18001d5ac  jnz     short loc_18001D58B
0x18001d5ae  imul    rax, r15, 68h ; 'h'
0x18001d5b2  lea     rcx, qword_18009FDE0
0x18001d5b9  cmp     byte ptr [rax+rcx], 0
0x18001d5bd  jz      short loc_18001D58B
0x18001d5bf  cmp     qword ptr [rbx+10h], 0
0x18001d5c4  jz      short loc_18001D58B
0x18001d5c6  mov     r8d, [rbx+0Ch]; MaxCount
0x18001d5ca  lea     rdx, [r14+2]; String2
0x18001d5ce  lea     rcx, aDa; "DA"
0x18001d5d5  call    cs:__imp__wcsnicmp
0x18001d5db  mov     r15, [rsp+68h+Sid1]
0x18001d5e0  lea     rbx, qword_18009FDE0
0x18001d5e7  test    eax, eax
0x18001d5e9  jz      loc_18001DABA
0x18001d5ef  mov     r14d, [rsp+68h+var_48]
0x18001d5f4  inc     edi
0x18001d5f6  cmp     edi, 44h ; 'D'
0x18001d5f9  jb      loc_18001DAC6
0x18001d5ff  test    ebp, ebp
0x18001d601  jnz     loc_18001DAD0
0x18001d607  mov     r14, [rsp+68h+var_40]
0x18001d60c  jmp     loc_18001D42E
0x18001d611  cmp     dword ptr [rbx+1Ch], 7
0x18001d615  jz      short loc_18001D65A
0x18001d617  test    sil, sil
0x18001d61a  jz      loc_18001D56E
0x18001d620  cmp     byte ptr [r14], 0
0x18001d624  jz      loc_18001D58B
0x18001d62a  mov     rdx, [rbx+10h]
0x18001d62e  test    rdx, rdx
0x18001d631  jnz     loc_18001D565
0x18001d637  jmp     loc_18001D58B
0x18001d63c  mov     r15, [rsp+68h+Sid1]
0x18001d641  mov     rcx, r15; Sid1
0x18001d644  call    cs:__imp_RtlEqualSid
0x18001d64a  lea     rbx, qword_18009FDE0
0x18001d651  test    al, al
0x18001d653  jz      short loc_18001D5EF
0x18001d655  jmp     loc_18001D425
0x18001d65a  test    ebp, ebp
0x18001d65c  jz      short loc_18001D617
0x18001d65e  mov     rax, [rsp+68h+Sid]
0x18001d666  test    rax, rax
0x18001d669  jnz     loc_18001D836
0x18001d66f  cmp     byte ptr [rsp+68h+arg_28], al
0x18001d676  jnz     short loc_18001D617
0x18001d678  cmp     cs:RootDomInited, eax
0x18001d67e  jz      short loc_18001D617
0x18001d680  lea     rcx, RootDomSidBuf; Sid
0x18001d687  call    cs:__imp_RtlValidSid
0x18001d68d  test    al, al
0x18001d68f  jz      short loc_18001D617
0x18001d691  cmp     byte ptr [r14], 0
0x18001d695  jz      short loc_18001D6A2
0x18001d697  cmp     qword ptr [rbx+10h], 0
0x18001d69c  jnz     loc_18001D617
0x18001d6a2  call    EnterWaitSddlSidLookup
0x18001d6a7  lea     rcx, RootDomSidBuf; Sid
0x18001d6ae  call    cs:__imp_RtlLengthSid
0x18001d6b4  mov     rcx, [rbx+10h]; void *
0x18001d6b8  lea     rdx, RootDomSidBuf; Src
0x18001d6bf  mov     r8d, eax; Size
0x18001d6c2  call    memcpy_0
0x18001d6c7  lea     rcx, RootDomSidBuf
0x18001d6ce  jmp     loc_18001D86F
0x18001d6d3  mov     eax, [rbx+1Ch]
0x18001d6d6  test    eax, eax
0x18001d6d8  jnz     loc_18001D828
0x18001d6de  call    EnterWaitSddlSidLookup
0x18001d6e3  imul    rax, r15, 68h ; 'h'
0x18001d6e7  lea     rcx, qword_18009FDE0
0x18001d6ee  cmp     byte ptr [rax+rcx], 0
0x18001d6f2  jz      short loc_18001D6FF
0x18001d6f4  cmp     qword ptr [rbx+10h], 0
0x18001d6f9  jnz     loc_18001D90D
0x18001d6ff  call    CacheDomainAndDnsDomainSids
0x18001d704  lea     rax, [r14+20h]
0x18001d708  mov     [rbx+10h], rax
0x18001d70c  mov     eax, [rbx+1Ch]
0x18001d70f  test    eax, eax
0x18001d711  jz      loc_18001D89C
0x18001d717  cmp     eax, 3
0x18001d71a  jnz     loc_18001D90D
0x18001d720  cmp     cs:gbDomainSidCached, 0
0x18001d727  jz      loc_18001D90D
0x18001d72d  mov     rcx, cs:Sid; Sid
0x18001d734  call    cs:__imp_RtlLengthSid
0x18001d73a  mov     rdx, cs:Sid; Src
0x18001d741  lea     rbx, qword_18009FDE0
0x18001d748  imul    rcx, r15, 68h ; 'h'
0x18001d74c  mov     r8d, eax; Size
0x18001d74f  mov     rcx, [rcx+rbx+10h]; void *
0x18001d754  call    memcpy_0
0x18001d759  imul    rax, r15, 68h ; 'h'
0x18001d75d  mov     rax, [rax+rbx+10h]
0x18001d762  inc     byte ptr [rax+1]
0x18001d765  mov     rcx, cs:Sid; Sid
0x18001d76c  call    cs:__imp_RtlSubAuthorityCountSid
0x18001d772  imul    rcx, r15, 68h ; 'h'
0x18001d776  movzx   edx, byte ptr [rax]; SubAuthority
0x18001d779  mov     rcx, [rcx+rbx+10h]; Sid
0x18001d77e  call    cs:__imp_RtlSubAuthoritySid
0x18001d784  imul    rcx, r15, 68h ; 'h'
0x18001d788  mov     ecx, [rcx+rbx+18h]
0x18001d78c  mov     [rax], ecx
0x18001d78e  imul    rax, r15, 68h ; 'h'
0x18001d792  mov     byte ptr [rax+rbx], 1
0x18001d796  call    LeaveWaitSddlSidLookup
0x18001d79b  imul    rax, r15, 68h ; 'h'
0x18001d79f  cmp     byte ptr [rax+rbx], 0
0x18001d7a3  jz      loc_18001D592
0x18001d7a9  imul    rax, r15, 68h ; 'h'
0x18001d7ad  cmp     qword ptr [rax+rbx+10h], 0
0x18001d7b3  jz      loc_18001D592
0x18001d7b9  jmp     loc_18001D425
0x18001d7be  mov     sil, 1
0x18001d7c1  mov     rcx, r15; Sid
0x18001d7c4  mov     [rsp+68h+arg_0], sil
0x18001d7c9  call    cs:__imp_RtlSubAuthorityCountSid
0x18001d7cf  cmp     [rax], dil
0x18001d7d2  jbe     loc_18001D509
0x18001d7d8  mov     rcx, r15; Sid
0x18001d7db  call    cs:__imp_RtlSubAuthorityCountSid
0x18001d7e1  mov     rcx, r15; Sid
0x18001d7e4  movzx   edx, byte ptr [rax]
0x18001d7e7  dec     edx; SubAuthority
0x18001d7e9  call    cs:__imp_RtlSubAuthoritySid
0x18001d7ef  mov     ecx, [rax]
0x18001d7f1  lea     eax, [rcx-1F2h]
0x18001d7f7  cmp     eax, 1Dh
0x18001d7fa  ja      loc_18001D509
0x18001d800  mov     edx, 20300001h
0x18001d805  bt      edx, eax
0x18001d808  jnb     loc_18001D509
0x18001d80e  mov     ebp, 1
0x18001d813  cmp     ecx, 206h
0x18001d819  jnz     loc_18001D509
0x18001d81f  mov     [rsp+68h+var_44], ebp
0x18001d823  jmp     loc_18001D509
0x18001d828  cmp     eax, 3
0x18001d82b  jnz     loc_18001D58B
0x18001d831  jmp     loc_18001D6DE
0x18001d836  cmp     byte ptr [rax+1], 0Fh
0x18001d83a  jnb     loc_18001D617
0x18001d840  call    EnterWaitSddlSidLookup
0x18001d845  mov     rcx, [rsp+68h+Sid]; Sid
0x18001d84d  call    cs:__imp_RtlLengthSid
0x18001d853  mov     rdx, [rsp+68h+Sid]; Src
0x18001d85b  mov     rcx, [rbx+10h]; void *
0x18001d85f  mov     r8d, eax; Size
0x18001d862  call    memcpy_0
0x18001d867  mov     rcx, [rsp+68h+Sid]; Sid
0x18001d86f  mov     rax, [rbx+10h]
0x18001d873  inc     byte ptr [rax+1]
0x18001d876  call    cs:__imp_RtlSubAuthorityCountSid
0x18001d87c  mov     rcx, [rbx+10h]; Sid
0x18001d880  movzx   edx, byte ptr [rax]; SubAuthority
0x18001d883  call    cs:__imp_RtlSubAuthoritySid
0x18001d889  mov     ecx, [rbx+18h]
0x18001d88c  mov     [rax], ecx
0x18001d88e  mov     byte ptr [r14], 1
0x18001d892  call    LeaveWaitSddlSidLookup
0x18001d897  jmp     loc_18001D617
0x18001d89c  cmp     cs:gbDnsDomainSidCached, 0
0x18001d8a3  jz      short loc_18001D90D
0x18001d8a5  mov     rcx, cs:Src; Sid
0x18001d8ac  call    cs:__imp_RtlLengthSid
0x18001d8b2  mov     rdx, cs:Src; Src
0x18001d8b9  lea     rbx, qword_18009FDE0
0x18001d8c0  imul    rcx, r15, 68h ; 'h'
0x18001d8c4  mov     r8d, eax; Size
0x18001d8c7  mov     rcx, [rcx+rbx+10h]; void *
0x18001d8cc  call    memcpy_0
0x18001d8d1  imul    rax, r15, 68h ; 'h'
0x18001d8d5  mov     rax, [rax+rbx+10h]
0x18001d8da  inc     byte ptr [rax+1]
0x18001d8dd  mov     rcx, cs:Src
0x18001d8e4  jmp     loc_18001D76C
0x18001d8e9  mov     eax, edi
0x18001d8eb  imul    rcx, rax, 68h ; 'h'
  ... truncated ...
```
