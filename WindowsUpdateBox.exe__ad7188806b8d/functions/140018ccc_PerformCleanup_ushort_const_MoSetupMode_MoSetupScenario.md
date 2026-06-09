# PerformCleanup(ushort const *,MoSetupMode,MoSetupScenario)

- ea: `0x140018ccc`
- end: `0x1400192aa`
- name: `?PerformCleanup@@YAJPEBGW4MoSetupMode@@W4MoSetupScenario@@@Z`
- size: `1502`
- prototype: `__int64 __fastcall(const WCHAR *, int, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x140013894`

## callees

- `0x140003ad0`
- `0x1400076c8`
- `0x1400076e8`
- `0x14000b33c`
- `0x14000bbc4`
- `0x14000c20c`
- `0x14000e2a0`
- `0x140010148`
- `0x140010644`
- `0x1400135b8`
- `0x140016bb4`
- `0x140018ccc`
- `0x1400192b0`
- `0x14001dd28`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140019225`
- `KERNEL32!HeapFree` at `0x140019261`
- `KERNEL32!HeapFree` at `0x140019225`
- `KERNEL32!HeapFree` at `0x140019261`
- `KERNEL32!GetProcessHeap` at `0x140019211`
- `KERNEL32!GetProcessHeap` at `0x14001924d`
- `KERNEL32!GetProcessHeap` at `0x140019211`
- `KERNEL32!GetProcessHeap` at `0x14001924d`
- `KERNEL32!GetFileAttributesW` at `0x140018f28`
- `KERNEL32!GetFileAttributesW` at `0x140018f28`
- `ole32!CoUninitialize` at `0x140019283`
- `ole32!CoUninitialize` at `0x140019283`
- `ole32!CoInitializeEx` at `0x140018d41`
- `ole32!CoInitializeEx` at `0x140018d41`

## string_xrefs

- `0x140018d97`: `Checking cleanup registry value...`
- `0x140018f73`: `Populating preservation paths...`
- `0x140018fbc`: `Acquiring privileges...`
- `0x140019006`: `Cleaning install folder...`
- `0x140019094`: `Removing CorrelationVector registry value...`
- `0x1400190f8`: `Removing cleanup registry value...`
- `0x140019151`: `Flushing MoSetup registry key...`

## pseudocode

```c
__int64 __fastcall PerformCleanup(const WCHAR *a1, int a2, unsigned int a3)
{
  int v6; // ebx
  int v7; // edi
  unsigned int v8; // esi
  HRESULT v9; // eax
  HANDLE v10; // rcx
  __int64 v11; // rcx
  const wchar_t *v12; // r15
  const wchar_t *v13; // rdx
  unsigned int v14; // esi
  HANDLE v15; // rcx
  HANDLE v16; // rcx
  __int64 SetupVolatileRegKey; // rax
  __int64 v18; // rcx
  bool v19; // sf
  char *v20; // rax
  HANDLE v21; // rcx
  HANDLE v22; // rcx
  HANDLE v23; // rcx
  HANDLE v24; // rcx
  DWORD FileAttributesW; // edi
  int v26; // edi
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  const wchar_t *v30; // rdx
  __int64 v31; // rcx
  const wchar_t *v32; // rdx
  __int64 v33; // rcx
  void *v34; // rsi
  HANDLE ProcessHeap; // rax
  void *v36; // rsi
  HANDLE v37; // rax
  _DWORD v39[2]; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v40[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v41; // [rsp+50h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-18h]
  __int64 v43; // [rsp+60h] [rbp-10h] BYREF
  LPVOID v44; // [rsp+68h] [rbp-8h]
  unsigned int v45; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v46; // [rsp+C8h] [rbp+58h] BYREF

  v40[1] = -2;
  v6 = 0;
  v40[0] = 0;
  v39[0] = 17;
  v39[1] = 18;
  v43 = 0;
  v44 = 0;
  v41 = 0;
  lpMem = 0;
  v45 = 0;
  v46 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    v8 = -2147024809;
LABEL_62:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"%s: Error = 0x%X",
      L"PerformCleanup",
      v7);
    goto LABEL_64;
  }
  v7 = 0;
  v9 = CoInitializeEx(0, 0);
  if ( v9 < 0 )
  {
    if ( v9 != -2147417850 )
    {
      v7 = v9;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
    }
  }
  else
  {
    v6 = 1;
  }
  v8 = v7;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
    goto LABEL_62;
  v10 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v10 = g_shLogFile;
  OutputMsg(v10, g_shLogEvent, L"Checking cleanup registry value...");
  v12 = L"SYSTEM\\Setup\\MoSetup";
  if ( a3 == 7 )
  {
    v13 = L"SYSTEM\\Setup\\MCT";
  }
  else
  {
    v13 = L"SYSTEM\\Setup\\MoSetup";
    if ( a3 == 9 )
      v13 = L"SYSTEM\\Setup\\Servicing";
  }
  if ( (int)CRegUtilT<unsigned long,CRegType,0,1>::GetValue(v11, v13, L"Cleanup", &v45) < 0 )
  {
    v15 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v15 = g_shLogFile;
    OutputMsg(v15, g_shLogEvent, L"Cleanup value missing... assuming no cleanup.");
    v14 = 0;
  }
  else
  {
    v14 = v45;
  }
  if ( a2 == 1 )
  {
    v16 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v16 = g_shLogFile;
    OutputMsg(v16, g_shLogEvent, L"Checking SetupHost result value...");
    SetupVolatileRegKey = MoSetupReg::GetSetupVolatileRegKey(a3);
    v19 = (int)CRegUtilT<unsigned long,CRegType,0,1>::GetValue(v18, SetupVolatileRegKey, L"SetupHostResult", &v46) < 0;
    v20 = (char *)g_shLogFile - 1;
    if ( v19 )
    {
      v23 = 0;
      if ( (unsigned __int64)v20 <= 0xFFFFFFFFFFFFFFFDuLL )
        v23 = g_shLogFile;
      OutputMsg(v23, g_shLogEvent, L"SetupHost result value missing... forcing full cleanup.");
      v14 = 1;
      goto LABEL_34;
    }
    v21 = 0;
    if ( (unsigned __int64)v20 <= 0xFFFFFFFFFFFFFFFDuLL )
      v21 = g_shLogFile;
    OutputMsg(v21, g_shLogEvent, L"SetupHost result value: [0x%X]", v46);
  }
  if ( !v14 )
  {
    v22 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v22 = g_shLogFile;
    OutputMsg(v22, g_shLogEvent, L"Skipping cleanup.");
    v7 = 0;
    goto LABEL_64;
  }
LABEL_34:
  v24 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v24 = g_shLogFile;
  OutputMsg(v24, g_shLogEvent, L"Performing cleanup level: [0x%X]", v14);
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
    v26 = 0;
  else
    v26 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v26 )
  {
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Populating preservation paths...");
    v7 = PopulatePreservePaths(a1, v14, &v43, &v41);
    v8 = v7;
    if ( v7 < 0 )
      goto LABEL_62;
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Acquiring privileges...");
    v7 = CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(v40, v39, 2);
    v8 = v7;
    if ( v7 < 0 )
      goto LABEL_62;
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Cleaning install folder...");
    v7 = CleanInstallFolder((__int64)a1);
    v8 = v7;
    if ( v7 < 0 )
      goto LABEL_62;
  }
  OutputMsg(
    (HANDLE)((unsigned __int64)g_shLogFile
           & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
    g_shLogEvent,
    L"Cleaning MoSetup Volatile key...");
  v27 = MoSetupReg::GetSetupVolatileRegKey(a3);
  v7 = CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyIfExists(v28, v27);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_62;
  OutputMsg(
    (HANDLE)((unsigned __int64)g_shLogFile
           & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
    g_shLogEvent,
    L"Removing CorrelationVector registry value...");
  if ( a3 == 7 )
  {
    v30 = L"SYSTEM\\Setup\\MCT";
  }
  else
  {
    v30 = L"SYSTEM\\Setup\\MoSetup";
    if ( a3 == 9 )
      v30 = L"SYSTEM\\Setup\\Servicing";
  }
  v7 = CRegUtilT<unsigned short *,CRegType,0,1>::DeleteValueIfExists(v29, v30, L"CorrelationVector");
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_62;
  OutputMsg(
    (HANDLE)((unsigned __int64)g_shLogFile
           & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
    g_shLogEvent,
    L"Removing cleanup registry value...");
  if ( a3 == 7 )
  {
    v32 = L"SYSTEM\\Setup\\MCT";
  }
  else
  {
    v32 = L"SYSTEM\\Setup\\MoSetup";
    if ( a3 == 9 )
      v32 = L"SYSTEM\\Setup\\Servicing";
  }
  v7 = CRegUtilT<unsigned short *,CRegType,0,1>::DeleteValueIfExists(v31, v32, L"Cleanup");
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_62;
  OutputMsg(
    (HANDLE)((unsigned __int64)g_shLogFile
           & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
    g_shLogEvent,
    L"Flushing MoSetup registry key...");
  if ( a3 == 7 )
  {
    v12 = L"SYSTEM\\Setup\\MCT";
  }
  else if ( a3 == 9 )
  {
    v12 = L"SYSTEM\\Setup\\Servicing";
  }
  v7 = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v33, v12);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_62;
  OutputMsg(
    (HANDLE)((unsigned __int64)g_shLogFile
           & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
    g_shLogEvent,
    L"Cleanup was successful.");
LABEL_64:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(&v41, 0);
  v34 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v34);
    lpMem = 0;
  }
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(&v43, 0);
  v36 = v44;
  if ( v44 )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v36);
    v44 = 0;
  }
  CAutoRevertApplyPrivilegesT<CEmptyType>::~CAutoRevertApplyPrivilegesT<CEmptyType>(v40);
  if ( v6 )
    CoUninitialize();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140018ccc  mov     rax, rsp
0x140018ccf  push    rbp
0x140018cd0  push    rsi
0x140018cd1  push    rdi
0x140018cd2  push    r12
0x140018cd4  push    r13
0x140018cd6  push    r14
0x140018cd8  push    r15
0x140018cda  mov     rbp, rsp
0x140018cdd  sub     rsp, 70h
0x140018ce1  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x140018ce9  mov     [rax+10h], rbx
0x140018ced  mov     r14d, r8d
0x140018cf0  mov     r13d, edx
0x140018cf3  mov     r12, rcx
0x140018cf6  xor     r15d, r15d
0x140018cf9  mov     ebx, r15d
0x140018cfc  mov     [rbp+var_40], ebx
0x140018cff  mov     [rbp+var_30], r15
0x140018d03  mov     [rbp+var_38], 11h
0x140018d0a  mov     [rbp+var_34], 12h
0x140018d11  mov     [rbp+var_10], r15
0x140018d15  mov     [rbp+var_8], r15
0x140018d19  mov     [rbp+var_20], r15
0x140018d1d  mov     [rbp+lpMem], r15
0x140018d21  mov     [rbp+arg_0], r15d
0x140018d25  mov     [rbp+arg_18], r15d
0x140018d29  test    rcx, rcx
0x140018d2c  jnz     short loc_140018D3A
0x140018d2e  mov     edi, 80070057h
0x140018d33  mov     esi, edi
0x140018d35  jmp     loc_14001918B
0x140018d3a  mov     edi, r15d
0x140018d3d  xor     edx, edx; dwCoInit
0x140018d3f  xor     ecx, ecx; pvReserved
0x140018d41  call    cs:__imp_CoInitializeEx
0x140018d48  nop     dword ptr [rax+rax+00h]
0x140018d4d  test    eax, eax
0x140018d4f  js      short loc_140018D5B
0x140018d51  mov     ebx, 1
0x140018d56  mov     [rbp+var_40], ebx
0x140018d59  jmp     short loc_140018D6B
0x140018d5b  cmp     eax, 80010106h
0x140018d60  jz      short loc_140018D6B
0x140018d62  mov     edi, eax
0x140018d64  mov     ecx, eax
0x140018d66  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140018d6b  mov     esi, edi
0x140018d6d  mov     ecx, edi
0x140018d6f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140018d74  test    edi, edi
0x140018d76  js      loc_14001918B
0x140018d7c  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140018d83  lea     rax, [r8-1]
0x140018d87  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018d8b  setnbe  al
0x140018d8e  mov     rcx, r15
0x140018d91  test    al, al
0x140018d93  cmovz   rcx, r8; hFile
0x140018d97  lea     r8, aCheckingCleanu; "Checking cleanup registry value..."
0x140018d9e  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140018da5  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140018daa  lea     r15, aSystemSetupMos; "SYSTEM\\Setup\\MoSetup"
0x140018db1  lea     rax, aSystemSetupSer; "SYSTEM\\Setup\\Servicing"
0x140018db8  cmp     r14d, 7
0x140018dbc  jz      short loc_140018DCB
0x140018dbe  mov     rdx, r15
0x140018dc1  cmp     r14d, 9
0x140018dc5  cmovz   rdx, rax
0x140018dc9  jmp     short loc_140018DD2
0x140018dcb  lea     rdx, aSystemSetupMct_0; "SYSTEM\\Setup\\MCT"
0x140018dd2  lea     r9, [rbp+arg_0]
0x140018dd6  lea     r8, aCleanup; "Cleanup"
0x140018ddd  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAK@Z; CRegUtilT<ulong,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140018de2  test    eax, eax
0x140018de4  js      short loc_140018DEB
0x140018de6  mov     esi, [rbp+arg_0]
0x140018de9  jmp     short loc_140018E1A
0x140018deb  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140018df2  lea     rax, [r8-1]
0x140018df6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018dfa  setnbe  al
0x140018dfd  xor     ecx, ecx
0x140018dff  test    al, al
0x140018e01  cmovz   rcx, r8; hFile
0x140018e05  lea     r8, aCleanupValueMi; "Cleanup value missing... assuming no cl"...
0x140018e0c  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140018e13  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140018e18  xor     esi, esi
0x140018e1a  cmp     r13d, 1
0x140018e1e  jnz     short loc_140018E9D
0x140018e20  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140018e27  lea     rax, [r8-1]
0x140018e2b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018e2f  setnbe  al
0x140018e32  xor     ecx, ecx
0x140018e34  test    al, al
0x140018e36  cmovz   rcx, r8; hFile
0x140018e3a  lea     r8, aCheckingSetuph; "Checking SetupHost result value..."
0x140018e41  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140018e48  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140018e4d  mov     ecx, r14d
0x140018e50  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140018e55  mov     rdx, rax
0x140018e58  lea     r9, [rbp+arg_18]
0x140018e5c  lea     r8, aSetuphostresul; "SetupHostResult"
0x140018e63  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAK@Z; CRegUtilT<ulong,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140018e68  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140018e6f  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140018e76  test    eax, eax
0x140018e78  lea     rax, [r8-1]
0x140018e7c  js      short loc_140018ED5
0x140018e7e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018e82  setnbe  al
0x140018e85  xor     ecx, ecx
0x140018e87  test    al, al
0x140018e89  cmovz   rcx, r8; hFile
0x140018e8d  mov     r9d, [rbp+arg_18]
0x140018e91  lea     r8, aSetuphostResul_0; "SetupHost result value: [0x%X]"
0x140018e98  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140018e9d  test    esi, esi
0x140018e9f  jnz     short loc_140018EF5
0x140018ea1  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140018ea8  lea     rax, [r8-1]
0x140018eac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018eb0  setnbe  al
0x140018eb3  xor     ecx, ecx
0x140018eb5  test    al, al
0x140018eb7  cmovz   rcx, r8; hFile
0x140018ebb  lea     r8, aSkippingCleanu; "Skipping cleanup."
0x140018ec2  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140018ec9  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140018ece  xor     edi, edi
0x140018ed0  jmp     loc_1400191F5
0x140018ed5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018ed9  setnbe  al
0x140018edc  xor     ecx, ecx
0x140018ede  test    al, al
0x140018ee0  cmovz   rcx, r8; hFile
0x140018ee4  lea     r8, aSetuphostResul_3; "SetupHost result value missing... forci"...
0x140018eeb  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140018ef0  mov     esi, 1
0x140018ef5  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140018efc  lea     rax, [r8-1]
0x140018f00  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018f04  setnbe  al
0x140018f07  xor     ecx, ecx
0x140018f09  test    al, al
0x140018f0b  cmovz   rcx, r8; hFile
0x140018f0f  mov     r9d, esi
0x140018f12  lea     r8, aPerformingClea; "Performing cleanup level: [0x%X]"
0x140018f19  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140018f20  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140018f25  mov     rcx, r12; lpFileName
0x140018f28  call    cs:__imp_GetFileAttributesW
0x140018f2f  nop     dword ptr [rax+rax+00h]
0x140018f34  mov     edi, eax
0x140018f36  cmp     eax, 0FFFFFFFFh
0x140018f39  jz      short loc_140018F43
0x140018f3b  shr     edi, 4
0x140018f3e  and     edi, 1
0x140018f41  jmp     short loc_140018F45
0x140018f43  xor     edi, edi
0x140018f45  xor     ecx, ecx
0x140018f47  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140018f4c  xor     ecx, ecx
0x140018f4e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140018f53  test    edi, edi
0x140018f55  jz      loc_140019035
0x140018f5b  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140018f62  lea     rax, [r8+1]
0x140018f66  and     rax, 0FFFFFFFFFFFFFFFEh
0x140018f6a  neg     rax
0x140018f6d  sbb     rcx, rcx
0x140018f70  and     rcx, r8; hFile
0x140018f73  lea     r8, aPopulatingPres; "Populating preservation paths..."
0x140018f7a  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140018f81  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140018f86  lea     r9, [rbp+var_20]
0x140018f8a  lea     r8, [rbp+var_10]
0x140018f8e  mov     edx, esi
0x140018f90  mov     rcx, r12
0x140018f93  call    ?PopulatePreservePaths@@YAJPEBGW4eSetupCleanup@@PEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@2@Z; PopulatePreservePaths(ushort const *,eSetupCleanup,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *)
0x140018f98  mov     edi, eax
0x140018f9a  mov     esi, eax
0x140018f9c  test    eax, eax
0x140018f9e  js      loc_14001918B
0x140018fa4  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140018fab  lea     rax, [r8+1]
0x140018faf  and     rax, 0FFFFFFFFFFFFFFFEh
0x140018fb3  neg     rax
0x140018fb6  sbb     rcx, rcx
0x140018fb9  and     rcx, r8; hFile
0x140018fbc  lea     r8, aAcquiringPrivi; "Acquiring privileges..."
0x140018fc3  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140018fca  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140018fcf  mov     r8d, 2
0x140018fd5  lea     rdx, [rbp+var_38]
0x140018fd9  lea     rcx, [rbp+var_30]
0x140018fdd  call    ?Enable@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAAJPEBKK@Z; CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(ulong const *,ulong)
0x140018fe2  mov     edi, eax
0x140018fe4  mov     esi, eax
0x140018fe6  test    eax, eax
0x140018fe8  js      loc_14001918B
0x140018fee  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140018ff5  lea     rax, [r8+1]
0x140018ff9  and     rax, 0FFFFFFFFFFFFFFFEh
0x140018ffd  neg     rax
0x140019000  sbb     rcx, rcx
0x140019003  and     rcx, r8; hFile
0x140019006  lea     r8, aCleaningInstal; "Cleaning install folder..."
0x14001900d  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140019014  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140019019  lea     r8, [rbp+var_20]
0x14001901d  lea     rdx, [rbp+var_10]
0x140019021  mov     rcx, r12
0x140019024  call    ?CleanInstallFolder@@YAJPEBGPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@1@Z; CleanInstallFolder(ushort const *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *)
0x140019029  mov     edi, eax
0x14001902b  mov     esi, eax
0x14001902d  test    eax, eax
0x14001902f  js      loc_14001918B
0x140019035  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001903c  lea     rax, [r8+1]
0x140019040  and     rax, 0FFFFFFFFFFFFFFFEh
0x140019044  neg     rax
0x140019047  sbb     rcx, rcx
0x14001904a  and     rcx, r8; hFile
0x14001904d  lea     r8, aCleaningMosetu; "Cleaning MoSetup Volatile key..."
0x140019054  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001905b  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140019060  mov     ecx, r14d
0x140019063  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140019068  mov     rdx, rax
0x14001906b  call    ?DeleteKeyIfExists@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyIfExists(HKEY__ *,ushort const *)
0x140019070  mov     edi, eax
0x140019072  mov     esi, eax
0x140019074  test    eax, eax
0x140019076  js      loc_14001918B
0x14001907c  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140019083  lea     rax, [r8+1]
0x140019087  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001908b  neg     rax
0x14001908e  sbb     rcx, rcx
0x140019091  and     rcx, r8; hFile
0x140019094  lea     r8, aRemovingCorrel; "Removing CorrelationVector registry val"...
0x14001909b  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x1400190a2  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x1400190a7  lea     r12, aSystemSetupSer; "SYSTEM\\Setup\\Servicing"
0x1400190ae  cmp     r14d, 7
0x1400190b2  jz      short loc_1400190C1
0x1400190b4  mov     rdx, r15
0x1400190b7  cmp     r14d, 9
0x1400190bb  cmovz   rdx, r12
0x1400190bf  jmp     short loc_1400190C8
0x1400190c1  lea     rdx, aSystemSetupMct_0; "SYSTEM\\Setup\\MCT"
0x1400190c8  lea     r8, aCorrelationvec; "CorrelationVector"
0x1400190cf  call    ?DeleteValueIfExists@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1@Z; CRegUtilT<ushort *,CRegType,0,1>::DeleteValueIfExists(HKEY__ *,ushort const *,ushort const *)
0x1400190d4  mov     edi, eax
0x1400190d6  mov     esi, eax
0x1400190d8  test    eax, eax
0x1400190da  js      loc_14001918B
0x1400190e0  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x1400190e7  lea     rax, [r8+1]
0x1400190eb  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400190ef  neg     rax
0x1400190f2  sbb     rcx, rcx
0x1400190f5  and     rcx, r8; hFile
0x1400190f8  lea     r8, aRemovingCleanu; "Removing cleanup registry value..."
0x1400190ff  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140019106  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001910b  cmp     r14d, 7
0x14001910f  jz      short loc_14001911E
0x140019111  mov     rdx, r15
0x140019114  cmp     r14d, 9
0x140019118  cmovz   rdx, r12
0x14001911c  jmp     short loc_140019125
0x14001911e  lea     rdx, aSystemSetupMct_0; "SYSTEM\\Setup\\MCT"
0x140019125  lea     r8, aCleanup; "Cleanup"
0x14001912c  call    ?DeleteValueIfExists@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1@Z; CRegUtilT<ushort *,CRegType,0,1>::DeleteValueIfExists(HKEY__ *,ushort const *,ushort const *)
0x140019131  mov     edi, eax
0x140019133  mov     esi, eax
0x140019135  test    eax, eax
0x140019137  js      short loc_14001918B
0x140019139  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140019140  lea     rax, [r8+1]
0x140019144  and     rax, 0FFFFFFFFFFFFFFFEh
0x140019148  neg     rax
0x14001914b  sbb     rcx, rcx
0x14001914e  and     rcx, r8; hFile
0x140019151  lea     r8, aFlushingMosetu; "Flushing MoSetup registry key..."
0x140019158  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001915f  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140019164  cmp     r14d, 7
0x140019168  jz      short loc_140019174
0x14001916a  cmp     r14d, 9
0x14001916e  cmovz   r15, r12
0x140019172  jmp     short loc_14001917B
0x140019174  lea     r15, aSystemSetupMct_0; "SYSTEM\\Setup\\MCT"
0x14001917b  mov     rdx, r15
0x14001917e  call    ?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z; CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)
  ... truncated ...
```
