# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::Run(int,CLEANUP_THRESHOLD,void *,int,TraceLoggingCorrelationVector *,ulong *,ulong *,unsigned __int64 *,ulong *)

- ea: `0x18002bae0`
- end: `0x18002c651`
- name: `?Run@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@SAJHW4CLEANUP_THRESHOLD@@PEAXHPEAVTraceLoggingCorrelationVector@@PEAK3PEA_K3@Z`
- size: `2929`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, TraceLoggingCorrelationVector *, _DWORD *, _DWORD *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180029aa4`

## callees

- `0x180001784`
- `0x18000638c`
- `0x180025f00`
- `0x180025f90`
- `0x180026824`
- `0x180027008`
- `0x18002724c`
- `0x180027d04`
- `0x18002872c`
- `0x1800293a4`
- `0x180029550`
- `0x18002acf8`
- `0x18002b224`
- `0x18002bae0`
- `0x18002cdac`
- `0x18002cebc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002c5c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002c62c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002c5c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002c62c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bcd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bdc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bedb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bfd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c0c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c48e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c54c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bcd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bdc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bedb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bfd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c0c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c48e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c54c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002bb7b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002bb7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bca2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bca2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bcb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bcb1`
- `WDSCORE!CurrentIP` at `0x18002bc31`
- `WDSCORE!CurrentIP` at `0x18002bcde`
- `WDSCORE!CurrentIP` at `0x18002bd6a`
- `WDSCORE!CurrentIP` at `0x18002bdc9`
- `WDSCORE!CurrentIP` at `0x18002be6a`
- `WDSCORE!CurrentIP` at `0x18002bee3`
- `WDSCORE!CurrentIP` at `0x18002bf5e`
- `WDSCORE!CurrentIP` at `0x18002bfd8`
- `WDSCORE!CurrentIP` at `0x18002c053`
- `WDSCORE!CurrentIP` at `0x18002c0cc`
- `WDSCORE!CurrentIP` at `0x18002c1ea`
- `WDSCORE!CurrentIP` at `0x18002c2de`
- `WDSCORE!CurrentIP` at `0x18002c341`
- `WDSCORE!CurrentIP` at `0x18002c3f6`
- `WDSCORE!CurrentIP` at `0x18002c496`
- `WDSCORE!CurrentIP` at `0x18002c554`
- `WDSCORE!CurrentIP` at `0x18002bc31`
- `WDSCORE!CurrentIP` at `0x18002bcde`
- `WDSCORE!CurrentIP` at `0x18002bd6a`
- `WDSCORE!CurrentIP` at `0x18002bdc9`
- `WDSCORE!CurrentIP` at `0x18002be6a`
- `WDSCORE!CurrentIP` at `0x18002bee3`
- `WDSCORE!CurrentIP` at `0x18002bf5e`
- `WDSCORE!CurrentIP` at `0x18002bfd8`
- `WDSCORE!CurrentIP` at `0x18002c053`
- `WDSCORE!CurrentIP` at `0x18002c0cc`
- `WDSCORE!CurrentIP` at `0x18002c1ea`
- `WDSCORE!CurrentIP` at `0x18002c2de`
- `WDSCORE!CurrentIP` at `0x18002c341`
- `WDSCORE!CurrentIP` at `0x18002c3f6`
- `WDSCORE!CurrentIP` at `0x18002c496`
- `WDSCORE!CurrentIP` at `0x18002c554`
- `WDSCORE!WdsTerminate` at `0x18002c5d6`
- `WDSCORE!WdsTerminate` at `0x18002c5d6`
- `WDSCORE!WdsInitialize` at `0x18002bbe6`
- `WDSCORE!WdsInitialize` at `0x18002bbe6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bc90`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bd3d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002be29`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bec6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bf3b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bfb3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c030`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c12e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c196`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c294`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c452`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c546`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c5b0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bc90`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bd3d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002be29`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bec6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bf3b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bfb3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c030`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c12e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c196`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c294`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c452`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c546`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002c5b0`

## string_xrefs

- `0x18002be33`: `RemoveWindowsOld`
- `0x18002bcc1`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002bd89`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002bdec`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002be95`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002bf7d`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c072`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c0f1`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c159`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c20f`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c257`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c300`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c360`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c415`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c4bb`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c504`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002c573`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run`
- `0x18002bc79`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002bd07`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002bda3`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002be06`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002be89`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002bf05`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002bf43`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002bffa`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c038`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c117`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c17f`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c229`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c27d`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c31a`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c37a`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c43b`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c4da`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c523`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c58d`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002c3fc`: `RemoveWindowsOld value is not set`
- `0x18002be70`: `RemoveWindowsOld value is set`
- `0x18002bfe1`: `SppDeleteSnapshots failed. hr = 0x%x`
- `0x18002c059`: `Interruption requested - Delete SPP snapshots.`
- `0x18002c4a7`: `Fail to reset RemoveWindowsOld. hr = 0x%x`
- `0x18002c4f0`: `Reset RemoveWindowsOld value to 0`
- `0x18002c55a`: `Cleanup completed successfully`
- `0x18002bc53`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Init`

## pseudocode

```c
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::Run(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        TraceLoggingCorrelationVector *a5,
        _DWORD *a6,
        _DWORD *a7,
        __int64 a8,
        _DWORD *a9)
{
  unsigned int v9; // esi
  DWORD LastError; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  LPCWSTR v17[4]; // [rsp+68h] [rbp-51h] BYREF
  int v18[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v19; // [rsp+90h] [rbp-29h]
  __int128 v20; // [rsp+98h] [rbp-21h]
  __int64 v21; // [rsp+A8h] [rbp-11h]

  memset(v17, 0, sizeof(v17));
  *(_QWORD *)v18 = 0;
  v19 = 0;
  v9 = CMiscHelpersT<CEmptyType>::ExpandFileName(L"%windir%\\Panther\\FastCleanup");
  if ( (v9 & 0x80000000) == 0 )
  {
    v21 = 0;
    v20 = 0;
    v9 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(2147942487LL);
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
  LastError = GetLastError();
  v11 = CurrentIP();
  v12 = ConstructPartialMsgW(0x2000000u, "Initialization failed. hr = %x0x", v9);
  WdsSetupLogMessageW(
    v12,
    0,
    L"D",
    0,
    512,
    L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
    L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Init",
    v11,
    LastError,
    0,
    0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
  v13 = GetLastError();
  v14 = CurrentIP();
  v15 = ConstructPartialMsgW(0x2000000u, "Cleanup failed. hr = 0x%x", v9);
  WdsSetupLogMessageW(
    v15,
    0,
    L"D",
    0,
    405,
    L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
    L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::Run",
    v14,
    v13,
    0,
    0);
  if ( CDirectoryProviderT<CWindowsOldAdaptor>::g_pDirectoryProvider )
  {
    operator delete((void *)CDirectoryProviderT<CWindowsOldAdaptor>::g_pDirectoryProvider);
    CDirectoryProviderT<CWindowsOldAdaptor>::g_pDirectoryProvider = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  WdsTerminate();
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = -1;
  if ( a9 )
    *a9 = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>(v18);
  SP<CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>>>::~SP<CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>>>(v17);
  return v9;
}

```

## disassembly

```asm
0x18002bae0  mov     rax, rsp
0x18002bae3  mov     [rax+20h], r9d
0x18002bae7  mov     [rax+18h], r8
0x18002baeb  mov     [rax+10h], edx
0x18002baee  mov     [rax+8], ecx
0x18002baf1  push    rbp
0x18002baf2  push    rbx
0x18002baf3  push    rsi
0x18002baf4  push    rdi
0x18002baf5  push    r12
0x18002baf7  push    r13
0x18002baf9  push    r14
0x18002bafb  push    r15
0x18002bafd  lea     rbp, [rax-47h]
0x18002bb01  sub     rsp, 0B8h
0x18002bb08  xor     r15d, r15d
0x18002bb0b  lea     rdx, [rbp+3Fh+lpFileName]
0x18002bb0f  xorps   xmm0, xmm0
0x18002bb12  mov     [rbp+3Fh+var_90], r15
0x18002bb16  or      r13d, 0FFFFFFFFh
0x18002bb1a  movsd   [rbp+3Fh+var_80], xmm0
0x18002bb1f  lea     rcx, aWindirPantherF; "%windir%\\Panther\\FastCleanup"
0x18002bb26  movsd   [rbp+3Fh+var_78], xmm0
0x18002bb2b  mov     r12d, r15d
0x18002bb2e  mov     [rbp+3Fh+arg_10], r15
0x18002bb32  mov     qword ptr [rbp+3Fh+var_70], r15
0x18002bb36  mov     [rbp+3Fh+var_68], r15
0x18002bb3a  mov     dword ptr [rbp+3Fh+arg_18], r15d
0x18002bb3e  mov     [rbp+3Fh+arg_8], r13d
0x18002bb42  mov     [rbp+3Fh+arg_0], r13d
0x18002bb46  mov     [rbp+3Fh+lpFileName], r15
0x18002bb4a  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x18002bb4f  mov     r14, [rbp+3Fh+lpFileName]
0x18002bb53  mov     esi, eax
0x18002bb55  test    eax, eax
0x18002bb57  js      loc_18002BC1E
0x18002bb5d  xor     eax, eax
0x18002bb5f  xorps   xmm0, xmm0
0x18002bb62  mov     [rbp+3Fh+var_50], rax
0x18002bb66  movups  [rbp+3Fh+var_60], xmm0
0x18002bb6a  test    r14, r14
0x18002bb6d  jnz     short loc_18002BB78
0x18002bb6f  mov     esi, 80070057h
0x18002bb74  mov     ecx, esi
0x18002bb76  jmp     short loc_18002BBBA
0x18002bb78  mov     rcx, r14; lpFileName
0x18002bb7b  call    cs:__imp_GetFileAttributesW
0x18002bb81  mov     ebx, eax
0x18002bb83  cmp     eax, r13d
0x18002bb86  jz      short loc_18002BB90
0x18002bb88  shr     ebx, 4
0x18002bb8b  and     ebx, 1
0x18002bb8e  jmp     short loc_18002BB93
0x18002bb90  mov     ebx, r15d
0x18002bb93  xor     ecx, ecx
0x18002bb95  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002bb9a  xor     ecx, ecx
0x18002bb9c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002bba1  mov     esi, r15d
0x18002bba4  test    ebx, ebx
0x18002bba6  jnz     short loc_18002BBBF
0x18002bba8  xor     edx, edx
0x18002bbaa  mov     rcx, r14
0x18002bbad  call    ?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)
0x18002bbb2  mov     esi, eax
0x18002bbb4  test    eax, eax
0x18002bbb6  jns     short loc_18002BBBF
0x18002bbb8  mov     ecx, eax
0x18002bbba  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002bbbf  mov     ecx, esi
0x18002bbc1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002bbc6  test    esi, esi
0x18002bbc8  js      short loc_18002BC1E
0x18002bbca  mov     [rsp+0F0h+var_C0], r15
0x18002bbcf  mov     r9, r14
0x18002bbd2  mov     dword ptr [rsp+0F0h+var_C8], r15d
0x18002bbd7  xor     r8d, r8d
0x18002bbda  xor     edx, edx
0x18002bbdc  mov     [rsp+0F0h+var_D0], 310F000h
0x18002bbe4  xor     ecx, ecx
0x18002bbe6  call    cs:__imp_WdsInitialize
0x18002bbec  mov     ecx, 1; Size
0x18002bbf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bbf6  test    rax, rax
0x18002bbf9  jnz     short loc_18002BC09
0x18002bbfb  mov     esi, 8007000Eh
0x18002bc00  mov     ecx, esi
0x18002bc02  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002bc07  jmp     short loc_18002BC13
0x18002bc09  mov     esi, r15d
0x18002bc0c  mov     cs:?g_pDirectoryProvider@?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@0PEAV1@EA, rax; CDirectoryProviderT<CWindowsOldAdaptor> * CDirectoryProviderT<CWindowsOldAdaptor>::g_pDirectoryProvider
0x18002bc13  mov     ecx, esi
0x18002bc15  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002bc1a  test    esi, esi
0x18002bc1c  jns     short loc_18002BC96
0x18002bc1e  mov     ecx, esi
0x18002bc20  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002bc25  test    esi, esi
0x18002bc27  jns     short loc_18002BC96
0x18002bc29  call    cs:__imp_GetLastError
0x18002bc2f  mov     edi, eax
0x18002bc31  call    cs:__imp_CurrentIP
0x18002bc37  mov     r8d, esi
0x18002bc3a  lea     rdx, aInitialization; "Initialization failed. hr = %x0x"
0x18002bc41  mov     ecx, 2000000h; unsigned int
0x18002bc46  mov     rbx, rax
0x18002bc49  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002bc4e  mov     [rsp+50h], r15d
0x18002bc53  lea     rcx, aCfastdeleteimp_7; "CFastDeleteImplT<class CDirectoryProvid"...
0x18002bc5a  mov     qword ptr [rsp+0F0h+var_A8], r15
0x18002bc5f  lea     r8, aD_0; "D"
0x18002bc66  mov     dword ptr [rsp+0F0h+var_B0], edi
0x18002bc6a  xor     r9d, r9d
0x18002bc6d  mov     [rsp+0F0h+var_B8], rbx
0x18002bc72  xor     edx, edx
0x18002bc74  mov     [rsp+0F0h+var_C0], rcx
0x18002bc79  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x18002bc80  mov     [rsp+0F0h+var_C8], rcx
0x18002bc85  mov     rcx, rax
0x18002bc88  mov     [rsp+0F0h+var_D0], 200h
0x18002bc90  call    cs:__imp_WdsSetupLogMessageW
0x18002bc96  mov     ecx, esi
0x18002bc98  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002bc9d  test    r14, r14
0x18002bca0  jz      short loc_18002BCBE
0x18002bca2  call    cs:__imp_GetProcessHeap
0x18002bca8  lea     r8, [r14-4]; lpMem
0x18002bcac  xor     edx, edx; dwFlags
0x18002bcae  mov     rcx, rax; hHeap
0x18002bcb1  call    cs:__imp_HeapFree
0x18002bcb7  xor     ecx, ecx
0x18002bcb9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002bcbe  xor     r14d, r14d
0x18002bcc1  lea     r15, aCfastdeleteimp_6; "CFastDeleteImplT<class CDirectoryProvid"...
0x18002bcc8  test    esi, esi
0x18002bcca  jns     short loc_18002BCD6
0x18002bccc  mov     r15d, r14d
0x18002bccf  mov     ecx, esi
0x18002bcd1  jmp     loc_18002C2D1
0x18002bcd6  call    cs:__imp_GetLastError
0x18002bcdc  mov     edi, eax
0x18002bcde  call    cs:__imp_CurrentIP
0x18002bce4  mov     r9d, 3
0x18002bcea  lea     rdx, aPerformSetupFo; "Perform setup folder cleanup with bPref"...
0x18002bcf1  mov     ecx, 4000000h; unsigned int
0x18002bcf6  mov     rbx, rax
0x18002bcf9  lea     r8d, [r9-2]
0x18002bcfd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002bd02  mov     [rsp+50h], r14d
0x18002bd07  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x18002bd0e  mov     qword ptr [rsp+0F0h+var_A8], r14
0x18002bd13  lea     r8, aD_0; "D"
0x18002bd1a  mov     dword ptr [rsp+0F0h+var_B0], edi
0x18002bd1e  xor     r9d, r9d
0x18002bd21  mov     [rsp+0F0h+var_B8], rbx
0x18002bd26  xor     edx, edx
0x18002bd28  mov     [rsp+0F0h+var_C0], r15
0x18002bd2d  mov     [rsp+0F0h+var_C8], rcx
0x18002bd32  mov     rcx, rax
0x18002bd35  mov     [rsp+0F0h+var_D0], 0D5h
0x18002bd3d  call    cs:__imp_WdsSetupLogMessageW
0x18002bd43  lea     r9, [rbp+3Fh+arg_8]
0x18002bd47  mov     r15d, 5
0x18002bd4d  lea     r8, aLastmigrations; "LastMigrationScope"
0x18002bd54  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG1PEAK@Z; CRegUtilT<ulong,CRegType,0,0>::GetValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002bd59  mov     esi, eax
0x18002bd5b  cmp     eax, 80070002h
0x18002bd60  jnz     short loc_18002BDB9
0x18002bd62  call    cs:__imp_GetLastError
0x18002bd68  mov     edi, eax
0x18002bd6a  call    cs:__imp_CurrentIP
0x18002bd70  lea     rdx, aMigrationScope; "Migration scope value is not set"
0x18002bd77  mov     ecx, 4000000h; unsigned int
0x18002bd7c  mov     rbx, rax
0x18002bd7f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002bd84  mov     [rsp+50h], r14d
0x18002bd89  lea     rcx, aCfastdeleteimp_6; "CFastDeleteImplT<class CDirectoryProvid"...
0x18002bd90  mov     qword ptr [rsp+0F0h+var_A8], r14
0x18002bd95  mov     dword ptr [rsp+0F0h+var_B0], edi
0x18002bd99  mov     [rsp+0F0h+var_B8], rbx
0x18002bd9e  mov     [rsp+0F0h+var_C0], rcx
0x18002bda3  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x18002bdaa  mov     [rsp+0F0h+var_C8], rcx
0x18002bdaf  mov     [rsp+0F0h+var_D0], 0E7h
0x18002bdb7  jmp     short loc_18002BE1A
0x18002bdb9  test    eax, eax
0x18002bdbb  js      loc_18002C2CF
0x18002bdc1  call    cs:__imp_GetLastError
0x18002bdc7  mov     edi, eax
0x18002bdc9  call    cs:__imp_CurrentIP
0x18002bdcf  mov     r8d, [rbp+3Fh+arg_8]
0x18002bdd3  lea     rdx, aMigrationScope_0; "Migration scope value %d"
0x18002bdda  mov     ecx, 4000000h; unsigned int
0x18002bddf  mov     rbx, rax
0x18002bde2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002bde7  mov     [rsp+50h], r14d
0x18002bdec  lea     rcx, aCfastdeleteimp_6; "CFastDeleteImplT<class CDirectoryProvid"...
0x18002bdf3  mov     qword ptr [rsp+0F0h+var_A8], r14
0x18002bdf8  mov     dword ptr [rsp+0F0h+var_B0], edi
0x18002bdfc  mov     [rsp+0F0h+var_B8], rbx
0x18002be01  mov     [rsp+0F0h+var_C0], rcx
0x18002be06  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x18002be0d  mov     [rsp+0F0h+var_C8], rcx
0x18002be12  mov     [rsp+0F0h+var_D0], 0ECh
0x18002be1a  xor     r9d, r9d
0x18002be1d  lea     r8, aD_0; "D"
0x18002be24  xor     edx, edx
0x18002be26  mov     rcx, rax
0x18002be29  call    cs:__imp_WdsSetupLogMessageW
0x18002be2f  lea     r9, [rbp+3Fh+arg_0]
0x18002be33  lea     r8, aRemovewindowso; "RemoveWindowsOld"
0x18002be3a  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG1PEAK@Z; CRegUtilT<ulong,CRegType,0,0>::GetValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002be3f  mov     r13d, [rbp+3Fh+arg_0]
0x18002be43  mov     esi, eax
0x18002be45  cmp     eax, 80070002h
0x18002be4a  jz      loc_18002C3EE
0x18002be50  cmp     r13d, 1
0x18002be54  jnz     loc_18002C3EE
0x18002be5a  test    eax, eax
0x18002be5c  js      loc_18002C2CF
0x18002be62  call    cs:__imp_GetLastError
0x18002be68  mov     edi, eax
0x18002be6a  call    cs:__imp_CurrentIP
0x18002be70  lea     rdx, aRemovewindowso_1; "RemoveWindowsOld value is set"
0x18002be77  mov     ecx, 4000000h; unsigned int
0x18002be7c  mov     rbx, rax
0x18002be7f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002be84  mov     [rsp+50h], r14d
0x18002be89  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x18002be90  mov     qword ptr [rsp+0F0h+var_A8], r14
0x18002be95  lea     r15, aCfastdeleteimp_6; "CFastDeleteImplT<class CDirectoryProvid"...
0x18002be9c  mov     dword ptr [rsp+0F0h+var_B0], edi
0x18002bea0  lea     r8, aD_0; "D"
0x18002bea7  mov     [rsp+0F0h+var_B8], rbx
0x18002beac  xor     r9d, r9d
0x18002beaf  mov     [rsp+0F0h+var_C0], r15
0x18002beb4  xor     edx, edx
0x18002beb6  mov     [rsp+0F0h+var_C8], rcx
0x18002bebb  mov     rcx, rax
0x18002bebe  mov     [rsp+0F0h+var_D0], 0FEh
0x18002bec6  call    cs:__imp_WdsSetupLogMessageW
0x18002becc  lea     rdx, [rbp+3Fh+arg_18]
0x18002bed0  call    ?PrefetchMFT@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEAH@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::PrefetchMFT(void *,int *)
0x18002bed5  mov     esi, eax
0x18002bed7  test    eax, eax
0x18002bed9  jns     short loc_18002BF43
0x18002bedb  call    cs:__imp_GetLastError
0x18002bee1  mov     edi, eax
0x18002bee3  call    cs:__imp_CurrentIP
0x18002bee9  mov     r8d, esi
0x18002beec  lea     rdx, aPrefetchMftFai; "Prefetch $MFT failed. hr = 0x%x"
0x18002bef3  mov     ecx, 3000000h; unsigned int
0x18002bef8  mov     rbx, rax
0x18002befb  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002bf00  mov     [rsp+50h], r14d
0x18002bf05  lea     rsi, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x18002bf0c  mov     qword ptr [rsp+0F0h+var_A8], r14
0x18002bf11  lea     r8, aD_0; "D"
0x18002bf18  mov     dword ptr [rsp+0F0h+var_B0], edi
0x18002bf1c  xor     r9d, r9d
0x18002bf1f  mov     [rsp+0F0h+var_B8], rbx
0x18002bf24  xor     edx, edx
0x18002bf26  mov     [rsp+0F0h+var_C0], r15
0x18002bf2b  mov     rcx, rax
0x18002bf2e  mov     [rsp+0F0h+var_C8], rsi
0x18002bf33  mov     [rsp+0F0h+var_D0], 10Ch
0x18002bf3b  call    cs:__imp_WdsSetupLogMessageW
0x18002bf41  jmp     short loc_18002BF4A
0x18002bf43  lea     rsi, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x18002bf4a  cmp     dword ptr [rbp+3Fh+arg_18], r14d
0x18002bf4e  jz      short loc_18002BFC1
0x18002bf50  mov     r15d, 0Ah
0x18002bf56  call    cs:__imp_GetLastError
0x18002bf5c  mov     edi, eax
0x18002bf5e  call    cs:__imp_CurrentIP
0x18002bf64  lea     rdx, aInterruptionRe_1; "Interruption requested - Prefech."
0x18002bf6b  mov     ecx, 4000000h; unsigned int
0x18002bf70  mov     rbx, rax
0x18002bf73  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002bf78  mov     [rsp+50h], r14d
0x18002bf7d  lea     rcx, aCfastdeleteimp_6; "CFastDeleteImplT<class CDirectoryProvid"...
0x18002bf84  mov     qword ptr [rsp+0F0h+var_A8], r14
0x18002bf89  mov     dword ptr [rsp+0F0h+var_B0], edi
0x18002bf8d  mov     [rsp+0F0h+var_B8], rbx
0x18002bf92  mov     [rsp+0F0h+var_C0], rcx
0x18002bf97  mov     [rsp+0F0h+var_C8], rsi
0x18002bf9c  mov     [rsp+0F0h+var_D0], 111h
0x18002bfa4  xor     r9d, r9d
0x18002bfa7  lea     r8, aD_0; "D"
0x18002bfae  xor     edx, edx
0x18002bfb0  mov     rcx, rax
0x18002bfb3  call    cs:__imp_WdsSetupLogMessageW
0x18002bfb9  mov     esi, r14d
0x18002bfbc  jmp     loc_18002C464
0x18002bfc1  lea     rdx, [rbp+3Fh+arg_18]
0x18002bfc5  call    ?SppDeleteSnapshots@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEAH@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::SppDeleteSnapshots(void *,int *)
0x18002bfca  mov     esi, eax
0x18002bfcc  test    eax, eax
0x18002bfce  jns     short loc_18002C038
0x18002bfd0  call    cs:__imp_GetLastError
  ... truncated ...
```
