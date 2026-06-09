# winreUpdateRecoveryEntryInBCD

- ea: `0x18003648c`
- end: `0x1800367b0`
- name: `winreUpdateRecoveryEntryInBCD`
- size: `804`
- prototype: `__int64 __fastcall(struct PartitionNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180019a90`

## callees

- `0x1800059fc`
- `0x18000c658`
- `0x18000c6f0`
- `0x18000ff68`
- `0x1800333b4`
- `0x180033cb8`
- `0x18003648c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003652d`
- `ntdll!RtlNtStatusToDosError` at `0x18003677f`
- `ntdll!RtlNtStatusToDosError` at `0x18003652d`
- `ntdll!RtlNtStatusToDosError` at `0x18003677f`
- `KERNEL32!HeapFree` at `0x180036735`
- `KERNEL32!HeapFree` at `0x180036735`
- `KERNEL32!GetProcessHeap` at `0x180036727`
- `KERNEL32!GetProcessHeap` at `0x180036727`
- `bcd!BcdSetElementData` at `0x1800366db`
- `bcd!BcdSetElementData` at `0x180036702`
- `bcd!BcdSetElementData` at `0x1800366db`
- `bcd!BcdSetElementData` at `0x180036702`
- `bcd!BcdCloseObject` at `0x180036745`
- `bcd!BcdCloseObject` at `0x180036745`
- `bcd!BcdOpenObject` at `0x180036547`
- `bcd!BcdOpenObject` at `0x180036547`
- `bcd!BcdOpenStore` at `0x180036506`
- `bcd!BcdOpenStore` at `0x180036506`

## string_xrefs

- `0x180036555`: `BcdOpenObject failed: 0x%x`
- `0x18003659e`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x1800365f0`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x18003669a`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x18003651b`: `open store failed: 0x%x`
- `0x180036597`: `failed to create boot path`
- `0x1800365e9`: `failed to create ram disk options`
- `0x180036658`: `failed to concatenate winre.wim path`
- `0x1800365ad`: `winreUpdateRecoveryEntryInBCD %s (0x%x) in file %S line %d`
- `0x1800365ff`: `winreUpdateRecoveryEntryInBCD %s (0x%x) in file %S line %d`
- `0x1800366b8`: `winreUpdateRecoveryEntryInBCD %s (0x%x) in file %S line %d`
- `0x18003676e`: `winreUpdateRecoveryEntryInBCDfailed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreUpdateRecoveryEntryInBCD(struct PartitionNode *a1, __int64 a2)
{
  int v4; // eax
  NTSTATUS v5; // ebx
  signed int v6; // edi
  int v7; // eax
  const wchar_t *v8; // r8
  unsigned int v9; // eax
  const wchar_t *v10; // r8
  unsigned int BcdDeviceObject; // eax
  void *v12; // rsi
  int v13; // eax
  int v14; // eax
  HANDLE ProcessHeap; // rax
  int v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+28h] [rbp-D8h]
  unsigned int *v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  void *v23; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v24; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v25[304]; // [rsp+60h] [rbp-A0h] BYREF

  v23 = 0;
  v22 = 0;
  v24 = 0;
  memset_0(v25, 0, 0x25Cu);
  lpMem = 0;
  LODWORD(v20) = 0;
  v4 = BcdOpenStore(0, 0, &v23);
  v5 = v4;
  if ( v4 < 0 )
  {
    UnattendLogW(1, L"open store failed: 0x%x", (unsigned int)v4);
    v6 = RtlNtStatusToDosError(v5);
    goto LABEL_23;
  }
  v7 = BcdOpenObject(v23, a2, &v22);
  v5 = v7;
  if ( v7 < 0 )
  {
    v6 = 0;
    UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v7);
    goto LABEL_23;
  }
  v6 = StringCchPrintfW(v25, 0x12Eu, L"%s\\", L"\\Recovery\\WindowsRE");
  if ( v6 < 0 )
  {
    v17 = 1503;
    v8 = L"failed to create boot path";
LABEL_7:
    UnattendLogW(
      2,
      L"winreUpdateRecoveryEntryInBCD %s (0x%x) in file %S line %d",
      v8,
      (unsigned int)v6,
      "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
      v17,
      v20);
    v6 = (unsigned __int16)v6;
    goto LABEL_23;
  }
  v9 = winreCreateRamdiskOptions(v23, a1, v25, &v24);
  v6 = v9;
  if ( v9 )
  {
    v18 = 1510;
    v10 = L"failed to create ram disk options";
LABEL_10:
    UnattendLogW(
      2,
      L"winreUpdateRecoveryEntryInBCD %s (0x%x) in file %S line %d",
      v10,
      v9,
      "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
      v18,
      v20);
    goto LABEL_23;
  }
  v9 = winreAddTrailingBackslash(v25);
  v6 = v9;
  if ( v9 )
  {
    v18 = 1516;
    v10 = L"failed to add trailing back slash";
    goto LABEL_10;
  }
  v6 = StringCchCatW(v25, 0x12Eu, L"Winre.wim");
  if ( v6 < 0 )
  {
    v17 = 1517;
    v8 = L"failed to concatenate winre.wim path";
    goto LABEL_7;
  }
  BcdDeviceObject = winreMakeBcdDeviceObject(4u, a1, v25, &v24, (struct _BCDE_DEVICE **)&lpMem, (unsigned int *)&v20);
  v12 = lpMem;
  v6 = BcdDeviceObject;
  if ( BcdDeviceObject )
  {
    LODWORD(v19) = 1524;
    UnattendLogW(
      2,
      L"winreUpdateRecoveryEntryInBCD %s (0x%x) in file %S line %d",
      L"failed to make bcd device object",
      BcdDeviceObject,
      "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
      v19,
      v20);
  }
  else
  {
    v13 = BcdSetElementData(v22, 285212673, lpMem, (unsigned int)v20);
    v5 = v13;
    if ( v13 >= 0 )
    {
      v14 = BcdSetElementData(v22, 553648129, v12, (unsigned int)v20);
      v5 = v14;
      if ( v14 < 0 )
        UnattendLogW(1, L"BcdSetElementData failed for OS device field: 0x%x", (unsigned int)v14);
    }
    else
    {
      UnattendLogW(1, L"BcdSetElementData failed for Device field 0x%x", (unsigned int)v13);
    }
  }
  if ( v12 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
  }
LABEL_23:
  if ( v22 )
  {
    BcdCloseObject();
    v22 = 0;
  }
  if ( v5 < 0 )
  {
    if ( !ReAgentError )
      ReAgentError = 7;
    UnattendLogW(2, L"winreUpdateRecoveryEntryInBCDfailed: 0x%x", (unsigned int)v5);
    return RtlNtStatusToDosError(v5);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003648c  mov     [rsp-8+arg_10], rbx
0x180036491  mov     [rsp-8+arg_18], rsi
0x180036496  push    rbp
0x180036497  push    rdi
0x180036498  push    r15
0x18003649a  lea     rbp, [rsp-1D0h]
0x1800364a2  sub     rsp, 2D0h
0x1800364a9  mov     rax, cs:__security_cookie
0x1800364b0  xor     rax, rsp
0x1800364b3  mov     [rbp+1E0h+var_20], rax
0x1800364ba  mov     rdi, rdx
0x1800364bd  mov     [rsp+2E0h+var_298], 0
0x1800364c6  mov     rsi, rcx
0x1800364c9  mov     [rsp+2E0h+var_2A0], 0
0x1800364d2  xorps   xmm0, xmm0
0x1800364d5  lea     rcx, [rsp+2E0h+var_280]; void *
0x1800364da  xor     edx, edx; Val
0x1800364dc  mov     r8d, 25Ch; Size
0x1800364e2  movups  xmmword ptr [rsp+2E0h+var_290.Data1], xmm0
0x1800364e7  call    memset_0
0x1800364ec  lea     r8, [rsp+2E0h+var_298]
0x1800364f1  mov     [rsp+2E0h+lpMem], 0
0x1800364fa  xor     edx, edx
0x1800364fc  mov     dword ptr [rsp+2E0h+var_2B0], 0
0x180036504  xor     ecx, ecx
0x180036506  call    cs:__imp_BcdOpenStore
0x18003650c  mov     ebx, eax
0x18003650e  mov     r15d, 2
0x180036514  test    eax, eax
0x180036516  jns     short loc_18003653A
0x180036518  mov     r8d, eax
0x18003651b  lea     rdx, aOpenStoreFaile_1; "open store failed: 0x%x"
0x180036522  lea     ecx, [r15-1]
0x180036526  call    UnattendLogW
0x18003652b  mov     ecx, ebx; Status
0x18003652d  call    cs:__imp_RtlNtStatusToDosError
0x180036533  mov     edi, eax
0x180036535  jmp     loc_18003673B
0x18003653a  mov     rcx, [rsp+2E0h+var_298]
0x18003653f  lea     r8, [rsp+2E0h+var_2A0]
0x180036544  mov     rdx, rdi
0x180036547  call    cs:__imp_BcdOpenObject
0x18003654d  mov     ebx, eax
0x18003654f  test    eax, eax
0x180036551  jns     short loc_18003656C
0x180036553  xor     edi, edi
0x180036555  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x18003655c  mov     r8d, eax
0x18003655f  lea     ecx, [rdi+1]
0x180036562  call    UnattendLogW
0x180036567  jmp     loc_18003673B
0x18003656c  lea     r9, aRecoveryWindow; "\\Recovery\\WindowsRE"
0x180036573  mov     edx, 12Eh; unsigned __int64
0x180036578  lea     r8, aS_1; "%s\\"
0x18003657f  lea     rcx, [rsp+2E0h+var_280]; unsigned __int16 *
0x180036584  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036589  mov     edi, eax
0x18003658b  test    eax, eax
0x18003658d  jns     short loc_1800365C4
0x18003658f  mov     dword ptr [rsp+2E0h+var_2B8], 5DFh
0x180036597  lea     r8, aFailedToCreate_2; "failed to create boot path"
0x18003659e  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800365a5  mov     r9d, edi
0x1800365a8  mov     [rsp+2E0h+var_2C0], rcx
0x1800365ad  lea     rdx, aWinreupdaterec; "winreUpdateRecoveryEntryInBCD %s (0x%x)"...
0x1800365b4  mov     ecx, r15d
0x1800365b7  call    UnattendLogW
0x1800365bc  movzx   edi, di
0x1800365bf  jmp     loc_18003673B
0x1800365c4  mov     rcx, [rsp+2E0h+var_298]; void *
0x1800365c9  lea     r9, [rsp+2E0h+var_290]; struct _GUID *
0x1800365ce  lea     r8, [rsp+2E0h+var_280]; unsigned __int16 *
0x1800365d3  mov     rdx, rsi; struct PartitionNode *
0x1800365d6  call    ?winreCreateRamdiskOptions@@YAKPEAXPEAUPartitionNode@@PEAGPEAU_GUID@@@Z; winreCreateRamdiskOptions(void *,PartitionNode *,ushort *,_GUID *)
0x1800365db  mov     edi, eax
0x1800365dd  test    eax, eax
0x1800365df  jz      short loc_180036613
0x1800365e1  mov     dword ptr [rsp+2E0h+var_2B8], 5E6h
0x1800365e9  lea     r8, aFailedToCreate_18; "failed to create ram disk options"
0x1800365f0  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800365f7  mov     r9d, eax
0x1800365fa  mov     [rsp+2E0h+var_2C0], rcx
0x1800365ff  lea     rdx, aWinreupdaterec; "winreUpdateRecoveryEntryInBCD %s (0x%x)"...
0x180036606  mov     ecx, r15d
0x180036609  call    UnattendLogW
0x18003660e  jmp     loc_18003673B
0x180036613  lea     rcx, [rsp+2E0h+var_280]
0x180036618  call    winreAddTrailingBackslash
0x18003661d  mov     edi, eax
0x18003661f  test    eax, eax
0x180036621  jz      short loc_180036634
0x180036623  mov     dword ptr [rsp+2E0h+var_2B8], 5ECh
0x18003662b  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x180036632  jmp     short loc_1800365F0
0x180036634  lea     r8, aWinreWim; "Winre.wim"
0x18003663b  mov     edx, 12Eh; unsigned __int64
0x180036640  lea     rcx, [rsp+2E0h+var_280]; unsigned __int16 *
0x180036645  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003664a  mov     edi, eax
0x18003664c  test    eax, eax
0x18003664e  jns     short loc_180036664
0x180036650  mov     dword ptr [rsp+2E0h+var_2B8], 5EDh
0x180036658  lea     r8, aFailedToConcat_2; "failed to concatenate winre.wim path"
0x18003665f  jmp     loc_18003659E
0x180036664  lea     rax, [rsp+2E0h+var_2B0]
0x180036669  mov     rdx, rsi; struct PartitionNode *
0x18003666c  mov     [rsp+2E0h+var_2B8], rax; unsigned int *
0x180036671  lea     r9, [rsp+2E0h+var_290]; struct _GUID *
0x180036676  lea     rax, [rsp+2E0h+lpMem]
0x18003667b  mov     ecx, 4; unsigned int
0x180036680  lea     r8, [rsp+2E0h+var_280]; unsigned __int16 *
0x180036685  mov     [rsp+2E0h+var_2C0], rax; struct _BCDE_DEVICE **
0x18003668a  call    ?winreMakeBcdDeviceObject@@YAKKPEAUPartitionNode@@PEBGPEAU_GUID@@PEAPEAU_BCDE_DEVICE@@PEAK@Z; winreMakeBcdDeviceObject(ulong,PartitionNode *,ushort const *,_GUID *,_BCDE_DEVICE * *,ulong *)
0x18003668f  mov     rsi, [rsp+2E0h+lpMem]
0x180036694  mov     edi, eax
0x180036696  test    eax, eax
0x180036698  jz      short loc_1800366C9
0x18003669a  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800366a1  mov     dword ptr [rsp+2E0h+var_2B8], 5F4h
0x1800366a9  mov     [rsp+2E0h+var_2C0], rcx
0x1800366ae  lea     r8, aFailedToMakeBc; "failed to make bcd device object"
0x1800366b5  mov     ecx, r15d
0x1800366b8  lea     rdx, aWinreupdaterec; "winreUpdateRecoveryEntryInBCD %s (0x%x)"...
0x1800366bf  mov     r9d, eax
0x1800366c2  call    UnattendLogW
0x1800366c7  jmp     short loc_180036722
0x1800366c9  mov     r9d, dword ptr [rsp+2E0h+var_2B0]
0x1800366ce  mov     r8, rsi
0x1800366d1  mov     rcx, [rsp+2E0h+var_2A0]
0x1800366d6  mov     edx, 11000001h
0x1800366db  call    cs:__imp_BcdSetElementData
0x1800366e1  mov     ebx, eax
0x1800366e3  test    eax, eax
0x1800366e5  jns     short loc_1800366F0
0x1800366e7  lea     rdx, aBcdsetelementd_2; "BcdSetElementData failed for Device fie"...
0x1800366ee  jmp     short loc_180036715
0x1800366f0  mov     r9d, dword ptr [rsp+2E0h+var_2B0]
0x1800366f5  mov     r8, rsi
0x1800366f8  mov     rcx, [rsp+2E0h+var_2A0]
0x1800366fd  mov     edx, 21000001h
0x180036702  call    cs:__imp_BcdSetElementData
0x180036708  mov     ebx, eax
0x18003670a  test    eax, eax
0x18003670c  jns     short loc_180036722
0x18003670e  lea     rdx, aBcdsetelementd_4; "BcdSetElementData failed for OS device "...
0x180036715  mov     r8d, eax
0x180036718  mov     ecx, 1
0x18003671d  call    UnattendLogW
0x180036722  test    rsi, rsi
0x180036725  jz      short loc_18003673B
0x180036727  call    cs:__imp_GetProcessHeap
0x18003672d  mov     r8, rsi; lpMem
0x180036730  xor     edx, edx; dwFlags
0x180036732  mov     rcx, rax; hHeap
0x180036735  call    cs:__imp_HeapFree
0x18003673b  mov     rcx, [rsp+2E0h+var_2A0]
0x180036740  test    rcx, rcx
0x180036743  jz      short loc_180036754
0x180036745  call    cs:__imp_BcdCloseObject
0x18003674b  mov     [rsp+2E0h+var_2A0], 0
0x180036754  test    ebx, ebx
0x180036756  jns     short loc_180036787
0x180036758  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x18003675f  jnz     short loc_18003676B
0x180036761  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 7; _ReAgentErrorCodes ReAgentError
0x18003676b  mov     r8d, ebx
0x18003676e  lea     rdx, aWinreupdaterec_0; "winreUpdateRecoveryEntryInBCDfailed: 0x"...
0x180036775  mov     ecx, r15d
0x180036778  call    UnattendLogW
0x18003677d  mov     ecx, ebx; Status
0x18003677f  call    cs:__imp_RtlNtStatusToDosError
0x180036785  mov     edi, eax
0x180036787  mov     eax, edi
0x180036789  mov     rcx, [rbp+1E0h+var_20]
0x180036790  xor     rcx, rsp; StackCookie
0x180036793  call    __security_check_cookie
0x180036798  lea     r11, [rsp+2E0h+var_10]
0x1800367a0  mov     rbx, [r11+30h]
0x1800367a4  mov     rsi, [r11+38h]
0x1800367a8  mov     rsp, r11
0x1800367ab  pop     r15
0x1800367ad  pop     rdi
0x1800367ae  pop     rbp
0x1800367af  retn
```
