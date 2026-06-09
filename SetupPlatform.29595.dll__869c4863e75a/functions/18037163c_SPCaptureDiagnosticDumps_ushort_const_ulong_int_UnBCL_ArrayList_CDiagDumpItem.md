# SPCaptureDiagnosticDumps(ushort const *,ulong,int,UnBCL::ArrayList<CDiagDumpItem *> *)

- ea: `0x18037163c`
- end: `0x1803723f7`
- name: `?SPCaptureDiagnosticDumps@@YAJPEBGKHPEAV?$ArrayList@PEAVCDiagDumpItem@@@UnBCL@@@Z`
- size: `3515`
- prototype: `void __noreturn(unsigned __int16 *, unsigned int, int, int, int, int, int, int, int, int, int, DWORD dwSize, int, LPVOID lpMem, int, SC_HANDLE hSCManager, int, int, int, __int64 pExceptionObject, int, int, int, int, int, int, int, int, int, int, int, BYTE Buffer, int, int, int, int, int, WCHAR ExeName)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18027ce2c`
- `0x180346360`

## callees

- `0x18001413d`
- `0x180057dec`
- `0x18009cf70`
- `0x1800a2880`
- `0x18011787c`
- `0x1802d010c`
- `0x18036ff98`
- `0x18037163c`
- `0x180372400`
- `0x180372544`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x1803719d8`
- `ADVAPI32!OpenSCManagerW` at `0x1803719d8`
- `ADVAPI32!OpenServiceW` at `0x180371ab1`
- `ADVAPI32!OpenServiceW` at `0x180371ab1`
- `ADVAPI32!CloseServiceHandle` at `0x180371c74`
- `ADVAPI32!CloseServiceHandle` at `0x1803723a9`
- `ADVAPI32!CloseServiceHandle` at `0x180371c74`
- `ADVAPI32!CloseServiceHandle` at `0x1803723a9`
- `ADVAPI32!QueryServiceStatusEx` at `0x180371ba2`
- `ADVAPI32!QueryServiceStatusEx` at `0x180371ba2`
- `KERNEL32!GetProcessHeap` at `0x180371e50`
- `KERNEL32!GetProcessHeap` at `0x180371f35`
- `KERNEL32!GetProcessHeap` at `0x180371f61`
- `KERNEL32!GetProcessHeap` at `0x1803723b4`
- `KERNEL32!GetProcessHeap` at `0x180371e50`
- `KERNEL32!GetProcessHeap` at `0x180371f35`
- `KERNEL32!GetProcessHeap` at `0x180371f61`
- `KERNEL32!GetProcessHeap` at `0x1803723b4`
- `KERNEL32!HeapAlloc` at `0x180371f72`
- `KERNEL32!HeapAlloc` at `0x180371f72`
- `KERNEL32!HeapFree` at `0x180371f43`
- `KERNEL32!HeapFree` at `0x1803723c2`
- `KERNEL32!HeapFree` at `0x180371f43`
- `KERNEL32!HeapFree` at `0x1803723c2`
- `KERNEL32!GetLastError` at `0x1803716bd`
- `KERNEL32!GetLastError` at `0x18037173b`
- `KERNEL32!GetLastError` at `0x1803717c8`
- `KERNEL32!GetLastError` at `0x180371847`
- `KERNEL32!GetLastError` at `0x180371946`
- `KERNEL32!GetLastError` at `0x1803719f2`
- `KERNEL32!GetLastError` at `0x180371a08`
- `KERNEL32!GetLastError` at `0x180371a24`
- `KERNEL32!GetLastError` at `0x180371ac3`
- `KERNEL32!GetLastError` at `0x180371ad9`
- `KERNEL32!GetLastError` at `0x180371af5`
- `KERNEL32!GetLastError` at `0x180371bb3`
- `KERNEL32!GetLastError` at `0x180371bc9`
- `KERNEL32!GetLastError` at `0x180371be5`
- `KERNEL32!GetLastError` at `0x180371c83`
- `KERNEL32!GetLastError` at `0x180371d31`
- `KERNEL32!GetLastError` at `0x180371dba`
- `KERNEL32!GetLastError` at `0x180371e7f`
- `KERNEL32!GetLastError` at `0x180371e95`
- `KERNEL32!GetLastError` at `0x180371eb1`
- `KERNEL32!GetLastError` at `0x180371f8d`
- `KERNEL32!GetLastError` at `0x18037200d`
- `KERNEL32!GetLastError` at `0x1803721ac`
- `KERNEL32!GetLastError` at `0x18037226b`
- `KERNEL32!GetLastError` at `0x1803716bd`
- `KERNEL32!GetLastError` at `0x18037173b`
- `KERNEL32!GetLastError` at `0x1803717c8`
- `KERNEL32!GetLastError` at `0x180371847`
- `KERNEL32!GetLastError` at `0x180371946`
- `KERNEL32!GetLastError` at `0x1803719f2`
- `KERNEL32!GetLastError` at `0x180371a08`
- `KERNEL32!GetLastError` at `0x180371a24`
- `KERNEL32!GetLastError` at `0x180371ac3`
- `KERNEL32!GetLastError` at `0x180371ad9`
- `KERNEL32!GetLastError` at `0x180371af5`
- `KERNEL32!GetLastError` at `0x180371bb3`
- `KERNEL32!GetLastError` at `0x180371bc9`
- `KERNEL32!GetLastError` at `0x180371be5`
- `KERNEL32!GetLastError` at `0x180371c83`
- `KERNEL32!GetLastError` at `0x180371d31`
- `KERNEL32!GetLastError` at `0x180371dba`
- `KERNEL32!GetLastError` at `0x180371e7f`
- `KERNEL32!GetLastError` at `0x180371e95`
- `KERNEL32!GetLastError` at `0x180371eb1`
- `KERNEL32!GetLastError` at `0x180371f8d`
- `KERNEL32!GetLastError` at `0x18037200d`
- `KERNEL32!GetLastError` at `0x1803721ac`
- `KERNEL32!GetLastError` at `0x18037226b`
- `KERNEL32!CloseHandle` at `0x180372321`
- `KERNEL32!CloseHandle` at `0x180372321`
- `KERNEL32!OpenProcess` at `0x1803720a9`
- `KERNEL32!OpenProcess` at `0x1803720a9`
- `KERNEL32!K32EnumProcesses` at `0x180371e71`
- `KERNEL32!K32EnumProcesses` at `0x180371e71`
- `KERNEL32!QueryFullProcessImageNameW` at `0x1803720d5`
- `KERNEL32!QueryFullProcessImageNameW` at `0x1803720d5`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18037213c`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18037213c`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180372374`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180372374`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18037219e`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18037219e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180372133`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037218c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180372133`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037218c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180372109`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180372109`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1803720e8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1803720e8`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180372164`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180372164`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180371962`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180371a9f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180371b11`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180371c01`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180371dd6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180371962`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180371a9f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180371b11`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180371c01`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180371dd6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180372173`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180372318`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180372173`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180372318`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180372124`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18037214d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180372124`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18037214d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371721`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803717ad`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371833`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803718ac`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803719c1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371a89`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371c5e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371d06`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371e39`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371f1d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371ff9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18037223f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180372302`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371721`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803717ad`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371833`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803718ac`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803719c1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371a89`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371c5e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371d06`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371e39`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371f1d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180371ff9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18037223f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180372302`
- `WDSCORE!CurrentIP` at `0x1803716c5`
- `WDSCORE!CurrentIP` at `0x180371743`
- `WDSCORE!CurrentIP` at `0x1803717d0`
- `WDSCORE!CurrentIP` at `0x18037184f`
- `WDSCORE!CurrentIP` at `0x18037194e`
- `WDSCORE!CurrentIP` at `0x180371a2c`
- `WDSCORE!CurrentIP` at `0x180371afd`
- `WDSCORE!CurrentIP` at `0x180371bed`
- `WDSCORE!CurrentIP` at `0x180371c8b`
- `WDSCORE!CurrentIP` at `0x180371d39`
- `WDSCORE!CurrentIP` at `0x180371dc2`
- `WDSCORE!CurrentIP` at `0x180371eb9`
- `WDSCORE!CurrentIP` at `0x180371f95`
- `WDSCORE!CurrentIP` at `0x180372015`
- `WDSCORE!CurrentIP` at `0x1803721b4`
- `WDSCORE!CurrentIP` at `0x180372273`
- `WDSCORE!CurrentIP` at `0x1803716c5`
- `WDSCORE!CurrentIP` at `0x180371743`
- `WDSCORE!CurrentIP` at `0x1803717d0`
- `WDSCORE!CurrentIP` at `0x18037184f`
- `WDSCORE!CurrentIP` at `0x18037194e`
- `WDSCORE!CurrentIP` at `0x180371a2c`
- `WDSCORE!CurrentIP` at `0x180371afd`
- `WDSCORE!CurrentIP` at `0x180371bed`
- `WDSCORE!CurrentIP` at `0x180371c8b`
- `WDSCORE!CurrentIP` at `0x180371d39`
- `WDSCORE!CurrentIP` at `0x180371dc2`
- `WDSCORE!CurrentIP` at `0x180371eb9`
- `WDSCORE!CurrentIP` at `0x180371f95`
- `WDSCORE!CurrentIP` at `0x180372015`
- `WDSCORE!CurrentIP` at `0x1803721b4`
- `WDSCORE!CurrentIP` at `0x180372273`

## string_xrefs

- `0x1803716b1`: `SeDebugPrivilege`
- `0x180371a38`: `DIAGDUMP: Error opening SC manager. Error: 0x%08X`
- `0x18037196b`: `DIAGDUMP: Searching for host process for service %s`
- `0x18037185b`: `DIAGDUMP: Failed to create live kernel dump. Error: 0x%08X`
- `0x1803717d9`: `DIAGDUMP: Capturing live kernel dump`
- `0x18037174f`: `DIAGDUMP: Failed to create dump files for main process tree. Error: 0x%08X`
- `0x1803716ce`: `DIAGDUMP: Capturing dump of main process tree`
- `0x180371d65`: `DIAGDUMP: Failed to create dump file%s for process with ID: 0x%08X. Error: 0x%08X`
- `0x1803722a8`: `DIAGDUMP: Failed to create dump file%s for process with ID: 0x%08X. Error: 0x%08X`
- `0x180371c0d`: `DIAGDUMP: Error getting service status for %s. Error: 0x%08X`
- `0x180371b1d`: `DIAGDUMP: Error opening service %s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall __noreturn SPCaptureDiagnosticDumps(
        unsigned __int16 *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        DWORD dwSize,
        int a13,
        LPVOID lpMem,
        int a15,
        SC_HANDLE hSCManager,
        int a17,
        int hSCManagera,
        int a19,
        __int64 pExceptionObject,
        int a21,
        int pExceptionObjecta,
        int a23,
        int a24,
        int a25,
        int a26,
        int a27,
        int a28,
        int a29,
        int a30,
        int a31,
        BYTE Buffer,
        int a33,
        int Buffera,
        int a35,
        int a36,
        int a37,
        WCHAR ExeName)
{
  DWORD LastError; // edi
  __int64 v41; // rbx
  struct tagLOG_PARTIAL_MSG *v42; // rax
  __int64 *v43; // rbp
  __int64 *v44; // rdx
  __int64 v45; // [rsp+0h] [rbp-398h] BYREF
  int v46; // [rsp+64h] [rbp-334h]
  int v47[3]; // [rsp+74h] [rbp-324h] BYREF
  unsigned __int16 *v48; // [rsp+88h] [rbp-310h]
  __int64 v49; // [rsp+A8h] [rbp-2F0h]
  __int64 v50; // [rsp+C8h] [rbp-2D0h]
  BYTE v51[56]; // [rsp+D8h] [rbp-2C0h] BYREF

  v50 = -2;
  v49 = a4;
  v48 = a1;
  v46 = 0;
  v47[0] = 0;
  v47[1] = 0;
  SPCaptureDiagnosticDumps_::_3_::CXXXXXHandledException::CXXXXXHandledException(v51);
  SPEnablePrivilege(L"SeDebugPrivilege", 1, v47);
  LastError = GetLastError();
  v41 = CurrentIP();
  v42 = ConstructPartialMsgW(0x4000000u, "DIAGDUMP: Capturing dump of main process tree");
  WdsSetupLogMessageW(
    v42,
    0,
    L"D",
    0,
    89,
    L"base\\ntsetup\\setupplatform\\lib\\diagnostics\\diagnostics.cpp",
    L"SPCaptureDiagnosticDumps",
    v41,
    LastError,
    0,
    0);
  try
  {
    try
    {
      SPCaptureProcessDump(a2, a1, 1);
    }
    catch ( ___R0PEAVCXXXXXTemp__3__SPCaptureDiagnosticDumps__YAJPEBGKHPEAV__ArrayList_PEAVCDiagDumpItem___UnBCL___Z__8 )
    {
      SPCaptureDiagnosticDumps_::_1_::catch_6();
      __eh34_caught_type(
        1,
        ___R0PEAVCXXXXXTemp__3__SPCaptureDiagnosticDumps__YAJPEBGKHPEAV__ArrayList_PEAVCDiagDumpItem___UnBCL___Z__8);
    }
  }
  catch ( UnBCL::Exception * )
  {
    v44 = &v45;
    v43 = v44;
    if ( *((_DWORD *)v44 + 29) )
      SPEnablePrivilege(L"SeDebugPrivilege", 0, 0);
    if ( !*((_DWORD *)v43 + 30) )
      throw;
    UnBCL::Exception::~Exception((UnBCL::Exception *)v51);
  }
}

```

## disassembly

```asm
0x18037163c  push    rbx
0x18037163e  push    rsi
0x18037163f  push    rdi
0x180371640  push    r12
0x180371642  push    r13
0x180371644  push    r14
0x180371646  push    r15
0x180371648  sub     rsp, 360h
0x18037164f  mov     [rsp+398h+var_2D0], 0FFFFFFFFFFFFFFFEh
0x18037165b  mov     rax, cs:__security_cookie
0x180371662  xor     rax, rsp
0x180371665  mov     [rsp+398h+var_48], rax
0x18037166d  mov     r12, r9
0x180371670  mov     [rsp+398h+var_2F0], r9
0x180371678  mov     r14d, r8d
0x18037167b  mov     esi, edx
0x18037167d  mov     r15, rcx
0x180371680  mov     [rsp+398h+var_310], rcx
0x180371688  xor     r13d, r13d
0x18037168b  mov     [rsp+398h+var_334], r13d
0x180371690  mov     [rsp+398h+var_324], r13d
0x180371695  mov     [rsp+398h+var_320], r13d
0x18037169a  lea     rcx, [rsp+398h+var_2C0]
0x1803716a2  call    _SPCaptureDiagnosticDumps____3___CXXXXXHandledException__CXXXXXHandledException
0x1803716a7  nop
0x1803716a8  lea     r8, [rsp+398h+var_324]; int *
0x1803716ad  lea     edx, [r13+1]; int
0x1803716b1  lea     rcx, aSedebugprivile; "SeDebugPrivilege"
0x1803716b8  call    ?SPEnablePrivilege@@YAHPEBGHPEAH@Z; SPEnablePrivilege(ushort const *,int,int *)
0x1803716bd  call    cs:__imp_GetLastError
0x1803716c3  mov     edi, eax
0x1803716c5  call    cs:__imp_CurrentIP
0x1803716cb  mov     rbx, rax
0x1803716ce  lea     rdx, aDiagdumpCaptur; "DIAGDUMP: Capturing dump of main proces"...
0x1803716d5  mov     ecx, 4000000h; unsigned int
0x1803716da  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1803716df  mov     [rsp+398h+var_348], r13d
0x1803716e4  mov     [rsp+398h+var_350], r13
0x1803716e9  mov     [rsp+398h+var_358], edi
0x1803716ed  mov     [rsp+398h+var_360], rbx
0x1803716f2  lea     rcx, aSpcapturediagn; "SPCaptureDiagnosticDumps"
0x1803716f9  mov     [rsp+398h+var_368], rcx
0x1803716fe  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\lib\\diag"...
0x180371705  mov     [rsp+398h+var_370], rcx
0x18037170a  mov     dword ptr [rsp+398h+var_378], 59h ; 'Y'
0x180371712  xor     r9d, r9d
0x180371715  lea     r8, aD_0; "D"
0x18037171c  xor     edx, edx
0x18037171e  mov     rcx, rax
0x180371721  call    cs:__imp_WdsSetupLogMessageW
0x180371727  lea     r8d, [r13+1]; int
0x18037172b  mov     rdx, r15; unsigned __int16 *
0x18037172e  mov     ecx, esi; unsigned int
0x180371730  call    ?SPCaptureProcessDump@@YAJKPEBGH@Z; SPCaptureProcessDump(ulong,ushort const *,int)
0x180371735  mov     esi, eax
0x180371737  test    eax, eax
0x180371739  jns     short loc_1803717B9
0x18037173b  call    cs:__imp_GetLastError
0x180371741  mov     edi, eax
0x180371743  call    cs:__imp_CurrentIP
0x180371749  mov     rbx, rax
0x18037174c  mov     r8d, esi
0x18037174f  lea     rdx, aDiagdumpFailed_4; "DIAGDUMP: Failed to create dump files f"...
0x180371756  mov     r13d, 2000000h
0x18037175c  mov     ecx, r13d; unsigned int
0x18037175f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180371764  mov     [rsp+398h+var_348], 0
0x18037176c  mov     [rsp+398h+var_350], 0
0x180371775  mov     [rsp+398h+var_358], edi
0x180371779  mov     [rsp+398h+var_360], rbx
0x18037177e  lea     rcx, aSpcapturediagn; "SPCaptureDiagnosticDumps"
0x180371785  mov     [rsp+398h+var_368], rcx
0x18037178a  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\lib\\diag"...
0x180371791  mov     [rsp+398h+var_370], rcx
0x180371796  mov     dword ptr [rsp+398h+var_378], 5Eh ; '^'
0x18037179e  xor     r9d, r9d
0x1803717a1  lea     r8, aD_0; "D"
0x1803717a8  xor     edx, edx
0x1803717aa  mov     rcx, rax
0x1803717ad  call    cs:__imp_WdsSetupLogMessageW
0x1803717b3  mov     [rsp+398h+var_334], esi
0x1803717b7  jmp     short loc_1803717BF
0x1803717b9  mov     r13d, 2000000h
0x1803717bf  test    r14d, r14d
0x1803717c2  jz      loc_1803718B6
0x1803717c8  call    cs:__imp_GetLastError
0x1803717ce  mov     edi, eax
0x1803717d0  call    cs:__imp_CurrentIP
0x1803717d6  mov     rbx, rax
0x1803717d9  lea     rdx, aDiagdumpCaptur_0; "DIAGDUMP: Capturing live kernel dump"
0x1803717e0  mov     ecx, 4000000h; unsigned int
0x1803717e5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1803717ea  mov     [rsp+398h+var_348], 0
0x1803717f2  mov     [rsp+398h+var_350], 0
0x1803717fb  mov     [rsp+398h+var_358], edi
0x1803717ff  mov     [rsp+398h+var_360], rbx
0x180371804  lea     r14, aSpcapturediagn; "SPCaptureDiagnosticDumps"
0x18037180b  mov     [rsp+398h+var_368], r14
0x180371810  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\lib\\diag"...
0x180371817  mov     [rsp+398h+var_370], rcx
0x18037181c  mov     dword ptr [rsp+398h+var_378], 63h ; 'c'
0x180371824  xor     r9d, r9d
0x180371827  lea     r8, aD_0; "D"
0x18037182e  xor     edx, edx
0x180371830  mov     rcx, rax
0x180371833  call    cs:__imp_WdsSetupLogMessageW
0x180371839  mov     rcx, r15; unsigned __int16 *
0x18037183c  call    ?SPCaptureLiveKernelDump@@YAJPEBG@Z; SPCaptureLiveKernelDump(ushort const *)
0x180371841  mov     esi, eax
0x180371843  test    eax, eax
0x180371845  jns     short loc_1803718B6
0x180371847  call    cs:__imp_GetLastError
0x18037184d  mov     edi, eax
0x18037184f  call    cs:__imp_CurrentIP
0x180371855  mov     rbx, rax
0x180371858  mov     r8d, esi
0x18037185b  lea     rdx, aDiagdumpFailed_7; "DIAGDUMP: Failed to create live kernel "...
0x180371862  mov     ecx, r13d; unsigned int
0x180371865  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18037186a  mov     [rsp+398h+var_348], 0
0x180371872  mov     [rsp+398h+var_350], 0
0x18037187b  mov     [rsp+398h+var_358], edi
0x18037187f  mov     [rsp+398h+var_360], rbx
0x180371884  mov     [rsp+398h+var_368], r14
0x180371889  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\lib\\diag"...
0x180371890  mov     [rsp+398h+var_370], rcx
0x180371895  mov     dword ptr [rsp+398h+var_378], 68h ; 'h'
0x18037189d  xor     r9d, r9d
0x1803718a0  lea     r8, aD_0; "D"
0x1803718a7  xor     edx, edx
0x1803718a9  mov     rcx, rax
0x1803718ac  call    cs:__imp_WdsSetupLogMessageW
0x1803718b2  mov     [rsp+398h+var_334], esi
0x1803718b6  test    r12, r12
0x1803718b9  jz      loc_1803723C9
0x1803718bf  xor     r14d, r14d
0x1803718c2  mov     [rsp+398h+var_308], r14
0x1803718ca  xor     r15d, r15d
0x1803718cd  mov     [rsp+398h+var_318], r15
0x1803718d5  mov     [rsp+398h+var_330], r14d
0x1803718da  xor     ebx, ebx
0x1803718dc  mov     [rsp+398h+var_338], ebx
0x1803718e0  mov     rax, [r12+8]
0x1803718e5  movsxd  rcx, dword ptr [rax+0Ch]
0x1803718e9  add     rcx, 8
0x1803718ed  add     rcx, r12
0x1803718f0  mov     rax, [rcx]
0x1803718f3  mov     rax, [rax]
0x1803718f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803718fb  cmp     ebx, eax
0x1803718fd  jge     loc_1803723A1
0x180371903  mov     rax, [r12+8]
0x180371908  movsxd  rcx, dword ptr [rax+10h]
0x18037190c  add     rcx, 8
0x180371910  add     rcx, r12
0x180371913  mov     rax, [rcx]
0x180371916  mov     edx, ebx
0x180371918  mov     rax, [rax+18h]
0x18037191c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180371921  mov     r12, [rax]
0x180371924  mov     rcx, r12; this
0x180371927  call    ?get_Name@CDiagDumpItem@@QEAAPEAVString@UnBCL@@XZ; CDiagDumpItem::get_Name(void)
0x18037192c  test    rax, rax
0x18037192f  jz      loc_18037234D
0x180371935  mov     rcx, r12
0x180371938  call    ?GetType@CProvisioningElement@@UEAA?AW4_PROVISIONINGELEMENTTYPE@@XZ; CProvisioningElement::GetType(void)
0x18037193d  cmp     eax, 1
0x180371940  jnz     loc_180371DAC
0x180371946  call    cs:__imp_GetLastError
0x18037194c  mov     ebx, eax
0x18037194e  call    cs:__imp_CurrentIP
0x180371954  mov     rdi, rax
0x180371957  mov     rcx, r12; this
0x18037195a  call    ?get_Name@CDiagDumpItem@@QEAAPEAVString@UnBCL@@XZ; CDiagDumpItem::get_Name(void)
0x18037195f  mov     rcx, rax
0x180371962  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180371968  mov     r8, rax
0x18037196b  lea     rdx, aDiagdumpSearch; "DIAGDUMP: Searching for host process fo"...
0x180371972  mov     ecx, 4000000h; unsigned int
0x180371977  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18037197c  xor     r15d, r15d
0x18037197f  mov     [rsp+398h+var_348], r15d
0x180371984  mov     [rsp+398h+var_350], r15
0x180371989  mov     [rsp+398h+var_358], ebx
0x18037198d  mov     [rsp+398h+var_360], rdi
0x180371992  lea     rcx, aSpcapturediagn; "SPCaptureDiagnosticDumps"
0x180371999  mov     [rsp+398h+var_368], rcx
0x18037199e  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\lib\\diag"...
0x1803719a5  mov     [rsp+398h+var_370], rcx
0x1803719aa  mov     dword ptr [rsp+398h+var_378], 78h ; 'x'
0x1803719b2  xor     r9d, r9d
0x1803719b5  lea     r8, aD_0; "D"
0x1803719bc  xor     edx, edx
0x1803719be  mov     rcx, rax
0x1803719c1  call    cs:__imp_WdsSetupLogMessageW
0x1803719c7  test    r14, r14
0x1803719ca  jnz     loc_180371A94
0x1803719d0  xor     edx, edx; lpDatabaseName
0x1803719d2  xor     ecx, ecx; lpMachineName
0x1803719d4  lea     r8d, [r15+5]; dwDesiredAccess
0x1803719d8  call    cs:__imp_OpenSCManagerW
0x1803719de  mov     r14, rax
0x1803719e1  mov     [rsp+398h+var_308], rax
0x1803719e9  test    rax, rax
0x1803719ec  jnz     loc_180371A94
0x1803719f2  call    cs:__imp_GetLastError
0x1803719f8  test    eax, eax
0x1803719fa  jle     short loc_180371A06
0x1803719fc  movzx   eax, ax
0x1803719ff  or      eax, 80070000h
0x180371a04  test    eax, eax
0x180371a06  jns     short loc_180371A1F
0x180371a08  call    cs:__imp_GetLastError
0x180371a0e  mov     esi, eax
0x180371a10  test    eax, eax
0x180371a12  jle     short loc_180371A24
0x180371a14  movzx   esi, ax
0x180371a17  or      esi, 80070000h
0x180371a1d  jmp     short loc_180371A24
0x180371a1f  mov     esi, 80004005h
0x180371a24  call    cs:__imp_GetLastError
0x180371a2a  mov     edi, eax
0x180371a2c  call    cs:__imp_CurrentIP
0x180371a32  mov     rbx, rax
0x180371a35  mov     r8d, esi
0x180371a38  lea     rdx, aDiagdumpErrorO_0; "DIAGDUMP: Error opening SC manager. Err"...
0x180371a3f  mov     ecx, r13d; unsigned int
0x180371a42  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180371a47  mov     [rsp+398h+var_348], r15d
0x180371a4c  mov     [rsp+398h+var_350], r15
0x180371a51  mov     [rsp+398h+var_358], edi
0x180371a55  mov     [rsp+398h+var_360], rbx
0x180371a5a  lea     rcx, aSpcapturediagn; "SPCaptureDiagnosticDumps"
0x180371a61  mov     [rsp+398h+var_368], rcx
0x180371a66  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\lib\\diag"...
0x180371a6d  mov     [rsp+398h+var_370], rcx
0x180371a72  mov     dword ptr [rsp+398h+var_378], 81h
0x180371a7a  xor     r9d, r9d
0x180371a7d  lea     r8, aD_0; "D"
0x180371a84  xor     edx, edx
0x180371a86  mov     rcx, rax
0x180371a89  call    cs:__imp_WdsSetupLogMessageW
0x180371a8f  jmp     loc_18037233D
0x180371a94  mov     rcx, r12; this
0x180371a97  call    ?get_Name@CDiagDumpItem@@QEAAPEAVString@UnBCL@@XZ; CDiagDumpItem::get_Name(void)
0x180371a9c  mov     rcx, rax
0x180371a9f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180371aa5  mov     r8d, 4; dwDesiredAccess
0x180371aab  mov     rdx, rax; lpServiceName
0x180371aae  mov     rcx, r14; hSCManager
0x180371ab1  call    cs:__imp_OpenServiceW
0x180371ab7  mov     rbx, rax
0x180371aba  test    rax, rax
0x180371abd  jnz     loc_180371B64
0x180371ac3  call    cs:__imp_GetLastError
0x180371ac9  test    eax, eax
0x180371acb  jle     short loc_180371AD7
0x180371acd  movzx   eax, ax
0x180371ad0  or      eax, 80070000h
0x180371ad5  test    eax, eax
0x180371ad7  jns     short loc_180371AF0
0x180371ad9  call    cs:__imp_GetLastError
0x180371adf  mov     esi, eax
0x180371ae1  test    eax, eax
0x180371ae3  jle     short loc_180371AF5
0x180371ae5  movzx   esi, ax
0x180371ae8  or      esi, 80070000h
0x180371aee  jmp     short loc_180371AF5
0x180371af0  mov     esi, 80004005h
0x180371af5  call    cs:__imp_GetLastError
0x180371afb  mov     ebx, eax
0x180371afd  call    cs:__imp_CurrentIP
0x180371b03  mov     rdi, rax
0x180371b06  mov     rcx, r12; this
0x180371b09  call    ?get_Name@CDiagDumpItem@@QEAAPEAVString@UnBCL@@XZ; CDiagDumpItem::get_Name(void)
0x180371b0e  mov     rcx, rax
0x180371b11  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180371b17  mov     r9d, esi
0x180371b1a  mov     r8, rax
0x180371b1d  lea     rdx, aDiagdumpErrorO; "DIAGDUMP: Error opening service %s. Err"...
0x180371b24  mov     ecx, r13d; unsigned int
0x180371b27  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180371b2c  mov     [rsp+398h+var_348], r15d
0x180371b31  mov     [rsp+398h+var_350], r15
0x180371b36  mov     [rsp+398h+var_358], ebx
0x180371b3a  mov     [rsp+398h+var_360], rdi
0x180371b3f  lea     rcx, aSpcapturediagn; "SPCaptureDiagnosticDumps"
0x180371b46  mov     [rsp+398h+var_368], rcx
0x180371b4b  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\lib\\diag"...
0x180371b52  mov     [rsp+398h+var_370], rcx
0x180371b57  mov     dword ptr [rsp+398h+var_378], 8Ah
0x180371b5f  jmp     loc_180371A7A
0x180371b64  xorps   xmm0, xmm0
0x180371b67  xor     eax, eax
0x180371b69  movups  xmmword ptr [rsp+398h+var_288], xmm0
0x180371b71  movups  [rsp+398h+var_278], xmm0
0x180371b79  mov     [rsp+398h+var_268], eax
0x180371b80  mov     [rsp+398h+var_328], r15d
0x180371b85  lea     rax, [rsp+398h+var_328]
0x180371b8a  mov     [rsp+398h+var_378], rax; pcbBytesNeeded
  ... truncated ...
```
