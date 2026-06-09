# PGetOemPluginInfo

- ea: `0x180030c2c`
- end: `0x180030efe`
- name: `PGetOemPluginInfo`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ed78`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18002dc48`
- `0x18002ef48`
- `0x18002f13c`
- `0x180030480`
- `0x180030c2c`
- `0x180033380`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180030ea1`
- `KERNEL32!LocalFree` at `0x180030ec9`
- `KERNEL32!LocalFree` at `0x180030ea1`
- `KERNEL32!LocalFree` at `0x180030ec9`
- `KERNEL32!LocalAlloc` at `0x180030e35`
- `KERNEL32!LocalAlloc` at `0x180030e35`

## string_xrefs

- `0x180030ce8`: `OEMConfigFile1`

## pseudocode

```c
__int64 __fastcall PGetOemPluginInfo(__int64 a1, void *a2, __int64 a3)
{
  void *v3; // r14
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
  __int64 v27; // rbx
  __int64 v28; // r12
  __int64 v29; // rax
  int v30; // ebx
  _DWORD *v31; // rax
  unsigned __int64 v32; // rdi
  void *DriverDirectory; // r12
  int v34; // esi
  unsigned int v35; // r14d
  _DWORD *v36; // r15
  HLOCAL hMem; // [rsp+20h] [rbp-A9h] BYREF
  void *v39; // [rsp+28h] [rbp-A1h]
  _QWORD v40[8]; // [rsp+30h] [rbp-99h] BYREF
  wchar_t String2[20]; // [rsp+70h] [rbp-59h] BYREF
  wchar_t v42[20]; // [rsp+98h] [rbp-31h] BYREF
  wchar_t v43[20]; // [rsp+C0h] [rbp-9h] BYREF

  v3 = a2;
  v39 = a2;
  memset_0(v40, 0, sizeof(v40));
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
    v18 = v42;
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
    v21 = v43;
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
    while ( v42[v26] );
    do
      ++v24;
    while ( v43[v24] );
    do
    {
      v27 = PtstrSearchStringInMultiSZPair(v6, String2);
      v40[v7] = v27;
      v28 = PtstrSearchStringInMultiSZPair(v6, v42);
      v29 = PtstrSearchStringInMultiSZPair(v6, v43);
      if ( !v27 && !v28 && !v29 )
        break;
      ++*((_WORD *)&v40[7] + v25 + 3);
      ++v7;
      ++String2[v26 + 19];
      ++v42[v24 + 19];
    }
    while ( v7 < 8 );
    v3 = v39;
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
  DriverDirectory = (void *)PtstrGetDriverDirectory(v3);
  if ( !DriverDirectory )
  {
    v30 = 0;
LABEL_42:
    VFreeOemPluginInfoInternal(v32);
    v32 = 0;
    goto LABEL_46;
  }
  v34 = *(_DWORD *)(v32 + 8);
  if ( v34 )
  {
    v35 = 0;
    v36 = (_DWORD *)(v32 + 24);
    do
    {
      if ( v35 < 8 )
      {
        v30 = BExpandOemFilename(v36, v40[v35], DriverDirectory);
        if ( !v30 )
          break;
      }
      ++v35;
      v36 += 44;
      --v34;
    }
    while ( v34 );
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
0x180030c2c  mov     [rsp-8+arg_0], rbx
0x180030c31  push    rbp
0x180030c32  push    rsi
0x180030c33  push    rdi
0x180030c34  push    r12
0x180030c36  push    r13
0x180030c38  push    r14
0x180030c3a  push    r15
0x180030c3c  lea     rbp, [rsp-27h]
0x180030c41  sub     rsp, 0F0h
0x180030c48  mov     rax, cs:__security_cookie
0x180030c4f  xor     rax, rsp
0x180030c52  mov     [rbp+57h+var_38], rax
0x180030c56  mov     r14, rdx
0x180030c59  mov     [rsp+120h+var_F8], rdx
0x180030c5e  xor     edx, edx; Val
0x180030c60  lea     rcx, [rsp+120h+var_F0]; void *
0x180030c65  mov     rbx, r8
0x180030c68  lea     r8d, [rdx+40h]; Size
0x180030c6c  call    memset_0
0x180030c71  xor     r15d, r15d
0x180030c74  lea     r8, [rsp+120h+hMem]
0x180030c79  mov     rdx, rbx
0x180030c7c  mov     [rsp+120h+hMem], r15
0x180030c81  call    BProcessPrinterIniFile
0x180030c86  test    eax, eax
0x180030c88  jz      loc_180030EB8
0x180030c8e  mov     r13, [rsp+120h+hMem]
0x180030c93  lea     r12d, [r15+1]
0x180030c97  mov     esi, r15d
0x180030c9a  test    r13, r13
0x180030c9d  jz      loc_180030E15
0x180030ca3  mov     r8d, 7FFFFFFEh
0x180030ca9  lea     edx, [r15+14h]
0x180030cad  mov     ecx, r8d
0x180030cb0  lea     r10, aOemdriverfile1; "OEMDriverFile1"
0x180030cb7  mov     r9d, edx
0x180030cba  lea     rax, [rbp+57h+String2]
0x180030cbe  test    rcx, rcx
0x180030cc1  jz      short loc_180030CE1
0x180030cc3  movzx   r11d, word ptr [r10]
0x180030cc7  test    r11w, r11w
0x180030ccb  jz      short loc_180030CE1
0x180030ccd  mov     [rax], r11w
0x180030cd1  add     r10, 2
0x180030cd5  add     rax, 2
0x180030cd9  sub     rcx, r12
0x180030cdc  sub     r9, r12
0x180030cdf  jnz     short loc_180030CBE
0x180030ce1  test    r9, r9
0x180030ce4  lea     rcx, [rax-2]
0x180030ce8  lea     r10, aOemconfigfile1; "OEMConfigFile1"
0x180030cef  mov     r9, rdx
0x180030cf2  cmovnz  rcx, rax
0x180030cf6  lea     rax, [rbp+57h+var_88]
0x180030cfa  mov     [rcx], r15w
0x180030cfe  mov     rcx, r8
0x180030d01  test    rcx, rcx
0x180030d04  jz      short loc_180030D24
0x180030d06  movzx   r11d, word ptr [r10]
0x180030d0a  test    r11w, r11w
0x180030d0e  jz      short loc_180030D24
0x180030d10  mov     [rax], r11w
0x180030d14  add     r10, 2
0x180030d18  add     rax, 2
0x180030d1c  sub     rcx, r12
0x180030d1f  sub     r9, r12
0x180030d22  jnz     short loc_180030D01
0x180030d24  lea     rcx, [rax-2]
0x180030d28  test    r9, r9
0x180030d2b  cmovnz  rcx, rax
0x180030d2f  lea     rax, [rbp+57h+var_60]
0x180030d33  mov     [rcx], r15w
0x180030d37  lea     rcx, aOemhelpfile1; "OEMHelpFile1"
0x180030d3e  test    r8, r8
0x180030d41  jz      short loc_180030D61
0x180030d43  movzx   r9d, word ptr [rcx]
0x180030d47  test    r9w, r9w
0x180030d4b  jz      short loc_180030D61
0x180030d4d  mov     [rax], r9w
0x180030d51  add     rcx, 2
0x180030d55  add     rax, 2
0x180030d59  sub     r8, r12
0x180030d5c  sub     rdx, r12
0x180030d5f  jnz     short loc_180030D3E
0x180030d61  test    rdx, rdx
0x180030d64  lea     rcx, [rax-2]
0x180030d68  cmovnz  rcx, rax
0x180030d6c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180030d70  xor     eax, eax
0x180030d72  mov     [rcx], r15w
0x180030d76  lea     rcx, [rbp+57h+String2]
0x180030d7a  mov     r15, rdi
0x180030d7d  inc     r15
0x180030d80  cmp     [rcx+r15*2], ax
0x180030d85  jnz     short loc_180030D7D
0x180030d87  lea     rcx, [rbp+57h+var_88]
0x180030d8b  mov     r14, rdi
0x180030d8e  inc     r14
0x180030d91  cmp     [rcx+r14*2], ax
0x180030d96  jnz     short loc_180030D8E
0x180030d98  lea     rcx, [rbp+57h+var_60]
0x180030d9c  inc     rdi
0x180030d9f  cmp     [rcx+rdi*2], ax
0x180030da3  jnz     short loc_180030D9C
0x180030da5  lea     rdx, [rbp+57h+String2]; String2
0x180030da9  mov     rcx, r13; String1
0x180030dac  call    PtstrSearchStringInMultiSZPair
0x180030db1  mov     ecx, esi
0x180030db3  lea     rdx, [rbp+57h+var_88]; String2
0x180030db7  mov     rbx, rax
0x180030dba  mov     [rsp+rcx*8+120h+var_F0], rax
0x180030dbf  mov     rcx, r13; String1
0x180030dc2  call    PtstrSearchStringInMultiSZPair
0x180030dc7  lea     rdx, [rbp+57h+var_60]; String2
0x180030dcb  mov     rcx, r13; String1
0x180030dce  mov     r12, rax
0x180030dd1  call    PtstrSearchStringInMultiSZPair
0x180030dd6  test    rbx, rbx
0x180030dd9  jnz     short loc_180030DE5
0x180030ddb  test    r12, r12
0x180030dde  jnz     short loc_180030DE5
0x180030de0  test    rax, rax
0x180030de3  jz      short loc_180030E07
0x180030de5  mov     r12d, 1
0x180030deb  add     [rbp+r15*2+57h+var_B2], r12w
0x180030df1  add     esi, r12d
0x180030df4  add     [rbp+r14*2+57h+var_8A], r12w
0x180030dfa  add     [rbp+rdi*2+57h+var_62], r12w
0x180030e00  cmp     esi, 8
0x180030e03  jb      short loc_180030DA5
0x180030e05  jmp     short loc_180030E0D
0x180030e07  mov     r12d, 1
0x180030e0d  mov     r14, [rsp+120h+var_F8]
0x180030e12  xor     r15d, r15d
0x180030e15  cmp     esi, 8
0x180030e18  sbb     ebx, ebx
0x180030e1a  and     ebx, r12d
0x180030e1d  jz      loc_180030EBB
0x180030e23  mov     eax, esi
0x180030e25  mov     ecx, 40h ; '@'; uFlags
0x180030e2a  imul    rdx, rax, 0B0h
0x180030e31  add     rdx, 18h; uBytes
0x180030e35  call    cs:__imp_LocalAlloc
0x180030e3b  mov     rdi, rax
0x180030e3e  test    rax, rax
0x180030e41  jz      short loc_180030EBE
0x180030e43  mov     [rax+8], esi
0x180030e46  test    esi, esi
0x180030e48  jz      short loc_180030EC1
0x180030e4a  mov     rcx, r14; Src
0x180030e4d  call    PtstrGetDriverDirectory
0x180030e52  mov     r12, rax
0x180030e55  test    rax, rax
0x180030e58  jnz     short loc_180030E5F
0x180030e5a  mov     ebx, r15d
0x180030e5d  jmp     short loc_180030EAB
0x180030e5f  mov     esi, [rdi+8]
0x180030e62  test    esi, esi
0x180030e64  jz      short loc_180030E9E
0x180030e66  mov     r14d, r15d
0x180030e69  lea     r15, [rdi+18h]
0x180030e6d  cmp     r14d, 8
0x180030e71  jnb     short loc_180030E8C
0x180030e73  mov     edx, r14d
0x180030e76  mov     r8, r12
0x180030e79  mov     rcx, r15
0x180030e7c  mov     rdx, [rsp+rdx*8+120h+var_F0]
0x180030e81  call    BExpandOemFilename
0x180030e86  mov     ebx, eax
0x180030e88  test    eax, eax
0x180030e8a  jz      short loc_180030E9B
0x180030e8c  inc     r14d
0x180030e8f  add     r15, 0B0h
0x180030e96  add     esi, 0FFFFFFFFh
0x180030e99  jnz     short loc_180030E6D
0x180030e9b  xor     r15d, r15d
0x180030e9e  mov     rcx, r12; hMem
0x180030ea1  call    cs:__imp_LocalFree
0x180030ea7  test    ebx, ebx
0x180030ea9  jnz     short loc_180030EC1
0x180030eab  mov     rcx, rdi
0x180030eae  call    VFreeOemPluginInfoInternal
0x180030eb3  mov     rdi, r15
0x180030eb6  jmp     short loc_180030EC1
0x180030eb8  mov     r13, r15
0x180030ebb  mov     rdi, r15
0x180030ebe  mov     ebx, r15d
0x180030ec1  test    r13, r13
0x180030ec4  jz      short loc_180030ECF
0x180030ec6  mov     rcx, r13; hMem
0x180030ec9  call    cs:__imp_LocalFree
0x180030ecf  neg     ebx
0x180030ed1  sbb     rax, rax
0x180030ed4  and     rax, rdi
0x180030ed7  mov     rcx, [rbp+57h+var_38]
0x180030edb  xor     rcx, rsp; StackCookie
0x180030ede  call    __security_check_cookie
0x180030ee3  mov     rbx, [rsp+120h+arg_0]
0x180030eeb  add     rsp, 0F0h
0x180030ef2  pop     r15
0x180030ef4  pop     r14
0x180030ef6  pop     r13
0x180030ef8  pop     r12
0x180030efa  pop     rdi
0x180030efb  pop     rsi
0x180030efc  pop     rbp
0x180030efd  retn
```
