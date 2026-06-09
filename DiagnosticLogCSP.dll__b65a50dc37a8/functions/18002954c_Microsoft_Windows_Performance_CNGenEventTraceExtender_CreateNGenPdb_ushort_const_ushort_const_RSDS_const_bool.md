# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)

- ea: `0x18002954c`
- end: `0x1800298a8`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z`
- size: `860`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const struct _RSDS *@<r9>, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180029218`

## callees

- `0x180001b90`
- `0x180011648`
- `0x1800161d4`
- `0x180016f5c`
- `0x180017000`
- `0x18002847c`
- `0x180028e68`
- `0x18002954c`
- `0x1800298b0`
- `0x180029974`
- `0x180029a94`
- `0x18002a904`
- `0x18002a964`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002958b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800295a2`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002958b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800295a2`

## string_xrefs

- `0x1800296e2`: `%wsngen.exe createpdb %ws %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  unsigned __int16 *v14; // rbx
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v15; // rcx
  __int64 v16; // rcx
  char *v17; // rax
  char *v18; // rsi
  int v19; // edx
  int v20; // ecx
  int v21; // esi
  void (*v22)(void); // rax
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v24; // rcx
  unsigned __int16 *v25; // rdi
  int v26; // eax
  __int64 v27; // r8
  int v28; // r15d
  unsigned __int16 *v29; // rdx
  int v30; // eax
  char *v31; // rax
  char *v32; // rsi
  int v33; // edx
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v34; // rcx
  unsigned __int16 *v35; // [rsp+30h] [rbp-51h] BYREF
  unsigned int v36; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int16 *v37; // [rsp+40h] [rbp-41h] BYREF
  int v38; // [rsp+48h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+50h] [rbp-31h] BYREF
  int *v40; // [rsp+60h] [rbp-21h]
  __int64 v41; // [rsp+68h] [rbp-19h]
  unsigned __int16 **v42; // [rsp+70h] [rbp-11h]
  __int64 v43; // [rsp+78h] [rbp-9h]

  v9 = (char *)a4 + 24;
  v10 = strrchr((const char *)a4 + 24, 47);
  v11 = strrchr(v9, 92);
  if ( v10 > v11 )
    v11 = v10;
  v12 = v11 + 1;
  if ( !v11 )
    v12 = v9;
  v37 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
    v13,
    (unsigned int)&v37,
    (_DWORD)a2,
    (_DWORD)v12,
    (__int64)a4);
  ATL::CSimpleStringT<unsigned short,0>::Append(&v37, L"\\", 1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(&v37, v12);
  v14 = v37;
  if ( Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(v15, v37) )
  {
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v16, TraceMerge_NGEN_CandidateEncountered_ExistingPDB, v14);
    if ( a2 )
    {
      v17 = (char *)*((_QWORD *)this + 7);
      v18 = (char *)(a2 - v17);
      do
      {
        v19 = *(unsigned __int16 *)&v18[(_QWORD)v17];
        v20 = *(unsigned __int16 *)v17 - v19;
        if ( v20 )
          break;
        v17 += 2;
      }
      while ( v19 );
      if ( v20 )
      {
        v21 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v12, a4);
        if ( v21 < 0 )
        {
          if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) > 0 )
            return (unsigned int)v21;
          v22 = *(void (**)(void))(**((_QWORD **)v14 - 3) + 8LL);
LABEL_16:
          v22();
          return (unsigned int)v21;
        }
      }
LABEL_42:
      if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
      return 0;
    }
    goto LABEL_45;
  }
  v35 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v35,
    L"%wsngen.exe createpdb %ws %ws",
    *((_QWORD *)this + a5 + 5),
    a3,
    a2);
  v25 = v35;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v24, TraceMerge_NGEN_CreatingPDB_Start, v35);
  v36 = 0;
  if ( *((int *)v25 - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(&v35, *((unsigned int *)v25 - 4));
    v25 = v35;
  }
  v26 = Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(v24, v25, &v36);
  v28 = v26;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
  {
    LODWORD(v35) = v36;
    v38 = v26;
    v40 = &v38;
    v41 = 4;
    v42 = &v35;
    v43 = 4;
    McGenEventWrite_EventWriteTransfer(v36, (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_CreatingPDB_Stop, v27, 3u, &v39);
  }
  v29 = v25 - 12;
  v30 = _InterlockedDecrement((volatile signed __int32 *)v25 - 2);
  if ( v28 >= 0 )
  {
    if ( v30 <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29);
    if ( a2 )
    {
      v31 = (char *)*((_QWORD *)this + 7);
      v32 = (char *)(a2 - v31);
      do
      {
        v33 = *(unsigned __int16 *)&v32[(_QWORD)v31];
        v34 = (Microsoft::Windows::Performance::CNGenEventTraceExtender *)((unsigned int)*(unsigned __int16 *)v31 - v33);
        if ( (_DWORD)v34 )
          break;
        v31 += 2;
      }
      while ( v33 );
      if ( (_DWORD)v34 )
      {
        if ( Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(v34, v14) )
        {
          v21 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v12, a4);
          if ( v21 < 0 )
          {
            if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) > 0 )
              return (unsigned int)v21;
            v22 = *(void (**)(void))(**((_QWORD **)v14 - 3) + 8LL);
            goto LABEL_16;
          }
        }
      }
      goto LABEL_42;
    }
LABEL_45:
    ATL::AtlThrowImpl(-2147467259);
  }
  if ( v30 <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29);
  if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x18002954c  push    rbp
0x18002954e  push    rbx
0x18002954f  push    rsi
0x180029550  push    rdi
0x180029551  push    r12
0x180029553  push    r13
0x180029555  push    r14
0x180029557  push    r15
0x180029559  lea     rbp, [rsp-17h]
0x18002955e  sub     rsp, 98h
0x180029565  mov     rax, cs:__security_cookie
0x18002956c  xor     rax, rsp
0x18002956f  mov     [rbp+4Fh+var_50], rax
0x180029573  mov     r13, r9
0x180029576  mov     r15, r8
0x180029579  mov     rsi, rdx
0x18002957c  mov     r14, rcx
0x18002957f  lea     rdi, [r9+18h]
0x180029583  mov     edx, 2Fh ; '/'; Ch
0x180029588  mov     rcx, rdi; Str
0x18002958b  call    cs:__imp_strrchr
0x180029592  nop     dword ptr [rax+rax+00h]
0x180029597  mov     rbx, rax
0x18002959a  mov     edx, 5Ch ; '\'; Ch
0x18002959f  mov     rcx, rdi; Str
0x1800295a2  call    cs:__imp_strrchr
0x1800295a9  nop     dword ptr [rax+rax+00h]
0x1800295ae  cmp     rbx, rax
0x1800295b1  cmova   rax, rbx
0x1800295b5  lea     r12, [rax+1]
0x1800295b9  test    rax, rax
0x1800295bc  cmovz   r12, rdi
0x1800295c0  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800295c7  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800295ce  mov     rax, [rax+18h]
0x1800295d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295d7  add     rax, 18h
0x1800295db  mov     [rbp+4Fh+var_90], rax
0x1800295df  mov     [rsp+0D0h+var_B0], r13
0x1800295e4  mov     r9, r12
0x1800295e7  mov     r8, rsi
0x1800295ea  lea     rdx, [rbp+4Fh+var_90]
0x1800295ee  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x1800295f3  mov     r8d, 1
0x1800295f9  lea     rdx, StringValue; "\\"
0x180029600  lea     rcx, [rbp+4Fh+var_90]
0x180029604  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180029609  mov     rdx, r12
0x18002960c  lea     rcx, [rbp+4Fh+var_90]
0x180029610  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x180029615  mov     rbx, [rbp+4Fh+var_90]
0x180029619  mov     rdx, rbx; unsigned __int16 *
0x18002961c  call    ?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)
0x180029621  test    al, al
0x180029623  jz      loc_1800296B1
0x180029629  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x180029630  jz      short loc_180029641
0x180029632  mov     r8, rbx
0x180029635  lea     rdx, TraceMerge_NGEN_CandidateEncountered_ExistingPDB
0x18002963c  call    McTemplateU0z_EventWriteTransfer
0x180029641  test    rsi, rsi
0x180029644  jz      loc_18002989D
0x18002964a  mov     rax, [r14+38h]
0x18002964e  sub     rsi, rax
0x180029651  movzx   ecx, word ptr [rax]
0x180029654  movzx   edx, word ptr [rax+rsi]
0x180029658  sub     ecx, edx
0x18002965a  jnz     short loc_180029664
0x18002965c  add     rax, 2
0x180029660  test    edx, edx
0x180029662  jnz     short loc_180029651
0x180029664  test    ecx, ecx
0x180029666  jz      short loc_1800296A9
0x180029668  mov     r9, r13; struct _RSDS *
0x18002966b  mov     r8, r12; char *
0x18002966e  mov     rdx, rbx; unsigned __int16 *
0x180029671  mov     rcx, r14; this
0x180029674  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x180029679  mov     esi, eax
0x18002967b  test    eax, eax
0x18002967d  jns     short loc_1800296A9
0x18002967f  lea     rdx, [rbx-18h]
0x180029683  or      edi, 0FFFFFFFFh
0x180029686  mov     ecx, edi
0x180029688  lock xadd [rdx+10h], ecx
0x18002968d  add     ecx, edi
0x18002968f  test    ecx, ecx
0x180029691  jg      short loc_1800296A2
0x180029693  mov     rcx, [rdx]
0x180029696  mov     rax, [rcx]
0x180029699  mov     rax, [rax+8]
0x18002969d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296a2  mov     eax, esi
0x1800296a4  jmp     loc_18002987C
0x1800296a9  or      edi, 0FFFFFFFFh
0x1800296ac  jmp     loc_18002985A
0x1800296b1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800296b8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800296bf  mov     rax, [rax+18h]
0x1800296c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296c8  add     rax, 18h
0x1800296cc  mov     [rbp+4Fh+var_A0], rax
0x1800296d0  movzx   r8d, [rbp+4Fh+arg_20]
0x1800296d5  mov     [rsp+0D0h+var_B0], rsi
0x1800296da  mov     r9, r15
0x1800296dd  mov     r8, [r14+r8*8+28h]
0x1800296e2  lea     rdx, aWsngenExeCreat; "%wsngen.exe createpdb %ws %ws"
0x1800296e9  lea     rcx, [rbp+4Fh+var_A0]
0x1800296ed  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800296f2  mov     rdi, [rbp+4Fh+var_A0]
0x1800296f6  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x1800296fd  jz      short loc_18002970E
0x1800296ff  mov     r8, rdi
0x180029702  lea     rdx, TraceMerge_NGEN_CreatingPDB_Start
0x180029709  call    McTemplateU0z_EventWriteTransfer
0x18002970e  mov     [rbp+4Fh+var_98], 0
0x180029715  cmp     dword ptr [rdi-8], 1
0x180029719  jle     short loc_18002972B
0x18002971b  mov     edx, [rdi-10h]
0x18002971e  lea     rcx, [rbp+4Fh+var_A0]
0x180029722  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180029727  mov     rdi, [rbp+4Fh+var_A0]
0x18002972b  lea     r8, [rbp+4Fh+var_98]; unsigned int *
0x18002972f  mov     rdx, rdi; unsigned __int16 *
0x180029732  call    ?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)
0x180029737  mov     r15d, eax
0x18002973a  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x180029741  jz      short loc_180029788
0x180029743  mov     ecx, [rbp+4Fh+var_98]
0x180029746  mov     dword ptr [rbp+4Fh+var_A0], ecx
0x180029749  mov     [rbp+4Fh+var_88], eax
0x18002974c  lea     rax, [rbp+4Fh+var_88]
0x180029750  mov     [rbp+4Fh+var_70], rax
0x180029754  mov     [rbp+4Fh+var_68], 4
0x18002975c  lea     rax, [rbp+4Fh+var_A0]
0x180029760  mov     [rbp+4Fh+var_60], rax
0x180029764  mov     [rbp+4Fh+var_58], 4
0x18002976c  lea     rax, [rbp+4Fh+var_80]
0x180029770  mov     [rsp+0D0h+var_B0], rax
0x180029775  mov     r9d, 3
0x18002977b  lea     rdx, TraceMerge_NGEN_CreatingPDB_Stop
0x180029782  call    McGenEventWrite_EventWriteTransfer
0x180029787  nop
0x180029788  lea     rdx, [rdi-18h]
0x18002978c  or      edi, 0FFFFFFFFh
0x18002978f  mov     eax, edi
0x180029791  lock xadd [rdx+10h], eax
0x180029796  add     eax, edi
0x180029798  test    r15d, r15d
0x18002979b  jns     short loc_1800297D9
0x18002979d  test    eax, eax
0x18002979f  jg      short loc_1800297B1
0x1800297a1  mov     rcx, [rdx]
0x1800297a4  mov     rax, [rcx]
0x1800297a7  mov     rax, [rax+8]
0x1800297ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297b0  nop
0x1800297b1  lea     rdx, [rbx-18h]
0x1800297b5  mov     eax, edi
0x1800297b7  lock xadd [rdx+10h], eax
0x1800297bc  add     eax, edi
0x1800297be  test    eax, eax
0x1800297c0  jg      short loc_1800297D1
0x1800297c2  mov     rcx, [rdx]
0x1800297c5  mov     rax, [rcx]
0x1800297c8  mov     rax, [rax+8]
0x1800297cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297d1  mov     eax, r15d
0x1800297d4  jmp     loc_18002987C
0x1800297d9  test    eax, eax
0x1800297db  jg      short loc_1800297EC
0x1800297dd  mov     rcx, [rdx]
0x1800297e0  mov     rax, [rcx]
0x1800297e3  mov     rax, [rax+8]
0x1800297e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297ec  test    rsi, rsi
0x1800297ef  jz      loc_18002989D
0x1800297f5  mov     rax, [r14+38h]
0x1800297f9  sub     rsi, rax
0x1800297fc  movzx   ecx, word ptr [rax]
0x1800297ff  movzx   edx, word ptr [rax+rsi]
0x180029803  sub     ecx, edx; this
0x180029805  jnz     short loc_18002980F
0x180029807  add     rax, 2
0x18002980b  test    edx, edx
0x18002980d  jnz     short loc_1800297FC
0x18002980f  test    ecx, ecx
0x180029811  jz      short loc_18002985A
0x180029813  mov     rdx, rbx; unsigned __int16 *
0x180029816  call    ?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)
0x18002981b  test    al, al
0x18002981d  jz      short loc_18002985A
0x18002981f  mov     r9, r13; struct _RSDS *
0x180029822  mov     r8, r12; char *
0x180029825  mov     rdx, rbx; unsigned __int16 *
0x180029828  mov     rcx, r14; this
0x18002982b  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x180029830  mov     esi, eax
0x180029832  test    eax, eax
0x180029834  jns     short loc_18002985A
0x180029836  lea     rdx, [rbx-18h]
0x18002983a  mov     ecx, edi
0x18002983c  lock xadd [rdx+10h], ecx
0x180029841  add     ecx, edi
0x180029843  test    ecx, ecx
0x180029845  jg      loc_1800296A2
0x18002984b  mov     rcx, [rdx]
0x18002984e  mov     r8, [rcx]
0x180029851  mov     rax, [r8+8]
0x180029855  jmp     loc_18002969D
0x18002985a  lea     rdx, [rbx-18h]
0x18002985e  mov     eax, edi
0x180029860  lock xadd [rdx+10h], eax
0x180029865  add     eax, edi
0x180029867  test    eax, eax
0x180029869  jg      short loc_18002987A
0x18002986b  mov     rcx, [rdx]
0x18002986e  mov     rax, [rcx]
0x180029871  mov     rax, [rax+8]
0x180029875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002987a  xor     eax, eax
0x18002987c  mov     rcx, [rbp+4Fh+var_50]
0x180029880  xor     rcx, rsp; StackCookie
0x180029883  call    __security_check_cookie
0x180029888  add     rsp, 98h
0x18002988f  pop     r15
0x180029891  pop     r14
0x180029893  pop     r13
0x180029895  pop     r12
0x180029897  pop     rdi
0x180029898  pop     rsi
0x180029899  pop     rbx
0x18002989a  pop     rbp
0x18002989b  retn
0x18002989d  mov     ecx, 80004005h; int
0x1800298a2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
