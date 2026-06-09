# DigestStorageMetadataHelper(HINSTANCE__ *,HINSTANCE__ *,IStorage &,bool,unsigned __int64)

- ea: `0x180003370`
- end: `0x180003a56`
- name: `?DigestStorageMetadataHelper@@YAHPEAUHINSTANCE__@@0AEAUIStorage@@_N_K@Z`
- size: `1766`
- prototype: `__int64 __fastcall(HINSTANCE, HINSTANCE, struct IStorage *, char, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180001be0`
- `0x1800022b0`
- `0x180003370`

## callees

- `0x180003370`
- `0x180004580`
- `0x180004ad0`
- `0x18000d300`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800033e5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800036ea`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180003938`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800033e5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800036ea`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180003938`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003911`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003983`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003911`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003983`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800034e1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800034e1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800038f7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003975`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800038f7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003975`

## string_xrefs

- `0x1800036e0`: `CoTaskMemFree`
- `0x18000392e`: `CoTaskMemFree`

## pseudocode

```c
__int64 __fastcall DigestStorageMetadataHelper(
        HINSTANCE a1,
        HINSTANCE a2,
        struct IStorage *a3,
        char a4,
        unsigned __int64 a5)
{
  HMODULE v7; // rsi
  FARPROC ProcAddress; // r15
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // r14
  struct tagSTATSTG *v12; // rsi
  __int64 v13; // rax
  int v14; // eax
  unsigned __int16 v15; // bx
  __int64 i; // rdi
  _QWORD *v17; // rbx
  __int64 v18; // rcx
  _WORD *v19; // rax
  DWORD LastError; // r12d
  unsigned int v21; // r15d
  __int64 v22; // rcx
  _WORD *v23; // rax
  int v24; // r8d
  int v25; // eax
  int v26; // eax
  unsigned int v27; // edi
  void (*v28)(void); // rsi
  unsigned int v29; // ebx
  int v30; // eax
  HMODULE v31; // rbx
  char *v32; // rdx
  unsigned __int16 *v33; // rax
  int v34; // ecx
  int v35; // r8d
  char *v36; // r8
  int v37; // eax
  int v38; // ecx
  DWORD v39; // ecx
  void (*v41)(void); // rdi
  unsigned int v42; // ebx
  unsigned int v43; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE v44; // [rsp+48h] [rbp-B8h]
  __int64 *v45; // [rsp+50h] [rbp-B0h] BYREF
  struct IStorage *v46; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v47; // [rsp+60h] [rbp-A0h]
  struct IStorage *v48; // [rsp+68h] [rbp-98h]
  HMODULE hModule; // [rsp+70h] [rbp-90h]
  __int64 v50; // [rsp+78h] [rbp-88h]
  _OWORD v51[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v52; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v53; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v54[50]; // [rsp+D0h] [rbp-30h] BYREF

  v50 = -2;
  v48 = a3;
  hModule = a2;
  v7 = a1;
  v44 = a1;
  if ( !a1 )
    return 0;
  if ( !a2 )
    return 0;
  ProcAddress = GetProcAddress(a2, "CryptHashData");
  if ( !ProcAddress )
    return 0;
  if ( !a4 )
  {
    memset(v51, 0, sizeof(v51));
    v52 = 0;
    v53 = 0;
    v9 = ((__int64 (__fastcall *)(struct IStorage *, _OWORD *, _QWORD))a3->lpVtbl->Stat)(a3, v51, 0);
    if ( v9 < 0 )
    {
LABEL_84:
      v39 = (unsigned __int16)v9;
      goto LABEL_71;
    }
    if ( !((unsigned int (__fastcall *)(unsigned __int64, char *, __int64, _QWORD))ProcAddress)(
            a5,
            (char *)&v52 + 8,
            16,
            0)
      || !((unsigned int (__fastcall *)(unsigned __int64, char *, __int64, _QWORD))ProcAddress)(
            a5,
            (char *)&v53 + 8,
            4,
            0) )
    {
      return 0;
    }
  }
  v45 = 0;
  v9 = ((__int64 (__fastcall *)(struct IStorage *, _QWORD, _QWORD, _QWORD, __int64 **))a3->lpVtbl->EnumElements)(
         a3,
         0,
         0,
         0,
         &v45);
  if ( v9 < 0 || !v45 )
    goto LABEL_84;
  v10 = -1;
  v43 = -1;
  v11 = 0;
  while ( v10 )
  {
    v26 = (*(__int64 (__fastcall **)(__int64 *, __int64, _OWORD *, unsigned int *))(*v45 + 24))(v45, 10, v54, &v43);
    v15 = v26;
    if ( v26 < 0 )
      goto LABEL_70;
    v27 = v43;
    if ( v43 > 0xA )
      goto LABEL_70;
    v11 = v43 + (unsigned int)v11;
    if ( !v43 )
      break;
    v28 = (void (*)(void))GetProcAddress(v7, "CoTaskMemFree");
    if ( v28 )
    {
      v29 = 0;
      do
      {
        if ( *(_QWORD *)&v54[5 * (int)v29] )
          v28();
        ++v29;
      }
      while ( v29 < v27 );
      v10 = v43;
      v7 = v44;
    }
    else
    {
      v10 = v43;
      v7 = v44;
    }
  }
  v12 = 0;
  if ( (_DWORD)v11 )
  {
    v12 = (struct tagSTATSTG *)LocalAlloc(0x40u, 80 * v11);
    v13 = *v45;
    if ( v12 )
    {
      (*(void (**)(void))(v13 + 40))();
      v43 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct tagSTATSTG *, unsigned int *))(*v45 + 24))(
              v45,
              (unsigned int)v11,
              v12,
              &v43);
      v15 = v14;
      if ( v14 >= 0 && (_DWORD)v11 == v43 )
      {
        QSortStatStg(v12, v11, 0, v11 - 1);
        goto LABEL_17;
      }
      FreeSortedStorageElements(v44, v12, v43);
      LocalFree(v12);
LABEL_70:
      (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
      v39 = v15;
    }
    else
    {
      (*(void (**)(void))(v13 + 16))();
      v39 = 8;
    }
LABEL_71:
    SetLastError(v39);
    return 0;
  }
LABEL_17:
  (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
  if ( !v12 )
    return 0;
  v47 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= (unsigned int)v11 )
    {
      v21 = 1;
      LastError = v47;
      goto LABEL_74;
    }
    v17 = (_QWORD *)((char *)v12 + 80 * i);
    if ( *((_DWORD *)v17 + 2) == 1 )
      break;
    if ( *((_DWORD *)v17 + 2) != 2 )
    {
      LastError = 11;
      v21 = 0;
      goto LABEL_74;
    }
    if ( !a4 )
    {
      v32 = (char *)*v17;
      v33 = (unsigned __int16 *)*v17;
      do
      {
        v34 = *(unsigned __int16 *)((char *)qword_18000F930 + (_QWORD)v33 - *v17);
        v35 = *v33 - v34;
        if ( v35 )
          break;
        ++v33;
      }
      while ( v34 );
      if ( !v35 )
        continue;
      v36 = (char *)((char *)&qword_18000F898 - v32);
      do
      {
        v37 = *(unsigned __int16 *)&v36[(_QWORD)v32];
        v38 = *(unsigned __int16 *)v32 - v37;
        if ( v38 )
          break;
        v32 += 2;
      }
      while ( v37 );
      if ( !v38 )
        continue;
    }
    if ( !*v17 )
    {
LABEL_27:
      LastError = 87;
      v21 = 0;
      goto LABEL_74;
    }
    v18 = 0x7FFFFFFF;
    v19 = (_WORD *)*v17;
    while ( *v19 )
    {
      ++v19;
      if ( !--v18 )
        goto LABEL_27;
    }
    if ( !((unsigned int (__fastcall *)(unsigned __int64, _QWORD, _QWORD, _QWORD))ProcAddress)(
            a5,
            *v17,
            (unsigned int)(-2 - 2 * v18),
            0)
      || !((unsigned int (__fastcall *)(unsigned __int64, _QWORD *, __int64, _QWORD))ProcAddress)(a5, v17 + 2, 8, 0)
      || !((unsigned int (__fastcall *)(unsigned __int64, _QWORD *, __int64, _QWORD))ProcAddress)(a5, v17 + 4, 8, 0)
      || !((unsigned int (__fastcall *)(unsigned __int64, _QWORD *, __int64, _QWORD))ProcAddress)(a5, v17 + 3, 8, 0) )
    {
LABEL_91:
      LastError = GetLastError();
      v21 = 0;
      goto LABEL_74;
    }
LABEL_32:
    ;
  }
  if ( !*v17 )
  {
    LOWORD(v25) = 87;
LABEL_94:
    LastError = (unsigned __int16)v25;
    v21 = 0;
LABEL_74:
    v31 = v44;
    goto LABEL_75;
  }
  v22 = 0x7FFFFFFF;
  v23 = (_WORD *)*v17;
  while ( *v23 )
  {
    ++v23;
    if ( !--v22 )
    {
      v24 = 0;
      v25 = -2147024809;
      goto LABEL_48;
    }
  }
  v24 = 0x7FFFFFFF - v22;
  v25 = 0;
LABEL_48:
  if ( v25 < 0 )
    goto LABEL_94;
  if ( !((unsigned int (__fastcall *)(unsigned __int64, _QWORD, _QWORD, _QWORD))ProcAddress)(
          a5,
          *v17,
          (unsigned int)(2 * v24),
          0)
    || !((unsigned int (__fastcall *)(unsigned __int64, _QWORD *, __int64, _QWORD))ProcAddress)(a5, v17 + 7, 16, 0)
    || !((unsigned int (__fastcall *)(unsigned __int64, _QWORD *, __int64, _QWORD))ProcAddress)(a5, v17 + 9, 4, 0)
    || !((unsigned int (__fastcall *)(unsigned __int64, _QWORD *, __int64, _QWORD))ProcAddress)(a5, v17 + 4, 8, 0)
    || !((unsigned int (__fastcall *)(unsigned __int64, _QWORD *, __int64, _QWORD))ProcAddress)(a5, v17 + 3, 8, 0) )
  {
    goto LABEL_91;
  }
  v46 = 0;
  v30 = ((__int64 (__fastcall *)(struct IStorage *, _QWORD, _QWORD, __int64, _QWORD, _DWORD, struct IStorage **))v48->lpVtbl->OpenStorage)(
          v48,
          *v17,
          0,
          16,
          0,
          0,
          &v46);
  if ( v30 < 0 || !v46 )
  {
    LastError = (unsigned __int16)v30;
    v21 = 0;
    if ( v46 )
      ((void (*)(void))v46->lpVtbl->Release)();
    goto LABEL_74;
  }
  v31 = v44;
  if ( (unsigned int)DigestStorageMetadataHelper(v44, hModule, v46, 1, a5) )
  {
    if ( v46 )
      ((void (__fastcall *)(struct IStorage *))v46->lpVtbl->Release)(v46);
    goto LABEL_32;
  }
  LastError = GetLastError();
  v21 = 0;
  if ( v46 )
    ((void (__fastcall *)(struct IStorage *))v46->lpVtbl->Release)(v46);
LABEL_75:
  if ( (_DWORD)v11 )
  {
    v41 = (void (*)(void))GetProcAddress(v31, "CoTaskMemFree");
    if ( v41 )
    {
      v42 = 0;
      do
      {
        if ( *((_QWORD *)v12 + 10 * (int)v42) )
          v41();
        ++v42;
      }
      while ( v42 < (unsigned int)v11 );
    }
  }
  LocalFree(v12);
  if ( !v21 )
    SetLastError(LastError);
  return v21;
}

```

## disassembly

```asm
0x180003370  push    rbp
0x180003372  push    rsi
0x180003373  push    rdi
0x180003374  push    r12
0x180003376  push    r13
0x180003378  push    r14
0x18000337a  push    r15
0x18000337c  lea     rbp, [rsp-300h]
0x180003384  sub     rsp, 400h
0x18000338b  mov     [rsp+430h+var_3B8], 0FFFFFFFFFFFFFFFEh
0x180003394  mov     [rsp+430h+arg_18], rbx
0x18000339c  mov     rax, cs:__security_cookie
0x1800033a3  xor     rax, rsp
0x1800033a6  mov     [rbp+330h+var_40], rax
0x1800033ad  movzx   r13d, r9b
0x1800033b1  mov     rbx, r8
0x1800033b4  mov     [rsp+430h+var_3C8], rbx
0x1800033b9  mov     rax, rdx
0x1800033bc  mov     [rsp+430h+hModule], rdx
0x1800033c1  mov     rsi, rcx
0x1800033c4  mov     [rsp+430h+var_3E8], rcx
0x1800033c9  test    rcx, rcx
0x1800033cc  jz      loc_180003917
0x1800033d2  test    rdx, rdx
0x1800033d5  jz      loc_180003917
0x1800033db  lea     rdx, aCrypthashdata; "CryptHashData"
0x1800033e2  mov     rcx, rax; hModule
0x1800033e5  call    cs:__imp_GetProcAddress
0x1800033eb  mov     r15, rax
0x1800033ee  test    rax, rax
0x1800033f1  jz      loc_180003917
0x1800033f7  mov     r12, [rbp+330h+arg_20]
0x1800033fe  test    r13b, r13b
0x180003401  jnz     short loc_18000347B
0x180003403  xorps   xmm0, xmm0
0x180003406  movups  [rbp+330h+var_3B0], xmm0
0x18000340a  movups  [rbp+330h+var_3A0], xmm0
0x18000340e  movups  [rbp+330h+var_390], xmm0
0x180003412  movups  [rbp+330h+var_380], xmm0
0x180003416  movups  [rbp+330h+var_370], xmm0
0x18000341a  mov     rax, [rbx]
0x18000341d  xor     r8d, r8d
0x180003420  lea     rdx, [rbp+330h+var_3B0]
0x180003424  mov     rcx, rbx
0x180003427  mov     rax, [rax+88h]
0x18000342e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003433  test    eax, eax
0x180003435  js      loc_1800039B6
0x18000343b  xor     r9d, r9d
0x18000343e  mov     r8d, 10h
0x180003444  lea     rdx, [rbp+330h+var_380+8]
0x180003448  mov     rcx, r12
0x18000344b  mov     rax, r15
0x18000344e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003453  test    eax, eax
0x180003455  jz      loc_180003917
0x18000345b  xor     r9d, r9d
0x18000345e  mov     r8d, 4
0x180003464  lea     rdx, [rbp+330h+var_370+8]
0x180003468  mov     rcx, r12
0x18000346b  mov     rax, r15
0x18000346e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003473  test    eax, eax
0x180003475  jz      loc_180003917
0x18000347b  mov     [rsp+430h+var_3E0], 0
0x180003484  mov     rax, [rbx]
0x180003487  lea     rcx, [rsp+430h+var_3E0]
0x18000348c  mov     [rsp+430h+var_410], rcx
0x180003491  xor     r9d, r9d
0x180003494  xor     r8d, r8d
0x180003497  xor     edx, edx
0x180003499  mov     rcx, rbx
0x18000349c  mov     rax, [rax+58h]
0x1800034a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034a5  test    eax, eax
0x1800034a7  js      loc_1800039B6
0x1800034ad  cmp     [rsp+430h+var_3E0], 0
0x1800034b3  jz      loc_1800039B6
0x1800034b9  mov     edi, 0FFFFFFFFh
0x1800034be  mov     [rsp+430h+var_3F0], edi
0x1800034c2  xor     r14d, r14d
0x1800034c5  test    edi, edi
0x1800034c7  jnz     loc_18000369F
0x1800034cd  xor     esi, esi
0x1800034cf  test    r14d, r14d
0x1800034d2  jz      short loc_180003552
0x1800034d4  lea     rdx, [r14+r14*4]
0x1800034d8  shl     rdx, 4; uBytes
0x1800034dc  mov     ecx, 40h ; '@'; uFlags
0x1800034e1  call    cs:__imp_LocalAlloc
0x1800034e7  mov     rsi, rax
0x1800034ea  mov     rcx, [rsp+430h+var_3E0]
0x1800034ef  test    rax, rax
0x1800034f2  mov     rax, [rcx]
0x1800034f5  jz      loc_180003A33
0x1800034fb  mov     rax, [rax+28h]
0x1800034ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003504  mov     [rsp+430h+var_3F0], 0
0x18000350c  mov     rcx, [rsp+430h+var_3E0]
0x180003511  mov     rax, [rcx]
0x180003514  lea     r9, [rsp+430h+var_3F0]
0x180003519  mov     r8, rsi
0x18000351c  mov     edx, r14d
0x18000351f  mov     rax, [rax+18h]
0x180003523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003528  mov     ebx, eax
0x18000352a  mov     r8d, [rsp+430h+var_3F0]; unsigned int
0x18000352f  test    eax, eax
0x180003531  js      loc_1800038E7
0x180003537  cmp     r14d, r8d
0x18000353a  jnz     loc_1800038E7
0x180003540  lea     r9d, [r14-1]; unsigned int
0x180003544  xor     r8d, r8d; unsigned int
0x180003547  mov     edx, r14d; unsigned int
0x18000354a  mov     rcx, rsi; struct tagSTATSTG *
0x18000354d  call    ?QSortStatStg@@YAXPEAUtagSTATSTG@@KII@Z; QSortStatStg(tagSTATSTG *,ulong,uint,uint)
0x180003552  mov     rcx, [rsp+430h+var_3E0]
0x180003557  mov     rax, [rcx]
0x18000355a  mov     rax, [rax+10h]
0x18000355e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003563  test    rsi, rsi
0x180003566  jz      loc_180003917
0x18000356c  mov     [rsp+430h+var_3D0], 0
0x180003574  xor     edi, edi
0x180003576  mov     r9d, 80070057h
0x18000357c  cmp     edi, r14d
0x18000357f  jnb     loc_180003A46
0x180003585  lea     rbx, [rdi+rdi*4]
0x180003589  shl     rbx, 4
0x18000358d  add     rbx, rsi
0x180003590  mov     ecx, [rbx+8]
0x180003593  sub     ecx, 1
0x180003596  jz      loc_180003665
0x18000359c  cmp     ecx, 1
0x18000359f  jnz     loc_18000391B
0x1800035a5  test    r13b, r13b
0x1800035a8  jz      loc_180003879
0x1800035ae  mov     rdx, [rbx]
0x1800035b1  test    rdx, rdx
0x1800035b4  jz      short loc_1800035D0
0x1800035b6  mov     ecx, 7FFFFFFFh
0x1800035bb  mov     rax, rdx
0x1800035be  xchg    ax, ax
0x1800035c0  cmp     word ptr [rax], 0
0x1800035c4  jz      short loc_1800035DC
0x1800035c6  add     rax, 2
0x1800035ca  sub     rcx, 1
0x1800035ce  jnz     short loc_1800035C0
0x1800035d0  movzx   r12d, r9w
0x1800035d4  xor     r15d, r15d
0x1800035d7  jmp     loc_180003924
0x1800035dc  lea     eax, [rcx+rcx]
0x1800035df  mov     r8d, 0FFFFFFFEh
0x1800035e5  sub     r8d, eax
0x1800035e8  xor     r9d, r9d
0x1800035eb  mov     rcx, r12
0x1800035ee  mov     rax, r15
0x1800035f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f6  test    eax, eax
0x1800035f8  jz      loc_180003A05
0x1800035fe  lea     rdx, [rbx+10h]
0x180003602  xor     r9d, r9d
0x180003605  mov     r8d, 8
0x18000360b  mov     rcx, r12
0x18000360e  mov     rax, r15
0x180003611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003616  test    eax, eax
0x180003618  jz      loc_180003A05
0x18000361e  lea     rdx, [rbx+20h]
0x180003622  xor     r9d, r9d
0x180003625  mov     r8d, 8
0x18000362b  mov     rcx, r12
0x18000362e  mov     rax, r15
0x180003631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003636  test    eax, eax
0x180003638  jz      loc_180003A05
0x18000363e  lea     rdx, [rbx+18h]
0x180003642  xor     r9d, r9d
0x180003645  mov     r8d, 8
0x18000364b  mov     rcx, r12
0x18000364e  mov     rax, r15
0x180003651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003656  test    eax, eax
0x180003658  jz      loc_180003A05
0x18000365e  inc     edi
0x180003660  jmp     loc_180003576
0x180003665  mov     rdx, [rbx]
0x180003668  test    rdx, rdx
0x18000366b  jz      loc_180003A24
0x180003671  mov     ecx, 7FFFFFFFh
0x180003676  mov     rax, rdx
0x180003679  nop     dword ptr [rax+00000000h]
0x180003680  cmp     word ptr [rax], 0
0x180003684  jz      loc_180003740
0x18000368a  add     rax, 2
0x18000368e  sub     rcx, 1
0x180003692  jnz     short loc_180003680
0x180003694  xor     r8d, r8d
0x180003697  mov     eax, r9d
0x18000369a  jmp     loc_18000374B
0x18000369f  mov     rcx, [rsp+430h+var_3E0]
0x1800036a4  mov     rax, [rcx]
0x1800036a7  lea     r9, [rsp+430h+var_3F0]
0x1800036ac  lea     r8, [rbp+330h+var_360]
0x1800036b0  mov     edx, 0Ah
0x1800036b5  mov     rax, [rax+18h]
0x1800036b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036be  mov     ebx, eax
0x1800036c0  test    eax, eax
0x1800036c2  js      loc_1800038FD
0x1800036c8  mov     edi, [rsp+430h+var_3F0]
0x1800036cc  cmp     edi, 0Ah
0x1800036cf  ja      loc_1800038FD
0x1800036d5  add     r14d, edi
0x1800036d8  test    edi, edi
0x1800036da  jz      loc_1800034CD
0x1800036e0  lea     rdx, aCotaskmemfree; "CoTaskMemFree"
0x1800036e7  mov     rcx, rsi; hModule
0x1800036ea  call    cs:__imp_GetProcAddress
0x1800036f0  mov     rsi, rax
0x1800036f3  test    rax, rax
0x1800036f6  jz      loc_180003A16
0x1800036fc  xor     ebx, ebx
0x1800036fe  test    edi, edi
0x180003700  jz      loc_180003A16
0x180003706  nop     word ptr [rax+rax+00000000h]
0x180003710  movsxd  rax, ebx
0x180003713  lea     rcx, [rax+rax*4]
0x180003717  add     rcx, rcx
0x18000371a  mov     rcx, [rbp+rcx*8+330h+var_360]
0x18000371f  test    rcx, rcx
0x180003722  jz      short loc_18000372C
0x180003724  mov     rax, rsi
0x180003727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000372c  inc     ebx
0x18000372e  cmp     ebx, edi
0x180003730  jb      short loc_180003710
0x180003732  mov     edi, [rsp+430h+var_3F0]
0x180003736  mov     rsi, [rsp+430h+var_3E8]
0x18000373b  jmp     loc_1800034C5
0x180003740  mov     r8d, 7FFFFFFFh
0x180003746  sub     r8, rcx
0x180003749  xor     eax, eax
0x18000374b  test    eax, eax
0x18000374d  js      loc_180003A27
0x180003753  add     r8d, r8d
0x180003756  xor     r9d, r9d
0x180003759  mov     rcx, r12
0x18000375c  mov     rax, r15
0x18000375f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003764  test    eax, eax
0x180003766  jz      loc_180003A05
0x18000376c  lea     rdx, [rbx+38h]
0x180003770  xor     r9d, r9d
0x180003773  mov     r8d, 10h
0x180003779  mov     rcx, r12
0x18000377c  mov     rax, r15
0x18000377f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003784  test    eax, eax
0x180003786  jz      loc_180003A05
0x18000378c  lea     rdx, [rbx+48h]
0x180003790  xor     r9d, r9d
0x180003793  mov     r8d, 4
0x180003799  mov     rcx, r12
0x18000379c  mov     rax, r15
0x18000379f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037a4  test    eax, eax
0x1800037a6  jz      loc_180003A05
0x1800037ac  lea     rdx, [rbx+20h]
0x1800037b0  xor     r9d, r9d
0x1800037b3  mov     r8d, 8
0x1800037b9  mov     rcx, r12
0x1800037bc  mov     rax, r15
0x1800037bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c4  test    eax, eax
0x1800037c6  jz      loc_180003A05
0x1800037cc  lea     rdx, [rbx+18h]
0x1800037d0  xor     r9d, r9d
0x1800037d3  mov     r8d, 8
0x1800037d9  mov     rcx, r12
0x1800037dc  mov     rax, r15
0x1800037df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e4  test    eax, eax
0x1800037e6  jz      loc_180003A05
0x1800037ec  xor     r8d, r8d
0x1800037ef  mov     [rsp+430h+var_3D8], r8
0x1800037f4  mov     rcx, [rsp+430h+var_3C8]
0x1800037f9  mov     rax, [rcx]
0x1800037fc  lea     rdx, [rsp+430h+var_3D8]
0x180003801  mov     [rsp+430h+var_400], rdx
0x180003806  mov     [rsp+430h+var_408], r8d
0x18000380b  mov     [rsp+430h+var_410], r8
0x180003810  mov     r9d, 10h
0x180003816  mov     rdx, [rbx]
0x180003819  mov     rax, [rax+30h]
0x18000381d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003822  mov     rcx, [rsp+430h+var_3D8]
0x180003827  test    eax, eax
0x180003829  js      loc_1800039E7
0x18000382f  test    rcx, rcx
  ... truncated ...
```
