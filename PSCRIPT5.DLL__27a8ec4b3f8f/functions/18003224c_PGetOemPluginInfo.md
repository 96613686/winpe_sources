# PGetOemPluginInfo

- ea: `0x18003224c`
- end: `0x180032535`
- name: `PGetOemPluginInfo`
- size: `745`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f8f8`

## callees

- `0x180001f20`
- `0x180002938`
- `0x18002f078`
- `0x180030424`
- `0x180030644`
- `0x180031a74`
- `0x18003224c`
- `0x180034a08`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800324cb`
- `KERNEL32!LocalFree` at `0x1800324f9`
- `KERNEL32!LocalFree` at `0x1800324cb`
- `KERNEL32!LocalFree` at `0x1800324f9`
- `KERNEL32!LocalAlloc` at `0x180032455`
- `KERNEL32!LocalAlloc` at `0x180032455`

## string_xrefs

- `0x180032308`: `OEMConfigFile1`

## pseudocode

```c
unsigned __int64 __fastcall PGetOemPluginInfo(__int64 a1, const wchar_t *a2, __int64 a3)
{
  const wchar_t *v3; // r14
  struct _FILETIME v5; // rcx
  wchar_t *v6; // r13
  unsigned int v7; // esi
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  const wchar_t *v11; // r10
  __int64 v12; // r9
  wchar_t *v13; // rax
  bool v14; // zf
  wchar_t *v15; // rcx
  const wchar_t *v16; // r10
  __int64 v17; // r9
  wchar_t *v18; // rax
  __int64 v19; // rcx
  wchar_t *v20; // rcx
  wchar_t *v21; // rax
  const wchar_t *v22; // rcx
  wchar_t *v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // r15
  __int64 v26; // r14
  const wchar_t *v27; // rbx
  const wchar_t *v28; // r12
  const wchar_t *v29; // rax
  int v30; // ebx
  _DWORD *v31; // rax
  unsigned __int64 v32; // rdi
  DWORD v33; // edx
  char *DriverDirectory; // r12
  int v35; // esi
  unsigned int v36; // r14d
  _QWORD *v37; // r15
  HLOCAL hMem; // [rsp+20h] [rbp-A9h] BYREF
  const wchar_t *v40; // [rsp+28h] [rbp-A1h]
  _QWORD v41[8]; // [rsp+30h] [rbp-99h] BYREF
  wchar_t String2[20]; // [rsp+70h] [rbp-59h] BYREF
  wchar_t v43[20]; // [rsp+98h] [rbp-31h] BYREF
  wchar_t v44[20]; // [rsp+C0h] [rbp-9h] BYREF

  v3 = a2;
  v40 = a2;
  memset_0(v41, 0, sizeof(v41));
  hMem = 0;
  if ( !BProcessPrinterIniFile(v5, a3, &hMem) )
  {
    v6 = 0;
LABEL_44:
    v32 = 0;
    goto LABEL_45;
  }
  v6 = (wchar_t *)hMem;
  v7 = 0;
  if ( hMem )
  {
    v8 = 2147483646;
    v9 = 20;
    v10 = 2147483646;
    v11 = L"OEMDriverFile1";
    v12 = 20;
    v13 = String2;
    do
    {
      if ( !v10 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v10;
      --v12;
    }
    while ( v12 );
    v14 = v12 == 0;
    v15 = v13 - 1;
    v16 = L"OEMConfigFile1";
    v17 = 20;
    if ( !v14 )
      v15 = v13;
    v18 = v43;
    *v15 = 0;
    v19 = 2147483646;
    do
    {
      if ( !v19 )
        break;
      if ( !*v16 )
        break;
      *v18++ = *v16++;
      --v19;
      --v17;
    }
    while ( v17 );
    v20 = v18 - 1;
    if ( v17 )
      v20 = v18;
    v21 = v44;
    *v20 = 0;
    v22 = L"OEMHelpFile1";
    do
    {
      if ( !v8 )
        break;
      if ( !*v22 )
        break;
      *v21++ = *v22++;
      --v8;
      --v9;
    }
    while ( v9 );
    v23 = v21 - 1;
    if ( v9 )
      v23 = v21;
    v24 = -1;
    *v23 = 0;
    v25 = -1;
    do
      ++v25;
    while ( String2[v25] );
    v26 = -1;
    do
      ++v26;
    while ( v43[v26] );
    do
      ++v24;
    while ( v44[v24] );
    do
    {
      v27 = PtstrSearchStringInMultiSZPair(v6, String2);
      v41[v7] = v27;
      v28 = PtstrSearchStringInMultiSZPair(v6, v43);
      v29 = PtstrSearchStringInMultiSZPair(v6, v44);
      if ( !v27 && !v28 && !v29 )
        break;
      ++*((_WORD *)&v41[7] + v25 + 3);
      ++v7;
      ++String2[v26 + 19];
      ++v43[v24 + 19];
    }
    while ( v7 < 8 );
    v3 = v40;
  }
  v30 = v7 < 8;
  if ( !v30 )
    goto LABEL_44;
  v31 = LocalAlloc(0x40u, 176LL * v7 + 24);
  v32 = (unsigned __int64)v31;
  if ( !v31 )
  {
LABEL_45:
    v30 = 0;
    goto LABEL_46;
  }
  v31[2] = v7;
  if ( !v7 )
    goto LABEL_46;
  DriverDirectory = PtstrGetDriverDirectory(v3);
  if ( !DriverDirectory )
  {
    v30 = 0;
LABEL_42:
    VFreeOemPluginInfoInternal((_DWORD *)v32, v33);
    v32 = 0;
    goto LABEL_46;
  }
  v35 = *(_DWORD *)(v32 + 8);
  if ( v35 )
  {
    v36 = 0;
    v37 = (_QWORD *)(v32 + 24);
    do
    {
      if ( v36 < 8 )
      {
        v30 = BExpandOemFilename(v37, (_WORD *)v41[v36], DriverDirectory);
        if ( !v30 )
          break;
      }
      ++v36;
      v37 += 22;
      --v35;
    }
    while ( v35 );
  }
  LocalFree(DriverDirectory);
  if ( !v30 )
    goto LABEL_42;
LABEL_46:
  if ( v6 )
    LocalFree(v6);
  return v32 & -(__int64)(v30 != 0);
}

```

## disassembly

```asm
0x18003224c  mov     [rsp-8+arg_0], rbx
0x180032251  push    rbp
0x180032252  push    rsi
0x180032253  push    rdi
0x180032254  push    r12
0x180032256  push    r13
0x180032258  push    r14
0x18003225a  push    r15
0x18003225c  lea     rbp, [rsp-27h]
0x180032261  sub     rsp, 0F0h
0x180032268  mov     rax, cs:__security_cookie
0x18003226f  xor     rax, rsp
0x180032272  mov     [rbp+57h+var_38], rax
0x180032276  mov     r14, rdx
0x180032279  mov     [rsp+120h+var_F8], rdx
0x18003227e  xor     edx, edx; Val
0x180032280  lea     rcx, [rsp+120h+var_F0]; void *
0x180032285  mov     rbx, r8
0x180032288  lea     r8d, [rdx+40h]; Size
0x18003228c  call    memset_0
0x180032291  xor     r15d, r15d
0x180032294  lea     r8, [rsp+120h+hMem]
0x180032299  mov     rdx, rbx
0x18003229c  mov     [rsp+120h+hMem], r15
0x1800322a1  call    BProcessPrinterIniFile
0x1800322a6  test    eax, eax
0x1800322a8  jz      loc_1800324E8
0x1800322ae  mov     r13, [rsp+120h+hMem]
0x1800322b3  lea     r12d, [r15+1]
0x1800322b7  mov     esi, r15d
0x1800322ba  test    r13, r13
0x1800322bd  jz      loc_180032435
0x1800322c3  mov     r8d, 7FFFFFFEh
0x1800322c9  lea     edx, [r15+14h]
0x1800322cd  mov     ecx, r8d
0x1800322d0  lea     r10, aOemdriverfile1; "OEMDriverFile1"
0x1800322d7  mov     r9d, edx
0x1800322da  lea     rax, [rbp+57h+String2]
0x1800322de  test    rcx, rcx
0x1800322e1  jz      short loc_180032301
0x1800322e3  movzx   r11d, word ptr [r10]
0x1800322e7  test    r11w, r11w
0x1800322eb  jz      short loc_180032301
0x1800322ed  mov     [rax], r11w
0x1800322f1  add     r10, 2
0x1800322f5  add     rax, 2
0x1800322f9  sub     rcx, r12
0x1800322fc  sub     r9, r12
0x1800322ff  jnz     short loc_1800322DE
0x180032301  test    r9, r9
0x180032304  lea     rcx, [rax-2]
0x180032308  lea     r10, aOemconfigfile1; "OEMConfigFile1"
0x18003230f  mov     r9, rdx
0x180032312  cmovnz  rcx, rax
0x180032316  lea     rax, [rbp+57h+var_88]
0x18003231a  mov     [rcx], r15w
0x18003231e  mov     rcx, r8
0x180032321  test    rcx, rcx
0x180032324  jz      short loc_180032344
0x180032326  movzx   r11d, word ptr [r10]
0x18003232a  test    r11w, r11w
0x18003232e  jz      short loc_180032344
0x180032330  mov     [rax], r11w
0x180032334  add     r10, 2
0x180032338  add     rax, 2
0x18003233c  sub     rcx, r12
0x18003233f  sub     r9, r12
0x180032342  jnz     short loc_180032321
0x180032344  lea     rcx, [rax-2]
0x180032348  test    r9, r9
0x18003234b  cmovnz  rcx, rax
0x18003234f  lea     rax, [rbp+57h+var_60]
0x180032353  mov     [rcx], r15w
0x180032357  lea     rcx, aOemhelpfile1; "OEMHelpFile1"
0x18003235e  test    r8, r8
0x180032361  jz      short loc_180032381
0x180032363  movzx   r9d, word ptr [rcx]
0x180032367  test    r9w, r9w
0x18003236b  jz      short loc_180032381
0x18003236d  mov     [rax], r9w
0x180032371  add     rcx, 2
0x180032375  add     rax, 2
0x180032379  sub     r8, r12
0x18003237c  sub     rdx, r12
0x18003237f  jnz     short loc_18003235E
0x180032381  test    rdx, rdx
0x180032384  lea     rcx, [rax-2]
0x180032388  cmovnz  rcx, rax
0x18003238c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180032390  xor     eax, eax
0x180032392  mov     [rcx], r15w
0x180032396  lea     rcx, [rbp+57h+String2]
0x18003239a  mov     r15, rdi
0x18003239d  inc     r15
0x1800323a0  cmp     [rcx+r15*2], ax
0x1800323a5  jnz     short loc_18003239D
0x1800323a7  lea     rcx, [rbp+57h+var_88]
0x1800323ab  mov     r14, rdi
0x1800323ae  inc     r14
0x1800323b1  cmp     [rcx+r14*2], ax
0x1800323b6  jnz     short loc_1800323AE
0x1800323b8  lea     rcx, [rbp+57h+var_60]
0x1800323bc  inc     rdi
0x1800323bf  cmp     [rcx+rdi*2], ax
0x1800323c3  jnz     short loc_1800323BC
0x1800323c5  lea     rdx, [rbp+57h+String2]; String2
0x1800323c9  mov     rcx, r13; String1
0x1800323cc  call    PtstrSearchStringInMultiSZPair
0x1800323d1  mov     ecx, esi
0x1800323d3  lea     rdx, [rbp+57h+var_88]; String2
0x1800323d7  mov     rbx, rax
0x1800323da  mov     [rsp+rcx*8+120h+var_F0], rax
0x1800323df  mov     rcx, r13; String1
0x1800323e2  call    PtstrSearchStringInMultiSZPair
0x1800323e7  lea     rdx, [rbp+57h+var_60]; String2
0x1800323eb  mov     rcx, r13; String1
0x1800323ee  mov     r12, rax
0x1800323f1  call    PtstrSearchStringInMultiSZPair
0x1800323f6  test    rbx, rbx
0x1800323f9  jnz     short loc_180032405
0x1800323fb  test    r12, r12
0x1800323fe  jnz     short loc_180032405
0x180032400  test    rax, rax
0x180032403  jz      short loc_180032427
0x180032405  mov     r12d, 1
0x18003240b  add     [rbp+r15*2+57h+var_B2], r12w
0x180032411  add     esi, r12d
0x180032414  add     [rbp+r14*2+57h+var_8A], r12w
0x18003241a  add     [rbp+rdi*2+57h+var_62], r12w
0x180032420  cmp     esi, 8
0x180032423  jb      short loc_1800323C5
0x180032425  jmp     short loc_18003242D
0x180032427  mov     r12d, 1
0x18003242d  mov     r14, [rsp+120h+var_F8]
0x180032432  xor     r15d, r15d
0x180032435  cmp     esi, 8
0x180032438  sbb     ebx, ebx
0x18003243a  and     ebx, r12d
0x18003243d  jz      loc_1800324EB
0x180032443  mov     eax, esi
0x180032445  mov     ecx, 40h ; '@'; uFlags
0x18003244a  imul    rdx, rax, 0B0h
0x180032451  add     rdx, 18h; uBytes
0x180032455  call    cs:__imp_LocalAlloc
0x18003245c  nop     dword ptr [rax+rax+00h]
0x180032461  mov     rdi, rax
0x180032464  test    rax, rax
0x180032467  jz      loc_1800324EE
0x18003246d  mov     [rax+8], esi
0x180032470  test    esi, esi
0x180032472  jz      short loc_1800324F1
0x180032474  mov     rcx, r14; Src
0x180032477  call    PtstrGetDriverDirectory
0x18003247c  mov     r12, rax
0x18003247f  test    rax, rax
0x180032482  jnz     short loc_180032489
0x180032484  mov     ebx, r15d
0x180032487  jmp     short loc_1800324DB
0x180032489  mov     esi, [rdi+8]
0x18003248c  test    esi, esi
0x18003248e  jz      short loc_1800324C8
0x180032490  mov     r14d, r15d
0x180032493  lea     r15, [rdi+18h]
0x180032497  cmp     r14d, 8
0x18003249b  jnb     short loc_1800324B6
0x18003249d  mov     edx, r14d
0x1800324a0  mov     r8, r12
0x1800324a3  mov     rcx, r15
0x1800324a6  mov     rdx, [rsp+rdx*8+120h+var_F0]
0x1800324ab  call    BExpandOemFilename
0x1800324b0  mov     ebx, eax
0x1800324b2  test    eax, eax
0x1800324b4  jz      short loc_1800324C5
0x1800324b6  inc     r14d
0x1800324b9  add     r15, 0B0h
0x1800324c0  add     esi, 0FFFFFFFFh
0x1800324c3  jnz     short loc_180032497
0x1800324c5  xor     r15d, r15d
0x1800324c8  mov     rcx, r12; hMem
0x1800324cb  call    cs:__imp_LocalFree
0x1800324d2  nop     dword ptr [rax+rax+00h]
0x1800324d7  test    ebx, ebx
0x1800324d9  jnz     short loc_1800324F1
0x1800324db  mov     rcx, rdi
0x1800324de  call    VFreeOemPluginInfoInternal
0x1800324e3  mov     rdi, r15
0x1800324e6  jmp     short loc_1800324F1
0x1800324e8  mov     r13, r15
0x1800324eb  mov     rdi, r15
0x1800324ee  mov     ebx, r15d
0x1800324f1  test    r13, r13
0x1800324f4  jz      short loc_180032505
0x1800324f6  mov     rcx, r13; hMem
0x1800324f9  call    cs:__imp_LocalFree
0x180032500  nop     dword ptr [rax+rax+00h]
0x180032505  neg     ebx
0x180032507  sbb     rax, rax
0x18003250a  and     rax, rdi
0x18003250d  mov     rcx, [rbp+57h+var_38]
0x180032511  xor     rcx, rsp; StackCookie
0x180032514  call    __security_check_cookie
0x180032519  mov     rbx, [rsp+120h+arg_0]
0x180032521  add     rsp, 0F0h
0x180032528  pop     r15
0x18003252a  pop     r14
0x18003252c  pop     r13
0x18003252e  pop     r12
0x180032530  pop     rdi
0x180032531  pop     rsi
0x180032532  pop     rbp
0x180032533  retn
```
