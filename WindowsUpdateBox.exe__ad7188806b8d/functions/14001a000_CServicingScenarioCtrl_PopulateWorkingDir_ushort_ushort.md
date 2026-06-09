# CServicingScenarioCtrl::PopulateWorkingDir(ushort * *,ushort * *)

- ea: `0x14001a000`
- end: `0x14001a413`
- name: `?PopulateWorkingDir@CServicingScenarioCtrl@@UEAAJPEAPEAG0@Z`
- size: `1043`
- prototype: `__int64 __fastcall(CServicingScenarioCtrl *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400076c8`
- `0x140007cb0`
- `0x140008434`
- `0x14000a564`
- `0x14000e2a0`
- `0x14000e878`
- `0x140010148`
- `0x1400135b8`
- `0x140016bb4`
- `0x140019db4`
- `0x14001a000`
- `0x14001dedc`
- `0x14001dfc8`
- `0x140053ba0`
- `0x140054ac8`
- `0x140054bd4`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14001a1fb`
- `KERNEL32!GetCurrentProcessId` at `0x14001a1fb`
- `KERNEL32!HeapFree` at `0x14001a385`
- `KERNEL32!HeapFree` at `0x14001a3b3`
- `KERNEL32!HeapFree` at `0x14001a3e1`
- `KERNEL32!HeapFree` at `0x14001a385`
- `KERNEL32!HeapFree` at `0x14001a3b3`
- `KERNEL32!HeapFree` at `0x14001a3e1`
- `KERNEL32!GetProcessHeap` at `0x14001a370`
- `KERNEL32!GetProcessHeap` at `0x14001a39e`
- `KERNEL32!GetProcessHeap` at `0x14001a3cc`
- `KERNEL32!GetProcessHeap` at `0x14001a370`
- `KERNEL32!GetProcessHeap` at `0x14001a39e`
- `KERNEL32!GetProcessHeap` at `0x14001a3cc`
- `KERNEL32!GetFileAttributesW` at `0x14001a16c`
- `KERNEL32!GetFileAttributesW` at `0x14001a16c`

## string_xrefs

- `0x14001a084`: `Opening Box: [%s]`
- `0x14001a0d9`: `Reading Box header...`
- `0x14001a2f7`: `%s: Working directory was preserved so it is already populated.`
- `0x14001a1cc`: `%s: Writing ProcessId value...`
- `0x14001a215`: `ProcessId`

## pseudocode

```c
__int64 __fastcall CServicingScenarioCtrl::PopulateWorkingDir(
        CServicingScenarioCtrl *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  LPCWSTR v5; // rsi
  __int64 v6; // r15
  void *v7; // r14
  __int64 v8; // rcx
  int Header; // edi
  HANDLE v10; // rcx
  __int64 v11; // rcx
  HANDLE v12; // rcx
  __int64 v13; // rcx
  HANDLE v14; // rcx
  __int64 SetupVolatileRegKey; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned __int16 **v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rcx
  HANDLE v28; // rcx
  HANDLE v29; // rcx
  HANDLE v30; // rcx
  unsigned __int16 *v31; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v33; // rax
  LPCWSTR lpFileName; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v36[3]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v37[16]; // [rsp+58h] [rbp-28h] BYREF
  void *Src[2]; // [rsp+68h] [rbp-18h]
  void *v40; // [rsp+D8h] [rbp+58h] BYREF

  v36[1] = -2;
  v36[2] = 0;
  v5 = 0;
  lpFileName = 0;
  v6 = 0;
  v36[0] = 0;
  v7 = 0;
  v40 = 0;
  if ( !a2 || !a3 )
  {
    v8 = 2147942487LL;
    Header = -2147024809;
LABEL_29:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    v28 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v28 = g_shLogFile;
    OutputMsg(v28, g_shLogEvent, L"%s: Error = 0x%X", L"CServicingScenarioCtrl::PopulateWorkingDir", Header);
    goto LABEL_38;
  }
  v10 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v10 = g_shLogFile;
  OutputMsg(v10, g_shLogEvent, L"Opening Box: [%s]", *((_QWORD *)this + 2));
  v11 = *((_QWORD *)this + 2);
  if ( !v11 )
    v11 = 0;
  Header = BoxOpenFromPath(v11, &v40);
  v8 = (unsigned int)Header;
  if ( Header < 0 )
  {
    v7 = v40;
    goto LABEL_29;
  }
  v12 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v12 = g_shLogFile;
  OutputMsg(v12, g_shLogEvent, L"Reading Box header...");
  *(_OWORD *)Src = 0;
  v7 = v40;
  Header = BoxReadHeader(v40, v37);
  v8 = (unsigned int)Header;
  if ( Header < 0 )
    goto LABEL_29;
  if ( !Src[1] )
  {
    Header = -2147019873;
    v8 = 2147947423LL;
    goto LABEL_29;
  }
  Header = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(Src[1]);
  v8 = (unsigned int)Header;
  if ( Header < 0 )
    goto LABEL_29;
  v13 = *((_QWORD *)this + 4);
  if ( !v13 )
    v13 = 0;
  Header = CMiscHelpersT<CEmptyType>::CombinePath(v13, 0, 0, &lpFileName);
  v8 = (unsigned int)Header;
  v5 = lpFileName;
  if ( Header < 0 )
    goto LABEL_29;
  GetFileAttributesW(lpFileName);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( *((_DWORD *)this + 3) )
  {
    v29 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v29 = g_shLogFile;
    OutputMsg(
      v29,
      g_shLogEvent,
      L"%s: Working directory was preserved so it is already populated.",
      L"CServicingScenarioCtrl::PopulateWorkingDir");
  }
  else
  {
    Header = CServicingScenarioCtrl::PopulateWorkingDir(this, v7);
    v8 = (unsigned int)Header;
    if ( Header < 0 )
      goto LABEL_29;
  }
  v14 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v14 = g_shLogFile;
  OutputMsg(v14, g_shLogEvent, L"%s: Writing ProcessId value...", L"CServicingScenarioCtrl::PopulateWorkingDir");
  SetupVolatileRegKey = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
  Header = CRegUtilT<unsigned long,CRegType,0,1>::CreateOrOpenKey(v16, SetupVolatileRegKey);
  v8 = (unsigned int)Header;
  if ( Header < 0 )
    goto LABEL_29;
  GetCurrentProcessId();
  v17 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
  Header = CRegUtilT<unsigned long,CRegType,0,1>::SetValue(v18, v17, L"ProcessId", v19);
  v8 = (unsigned int)Header;
  if ( Header < 0 )
    goto LABEL_29;
  v20 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
  Header = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v21, v20);
  v8 = (unsigned int)Header;
  if ( Header < 0 )
    goto LABEL_29;
  Header = ScenarioCtrlHelpers::GenerateBoxHash((ScenarioCtrlHelpers *)v36, v22);
  v8 = (unsigned int)Header;
  v6 = v36[0];
  if ( Header < 0 )
    goto LABEL_29;
  v23 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
  Header = CRegUtilT<unsigned short *,CRegType,0,1>::SetValue(v24, v23, v25, v6);
  v8 = (unsigned int)Header;
  if ( Header < 0 )
    goto LABEL_29;
  v26 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
  Header = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v27, v26);
  v8 = (unsigned int)Header;
  if ( Header < 0 )
    goto LABEL_29;
  v30 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v30 = g_shLogFile;
  OutputMsg(v30, g_shLogEvent, L"%s: File hash stored!", L"CServicingScenarioCtrl::PopulateWorkingDir");
  v31 = (unsigned __int16 *)v5;
  v5 = 0;
  *a2 = v31;
  *a3 = 0;
LABEL_38:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)Header);
  if ( v7 )
    FreeBoxFileHandle(v7);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)Header;
}

```

## disassembly

```asm
0x14001a000  mov     rax, rsp
0x14001a003  mov     [rax+10h], rdx
0x14001a007  push    rbp
0x14001a008  push    rsi
0x14001a009  push    rdi
0x14001a00a  push    r12
0x14001a00c  push    r13
0x14001a00e  push    r14
0x14001a010  push    r15
0x14001a012  mov     rbp, rsp
0x14001a015  sub     rsp, 80h
0x14001a01c  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x14001a024  mov     [rax+8], rbx
0x14001a028  mov     r12, r8
0x14001a02b  mov     rbx, rcx
0x14001a02e  xor     edi, edi
0x14001a030  mov     [rbp+var_30], rdi
0x14001a034  mov     r13d, edi
0x14001a037  mov     [rbp+var_50], rdi
0x14001a03b  mov     esi, edi
0x14001a03d  mov     [rbp+lpFileName], rdi
0x14001a041  mov     r15d, edi
0x14001a044  mov     [rbp+var_40], rdi
0x14001a048  mov     r14d, edi
0x14001a04b  mov     [rbp+arg_18], rdi
0x14001a04f  test    rdx, rdx
0x14001a052  jnz     short loc_14001A060
0x14001a054  mov     ecx, 80070057h
0x14001a059  mov     edi, ecx
0x14001a05b  jmp     loc_14001A28F
0x14001a060  test    r12, r12
0x14001a063  jz      short loc_14001A054
0x14001a065  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a06c  lea     rax, [r8-1]
0x14001a070  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a074  setnbe  al
0x14001a077  mov     rcx, rdi
0x14001a07a  test    al, al
0x14001a07c  cmovz   rcx, r8; hFile
0x14001a080  mov     r9, [rbx+10h]
0x14001a084  lea     r8, aOpeningBoxS; "Opening Box: [%s]"
0x14001a08b  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a092  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a097  mov     rcx, [rbx+10h]
0x14001a09b  test    rcx, rcx
0x14001a09e  cmovz   rcx, rdi
0x14001a0a2  lea     rdx, [rbp+arg_18]
0x14001a0a6  call    BoxOpenFromPath
0x14001a0ab  mov     edi, eax
0x14001a0ad  mov     ecx, eax
0x14001a0af  xor     edx, edx
0x14001a0b1  test    eax, eax
0x14001a0b3  jns     short loc_14001A0BE
0x14001a0b5  mov     r14, [rbp+arg_18]
0x14001a0b9  jmp     loc_14001A28F
0x14001a0be  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a0c5  lea     rax, [r8-1]
0x14001a0c9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a0cd  setnbe  al
0x14001a0d0  mov     rcx, rdx
0x14001a0d3  test    al, al
0x14001a0d5  cmovz   rcx, r8; hFile
0x14001a0d9  lea     r8, aReadingBoxHead; "Reading Box header..."
0x14001a0e0  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a0e7  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a0ec  xorps   xmm0, xmm0
0x14001a0ef  movups  xmmword ptr [rbp+Src], xmm0
0x14001a0f3  mov     r14, [rbp+arg_18]
0x14001a0f7  lea     rdx, [rbp+var_28]
0x14001a0fb  mov     rcx, r14
0x14001a0fe  call    BoxReadHeader
0x14001a103  mov     edi, eax
0x14001a105  mov     ecx, eax
0x14001a107  test    eax, eax
0x14001a109  js      loc_14001A28F
0x14001a10f  mov     rcx, [rbp+Src+8]; Src
0x14001a113  test    rcx, rcx
0x14001a116  jnz     short loc_14001A124
0x14001a118  mov     edi, 8007139Fh
0x14001a11d  mov     ecx, edi
0x14001a11f  jmp     loc_14001A28F
0x14001a124  lea     rdx, [rbp+var_50]
0x14001a128  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x14001a12d  mov     edi, eax
0x14001a12f  mov     ecx, eax
0x14001a131  xor     eax, eax
0x14001a133  mov     r13, [rbp+var_50]
0x14001a137  test    ecx, ecx
0x14001a139  js      loc_14001A28F
0x14001a13f  mov     rcx, [rbx+20h]
0x14001a143  test    rcx, rcx
0x14001a146  cmovz   rcx, rax
0x14001a14a  lea     r9, [rbp+lpFileName]
0x14001a14e  xor     r8d, r8d
0x14001a151  mov     rdx, r13
0x14001a154  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001a159  mov     edi, eax
0x14001a15b  mov     ecx, eax
0x14001a15d  mov     rsi, [rbp+lpFileName]
0x14001a161  test    eax, eax
0x14001a163  js      loc_14001A28F
0x14001a169  mov     rcx, rsi; lpFileName
0x14001a16c  call    cs:__imp_GetFileAttributesW
0x14001a173  nop     dword ptr [rax+rax+00h]
0x14001a178  xor     ecx, ecx
0x14001a17a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001a17f  xor     ecx, ecx
0x14001a181  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001a186  xor     edi, edi
0x14001a188  cmp     [rbx+0Ch], edi
0x14001a18b  jnz     loc_14001A2D5
0x14001a191  mov     rdx, r14; void *
0x14001a194  mov     rcx, rbx; this
0x14001a197  call    ?PopulateWorkingDir@CServicingScenarioCtrl@@AEAAJPEAX@Z; CServicingScenarioCtrl::PopulateWorkingDir(void *)
0x14001a19c  mov     edi, eax
0x14001a19e  mov     ecx, eax
0x14001a1a0  test    eax, eax
0x14001a1a2  js      loc_14001A28F
0x14001a1a8  xor     edi, edi
0x14001a1aa  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a1b1  lea     rax, [r8-1]
0x14001a1b5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a1b9  setnbe  al
0x14001a1bc  mov     rcx, rdi
0x14001a1bf  test    al, al
0x14001a1c1  cmovz   rcx, r8; hFile
0x14001a1c5  lea     r9, aCservicingscen_2; "CServicingScenarioCtrl::PopulateWorking"...
0x14001a1cc  lea     r8, aSWritingProces; "%s: Writing ProcessId value..."
0x14001a1d3  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a1da  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a1df  mov     ecx, [rbx+8]
0x14001a1e2  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a1e7  mov     rdx, rax
0x14001a1ea  call    ?CreateOrOpenKey@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG@Z; CRegUtilT<ulong,CRegType,0,1>::CreateOrOpenKey(HKEY__ *,ushort const *)
0x14001a1ef  mov     edi, eax
0x14001a1f1  mov     ecx, eax
0x14001a1f3  test    eax, eax
0x14001a1f5  js      loc_14001A28F
0x14001a1fb  call    cs:__imp_GetCurrentProcessId
0x14001a202  nop     dword ptr [rax+rax+00h]
0x14001a207  mov     r9d, eax
0x14001a20a  mov     ecx, [rbx+8]
0x14001a20d  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a212  mov     rdx, rax
0x14001a215  lea     r8, aProcessid; "ProcessId"
0x14001a21c  call    ?SetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1K@Z; CRegUtilT<ulong,CRegType,0,1>::SetValue(HKEY__ *,ushort const *,ushort const *,ulong)
0x14001a221  mov     edi, eax
0x14001a223  mov     ecx, eax
0x14001a225  test    eax, eax
0x14001a227  js      short loc_14001A28F
0x14001a229  mov     ecx, [rbx+8]
0x14001a22c  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a231  mov     rdx, rax
0x14001a234  call    ?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z; CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)
0x14001a239  mov     edi, eax
0x14001a23b  mov     ecx, eax
0x14001a23d  test    eax, eax
0x14001a23f  js      short loc_14001A28F
0x14001a241  lea     rcx, [rbp+var_40]; this
0x14001a245  call    ?GenerateBoxHash@ScenarioCtrlHelpers@@YAJPEAPEAG@Z; ScenarioCtrlHelpers::GenerateBoxHash(ushort * *)
0x14001a24a  mov     edi, eax
0x14001a24c  mov     ecx, eax
0x14001a24e  mov     r15, [rbp+var_40]
0x14001a252  test    eax, eax
0x14001a254  js      short loc_14001A28F
0x14001a256  mov     ecx, [rbx+8]
0x14001a259  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a25e  mov     rdx, rax
0x14001a261  mov     r9, r15
0x14001a264  call    ?SetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG11@Z; CRegUtilT<ushort *,CRegType,0,1>::SetValue(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x14001a269  mov     edi, eax
0x14001a26b  mov     ecx, eax
0x14001a26d  test    eax, eax
0x14001a26f  js      short loc_14001A28F
0x14001a271  mov     ecx, [rbx+8]
0x14001a274  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a279  mov     rdx, rax
0x14001a27c  call    ?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z; CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)
0x14001a281  mov     edi, eax
0x14001a283  mov     ecx, eax
0x14001a285  xor     ebx, ebx
0x14001a287  test    eax, eax
0x14001a289  jns     loc_14001A30F
0x14001a28f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001a294  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a29b  lea     rax, [r8-1]
0x14001a29f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a2a3  setnbe  al
0x14001a2a6  xor     r12d, r12d
0x14001a2a9  mov     ecx, r12d
0x14001a2ac  test    al, al
0x14001a2ae  cmovz   rcx, r8; hFile
0x14001a2b2  mov     [rsp+80h+var_60], edi
0x14001a2b6  lea     r9, aCservicingscen_2; "CServicingScenarioCtrl::PopulateWorking"...
0x14001a2bd  lea     r8, aSError0xX; "%s: Error = 0x%X"
0x14001a2c4  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a2cb  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a2d0  jmp     loc_14001A355
0x14001a2d5  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a2dc  lea     rax, [r8-1]
0x14001a2e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a2e4  setnbe  al
0x14001a2e7  mov     rcx, rdi
0x14001a2ea  test    al, al
0x14001a2ec  cmovz   rcx, r8; hFile
0x14001a2f0  lea     r9, aCservicingscen_2; "CServicingScenarioCtrl::PopulateWorking"...
0x14001a2f7  lea     r8, aSWorkingDirect; "%s: Working directory was preserved so "...
0x14001a2fe  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a305  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a30a  jmp     loc_14001A1AA
0x14001a30f  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a316  lea     rax, [r8-1]
0x14001a31a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a31e  setnbe  al
0x14001a321  mov     rcx, rbx
0x14001a324  test    al, al
0x14001a326  cmovz   rcx, r8; hFile
0x14001a32a  lea     r9, aCservicingscen_2; "CServicingScenarioCtrl::PopulateWorking"...
0x14001a331  lea     r8, aSFileHashStore; "%s: File hash stored!"
0x14001a338  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a33f  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a344  mov     rax, rsi
0x14001a347  mov     rsi, rbx
0x14001a34a  mov     rcx, [rbp+arg_8]
0x14001a34e  mov     [rcx], rax
0x14001a351  mov     [r12], rbx
0x14001a355  mov     ecx, edi
0x14001a357  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001a35c  nop
0x14001a35d  test    r14, r14
0x14001a360  jz      short loc_14001A36B
0x14001a362  mov     rcx, r14; lpMem
0x14001a365  call    FreeBoxFileHandle
0x14001a36a  nop
0x14001a36b  test    r15, r15
0x14001a36e  jz      short loc_14001A399
0x14001a370  call    cs:__imp_GetProcessHeap
0x14001a377  nop     dword ptr [rax+rax+00h]
0x14001a37c  mov     rcx, rax; hHeap
0x14001a37f  lea     r8, [r15-4]; lpMem
0x14001a383  xor     edx, edx; dwFlags
0x14001a385  call    cs:__imp_HeapFree
0x14001a38c  nop     dword ptr [rax+rax+00h]
0x14001a391  xor     ecx, ecx
0x14001a393  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001a398  nop
0x14001a399  test    rsi, rsi
0x14001a39c  jz      short loc_14001A3C7
0x14001a39e  call    cs:__imp_GetProcessHeap
0x14001a3a5  nop     dword ptr [rax+rax+00h]
0x14001a3aa  mov     rcx, rax; hHeap
0x14001a3ad  lea     r8, [rsi-4]; lpMem
0x14001a3b1  xor     edx, edx; dwFlags
0x14001a3b3  call    cs:__imp_HeapFree
0x14001a3ba  nop     dword ptr [rax+rax+00h]
0x14001a3bf  xor     ecx, ecx
0x14001a3c1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001a3c6  nop
0x14001a3c7  test    r13, r13
0x14001a3ca  jz      short loc_14001A3F5
0x14001a3cc  call    cs:__imp_GetProcessHeap
0x14001a3d3  nop     dword ptr [rax+rax+00h]
0x14001a3d8  mov     rcx, rax; hHeap
0x14001a3db  lea     r8, [r13-4]; lpMem
0x14001a3df  xor     edx, edx; dwFlags
0x14001a3e1  call    cs:__imp_HeapFree
0x14001a3e8  nop     dword ptr [rax+rax+00h]
0x14001a3ed  xor     ecx, ecx
0x14001a3ef  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001a3f4  nop
0x14001a3f5  mov     eax, edi
0x14001a3f7  mov     rbx, [rsp+80h+arg_0]
0x14001a3ff  add     rsp, 80h
0x14001a406  pop     r15
0x14001a408  pop     r14
0x14001a40a  pop     r13
0x14001a40c  pop     r12
0x14001a40e  pop     rdi
0x14001a40f  pop     rsi
0x14001a410  pop     rbp
0x14001a411  retn
```
