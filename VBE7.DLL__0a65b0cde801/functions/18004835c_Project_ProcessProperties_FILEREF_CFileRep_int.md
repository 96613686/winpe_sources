# Project::ProcessProperties(FILEREF *,CFileRep *,int *)

- ea: `0x18004835c`
- end: `0x180048a85`
- name: `?ProcessProperties@Project@@AEAAJPEAUFILEREF@@PEAVCFileRep@@PEAH@Z`
- size: `1833`
- prototype: `__int64 __fastcall(Project *__hidden this, struct FILEREF *, struct CFileRep *, int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800438f4`

## callees

- `0x180015ae8`
- `0x1800164ec`
- `0x18001653c`
- `0x18001b8c8`
- `0x18001bf84`
- `0x180020c90`
- `0x180020d44`
- `0x1800411a0`
- `0x180041910`
- `0x18004835c`
- `0x180049950`
- `0x18004afd4`
- `0x18005a514`
- `0x18005a680`
- `0x18005ab18`
- `0x1800d4d48`
- `0x1802cbf5c`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!free` at `0x1800488d3`
- `MSVCR100!free` at `0x1800488d3`
- `MSVCR100!malloc` at `0x1800484f4`
- `MSVCR100!malloc` at `0x18004895d`
- `MSVCR100!malloc` at `0x1800484f4`
- `MSVCR100!malloc` at `0x18004895d`
- `MSVCR100!atoi` at `0x1800483c0`
- `MSVCR100!atoi` at `0x180048615`
- `MSVCR100!atoi` at `0x180048628`
- `MSVCR100!atoi` at `0x180048749`
- `MSVCR100!atoi` at `0x180048769`
- `MSVCR100!atoi` at `0x180048781`
- `MSVCR100!atoi` at `0x180048799`
- `MSVCR100!atoi` at `0x180048845`
- `MSVCR100!atoi` at `0x180048913`
- `MSVCR100!atoi` at `0x1800489fc`
- `MSVCR100!atoi` at `0x1800483c0`
- `MSVCR100!atoi` at `0x180048615`
- `MSVCR100!atoi` at `0x180048628`
- `MSVCR100!atoi` at `0x180048749`
- `MSVCR100!atoi` at `0x180048769`
- `MSVCR100!atoi` at `0x180048781`
- `MSVCR100!atoi` at `0x180048799`
- `MSVCR100!atoi` at `0x180048845`
- `MSVCR100!atoi` at `0x180048913`
- `MSVCR100!atoi` at `0x1800489fc`
- `KERNEL32!lstrlenA` at `0x180048952`
- `KERNEL32!lstrlenA` at `0x180048952`
- `KERNEL32!lstrcmpiA` at `0x1800489c1`
- `KERNEL32!lstrcmpiA` at `0x1800489c1`
- `KERNEL32!lstrcpyA` at `0x180048979`
- `KERNEL32!lstrcpyA` at `0x180048979`
- `ole32!CLSIDFromString` at `0x180048460`
- `ole32!CLSIDFromString` at `0x180048580`
- `ole32!CLSIDFromString` at `0x1800485f8`
- `ole32!CLSIDFromString` at `0x180048460`
- `ole32!CLSIDFromString` at `0x180048580`
- `ole32!CLSIDFromString` at `0x1800485f8`

## string_xrefs

- `0x18004889b`: `DllBaseAddress`

## pseudocode

```c
__int64 __fastcall Project::ProcessProperties(Project *this, struct FILEREF *a2, struct CFileRep *a3, int *a4)
{
  char **v4; // r14
  char *v5; // rbx
  int v8; // r15d
  int v9; // eax
  int v10; // eax
  char *v11; // rax
  const char *v12; // r9
  __int64 v13; // rax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  bool v19; // cf
  int v20; // eax
  bool v21; // cf
  int v22; // eax
  unsigned int ProjectProtection; // ebx
  void *v24; // rax
  char *v25; // rbx
  char *v26; // rdi
  __int64 v27; // rax
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  unsigned __int64 v30; // rcx
  void *v31; // rsp
  void *v32; // rsp
  const char *v33; // rbx
  char *v34; // rdi
  __int64 v35; // rax
  unsigned __int64 v36; // rax
  __int64 v37; // rcx
  unsigned __int64 v38; // rcx
  void *v39; // rsp
  void *v40; // rsp
  char *v41; // rax
  const char *v42; // rcx
  char *v43; // rdi
  int v44; // eax
  __int64 v45; // rbx
  int v46; // eax
  char *v47; // rdx
  const char *v48; // rdx
  const char *v49; // rdx
  char *v50; // rdx
  unsigned int v51; // eax
  const char *v52; // rcx
  const char *v53; // rcx
  const char *v54; // rcx
  const char *v55; // rcx
  const char *PrintFullPath; // rax
  const char *v57; // rax
  const char *v58; // rax
  const char *v59; // rcx
  char *v60; // rdx
  const char *v61; // rax
  void **v62; // rbx
  __int64 v63; // r12
  signed __int64 v64; // rdi
  const char *v65; // rcx
  unsigned int v66; // eax
  const CHAR *v67; // rcx
  int v68; // eax
  int v69; // eax
  CHAR *v70; // rax
  wchar_t *i; // rax
  wchar_t *v72; // rbx
  __int64 v73; // rcx
  const char *v74; // rcx
  int v75; // eax
  const char *v76; // rax
  wchar_t v78[2]; // [rsp+30h] [rbp+0h] BYREF
  int v79; // [rsp+34h] [rbp+4h]
  int *v80; // [rsp+38h] [rbp+8h]
  CLSID pclsid; // [rsp+40h] [rbp+10h] BYREF

  v4 = proj_lpprojtext;
  v80 = a4;
  v5 = proj_lpprojtext[7];
  v79 = 0;
  *(_DWORD *)v78 = 0;
  v8 = 0;
  if ( !v5 )
    goto LABEL_47;
  v9 = atoi(v5);
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 == 1 )
        *((_DWORD *)this + 716) |= 0x4000u;
    }
    else
    {
      *((_DWORD *)this + 716) |= 0x40u;
    }
  }
  else
  {
    *((_DWORD *)this + 716) |= 0x800u;
  }
  v11 = lstrchr(v5, 44);
  if ( v11 )
  {
    v12 = v11 + 1;
    if ( ((unsigned __int64)(v11 + 1) & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      v14 = 2 * v13 + 2;
      v15 = v14 + 15;
      if ( v14 + 15 < v14 )
        v15 = 0xFFFFFFFFFFFFFF0LL;
      v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
      v17 = alloca(v16);
      v18 = alloca(v16);
      v12 = (const char *)strcpyWfromA(v78, v12);
    }
    CLSIDFromString((LPCOLESTR)v12, &pclsid);
    if ( *((_DWORD *)CVbe::m_pVbe + 49) )
    {
      v19 = *(_QWORD *)&pclsid.Data1 < 0x11D2B6D4FF5F8420uLL;
      if ( *(_QWORD *)&pclsid.Data1 == 0x11D2B6D4FF5F8420LL
        && (v19 = *(_QWORD *)pclsid.Data4 < 0x422470C9A0008599uLL, *(_QWORD *)pclsid.Data4 == 0x422470C9A0008599LL) )
      {
        v20 = 0;
      }
      else
      {
        v20 = -v19 - (v19 - 1);
      }
      if ( v20 )
        goto LABEL_28;
LABEL_27:
      ProjectProtection = 50069;
      goto LABEL_113;
    }
    v21 = *(_QWORD *)&pclsid.Data1 < 0x11D2B6D1447F54C6uLL;
    if ( *(_QWORD *)&pclsid.Data1 == 0x11D2B6D1447F54C6LL
      && (v21 = *(_QWORD *)pclsid.Data4 < 0x422470C9A0008599uLL, *(_QWORD *)pclsid.Data4 == 0x422470C9A0008599LL) )
    {
      v22 = 0;
    }
    else
    {
      v22 = -v21 - (v21 - 1);
    }
    if ( !v22 )
      goto LABEL_27;
  }
LABEL_28:
  if ( v4[8] )
  {
    v24 = malloc(0x30u);
    *((_QWORD *)this + 41) = v24;
    if ( !v24 )
    {
      ProjectProtection = 7;
      goto LABEL_113;
    }
    v25 = v4[8];
    v26 = lstrchr(v25, 44);
    *v26 = 0;
    if ( ((unsigned __int64)v25 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      v27 = -1;
      do
        ++v27;
      while ( v25[v27] );
      v28 = 2 * v27 + 2;
      v29 = v28 + 15;
      if ( v28 + 15 < v28 )
        v29 = 0xFFFFFFFFFFFFFF0LL;
      v30 = v29 & 0xFFFFFFFFFFFFFFF0uLL;
      v31 = alloca(v30);
      v32 = alloca(v30);
      v25 = (char *)strcpyWfromA(v78, v25);
    }
    CLSIDFromString((LPCOLESTR)v25, (LPCLSID)(*((_QWORD *)this + 41) + 24LL));
    v33 = v26 + 1;
    v34 = lstrchr(v26 + 1, 44);
    *v34 = 0;
    if ( ((unsigned __int64)v33 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      v35 = -1;
      do
        ++v35;
      while ( v33[v35] );
      v36 = 2 * v35 + 2;
      v37 = v36 + 15;
      if ( v36 + 15 < v36 )
        v37 = 0xFFFFFFFFFFFFFF0LL;
      v38 = v37 & 0xFFFFFFFFFFFFFFF0uLL;
      v39 = alloca(v38);
      v40 = alloca(v38);
      v33 = (const char *)strcpyWfromA(v78, v33);
    }
    CLSIDFromString((LPCOLESTR)v33, (LPCLSID)(*((_QWORD *)this + 41) + 8LL));
    v41 = lstrchr(v34 + 1, 44);
    v42 = v34 + 1;
    *v41 = 0;
    v43 = v41;
    **((_DWORD **)this + 41) = atoi(v42);
    *(_DWORD *)(*((_QWORD *)this + 41) + 4LL) = atoi(v43 + 1);
    *(_QWORD *)(*((_QWORD *)this + 41) + 40LL) = 0;
    v44 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, CLSID *))CVbe::m_pVbe + 9))(
            *((_QWORD *)CVbe::m_pVbe + 9),
            &IID_IVbeSite,
            &pclsid);
    v45 = *((_QWORD *)this + 41);
    if ( v44 >= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pclsid.Data1 + 16LL))(*(_QWORD *)&pclsid.Data1);
    v46 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, __int64))(**((_QWORD **)CVbe::m_pVbe + 9) + 88LL))(
            *((_QWORD *)CVbe::m_pVbe + 9),
            0,
            *((_QWORD *)this + 41) + 8LL,
            v45,
            *((_QWORD *)this + 41) + 4LL);
    if ( v46 < 0 )
    {
      ProjectProtection = _ErrFromHrDefault(v46);
      if ( ProjectProtection )
        goto LABEL_113;
    }
  }
LABEL_47:
  v47 = v4[11];
  if ( v47 )
    lstrncpyz((char *)this + 210, v47, 0x28u);
  v48 = v4[26];
  if ( v48 && *v48 )
    CFileRep::SetFullPath((Project *)((char *)this + 456), v48);
  v49 = v4[10];
  if ( v49 )
    CFileRep::SetFullPath((Project *)((char *)this + 256), v49);
  v50 = v4[9];
  if ( v4[17] )
    v8 = 1;
  if ( v50 )
  {
    v51 = Project::ErrSetProjectDocStr(this, v50, 0);
    if ( v51 )
      Error(v51);
    v8 = 1;
  }
  v52 = v4[27];
  if ( v4[25] )
    v8 = 1;
  if ( v52 )
    *((_DWORD *)this + 143) = (unsigned int)atoi(v52) >> 16;
  v53 = v4[12];
  if ( v53 )
  {
    v8 = 1;
    *((_DWORD *)this + 144) = atoi(v53);
  }
  v54 = v4[13];
  if ( v54 )
  {
    v8 = 1;
    *((_DWORD *)this + 145) = atoi(v54);
  }
  v55 = v4[14];
  if ( v55 )
  {
    v8 = 1;
    *((_DWORD *)this + 146) = atoi(v55);
  }
  if ( *((_DWORD *)this + 144) >= 0x2710u )
  {
    *((_DWORD *)this + 144) = 1;
    PrintFullPath = CFileRep::GetPrintFullPath(a3);
    ProcessPropertiesError(PrintFullPath, "MajorVer", v78);
  }
  if ( *((_DWORD *)this + 145) >= 0x2710u )
  {
    *((_DWORD *)this + 145) = 0;
    v57 = CFileRep::GetPrintFullPath(a3);
    ProcessPropertiesError(v57, "MinorVer", v78);
  }
  if ( *((_DWORD *)this + 146) >= 0x2710u )
  {
    *((_DWORD *)this + 146) = 0;
    v58 = CFileRep::GetPrintFullPath(a3);
    ProcessPropertiesError(v58, "RevisionVer", v78);
  }
  v59 = v4[15];
  if ( v59 )
  {
    v8 = 1;
    *((_DWORD *)this + 147) = atoi(v59) != 0;
  }
  v60 = v4[16];
  if ( v60 )
  {
    if ( (unsigned int)MiscScaledLongFromLpsz((int *)&pclsid, v60, 0)
      && (unsigned int)ExeIsValidBaseAddress(pclsid.Data1) )
    {
      *((_DWORD *)this + 138) = pclsid.Data1;
    }
    else
    {
      v61 = CFileRep::GetPrintFullPath(a3);
      ProcessPropertiesError(v61, "DllBaseAddress", v78);
    }
    v8 = 1;
  }
  v62 = (void **)((char *)this + 592);
  v63 = 6;
  v64 = (char *)v4 - (char *)this;
  do
  {
    if ( *(void **)((char *)v62 + v64 - 368) )
    {
      if ( *v62 )
        free(*v62);
      *v62 = StrHszMakeFromLpszImpl(*(const char **)((char *)v62 + v64 - 368));
    }
    ++v62;
    --v63;
  }
  while ( v63 );
  ProjectProtection = Project::ReadProjectProtection(this, v4);
  if ( ProjectProtection )
    goto LABEL_113;
  v65 = v4[34];
  if ( v65 )
  {
    v66 = atoi(v65);
    *((_DWORD *)this + 726) = v66;
    if ( v66 >= 4 )
      *((_DWORD *)this + 726) = -1;
  }
  v67 = v4[35];
  if ( !v67 )
    goto LABEL_108;
  v68 = *((_DWORD *)this + 726);
  if ( v68 == 1 )
  {
    *((_QWORD *)this + 364) = 0;
    for ( i = (wchar_t *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 52) + 32LL))((char *)this + 416);
          ;
          i = COldRefLibIdNode::GetOldRefLibIdRel((COldRefLibIdNode *)v72) )
    {
      v72 = i;
      if ( !i )
        break;
      v73 = *((_QWORD *)i + 7);
      if ( v73 && !lstrcmpiA(*(LPCSTR *)(*(_QWORD *)(v73 + 136) + 8LL), v4[35]) )
      {
        *((_QWORD *)this + 364) = *((_QWORD *)v72 + 7);
        break;
      }
    }
    if ( *((_QWORD *)this + 364) )
      goto LABEL_108;
    goto LABEL_107;
  }
  if ( (unsigned int)(v68 - 2) > 1 )
  {
    *((_QWORD *)this + 364) = 0;
    goto LABEL_108;
  }
  v69 = lstrlenA(v67);
  v70 = (CHAR *)malloc(v69 + 1);
  *((_QWORD *)this + 364) = v70;
  if ( !v70 )
  {
LABEL_107:
    *((_DWORD *)this + 726) = -1;
    goto LABEL_108;
  }
  lstrcpyA(v70, v4[35]);
LABEL_108:
  v74 = v4[36];
  if ( v74 )
  {
    v75 = atoi(v74);
    *((_DWORD *)this + 725) &= ~1u;
    *((_DWORD *)this + 725) |= v75 != 0;
  }
  if ( !v79 )
  {
    ProjectProtection = 0;
    goto LABEL_114;
  }
  ProjectProtection = 60070;
  v76 = CFileRep::GetPrintFullPath(a3);
  ErrorRemember(0xEAA6u, v76);
  Project::fSetDirtyFlag(this, 1);
LABEL_113:
  Error(ProjectProtection);
LABEL_114:
  if ( v80 )
    *v80 = v8;
  return ProjectProtection != 0 ? 0x800AEA5F : 0;
}

```

## disassembly

```asm
0x18004835c  push    rbp
0x18004835e  push    rsi
0x18004835f  push    rdi
0x180048360  push    r12
0x180048362  push    r13
0x180048364  push    r14
0x180048366  push    r15
0x180048368  mov     eax, 60h
0x18004836d  call    _alloca_probe
0x180048372  sub     rsp, rax
0x180048375  lea     rbp, [rsp+30h]
0x18004837a  mov     [rbp+60h+arg_8], rbx
0x18004837e  mov     rax, cs:__security_cookie
0x180048385  xor     rax, rbp
0x180048388  mov     [rbp+60h+var_40], rax
0x18004838c  mov     r14, cs:?proj_lpprojtext@@3PEAUtagPROJTEXT@@EA; tagPROJTEXT * proj_lpprojtext
0x180048393  xor     r12d, r12d
0x180048396  mov     [rbp+60h+var_58], r9
0x18004839a  mov     rbx, [r14+38h]
0x18004839e  mov     r13, r8
0x1800483a1  mov     rsi, rcx
0x1800483a4  mov     [rbp+60h+var_5C], r12d
0x1800483a8  mov     dword ptr [rbp+60h+var_60], r12d
0x1800483ac  mov     r15d, r12d
0x1800483af  lea     edi, [r12+1]
0x1800483b4  test    rbx, rbx
0x1800483b7  jz      loc_1800486B8
0x1800483bd  mov     rcx, rbx; String
0x1800483c0  call    cs:__imp_atoi
0x1800483c6  test    eax, eax
0x1800483c8  jz      short loc_1800483E5
0x1800483ca  dec     eax
0x1800483cc  jz      short loc_1800483DC
0x1800483ce  dec     eax
0x1800483d0  jnz     short loc_1800483ED
0x1800483d2  bts     dword ptr [rsi+0B30h], 0Eh
0x1800483da  jmp     short loc_1800483ED
0x1800483dc  or      dword ptr [rsi+0B30h], 40h
0x1800483e3  jmp     short loc_1800483ED
0x1800483e5  bts     dword ptr [rsi+0B30h], 0Bh
0x1800483ed  mov     dl, 2Ch ; ','; char
0x1800483ef  mov     rcx, rbx; char *
0x1800483f2  call    ?lstrchr@@YAPEADPEADD@Z; lstrchr(char *,char)
0x1800483f7  mov     rdx, 0FFFFFFFFFFFFFF0h
0x180048401  mov     r9, rax
0x180048404  test    rax, rax
0x180048407  jz      loc_1800484E5
0x18004840d  add     r9, rdi
0x180048410  test    r9, 0FFFFFFFFFFFF0000h
0x180048417  jz      short loc_180048459
0x180048419  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004841d  inc     rax
0x180048420  cmp     [r9+rax], r12b
0x180048424  jnz     short loc_18004841D
0x180048426  lea     rax, ds:2[rax*2]
0x18004842e  lea     rcx, [rax+0Fh]
0x180048432  cmp     rcx, rax
0x180048435  ja      short loc_18004843A
0x180048437  mov     rcx, rdx
0x18004843a  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18004843e  mov     rax, rcx
0x180048441  call    _alloca_probe
0x180048446  sub     rsp, rcx
0x180048449  mov     rdx, r9; char *
0x18004844c  lea     rcx, [rsp+90h+var_60]; wchar_t *
0x180048451  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x180048456  mov     r9, rax
0x180048459  lea     rdx, [rbp+60h+pclsid]; pclsid
0x18004845d  mov     rcx, r9; lpsz
0x180048460  call    cs:__imp_CLSIDFromString
0x180048466  mov     r11, cs:?m_pVbe@CVbe@@0PEAV1@EA; CVbe * CVbe::m_pVbe
0x18004846d  lea     r9, cs:180000000h
0x180048474  mov     r8d, [r11+0C4h]
0x18004847b  test    r8d, r8d
0x18004847e  jz      short loc_1800484B0
0x180048480  lea     rax, [rbp+60h+pclsid]
0x180048484  mov     rdx, [rax]
0x180048487  cmp     rdx, ds:rva qword_1803A3848[r9]
0x18004848e  jnz     short loc_1800484A2
0x180048490  mov     rdx, [rax+8]
0x180048494  cmp     rdx, ds:rva qword_1803A3850[r9]
0x18004849b  jnz     short loc_1800484A2
0x18004849d  mov     eax, r12d
0x1800484a0  jmp     short loc_1800484A7
0x1800484a2  sbb     eax, eax
0x1800484a4  sbb     eax, 0FFFFFFFFh
0x1800484a7  test    eax, eax
0x1800484a9  jz      short loc_1800484DB
0x1800484ab  test    r8d, r8d
0x1800484ae  jnz     short loc_1800484E5
0x1800484b0  lea     rax, [rbp+60h+pclsid]
0x1800484b4  mov     rdx, [rax]
0x1800484b7  cmp     rdx, qword ptr ds:rva stru_1803A3838.Data1[r9]
0x1800484be  jnz     short loc_1800484D2
0x1800484c0  mov     rdx, [rax+8]
0x1800484c4  cmp     rdx, qword ptr ds:rva stru_1803A3838.Data4[r9]
0x1800484cb  jnz     short loc_1800484D2
0x1800484cd  mov     eax, r12d
0x1800484d0  jmp     short loc_1800484D7
0x1800484d2  sbb     eax, eax
0x1800484d4  sbb     eax, 0FFFFFFFFh
0x1800484d7  test    eax, eax
0x1800484d9  jnz     short loc_1800484E5
0x1800484db  mov     ebx, 0C395h
0x1800484e0  jmp     loc_180048A49
0x1800484e5  cmp     [r14+40h], r12
0x1800484e9  jz      loc_1800486B8
0x1800484ef  mov     ecx, 30h ; '0'; Size
0x1800484f4  call    cs:__imp_malloc
0x1800484fa  mov     [rsi+148h], rax
0x180048501  test    rax, rax
0x180048504  jnz     short loc_18004850E
0x180048506  lea     ebx, [rax+7]
0x180048509  jmp     loc_180048A49
0x18004850e  mov     rbx, [r14+40h]
0x180048512  mov     dl, 2Ch ; ','; char
0x180048514  mov     rcx, rbx; char *
0x180048517  call    ?lstrchr@@YAPEADPEADD@Z; lstrchr(char *,char)
0x18004851c  mov     rdi, rax
0x18004851f  mov     [rax], r12b
0x180048522  test    rbx, 0FFFFFFFFFFFF0000h
0x180048529  jz      short loc_180048572
0x18004852b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004852f  inc     rax
0x180048532  cmp     [rbx+rax], r12b
0x180048536  jnz     short loc_18004852F
0x180048538  lea     rax, ds:2[rax*2]
0x180048540  lea     rcx, [rax+0Fh]
0x180048544  cmp     rcx, rax
0x180048547  ja      short loc_180048553
0x180048549  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180048553  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180048557  mov     rax, rcx
0x18004855a  call    _alloca_probe
0x18004855f  sub     rsp, rcx
0x180048562  mov     rdx, rbx; char *
0x180048565  lea     rcx, [rsp+90h+var_60]; wchar_t *
0x18004856a  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x18004856f  mov     rbx, rax
0x180048572  mov     rdx, [rsi+148h]
0x180048579  mov     rcx, rbx; lpsz
0x18004857c  add     rdx, 18h; pclsid
0x180048580  call    cs:__imp_CLSIDFromString
0x180048586  lea     rbx, [rdi+1]
0x18004858a  mov     dl, 2Ch ; ','; char
0x18004858c  mov     rcx, rbx; char *
0x18004858f  call    ?lstrchr@@YAPEADPEADD@Z; lstrchr(char *,char)
0x180048594  mov     rdi, rax
0x180048597  mov     [rax], r12b
0x18004859a  test    rbx, 0FFFFFFFFFFFF0000h
0x1800485a1  jz      short loc_1800485EA
0x1800485a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800485a7  inc     rax
0x1800485aa  cmp     [rbx+rax], r12b
0x1800485ae  jnz     short loc_1800485A7
0x1800485b0  lea     rax, ds:2[rax*2]
0x1800485b8  lea     rcx, [rax+0Fh]
0x1800485bc  cmp     rcx, rax
0x1800485bf  ja      short loc_1800485CB
0x1800485c1  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800485cb  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800485cf  mov     rax, rcx
0x1800485d2  call    _alloca_probe
0x1800485d7  sub     rsp, rcx
0x1800485da  mov     rdx, rbx; char *
0x1800485dd  lea     rcx, [rsp+90h+var_60]; wchar_t *
0x1800485e2  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x1800485e7  mov     rbx, rax
0x1800485ea  mov     rdx, [rsi+148h]
0x1800485f1  mov     rcx, rbx; lpsz
0x1800485f4  add     rdx, 8; pclsid
0x1800485f8  call    cs:__imp_CLSIDFromString
0x1800485fe  lea     rbx, [rdi+1]
0x180048602  mov     dl, 2Ch ; ','; char
0x180048604  mov     rcx, rbx; char *
0x180048607  call    ?lstrchr@@YAPEADPEADD@Z; lstrchr(char *,char)
0x18004860c  mov     rcx, rbx; String
0x18004860f  mov     [rax], r12b
0x180048612  mov     rdi, rax
0x180048615  call    cs:__imp_atoi
0x18004861b  mov     rcx, [rsi+148h]
0x180048622  mov     [rcx], eax
0x180048624  lea     rcx, [rdi+1]; String
0x180048628  call    cs:__imp_atoi
0x18004862e  mov     rcx, [rsi+148h]
0x180048635  lea     r8, [rbp+60h+pclsid]
0x180048639  mov     [rcx+4], eax
0x18004863c  mov     rax, [rsi+148h]
0x180048643  lea     rdx, IID_IVbeSite
0x18004864a  mov     [rax+28h], r12
0x18004864e  mov     rax, cs:?m_pVbe@CVbe@@0PEAV1@EA; CVbe * CVbe::m_pVbe
0x180048655  mov     rcx, [rax+48h]
0x180048659  mov     rax, [rcx]
0x18004865c  call    qword ptr [rax]
0x18004865e  mov     rbx, [rsi+148h]
0x180048665  test    eax, eax
0x180048667  js      short loc_180048673
0x180048669  mov     rcx, qword ptr [rbp+60h+pclsid.Data1]
0x18004866d  mov     rax, [rcx]
0x180048670  call    qword ptr [rax+10h]
0x180048673  mov     rax, cs:?m_pVbe@CVbe@@0PEAV1@EA; CVbe * CVbe::m_pVbe
0x18004867a  mov     r8, [rsi+148h]
0x180048681  mov     r9, rbx
0x180048684  mov     rcx, [rax+48h]
0x180048688  lea     rax, [r8+4]
0x18004868c  add     r8, 8
0x180048690  mov     r10, [rcx]
0x180048693  xor     edx, edx
0x180048695  mov     [rsp+90h+var_70], rax
0x18004869a  call    qword ptr [r10+58h]
0x18004869e  test    eax, eax
0x1800486a0  jns     short loc_1800486B3
0x1800486a2  mov     ecx, eax; int
0x1800486a4  call    ?_ErrFromHrDefault@@YAIJ@Z; _ErrFromHrDefault(long)
0x1800486a9  mov     ebx, eax
0x1800486ab  test    eax, eax
0x1800486ad  jnz     loc_180048A49
0x1800486b3  mov     edi, 1
0x1800486b8  mov     rdx, [r14+58h]; char *
0x1800486bc  test    rdx, rdx
0x1800486bf  jz      short loc_1800486D3
0x1800486c1  lea     rcx, [rsi+0D2h]; char *
0x1800486c8  mov     r8d, 28h ; '('; unsigned int
0x1800486ce  call    ?lstrncpyz@@YAIPEAD0I@Z; lstrncpyz(char *,char *,uint)
0x1800486d3  mov     rdx, [r14+0D0h]; char *
0x1800486da  test    rdx, rdx
0x1800486dd  jz      short loc_1800486F0
0x1800486df  cmp     [rdx], r12b
0x1800486e2  jz      short loc_1800486F0
0x1800486e4  lea     rcx, [rsi+1C8h]; this
0x1800486eb  call    ?SetFullPath@CFileRep@@QEAAHPEBD@Z; CFileRep::SetFullPath(char const *)
0x1800486f0  mov     rdx, [r14+50h]; char *
0x1800486f4  test    rdx, rdx
0x1800486f7  jz      short loc_180048705
0x1800486f9  lea     rcx, [rsi+100h]; this
0x180048700  call    ?SetFullPath@CFileRep@@QEAAHPEBD@Z; CFileRep::SetFullPath(char const *)
0x180048705  cmp     [r14+88h], r12
0x18004870c  mov     rdx, [r14+48h]; char *
0x180048710  cmovnz  r15d, edi
0x180048714  test    rdx, rdx
0x180048717  jz      short loc_180048732
0x180048719  xor     r8d, r8d; int
0x18004871c  mov     rcx, rsi; this
0x18004871f  call    ?ErrSetProjectDocStr@Project@@QEAAIPEADH@Z; Project::ErrSetProjectDocStr(char *,int)
0x180048724  test    eax, eax
0x180048726  jz      short loc_18004872F
0x180048728  mov     ecx, eax; unsigned int
0x18004872a  call    ?Error@@YAXI@Z; Error(uint)
0x18004872f  mov     r15d, edi
0x180048732  cmp     [r14+0C8h], r12
0x180048739  mov     rcx, [r14+0D8h]; String
0x180048740  cmovnz  r15d, edi
0x180048744  test    rcx, rcx
0x180048747  jz      short loc_180048760
0x180048749  call    cs:__imp_atoi
0x18004874f  mov     r11d, eax
0x180048752  shr     r11, 10h
0x180048756  movzx   eax, r11w
0x18004875a  mov     [rsi+23Ch], eax
0x180048760  mov     rcx, [r14+60h]; String
0x180048764  test    rcx, rcx
0x180048767  jz      short loc_180048778
0x180048769  call    cs:__imp_atoi
0x18004876f  mov     r15d, edi
0x180048772  mov     [rsi+240h], eax
0x180048778  mov     rcx, [r14+68h]; String
0x18004877c  test    rcx, rcx
0x18004877f  jz      short loc_180048790
0x180048781  call    cs:__imp_atoi
0x180048787  mov     r15d, edi
0x18004878a  mov     [rsi+244h], eax
0x180048790  mov     rcx, [r14+70h]; String
0x180048794  test    rcx, rcx
0x180048797  jz      short loc_1800487A8
0x180048799  call    cs:__imp_atoi
0x18004879f  mov     r15d, edi
0x1800487a2  mov     [rsi+248h], eax
0x1800487a8  mov     eax, [rsi+240h]
0x1800487ae  mov     ebx, 270Fh
0x1800487b3  cmp     eax, ebx
0x1800487b5  jg      short loc_1800487BB
0x1800487b7  test    eax, eax
0x1800487b9  jns     short loc_1800487DC
0x1800487bb  mov     rcx, r13; this
0x1800487be  mov     [rsi+240h], edi
0x1800487c4  call    ?GetPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetPrintFullPath(void)
0x1800487c9  lea     r8, [rbp+60h+var_60]
0x1800487cd  lea     rdx, aMajorver; "MajorVer"
0x1800487d4  mov     rcx, rax
0x1800487d7  call    _ProcessPropertiesError
0x1800487dc  mov     eax, [rsi+244h]
0x1800487e2  cmp     eax, ebx
0x1800487e4  jg      short loc_1800487EA
0x1800487e6  test    eax, eax
0x1800487e8  jns     short loc_18004880C
0x1800487ea  mov     rcx, r13; this
0x1800487ed  mov     [rsi+244h], r12d
0x1800487f4  call    ?GetPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetPrintFullPath(void)
0x1800487f9  lea     r8, [rbp+60h+var_60]
0x1800487fd  lea     rdx, aMinorver; "MinorVer"
  ... truncated ...
```
