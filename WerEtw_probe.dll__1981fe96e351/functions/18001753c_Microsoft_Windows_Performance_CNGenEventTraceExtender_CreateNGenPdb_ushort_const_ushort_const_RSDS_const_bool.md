# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)

- ea: `0x18001753c`
- end: `0x180017931`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z`
- size: `1013`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const struct _RSDS *@<r9>, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017214`

## callees

- `0x180001870`
- `0x180003bb8`
- `0x1800045d4`
- `0x180005304`
- `0x1800053a8`
- `0x1800164e0`
- `0x180016e84`
- `0x18001753c`
- `0x180017938`
- `0x1800179fc`
- `0x180018910`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001757b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001758c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001757b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001758c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001761a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017894`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001761a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017894`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001762d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800178a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001762d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800178a3`

## string_xrefs

- `0x1800176ef`: `%wsngen.exe createpdb %ws %ws`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        char *a2,
        const unsigned __int16 *a3,
        const struct _RSDS *a4,
        bool a5)
{
  const char *v5; // rdi
  char *v10; // rbx
  char *v11; // rax
  const char *v12; // r12
  int v13; // ecx
  const unsigned __int16 *v14; // rbx
  HANDLE FileW; // rax
  __int64 v16; // r8
  __int64 v17; // rcx
  const wchar_t *v18; // rax
  __int64 v19; // rcx
  char *v20; // rax
  char *v21; // rsi
  int v22; // r9d
  int v23; // edx
  int v24; // edi
  bool v25; // sf
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v26; // rcx
  __int64 v27; // r8
  unsigned __int16 *v28; // rdi
  __int64 v29; // rcx
  LPCWSTR v30; // rax
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // r8
  int v34; // r14d
  unsigned __int16 *v35; // rdx
  int v36; // eax
  char *v38; // rax
  char *v39; // rsi
  int v40; // edx
  int v41; // ecx
  HANDLE v42; // rax
  LPCWSTR lpFileName; // [rsp+40h] [rbp-41h] BYREF
  unsigned int v44; // [rsp+48h] [rbp-39h] BYREF
  int v45; // [rsp+50h] [rbp-31h] BYREF
  _BYTE v46[16]; // [rsp+58h] [rbp-29h] BYREF
  const wchar_t *v47; // [rsp+68h] [rbp-19h]
  __int64 v48; // [rsp+70h] [rbp-11h]
  LPCWSTR *p_lpFileName; // [rsp+78h] [rbp-9h]
  __int64 v50; // [rsp+80h] [rbp-1h]

  v5 = (char *)a4 + 24;
  v10 = strrchr((const char *)a4 + 24, 47);
  v11 = strrchr(v5, 92);
  if ( v10 > v11 )
    v11 = v10;
  v12 = v11 + 1;
  if ( !v11 )
    v12 = v5;
  lpFileName = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
    v13,
    (unsigned int)&lpFileName,
    (_DWORD)a2,
    (_DWORD)v12,
    (__int64)a4);
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpFileName, L"\\", 1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(
    &lpFileName,
    v12);
  v14 = lpFileName;
  FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    CloseHandle(FileW);
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    {
      if ( v14 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v14[v17] );
        v18 = v14;
        v19 = (unsigned int)(2 * v17 + 2);
      }
      else
      {
        v18 = L"NULL";
        v19 = 10;
      }
      v47 = v18;
      v48 = (unsigned int)v19;
      McGenEventWrite_EventWriteTransfer(v19, &TraceMerge_NGEN_CandidateEncountered_ExistingPDB, v16, 2, v46);
    }
    if ( a2 )
    {
      v20 = (char *)*((_QWORD *)this + 7);
      v21 = (char *)(a2 - v20);
      do
      {
        v22 = *(unsigned __int16 *)&v21[(_QWORD)v20];
        v23 = *(unsigned __int16 *)v20 - v22;
        if ( v23 )
          break;
        v20 += 2;
      }
      while ( v22 );
      if ( v23 )
      {
        v24 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v12, a4);
        v25 = v24 < 0;
        goto LABEL_45;
      }
      goto LABEL_49;
    }
    goto LABEL_52;
  }
  lpFileName = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &lpFileName,
    L"%wsngen.exe createpdb %ws %ws",
    *((_QWORD *)this + a5 + 5),
    a3,
    a2);
  v28 = (unsigned __int16 *)lpFileName;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
  {
    if ( lpFileName )
    {
      v29 = -1;
      do
        ++v29;
      while ( lpFileName[v29] );
      v30 = lpFileName;
      v31 = (unsigned int)(2 * v29 + 2);
    }
    else
    {
      v30 = L"NULL";
      v31 = 10;
    }
    v47 = v30;
    v48 = (unsigned int)v31;
    McGenEventWrite_EventWriteTransfer(v31, &TraceMerge_NGEN_CreatingPDB_Start, v27, 2, v46);
  }
  v44 = 0;
  if ( *((int *)v28 - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(&lpFileName, *((unsigned int *)v28 - 4));
    v28 = (unsigned __int16 *)lpFileName;
  }
  v32 = Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(v26, v28, &v44);
  v34 = v32;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
  {
    v45 = v32;
    LODWORD(lpFileName) = v44;
    v47 = (const wchar_t *)&v45;
    p_lpFileName = &lpFileName;
    v48 = 4;
    v50 = 4;
    McGenEventWrite_EventWriteTransfer(v44, &TraceMerge_NGEN_CreatingPDB_Stop, v33, 3, v46);
  }
  v35 = v28 - 12;
  v36 = _InterlockedExchangeAdd((volatile signed __int32 *)v28 - 2, 0xFFFFFFFF);
  if ( v34 >= 0 )
  {
    if ( v36 <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 8LL))(*(_QWORD *)v35);
    if ( a2 )
    {
      v38 = (char *)*((_QWORD *)this + 7);
      v39 = (char *)(a2 - v38);
      do
      {
        v40 = *(unsigned __int16 *)&v39[(_QWORD)v38];
        v41 = *(unsigned __int16 *)v38 - v40;
        if ( v41 )
          break;
        v38 += 2;
      }
      while ( v40 );
      if ( v41 )
      {
        v42 = CreateFileW(v14, 0, 3u, 0, 3u, 0, 0);
        if ( v42 != (HANDLE)-1LL )
        {
          CloseHandle(v42);
          v24 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v12, a4);
          v25 = v24 < 0;
LABEL_45:
          if ( v25 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
            return (unsigned int)v24;
          }
        }
      }
LABEL_49:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
      return 0;
    }
LABEL_52:
    ATL::AtlThrowImpl(-2147467259);
  }
  if ( v36 <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 8LL))(*(_QWORD *)v35);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x18001753c  push    rbp
0x18001753e  push    rbx
0x18001753f  push    rsi
0x180017540  push    rdi
0x180017541  push    r12
0x180017543  push    r13
0x180017545  push    r14
0x180017547  push    r15
0x180017549  lea     rbp, [rsp-17h]
0x18001754e  sub     rsp, 98h
0x180017555  mov     rax, cs:__security_cookie
0x18001755c  xor     rax, rsp
0x18001755f  mov     [rbp+4Fh+var_48], rax
0x180017563  lea     rdi, [r9+18h]
0x180017567  mov     rsi, rdx
0x18001756a  mov     r15, rcx
0x18001756d  mov     edx, 2Fh ; '/'; Ch
0x180017572  mov     rcx, rdi; Str
0x180017575  mov     r13, r9
0x180017578  mov     r14, r8
0x18001757b  call    cs:__imp_strrchr
0x180017581  mov     edx, 5Ch ; '\'; Ch
0x180017586  mov     rcx, rdi; Str
0x180017589  mov     rbx, rax
0x18001758c  call    cs:__imp_strrchr
0x180017592  cmp     rbx, rax
0x180017595  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001759c  cmova   rax, rbx
0x1800175a0  test    rax, rax
0x1800175a3  lea     r12, [rax+1]
0x1800175a7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800175ae  cmovz   r12, rdi
0x1800175b2  mov     rax, [rax+18h]
0x1800175b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175bb  add     rax, 18h
0x1800175bf  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13
0x1800175c4  mov     r9, r12
0x1800175c7  mov     [rbp+4Fh+lpFileName], rax
0x1800175cb  mov     r8, rsi
0x1800175ce  lea     rdx, [rbp+4Fh+lpFileName]
0x1800175d2  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x1800175d7  mov     r8d, 1
0x1800175dd  lea     rdx, asc_18002D2B0; "\\"
0x1800175e4  lea     rcx, [rbp+4Fh+lpFileName]
0x1800175e8  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800175ed  mov     rdx, r12
0x1800175f0  lea     rcx, [rbp+4Fh+lpFileName]
0x1800175f4  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x1800175f9  mov     rbx, [rbp+4Fh+lpFileName]
0x1800175fd  xor     edi, edi
0x1800175ff  mov     [rsp+0D0h+hTemplateFile], rdi; hTemplateFile
0x180017604  xor     r9d, r9d; lpSecurityAttributes
0x180017607  mov     [rsp+0D0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18001760b  xor     edx, edx; dwDesiredAccess
0x18001760d  mov     rcx, rbx; lpFileName
0x180017610  lea     eax, [rdi+3]
0x180017613  mov     r8d, eax; dwShareMode
0x180017616  mov     [rsp+0D0h+dwCreationDisposition], eax; dwCreationDisposition
0x18001761a  call    cs:__imp_CreateFileW
0x180017620  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017624  jz      loc_1800176D3
0x18001762a  mov     rcx, rax; hObject
0x18001762d  call    cs:__imp_CloseHandle
0x180017633  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18001763a  jz      short loc_18001768B
0x18001763c  test    rbx, rbx
0x18001763f  jz      short loc_18001765A
0x180017641  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180017645  inc     rcx
0x180017648  cmp     [rbx+rcx*2], di
0x18001764c  jnz     short loc_180017645
0x18001764e  mov     rax, rbx
0x180017651  lea     ecx, ds:2[rcx*2]
0x180017658  jmp     short loc_180017666
0x18001765a  lea     rax, aNull; "NULL"
0x180017661  mov     ecx, 0Ah
0x180017666  mov     [rbp+4Fh+var_68], rax
0x18001766a  lea     rdx, TraceMerge_NGEN_CandidateEncountered_ExistingPDB
0x180017671  lea     rax, [rbp+4Fh+var_78]
0x180017675  mov     dword ptr [rbp+4Fh+var_60], ecx
0x180017678  mov     r9d, 2
0x18001767e  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x180017683  mov     dword ptr [rbp+4Fh+var_60+4], edi
0x180017686  call    McGenEventWrite_EventWriteTransfer
0x18001768b  test    rsi, rsi
0x18001768e  jz      loc_180017926
0x180017694  mov     rax, [r15+38h]
0x180017698  sub     rsi, rax
0x18001769b  movzx   edx, word ptr [rax]
0x18001769e  movzx   r9d, word ptr [rax+rsi]
0x1800176a3  sub     edx, r9d
0x1800176a6  jnz     short loc_1800176B1
0x1800176a8  add     rax, 2
0x1800176ac  test    r9d, r9d
0x1800176af  jnz     short loc_18001769B
0x1800176b1  test    edx, edx
0x1800176b3  jz      loc_1800178E4
0x1800176b9  mov     r9, r13; struct _RSDS *
0x1800176bc  mov     r8, r12; char *
0x1800176bf  mov     rdx, rbx; unsigned __int16 *
0x1800176c2  mov     rcx, r15; this
0x1800176c5  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x1800176ca  mov     edi, eax
0x1800176cc  test    eax, eax
0x1800176ce  jmp     loc_1800178BE
0x1800176d3  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800176da  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800176e1  mov     rax, [rax+18h]
0x1800176e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176ea  movzx   r8d, [rbp+4Fh+arg_20]
0x1800176ef  lea     rdx, aWsngenExeCreat; "%wsngen.exe createpdb %ws %ws"
0x1800176f6  add     rax, 18h
0x1800176fa  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rsi
0x1800176ff  mov     [rbp+4Fh+lpFileName], rax
0x180017703  lea     rcx, [rbp+4Fh+lpFileName]
0x180017707  mov     r9, r14
0x18001770a  mov     r8, [r15+r8*8+28h]
0x18001770f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180017714  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18001771b  mov     rdi, [rbp+4Fh+lpFileName]
0x18001771f  jz      short loc_180017772
0x180017721  xor     edx, edx
0x180017723  test    rdi, rdi
0x180017726  jz      short loc_180017741
0x180017728  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001772c  inc     rcx
0x18001772f  cmp     [rdi+rcx*2], dx
0x180017733  jnz     short loc_18001772C
0x180017735  mov     rax, rdi
0x180017738  lea     ecx, ds:2[rcx*2]
0x18001773f  jmp     short loc_18001774D
0x180017741  lea     rax, aNull; "NULL"
0x180017748  mov     ecx, 0Ah
0x18001774d  mov     [rbp+4Fh+var_68], rax
0x180017751  mov     r9d, 2
0x180017757  lea     rax, [rbp+4Fh+var_78]
0x18001775b  mov     dword ptr [rbp+4Fh+var_60+4], edx
0x18001775e  lea     rdx, TraceMerge_NGEN_CreatingPDB_Start
0x180017765  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x18001776a  mov     dword ptr [rbp+4Fh+var_60], ecx
0x18001776d  call    McGenEventWrite_EventWriteTransfer
0x180017772  mov     [rbp+4Fh+var_88], 0
0x180017779  cmp     dword ptr [rdi-8], 1
0x18001777d  jle     short loc_18001778F
0x18001777f  mov     edx, [rdi-10h]
0x180017782  lea     rcx, [rbp+4Fh+lpFileName]
0x180017786  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18001778b  mov     rdi, [rbp+4Fh+lpFileName]
0x18001778f  lea     r8, [rbp+4Fh+var_88]; unsigned int *
0x180017793  mov     rdx, rdi; unsigned __int16 *
0x180017796  call    ?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)
0x18001779b  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x1800177a2  mov     r14d, eax
0x1800177a5  jz      short loc_1800177EB
0x1800177a7  mov     ecx, [rbp+4Fh+var_88]
0x1800177aa  lea     rdx, TraceMerge_NGEN_CreatingPDB_Stop
0x1800177b1  mov     [rbp+4Fh+var_80], eax
0x1800177b4  mov     r9d, 3
0x1800177ba  lea     rax, [rbp+4Fh+var_80]
0x1800177be  mov     dword ptr [rbp+4Fh+lpFileName], ecx
0x1800177c1  mov     [rbp+4Fh+var_68], rax
0x1800177c5  lea     rax, [rbp+4Fh+lpFileName]
0x1800177c9  mov     [rbp+4Fh+var_58], rax
0x1800177cd  lea     rax, [rbp+4Fh+var_78]
0x1800177d1  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x1800177d6  mov     [rbp+4Fh+var_60], 4
0x1800177de  mov     [rbp+4Fh+var_50], 4
0x1800177e6  call    McGenEventWrite_EventWriteTransfer
0x1800177eb  lea     rdx, [rdi-18h]
0x1800177ef  or      eax, 0FFFFFFFFh
0x1800177f2  lock xadd [rdx+10h], eax
0x1800177f7  test    r14d, r14d
0x1800177fa  jns     short loc_180017838
0x1800177fc  sub     eax, 1
0x1800177ff  jg      short loc_180017810
0x180017801  mov     rcx, [rdx]
0x180017804  mov     rax, [rcx]
0x180017807  mov     rax, [rax+8]
0x18001780b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017810  lea     rdx, [rbx-18h]
0x180017814  or      eax, 0FFFFFFFFh
0x180017817  lock xadd [rdx+10h], eax
0x18001781c  sub     eax, 1
0x18001781f  jg      short loc_180017830
0x180017821  mov     rcx, [rdx]
0x180017824  mov     rax, [rcx]
0x180017827  mov     rax, [rax+8]
0x18001782b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017830  mov     eax, r14d
0x180017833  jmp     loc_180017906
0x180017838  xor     r14d, r14d
0x18001783b  sub     eax, 1
0x18001783e  jg      short loc_18001784F
0x180017840  mov     rcx, [rdx]
0x180017843  mov     rax, [rcx]
0x180017846  mov     rax, [rax+8]
0x18001784a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001784f  test    rsi, rsi
0x180017852  jz      loc_180017926
0x180017858  mov     rax, [r15+38h]
0x18001785c  sub     rsi, rax
0x18001785f  movzx   ecx, word ptr [rax]
0x180017862  movzx   edx, word ptr [rax+rsi]
0x180017866  sub     ecx, edx
0x180017868  jnz     short loc_180017872
0x18001786a  add     rax, 2
0x18001786e  test    edx, edx
0x180017870  jnz     short loc_18001785F
0x180017872  test    ecx, ecx
0x180017874  jz      short loc_1800178E4
0x180017876  mov     eax, 3
0x18001787b  mov     [rsp+0D0h+hTemplateFile], r14; hTemplateFile
0x180017880  mov     r8d, eax; dwShareMode
0x180017883  mov     [rsp+0D0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180017888  xor     r9d, r9d; lpSecurityAttributes
0x18001788b  mov     [rsp+0D0h+dwCreationDisposition], eax; dwCreationDisposition
0x18001788f  xor     edx, edx; dwDesiredAccess
0x180017891  mov     rcx, rbx; lpFileName
0x180017894  call    cs:__imp_CreateFileW
0x18001789a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001789e  jz      short loc_1800178E4
0x1800178a0  mov     rcx, rax; hObject
0x1800178a3  call    cs:__imp_CloseHandle
0x1800178a9  mov     r9, r13; struct _RSDS *
0x1800178ac  mov     r8, r12; char *
0x1800178af  mov     rdx, rbx; unsigned __int16 *
0x1800178b2  mov     rcx, r15; this
0x1800178b5  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x1800178ba  mov     edi, eax
0x1800178bc  test    eax, eax
0x1800178be  jns     short loc_1800178E4
0x1800178c0  lea     rdx, [rbx-18h]
0x1800178c4  or      ecx, 0FFFFFFFFh
0x1800178c7  lock xadd [rdx+10h], ecx
0x1800178cc  sub     ecx, 1
0x1800178cf  jg      short loc_1800178E0
0x1800178d1  mov     rcx, [rdx]
0x1800178d4  mov     r8, [rcx]
0x1800178d7  mov     rax, [r8+8]
0x1800178db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178e0  mov     eax, edi
0x1800178e2  jmp     short loc_180017906
0x1800178e4  lea     rdx, [rbx-18h]
0x1800178e8  or      eax, 0FFFFFFFFh
0x1800178eb  lock xadd [rdx+10h], eax
0x1800178f0  sub     eax, 1
0x1800178f3  jg      short loc_180017904
0x1800178f5  mov     rcx, [rdx]
0x1800178f8  mov     rax, [rcx]
0x1800178fb  mov     rax, [rax+8]
0x1800178ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017904  xor     eax, eax
0x180017906  mov     rcx, [rbp+4Fh+var_48]
0x18001790a  xor     rcx, rsp; StackCookie
0x18001790d  call    __security_check_cookie
0x180017912  add     rsp, 98h
0x180017919  pop     r15
0x18001791b  pop     r14
0x18001791d  pop     r13
0x18001791f  pop     r12
0x180017921  pop     rdi
0x180017922  pop     rsi
0x180017923  pop     rbx
0x180017924  pop     rbp
0x180017925  retn
0x180017926  mov     ecx, 80004005h; int
0x18001792b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
