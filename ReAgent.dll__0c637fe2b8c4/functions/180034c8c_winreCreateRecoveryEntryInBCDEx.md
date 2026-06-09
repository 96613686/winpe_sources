# winreCreateRecoveryEntryInBCDEx

- ea: `0x180034c8c`
- end: `0x1800351fc`
- name: `winreCreateRecoveryEntryInBCDEx`
- size: `1392`
- prototype: `__int64 __fastcall(void *, struct PartitionNode *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800342f4`
- `0x180034aa4`

## callees

- `0x1800059fc`
- `0x18000c658`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18000ff68`
- `0x1800333b4`
- `0x180033cb8`
- `0x180034c8c`
- `0x18004e19c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800351cf`
- `ntdll!RtlNtStatusToDosError` at `0x1800351cf`
- `KERNEL32!HeapFree` at `0x180035187`
- `KERNEL32!HeapFree` at `0x180035187`
- `KERNEL32!GetProcessHeap` at `0x180035179`
- `KERNEL32!GetProcessHeap` at `0x180035179`
- `bcd!BcdSetElementData` at `0x180034eeb`
- `bcd!BcdSetElementData` at `0x180034f22`
- `bcd!BcdSetElementData` at `0x180034f45`
- `bcd!BcdSetElementData` at `0x180034fd3`
- `bcd!BcdSetElementData` at `0x180034ffa`
- `bcd!BcdSetElementData` at `0x180035021`
- `bcd!BcdSetElementData` at `0x180035055`
- `bcd!BcdSetElementData` at `0x18003506e`
- `bcd!BcdSetElementData` at `0x18003509f`
- `bcd!BcdSetElementData` at `0x1800350d8`
- `bcd!BcdSetElementData` at `0x180035111`
- `bcd!BcdSetElementData` at `0x18003514d`
- `bcd!BcdSetElementData` at `0x180034eeb`
- `bcd!BcdSetElementData` at `0x180034f22`
- `bcd!BcdSetElementData` at `0x180034f45`
- `bcd!BcdSetElementData` at `0x180034fd3`
- `bcd!BcdSetElementData` at `0x180034ffa`
- `bcd!BcdSetElementData` at `0x180035021`
- `bcd!BcdSetElementData` at `0x180035055`
- `bcd!BcdSetElementData` at `0x18003506e`
- `bcd!BcdSetElementData` at `0x18003509f`
- `bcd!BcdSetElementData` at `0x1800350d8`
- `bcd!BcdSetElementData` at `0x180035111`
- `bcd!BcdSetElementData` at `0x18003514d`
- `bcd!BcdCreateObject` at `0x180034d32`
- `bcd!BcdCreateObject` at `0x180034d32`
- `bcd!BcdCloseObject` at `0x180035197`
- `bcd!BcdCloseObject` at `0x180035197`
- `bcd!BcdQueryObject` at `0x180034d65`
- `bcd!BcdQueryObject` at `0x180034d65`

## string_xrefs

- `0x180034dab`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180034dfc`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180034ea5`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180034f82`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180034d3e`: `BcdCreateObject failed: 0x%x`
- `0x180034da4`: `failed to create boot path`
- `0x180034dba`: `winreCreateRecoveryEntryInBCDEx %s (0x%x) in file %S line %d`
- `0x180034e0b`: `winreCreateRecoveryEntryInBCDEx %s (0x%x) in file %S line %d`
- `0x180034ec5`: `winreCreateRecoveryEntryInBCDEx %s (0x%x) in file %S line %d`
- `0x180034fa2`: `winreCreateRecoveryEntryInBCDEx %s (0x%x) in file %S line %d`
- `0x180034df5`: `failed to create ram disk options`
- `0x180034e64`: `failed to concatenate winre.wim path`
- `0x180034f5f`: `\windows\system32\winload.efi`
- `0x180034f58`: `\windows\system32\winload.exe`
- `0x180034f96`: `failed to get the length of loader relative path`
- `0x1800351bc`: `winreCreateRecoveryEntryInBCDExfailed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreCreateRecoveryEntryInBCDEx(void *a1, struct PartitionNode *a2, __int64 a3, _OWORD *a4)
{
  int v7; // edi
  int v9; // eax
  NTSTATUS v10; // ebx
  int v11; // eax
  const wchar_t *v12; // r8
  unsigned int v13; // eax
  const wchar_t *v14; // r8
  unsigned int BcdDeviceObject; // eax
  void *v16; // r14
  int v17; // eax
  const wchar_t *v18; // rdx
  int IsEfi; // eax
  const unsigned __int16 *v20; // r11
  int v21; // eax
  __int64 v22; // r11
  unsigned __int16 v23; // si
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // r9
  int v29; // eax
  HANDLE ProcessHeap; // rax
  int v32; // [rsp+28h] [rbp-D8h]
  int v33; // [rsp+28h] [rbp-D8h]
  unsigned int *v34; // [rsp+28h] [rbp-D8h]
  unsigned int v35; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v41[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID v43; // [rsp+70h] [rbp-90h] BYREF
  __int128 v44; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v45[304]; // [rsp+90h] [rbp-70h] BYREF

  v38 = 0;
  v7 = 0;
  v44 = 0;
  v43 = 0;
  memset_0(v45, 0, 0x25Cu);
  lpMem = 0;
  v35 = 0;
  v37 = 0;
  v39 = 1;
  v40 = 0;
  *a4 = 0;
  v41[0] = 1;
  v41[1] = 270532611;
  v9 = BcdCreateObject(a1, 0, v41, &v38);
  v10 = v9;
  if ( v9 < 0 )
  {
    UnattendLogW(1, L"BcdCreateObject failed: 0x%x", (unsigned int)v9);
    goto LABEL_47;
  }
  v11 = BcdQueryObject(v38, 0, 0, &v44);
  v10 = v11;
  if ( v11 < 0 )
  {
    UnattendLogW(1, L"BcdQueryObject failed: 0x%x", (unsigned int)v11);
    goto LABEL_47;
  }
  v7 = StringCchPrintfW(v45, 0x12Eu, L"%s\\", L"\\Recovery\\WindowsRE");
  if ( v7 < 0 )
  {
    v32 = 1216;
    v12 = L"failed to create boot path";
LABEL_8:
    UnattendLogW(
      2,
      L"winreCreateRecoveryEntryInBCDEx %s (0x%x) in file %S line %d",
      v12,
      (unsigned int)v7,
      "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
      v32);
    v7 = (unsigned __int16)v7;
    goto LABEL_47;
  }
  v13 = winreCreateRamdiskOptions(a1, a2, v45, &v43);
  v7 = v13;
  if ( v13 )
  {
    v33 = 1223;
    v14 = L"failed to create ram disk options";
LABEL_11:
    UnattendLogW(
      2,
      L"winreCreateRecoveryEntryInBCDEx %s (0x%x) in file %S line %d",
      v14,
      v13,
      "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
      v33);
    goto LABEL_47;
  }
  v13 = winreAddTrailingBackslash(v45);
  v7 = v13;
  if ( v13 )
  {
    v33 = 1230;
    v14 = L"failed to add trailing back slash";
    goto LABEL_11;
  }
  v7 = StringCchCatW(v45, 0x12Eu, L"Winre.wim");
  if ( v7 < 0 )
  {
    v32 = 1231;
    v12 = L"failed to concatenate winre.wim path";
    goto LABEL_8;
  }
  BcdDeviceObject = winreMakeBcdDeviceObject(4u, a2, v45, &v43, (struct _BCDE_DEVICE **)&lpMem, &v35);
  v16 = lpMem;
  v7 = BcdDeviceObject;
  if ( BcdDeviceObject )
  {
    LODWORD(v34) = 1238;
    UnattendLogW(
      2,
      L"winreCreateRecoveryEntryInBCDEx %s (0x%x) in file %S line %d",
      L"failed to make bcd device object",
      BcdDeviceObject,
      "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
      v34);
    goto LABEL_45;
  }
  v17 = BcdSetElementData(v38, 285212673, lpMem, v35);
  v10 = v17;
  if ( v17 < 0 )
    goto LABEL_19;
  v17 = BcdSetElementData(v38, 553648129, v16, v35);
  v10 = v17;
  if ( v17 < 0 )
    goto LABEL_19;
  v17 = BcdSetElementData(v38, 570425346, L"\\windows", 20);
  v10 = v17;
  if ( v17 < 0 )
    goto LABEL_19;
  IsEfi = Utils::IsEfi();
  v20 = L"\\windows\\system32\\winload.efi";
  if ( !IsEfi )
    v20 = L"\\windows\\system32\\winload.exe";
  v21 = StringCchLengthW(v20, 0x12Eu, &v37);
  v23 = v21;
  if ( v21 < 0 )
  {
    LODWORD(v34) = 1283;
    UnattendLogW(
      2,
      L"winreCreateRecoveryEntryInBCDEx %s (0x%x) in file %S line %d",
      L"failed to get the length of loader relative path",
      (unsigned int)v21,
      "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
      v34);
    v7 = v23;
    goto LABEL_45;
  }
  v17 = BcdSetElementData(v38, 301989890, v22, (unsigned int)(2 * v37 + 2));
  v10 = v17;
  if ( v17 < 0 || (v17 = BcdSetElementData(v38, 301989892, L"Windows Recovery Environment", 60), v10 = v17, v17 < 0) )
  {
LABEL_19:
    v18 = L"BcdSetElementData failed: 0x%x";
  }
  else
  {
    v17 = BcdSetElementData(v38, 335544326, &GUID_BOOT_LOADER_SETTINGS_GROUP, 16);
    v10 = v17;
    if ( v17 >= 0 )
    {
      v42 = 0;
      BcdSetElementData(v38, 620757024, &v42, 8);
      v24 = BcdSetElementData(v38, 637534242, &v39, 2);
      if ( v24 < 0 )
        UnattendLogW(2, L"BcdSetElementData failed: 0x%x", (unsigned int)v24);
      v25 = BcdSetElementData(v38, 1174405136, &v39, 2);
      if ( v25 < 0 )
        UnattendLogW(2, L"BcdSetElementData failed: 0x%x", (unsigned int)v25);
      v40 = 1;
      v26 = BcdSetElementData(v38, 620757186, &v40, 8);
      if ( v26 < 0 )
        UnattendLogW(2, L"BcdSetElementData failed: 0x%x", (unsigned int)v26);
      v40 = 3;
      v27 = BcdSetElementData(v38, 352321637, &v40, 8);
      if ( v27 < 0 )
        UnattendLogW(2, L"BcdSetElementData failed: 0x%x", (unsigned int)v27);
      v28 = -1;
      do
        ++v28;
      while ( *(_WORD *)(a3 + 2 * v28) );
      v29 = BcdSetElementData(v38, 301989893, a3, (unsigned int)(2 * v28));
      v10 = v29;
      if ( v29 >= 0 )
        *a4 = v44;
      else
        UnattendLogW(2, L"BcdSetElementData failed: 0x%x", (unsigned int)v29);
      goto LABEL_45;
    }
    v18 = L"BcdSetElementData(BCDE_LIBRARY_TYPE_INHERIT) failed: 0x%x";
  }
  UnattendLogW(1, v18, (unsigned int)v17);
LABEL_45:
  if ( v16 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
  }
LABEL_47:
  if ( v38 )
  {
    BcdCloseObject();
    v38 = 0;
  }
  if ( v10 < 0 )
  {
    if ( !ReAgentError )
      ReAgentError = 7;
    UnattendLogW(2, L"winreCreateRecoveryEntryInBCDExfailed: 0x%x", (unsigned int)v10);
    return RtlNtStatusToDosError(v10);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180034c8c  push    rbp
0x180034c8e  push    rbx
0x180034c8f  push    rsi
0x180034c90  push    rdi
0x180034c91  push    r12
0x180034c93  push    r13
0x180034c95  push    r14
0x180034c97  push    r15
0x180034c99  lea     rbp, [rsp-208h]
0x180034ca1  sub     rsp, 308h
0x180034ca8  mov     rax, cs:__security_cookie
0x180034caf  xor     rax, rsp
0x180034cb2  mov     [rbp+240h+var_50], rax
0x180034cb9  mov     r15, r8
0x180034cbc  mov     rsi, rdx
0x180034cbf  mov     r14, rcx
0x180034cc2  xor     r13d, r13d
0x180034cc5  xorps   xmm0, xmm0
0x180034cc8  mov     [rsp+340h+var_2F8], r13
0x180034ccd  xorps   xmm1, xmm1
0x180034cd0  lea     rcx, [rbp+240h+var_2B0]; void *
0x180034cd4  xor     edx, edx; Val
0x180034cd6  mov     r8d, 25Ch; Size
0x180034cdc  mov     edi, r13d
0x180034cdf  mov     r12, r9
0x180034ce2  movups  [rbp+240h+var_2C0], xmm0
0x180034ce6  movups  xmmword ptr [rsp+340h+var_2D0.Data1], xmm1
0x180034ceb  call    memset_0
0x180034cf0  xorps   xmm0, xmm0
0x180034cf3  mov     [rsp+340h+lpMem], r13
0x180034cf8  lea     r9, [rsp+340h+var_2F8]
0x180034cfd  mov     [rsp+340h+var_310], r13d
0x180034d02  lea     r8, [rsp+340h+var_2E0]
0x180034d07  mov     [rsp+340h+var_300], r13
0x180034d0c  xor     edx, edx
0x180034d0e  mov     [rsp+340h+var_2F0], 1
0x180034d15  mov     rcx, r14
0x180034d18  mov     [rsp+340h+var_2E8], r13
0x180034d1d  movups  xmmword ptr [r12], xmm0
0x180034d22  mov     [rsp+340h+var_2E0], 1
0x180034d2a  mov     [rsp+340h+var_2DC], 10200003h
0x180034d32  call    cs:__imp_BcdCreateObject
0x180034d38  mov     ebx, eax
0x180034d3a  test    eax, eax
0x180034d3c  jns     short loc_180034D57
0x180034d3e  lea     rdx, aBcdcreateobjec_0; "BcdCreateObject failed: 0x%x"
0x180034d45  mov     r8d, eax
0x180034d48  mov     ecx, 1
0x180034d4d  call    UnattendLogW
0x180034d52  jmp     loc_18003518D
0x180034d57  mov     rcx, [rsp+340h+var_2F8]
0x180034d5c  lea     r9, [rbp+240h+var_2C0]
0x180034d60  xor     r8d, r8d
0x180034d63  xor     edx, edx
0x180034d65  call    cs:__imp_BcdQueryObject
0x180034d6b  mov     ebx, eax
0x180034d6d  test    eax, eax
0x180034d6f  jns     short loc_180034D7A
0x180034d71  lea     rdx, aBcdqueryobject_0; "BcdQueryObject failed: 0x%x"
0x180034d78  jmp     short loc_180034D45
0x180034d7a  lea     r9, aRecoveryWindow; "\\Recovery\\WindowsRE"
0x180034d81  mov     edx, 12Eh; unsigned __int64
0x180034d86  lea     r8, aS_1; "%s\\"
0x180034d8d  lea     rcx, [rbp+240h+var_2B0]; unsigned __int16 *
0x180034d91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034d96  mov     edi, eax
0x180034d98  test    eax, eax
0x180034d9a  jns     short loc_180034DD3
0x180034d9c  mov     dword ptr [rsp+340h+var_318], 4C0h
0x180034da4  lea     r8, aFailedToCreate_2; "failed to create boot path"
0x180034dab  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180034db2  mov     r9d, edi
0x180034db5  mov     [rsp+340h+var_320], rcx
0x180034dba  lea     rdx, aWinrecreaterec_0; "winreCreateRecoveryEntryInBCDEx %s (0x%"...
0x180034dc1  mov     ecx, 2
0x180034dc6  call    UnattendLogW
0x180034dcb  movzx   edi, di
0x180034dce  jmp     loc_18003518D
0x180034dd3  lea     r9, [rsp+340h+var_2D0]; struct _GUID *
0x180034dd8  mov     rdx, rsi; struct PartitionNode *
0x180034ddb  lea     r8, [rbp+240h+var_2B0]; unsigned __int16 *
0x180034ddf  mov     rcx, r14; void *
0x180034de2  call    ?winreCreateRamdiskOptions@@YAKPEAXPEAUPartitionNode@@PEAGPEAU_GUID@@@Z; winreCreateRamdiskOptions(void *,PartitionNode *,ushort *,_GUID *)
0x180034de7  mov     edi, eax
0x180034de9  test    eax, eax
0x180034deb  jz      short loc_180034E21
0x180034ded  mov     dword ptr [rsp+340h+var_318], 4C7h
0x180034df5  lea     r8, aFailedToCreate_18; "failed to create ram disk options"
0x180034dfc  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180034e03  mov     r9d, eax
0x180034e06  mov     [rsp+340h+var_320], rcx
0x180034e0b  lea     rdx, aWinrecreaterec_0; "winreCreateRecoveryEntryInBCDEx %s (0x%"...
0x180034e12  mov     ecx, 2
0x180034e17  call    UnattendLogW
0x180034e1c  jmp     loc_18003518D
0x180034e21  lea     rcx, [rbp+240h+var_2B0]
0x180034e25  call    winreAddTrailingBackslash
0x180034e2a  mov     edi, eax
0x180034e2c  test    eax, eax
0x180034e2e  jz      short loc_180034E41
0x180034e30  mov     dword ptr [rsp+340h+var_318], 4CEh
0x180034e38  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x180034e3f  jmp     short loc_180034DFC
0x180034e41  lea     r8, aWinreWim; "Winre.wim"
0x180034e48  mov     edx, 12Eh; unsigned __int64
0x180034e4d  lea     rcx, [rbp+240h+var_2B0]; unsigned __int16 *
0x180034e51  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034e56  mov     edi, eax
0x180034e58  test    eax, eax
0x180034e5a  jns     short loc_180034E70
0x180034e5c  mov     dword ptr [rsp+340h+var_318], 4CFh
0x180034e64  lea     r8, aFailedToConcat_2; "failed to concatenate winre.wim path"
0x180034e6b  jmp     loc_180034DAB
0x180034e70  lea     rax, [rsp+340h+var_310]
0x180034e75  mov     rdx, rsi; struct PartitionNode *
0x180034e78  mov     [rsp+340h+var_318], rax; unsigned int *
0x180034e7d  lea     r9, [rsp+340h+var_2D0]; struct _GUID *
0x180034e82  lea     rax, [rsp+340h+lpMem]
0x180034e87  mov     ecx, 4; unsigned int
0x180034e8c  lea     r8, [rbp+240h+var_2B0]; unsigned __int16 *
0x180034e90  mov     [rsp+340h+var_320], rax; struct _BCDE_DEVICE **
0x180034e95  call    ?winreMakeBcdDeviceObject@@YAKKPEAUPartitionNode@@PEBGPEAU_GUID@@PEAPEAU_BCDE_DEVICE@@PEAK@Z; winreMakeBcdDeviceObject(ulong,PartitionNode *,ushort const *,_GUID *,_BCDE_DEVICE * *,ulong *)
0x180034e9a  mov     r14, [rsp+340h+lpMem]
0x180034e9f  mov     edi, eax
0x180034ea1  test    eax, eax
0x180034ea3  jz      short loc_180034ED9
0x180034ea5  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180034eac  mov     dword ptr [rsp+340h+var_318], 4D6h
0x180034eb4  mov     [rsp+340h+var_320], rcx
0x180034eb9  lea     r8, aFailedToMakeBc; "failed to make bcd device object"
0x180034ec0  mov     ecx, 2
0x180034ec5  lea     rdx, aWinrecreaterec_0; "winreCreateRecoveryEntryInBCDEx %s (0x%"...
0x180034ecc  mov     r9d, eax
0x180034ecf  call    UnattendLogW
0x180034ed4  jmp     loc_180035174
0x180034ed9  mov     r9d, [rsp+340h+var_310]
0x180034ede  mov     r8, r14
0x180034ee1  mov     rcx, [rsp+340h+var_2F8]
0x180034ee6  mov     edx, 11000001h
0x180034eeb  call    cs:__imp_BcdSetElementData
0x180034ef1  mov     ebx, eax
0x180034ef3  test    eax, eax
0x180034ef5  jns     short loc_180034F10
0x180034ef7  lea     rdx, aBcdsetelementd_1; "BcdSetElementData failed: 0x%x"
0x180034efe  mov     ecx, 1
0x180034f03  mov     r8d, eax
0x180034f06  call    UnattendLogW
0x180034f0b  jmp     loc_180035174
0x180034f10  mov     r9d, [rsp+340h+var_310]
0x180034f15  mov     r8, r14
0x180034f18  mov     rcx, [rsp+340h+var_2F8]
0x180034f1d  mov     edx, 21000001h
0x180034f22  call    cs:__imp_BcdSetElementData
0x180034f28  mov     ebx, eax
0x180034f2a  test    eax, eax
0x180034f2c  js      short loc_180034EF7
0x180034f2e  mov     rcx, [rsp+340h+var_2F8]
0x180034f33  lea     r8, aWindows; "\\windows"
0x180034f3a  mov     r9d, 14h
0x180034f40  mov     edx, 22000002h
0x180034f45  call    cs:__imp_BcdSetElementData
0x180034f4b  mov     ebx, eax
0x180034f4d  test    eax, eax
0x180034f4f  js      short loc_180034EF7
0x180034f51  call    ?IsEfi@Utils@@SAHXZ; Utils::IsEfi(void)
0x180034f56  test    eax, eax
0x180034f58  lea     rcx, aWindowsSystem3_2; "\\windows\\system32\\winload.exe"
0x180034f5f  lea     r11, aWindowsSystem3_0; "\\windows\\system32\\winload.efi"
0x180034f66  mov     edx, 12Eh; unsigned __int64
0x180034f6b  cmovz   r11, rcx
0x180034f6f  lea     r8, [rsp+340h+var_300]; unsigned __int64 *
0x180034f74  mov     rcx, r11; unsigned __int16 *
0x180034f77  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180034f7c  mov     esi, eax
0x180034f7e  test    eax, eax
0x180034f80  jns     short loc_180034FB9
0x180034f82  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180034f89  mov     dword ptr [rsp+340h+var_318], 503h
0x180034f91  mov     [rsp+340h+var_320], rcx
0x180034f96  lea     r8, aFailedToGetThe_2; "failed to get the length of loader rela"...
0x180034f9d  mov     ecx, 2
0x180034fa2  lea     rdx, aWinrecreaterec_0; "winreCreateRecoveryEntryInBCDEx %s (0x%"...
0x180034fa9  mov     r9d, eax
0x180034fac  call    UnattendLogW
0x180034fb1  movzx   edi, si
0x180034fb4  jmp     loc_180035174
0x180034fb9  mov     r9d, dword ptr [rsp+340h+var_300]
0x180034fbe  mov     r8, r11
0x180034fc1  mov     rcx, [rsp+340h+var_2F8]
0x180034fc6  mov     edx, 12000002h
0x180034fcb  lea     r9d, ds:2[r9*2]
0x180034fd3  call    cs:__imp_BcdSetElementData
0x180034fd9  mov     ebx, eax
0x180034fdb  test    eax, eax
0x180034fdd  js      loc_180034EF7
0x180034fe3  mov     rcx, [rsp+340h+var_2F8]
0x180034fe8  lea     r8, aWindowsRecover_0; "Windows Recovery Environment"
0x180034fef  mov     r9d, 3Ch ; '<'
0x180034ff5  mov     edx, 12000004h
0x180034ffa  call    cs:__imp_BcdSetElementData
0x180035000  mov     ebx, eax
0x180035002  test    eax, eax
0x180035004  js      loc_180034EF7
0x18003500a  mov     rcx, [rsp+340h+var_2F8]
0x18003500f  lea     r8, GUID_BOOT_LOADER_SETTINGS_GROUP
0x180035016  mov     r9d, 10h
0x18003501c  mov     edx, 14000006h
0x180035021  call    cs:__imp_BcdSetElementData
0x180035027  mov     ebx, eax
0x180035029  test    eax, eax
0x18003502b  jns     short loc_180035039
0x18003502d  lea     rdx, aBcdsetelementd_0; "BcdSetElementData(BCDE_LIBRARY_TYPE_INH"...
0x180035034  jmp     loc_180034EFE
0x180035039  mov     rcx, [rsp+340h+var_2F8]
0x18003503e  lea     r8, [rsp+340h+var_2D8]
0x180035043  mov     ebx, 8
0x180035048  mov     [rsp+340h+var_2D8], r13
0x18003504d  mov     r9d, ebx
0x180035050  mov     edx, 25000020h
0x180035055  call    cs:__imp_BcdSetElementData
0x18003505b  mov     rcx, [rsp+340h+var_2F8]
0x180035060  lea     r9d, [rbx-6]
0x180035064  lea     r8, [rsp+340h+var_2F0]
0x180035069  mov     edx, 26000022h
0x18003506e  call    cs:__imp_BcdSetElementData
0x180035074  test    eax, eax
0x180035076  jns     short loc_18003508A
0x180035078  mov     r8d, eax
0x18003507b  lea     rdx, aBcdsetelementd_1; "BcdSetElementData failed: 0x%x"
0x180035082  lea     ecx, [rbx-6]
0x180035085  call    UnattendLogW
0x18003508a  mov     rcx, [rsp+340h+var_2F8]
0x18003508f  lea     r8, [rsp+340h+var_2F0]
0x180035094  mov     r9d, 2
0x18003509a  mov     edx, 46000010h
0x18003509f  call    cs:__imp_BcdSetElementData
0x1800350a5  test    eax, eax
0x1800350a7  jns     short loc_1800350BD
0x1800350a9  mov     r8d, eax
0x1800350ac  lea     rdx, aBcdsetelementd_1; "BcdSetElementData failed: 0x%x"
0x1800350b3  mov     ecx, 2
0x1800350b8  call    UnattendLogW
0x1800350bd  mov     rcx, [rsp+340h+var_2F8]
0x1800350c2  lea     r8, [rsp+340h+var_2E8]
0x1800350c7  mov     r9d, ebx
0x1800350ca  mov     [rsp+340h+var_2E8], 1
0x1800350d3  mov     edx, 250000C2h
0x1800350d8  call    cs:__imp_BcdSetElementData
0x1800350de  test    eax, eax
0x1800350e0  jns     short loc_1800350F6
0x1800350e2  mov     r8d, eax
0x1800350e5  lea     rdx, aBcdsetelementd_1; "BcdSetElementData failed: 0x%x"
0x1800350ec  mov     ecx, 2
0x1800350f1  call    UnattendLogW
0x1800350f6  mov     rcx, [rsp+340h+var_2F8]
0x1800350fb  lea     r8, [rsp+340h+var_2E8]
0x180035100  mov     r9d, ebx
0x180035103  mov     [rsp+340h+var_2E8], 3
0x18003510c  mov     edx, 15000065h
0x180035111  call    cs:__imp_BcdSetElementData
0x180035117  test    eax, eax
0x180035119  jns     short loc_18003512F
0x18003511b  mov     r8d, eax
0x18003511e  lea     rdx, aBcdsetelementd_1; "BcdSetElementData failed: 0x%x"
0x180035125  mov     ecx, 2
0x18003512a  call    UnattendLogW
0x18003512f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180035133  inc     r9
0x180035136  cmp     [r15+r9*2], r13w
0x18003513b  jnz     short loc_180035133
0x18003513d  mov     rcx, [rsp+340h+var_2F8]
0x180035142  add     r9d, r9d
0x180035145  mov     r8, r15
0x180035148  mov     edx, 12000005h
0x18003514d  call    cs:__imp_BcdSetElementData
0x180035153  mov     ebx, eax
0x180035155  test    eax, eax
0x180035157  jns     short loc_18003516A
0x180035159  lea     rdx, aBcdsetelementd_1; "BcdSetElementData failed: 0x%x"
0x180035160  mov     ecx, 2
0x180035165  jmp     loc_180034F03
0x18003516a  movups  xmm0, [rbp+240h+var_2C0]
0x18003516e  movdqu  xmmword ptr [r12], xmm0
0x180035174  test    r14, r14
0x180035177  jz      short loc_18003518D
0x180035179  call    cs:__imp_GetProcessHeap
0x18003517f  mov     r8, r14; lpMem
0x180035182  xor     edx, edx; dwFlags
0x180035184  mov     rcx, rax; hHeap
0x180035187  call    cs:__imp_HeapFree
0x18003518d  mov     rcx, [rsp+340h+var_2F8]
0x180035192  test    rcx, rcx
0x180035195  jz      short loc_1800351A2
0x180035197  call    cs:__imp_BcdCloseObject
0x18003519d  mov     [rsp+340h+var_2F8], r13
0x1800351a2  test    ebx, ebx
0x1800351a4  jns     short loc_1800351D7
0x1800351a6  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r13d; _ReAgentErrorCodes ReAgentError
0x1800351ad  jnz     short loc_1800351B9
0x1800351af  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 7; _ReAgentErrorCodes ReAgentError
  ... truncated ...
```
