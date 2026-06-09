# PGetOemPluginInfo

- ea: `0x180027d9c`
- end: `0x180028169`
- name: `PGetOemPluginInfo`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180027964`

## callees

- `0x1800263fc`
- `0x180027d9c`
- `0x180028170`
- `0x18003969c`
- `0x18003bcf4`
- `0x1800487e0`
- `0x180049128`
- `0x1800491dc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180027e39`
- `KERNEL32!LocalFree` at `0x180027fe2`
- `KERNEL32!LocalFree` at `0x180027e39`
- `KERNEL32!LocalFree` at `0x180027fe2`
- `KERNEL32!LocalAlloc` at `0x180027fa1`
- `KERNEL32!LocalAlloc` at `0x180027fa1`

## string_xrefs

- `0x18002805c`: `OEMConfigFile1`

## pseudocode

```c
__int64 __fastcall PGetOemPluginInfo(__int64 a1, void *a2, __int64 a3)
{
  void *v3; // rsi
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
  const wchar_t *v21; // rbx
  const wchar_t *j; // rbx
  int v23; // edx
  __int64 v24; // rcx
  const wchar_t *v25; // rax
  __int64 v26; // rcx
  wchar_t *v27; // rax
  unsigned int v28; // r14d
  const wchar_t *v29; // rax
  void *DriverDirectory; // r12
  int v31; // esi
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // r9
  const wchar_t *v36; // r10
  wchar_t *v37; // rax
  bool v38; // zf
  wchar_t *v39; // rcx
  const wchar_t *v40; // r10
  __int64 v41; // r9
  wchar_t *v42; // rax
  __int64 v43; // rcx
  wchar_t *v44; // rcx
  wchar_t *v45; // rax
  const wchar_t *v46; // rcx
  wchar_t *v47; // rcx
  __int64 v48; // rax
  __int64 v49; // r12
  __int64 v50; // r14
  const wchar_t *v51; // r15
  wchar_t *String1; // [rsp+20h] [rbp-A9h] BYREF
  void *Src; // [rsp+28h] [rbp-A1h]
  _QWORD v54[8]; // [rsp+30h] [rbp-99h] BYREF
  wchar_t String2[20]; // [rsp+70h] [rbp-59h] BYREF
  wchar_t v56[20]; // [rsp+98h] [rbp-31h] BYREF
  wchar_t v57[20]; // [rsp+C0h] [rbp-9h] BYREF

  v3 = a2;
  Src = a2;
  memset_0(v54, 0, sizeof(v54));
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
  v32 = 20;
  v33 = 2147483646;
  v34 = 2147483646;
  v35 = 20;
  v36 = L"OEMDriverFile1";
  v37 = String2;
  do
  {
    if ( !v34 )
      break;
    if ( !*v36 )
      break;
    *v37++ = *v36++;
    --v34;
    --v35;
  }
  while ( v35 );
  v38 = v35 == 0;
  v39 = v37 - 1;
  v40 = L"OEMConfigFile1";
  v41 = 20;
  if ( !v38 )
    v39 = v37;
  v42 = v56;
  *v39 = 0;
  v43 = 2147483646;
  do
  {
    if ( !v43 )
      break;
    if ( !*v40 )
      break;
    *v42++ = *v40++;
    --v43;
    --v41;
  }
  while ( v41 );
  v44 = v42 - 1;
  if ( v41 )
    v44 = v42;
  v45 = v57;
  *v44 = 0;
  v46 = L"OEMHelpFile1";
  do
  {
    if ( !v33 )
      break;
    if ( !*v46 )
      break;
    *v45++ = *v46++;
    --v33;
    --v32;
  }
  while ( v32 );
  v47 = v45 - 1;
  if ( v32 )
    v47 = v45;
  v48 = -1;
  *v47 = 0;
  do
    ++v48;
  while ( String2[v48] );
  String1 = (wchar_t *)v48;
  v49 = -1;
  do
    ++v49;
  while ( v56[v49] );
  v11 = -1;
  do
    ++v11;
  while ( v57[v11] );
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
    v54[v28] = v15;
    while ( *v17 )
    {
      v18 = wcsicmp(v17, v56);
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
      v21 = (const wchar_t *)(v5 + 2);
      v5 = 0;
      v17 = &v21[v20];
    }
    for ( j = v8; *j; j = &v25[v26 + 1] )
    {
      v23 = wcsicmp(j, v57);
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
    ++String2[v49 + 19];
    ++v28;
    ++v56[v11 + 19];
    ++*((_WORD *)&v54[7] + (_QWORD)v27 + 3);
    if ( v28 >= 8 )
      goto LABEL_37;
  }
  if ( v25 )
    goto LABEL_36;
LABEL_37:
  v3 = Src;
LABEL_38:
  v9 = v28 < 8;
  if ( !v9 )
    goto LABEL_3;
  v29 = (const wchar_t *)LocalAlloc(0x40u, 176LL * v28 + 24);
  v5 = (unsigned __int64)v29;
  if ( !v29 )
    goto LABEL_3;
  *((_DWORD *)v29 + 2) = v28;
  if ( v28 )
  {
    DriverDirectory = (void *)PtstrGetDriverDirectory(v3);
    if ( !DriverDirectory )
    {
      v9 = 0;
      goto LABEL_44;
    }
    v31 = *(_DWORD *)(v5 + 8);
    if ( v31 )
    {
      v50 = 0;
      v51 = (const wchar_t *)(v5 + 24);
      do
      {
        if ( (unsigned int)v50 < 8 )
        {
          v9 = BExpandOemFilename(v51, v54[v50], DriverDirectory);
          if ( !v9 )
            break;
        }
        v50 = (unsigned int)(v50 + 1);
        v51 += 88;
        --v31;
      }
      while ( v31 );
    }
    LocalFree(DriverDirectory);
    if ( !v9 )
    {
LABEL_44:
      VFreeOemPluginInfoInternal(v5);
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
0x180027d9c  mov     [rsp-8+arg_0], rbx
0x180027da1  push    rbp
0x180027da2  push    rsi
0x180027da3  push    rdi
0x180027da4  push    r12
0x180027da6  push    r13
0x180027da8  push    r14
0x180027daa  push    r15
0x180027dac  lea     rbp, [rsp-27h]
0x180027db1  sub     rsp, 0F0h
0x180027db8  mov     rax, cs:__security_cookie
0x180027dbf  xor     rax, rsp
0x180027dc2  mov     [rbp+57h+var_38], rax
0x180027dc6  mov     rsi, rdx
0x180027dc9  mov     [rsp+120h+Src], rdx
0x180027dce  xor     edx, edx; Val
0x180027dd0  lea     rcx, [rsp+120h+var_F0]; void *
0x180027dd5  mov     rbx, r8
0x180027dd8  lea     r8d, [rdx+40h]; Size
0x180027ddc  call    memset_0
0x180027de1  xor     edi, edi
0x180027de3  lea     r8, [rsp+120h+String1]
0x180027de8  mov     rdx, rbx
0x180027deb  mov     [rsp+120h+String1], rdi
0x180027df0  call    BProcessPrinterIniFile
0x180027df5  test    eax, eax
0x180027df7  jnz     loc_180027FFF
0x180027dfd  mov     r13d, edi
0x180027e00  xor     ebx, ebx
0x180027e02  test    r13, r13
0x180027e05  jnz     short loc_180027E36
0x180027e07  neg     ebx
0x180027e09  sbb     rax, rax
0x180027e0c  and     rax, rdi
0x180027e0f  mov     rcx, [rbp+57h+var_38]
0x180027e13  xor     rcx, rsp; StackCookie
0x180027e16  call    __security_check_cookie
0x180027e1b  mov     rbx, [rsp+120h+arg_0]
0x180027e23  add     rsp, 0F0h
0x180027e2a  pop     r15
0x180027e2c  pop     r14
0x180027e2e  pop     r13
0x180027e30  pop     r12
0x180027e32  pop     rdi
0x180027e33  pop     rsi
0x180027e34  pop     rbp
0x180027e35  retn
0x180027e36  mov     rcx, r13; hMem
0x180027e39  call    cs:__imp_LocalFree
0x180027e3f  jmp     short loc_180027E07
0x180027e41  lea     rax, [rbp+57h+var_60]
0x180027e45  mov     r15, r9
0x180027e48  inc     r15
0x180027e4b  cmp     [rax+r15*2], di
0x180027e50  jnz     short loc_180027E48
0x180027e52  mov     rbx, r13
0x180027e55  cmp     [rbx], di
0x180027e58  jz      short loc_180027E98
0x180027e5a  lea     rdx, [rbp+57h+String2]; String2
0x180027e5e  mov     rcx, rbx; String1
0x180027e61  call    _wcsicmp
0x180027e66  or      r9, 0FFFFFFFFFFFFFFFFh
0x180027e6a  mov     rcx, r9
0x180027e6d  inc     rcx
0x180027e70  cmp     [rbx+rcx*2], di
0x180027e74  jnz     short loc_180027E6D
0x180027e76  lea     rsi, [rcx+1]
0x180027e7a  lea     rsi, [rbx+rsi*2]
0x180027e7e  test    eax, eax
0x180027e80  jz      short loc_180027E9B
0x180027e82  mov     rax, r9
0x180027e85  inc     rax
0x180027e88  cmp     [rsi+rax*2], di
0x180027e8c  jnz     short loc_180027E85
0x180027e8e  lea     rbx, [rax+1]
0x180027e92  lea     rbx, [rsi+rbx*2]
0x180027e96  jmp     short loc_180027E55
0x180027e98  mov     rsi, rdi
0x180027e9b  mov     eax, r14d
0x180027e9e  mov     rbx, r13
0x180027ea1  mov     [rsp+rax*8+120h+var_F0], rsi
0x180027ea6  cmp     [rbx], di
0x180027ea9  jz      short loc_180027EEF
0x180027eab  lea     rdx, [rbp+57h+var_88]; String2
0x180027eaf  mov     rcx, rbx; String1
0x180027eb2  call    _wcsicmp
0x180027eb7  or      r9, 0FFFFFFFFFFFFFFFFh
0x180027ebb  mov     rcx, r9
0x180027ebe  inc     rcx
0x180027ec1  cmp     [rbx+rcx*2], di
0x180027ec5  jnz     short loc_180027EBE
0x180027ec7  xor     r8d, r8d
0x180027eca  lea     rdi, [rcx+1]
0x180027ece  lea     rdi, [rbx+rdi*2]
0x180027ed2  test    eax, eax
0x180027ed4  jz      short loc_180027EF2
0x180027ed6  mov     rax, r9
0x180027ed9  inc     rax
0x180027edc  cmp     [rdi+rax*2], r8w
0x180027ee1  jnz     short loc_180027ED9
0x180027ee3  lea     rbx, [rdi+2]
0x180027ee7  xor     edi, edi
0x180027ee9  lea     rbx, [rbx+rax*2]
0x180027eed  jmp     short loc_180027EA6
0x180027eef  xor     r8d, r8d
0x180027ef2  mov     rbx, r13
0x180027ef5  cmp     [rbx], r8w
0x180027ef9  jz      short loc_180027F40
0x180027efb  lea     rdx, [rbp+57h+var_60]; String2
0x180027eff  mov     rcx, rbx; String1
0x180027f02  call    _wcsicmp
0x180027f07  or      r9, 0FFFFFFFFFFFFFFFFh
0x180027f0b  mov     edx, eax
0x180027f0d  mov     rcx, r9
0x180027f10  xor     r8d, r8d
0x180027f13  inc     rcx
0x180027f16  cmp     [rbx+rcx*2], r8w
0x180027f1b  jnz     short loc_180027F13
0x180027f1d  lea     rax, [rcx+1]
0x180027f21  lea     rax, [rbx+rax*2]
0x180027f25  test    edx, edx
0x180027f27  jz      short loc_180027F43
0x180027f29  mov     rcx, r9
0x180027f2c  inc     rcx
0x180027f2f  cmp     [rax+rcx*2], r8w
0x180027f34  jnz     short loc_180027F2C
0x180027f36  lea     rbx, [rcx+1]
0x180027f3a  lea     rbx, [rax+rbx*2]
0x180027f3e  jmp     short loc_180027EF5
0x180027f40  mov     rax, r8
0x180027f43  test    rsi, rsi
0x180027f46  jz      loc_180028110
0x180027f4c  xor     edi, edi
0x180027f4e  mov     rax, [rsp+120h+String1]
0x180027f53  mov     esi, 1
0x180027f58  add     [rbp+r12*2+57h+var_8A], si
0x180027f5e  add     r14d, esi
0x180027f61  add     [rbp+r15*2+57h+var_62], si
0x180027f67  add     [rbp+rax*2+57h+var_B2], si
0x180027f6c  cmp     r14d, 8
0x180027f70  jb      loc_180027E52
0x180027f76  mov     rsi, [rsp+120h+Src]
0x180027f7b  mov     eax, 1
0x180027f80  cmp     r14d, 8
0x180027f84  sbb     ebx, ebx
0x180027f86  and     ebx, eax
0x180027f88  jz      loc_180027E00
0x180027f8e  mov     eax, r14d
0x180027f91  mov     ecx, 40h ; '@'; uFlags
0x180027f96  imul    rdx, rax, 0B0h
0x180027f9d  add     rdx, 18h; uBytes
0x180027fa1  call    cs:__imp_LocalAlloc
0x180027fa7  mov     rdi, rax
0x180027faa  test    rax, rax
0x180027fad  jz      loc_180027E00
0x180027fb3  mov     [rax+8], r14d
0x180027fb7  test    r14d, r14d
0x180027fba  jz      loc_180027E02
0x180027fc0  mov     rcx, rsi; Src
0x180027fc3  call    PtstrGetDriverDirectory
0x180027fc8  mov     r12, rax
0x180027fcb  test    rax, rax
0x180027fce  jz      loc_180028127
0x180027fd4  mov     esi, [rdi+8]
0x180027fd7  test    esi, esi
0x180027fd9  jnz     loc_18002812E
0x180027fdf  mov     rcx, r12; hMem
0x180027fe2  call    cs:__imp_LocalFree
0x180027fe8  test    ebx, ebx
0x180027fea  jnz     loc_180027E02
0x180027ff0  mov     rcx, rdi
0x180027ff3  call    VFreeOemPluginInfoInternal
0x180027ff8  xor     edi, edi
0x180027ffa  jmp     loc_180027E02
0x180027fff  mov     r13, [rsp+120h+String1]
0x180028004  mov     r14d, edi
0x180028007  mov     eax, 1
0x18002800c  test    r13, r13
0x18002800f  jz      loc_180027F80
0x180028015  lea     edx, [rax+13h]
0x180028018  mov     r8d, 7FFFFFFEh
0x18002801e  mov     ecx, r8d
0x180028021  lea     esi, [rdx-13h]
0x180028024  mov     r9d, edx
0x180028027  lea     r10, aOemdriverfile1; "OEMDriverFile1"
0x18002802e  lea     rax, [rbp+57h+String2]
0x180028032  test    rcx, rcx
0x180028035  jz      short loc_180028055
0x180028037  movzx   r11d, word ptr [r10]
0x18002803b  test    r11w, r11w
0x18002803f  jz      short loc_180028055
0x180028041  mov     [rax], r11w
0x180028045  add     r10, 2
0x180028049  add     rax, 2
0x18002804d  sub     rcx, rsi
0x180028050  sub     r9, rsi
0x180028053  jnz     short loc_180028032
0x180028055  test    r9, r9
0x180028058  lea     rcx, [rax-2]
0x18002805c  lea     r10, aOemconfigfile1; "OEMConfigFile1"
0x180028063  mov     r9, rdx
0x180028066  cmovnz  rcx, rax
0x18002806a  lea     rax, [rbp+57h+var_88]
0x18002806e  mov     [rcx], di
0x180028071  mov     rcx, r8
0x180028074  test    rcx, rcx
0x180028077  jz      short loc_180028097
0x180028079  movzx   r11d, word ptr [r10]
0x18002807d  test    r11w, r11w
0x180028081  jz      short loc_180028097
0x180028083  mov     [rax], r11w
0x180028087  add     r10, 2
0x18002808b  add     rax, 2
0x18002808f  sub     rcx, rsi
0x180028092  sub     r9, rsi
0x180028095  jnz     short loc_180028074
0x180028097  lea     rcx, [rax-2]
0x18002809b  test    r9, r9
0x18002809e  cmovnz  rcx, rax
0x1800280a2  lea     rax, [rbp+57h+var_60]
0x1800280a6  mov     [rcx], di
0x1800280a9  lea     rcx, aOemhelpfile1; "OEMHelpFile1"
0x1800280b0  test    r8, r8
0x1800280b3  jz      short loc_1800280D3
0x1800280b5  movzx   r9d, word ptr [rcx]
0x1800280b9  test    r9w, r9w
0x1800280bd  jz      short loc_1800280D3
0x1800280bf  mov     [rax], r9w
0x1800280c3  add     rcx, 2
0x1800280c7  add     rax, 2
0x1800280cb  sub     r8, rsi
0x1800280ce  sub     rdx, rsi
0x1800280d1  jnz     short loc_1800280B0
0x1800280d3  test    rdx, rdx
0x1800280d6  lea     rcx, [rax-2]
0x1800280da  cmovnz  rcx, rax
0x1800280de  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800280e2  mov     rax, r9
0x1800280e5  mov     [rcx], di
0x1800280e8  lea     rcx, [rbp+57h+String2]
0x1800280ec  inc     rax
0x1800280ef  cmp     [rcx+rax*2], di
0x1800280f3  jnz     short loc_1800280EC
0x1800280f5  mov     [rsp+120h+String1], rax
0x1800280fa  mov     r12, r9
0x1800280fd  lea     rax, [rbp+57h+var_88]
0x180028101  inc     r12
0x180028104  cmp     [rax+r12*2], di
0x180028109  jnz     short loc_180028101
0x18002810b  jmp     loc_180027E41
0x180028110  test    rdi, rdi
0x180028113  jnz     loc_180027F4C
0x180028119  test    rax, rax
0x18002811c  jz      loc_180027F76
0x180028122  jmp     loc_180027F4E
0x180028127  xor     ebx, ebx
0x180028129  jmp     loc_180027FF0
0x18002812e  xor     r14d, r14d
0x180028131  lea     r15, [rdi+18h]
0x180028135  cmp     r14d, 8
0x180028139  jnb     short loc_180028155
0x18002813b  mov     rdx, [rsp+r14*8+120h+var_F0]
0x180028140  mov     r8, r12
0x180028143  mov     rcx, r15
0x180028146  call    BExpandOemFilename
0x18002814b  mov     ebx, eax
0x18002814d  test    eax, eax
0x18002814f  jz      loc_180027FDF
0x180028155  inc     r14d
0x180028158  add     r15, 0B0h
0x18002815f  add     esi, 0FFFFFFFFh
0x180028162  jnz     short loc_180028135
0x180028164  jmp     loc_180027FDF
```
