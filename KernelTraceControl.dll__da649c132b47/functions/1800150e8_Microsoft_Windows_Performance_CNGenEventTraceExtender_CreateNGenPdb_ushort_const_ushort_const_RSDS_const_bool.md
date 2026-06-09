# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)

- ea: `0x1800150e8`
- end: `0x1800153f0`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z`
- size: `776`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, char *, const unsigned __int16 *, const struct _RSDS *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014e44`

## callees

- `0x18000139c`
- `0x18000e858`
- `0x180012df4`
- `0x180012f28`
- `0x180013cac`
- `0x180013d24`
- `0x1800150e8`
- `0x1800153f0`
- `0x1800155bc`
- `0x180015694`
- `0x180015a08`
- `0x180027910`

## import_xrefs

- `msvcrt!strrchr` at `0x180015127`
- `msvcrt!strrchr` at `0x180015138`
- `msvcrt!strrchr` at `0x180015127`
- `msvcrt!strrchr` at `0x180015138`
- `KERNEL32!CloseHandle` at `0x1800151e5`
- `KERNEL32!CloseHandle` at `0x18001538f`
- `KERNEL32!CloseHandle` at `0x1800151e5`
- `KERNEL32!CloseHandle` at `0x18001538f`
- `KERNEL32!CreateFileW` at `0x1800151d6`
- `KERNEL32!CreateFileW` at `0x180015380`
- `KERNEL32!CreateFileW` at `0x1800151d6`
- `KERNEL32!CreateFileW` at `0x180015380`

## string_xrefs

- `0x18001527b`: `%wsngen.exe createpdb %ws %ws`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        char *a2,
        const unsigned __int16 *a3,
        const struct _RSDS *a4,
        bool a5)
{
  const char *v9; // r15
  char *v10; // rbx
  char *v11; // rax
  int v12; // ecx
  __int64 v13; // rax
  const unsigned __int16 *v14; // rbx
  HANDLE FileW; // rax
  __int64 v16; // rcx
  char *v17; // rax
  char *v18; // rsi
  unsigned __int16 v19; // cx
  int v20; // eax
  __int64 v21; // r8
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v22; // rcx
  unsigned __int16 *v23; // rbx
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // edi
  unsigned __int16 *v28; // rdx
  int v29; // eax
  char *v30; // rax
  char *v31; // rsi
  unsigned __int16 v32; // cx
  int v33; // eax
  HANDLE v34; // rax
  LPCWSTR lpFileName; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v37[3]; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v38; // [rsp+A8h] [rbp+48h] BYREF

  v37[1] = (unsigned __int16 *)-2LL;
  v9 = (char *)a4 + 24;
  v10 = strrchr((const char *)a4 + 24, 47);
  v11 = strrchr(v9, 92);
  if ( v10 > v11 )
    v11 = v10;
  if ( v11 )
    v9 = v11 + 1;
  lpFileName = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
    v12,
    (unsigned int)&lpFileName,
    (_DWORD)a2,
    (_DWORD)v9,
    (__int64)a4);
  v13 = -1;
  do
    ++v13;
  while ( SubBlock[v13] );
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpFileName, L"\\", (unsigned int)v13);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(
    &lpFileName,
    v9);
  v14 = lpFileName;
  FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    CloseHandle(FileW);
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      Template_z(v16, TraceMerge_NGEN_CandidateEncountered_ExistingPDB, v14);
    if ( !a2 )
      ATL::AtlThrowImpl(-2147467259);
    v17 = (char *)*((_QWORD *)this + 7);
    v18 = (char *)(a2 - v17);
    while ( 1 )
    {
      v19 = *(_WORD *)v17;
      if ( *(_WORD *)v17 != *(_WORD *)&v18[(_QWORD)v17] )
        break;
      v17 += 2;
      if ( !v19 )
      {
        v20 = 0;
        goto LABEL_17;
      }
    }
    v20 = v19 < *(_WORD *)&v18[(_QWORD)v17] ? -1 : 1;
LABEL_17:
    if ( v20 )
    {
LABEL_44:
      v27 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v9, a4);
      if ( v27 < 0 )
        goto LABEL_46;
      goto LABEL_45;
    }
    goto LABEL_45;
  }
  v37[0] = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( a5 )
    v21 = *((_QWORD *)this + 6);
  else
    v21 = *((_QWORD *)this + 5);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    v37,
    L"%wsngen.exe createpdb %ws %ws",
    v21,
    a3,
    a2);
  v23 = v37[0];
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    Template_z(v22, TraceMerge_NGEN_CreatingPDB_Start, v37[0]);
  v38 = 0;
  if ( *((int *)v23 - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(v37, *((unsigned int *)v23 - 4));
    v23 = v37[0];
  }
  v24 = Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(v22, v23, &v38);
  v27 = v24;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    Template_qq(v26, v25, v24, v38);
  v28 = v23 - 12;
  v29 = _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF);
  if ( v27 >= 0 )
  {
    if ( v29 <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 8LL))(*(_QWORD *)v28);
    if ( !a2 )
      ATL::AtlThrowImpl(-2147467259);
    v30 = (char *)*((_QWORD *)this + 7);
    v31 = (char *)(a2 - v30);
    while ( 1 )
    {
      v32 = *(_WORD *)v30;
      if ( *(_WORD *)v30 != *(_WORD *)&v31[(_QWORD)v30] )
        break;
      v30 += 2;
      if ( !v32 )
      {
        v33 = 0;
        goto LABEL_41;
      }
    }
    v33 = v32 < *(_WORD *)&v31[(_QWORD)v30] ? -1 : 1;
LABEL_41:
    v14 = lpFileName;
    if ( v33 )
    {
      v34 = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
      if ( v34 != (HANDLE)-1LL )
      {
        CloseHandle(v34);
        goto LABEL_44;
      }
    }
LABEL_45:
    v27 = 0;
    goto LABEL_46;
  }
  if ( v29 <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 8LL))(*(_QWORD *)v28);
  v14 = lpFileName;
LABEL_46:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x1800150e8  mov     rax, rsp
0x1800150eb  push    rbp
0x1800150ec  push    r12
0x1800150ee  push    r13
0x1800150f0  push    r14
0x1800150f2  push    r15
0x1800150f4  mov     rbp, rsp
0x1800150f7  sub     rsp, 60h
0x1800150fb  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180015103  mov     [rax+8], rbx
0x180015107  mov     [rax+10h], rsi
0x18001510b  mov     [rax+18h], rdi
0x18001510f  mov     r13, r9
0x180015112  mov     rdi, r8
0x180015115  mov     rsi, rdx
0x180015118  mov     r14, rcx
0x18001511b  lea     r15, [r9+18h]
0x18001511f  mov     edx, 2Fh ; '/'; Ch
0x180015124  mov     rcx, r15; Str
0x180015127  call    cs:__imp_strrchr
0x18001512d  mov     rbx, rax
0x180015130  mov     edx, 5Ch ; '\'; Ch
0x180015135  mov     rcx, r15; Str
0x180015138  call    cs:__imp_strrchr
0x18001513e  cmp     rbx, rax
0x180015141  cmova   rax, rbx
0x180015145  lea     rcx, [rax+1]
0x180015149  xor     r12d, r12d
0x18001514c  test    rax, rax
0x18001514f  cmovnz  r15, rcx
0x180015153  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001515a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180015161  mov     rax, [rax+18h]
0x180015165  call    cs:__guard_dispatch_icall_fptr
0x18001516b  add     rax, 18h
0x18001516f  mov     [rbp+lpFileName], rax
0x180015173  mov     qword ptr [rsp+60h+dwCreationDisposition], r13
0x180015178  mov     r9, r15
0x18001517b  mov     r8, rsi
0x18001517e  lea     rdx, [rbp+lpFileName]
0x180015182  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x180015187  lea     rdx, SubBlock; "\\"
0x18001518e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015192  inc     rax
0x180015195  cmp     [rdx+rax*2], r12w
0x18001519a  jnz     short loc_180015192
0x18001519c  mov     r8d, eax
0x18001519f  lea     rcx, [rbp+lpFileName]
0x1800151a3  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800151a8  mov     rdx, r15
0x1800151ab  lea     rcx, [rbp+lpFileName]
0x1800151af  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x1800151b4  mov     [rsp+60h+hTemplateFile], r12; hTemplateFile
0x1800151b9  mov     [rsp+60h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800151be  mov     eax, 3
0x1800151c3  mov     [rsp+60h+dwCreationDisposition], eax; dwCreationDisposition
0x1800151c7  xor     r9d, r9d; lpSecurityAttributes
0x1800151ca  mov     r8d, eax; dwShareMode
0x1800151cd  xor     edx, edx; dwDesiredAccess
0x1800151cf  mov     rbx, [rbp+lpFileName]
0x1800151d3  mov     rcx, rbx; lpFileName
0x1800151d6  call    cs:__imp_CreateFileW
0x1800151dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800151e0  jz      short loc_180015243
0x1800151e2  mov     rcx, rax; hObject
0x1800151e5  call    cs:__imp_CloseHandle
0x1800151eb  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x1800151f2  jz      short loc_180015203
0x1800151f4  mov     r8, rbx
0x1800151f7  lea     rdx, TraceMerge_NGEN_CandidateEncountered_ExistingPDB
0x1800151fe  call    Template_z
0x180015203  test    rsi, rsi
0x180015206  jnz     short loc_180015213
0x180015208  mov     ecx, 80004005h; int
0x18001520d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015213  mov     rax, [r14+38h]
0x180015217  sub     rsi, rax
0x18001521a  movzx   ecx, word ptr [rax]
0x18001521d  cmp     cx, [rax+rsi]
0x180015221  jnz     short loc_180015231
0x180015223  add     rax, 2
0x180015227  test    cx, cx
0x18001522a  jnz     short loc_18001521A
0x18001522c  mov     eax, r12d
0x18001522f  jmp     short loc_180015236
0x180015231  sbb     eax, eax
0x180015233  or      eax, 1
0x180015236  test    eax, eax
0x180015238  jz      loc_1800153AC
0x18001523e  jmp     loc_180015395
0x180015243  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001524a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180015251  mov     rax, [rax+18h]
0x180015255  call    cs:__guard_dispatch_icall_fptr
0x18001525b  add     rax, 18h
0x18001525f  mov     [rbp+var_18], rax
0x180015263  cmp     [rbp+arg_20], r12b
0x180015267  jz      short loc_18001526F
0x180015269  mov     r8, [r14+30h]
0x18001526d  jmp     short loc_180015273
0x18001526f  mov     r8, [r14+28h]
0x180015273  mov     qword ptr [rsp+60h+dwCreationDisposition], rsi
0x180015278  mov     r9, rdi
0x18001527b  lea     rdx, aWsngenExeCreat; "%wsngen.exe createpdb %ws %ws"
0x180015282  lea     rcx, [rbp+var_18]
0x180015286  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001528b  mov     rbx, [rbp+var_18]
0x18001528f  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x180015296  jz      short loc_1800152A7
0x180015298  mov     r8, rbx
0x18001529b  lea     rdx, TraceMerge_NGEN_CreatingPDB_Start
0x1800152a2  call    Template_z
0x1800152a7  mov     [rbp+arg_18], r12d
0x1800152ab  cmp     dword ptr [rbx-8], 1
0x1800152af  jle     short loc_1800152C1
0x1800152b1  mov     edx, [rbx-10h]
0x1800152b4  lea     rcx, [rbp+var_18]
0x1800152b8  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x1800152bd  mov     rbx, [rbp+var_18]
0x1800152c1  lea     r8, [rbp+arg_18]; unsigned int *
0x1800152c5  mov     rdx, rbx; unsigned __int16 *
0x1800152c8  call    ?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)
0x1800152cd  mov     edi, eax
0x1800152cf  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x1800152d6  jz      short loc_1800152E5
0x1800152d8  mov     r9d, [rbp+arg_18]
0x1800152dc  mov     r8d, eax
0x1800152df  call    Template_qq
0x1800152e4  nop
0x1800152e5  lea     rdx, [rbx-18h]
0x1800152e9  or      eax, 0FFFFFFFFh
0x1800152ec  lock xadd [rdx+10h], eax
0x1800152f1  test    edi, edi
0x1800152f3  jns     short loc_180015313
0x1800152f5  sub     eax, 1
0x1800152f8  jg      short loc_18001530A
0x1800152fa  mov     rcx, [rdx]
0x1800152fd  mov     rax, [rcx]
0x180015300  mov     rax, [rax+8]
0x180015304  call    cs:__guard_dispatch_icall_fptr
0x18001530a  mov     rbx, [rbp+lpFileName]
0x18001530e  jmp     loc_1800153AF
0x180015313  sub     eax, 1
0x180015316  jg      short loc_180015328
0x180015318  mov     rcx, [rdx]
0x18001531b  mov     rax, [rcx]
0x18001531e  mov     rax, [rax+8]
0x180015322  call    cs:__guard_dispatch_icall_fptr
0x180015328  test    rsi, rsi
0x18001532b  jnz     short loc_180015338
0x18001532d  mov     ecx, 80004005h; int
0x180015332  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015338  mov     rax, [r14+38h]
0x18001533c  sub     rsi, rax
0x18001533f  movzx   ecx, word ptr [rax]
0x180015342  cmp     cx, [rax+rsi]
0x180015346  jnz     short loc_180015356
0x180015348  add     rax, 2
0x18001534c  test    cx, cx
0x18001534f  jnz     short loc_18001533F
0x180015351  mov     eax, r12d
0x180015354  jmp     short loc_18001535B
0x180015356  sbb     eax, eax
0x180015358  or      eax, 1
0x18001535b  mov     rbx, [rbp+lpFileName]
0x18001535f  test    eax, eax
0x180015361  jz      short loc_1800153AC
0x180015363  mov     [rsp+60h+hTemplateFile], r12; hTemplateFile
0x180015368  mov     [rsp+60h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18001536d  mov     r8d, 3; dwShareMode
0x180015373  mov     [rsp+60h+dwCreationDisposition], r8d; dwCreationDisposition
0x180015378  xor     r9d, r9d; lpSecurityAttributes
0x18001537b  xor     edx, edx; dwDesiredAccess
0x18001537d  mov     rcx, rbx; lpFileName
0x180015380  call    cs:__imp_CreateFileW
0x180015386  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001538a  jz      short loc_1800153AC
0x18001538c  mov     rcx, rax; hObject
0x18001538f  call    cs:__imp_CloseHandle
0x180015395  mov     r9, r13; struct _RSDS *
0x180015398  mov     r8, r15; char *
0x18001539b  mov     rdx, rbx; unsigned __int16 *
0x18001539e  mov     rcx, r14; this
0x1800153a1  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x1800153a6  test    eax, eax
0x1800153a8  mov     edi, eax
0x1800153aa  js      short loc_1800153AF
0x1800153ac  mov     edi, r12d
0x1800153af  lea     rdx, [rbx-18h]
0x1800153b3  or      ecx, 0FFFFFFFFh
0x1800153b6  lock xadd [rdx+10h], ecx
0x1800153bb  sub     ecx, 1
0x1800153be  jg      short loc_1800153D0
0x1800153c0  mov     rcx, [rdx]
0x1800153c3  mov     r8, [rcx]
0x1800153c6  mov     rax, [r8+8]
0x1800153ca  call    cs:__guard_dispatch_icall_fptr
0x1800153d0  mov     eax, edi
0x1800153d2  lea     r11, [rsp+60h+var_s0]
0x1800153d7  mov     rbx, [r11+30h]
0x1800153db  mov     rsi, [r11+38h]
0x1800153df  mov     rdi, [r11+40h]
0x1800153e3  mov     rsp, r11
0x1800153e6  pop     r15
0x1800153e8  pop     r14
0x1800153ea  pop     r13
0x1800153ec  pop     r12
0x1800153ee  pop     rbp
0x1800153ef  retn
```
