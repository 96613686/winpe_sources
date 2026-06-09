# CPackageScenarioCtrl::PopulateWorkingDir(ushort * *,ushort * *)

- ea: `0x140019830`
- end: `0x140019dab`
- name: `?PopulateWorkingDir@CPackageScenarioCtrl@@UEAAJPEAPEAG0@Z`
- size: `1403`
- prototype: `__int64 __fastcall(CPackageScenarioCtrl *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400076c8`
- `0x140007cb0`
- `0x140008434`
- `0x14000a564`
- `0x14000ba6c`
- `0x14000e2a0`
- `0x14000e878`
- `0x140010148`
- `0x1400135b8`
- `0x140016bb4`
- `0x1400195dc`
- `0x140019830`
- `0x14001dedc`
- `0x14001dfc8`
- `0x140053ba0`
- `0x140054ac8`
- `0x140054bd4`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140019ad5`
- `KERNEL32!GetCurrentProcessId` at `0x140019c3f`
- `KERNEL32!GetCurrentProcessId` at `0x140019ad5`
- `KERNEL32!GetCurrentProcessId` at `0x140019c3f`
- `KERNEL32!HeapFree` at `0x140019d1c`
- `KERNEL32!HeapFree` at `0x140019d4a`
- `KERNEL32!HeapFree` at `0x140019d79`
- `KERNEL32!HeapFree` at `0x140019d1c`
- `KERNEL32!HeapFree` at `0x140019d4a`
- `KERNEL32!HeapFree` at `0x140019d79`
- `KERNEL32!GetProcessHeap` at `0x140019d07`
- `KERNEL32!GetProcessHeap` at `0x140019d35`
- `KERNEL32!GetProcessHeap` at `0x140019d63`
- `KERNEL32!GetProcessHeap` at `0x140019d07`
- `KERNEL32!GetProcessHeap` at `0x140019d35`
- `KERNEL32!GetProcessHeap` at `0x140019d63`
- `KERNEL32!GetFileAttributesW` at `0x14001999b`
- `KERNEL32!GetFileAttributesW` at `0x14001999b`

## string_xrefs

- `0x1400198b9`: `Opening Box: [%s]`
- `0x14001990c`: `Reading Box header...`
- `0x140019a13`: `%s: Working directory was preserved so it is already populated.`
- `0x140019ac2`: `%s: Writing ProcessId value...`
- `0x140019c2c`: `%s: Writing ProcessId value...`
- `0x140019aef`: `ProcessId`
- `0x140019c59`: `ProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPackageScenarioCtrl::PopulateWorkingDir(
        CPackageScenarioCtrl *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  LPCWSTR v4; // r14
  __int64 v5; // r13
  void *v6; // r15
  __int64 v7; // rcx
  int Header; // edi
  HANDLE v9; // rcx
  __int64 v10; // rcx
  HANDLE v11; // rcx
  __int64 v12; // rcx
  DWORD FileAttributesW; // eax
  BOOL v14; // esi
  HANDLE v15; // rcx
  HANDLE v16; // rcx
  __int64 SetupVolatileRegKey; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  HANDLE v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned __int16 **v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // rcx
  HANDLE v33; // rcx
  HANDLE v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  HANDLE v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // r9
  __int64 v41; // rax
  __int64 v42; // rcx
  HANDLE v43; // rcx
  unsigned __int16 *v44; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v46; // rax
  LPCWSTR lpFileName; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v49[3]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v50[16]; // [rsp+58h] [rbp-28h] BYREF
  void *Src[2]; // [rsp+68h] [rbp-18h]
  void *v54; // [rsp+D8h] [rbp+58h] BYREF

  v49[1] = -2;
  v49[2] = 0;
  v4 = 0;
  lpFileName = 0;
  v5 = 0;
  v49[0] = 0;
  v6 = 0;
  v54 = 0;
  if ( a2 && a3 )
  {
    v9 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v9 = g_shLogFile;
    OutputMsg(v9, g_shLogEvent, L"Opening Box: [%s]", *((_QWORD *)this + 2));
    v10 = *((_QWORD *)this + 2);
    if ( !v10 )
      v10 = 0;
    Header = BoxOpenFromPath(v10, &v54);
    v7 = (unsigned int)Header;
    if ( Header < 0 )
    {
      v6 = v54;
      goto LABEL_54;
    }
    v11 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v11 = g_shLogFile;
    OutputMsg(v11, g_shLogEvent, L"Reading Box header...");
    *(_OWORD *)Src = 0;
    v6 = v54;
    Header = BoxReadHeader(v54, v50);
    v7 = (unsigned int)Header;
    if ( Header < 0 )
      goto LABEL_54;
    if ( !Src[1] )
    {
      Header = -2147019873;
LABEL_53:
      v7 = (unsigned int)Header;
      goto LABEL_54;
    }
    Header = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(Src[1]);
    v7 = (unsigned int)Header;
    if ( Header < 0 )
      goto LABEL_54;
    v12 = *((_QWORD *)this + 4);
    if ( !v12 )
      v12 = 0;
    Header = CMiscHelpersT<CEmptyType>::CombinePath(v12, 0, 0, &lpFileName);
    v7 = (unsigned int)Header;
    v4 = lpFileName;
    if ( Header < 0 )
      goto LABEL_54;
    FileAttributesW = GetFileAttributesW(lpFileName);
    v14 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( *((_DWORD *)this + 10) == 1 )
    {
      if ( *((_DWORD *)this + 14) )
      {
        v15 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v15 = g_shLogFile;
        OutputMsg(
          v15,
          g_shLogEvent,
          L"%s: Working directory was preserved so it is already populated.",
          L"CPackageScenarioCtrl::PopulateWorkingDir");
      }
      else
      {
        Header = CPackageScenarioCtrl::PopulateWorkingDir(this, v6);
        v7 = (unsigned int)Header;
        if ( Header < 0 )
          goto LABEL_54;
      }
      v16 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v16 = g_shLogFile;
      OutputMsg(v16, g_shLogEvent, L"%s: Setting PreDownload mode...", L"CPackageScenarioCtrl::PopulateWorkingDir");
      SetupVolatileRegKey = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CRegUtilT<unsigned long,CRegType,0,1>::CreateOrOpenKey(v18, SetupVolatileRegKey);
      v7 = (unsigned int)Header;
      if ( Header < 0 )
        goto LABEL_54;
      v19 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CRegUtilT<unsigned long,CRegType,0,1>::SetValue(v20, v19, L"PreDownloadMode", 1);
      v7 = (unsigned int)Header;
      if ( Header < 0 )
        goto LABEL_54;
      v21 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v21 = g_shLogFile;
      OutputMsg(v21, g_shLogEvent, L"%s: Writing ProcessId value...", L"CPackageScenarioCtrl::PopulateWorkingDir");
      GetCurrentProcessId();
      v22 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CRegUtilT<unsigned long,CRegType,0,1>::SetValue(v23, v22, L"ProcessId", v24);
      v7 = (unsigned int)Header;
      if ( Header < 0 )
        goto LABEL_54;
      v25 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v26, v25);
      v7 = (unsigned int)Header;
      if ( Header < 0 )
        goto LABEL_54;
      Header = ScenarioCtrlHelpers::GenerateBoxHash((ScenarioCtrlHelpers *)v49, v27);
      v7 = (unsigned int)Header;
      v5 = v49[0];
      if ( Header < 0 )
        goto LABEL_54;
      v28 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CRegUtilT<unsigned short *,CRegType,0,1>::SetValue(v29, v28, v30, v5);
      v7 = (unsigned int)Header;
      if ( Header < 0 )
        goto LABEL_54;
      v31 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v32, v31);
      v7 = (unsigned int)Header;
      if ( Header < 0 )
        goto LABEL_54;
      v33 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v33 = g_shLogFile;
      OutputMsg(v33, g_shLogEvent, L"%s: File hash stored!", L"CPackageScenarioCtrl::PopulateWorkingDir");
    }
    else
    {
      v34 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v34 = g_shLogFile;
      OutputMsg(v34, g_shLogEvent, L"%s: Clearing PreDownload mode...", L"CPackageScenarioCtrl::PopulateWorkingDir");
      v35 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CRegUtilT<unsigned long,CRegType,0,1>::DeleteValueIfExists(v36, v35, L"PreDownloadMode");
      v7 = (unsigned int)Header;
      if ( Header < 0 )
        goto LABEL_54;
      v37 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v37 = g_shLogFile;
      OutputMsg(v37, g_shLogEvent, L"%s: Writing ProcessId value...", L"CPackageScenarioCtrl::PopulateWorkingDir");
      GetCurrentProcessId();
      v38 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CRegUtilT<unsigned long,CRegType,0,1>::SetValue(v39, v38, L"ProcessId", v40);
      v7 = (unsigned int)Header;
      if ( Header < 0 )
        goto LABEL_54;
      v41 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v42, v41);
      v7 = (unsigned int)Header;
      if ( Header < 0 )
        goto LABEL_54;
      if ( !v14 )
      {
        Header = -2145116147;
        goto LABEL_53;
      }
    }
    v44 = (unsigned __int16 *)v4;
    v4 = 0;
    *a2 = v44;
    *a3 = 0;
    goto LABEL_58;
  }
  v7 = 2147942487LL;
  Header = -2147024809;
LABEL_54:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
  v43 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v43 = g_shLogFile;
  OutputMsg(v43, g_shLogEvent, L"%s: Error = 0x%X", L"CPackageScenarioCtrl::PopulateWorkingDir", Header);
LABEL_58:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)Header);
  if ( v6 )
    FreeBoxFileHandle(v6);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v5 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v46 = GetProcessHeap();
    HeapFree(v46, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)Header;
}

```

## disassembly

```asm
0x140019830  mov     rax, rsp
0x140019833  mov     [rax+18h], r8
0x140019837  mov     [rax+10h], rdx
0x14001983b  push    rbp
0x14001983c  push    rsi
0x14001983d  push    rdi
0x14001983e  push    r12
0x140019840  push    r13
0x140019842  push    r14
0x140019844  push    r15
0x140019846  mov     rbp, rsp
0x140019849  sub     rsp, 80h
0x140019850  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x140019858  mov     [rax+8], rbx
0x14001985c  mov     rax, r8
0x14001985f  mov     rbx, rcx
0x140019862  xor     esi, esi
0x140019864  mov     [rbp+var_30], rsi
0x140019868  mov     r12d, esi
0x14001986b  mov     [rbp+var_50], rsi
0x14001986f  mov     r14d, esi
0x140019872  mov     [rbp+lpFileName], rsi
0x140019876  mov     r13d, esi
0x140019879  mov     [rbp+var_40], rsi
0x14001987d  mov     r15d, esi
0x140019880  mov     [rbp+arg_18], rsi
0x140019884  test    rdx, rdx
0x140019887  jnz     short loc_140019895
0x140019889  mov     ecx, 80070057h
0x14001988e  mov     edi, ecx
0x140019890  jmp     loc_140019C96
0x140019895  test    rax, rax
0x140019898  jz      short loc_140019889
0x14001989a  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x1400198a1  lea     rax, [r8-1]
0x1400198a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400198a9  setnbe  al
0x1400198ac  mov     rcx, rsi
0x1400198af  test    al, al
0x1400198b1  cmovz   rcx, r8; hFile
0x1400198b5  mov     r9, [rbx+10h]
0x1400198b9  lea     r8, aOpeningBoxS; "Opening Box: [%s]"
0x1400198c0  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x1400198c7  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x1400198cc  mov     rcx, [rbx+10h]
0x1400198d0  test    rcx, rcx
0x1400198d3  cmovz   rcx, rsi
0x1400198d7  lea     rdx, [rbp+arg_18]
0x1400198db  call    BoxOpenFromPath
0x1400198e0  mov     edi, eax
0x1400198e2  mov     ecx, eax
0x1400198e4  test    eax, eax
0x1400198e6  jns     short loc_1400198F1
0x1400198e8  mov     r15, [rbp+arg_18]
0x1400198ec  jmp     loc_140019C96
0x1400198f1  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x1400198f8  lea     rax, [r8-1]
0x1400198fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019900  setnbe  al
0x140019903  mov     rcx, rsi
0x140019906  test    al, al
0x140019908  cmovz   rcx, r8; hFile
0x14001990c  lea     r8, aReadingBoxHead; "Reading Box header..."
0x140019913  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001991a  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001991f  xorps   xmm0, xmm0
0x140019922  movups  xmmword ptr [rbp+Src], xmm0
0x140019926  mov     r15, [rbp+arg_18]
0x14001992a  lea     rdx, [rbp+var_28]
0x14001992e  mov     rcx, r15
0x140019931  call    BoxReadHeader
0x140019936  mov     edi, eax
0x140019938  mov     ecx, eax
0x14001993a  test    eax, eax
0x14001993c  js      loc_140019C96
0x140019942  mov     rcx, [rbp+Src+8]; Src
0x140019946  test    rcx, rcx
0x140019949  jnz     short loc_140019955
0x14001994b  mov     edi, 8007139Fh
0x140019950  jmp     loc_140019C94
0x140019955  lea     rdx, [rbp+var_50]
0x140019959  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x14001995e  mov     edi, eax
0x140019960  mov     ecx, eax
0x140019962  mov     r12, [rbp+var_50]
0x140019966  test    eax, eax
0x140019968  js      loc_140019C96
0x14001996e  mov     rcx, [rbx+20h]
0x140019972  test    rcx, rcx
0x140019975  cmovz   rcx, rsi
0x140019979  lea     r9, [rbp+lpFileName]
0x14001997d  xor     r8d, r8d
0x140019980  mov     rdx, r12
0x140019983  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x140019988  mov     edi, eax
0x14001998a  mov     ecx, eax
0x14001998c  mov     r14, [rbp+lpFileName]
0x140019990  test    eax, eax
0x140019992  js      loc_140019C96
0x140019998  mov     rcx, r14; lpFileName
0x14001999b  call    cs:__imp_GetFileAttributesW
0x1400199a2  nop     dword ptr [rax+rax+00h]
0x1400199a7  mov     esi, eax
0x1400199a9  cmp     eax, 0FFFFFFFFh
0x1400199ac  jz      short loc_1400199B8
0x1400199ae  shr     esi, 4
0x1400199b1  not     esi
0x1400199b3  and     esi, 1
0x1400199b6  jmp     short loc_1400199BA
0x1400199b8  xor     esi, esi
0x1400199ba  xor     ecx, ecx
0x1400199bc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400199c1  xor     ecx, ecx
0x1400199c3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400199c8  cmp     dword ptr [rbx+28h], 1
0x1400199cc  jnz     loc_140019BB1
0x1400199d2  xor     esi, esi
0x1400199d4  cmp     [rbx+38h], esi
0x1400199d7  jnz     short loc_1400199F1
0x1400199d9  mov     rdx, r15; void *
0x1400199dc  mov     rcx, rbx; this
0x1400199df  call    ?PopulateWorkingDir@CPackageScenarioCtrl@@AEAAJPEAX@Z; CPackageScenarioCtrl::PopulateWorkingDir(void *)
0x1400199e4  mov     edi, eax
0x1400199e6  mov     ecx, eax
0x1400199e8  test    eax, eax
0x1400199ea  jns     short loc_140019A26
0x1400199ec  jmp     loc_140019C96
0x1400199f1  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x1400199f8  lea     rax, [r8-1]
0x1400199fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019a00  setnbe  al
0x140019a03  mov     rcx, rsi
0x140019a06  test    al, al
0x140019a08  cmovz   rcx, r8; hFile
0x140019a0c  lea     r9, aCpackagescenar_1; "CPackageScenarioCtrl::PopulateWorkingDi"...
0x140019a13  lea     r8, aSWorkingDirect; "%s: Working directory was preserved so "...
0x140019a1a  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140019a21  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140019a26  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140019a2d  lea     rax, [r8-1]
0x140019a31  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019a35  setnbe  al
0x140019a38  mov     rcx, rsi
0x140019a3b  test    al, al
0x140019a3d  cmovz   rcx, r8; hFile
0x140019a41  lea     r9, aCpackagescenar_1; "CPackageScenarioCtrl::PopulateWorkingDi"...
0x140019a48  lea     r8, aSSettingPredow; "%s: Setting PreDownload mode..."
0x140019a4f  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140019a56  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140019a5b  mov     ecx, [rbx+8]
0x140019a5e  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140019a63  mov     rdx, rax
0x140019a66  call    ?CreateOrOpenKey@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG@Z; CRegUtilT<ulong,CRegType,0,1>::CreateOrOpenKey(HKEY__ *,ushort const *)
0x140019a6b  mov     edi, eax
0x140019a6d  mov     ecx, eax
0x140019a6f  test    eax, eax
0x140019a71  js      loc_140019C96
0x140019a77  mov     ecx, [rbx+8]
0x140019a7a  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140019a7f  mov     rdx, rax
0x140019a82  mov     r9d, 1
0x140019a88  lea     r8, aPredownloadmod; "PreDownloadMode"
0x140019a8f  call    ?SetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1K@Z; CRegUtilT<ulong,CRegType,0,1>::SetValue(HKEY__ *,ushort const *,ushort const *,ulong)
0x140019a94  mov     edi, eax
0x140019a96  mov     ecx, eax
0x140019a98  test    eax, eax
0x140019a9a  js      loc_140019C96
0x140019aa0  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140019aa7  lea     rax, [r8-1]
0x140019aab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019aaf  setnbe  al
0x140019ab2  mov     rcx, rsi
0x140019ab5  test    al, al
0x140019ab7  cmovz   rcx, r8; hFile
0x140019abb  lea     r9, aCpackagescenar_1; "CPackageScenarioCtrl::PopulateWorkingDi"...
0x140019ac2  lea     r8, aSWritingProces; "%s: Writing ProcessId value..."
0x140019ac9  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140019ad0  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140019ad5  call    cs:__imp_GetCurrentProcessId
0x140019adc  nop     dword ptr [rax+rax+00h]
0x140019ae1  mov     r9d, eax
0x140019ae4  mov     ecx, [rbx+8]
0x140019ae7  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140019aec  mov     rdx, rax
0x140019aef  lea     r8, aProcessid; "ProcessId"
0x140019af6  call    ?SetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1K@Z; CRegUtilT<ulong,CRegType,0,1>::SetValue(HKEY__ *,ushort const *,ushort const *,ulong)
0x140019afb  mov     edi, eax
0x140019afd  mov     ecx, eax
0x140019aff  test    eax, eax
0x140019b01  js      loc_140019C96
0x140019b07  mov     ecx, [rbx+8]
0x140019b0a  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140019b0f  mov     rdx, rax
0x140019b12  call    ?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z; CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)
0x140019b17  mov     edi, eax
0x140019b19  mov     ecx, eax
0x140019b1b  test    eax, eax
0x140019b1d  js      loc_140019C96
0x140019b23  lea     rcx, [rbp+var_40]; this
0x140019b27  call    ?GenerateBoxHash@ScenarioCtrlHelpers@@YAJPEAPEAG@Z; ScenarioCtrlHelpers::GenerateBoxHash(ushort * *)
0x140019b2c  mov     edi, eax
0x140019b2e  mov     ecx, eax
0x140019b30  mov     r13, [rbp+var_40]
0x140019b34  test    eax, eax
0x140019b36  js      loc_140019C96
0x140019b3c  mov     ecx, [rbx+8]
0x140019b3f  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140019b44  mov     rdx, rax
0x140019b47  mov     r9, r13
0x140019b4a  call    ?SetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG11@Z; CRegUtilT<ushort *,CRegType,0,1>::SetValue(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x140019b4f  mov     edi, eax
0x140019b51  mov     ecx, eax
0x140019b53  test    eax, eax
0x140019b55  js      loc_140019C96
0x140019b5b  mov     ecx, [rbx+8]
0x140019b5e  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140019b63  mov     rdx, rax
0x140019b66  call    ?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z; CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)
0x140019b6b  mov     edi, eax
0x140019b6d  mov     ecx, eax
0x140019b6f  test    eax, eax
0x140019b71  js      loc_140019C96
0x140019b77  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140019b7e  lea     rax, [r8-1]
0x140019b82  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019b86  setnbe  al
0x140019b89  mov     rcx, rsi
0x140019b8c  test    al, al
0x140019b8e  cmovz   rcx, r8; hFile
0x140019b92  lea     r9, aCpackagescenar_1; "CPackageScenarioCtrl::PopulateWorkingDi"...
0x140019b99  lea     r8, aSFileHashStore; "%s: File hash stored!"
0x140019ba0  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140019ba7  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140019bac  jmp     loc_140019CD8
0x140019bb1  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140019bb8  lea     rax, [r8-1]
0x140019bbc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019bc0  setnbe  al
0x140019bc3  xor     ecx, ecx
0x140019bc5  test    al, al
0x140019bc7  cmovz   rcx, r8; hFile
0x140019bcb  lea     r9, aCpackagescenar_1; "CPackageScenarioCtrl::PopulateWorkingDi"...
0x140019bd2  lea     r8, aSClearingPredo; "%s: Clearing PreDownload mode..."
0x140019bd9  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140019be0  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140019be5  mov     ecx, [rbx+8]
0x140019be8  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140019bed  mov     rdx, rax
0x140019bf0  lea     r8, aPredownloadmod; "PreDownloadMode"
0x140019bf7  call    ?DeleteValueIfExists@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1@Z; CRegUtilT<ulong,CRegType,0,1>::DeleteValueIfExists(HKEY__ *,ushort const *,ushort const *)
0x140019bfc  mov     edi, eax
0x140019bfe  mov     ecx, eax
0x140019c00  test    eax, eax
0x140019c02  jns     short loc_140019C0B
0x140019c04  xor     esi, esi
0x140019c06  jmp     loc_140019C96
0x140019c0b  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140019c12  lea     rax, [r8-1]
0x140019c16  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019c1a  setnbe  al
0x140019c1d  xor     ecx, ecx
0x140019c1f  test    al, al
0x140019c21  cmovz   rcx, r8; hFile
0x140019c25  lea     r9, aCpackagescenar_1; "CPackageScenarioCtrl::PopulateWorkingDi"...
0x140019c2c  lea     r8, aSWritingProces; "%s: Writing ProcessId value..."
0x140019c33  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140019c3a  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140019c3f  call    cs:__imp_GetCurrentProcessId
0x140019c46  nop     dword ptr [rax+rax+00h]
0x140019c4b  mov     r9d, eax
0x140019c4e  mov     ecx, [rbx+8]
0x140019c51  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140019c56  mov     rdx, rax
0x140019c59  lea     r8, aProcessid; "ProcessId"
0x140019c60  call    ?SetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1K@Z; CRegUtilT<ulong,CRegType,0,1>::SetValue(HKEY__ *,ushort const *,ushort const *,ulong)
0x140019c65  mov     edi, eax
0x140019c67  mov     ecx, eax
0x140019c69  test    eax, eax
0x140019c6b  js      short loc_140019C04
0x140019c6d  mov     ecx, [rbx+8]
0x140019c70  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x140019c75  mov     rdx, rax
0x140019c78  call    ?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z; CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)
0x140019c7d  mov     edi, eax
0x140019c7f  mov     ecx, eax
0x140019c81  test    eax, eax
0x140019c83  js      loc_140019C04
0x140019c89  test    esi, esi
0x140019c8b  jnz     short loc_140019CD6
0x140019c8d  mov     edi, 8024200Dh
0x140019c92  xor     esi, esi
0x140019c94  mov     ecx, edi
0x140019c96  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140019c9b  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140019ca2  lea     rax, [r8-1]
0x140019ca6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019caa  setnbe  al
0x140019cad  mov     rcx, rsi
0x140019cb0  test    al, al
0x140019cb2  cmovz   rcx, r8; hFile
  ... truncated ...
```
