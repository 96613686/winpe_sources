# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessTreeForDeletion(void *,int,CLEANUP_THRESHOLD,CSortedArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault> const *,int *,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault> *,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault> *,double *)

- ea: `0x18002b224`
- end: `0x18002b4e6`
- name: `?ProcessTreeForDeletion@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXHW4CLEANUP_THRESHOLD@@PEBV?$CSortedArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@PEAHPEAV?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAV?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAN@Z`
- size: `706`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, _DWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18002bae0`

## callees

- `0x18000638c`
- `0x1800256cc`
- `0x180026000`
- `0x180027008`
- `0x180028368`
- `0x1800293a4`
- `0x18002b224`
- `0x18002b4ec`
- `0x18002b848`
- `0x18002c910`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b430`
- `WDSCORE!CurrentIP` at `0x18002b438`
- `WDSCORE!CurrentIP` at `0x18002b438`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b49e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b49e`

## string_xrefs

- `0x18002b487`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002b45d`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::ProcessTreeForDeletion`

## pseudocode

```c
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessTreeForDeletion(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v9; // rdx
  __int64 v10; // xmm6_8
  __int64 v11; // rbx
  unsigned int v13; // esi
  __int64 v14; // rcx
  int Paths; // eax
  unsigned int v16; // edx
  __int64 v17; // r14
  int v18; // edi
  _WORD *v19; // r8
  __int64 v20; // rdx
  _WORD *v21; // r9
  __int64 v22; // rax
  _WORD *v23; // rcx
  int v24; // eax
  _QWORD *v25; // rax
  DWORD LastError; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  __int64 v30; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+70h] [rbp-98h] BYREF
  __int64 v32; // [rsp+78h] [rbp-90h] BYREF
  __int64 v33; // [rsp+80h] [rbp-88h] BYREF
  __int64 v34; // [rsp+88h] [rbp-80h]
  __int64 v35; // [rsp+90h] [rbp-78h]
  _BYTE v36[528]; // [rsp+98h] [rbp-70h] BYREF

  v9 = *(unsigned int *)(a4 + 4);
  v10 = 0;
  v11 = 0;
  v34 = a6;
  v35 = a8;
  v32 = 0;
  v31 = 0;
  v33 = 0;
  CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::SetSize(
    a7,
    v9);
  if ( !CDirectoryProviderT<CWindowsOldAdaptor>::g_pDirectoryProvider )
  {
    v13 = -2147418113;
    goto LABEL_3;
  }
  v30 = 0;
  Paths = CWindowsOldAdaptor::GetPaths(a2, &v30);
  v13 = Paths;
  if ( Paths >= 0 )
  {
    v11 = v30;
    v33 = v30;
    v17 = v30;
    v30 = 0;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Paths);
    v17 = v16;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
  SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>::~SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>(&v30);
  if ( (v13 & 0x80000000) != 0 )
  {
LABEL_3:
    v14 = v13;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
    goto LABEL_27;
  }
  v18 = 0;
  if ( *(int *)(v17 + 4) > 0 )
  {
    while ( 1 )
    {
      v19 = v36;
      v20 = 261;
      v21 = *(_WORD **)(*(_QWORD *)(v11 + 8) + 8LL * v18);
      v22 = 2147483646;
      do
      {
        if ( !v22 )
          break;
        if ( !*v21 )
          break;
        *v19++ = *v21++;
        --v22;
        --v20;
      }
      while ( v20 );
      v23 = v19 - 1;
      v13 = v20 == 0 ? 0x8007007A : 0;
      if ( v20 )
        v23 = v19;
      *v23 = 0;
      if ( !v20 )
        goto LABEL_3;
      v24 = CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::RetrieveNtfsEntry(v34, a4, v36, &v31);
      if ( v24 != -2147024894 )
      {
        if ( v24 != -2147024893 && (v13 = v24, v24 < 0)
          || (v24 = CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessTreeForDeletionInternal(
                      v31,
                      (unsigned int)v36,
                      0,
                      0,
                      1,
                      a7,
                      (__int64)&v32),
              v13 = v24,
              v24 < 0) )
        {
          v14 = (unsigned int)v24;
          goto LABEL_4;
        }
      }
      if ( ++v18 >= *(_DWORD *)(v17 + 4) )
      {
        v10 = v32;
        break;
      }
    }
  }
  if ( *(_DWORD *)(a7 + 4) )
    std::_Sort<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry * *,__int64,bool (*)(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *)>(
      *(_QWORD *)(a7 + 8),
      *(_QWORD *)(a7 + 8) + 8LL * *(int *)(a7 + 4),
      (8LL * *(int *)(a7 + 4)) >> 3,
      CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::CSortHelper<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CAdaptorDefaultSpecializeFileSize>::LessOp);
  v25 = (_QWORD *)v35;
  *a5 = 0;
  *v25 = v10;
  if ( (v13 & 0x80000000) != 0 )
  {
LABEL_27:
    LastError = GetLastError();
    v27 = CurrentIP();
    v28 = ConstructPartialMsgW(0x2000000u, "ProcessTreeForDeletion failed. hr = 0x%x", v13);
    WdsSetupLogMessageW(
      v28,
      0,
      L"D",
      0,
      1094,
      L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
      L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::ProcessTreeForDeletion",
      v27,
      LastError,
      0,
      0);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
  SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>::~SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>(&v33);
  return v13;
}

```

## disassembly

```asm
0x18002b224  mov     rax, rsp
0x18002b227  mov     [rax+8], rbx
0x18002b22b  push    rbp
0x18002b22c  push    rsi
0x18002b22d  push    rdi
0x18002b22e  push    r12
0x18002b230  push    r13
0x18002b232  push    r14
0x18002b234  push    r15
0x18002b236  lea     rbp, [rax-1F8h]
0x18002b23d  sub     rsp, 2C0h
0x18002b244  movaps  xmmword ptr [rax-48h], xmm6
0x18002b248  mov     rax, cs:__security_cookie
0x18002b24f  xor     rax, rsp
0x18002b252  mov     [rbp+1F0h+var_50], rax
0x18002b259  mov     rax, [rbp+1F0h+arg_28]
0x18002b260  xor     esi, esi
0x18002b262  mov     r15, [rbp+1F0h+arg_30]
0x18002b269  mov     edi, edx
0x18002b26b  mov     edx, [r9+4]
0x18002b26f  xorps   xmm6, xmm6
0x18002b272  mov     r12, [rbp+1F0h+arg_20]
0x18002b279  mov     ebx, esi
0x18002b27b  mov     [rbp+1F0h+var_270], rax
0x18002b27f  mov     rcx, r15
0x18002b282  mov     rax, [rbp+1F0h+arg_38]
0x18002b289  mov     r13, r9
0x18002b28c  mov     [rbp+1F0h+var_268], rax
0x18002b290  movsd   [rsp+2F0h+var_280], xmm6
0x18002b296  mov     [rsp+2F0h+var_288], rsi
0x18002b29b  mov     [rsp+2F0h+var_278], rbx
0x18002b2a0  call    ?SetSize@?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18002b2a5  cmp     cs:?g_pDirectoryProvider@?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@0PEAV1@EA, rsi; CDirectoryProviderT<CWindowsOldAdaptor> * CDirectoryProviderT<CWindowsOldAdaptor>::g_pDirectoryProvider
0x18002b2ac  jnz     short loc_18002B2BF
0x18002b2ae  mov     esi, 8000FFFFh
0x18002b2b3  mov     ecx, esi
0x18002b2b5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b2ba  jmp     loc_18002B430
0x18002b2bf  lea     rdx, [rsp+2F0h+var_290]
0x18002b2c4  mov     [rsp+2F0h+var_290], rsi
0x18002b2c9  mov     ecx, edi
0x18002b2cb  call    ?GetPaths@CWindowsOldAdaptor@@SAJHPEAPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@@Z; CWindowsOldAdaptor::GetPaths(int,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> * *)
0x18002b2d0  xor     edx, edx
0x18002b2d2  mov     esi, eax
0x18002b2d4  test    eax, eax
0x18002b2d6  jns     short loc_18002B2E4
0x18002b2d8  mov     ecx, eax
0x18002b2da  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b2df  mov     r14d, edx
0x18002b2e2  jmp     short loc_18002B2F6
0x18002b2e4  mov     rbx, [rsp+2F0h+var_290]
0x18002b2e9  mov     [rsp+2F0h+var_278], rbx
0x18002b2ee  mov     r14, rbx
0x18002b2f1  mov     [rsp+2F0h+var_290], rdx
0x18002b2f6  mov     ecx, esi
0x18002b2f8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b2fd  lea     rcx, [rsp+2F0h+var_290]
0x18002b302  call    ??1?$SP@V?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@V?$SP_CPP@V?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@@@@@QEAA@XZ; SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>::~SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>(void)
0x18002b307  xor     r10d, r10d
0x18002b30a  test    esi, esi
0x18002b30c  js      short loc_18002B2B3
0x18002b30e  mov     edi, r10d
0x18002b311  cmp     [r14+4], r10d
0x18002b315  jle     loc_18002B3F5
0x18002b31b  mov     rcx, [rbx+8]
0x18002b31f  lea     r8, [rbp+1F0h+var_260]
0x18002b323  movsxd  rax, edi
0x18002b326  mov     edx, 105h
0x18002b32b  mov     r9, [rcx+rax*8]
0x18002b32f  mov     eax, 7FFFFFFEh
0x18002b334  test    rax, rax
0x18002b337  jz      short loc_18002B357
0x18002b339  movzx   ecx, word ptr [r9]
0x18002b33d  test    cx, cx
0x18002b340  jz      short loc_18002B357
0x18002b342  mov     [r8], cx
0x18002b346  add     r9, 2
0x18002b34a  add     r8, 2
0x18002b34e  dec     rax
0x18002b351  sub     rdx, 1
0x18002b355  jnz     short loc_18002B334
0x18002b357  mov     rax, rdx
0x18002b35a  lea     rcx, [r8-2]
0x18002b35e  neg     rax
0x18002b361  sbb     esi, esi
0x18002b363  not     esi
0x18002b365  and     esi, 8007007Ah
0x18002b36b  test    rdx, rdx
0x18002b36e  cmovnz  rcx, r8
0x18002b372  mov     [rcx], r10w
0x18002b376  jz      loc_18002B2B3
0x18002b37c  mov     rcx, [rbp+1F0h+var_270]
0x18002b380  lea     r9, [rsp+2F0h+var_288]
0x18002b385  lea     r8, [rbp+1F0h+var_260]
0x18002b389  mov     rdx, r13
0x18002b38c  call    ?RetrieveNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEBV?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@PEBV?$CSortedArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBGPEAPEBUCFastNtfsEntry@1@@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::RetrieveNtfsEntry(CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault> const *,CSortedArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault> const *,ushort const * const,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry const * *)
0x18002b391  cmp     eax, 80070002h
0x18002b396  jz      short loc_18002B3E0
0x18002b398  cmp     eax, 80070003h
0x18002b39d  jz      short loc_18002B3A5
0x18002b39f  mov     esi, eax
0x18002b3a1  test    eax, eax
0x18002b3a3  js      short loc_18002B3D9
0x18002b3a5  mov     rcx, [rsp+2F0h+var_288]
0x18002b3aa  lea     rax, [rsp+2F0h+var_280]
0x18002b3af  mov     [rsp+2F0h+var_2C0], rax
0x18002b3b4  lea     rdx, [rbp+1F0h+var_260]
0x18002b3b8  mov     [rsp+2F0h+var_2C8], r15
0x18002b3bd  xor     r9d, r9d
0x18002b3c0  xor     r8d, r8d
0x18002b3c3  mov     dword ptr [rsp+2F0h+var_2D0], 1
0x18002b3cb  call    ?ProcessTreeForDeletionInternal@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEBUCFastNtfsEntry@1@PEBGIHHPEAV?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAN@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessTreeForDeletionInternal(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry const *,ushort const *,uint,int,int,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault> *,double *)
0x18002b3d0  xor     r10d, r10d
0x18002b3d3  mov     esi, eax
0x18002b3d5  test    eax, eax
0x18002b3d7  jns     short loc_18002B3E3
0x18002b3d9  mov     ecx, eax
0x18002b3db  jmp     loc_18002B2B5
0x18002b3e0  xor     r10d, r10d
0x18002b3e3  inc     edi
0x18002b3e5  cmp     edi, [r14+4]
0x18002b3e9  jl      loc_18002B31B
0x18002b3ef  movsd   xmm6, [rsp+2F0h+var_280]
0x18002b3f5  cmp     [r15+4], r10d
0x18002b3f9  jz      short loc_18002B420
0x18002b3fb  mov     rcx, [r15+8]
0x18002b3ff  lea     r9, ?LessOp@?$CSortHelper@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@VCAdaptorDefaultSpecializeFileSize@2@@?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@SA_NPEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@0@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::CSortHelper<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CAdaptorDefaultSpecializeFileSize>::LessOp(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *)
0x18002b406  movsxd  rax, dword ptr [r15+4]
0x18002b40a  lea     rdx, [rcx+rax*8]
0x18002b40e  mov     r8, rdx
0x18002b411  sub     r8, rcx
0x18002b414  sar     r8, 3
0x18002b418  call    ??$_Sort@PEAPEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_JP6A_NPEAU12@0@Z@std@@YAXPEAPEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@0_JP6A_NPEAU12@2@Z@Z; std::_Sort<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry * *,__int64,bool (*)(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *)>(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry * *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry * *,__int64,bool (*)(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *))
0x18002b41d  xor     r10d, r10d
0x18002b420  mov     rax, [rbp+1F0h+var_268]
0x18002b424  mov     [r12], r10d
0x18002b428  movsd   qword ptr [rax], xmm6
0x18002b42c  test    esi, esi
0x18002b42e  jns     short loc_18002B4A4
0x18002b430  call    cs:__imp_GetLastError
0x18002b436  mov     edi, eax
0x18002b438  call    cs:__imp_CurrentIP
0x18002b43e  mov     r8d, esi
0x18002b441  lea     rdx, aProcesstreefor_0; "ProcessTreeForDeletion failed. hr = 0x%"...
0x18002b448  mov     ecx, 2000000h; unsigned int
0x18002b44d  mov     rbx, rax
0x18002b450  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002b455  mov     [rsp+2F0h+var_2A0], 0
0x18002b45d  lea     rcx, aCfastdeleteimp_1; "CFastDeleteImplT<class CDirectoryProvid"...
0x18002b464  mov     qword ptr [rsp+2F0h+var_2A8], 0
0x18002b46d  lea     r8, aD_0; "D"
0x18002b474  mov     dword ptr [rsp+2F0h+var_2B0], edi
0x18002b478  xor     r9d, r9d
0x18002b47b  mov     qword ptr [rsp+2F0h+var_2B8], rbx
0x18002b480  xor     edx, edx
0x18002b482  mov     [rsp+2F0h+var_2C0], rcx
0x18002b487  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x18002b48e  mov     [rsp+2F0h+var_2C8], rcx
0x18002b493  mov     rcx, rax
0x18002b496  mov     dword ptr [rsp+2F0h+var_2D0], 446h
0x18002b49e  call    cs:__imp_WdsSetupLogMessageW
0x18002b4a4  mov     ecx, esi
0x18002b4a6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b4ab  lea     rcx, [rsp+2F0h+var_278]
0x18002b4b0  call    ??1?$SP@V?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@V?$SP_CPP@V?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@@@@@QEAA@XZ; SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>::~SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>(void)
0x18002b4b5  mov     eax, esi
0x18002b4b7  mov     rcx, [rbp+1F0h+var_50]
0x18002b4be  xor     rcx, rsp; StackCookie
0x18002b4c1  call    __security_check_cookie
0x18002b4c6  lea     r11, [rsp+2F0h+var_30]
0x18002b4ce  mov     rbx, [r11+40h]
0x18002b4d2  movaps  xmm6, xmmword ptr [r11-10h]
0x18002b4d7  mov     rsp, r11
0x18002b4da  pop     r15
0x18002b4dc  pop     r14
0x18002b4de  pop     r13
0x18002b4e0  pop     r12
0x18002b4e2  pop     rdi
0x18002b4e3  pop     rsi
0x18002b4e4  pop     rbp
0x18002b4e5  retn
```
