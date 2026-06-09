# ResolverManagerp_ExecuteResolvers(_PCA_DIALOG_REQUESTS *,_PCA_RESOLVER_MANAGER_DATA *,unsigned __int64)

- ea: `0x1800171b0`
- end: `0x180017826`
- name: `?ResolverManagerp_ExecuteResolvers@@YAKPEAU_PCA_DIALOG_REQUESTS@@PEAU_PCA_RESOLVER_MANAGER_DATA@@_K@Z`
- size: `1654`
- prototype: `__int64 __fastcall(struct _PCA_DIALOG_REQUESTS *, struct _PCA_RESOLVER_MANAGER_DATA *, unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180014f80`

## callees

- `0x18000c73c`
- `0x18000dc08`
- `0x180012920`
- `0x180013fac`
- `0x1800171b0`
- `0x180018078`
- `0x180018174`
- `0x180018230`
- `0x180018a1c`
- `0x1800195c8`
- `0x18001b320`
- `0x18004ee40`
- `0x18007a9cf`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001766d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800176b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001766d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800176b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001758e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001758e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001740c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001740c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800175ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800175ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001776e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001776e`

## string_xrefs

- `0x180017587`: `pcadm.dll`
- `0x18001775f`: `Failed to load pcadm.dll,%d`
- `0x1800177ea`: `Failed to create dialog [%d]`
- `0x1800177c3`: `Failed to set executable path in dialog [%d]`
- `0x1800176bd`: `Failed to read NoisyResolvers [%d]`
- `0x1800177b4`: `Failed to set user sid in dialog [%d]`

## pseudocode

```c
__int64 __fastcall ResolverManagerp_ExecuteResolvers(
        struct _PCA_DIALOG_REQUESTS *a1,
        struct _PCA_RESOLVER_MANAGER_DATA *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // r12
  struct _PCA_DIALOG_REQUESTS *v5; // rcx
  __int64 *v6; // rax
  __int64 v7; // rdx
  struct _PCA_CHAIN *v8; // r13
  _DWORD *v9; // rsi
  unsigned int Value; // eax
  unsigned int v11; // ebx
  unsigned __int64 i; // r14
  __int64 *v13; // rax
  __int64 v14; // rcx
  unsigned __int64 j; // rdi
  unsigned __int64 v16; // rcx
  struct _PCA_RESOLVER * near *v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // eax
  struct _PCA_CHAIN *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  _QWORD *v24; // rbx
  HMODULE Library; // rax
  __int64 v26; // rax
  __int64 v27; // r8
  struct _PCA_RESOLVER *v28; // rbx
  struct _PCA_CHAIN *v29; // rax
  struct _PCA_RESOLVER *v30; // rbx
  struct _PCA_CHAIN *v31; // rax
  struct _PCA_RESOLVER *v32; // rbx
  struct _PCA_CHAIN *v33; // rax
  DWORD LastError; // eax
  const char *v35; // r9
  int v36; // r8d
  const char *v37; // r9
  int v38; // r8d
  unsigned __int16 *v39; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v40; // [rsp+20h] [rbp-E0h]
  __int64 v41; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v42; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v43; // [rsp+38h] [rbp-C8h]
  __int64 v44; // [rsp+40h] [rbp-C0h]
  HMODULE hLibModule; // [rsp+48h] [rbp-B8h] BYREF
  FARPROC ProcAddress; // [rsp+50h] [rbp-B0h]
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  struct _PCA_RESOLVER_MANAGER_DATA *v48; // [rsp+60h] [rbp-A0h]
  __int64 v49; // [rsp+68h] [rbp-98h]
  HMODULE *p_hLibModule; // [rsp+70h] [rbp-90h]
  char v51; // [rsp+78h] [rbp-88h]
  void *v52[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h]
  unsigned __int64 v54; // [rsp+98h] [rbp-68h]
  void *v55[3]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v56; // [rsp+B8h] [rbp-48h]
  __int64 v57; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v58; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v59[38]; // [rsp+D0h] [rbp-30h]
  __int64 v60; // [rsp+200h] [rbp+100h]
  unsigned __int16 v61[104]; // [rsp+210h] [rbp+110h] BYREF

  v3 = a3;
  v43 = a3;
  v48 = a2;
  memset_0(v61, 0, 0xC8u);
  hLibModule = 0;
  p_hLibModule = &hLibModule;
  v51 = 1;
  memset_0(&v57, 0, 0x148u);
  v5 = a1;
  v6 = &v57;
  v7 = 2;
  do
  {
    *(_OWORD *)v5 = *(_OWORD *)v6;
    *((_OWORD *)v5 + 1) = *((_OWORD *)v6 + 1);
    *((_OWORD *)v5 + 2) = *((_OWORD *)v6 + 2);
    *((_OWORD *)v5 + 3) = *((_OWORD *)v6 + 3);
    *((_OWORD *)v5 + 4) = *((_OWORD *)v6 + 4);
    *((_OWORD *)v5 + 5) = *((_OWORD *)v6 + 5);
    *((_OWORD *)v5 + 6) = *((_OWORD *)v6 + 6);
    *((_OWORD *)v5 + 7) = *((_OWORD *)v6 + 7);
    v5 = (struct _PCA_DIALOG_REQUESTS *)((char *)v5 + 128);
    v6 += 16;
    --v7;
  }
  while ( v7 );
  *(_OWORD *)v5 = *(_OWORD *)v6;
  *((_OWORD *)v5 + 1) = *((_OWORD *)v6 + 1);
  *((_OWORD *)v5 + 2) = *((_OWORD *)v6 + 2);
  *((_OWORD *)v5 + 3) = *((_OWORD *)v6 + 3);
  *((_QWORD *)v5 + 8) = v6[8];
  v8 = PcapChainFromHandle(v3);
  v49 = *((_QWORD *)PcapChainFromHandle(v3) + 667);
  v9 = 0;
  v42 = 0;
  v47 = 0;
  Value = PcaStoreGetValueEx(&v47, 8, (char *)v8 + 36, (char *)v8 + 4176, 6);
  v11 = Value;
  if ( (Value & 0xFFFFFFFD) != 0 )
  {
    LODWORD(v39) = Value;
    AslLogCallPrintf(
      1,
      (unsigned int)"ResolverManagerp_ExecuteResolvers",
      1103,
      (unsigned int)"Failed to read NoisyResolvers [%d]",
      v39);
    goto LABEL_18;
  }
  v11 = 0;
  for ( i = 0; i < 0x26; ++i )
  {
    if ( i != 37 && !*((_DWORD *)v8 + 141) && *((_DWORD *)v8 + 1182) && i || !*((_DWORD *)v48 + i + 76) )
      continue;
    v18 = (&g_Resolvers)[i];
    ProcAddress = (FARPROC)v18;
    v19 = v47;
    if ( _bittest64(&v19, i) )
    {
      v28 = *v18;
      v29 = PcapChainFromHandle(v3);
      PcaTracePrintf("ResolverManager", *((_DWORD *)v29 + 4), 0, "Resolver,%S,Bypass,Noisy", v28);
LABEL_50:
      v11 = 0;
      continue;
    }
    v57 |= 1LL << i;
    v20 = *((_DWORD *)v18 + 5);
    if ( v20 )
    {
      if ( v20 == -1 )
      {
        if ( *((_DWORD *)v8 + 1182) )
        {
          v32 = *v18;
          v33 = PcapChainFromHandle(v3);
          PcaTracePrintf("ResolverManager", *((_DWORD *)v33 + 4), 0, "Resolver,%S,Bypass,LatestOs", v32);
          goto LABEL_50;
        }
      }
      else if ( *((_DWORD *)v8 + 1180) >= v20 )
      {
        v30 = *v18;
        v31 = PcapChainFromHandle(v3);
        PcaTracePrintf("ResolverManager", *((_DWORD *)v31 + 4), 0, "Resolver,%S,Bypass,SilentOs", v30);
        goto LABEL_50;
      }
    }
    v44 = *((_QWORD *)v48 + i);
    v21 = PcapChainFromHandle(v3);
    v22 = PcaDialogCreate(&v42, *((_DWORD *)v21 + 4));
    v11 = v22;
    if ( v22 )
    {
      LODWORD(v39) = v22;
      AslLogCallPrintf(
        1,
        (unsigned int)"ResolverManagerp_ExecuteResolvers",
        1181,
        (unsigned int)"Failed to create dialog [%d]",
        v39);
      v9 = (_DWORD *)v42;
      goto LABEL_16;
    }
    v9 = (_DWORD *)v42;
    v23 = PcaDialogSetAppInformation(
            v42,
            (const unsigned __int16 *)v8 + 1568,
            (const unsigned __int16 *)v8 + 284,
            (const unsigned __int16 *)v8 + 544,
            (const unsigned __int16 *)v8 + 1828);
    v11 = v23;
    if ( v23 )
    {
      v37 = "Failed to set executable path in dialog [%d]";
      v38 = 1191;
      goto LABEL_62;
    }
    v23 = PcaDialogSetUserSid((unsigned __int64)v9, (const unsigned __int16 *)v8 + 18);
    v11 = v23;
    if ( v23 )
    {
      v37 = "Failed to set user sid in dialog [%d]";
      v38 = 1197;
LABEL_62:
      LODWORD(v40) = v23;
      AslLogCallPrintf(1, (unsigned int)"ResolverManagerp_ExecuteResolvers", v38, (_DWORD)v37, v40);
      goto LABEL_16;
    }
    v24 = ProcAddress;
    LODWORD(v44) = (*((__int64 (__fastcall **)(__int64, _DWORD *, unsigned __int64, __int64))ProcAddress + 6))(
                     v44,
                     v9,
                     v43,
                     v49);
    LODWORD(v40) = v44;
    if ( StringCchPrintfW(v61, 0x64u, L"PCA resolve is called, resolver name: %ws, result: %d", *v24, v40) >= 0 )
    {
      Library = LoadLibraryExW(L"pcadm.dll", 0, 0x800u);
      hLibModule = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "PcaPldAddGenDbRecord");
        if ( ProcAddress )
        {
          v56 = 7;
          v55[2] = 0;
          LOWORD(v55[0]) = 0;
          v26 = std::char_traits<unsigned short>::length((char *)v8 + 3136);
          std::wstring::assign(v55, (char *)v8 + 3136, v26);
          v54 = 7;
          v53 = 0;
          LOWORD(v52[0]) = 0;
          if ( v61[0] )
          {
            v27 = -1;
            do
              ++v27;
            while ( v61[v27] );
          }
          else
          {
            v27 = 0;
          }
          std::wstring::assign(v52, v61, v27);
          ((void (__fastcall *)(__int64, void **, void **))ProcAddress)(3, v52, v55);
          if ( v54 >= 8 )
            operator delete(v52[0]);
          v54 = 7;
          v53 = 0;
          LOWORD(v52[0]) = 0;
          if ( v56 >= 8 )
            operator delete(v55[0]);
          goto LABEL_32;
        }
        LastError = GetLastError();
        v35 = "Failed to get PcaPldAddGenDbRecord,%d";
        v36 = 1226;
      }
      else
      {
        LastError = GetLastError();
        v35 = "Failed to load pcadm.dll,%d";
        v36 = 1220;
      }
      LODWORD(v39) = LastError;
      AslLogCallPrintf(1, (unsigned int)"ResolverManagerp_ExecuteResolvers", v36, (_DWORD)v35, v39);
    }
    else
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"ResolverManagerp_ExecuteResolvers",
        1214,
        (unsigned int)"Failed to StringCchPrintf");
    }
LABEL_32:
    if ( (_DWORD)v44 )
    {
      LODWORD(v41) = v44;
      AslLogCallPrintf(
        1,
        (unsigned int)"ResolverManagerp_ExecuteResolvers",
        1234,
        (unsigned int)"Resolve failed for %S - ignoring Resolver [%d]",
        *v24,
        v41);
      v11 = 0;
    }
    else
    {
      v11 = 0;
      if ( *v9 )
      {
        v58 |= 1LL << i;
        v59[i] = (unsigned __int64)v9;
        ++v60;
      }
      else
      {
        ObsoleteShellApi_Delete((unsigned __int64)v9);
      }
      v42 = 0;
      v9 = 0;
    }
    v3 = v43;
  }
  v13 = &v57;
  v14 = 2;
  do
  {
    *(_OWORD *)a1 = *(_OWORD *)v13;
    *((_OWORD *)a1 + 1) = *((_OWORD *)v13 + 1);
    *((_OWORD *)a1 + 2) = *((_OWORD *)v13 + 2);
    *((_OWORD *)a1 + 3) = *((_OWORD *)v13 + 3);
    *((_OWORD *)a1 + 4) = *((_OWORD *)v13 + 4);
    *((_OWORD *)a1 + 5) = *((_OWORD *)v13 + 5);
    *((_OWORD *)a1 + 6) = *((_OWORD *)v13 + 6);
    *((_OWORD *)a1 + 7) = *((_OWORD *)v13 + 7);
    a1 = (struct _PCA_DIALOG_REQUESTS *)((char *)a1 + 128);
    v13 += 16;
    --v14;
  }
  while ( v14 );
  *(_OWORD *)a1 = *(_OWORD *)v13;
  *((_OWORD *)a1 + 1) = *((_OWORD *)v13 + 1);
  *((_OWORD *)a1 + 2) = *((_OWORD *)v13 + 2);
  *((_OWORD *)a1 + 3) = *((_OWORD *)v13 + 3);
  *((_QWORD *)a1 + 8) = v13[8];
  memset_0(&v57, 0, 0x148u);
LABEL_16:
  if ( v9 )
    ObsoleteShellApi_Delete((unsigned __int64)v9);
LABEL_18:
  for ( j = 0; j < 0x26; ++j )
  {
    v16 = v59[j];
    if ( v16 )
      ObsoleteShellApi_Delete(v16);
  }
  if ( hLibModule )
    FreeLibrary(hLibModule);
  return v11;
}

```

## disassembly

```asm
0x1800171b0  mov     [rsp-8+arg_18], rbx
0x1800171b5  push    rbp
0x1800171b6  push    rsi
0x1800171b7  push    rdi
0x1800171b8  push    r12
0x1800171ba  push    r13
0x1800171bc  push    r14
0x1800171be  push    r15
0x1800171c0  lea     rbp, [rsp-1F0h]
0x1800171c8  sub     rsp, 2F0h
0x1800171cf  mov     rax, cs:__security_cookie
0x1800171d6  xor     rax, rsp
0x1800171d9  mov     [rbp+220h+var_40], rax
0x1800171e0  mov     r12, r8
0x1800171e3  mov     [rsp+320h+var_2E8], r8
0x1800171e8  mov     [rsp+320h+var_2C0], rdx
0x1800171ed  mov     rdi, rcx
0x1800171f0  xor     edx, edx; Val
0x1800171f2  mov     r8d, 0C8h; Size
0x1800171f8  lea     rcx, [rbp+220h+var_110]; void *
0x1800171ff  call    memset_0
0x180017204  xor     r14d, r14d
0x180017207  mov     [rsp+320h+hLibModule], r14
0x18001720c  lea     rax, [rsp+320h+hLibModule]
0x180017211  mov     [rsp+320h+var_2B0], rax
0x180017216  mov     [rsp+320h+var_2A8], 1
0x18001721b  xor     edx, edx; Val
0x18001721d  mov     r8d, 148h; Size
0x180017223  lea     rcx, [rbp+220h+var_260]; void *
0x180017227  call    memset_0
0x18001722c  mov     rcx, rdi
0x18001722f  lea     rax, [rbp+220h+var_260]
0x180017233  lea     edx, [r14+2]
0x180017237  lea     r8d, [rdx+7Eh]
0x18001723b  movups  xmm0, xmmword ptr [rax]
0x18001723e  movups  xmmword ptr [rcx], xmm0
0x180017241  movups  xmm1, xmmword ptr [rax+10h]
0x180017245  movups  xmmword ptr [rcx+10h], xmm1
0x180017249  movups  xmm0, xmmword ptr [rax+20h]
0x18001724d  movups  xmmword ptr [rcx+20h], xmm0
0x180017251  movups  xmm1, xmmword ptr [rax+30h]
0x180017255  movups  xmmword ptr [rcx+30h], xmm1
0x180017259  movups  xmm0, xmmword ptr [rax+40h]
0x18001725d  movups  xmmword ptr [rcx+40h], xmm0
0x180017261  movups  xmm1, xmmword ptr [rax+50h]
0x180017265  movups  xmmword ptr [rcx+50h], xmm1
0x180017269  movups  xmm0, xmmword ptr [rax+60h]
0x18001726d  movups  xmmword ptr [rcx+60h], xmm0
0x180017271  movups  xmm1, xmmword ptr [rax+70h]
0x180017275  movups  xmmword ptr [rcx+70h], xmm1
0x180017279  add     rcx, r8
0x18001727c  add     rax, r8
0x18001727f  sub     rdx, 1
0x180017283  jnz     short loc_18001723B
0x180017285  movups  xmm0, xmmword ptr [rax]
0x180017288  movups  xmmword ptr [rcx], xmm0
0x18001728b  movups  xmm1, xmmword ptr [rax+10h]
0x18001728f  movups  xmmword ptr [rcx+10h], xmm1
0x180017293  movups  xmm0, xmmword ptr [rax+20h]
0x180017297  movups  xmmword ptr [rcx+20h], xmm0
0x18001729b  movups  xmm1, xmmword ptr [rax+30h]
0x18001729f  movups  xmmword ptr [rcx+30h], xmm1
0x1800172a3  mov     rax, [rax+40h]
0x1800172a7  mov     [rcx+40h], rax
0x1800172ab  mov     rcx, r12; unsigned __int64
0x1800172ae  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800172b3  mov     r13, rax
0x1800172b6  mov     rcx, r12; unsigned __int64
0x1800172b9  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800172be  mov     rax, [rax+14D8h]
0x1800172c5  mov     [rsp+320h+var_2B8], rax
0x1800172ca  mov     rsi, r14
0x1800172cd  mov     [rsp+320h+var_2F0], r14
0x1800172d2  mov     [rsp+320h+var_2C8], r14
0x1800172d7  lea     r8, [r13+24h]
0x1800172db  lea     r9, [r13+1050h]
0x1800172e2  mov     dword ptr [rsp+320h+var_300], 6
0x1800172ea  mov     edx, 8
0x1800172ef  lea     rcx, [rsp+320h+var_2C8]
0x1800172f4  call    ?PcaStoreGetValueEx@@YAKPEAX_KPEBG2W4_PCA_SLOT_ID@@@Z; PcaStoreGetValueEx(void *,unsigned __int64,ushort const *,ushort const *,_PCA_SLOT_ID)
0x1800172f9  mov     ebx, eax
0x1800172fb  test    eax, 0FFFFFFFDh
0x180017300  jnz     loc_1800176B9
0x180017306  xor     ebx, ebx
0x180017308  mov     r14d, ebx
0x18001730b  lea     r15, aResolvermanage_0; "ResolverManagerp_ExecuteResolvers"
0x180017312  cmp     r14, 26h ; '&'
0x180017316  jnb     short loc_18001734F
0x180017318  cmp     r14, 25h ; '%'
0x18001731c  jz      short loc_180017330
0x18001731e  cmp     [r13+234h], ebx
0x180017325  jnz     short loc_180017330
0x180017327  cmp     [r13+1278h], ebx
0x18001732e  jnz     short loc_180017348
0x180017330  mov     rdx, [rsp+320h+var_2C0]
0x180017335  cmp     [rdx+r14*4+130h], ebx
0x18001733d  jnz     loc_18001743F
0x180017343  inc     r14
0x180017346  jmp     short loc_180017312
0x180017348  test    r14, r14
0x18001734b  jnz     short loc_180017343
0x18001734d  jmp     short loc_180017330
0x18001734f  lea     rax, [rbp+220h+var_260]
0x180017353  mov     ecx, 2
0x180017358  lea     edx, [rcx+7Eh]
0x18001735b  movups  xmm0, xmmword ptr [rax]
0x18001735e  movups  xmmword ptr [rdi], xmm0
0x180017361  movups  xmm1, xmmword ptr [rax+10h]
0x180017365  movups  xmmword ptr [rdi+10h], xmm1
0x180017369  movups  xmm0, xmmword ptr [rax+20h]
0x18001736d  movups  xmmword ptr [rdi+20h], xmm0
0x180017371  movups  xmm1, xmmword ptr [rax+30h]
0x180017375  movups  xmmword ptr [rdi+30h], xmm1
0x180017379  movups  xmm0, xmmword ptr [rax+40h]
0x18001737d  movups  xmmword ptr [rdi+40h], xmm0
0x180017381  movups  xmm1, xmmword ptr [rax+50h]
0x180017385  movups  xmmword ptr [rdi+50h], xmm1
0x180017389  movups  xmm0, xmmword ptr [rax+60h]
0x18001738d  movups  xmmword ptr [rdi+60h], xmm0
0x180017391  movups  xmm1, xmmword ptr [rax+70h]
0x180017395  movups  xmmword ptr [rdi+70h], xmm1
0x180017399  add     rdi, rdx
0x18001739c  add     rax, rdx
0x18001739f  sub     rcx, 1
0x1800173a3  jnz     short loc_18001735B
0x1800173a5  movups  xmm0, xmmword ptr [rax]
0x1800173a8  movups  xmmword ptr [rdi], xmm0
0x1800173ab  movups  xmm1, xmmword ptr [rax+10h]
0x1800173af  movups  xmmword ptr [rdi+10h], xmm1
0x1800173b3  movups  xmm0, xmmword ptr [rax+20h]
0x1800173b7  movups  xmmword ptr [rdi+20h], xmm0
0x1800173bb  movups  xmm1, xmmword ptr [rax+30h]
0x1800173bf  movups  xmmword ptr [rdi+30h], xmm1
0x1800173c3  mov     rax, [rax+40h]
0x1800173c7  mov     [rdi+40h], rax
0x1800173cb  xor     edx, edx; Val
0x1800173cd  mov     r8d, 148h; Size
0x1800173d3  lea     rcx, [rbp+220h+var_260]; void *
0x1800173d7  call    memset_0
0x1800173dc  xor     r14d, r14d
0x1800173df  test    rsi, rsi
0x1800173e2  jnz     loc_18001780E
0x1800173e8  mov     rdi, r14
0x1800173eb  mov     rcx, [rbp+rdi*8+220h+var_250]; unsigned __int64
0x1800173f0  test    rcx, rcx
0x1800173f3  jnz     loc_18001781B
0x1800173f9  inc     rdi
0x1800173fc  cmp     rdi, 26h ; '&'
0x180017400  jb      short loc_1800173EB
0x180017402  mov     rcx, [rsp+320h+hLibModule]; hLibModule
0x180017407  test    rcx, rcx
0x18001740a  jz      short loc_180017413
0x18001740c  call    cs:__imp_FreeLibrary
0x180017412  nop
0x180017413  mov     eax, ebx
0x180017415  mov     rcx, [rbp+220h+var_40]
0x18001741c  xor     rcx, rsp; StackCookie
0x18001741f  call    __security_check_cookie
0x180017424  mov     rbx, [rsp+320h+arg_18]
0x18001742c  add     rsp, 2F0h
0x180017433  pop     r15
0x180017435  pop     r14
0x180017437  pop     r13
0x180017439  pop     r12
0x18001743b  pop     rdi
0x18001743c  pop     rsi
0x18001743d  pop     rbp
0x18001743e  retn
0x18001743f  lea     rcx, ?g_Resolvers@@3PAPEAU_PCA_RESOLVER@@A; _PCA_RESOLVER * near * g_Resolvers
0x180017446  mov     rcx, [rcx+r14*8]
0x18001744a  mov     [rsp+320h+var_2D0], rcx
0x18001744f  mov     rax, [rsp+320h+var_2C8]
0x180017454  bt      rax, r14
0x180017458  jb      loc_1800176E0
0x18001745e  mov     rax, [rbp+220h+var_260]
0x180017462  bts     rax, r14
0x180017466  mov     [rbp+220h+var_260], rax
0x18001746a  mov     eax, [rcx+14h]
0x18001746d  test    eax, eax
0x18001746f  jnz     loc_180017724
0x180017475  mov     rax, [rdx+r14*8]
0x180017479  mov     [rsp+320h+var_2E0], rax
0x18001747e  mov     rcx, r12; unsigned __int64
0x180017481  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x180017486  mov     edx, [rax+10h]; unsigned int
0x180017489  lea     rcx, [rsp+320h+var_2F0]; unsigned __int64 *
0x18001748e  call    ?PcaDialogCreate@@YAKPEA_KI@Z; PcaDialogCreate(unsigned __int64 *,uint)
0x180017493  mov     ebx, eax
0x180017495  test    eax, eax
0x180017497  jnz     loc_1800177E6
0x18001749d  lea     r12, [r13+0C40h]
0x1800174a4  lea     rax, [r13+0E48h]
0x1800174ab  lea     r9, [r13+440h]; unsigned __int16 *
0x1800174b2  lea     r8, [r13+238h]; unsigned __int16 *
0x1800174b9  mov     [rsp+320h+var_300], rax; unsigned __int16 *
0x1800174be  mov     rdx, r12; unsigned __int16 *
0x1800174c1  mov     rsi, [rsp+320h+var_2F0]
0x1800174c6  mov     rcx, rsi; unsigned __int64
0x1800174c9  call    ?PcaDialogSetAppInformation@@YAK_KPEBG111@Z; PcaDialogSetAppInformation(unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800174ce  mov     ebx, eax
0x1800174d0  test    eax, eax
0x1800174d2  jnz     loc_1800177C3
0x1800174d8  lea     rdx, [r13+24h]; unsigned __int16 *
0x1800174dc  mov     rcx, rsi; unsigned __int64
0x1800174df  call    ?PcaDialogSetUserSid@@YAK_KPEBG@Z; PcaDialogSetUserSid(unsigned __int64,ushort const *)
0x1800174e4  mov     ebx, eax
0x1800174e6  test    eax, eax
0x1800174e8  jnz     loc_1800177B4
0x1800174ee  mov     r9, [rsp+320h+var_2B8]
0x1800174f3  mov     r8, [rsp+320h+var_2E8]
0x1800174f8  mov     rdx, rsi
0x1800174fb  mov     rcx, [rsp+320h+var_2E0]
0x180017500  mov     rbx, [rsp+320h+var_2D0]
0x180017505  mov     rax, [rbx+30h]
0x180017509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001750e  mov     dword ptr [rsp+320h+var_2E0], eax
0x180017512  mov     dword ptr [rsp+320h+var_300], eax
0x180017516  mov     r9, [rbx]
0x180017519  lea     r8, aPcaResolveIsCa; "PCA resolve is called, resolver name: %"...
0x180017520  mov     edx, 64h ; 'd'; unsigned __int64
0x180017525  lea     rcx, [rbp+220h+var_110]; unsigned __int16 *
0x18001752c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017531  test    eax, eax
0x180017533  jns     short loc_18001757F
0x180017535  lea     r9, aFailedToString_0; "Failed to StringCchPrintf"
0x18001753c  mov     r8d, 4BEh
0x180017542  mov     rdx, r15
0x180017545  mov     ecx, 1
0x18001754a  call    AslLogCallPrintf
0x18001754f  mov     eax, dword ptr [rsp+320h+var_2E0]
0x180017553  test    eax, eax
0x180017555  jnz     loc_180017678
0x18001755b  xor     ebx, ebx
0x18001755d  cmp     [rsi], ebx
0x18001755f  jnz     loc_180017797
0x180017565  mov     rcx, rsi; unsigned __int64
0x180017568  call    ?ObsoleteShellApi_Delete@@YAX_K@Z; ObsoleteShellApi_Delete(unsigned __int64)
0x18001756d  mov     [rsp+320h+var_2F0], rbx
0x180017572  mov     rsi, rbx
0x180017575  mov     r12, [rsp+320h+var_2E8]
0x18001757a  jmp     loc_180017343
0x18001757f  xor     edx, edx; hFile
0x180017581  mov     r8d, 800h; dwFlags
0x180017587  lea     rcx, aPcadmDll; "pcadm.dll"
0x18001758e  call    cs:__imp_LoadLibraryExW
0x180017594  mov     [rsp+320h+hLibModule], rax
0x180017599  test    rax, rax
0x18001759c  jz      loc_180017759
0x1800175a2  lea     rdx, aPcapldaddgendb; "PcaPldAddGenDbRecord"
0x1800175a9  mov     rcx, rax; hModule
0x1800175ac  call    cs:__imp_GetProcAddress
0x1800175b2  mov     [rsp+320h+var_2D0], rax
0x1800175b7  xor     ecx, ecx
0x1800175b9  test    rax, rax
0x1800175bc  jz      loc_18001776E
0x1800175c2  mov     [rbp+220h+var_268], 7
0x1800175ca  mov     [rbp+220h+var_270], rcx
0x1800175ce  mov     word ptr [rbp+220h+var_280], cx
0x1800175d2  mov     rcx, r12
0x1800175d5  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800175da  mov     r8, rax
0x1800175dd  mov     rdx, r12
0x1800175e0  lea     rcx, [rbp+220h+var_280]
0x1800175e4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800175e9  nop
0x1800175ea  mov     r12d, 7
0x1800175f0  mov     [rbp+220h+var_288], r12
0x1800175f4  xor     ecx, ecx
0x1800175f6  mov     [rbp+220h+var_290], rcx
0x1800175fa  mov     word ptr [rbp+220h+var_2A0], cx
0x1800175fe  cmp     [rbp+220h+var_110], cx
0x180017605  jz      loc_1800176A5
0x18001760b  lea     rax, [rbp+220h+var_110]
0x180017612  or      r8, 0FFFFFFFFFFFFFFFFh
0x180017616  inc     r8
0x180017619  cmp     [rax+r8*2], cx
0x18001761e  jnz     short loc_180017616
0x180017620  lea     rdx, [rbp+220h+var_110]
0x180017627  lea     rcx, [rbp+220h+var_2A0]
0x18001762b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180017630  nop
0x180017631  lea     r8, [rbp+220h+var_280]
0x180017635  lea     rdx, [rbp+220h+var_2A0]
0x180017639  mov     ecx, 3
0x18001763e  mov     rax, [rsp+320h+var_2D0]
0x180017643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017648  nop
0x180017649  cmp     [rbp+220h+var_288], 8
0x18001764e  jnb     short loc_1800176AD
0x180017650  mov     [rbp+220h+var_288], r12
0x180017654  xor     eax, eax
0x180017656  mov     [rbp+220h+var_290], rax
0x18001765a  mov     word ptr [rbp+220h+var_2A0], ax
0x18001765e  cmp     [rbp+220h+var_268], 8
0x180017663  jb      loc_18001754F
0x180017669  mov     rcx, [rbp+220h+var_280]
0x18001766d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180017673  jmp     loc_18001754F
0x180017678  mov     dword ptr [rsp+320h+var_2F8], eax
0x18001767c  mov     rax, [rbx]
  ... truncated ...
```
