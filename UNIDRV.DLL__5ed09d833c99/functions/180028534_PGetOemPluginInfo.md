# PGetOemPluginInfo

- ea: `0x180028534`
- end: `0x180028914`
- name: `PGetOemPluginInfo`
- size: `992`
- prototype: `unsigned __int64 __fastcall(__int64, void *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800280ec`

## callees

- `0x180026ae0`
- `0x180028534`
- `0x18002891c`
- `0x18003a158`
- `0x18003cabc`
- `0x180049d00`
- `0x18004a668`
- `0x18004a71c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800285d2`
- `KERNEL32!LocalFree` at `0x180028787`
- `KERNEL32!LocalFree` at `0x1800285d2`
- `KERNEL32!LocalFree` at `0x180028787`
- `KERNEL32!LocalAlloc` at `0x180028740`
- `KERNEL32!LocalAlloc` at `0x180028740`

## string_xrefs

- `0x180028807`: `OEMConfigFile1`

## pseudocode

```c
__int64 __fastcall PGetOemPluginInfo(__int64 a1, wchar_t *a2, __int64 a3)
{
  const wchar_t *v3; // rsi
  unsigned __int64 v5; // rdi
  struct _FILETIME v6; // rcx
  int v7; // r9d
  wchar_t *v8; // r13
  int v9; // ebx
  __int64 v11; // r15
  const wchar_t *i; // rbx
  int v13; // eax
  __int64 v14; // rcx
  const wchar_t *v15; // rsi
  __int64 v16; // rax
  const wchar_t *v17; // rbx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  char *v21; // rbx
  const wchar_t *j; // rbx
  int v23; // edx
  __int64 v24; // rcx
  const wchar_t *v25; // rax
  __int64 v26; // rcx
  wchar_t *v27; // rax
  unsigned int v28; // r14d
  _DWORD *v29; // rax
  DWORD v30; // edx
  char *DriverDirectory; // r12
  int v32; // esi
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 v36; // r9
  const wchar_t *v37; // r10
  wchar_t *v38; // rax
  bool v39; // zf
  wchar_t *v40; // rcx
  const wchar_t *v41; // r10
  __int64 v42; // r9
  wchar_t *v43; // rax
  __int64 v44; // rcx
  wchar_t *v45; // rcx
  wchar_t *v46; // rax
  const wchar_t *v47; // rcx
  wchar_t *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r12
  __int64 v51; // r14
  _QWORD *v52; // r15
  wchar_t *String1; // [rsp+20h] [rbp-A9h] BYREF
  void *Src; // [rsp+28h] [rbp-A1h]
  _QWORD v55[8]; // [rsp+30h] [rbp-99h] BYREF
  wchar_t String2[20]; // [rsp+70h] [rbp-59h] BYREF
  wchar_t v57[20]; // [rsp+98h] [rbp-31h] BYREF
  wchar_t v58[20]; // [rsp+C0h] [rbp-9h] BYREF

  v3 = a2;
  Src = a2;
  memset_0(v55, 0, sizeof(v55));
  v5 = 0;
  String1 = 0;
  if ( !BProcessPrinterIniFile(v6, a3, &String1, v7) )
  {
    v8 = 0;
LABEL_3:
    v9 = 0;
    goto LABEL_4;
  }
  v8 = String1;
  v28 = 0;
  if ( !String1 )
    goto LABEL_38;
  v33 = 20;
  v34 = 2147483646;
  v35 = 2147483646;
  v36 = 20;
  v37 = L"OEMDriverFile1";
  v38 = String2;
  do
  {
    if ( !v35 )
      break;
    if ( !*v37 )
      break;
    *v38++ = *v37++;
    --v35;
    --v36;
  }
  while ( v36 );
  v39 = v36 == 0;
  v40 = v38 - 1;
  v41 = L"OEMConfigFile1";
  v42 = 20;
  if ( !v39 )
    v40 = v38;
  v43 = v57;
  *v40 = 0;
  v44 = 2147483646;
  do
  {
    if ( !v44 )
      break;
    if ( !*v41 )
      break;
    *v43++ = *v41++;
    --v44;
    --v42;
  }
  while ( v42 );
  v45 = v43 - 1;
  if ( v42 )
    v45 = v43;
  v46 = v58;
  *v45 = 0;
  v47 = L"OEMHelpFile1";
  do
  {
    if ( !v34 )
      break;
    if ( !*v47 )
      break;
    *v46++ = *v47++;
    --v34;
    --v33;
  }
  while ( v33 );
  v48 = v46 - 1;
  if ( v33 )
    v48 = v46;
  v49 = -1;
  *v48 = 0;
  do
    ++v49;
  while ( String2[v49] );
  String1 = (wchar_t *)v49;
  v50 = -1;
  do
    ++v50;
  while ( v57[v50] );
  v11 = -1;
  do
    ++v11;
  while ( v58[v11] );
  while ( 1 )
  {
    for ( i = v8; *i; i = &v15[v16 + 1] )
    {
      v13 = wcsicmp(i, String2);
      v14 = -1;
      do
        ++v14;
      while ( i[v14] );
      v15 = &i[v14 + 1];
      if ( !v13 )
        goto LABEL_17;
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
    }
    v15 = 0;
LABEL_17:
    v17 = v8;
    v55[v28] = v15;
    while ( *v17 )
    {
      v18 = wcsicmp(v17, v57);
      v19 = -1;
      do
        ++v19;
      while ( v17[v19] );
      v5 = (unsigned __int64)&v17[v19 + 1];
      if ( !v18 )
        break;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)(v5 + 2 * v20) );
      v21 = (char *)(v5 + 2);
      v5 = 0;
      v17 = (const wchar_t *)&v21[2 * v20];
    }
    for ( j = v8; *j; j = &v25[v26 + 1] )
    {
      v23 = wcsicmp(j, v58);
      v24 = -1;
      do
        ++v24;
      while ( j[v24] );
      v25 = &j[v24 + 1];
      if ( !v23 )
        goto LABEL_34;
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
    }
    v25 = 0;
LABEL_34:
    if ( !v15 && !v5 )
      break;
    v5 = 0;
LABEL_36:
    v27 = String1;
    ++String2[v50 + 19];
    ++v28;
    ++v57[v11 + 19];
    ++*((_WORD *)&v55[7] + (_QWORD)v27 + 3);
    if ( v28 >= 8 )
      goto LABEL_37;
  }
  if ( v25 )
    goto LABEL_36;
LABEL_37:
  v3 = (const wchar_t *)Src;
LABEL_38:
  v9 = v28 < 8;
  if ( !v9 )
    goto LABEL_3;
  v29 = LocalAlloc(0x40u, 176LL * v28 + 24);
  v5 = (unsigned __int64)v29;
  if ( !v29 )
    goto LABEL_3;
  v29[2] = v28;
  if ( v28 )
  {
    DriverDirectory = PtstrGetDriverDirectory(v3);
    if ( !DriverDirectory )
    {
      v9 = 0;
      goto LABEL_44;
    }
    v32 = *(_DWORD *)(v5 + 8);
    if ( v32 )
    {
      v51 = 0;
      v52 = (_QWORD *)(v5 + 24);
      do
      {
        if ( (unsigned int)v51 < 8 )
        {
          v9 = BExpandOemFilename(v52, (_WORD *)v55[v51], DriverDirectory);
          if ( !v9 )
            break;
        }
        v51 = (unsigned int)(v51 + 1);
        v52 += 22;
        --v32;
      }
      while ( v32 );
    }
    LocalFree(DriverDirectory);
    if ( !v9 )
    {
LABEL_44:
      VFreeOemPluginInfoInternal((_DWORD *)v5, v30);
      v5 = 0;
    }
  }
LABEL_4:
  if ( v8 )
    LocalFree(v8);
  return v5 & -(__int64)(v9 != 0);
}

```

## disassembly

```asm
0x180028534  mov     [rsp-8+arg_0], rbx
0x180028539  push    rbp
0x18002853a  push    rsi
0x18002853b  push    rdi
0x18002853c  push    r12
0x18002853e  push    r13
0x180028540  push    r14
0x180028542  push    r15
0x180028544  lea     rbp, [rsp-27h]
0x180028549  sub     rsp, 0F0h
0x180028550  mov     rax, cs:__security_cookie
0x180028557  xor     rax, rsp
0x18002855a  mov     [rbp+57h+var_38], rax
0x18002855e  mov     rsi, rdx
0x180028561  mov     [rsp+120h+Src], rdx
0x180028566  xor     edx, edx; Val
0x180028568  lea     rcx, [rsp+120h+var_F0]; void *
0x18002856d  mov     rbx, r8
0x180028570  lea     r8d, [rdx+40h]; Size
0x180028574  call    memset_0
0x180028579  xor     edi, edi
0x18002857b  lea     r8, [rsp+120h+String1]
0x180028580  mov     rdx, rbx
0x180028583  mov     [rsp+120h+String1], rdi
0x180028588  call    BProcessPrinterIniFile
0x18002858d  test    eax, eax
0x18002858f  jnz     loc_1800287AA
0x180028595  mov     r13d, edi
0x180028598  xor     ebx, ebx
0x18002859a  test    r13, r13
0x18002859d  jnz     short loc_1800285CF
0x18002859f  neg     ebx
0x1800285a1  sbb     rax, rax
0x1800285a4  and     rax, rdi
0x1800285a7  mov     rcx, [rbp+57h+var_38]
0x1800285ab  xor     rcx, rsp; StackCookie
0x1800285ae  call    __security_check_cookie
0x1800285b3  mov     rbx, [rsp+120h+arg_0]
0x1800285bb  add     rsp, 0F0h
0x1800285c2  pop     r15
0x1800285c4  pop     r14
0x1800285c6  pop     r13
0x1800285c8  pop     r12
0x1800285ca  pop     rdi
0x1800285cb  pop     rsi
0x1800285cc  pop     rbp
0x1800285cd  retn
0x1800285cf  mov     rcx, r13; hMem
0x1800285d2  call    cs:__imp_LocalFree
0x1800285d9  nop     dword ptr [rax+rax+00h]
0x1800285de  jmp     short loc_18002859F
0x1800285e0  lea     rax, [rbp+57h+var_60]
0x1800285e4  mov     r15, r9
0x1800285e7  inc     r15
0x1800285ea  cmp     [rax+r15*2], di
0x1800285ef  jnz     short loc_1800285E7
0x1800285f1  mov     rbx, r13
0x1800285f4  cmp     [rbx], di
0x1800285f7  jz      short loc_180028637
0x1800285f9  lea     rdx, [rbp+57h+String2]; String2
0x1800285fd  mov     rcx, rbx; String1
0x180028600  call    _wcsicmp
0x180028605  or      r9, 0FFFFFFFFFFFFFFFFh
0x180028609  mov     rcx, r9
0x18002860c  inc     rcx
0x18002860f  cmp     [rbx+rcx*2], di
0x180028613  jnz     short loc_18002860C
0x180028615  lea     rsi, [rcx+1]
0x180028619  lea     rsi, [rbx+rsi*2]
0x18002861d  test    eax, eax
0x18002861f  jz      short loc_18002863A
0x180028621  mov     rax, r9
0x180028624  inc     rax
0x180028627  cmp     [rsi+rax*2], di
0x18002862b  jnz     short loc_180028624
0x18002862d  lea     rbx, [rax+1]
0x180028631  lea     rbx, [rsi+rbx*2]
0x180028635  jmp     short loc_1800285F4
0x180028637  mov     rsi, rdi
0x18002863a  mov     eax, r14d
0x18002863d  mov     rbx, r13
0x180028640  mov     [rsp+rax*8+120h+var_F0], rsi
0x180028645  cmp     [rbx], di
0x180028648  jz      short loc_18002868E
0x18002864a  lea     rdx, [rbp+57h+var_88]; String2
0x18002864e  mov     rcx, rbx; String1
0x180028651  call    _wcsicmp
0x180028656  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002865a  mov     rcx, r9
0x18002865d  inc     rcx
0x180028660  cmp     [rbx+rcx*2], di
0x180028664  jnz     short loc_18002865D
0x180028666  xor     r8d, r8d
0x180028669  lea     rdi, [rcx+1]
0x18002866d  lea     rdi, [rbx+rdi*2]
0x180028671  test    eax, eax
0x180028673  jz      short loc_180028691
0x180028675  mov     rax, r9
0x180028678  inc     rax
0x18002867b  cmp     [rdi+rax*2], r8w
0x180028680  jnz     short loc_180028678
0x180028682  lea     rbx, [rdi+2]
0x180028686  xor     edi, edi
0x180028688  lea     rbx, [rbx+rax*2]
0x18002868c  jmp     short loc_180028645
0x18002868e  xor     r8d, r8d
0x180028691  mov     rbx, r13
0x180028694  cmp     [rbx], r8w
0x180028698  jz      short loc_1800286DF
0x18002869a  lea     rdx, [rbp+57h+var_60]; String2
0x18002869e  mov     rcx, rbx; String1
0x1800286a1  call    _wcsicmp
0x1800286a6  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800286aa  mov     edx, eax
0x1800286ac  mov     rcx, r9
0x1800286af  xor     r8d, r8d
0x1800286b2  inc     rcx
0x1800286b5  cmp     [rbx+rcx*2], r8w
0x1800286ba  jnz     short loc_1800286B2
0x1800286bc  lea     rax, [rcx+1]
0x1800286c0  lea     rax, [rbx+rax*2]
0x1800286c4  test    edx, edx
0x1800286c6  jz      short loc_1800286E2
0x1800286c8  mov     rcx, r9
0x1800286cb  inc     rcx
0x1800286ce  cmp     [rax+rcx*2], r8w
0x1800286d3  jnz     short loc_1800286CB
0x1800286d5  lea     rbx, [rcx+1]
0x1800286d9  lea     rbx, [rax+rbx*2]
0x1800286dd  jmp     short loc_180028694
0x1800286df  mov     rax, r8
0x1800286e2  test    rsi, rsi
0x1800286e5  jz      loc_1800288BB
0x1800286eb  xor     edi, edi
0x1800286ed  mov     rax, [rsp+120h+String1]
0x1800286f2  mov     esi, 1
0x1800286f7  add     [rbp+r12*2+57h+var_8A], si
0x1800286fd  add     r14d, esi
0x180028700  add     [rbp+r15*2+57h+var_62], si
0x180028706  add     [rbp+rax*2+57h+var_B2], si
0x18002870b  cmp     r14d, 8
0x18002870f  jb      loc_1800285F1
0x180028715  mov     rsi, [rsp+120h+Src]
0x18002871a  mov     eax, 1
0x18002871f  cmp     r14d, 8
0x180028723  sbb     ebx, ebx
0x180028725  and     ebx, eax
0x180028727  jz      loc_180028598
0x18002872d  mov     eax, r14d
0x180028730  mov     ecx, 40h ; '@'; uFlags
0x180028735  imul    rdx, rax, 0B0h
0x18002873c  add     rdx, 18h; uBytes
0x180028740  call    cs:__imp_LocalAlloc
0x180028747  nop     dword ptr [rax+rax+00h]
0x18002874c  mov     rdi, rax
0x18002874f  test    rax, rax
0x180028752  jz      loc_180028598
0x180028758  mov     [rax+8], r14d
0x18002875c  test    r14d, r14d
0x18002875f  jz      loc_18002859A
0x180028765  mov     rcx, rsi; Src
0x180028768  call    PtstrGetDriverDirectory
0x18002876d  mov     r12, rax
0x180028770  test    rax, rax
0x180028773  jz      loc_1800288D2
0x180028779  mov     esi, [rdi+8]
0x18002877c  test    esi, esi
0x18002877e  jnz     loc_1800288D9
0x180028784  mov     rcx, r12; hMem
0x180028787  call    cs:__imp_LocalFree
0x18002878e  nop     dword ptr [rax+rax+00h]
0x180028793  test    ebx, ebx
0x180028795  jnz     loc_18002859A
0x18002879b  mov     rcx, rdi
0x18002879e  call    VFreeOemPluginInfoInternal
0x1800287a3  xor     edi, edi
0x1800287a5  jmp     loc_18002859A
0x1800287aa  mov     r13, [rsp+120h+String1]
0x1800287af  mov     r14d, edi
0x1800287b2  mov     eax, 1
0x1800287b7  test    r13, r13
0x1800287ba  jz      loc_18002871F
0x1800287c0  lea     edx, [rax+13h]
0x1800287c3  mov     r8d, 7FFFFFFEh
0x1800287c9  mov     ecx, r8d
0x1800287cc  lea     esi, [rdx-13h]
0x1800287cf  mov     r9d, edx
0x1800287d2  lea     r10, aOemdriverfile1; "OEMDriverFile1"
0x1800287d9  lea     rax, [rbp+57h+String2]
0x1800287dd  test    rcx, rcx
0x1800287e0  jz      short loc_180028800
0x1800287e2  movzx   r11d, word ptr [r10]
0x1800287e6  test    r11w, r11w
0x1800287ea  jz      short loc_180028800
0x1800287ec  mov     [rax], r11w
0x1800287f0  add     r10, 2
0x1800287f4  add     rax, 2
0x1800287f8  sub     rcx, rsi
0x1800287fb  sub     r9, rsi
0x1800287fe  jnz     short loc_1800287DD
0x180028800  test    r9, r9
0x180028803  lea     rcx, [rax-2]
0x180028807  lea     r10, aOemconfigfile1; "OEMConfigFile1"
0x18002880e  mov     r9, rdx
0x180028811  cmovnz  rcx, rax
0x180028815  lea     rax, [rbp+57h+var_88]
0x180028819  mov     [rcx], di
0x18002881c  mov     rcx, r8
0x18002881f  test    rcx, rcx
0x180028822  jz      short loc_180028842
0x180028824  movzx   r11d, word ptr [r10]
0x180028828  test    r11w, r11w
0x18002882c  jz      short loc_180028842
0x18002882e  mov     [rax], r11w
0x180028832  add     r10, 2
0x180028836  add     rax, 2
0x18002883a  sub     rcx, rsi
0x18002883d  sub     r9, rsi
0x180028840  jnz     short loc_18002881F
0x180028842  lea     rcx, [rax-2]
0x180028846  test    r9, r9
0x180028849  cmovnz  rcx, rax
0x18002884d  lea     rax, [rbp+57h+var_60]
0x180028851  mov     [rcx], di
0x180028854  lea     rcx, aOemhelpfile1; "OEMHelpFile1"
0x18002885b  test    r8, r8
0x18002885e  jz      short loc_18002887E
0x180028860  movzx   r9d, word ptr [rcx]
0x180028864  test    r9w, r9w
0x180028868  jz      short loc_18002887E
0x18002886a  mov     [rax], r9w
0x18002886e  add     rcx, 2
0x180028872  add     rax, 2
0x180028876  sub     r8, rsi
0x180028879  sub     rdx, rsi
0x18002887c  jnz     short loc_18002885B
0x18002887e  test    rdx, rdx
0x180028881  lea     rcx, [rax-2]
0x180028885  cmovnz  rcx, rax
0x180028889  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002888d  mov     rax, r9
0x180028890  mov     [rcx], di
0x180028893  lea     rcx, [rbp+57h+String2]
0x180028897  inc     rax
0x18002889a  cmp     [rcx+rax*2], di
0x18002889e  jnz     short loc_180028897
0x1800288a0  mov     [rsp+120h+String1], rax
0x1800288a5  mov     r12, r9
0x1800288a8  lea     rax, [rbp+57h+var_88]
0x1800288ac  inc     r12
0x1800288af  cmp     [rax+r12*2], di
0x1800288b4  jnz     short loc_1800288AC
0x1800288b6  jmp     loc_1800285E0
0x1800288bb  test    rdi, rdi
0x1800288be  jnz     loc_1800286EB
0x1800288c4  test    rax, rax
0x1800288c7  jz      loc_180028715
0x1800288cd  jmp     loc_1800286ED
0x1800288d2  xor     ebx, ebx
0x1800288d4  jmp     loc_18002879B
0x1800288d9  xor     r14d, r14d
0x1800288dc  lea     r15, [rdi+18h]
0x1800288e0  cmp     r14d, 8
0x1800288e4  jnb     short loc_180028900
0x1800288e6  mov     rdx, [rsp+r14*8+120h+var_F0]
0x1800288eb  mov     r8, r12
0x1800288ee  mov     rcx, r15
0x1800288f1  call    BExpandOemFilename
0x1800288f6  mov     ebx, eax
0x1800288f8  test    eax, eax
0x1800288fa  jz      loc_180028784
0x180028900  inc     r14d
0x180028903  add     r15, 0B0h
0x18002890a  add     esi, 0FFFFFFFFh
0x18002890d  jnz     short loc_1800288E0
0x18002890f  jmp     loc_180028784
```
