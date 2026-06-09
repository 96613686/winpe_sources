# winreCreateRamdiskOptions(void *,PartitionNode *,ushort *,_GUID *)

- ea: `0x1800333b4`
- end: `0x18003367e`
- name: `?winreCreateRamdiskOptions@@YAKPEAXPEAUPartitionNode@@PEAGPEAU_GUID@@@Z`
- size: `714`
- prototype: `unsigned int(void *, struct PartitionNode *, unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180034c8c`
- `0x18003648c`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x1800333b4`
- `0x180033cb8`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180033653`
- `ntdll!RtlNtStatusToDosError` at `0x180033653`
- `ole32!CoTaskMemFree` at `0x180033602`
- `ole32!CoTaskMemFree` at `0x180033602`
- `bcd!BcdSetElementData` at `0x1800334f0`
- `bcd!BcdSetElementData` at `0x1800335a9`
- `bcd!BcdSetElementData` at `0x1800335dc`
- `bcd!BcdSetElementData` at `0x1800334f0`
- `bcd!BcdSetElementData` at `0x1800335a9`
- `bcd!BcdSetElementData` at `0x1800335dc`
- `bcd!BcdCreateObject` at `0x180033432`
- `bcd!BcdCreateObject` at `0x180033432`
- `bcd!BcdCloseObject` at `0x180033612`
- `bcd!BcdCloseObject` at `0x180033612`
- `bcd!BcdQueryObject` at `0x180033462`
- `bcd!BcdQueryObject` at `0x180033462`

## string_xrefs

- `0x1800334ad`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x18003353b`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x18003343e`: `BcdCreateObject failed: 0x%x`
- `0x1800334cd`: `winreCreateRamdiskOptions %s (0x%x) in file %S line %d`
- `0x180033545`: `winreCreateRamdiskOptions %s (0x%x) in file %S line %d`
- `0x180033534`: `failed to create boot.sdi file path`
- `0x180033584`: `failed to get boot.sdi path length`
- `0x180033628`: `winreCreateRamdiskOptions returning 0x%x`
- `0x180033642`: `winreCreateRamdiskOptions returning 0x%x`

## pseudocode

```c
ULONG __fastcall winreCreateRamdiskOptions(void *a1, struct PartitionNode *a2, unsigned __int16 *a3, struct _GUID *a4)
{
  unsigned int v7; // edi
  int v9; // eax
  NTSTATUS v10; // ebx
  int Object; // eax
  unsigned int BcdDeviceObject; // eax
  void *v13; // r14
  int v14; // eax
  int v15; // r15d
  const wchar_t *v16; // r8
  int v17; // eax
  unsigned int *v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v24[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v25[304]; // [rsp+60h] [rbp-A0h] BYREF

  v7 = 0;
  v23 = 0;
  memset_0(v25, 0, 0x25Cu);
  pv = 0;
  v24[0] = 1;
  LODWORD(v20) = 0;
  v22 = 0;
  v24[1] = 805306368;
  v9 = BcdCreateObject(a1, 0, v24, &v23);
  v10 = v9;
  if ( v9 < 0 )
  {
    UnattendLogW(2, L"BcdCreateObject failed: 0x%x", (unsigned int)v9);
    goto LABEL_20;
  }
  Object = BcdQueryObject(v23, 0, 0, a4);
  v10 = Object;
  if ( Object < 0 )
  {
    UnattendLogW(1, L"BcdQueryObject failed: 0x%x", (unsigned int)Object);
    goto LABEL_20;
  }
  BcdDeviceObject = winreMakeBcdDeviceObject(2u, a2, 0, 0, (struct _BCDE_DEVICE **)&pv, (unsigned int *)&v20);
  v13 = pv;
  v7 = BcdDeviceObject;
  if ( BcdDeviceObject )
  {
    LODWORD(v19) = 1001;
    UnattendLogW(
      2,
      L"winreCreateRamdiskOptions %s (0x%x) in file %S line %d",
      L"failed to make bcd device object",
      BcdDeviceObject,
      "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
      v19,
      v20);
    goto LABEL_18;
  }
  v14 = BcdSetElementData(v23, 822083587, pv, (unsigned int)v20);
  v10 = v14;
  if ( v14 >= 0 )
  {
    v15 = StringCchPrintfW(v25, 0x12Eu, L"%s%s", a3, L"boot.sdi");
    if ( v15 < 0 )
    {
      LODWORD(v19) = 1021;
      v16 = L"failed to create boot.sdi file path";
LABEL_11:
      UnattendLogW(
        2,
        L"winreCreateRamdiskOptions %s (0x%x) in file %S line %d",
        v16,
        (unsigned int)v15,
        "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
        v19);
      v7 = (unsigned __int16)v15;
      goto LABEL_18;
    }
    v15 = StringCchLengthW(v25, 0x12Eu, &v22);
    if ( v15 < 0 )
    {
      LODWORD(v19) = 1023;
      v16 = L"failed to get boot.sdi path length";
      goto LABEL_11;
    }
    v17 = BcdSetElementData(v23, 838860804, v25, (unsigned int)(2 * v22 + 2));
    if ( v17 < 0 )
      UnattendLogW(1, L"BcdSetElementData failed: 0x%x", (unsigned int)v17);
    v14 = BcdSetElementData(v23, 301989892, L"Windows Recovery", 36);
    v10 = v14;
    if ( v14 >= 0 )
      goto LABEL_18;
  }
  UnattendLogW(1, L"BcdSetElementData failed: 0x%x", (unsigned int)v14);
LABEL_18:
  if ( v13 )
    CoTaskMemFree(v13);
LABEL_20:
  if ( v23 )
  {
    BcdCloseObject();
    v23 = 0;
  }
  if ( v7 )
  {
    UnattendLogW(1, L"winreCreateRamdiskOptions returning 0x%x", v7);
    return v7;
  }
  else if ( v10 >= 0 )
  {
    return 0;
  }
  else
  {
    UnattendLogW(1, L"winreCreateRamdiskOptions returning 0x%x", (unsigned int)v10);
    return RtlNtStatusToDosError(v10);
  }
}

```

## disassembly

```asm
0x1800333b4  push    rbp
0x1800333b6  push    rbx
0x1800333b7  push    rsi
0x1800333b8  push    rdi
0x1800333b9  push    r13
0x1800333bb  push    r14
0x1800333bd  push    r15
0x1800333bf  lea     rbp, [rsp-1D0h]
0x1800333c7  sub     rsp, 2D0h
0x1800333ce  mov     rax, cs:__security_cookie
0x1800333d5  xor     rax, rsp
0x1800333d8  mov     [rbp+200h+var_40], rax
0x1800333df  mov     r15, r8
0x1800333e2  mov     r14, rdx
0x1800333e5  mov     rbx, rcx
0x1800333e8  xor     edi, edi
0x1800333ea  xor     edx, edx; Val
0x1800333ec  mov     [rsp+300h+var_2B8], rdi
0x1800333f1  mov     r8d, 25Ch; Size
0x1800333f7  lea     rcx, [rsp+300h+var_2A0]; void *
0x1800333fc  mov     rsi, r9
0x1800333ff  call    memset_0
0x180033404  lea     r13d, [rdi+1]
0x180033408  mov     [rsp+300h+pv], rdi
0x18003340d  lea     r9, [rsp+300h+var_2B8]
0x180033412  mov     [rsp+300h+var_2B0], r13d
0x180033417  lea     r8, [rsp+300h+var_2B0]
0x18003341c  mov     dword ptr [rsp+300h+var_2D0], edi
0x180033420  xor     edx, edx
0x180033422  mov     [rsp+300h+var_2C0], rdi
0x180033427  mov     rcx, rbx
0x18003342a  mov     [rsp+300h+var_2AC], 30000000h
0x180033432  call    cs:__imp_BcdCreateObject
0x180033438  mov     ebx, eax
0x18003343a  test    eax, eax
0x18003343c  jns     short loc_180033455
0x18003343e  lea     rdx, aBcdcreateobjec_0; "BcdCreateObject failed: 0x%x"
0x180033445  lea     ecx, [rdi+2]
0x180033448  mov     r8d, eax
0x18003344b  call    UnattendLogW
0x180033450  jmp     loc_180033608
0x180033455  mov     rcx, [rsp+300h+var_2B8]
0x18003345a  mov     r9, rsi
0x18003345d  xor     r8d, r8d
0x180033460  xor     edx, edx
0x180033462  call    cs:__imp_BcdQueryObject
0x180033468  mov     ebx, eax
0x18003346a  test    eax, eax
0x18003346c  jns     short loc_18003347A
0x18003346e  lea     rdx, aBcdqueryobject_0; "BcdQueryObject failed: 0x%x"
0x180033475  mov     ecx, r13d
0x180033478  jmp     short loc_180033448
0x18003347a  xor     r9d, r9d; struct _GUID *
0x18003347d  lea     rax, [rsp+300h+var_2D0]
0x180033482  mov     [rsp+300h+var_2D8], rax; unsigned int *
0x180033487  xor     r8d, r8d; unsigned __int16 *
0x18003348a  lea     rax, [rsp+300h+pv]
0x18003348f  mov     rdx, r14; struct PartitionNode *
0x180033492  mov     [rsp+300h+var_2E0], rax; struct _BCDE_DEVICE **
0x180033497  lea     esi, [r9+2]
0x18003349b  mov     ecx, esi; unsigned int
0x18003349d  call    ?winreMakeBcdDeviceObject@@YAKKPEAUPartitionNode@@PEBGPEAU_GUID@@PEAPEAU_BCDE_DEVICE@@PEAK@Z; winreMakeBcdDeviceObject(ulong,PartitionNode *,ushort const *,_GUID *,_BCDE_DEVICE * *,ulong *)
0x1800334a2  mov     r14, [rsp+300h+pv]
0x1800334a7  mov     edi, eax
0x1800334a9  test    eax, eax
0x1800334ab  jz      short loc_1800334DE
0x1800334ad  lea     rax, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800334b4  mov     dword ptr [rsp+300h+var_2D8], 3E9h
0x1800334bc  mov     r9d, edi
0x1800334bf  mov     [rsp+300h+var_2E0], rax
0x1800334c4  lea     r8, aFailedToMakeBc; "failed to make bcd device object"
0x1800334cb  mov     ecx, esi
0x1800334cd  lea     rdx, aWinrecreateram; "winreCreateRamdiskOptions %s (0x%x) in "...
0x1800334d4  call    UnattendLogW
0x1800334d9  jmp     loc_1800335FA
0x1800334de  mov     r9d, dword ptr [rsp+300h+var_2D0]
0x1800334e3  mov     r8, r14
0x1800334e6  mov     rcx, [rsp+300h+var_2B8]
0x1800334eb  mov     edx, 31000003h
0x1800334f0  call    cs:__imp_BcdSetElementData
0x1800334f6  mov     ebx, eax
0x1800334f8  test    eax, eax
0x1800334fa  js      loc_1800335E8
0x180033500  lea     rax, aBootSdi; "boot.sdi"
0x180033507  mov     r9, r15
0x18003350a  lea     r8, aSS_2; "%s%s"
0x180033511  mov     [rsp+300h+var_2E0], rax
0x180033516  mov     edx, 12Eh; unsigned __int64
0x18003351b  lea     rcx, [rsp+300h+var_2A0]; unsigned __int16 *
0x180033520  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033525  mov     r15d, eax
0x180033528  test    eax, eax
0x18003352a  jns     short loc_180033561
0x18003352c  mov     dword ptr [rsp+300h+var_2D8], 3FDh
0x180033534  lea     r8, aFailedToCreate_1; "failed to create boot.sdi file path"
0x18003353b  lea     rax, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180033542  mov     r9d, r15d
0x180033545  lea     rdx, aWinrecreateram; "winreCreateRamdiskOptions %s (0x%x) in "...
0x18003354c  mov     [rsp+300h+var_2E0], rax
0x180033551  mov     ecx, esi
0x180033553  call    UnattendLogW
0x180033558  movzx   edi, r15w
0x18003355c  jmp     loc_1800335FA
0x180033561  lea     r8, [rsp+300h+var_2C0]; unsigned __int64 *
0x180033566  mov     edx, 12Eh; unsigned __int64
0x18003356b  lea     rcx, [rsp+300h+var_2A0]; unsigned __int16 *
0x180033570  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180033575  mov     r15d, eax
0x180033578  test    eax, eax
0x18003357a  jns     short loc_18003358D
0x18003357c  mov     dword ptr [rsp+300h+var_2D8], 3FFh
0x180033584  lea     r8, aFailedToGetBoo_1; "failed to get boot.sdi path length"
0x18003358b  jmp     short loc_18003353B
0x18003358d  mov     r9d, dword ptr [rsp+300h+var_2C0]
0x180033592  lea     r8, [rsp+300h+var_2A0]
0x180033597  mov     rcx, [rsp+300h+var_2B8]
0x18003359c  mov     edx, 32000004h
0x1800335a1  lea     r9d, ds:2[r9*2]
0x1800335a9  call    cs:__imp_BcdSetElementData
0x1800335af  test    eax, eax
0x1800335b1  jns     short loc_1800335C5
0x1800335b3  mov     r8d, eax
0x1800335b6  lea     rdx, aBcdsetelementd_1; "BcdSetElementData failed: 0x%x"
0x1800335bd  mov     ecx, r13d
0x1800335c0  call    UnattendLogW
0x1800335c5  mov     rcx, [rsp+300h+var_2B8]
0x1800335ca  lea     r8, aWindowsRecover; "Windows Recovery"
0x1800335d1  mov     r9d, 24h ; '$'
0x1800335d7  mov     edx, 12000004h
0x1800335dc  call    cs:__imp_BcdSetElementData
0x1800335e2  mov     ebx, eax
0x1800335e4  test    eax, eax
0x1800335e6  jns     short loc_1800335FA
0x1800335e8  mov     r8d, eax
0x1800335eb  lea     rdx, aBcdsetelementd_1; "BcdSetElementData failed: 0x%x"
0x1800335f2  mov     ecx, r13d
0x1800335f5  call    UnattendLogW
0x1800335fa  test    r14, r14
0x1800335fd  jz      short loc_180033608
0x1800335ff  mov     rcx, r14; pv
0x180033602  call    cs:__imp_CoTaskMemFree
0x180033608  mov     rcx, [rsp+300h+var_2B8]
0x18003360d  test    rcx, rcx
0x180033610  jz      short loc_180033621
0x180033612  call    cs:__imp_BcdCloseObject
0x180033618  mov     [rsp+300h+var_2B8], 0
0x180033621  test    edi, edi
0x180033623  jz      short loc_18003363B
0x180033625  mov     r8d, edi
0x180033628  lea     rdx, aWinrecreateram_0; "winreCreateRamdiskOptions returning 0x%"...
0x18003362f  mov     ecx, r13d
0x180033632  call    UnattendLogW
0x180033637  mov     eax, edi
0x180033639  jmp     short loc_18003365D
0x18003363b  test    ebx, ebx
0x18003363d  jns     short loc_18003365B
0x18003363f  mov     r8d, ebx
0x180033642  lea     rdx, aWinrecreateram_0; "winreCreateRamdiskOptions returning 0x%"...
0x180033649  mov     ecx, r13d
0x18003364c  call    UnattendLogW
0x180033651  mov     ecx, ebx; Status
0x180033653  call    cs:__imp_RtlNtStatusToDosError
0x180033659  jmp     short loc_18003365D
0x18003365b  xor     eax, eax
0x18003365d  mov     rcx, [rbp+200h+var_40]
0x180033664  xor     rcx, rsp; StackCookie
0x180033667  call    __security_check_cookie
0x18003366c  add     rsp, 2D0h
0x180033673  pop     r15
0x180033675  pop     r14
0x180033677  pop     r13
0x180033679  pop     rdi
0x18003367a  pop     rsi
0x18003367b  pop     rbx
0x18003367c  pop     rbp
0x18003367d  retn
```
