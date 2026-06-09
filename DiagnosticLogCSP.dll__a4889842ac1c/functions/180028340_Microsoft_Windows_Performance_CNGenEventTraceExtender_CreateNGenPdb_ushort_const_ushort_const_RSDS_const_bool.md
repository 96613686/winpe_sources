# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)

- ea: `0x180028340`
- end: `0x180028737`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z`
- size: `1015`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, char *, const unsigned __int16 *, const struct _RSDS *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028018`

## callees

- `0x180001b60`
- `0x180010db8`
- `0x180015674`
- `0x18001639c`
- `0x180016440`
- `0x1800272dc`
- `0x180027c84`
- `0x180028340`
- `0x180028740`
- `0x180028804`
- `0x180029710`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002837f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180028390`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002837f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180028390`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028431`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028431`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286a9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002841e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002869a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002841e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002869a`

## string_xrefs

- `0x180028508`: `%wsngen.exe createpdb %ws %ws`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        char *a2,
        const unsigned __int16 *a3,
        const struct _RSDS *a4,
        bool a5)
{
  const char *v9; // rdi
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
  unsigned __int16 *v30; // rax
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
  unsigned __int16 *v43; // [rsp+40h] [rbp-51h] BYREF
  unsigned int v44; // [rsp+48h] [rbp-49h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-41h] BYREF
  int v46; // [rsp+58h] [rbp-39h] BYREF
  _BYTE v47[16]; // [rsp+60h] [rbp-31h] BYREF
  _DWORD *v48; // [rsp+70h] [rbp-21h]
  __int64 v49; // [rsp+78h] [rbp-19h]
  unsigned __int16 **v50; // [rsp+80h] [rbp-11h]
  __int64 v51; // [rsp+88h] [rbp-9h]

  v9 = (char *)a4 + 24;
  v10 = strrchr((const char *)a4 + 24, 47);
  v11 = strrchr(v9, 92);
  if ( v10 > v11 )
    v11 = v10;
  v12 = v11 + 1;
  if ( !v11 )
    v12 = v9;
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
      v48 = v18;
      v49 = (unsigned int)v19;
      McGenEventWrite_EventWriteTransfer(v19, TraceMerge_NGEN_CandidateEncountered_ExistingPDB, v16, 2, v47);
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
  v43 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v43,
    L"%wsngen.exe createpdb %ws %ws",
    *((_QWORD *)this + a5 + 5),
    a3,
    a2);
  v28 = v43;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
  {
    if ( v43 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v43[v29] );
      v30 = v43;
      v31 = (unsigned int)(2 * v29 + 2);
    }
    else
    {
      v30 = L"NULL";
      v31 = 10;
    }
    v48 = v30;
    v49 = (unsigned int)v31;
    McGenEventWrite_EventWriteTransfer(v31, TraceMerge_NGEN_CreatingPDB_Start, v27, 2, v47);
  }
  v44 = 0;
  if ( *((int *)v28 - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(&v43, *((unsigned int *)v28 - 4));
    v28 = v43;
  }
  v32 = Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(v26, v28, &v44);
  v34 = v32;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
  {
    LODWORD(v43) = v44;
    v46 = v32;
    v48 = &v46;
    v49 = 4;
    v50 = &v43;
    v51 = 4;
    McGenEventWrite_EventWriteTransfer(v44, TraceMerge_NGEN_CreatingPDB_Stop, v33, 3, v47);
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
0x180028340  push    rbp
0x180028342  push    rbx
0x180028343  push    rsi
0x180028344  push    rdi
0x180028345  push    r12
0x180028347  push    r13
0x180028349  push    r14
0x18002834b  push    r15
0x18002834d  lea     rbp, [rsp-17h]
0x180028352  sub     rsp, 0A8h
0x180028359  mov     rax, cs:__security_cookie
0x180028360  xor     rax, rsp
0x180028363  mov     [rbp+4Fh+var_50], rax
0x180028367  mov     r13, r9
0x18002836a  mov     r14, r8
0x18002836d  mov     rsi, rdx
0x180028370  mov     r15, rcx
0x180028373  lea     rdi, [r9+18h]
0x180028377  mov     edx, 2Fh ; '/'; Ch
0x18002837c  mov     rcx, rdi; Str
0x18002837f  call    cs:__imp_strrchr
0x180028385  mov     rbx, rax
0x180028388  mov     edx, 5Ch ; '\'; Ch
0x18002838d  mov     rcx, rdi; Str
0x180028390  call    cs:__imp_strrchr
0x180028396  cmp     rbx, rax
0x180028399  cmova   rax, rbx
0x18002839d  lea     r12, [rax+1]
0x1800283a1  test    rax, rax
0x1800283a4  cmovz   r12, rdi
0x1800283a8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800283af  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800283b6  mov     rax, [rax+18h]
0x1800283ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283bf  add     rax, 18h
0x1800283c3  mov     [rbp+4Fh+lpFileName], rax
0x1800283c7  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13
0x1800283cc  mov     r9, r12
0x1800283cf  mov     r8, rsi
0x1800283d2  lea     rdx, [rbp+4Fh+lpFileName]
0x1800283d6  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x1800283db  mov     r8d, 1
0x1800283e1  lea     rdx, StringValue; "\\"
0x1800283e8  lea     rcx, [rbp+4Fh+lpFileName]
0x1800283ec  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800283f1  mov     rdx, r12
0x1800283f4  lea     rcx, [rbp+4Fh+lpFileName]
0x1800283f8  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x1800283fd  xor     edi, edi
0x1800283ff  mov     [rsp+0E0h+hTemplateFile], rdi; hTemplateFile
0x180028404  mov     [rsp+0E0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180028408  lea     eax, [rdi+3]
0x18002840b  mov     [rsp+0E0h+dwCreationDisposition], eax; dwCreationDisposition
0x18002840f  xor     r9d, r9d; lpSecurityAttributes
0x180028412  mov     r8d, eax; dwShareMode
0x180028415  xor     edx, edx; dwDesiredAccess
0x180028417  mov     rbx, [rbp+4Fh+lpFileName]
0x18002841b  mov     rcx, rbx; lpFileName
0x18002841e  call    cs:__imp_CreateFileW
0x180028424  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028428  jz      loc_1800284D7
0x18002842e  mov     rcx, rax; hObject
0x180028431  call    cs:__imp_CloseHandle
0x180028437  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18002843e  jz      short loc_18002848F
0x180028440  test    rbx, rbx
0x180028443  jz      short loc_18002845E
0x180028445  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180028449  inc     rcx
0x18002844c  cmp     [rbx+rcx*2], di
0x180028450  jnz     short loc_180028449
0x180028452  mov     rax, rbx
0x180028455  lea     ecx, ds:2[rcx*2]
0x18002845c  jmp     short loc_18002846A
0x18002845e  lea     rax, aNull; "NULL"
0x180028465  mov     ecx, 0Ah
0x18002846a  mov     [rbp+4Fh+var_70], rax
0x18002846e  mov     dword ptr [rbp+4Fh+var_68], ecx
0x180028471  mov     dword ptr [rbp+4Fh+var_68+4], edi
0x180028474  lea     rax, [rbp+4Fh+var_80]
0x180028478  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x18002847d  mov     r9d, 2
0x180028483  lea     rdx, TraceMerge_NGEN_CandidateEncountered_ExistingPDB
0x18002848a  call    McGenEventWrite_EventWriteTransfer
0x18002848f  test    rsi, rsi
0x180028492  jz      loc_18002872C
0x180028498  mov     rax, [r15+38h]
0x18002849c  sub     rsi, rax
0x18002849f  movzx   edx, word ptr [rax]
0x1800284a2  movzx   r9d, word ptr [rax+rsi]
0x1800284a7  sub     edx, r9d
0x1800284aa  jnz     short loc_1800284B5
0x1800284ac  add     rax, 2
0x1800284b0  test    r9d, r9d
0x1800284b3  jnz     short loc_18002849F
0x1800284b5  test    edx, edx
0x1800284b7  jz      loc_1800286EA
0x1800284bd  mov     r9, r13; struct _RSDS *
0x1800284c0  mov     r8, r12; char *
0x1800284c3  mov     rdx, rbx; unsigned __int16 *
0x1800284c6  mov     rcx, r15; this
0x1800284c9  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x1800284ce  mov     edi, eax
0x1800284d0  test    eax, eax
0x1800284d2  jmp     loc_1800286C4
0x1800284d7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800284de  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800284e5  mov     rax, [rax+18h]
0x1800284e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284ee  add     rax, 18h
0x1800284f2  mov     [rbp+4Fh+var_A0], rax
0x1800284f6  movzx   r8d, [rbp+4Fh+arg_20]
0x1800284fb  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rsi
0x180028500  mov     r9, r14
0x180028503  mov     r8, [r15+r8*8+28h]
0x180028508  lea     rdx, aWsngenExeCreat; "%wsngen.exe createpdb %ws %ws"
0x18002850f  lea     rcx, [rbp+4Fh+var_A0]
0x180028513  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180028518  mov     rdi, [rbp+4Fh+var_A0]
0x18002851c  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x180028523  jz      short loc_180028576
0x180028525  xor     edx, edx
0x180028527  test    rdi, rdi
0x18002852a  jz      short loc_180028545
0x18002852c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180028530  inc     rcx
0x180028533  cmp     [rdi+rcx*2], dx
0x180028537  jnz     short loc_180028530
0x180028539  mov     rax, rdi
0x18002853c  lea     ecx, ds:2[rcx*2]
0x180028543  jmp     short loc_180028551
0x180028545  lea     rax, aNull; "NULL"
0x18002854c  mov     ecx, 0Ah
0x180028551  mov     [rbp+4Fh+var_70], rax
0x180028555  mov     dword ptr [rbp+4Fh+var_68], ecx
0x180028558  mov     dword ptr [rbp+4Fh+var_68+4], edx
0x18002855b  lea     rax, [rbp+4Fh+var_80]
0x18002855f  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x180028564  mov     r9d, 2
0x18002856a  lea     rdx, TraceMerge_NGEN_CreatingPDB_Start
0x180028571  call    McGenEventWrite_EventWriteTransfer
0x180028576  mov     [rbp+4Fh+var_98], 0
0x18002857d  cmp     dword ptr [rdi-8], 1
0x180028581  jle     short loc_180028593
0x180028583  mov     edx, [rdi-10h]
0x180028586  lea     rcx, [rbp+4Fh+var_A0]
0x18002858a  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18002858f  mov     rdi, [rbp+4Fh+var_A0]
0x180028593  lea     r8, [rbp+4Fh+var_98]; unsigned int *
0x180028597  mov     rdx, rdi; unsigned __int16 *
0x18002859a  call    ?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)
0x18002859f  mov     r14d, eax
0x1800285a2  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x1800285a9  jz      short loc_1800285F0
0x1800285ab  mov     ecx, [rbp+4Fh+var_98]
0x1800285ae  mov     dword ptr [rbp+4Fh+var_A0], ecx
0x1800285b1  mov     [rbp+4Fh+var_88], eax
0x1800285b4  lea     rax, [rbp+4Fh+var_88]
0x1800285b8  mov     [rbp+4Fh+var_70], rax
0x1800285bc  mov     [rbp+4Fh+var_68], 4
0x1800285c4  lea     rax, [rbp+4Fh+var_A0]
0x1800285c8  mov     [rbp+4Fh+var_60], rax
0x1800285cc  mov     [rbp+4Fh+var_58], 4
0x1800285d4  lea     rax, [rbp+4Fh+var_80]
0x1800285d8  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x1800285dd  mov     r9d, 3
0x1800285e3  lea     rdx, TraceMerge_NGEN_CreatingPDB_Stop
0x1800285ea  call    McGenEventWrite_EventWriteTransfer
0x1800285ef  nop
0x1800285f0  lea     rdx, [rdi-18h]
0x1800285f4  or      eax, 0FFFFFFFFh
0x1800285f7  lock xadd [rdx+10h], eax
0x1800285fc  test    r14d, r14d
0x1800285ff  jns     short loc_18002863E
0x180028601  sub     eax, 1
0x180028604  jg      short loc_180028616
0x180028606  mov     rcx, [rdx]
0x180028609  mov     rax, [rcx]
0x18002860c  mov     rax, [rax+8]
0x180028610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028615  nop
0x180028616  lea     rdx, [rbx-18h]
0x18002861a  or      eax, 0FFFFFFFFh
0x18002861d  lock xadd [rdx+10h], eax
0x180028622  sub     eax, 1
0x180028625  jg      short loc_180028636
0x180028627  mov     rcx, [rdx]
0x18002862a  mov     rax, [rcx]
0x18002862d  mov     rax, [rax+8]
0x180028631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028636  mov     eax, r14d
0x180028639  jmp     loc_18002870C
0x18002863e  xor     r14d, r14d
0x180028641  sub     eax, 1
0x180028644  jg      short loc_180028655
0x180028646  mov     rcx, [rdx]
0x180028649  mov     rax, [rcx]
0x18002864c  mov     rax, [rax+8]
0x180028650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028655  test    rsi, rsi
0x180028658  jz      loc_18002872C
0x18002865e  mov     rax, [r15+38h]
0x180028662  sub     rsi, rax
0x180028665  movzx   ecx, word ptr [rax]
0x180028668  movzx   edx, word ptr [rax+rsi]
0x18002866c  sub     ecx, edx
0x18002866e  jnz     short loc_180028678
0x180028670  add     rax, 2
0x180028674  test    edx, edx
0x180028676  jnz     short loc_180028665
0x180028678  test    ecx, ecx
0x18002867a  jz      short loc_1800286EA
0x18002867c  mov     [rsp+0E0h+hTemplateFile], r14; hTemplateFile
0x180028681  mov     [rsp+0E0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180028686  mov     eax, 3
0x18002868b  mov     [rsp+0E0h+dwCreationDisposition], eax; dwCreationDisposition
0x18002868f  xor     r9d, r9d; lpSecurityAttributes
0x180028692  mov     r8d, eax; dwShareMode
0x180028695  xor     edx, edx; dwDesiredAccess
0x180028697  mov     rcx, rbx; lpFileName
0x18002869a  call    cs:__imp_CreateFileW
0x1800286a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800286a4  jz      short loc_1800286EA
0x1800286a6  mov     rcx, rax; hObject
0x1800286a9  call    cs:__imp_CloseHandle
0x1800286af  mov     r9, r13; struct _RSDS *
0x1800286b2  mov     r8, r12; char *
0x1800286b5  mov     rdx, rbx; unsigned __int16 *
0x1800286b8  mov     rcx, r15; this
0x1800286bb  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x1800286c0  mov     edi, eax
0x1800286c2  test    eax, eax
0x1800286c4  jns     short loc_1800286EA
0x1800286c6  lea     rdx, [rbx-18h]
0x1800286ca  or      ecx, 0FFFFFFFFh
0x1800286cd  lock xadd [rdx+10h], ecx
0x1800286d2  sub     ecx, 1
0x1800286d5  jg      short loc_1800286E6
0x1800286d7  mov     rcx, [rdx]
0x1800286da  mov     r8, [rcx]
0x1800286dd  mov     rax, [r8+8]
0x1800286e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286e6  mov     eax, edi
0x1800286e8  jmp     short loc_18002870C
0x1800286ea  lea     rdx, [rbx-18h]
0x1800286ee  or      eax, 0FFFFFFFFh
0x1800286f1  lock xadd [rdx+10h], eax
0x1800286f6  sub     eax, 1
0x1800286f9  jg      short loc_18002870A
0x1800286fb  mov     rcx, [rdx]
0x1800286fe  mov     rax, [rcx]
0x180028701  mov     rax, [rax+8]
0x180028705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002870a  xor     eax, eax
0x18002870c  mov     rcx, [rbp+4Fh+var_50]
0x180028710  xor     rcx, rsp; StackCookie
0x180028713  call    __security_check_cookie
0x180028718  add     rsp, 0A8h
0x18002871f  pop     r15
0x180028721  pop     r14
0x180028723  pop     r13
0x180028725  pop     r12
0x180028727  pop     rdi
0x180028728  pop     rsi
0x180028729  pop     rbx
0x18002872a  pop     rbp
0x18002872b  retn
0x18002872c  mov     ecx, 80004005h; int
0x180028731  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
