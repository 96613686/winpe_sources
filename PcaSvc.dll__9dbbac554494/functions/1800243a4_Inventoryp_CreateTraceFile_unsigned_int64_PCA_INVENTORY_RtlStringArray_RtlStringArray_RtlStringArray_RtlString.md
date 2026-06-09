# Inventoryp_CreateTraceFile(unsigned __int64,_PCA_INVENTORY *,RtlStringArray *,RtlStringArray *,RtlStringArray *,RtlStringArray *,RtlNameValueArray *,PCA_INSTALLER_TYPE,int,unsigned __int64)

- ea: `0x1800243a4`
- end: `0x180024ada`
- name: `?Inventoryp_CreateTraceFile@@YAK_KPEAU_PCA_INVENTORY@@PEAVRtlStringArray@@222PEAVRtlNameValueArray@@W4PCA_INSTALLER_TYPE@@H0@Z`
- size: `1846`
- prototype: `__int64 __fastcall(unsigned __int64, __int64, ULONGLONG *, ULONGLONG *, ULONGLONG *, __int64, struct RtlNameValueArray *, int, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021b90`

## callees

- `0x180005820`
- `0x180007aec`
- `0x18000b76c`
- `0x18000cb00`
- `0x18000d530`
- `0x18000dc08`
- `0x180012920`
- `0x180013fac`
- `0x18001b320`
- `0x18001e688`
- `0x180020c44`
- `0x1800212b0`
- `0x1800243a4`
- `0x180024ae0`
- `0x1800ee5d0`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlGetNtSystemRoot` at `0x1800248a1`
- `ntdll!RtlGetNtSystemRoot` at `0x1800248a1`
- `ntdll!RtlFreeHeap` at `0x180024a81`
- `ntdll!RtlFreeHeap` at `0x180024aae`
- `ntdll!RtlFreeHeap` at `0x180024a81`
- `ntdll!RtlFreeHeap` at `0x180024aae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248f0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800248e6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800248e6`

## string_xrefs

- `0x18002456b`: `InstallShield`
- `0x18002455f`: `InstallAware`
- `0x1800248aa`: `%s\AppCompat\Programs\Install`
- `0x1800248ff`: `Failed to create directory [%d]`
- `0x1800248ce`: `Failed to create trace file name [%d]`
- `0x1800249c4`: `Failed to create trace file name [%d]`
- `0x18002446f`: `Inventoryp_CreateTraceFile`
- `0x1800244dd`: `Failed to add uninstall tag [%d]`
- `0x1800244c7`: `Uninstaller`
- `0x18002453b`: `AdvancedInstaller`
- `0x1800247cb`: `ArpCreate`
- `0x180024849`: `ArpCreate`
- `0x1800246d8`: `FileCreate`
- `0x180024757`: `FileCreate`
- `0x180024674`: `Failed to add MsiDetected [%d]`
- `0x18002465e`: `MsiDetected`
- `0x18002462e`: `Failed to add InstallerType [%d]`
- `0x180024618`: `InstallerType`
- `0x180024a4e`: `Summary,MsiDetected,%d,Files,%d,Keys,%d`
- `0x180024a13`: `TraceFileCreated,%S`
- `0x1800249a3`: `%s\INSTALL_%04x_%08lx-%04hx-%04hx-%02hx%02hx-%02hx%02hx%02hx%02hx%02hx%02hx.txt`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Inventoryp_CreateTraceFile(
        unsigned __int64 a1,
        __int64 a2,
        ULONGLONG *a3,
        ULONGLONG *a4,
        ULONGLONG *a5,
        __int64 a6,
        struct RtlNameValueArray *a7,
        int a8,
        int a9)
{
  void *v12; // rdx
  int appended; // eax
  unsigned int v14; // ebx
  const char *v15; // r9
  int v16; // r8d
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // rdi
  const unsigned __int16 *v19; // r9
  const unsigned __int16 *v20; // rdx
  int v21; // r12d
  ULONGLONG i; // rdi
  const unsigned __int16 **v23; // rdx
  const unsigned __int16 *v24; // rbx
  const unsigned __int16 *v25; // rdx
  ULONGLONG j; // rdi
  const unsigned __int16 **v27; // rdx
  const unsigned __int16 *v28; // rbx
  const unsigned __int16 *v29; // rdx
  int v30; // r15d
  ULONGLONG k; // rdi
  const unsigned __int16 *v32; // rdx
  const unsigned __int16 **v33; // r9
  ULONGLONG m; // rdi
  const unsigned __int16 *v35; // rdx
  __int64 v36; // r9
  ULONGLONG v37; // rcx
  const unsigned __int16 **v38; // r9
  __int64 NtSystemRoot; // rax
  int v40; // eax
  int v41; // eax
  struct _PCA_CHAIN *v42; // rax
  struct _PCA_CHAIN *v43; // rax
  unsigned __int64 v45; // [rsp+20h] [rbp-E0h]
  ULONGLONG pullResult; // [rsp+80h] [rbp-80h] BYREF
  HANDLE HeapHandle[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v48[2]; // [rsp+98h] [rbp-68h]
  PVOID P[2]; // [rsp+A8h] [rbp-58h]
  __int64 v50; // [rsp+B8h] [rbp-48h]
  __int64 v51; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v52; // [rsp+C8h] [rbp-38h]
  WCHAR PathName[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR FileName[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v51 = a2;
  v52 = a1;
  v50 = a6;
  RtlNameValueArray::RtlNameValueArray((RtlNameValueArray *)HeapHandle);
  if ( !(unsigned int)AslLogGetDefaultFlags() )
    goto LABEL_104;
  *(_OWORD *)HeapHandle = 0;
  *(_OWORD *)v48 = 0;
  *(_OWORD *)P = 0;
  if ( !a7 )
  {
    PcaTracePrintf("Inventory", 0, 0, "No attributes captured");
LABEL_104:
    v14 = 0;
    goto LABEL_105;
  }
  appended = RtlNameValueArray::Initialize((RtlNameValueArray *)HeapHandle, v12, 0x40u, 0x400u);
  v14 = appended;
  if ( appended )
  {
    v15 = "Failed to initialize attribute list [%d]";
    v16 = 342;
    goto LABEL_6;
  }
  appended = RtlNameValueArray::Assign((RtlNameValueArray *)HeapHandle, a7);
  v14 = appended;
  if ( appended )
  {
    v15 = "Failed to snapshot static attributes [%d]";
    v16 = 348;
    goto LABEL_6;
  }
  v18 = L"1";
  if ( *((_DWORD *)PcapChainFromHandle(a1) + 6) == 3 )
  {
    appended = RtlNameValueArray::Insert((RtlNameValueArray *)HeapHandle, v17, L"Uninstaller", L"1", v48[0]);
    v14 = appended;
    if ( appended )
    {
      v15 = "Failed to add uninstall tag [%d]";
      v16 = 363;
      goto LABEL_6;
    }
  }
  if ( a8 <= 8 )
  {
    switch ( a8 )
    {
      case 8:
        v19 = L"7-Zip";
        goto LABEL_49;
      case 0:
        v19 = L"Other";
        goto LABEL_49;
      case 1:
        v19 = L"MSI";
        goto LABEL_49;
      case 2:
        v19 = L"InstallShield";
        goto LABEL_49;
      case 3:
        v19 = L"InstallAware";
        goto LABEL_49;
      case 4:
        v19 = L"NullSoft";
        goto LABEL_49;
      case 5:
        v19 = L"Inno";
        goto LABEL_49;
      case 6:
        v19 = L"AdvancedInstaller";
        goto LABEL_49;
      case 7:
        v19 = L"DemoShield";
        goto LABEL_49;
    }
    goto LABEL_40;
  }
  switch ( a8 )
  {
    case 9:
      v19 = L"WinZip";
      break;
    case 10:
      v19 = L"Sonic";
      break;
    case 11:
      v19 = L"IllustrateSpoon";
      break;
    case 12:
      v19 = L"WinRAR";
      break;
    case 13:
      v19 = L"Astrum";
      break;
    case 14:
      v19 = L"Raphael";
      break;
    case 15:
      v19 = L"Gentee";
      break;
    case 16:
      v19 = L"Wise";
      break;
    default:
LABEL_40:
      v19 = L"Unknown";
      break;
  }
LABEL_49:
  appended = RtlNameValueArray::Insert((RtlNameValueArray *)HeapHandle, v17, L"InstallerType", v19, v48[0]);
  v14 = appended;
  if ( appended )
  {
    v15 = "Failed to add InstallerType [%d]";
    v16 = 449;
  }
  else
  {
    if ( !a9 )
      v18 = L"0";
    appended = RtlNameValueArray::Insert((RtlNameValueArray *)HeapHandle, v20, L"MsiDetected", v18, v48[0]);
    v14 = appended;
    if ( appended )
    {
      v15 = "Failed to add MsiDetected [%d]";
      v16 = 459;
    }
    else
    {
      v21 = 0;
      for ( i = 0; i < a3[2]; ++i )
      {
        pullResult = 0;
        if ( ULongLongMult(a3[1], i, &pullResult) < 0
          || (v23 = (const unsigned __int16 **)(a3[5] + pullResult), (unsigned __int64)v23 < a3[5]) )
        {
          v23 = 0;
        }
        v24 = *v23;
        if ( (unsigned int)PcaUtilityIsInventoryFile(*v23) )
        {
          appended = RtlNameValueArray::Insert((RtlNameValueArray *)HeapHandle, v25, L"FileCreate", v24, v48[0]);
          v14 = appended;
          if ( appended )
          {
            v15 = "Failed to add file name to report [%d]";
            v16 = 487;
            goto LABEL_6;
          }
          ++v21;
        }
      }
      for ( j = 0; j < a4[2]; ++j )
      {
        pullResult = 0;
        if ( ULongLongMult(a4[1], j, &pullResult) < 0
          || (v27 = (const unsigned __int16 **)(a4[5] + pullResult), (unsigned __int64)v27 < a4[5]) )
        {
          v27 = 0;
        }
        v28 = *v27;
        if ( (unsigned int)PcaUtilityIsInventoryFile(*v27) )
        {
          appended = RtlNameValueArray::Insert((RtlNameValueArray *)HeapHandle, v29, L"FileCreate", v28, v48[0]);
          v14 = appended;
          if ( appended )
          {
            v15 = "Failed to add file name to report [%d]";
            v16 = 506;
            goto LABEL_6;
          }
          ++v21;
        }
      }
      v30 = 0;
      for ( k = 0; k < a5[2]; ++k )
      {
        pullResult = 0;
        if ( ULongLongMult(a5[1], k, &pullResult) < 0
          || (v33 = (const unsigned __int16 **)(a5[5] + pullResult), (unsigned __int64)v33 < a5[5]) )
        {
          v33 = 0;
        }
        appended = RtlNameValueArray::Insert((RtlNameValueArray *)HeapHandle, v32, L"ArpCreate", *v33, v48[0]);
        v14 = appended;
        if ( appended )
        {
          v15 = "Failed to add arp key to report [%d]";
          v16 = 533;
          goto LABEL_6;
        }
        ++v30;
      }
      if ( !a5[2] )
      {
        for ( m = 0; m < *(_QWORD *)(v50 + 16); ++m )
        {
          pullResult = 0;
          if ( ULongLongMult(*(_QWORD *)(v50 + 8), m, &pullResult) < 0
            || (v37 = *(_QWORD *)(v36 + 40), v38 = (const unsigned __int16 **)(v37 + pullResult), v37 + pullResult < v37) )
          {
            v38 = 0;
          }
          appended = RtlNameValueArray::Insert((RtlNameValueArray *)HeapHandle, v35, L"ArpCreate", *v38, v48[0]);
          v14 = appended;
          if ( appended )
          {
            v15 = "Failed to add arp key to report [%d]";
            v16 = 548;
            goto LABEL_6;
          }
          ++v30;
        }
      }
      appended = RtlNameValueArray::AppendTimeStamp((RtlNameValueArray *)HeapHandle, L"StopTime");
      v14 = appended;
      if ( appended )
      {
        v15 = "Failed to add timestamp [%d]";
        v16 = 562;
      }
      else
      {
        NtSystemRoot = RtlGetNtSystemRoot();
        v40 = StringCchPrintfW(PathName, 0x104u, L"%s\\AppCompat\\Programs\\Install", NtSystemRoot);
        if ( v40 < 0 )
        {
          v14 = (unsigned __int16)v40;
          LODWORD(v45) = (unsigned __int16)v40;
          AslLogCallPrintf(
            1,
            (unsigned int)"Inventoryp_CreateTraceFile",
            576,
            (unsigned int)"Failed to create trace file name [%d]",
            v45);
          goto LABEL_105;
        }
        if ( CreateDirectoryW(PathName, 0) || (appended = GetLastError(), v14 = appended, appended == 183) )
        {
          LODWORD(v45) = 0xFFFF;
          v41 = StringCchPrintfW(
                  FileName,
                  0x104u,
                  L"%s\\INSTALL_%04x_%08lx-%04hx-%04hx-%02hx%02hx-%02hx%02hx%02hx%02hx%02hx%02hx.txt",
                  PathName,
                  v45,
                  *(_DWORD *)(v51 + 520),
                  *(unsigned __int16 *)(v51 + 524),
                  *(unsigned __int16 *)(v51 + 526),
                  *(unsigned __int8 *)(v51 + 528),
                  *(unsigned __int8 *)(v51 + 529),
                  *(unsigned __int8 *)(v51 + 530),
                  *(unsigned __int8 *)(v51 + 531),
                  *(unsigned __int8 *)(v51 + 532),
                  *(unsigned __int8 *)(v51 + 533),
                  *(unsigned __int8 *)(v51 + 534),
                  *(unsigned __int8 *)(v51 + 535));
          if ( v41 < 0 )
          {
            v14 = (unsigned __int16)v41;
            LODWORD(v45) = (unsigned __int16)v41;
            AslLogCallPrintf(
              1,
              (unsigned int)"Inventoryp_CreateTraceFile",
              606,
              (unsigned int)"Failed to create trace file name [%d]",
              v45);
            goto LABEL_105;
          }
          appended = PcaUtilityNameValueArraySaveToFile((struct RtlNameValueArray *)HeapHandle, FileName);
          v14 = appended;
          if ( !appended )
          {
            v42 = PcapChainFromHandle(v52);
            PcaTracePrintf("Inventory", *((_DWORD *)v42 + 4), 0, "TraceFileCreated,%S", FileName);
            v43 = PcapChainFromHandle(v52);
            PcaTracePrintf(
              "Inventory",
              *((_DWORD *)v43 + 4),
              0,
              "Summary,MsiDetected,%d,Files,%d,Keys,%d",
              a9 != 0,
              v21,
              v30);
            goto LABEL_104;
          }
          v15 = "Failed to save trace file [%d]";
          v16 = 612;
        }
        else
        {
          v15 = "Failed to create directory [%d]";
          v16 = 583;
        }
      }
    }
  }
LABEL_6:
  LODWORD(v45) = appended;
  AslLogCallPrintf(1, (unsigned int)"Inventoryp_CreateTraceFile", v16, (_DWORD)v15, v45);
LABEL_105:
  RtlStringArray::Clear((RtlStringArray *)HeapHandle);
  if ( P[1] )
    RtlFreeHeap(HeapHandle[0], 0, P[1]);
  *(_OWORD *)HeapHandle = 0;
  *(_OWORD *)v48 = 0;
  *(_OWORD *)P = 0;
  RtlStringArray::Clear((RtlStringArray *)HeapHandle);
  if ( P[1] )
    RtlFreeHeap(HeapHandle[0], 0, P[1]);
  return v14;
}

```

## disassembly

```asm
0x1800243a4  push    rbp
0x1800243a6  push    rbx
0x1800243a7  push    rsi
0x1800243a8  push    rdi
0x1800243a9  push    r12
0x1800243ab  push    r13
0x1800243ad  push    r14
0x1800243af  push    r15
0x1800243b1  lea     rbp, [rsp-408h]
0x1800243b9  sub     rsp, 508h
0x1800243c0  mov     rax, cs:__security_cookie
0x1800243c7  xor     rax, rsp
0x1800243ca  mov     [rbp+440h+var_50], rax
0x1800243d1  mov     r14, r9
0x1800243d4  mov     rsi, r8
0x1800243d7  mov     [rbp+440h+var_480], rdx
0x1800243db  mov     r15, rcx
0x1800243de  mov     [rbp+440h+var_478], rcx
0x1800243e2  mov     r13, [rbp+440h+arg_20]
0x1800243e9  mov     rax, [rbp+440h+arg_28]
0x1800243f0  mov     [rbp+440h+var_488], rax
0x1800243f4  mov     rdi, [rbp+440h+arg_30]
0x1800243fb  lea     rcx, [rbp+440h+HeapHandle]; this
0x1800243ff  call    ??0RtlNameValueArray@@QEAA@XZ; RtlNameValueArray::RtlNameValueArray(void)
0x180024404  nop
0x180024405  call    AslLogGetDefaultFlags
0x18002440a  test    eax, eax
0x18002440c  jz      loc_180024A67
0x180024412  xorps   xmm0, xmm0
0x180024415  movups  xmmword ptr [rbp+440h+HeapHandle], xmm0
0x180024419  movups  xmmword ptr [rbp+440h+var_4A8], xmm0
0x18002441d  movups  xmmword ptr [rbp+440h+P], xmm0
0x180024421  test    rdi, rdi
0x180024424  jnz     short loc_180024443
0x180024426  lea     r9, aNoAttributesCa; "No attributes captured"
0x18002442d  xor     r8d, r8d; unsigned int
0x180024430  xor     edx, edx; unsigned int
0x180024432  lea     rcx, aInventory_0; "Inventory"
0x180024439  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x18002443e  jmp     loc_180024A67
0x180024443  mov     r9d, 400h; unsigned __int64
0x180024449  mov     r8d, 40h ; '@'; unsigned __int64
0x18002444f  lea     rcx, [rbp+440h+HeapHandle]; this
0x180024453  call    ?Initialize@RtlNameValueArray@@QEAAJPEAX_K1@Z; RtlNameValueArray::Initialize(void *,unsigned __int64,unsigned __int64)
0x180024458  mov     ebx, eax
0x18002445a  test    eax, eax
0x18002445c  jz      short loc_180024485
0x18002445e  lea     r9, aFailedToInitia_13; "Failed to initialize attribute list [%d"...
0x180024465  mov     r8d, 156h
0x18002446b  mov     dword ptr [rsp+540h+var_520], eax
0x18002446f  lea     rdx, aInventorypCrea; "Inventoryp_CreateTraceFile"
0x180024476  mov     ecx, 1
0x18002447b  call    AslLogCallPrintf
0x180024480  jmp     loc_180024A69
0x180024485  mov     rdx, rdi; struct RtlNameValueArray *
0x180024488  lea     rcx, [rbp+440h+HeapHandle]; this
0x18002448c  call    ?Assign@RtlNameValueArray@@QEAAJPEAV1@@Z; RtlNameValueArray::Assign(RtlNameValueArray *)
0x180024491  mov     ebx, eax
0x180024493  test    eax, eax
0x180024495  jz      short loc_1800244A6
0x180024497  lea     r9, aFailedToSnapsh; "Failed to snapshot static attributes [%"...
0x18002449e  mov     r8d, 15Ch
0x1800244a4  jmp     short loc_18002446B
0x1800244a6  mov     rcx, r15; unsigned __int64
0x1800244a9  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800244ae  lea     rdi, a1; "1"
0x1800244b5  cmp     dword ptr [rax+18h], 3
0x1800244b9  jnz     short loc_1800244EF
0x1800244bb  mov     rax, [rbp+440h+var_4A8]
0x1800244bf  mov     [rsp+540h+var_520], rax; unsigned __int64
0x1800244c4  mov     r9, rdi; unsigned __int16 *
0x1800244c7  lea     r8, aUninstaller; "Uninstaller"
0x1800244ce  lea     rcx, [rbp+440h+HeapHandle]; this
0x1800244d2  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800244d7  mov     ebx, eax
0x1800244d9  test    eax, eax
0x1800244db  jz      short loc_1800244EF
0x1800244dd  lea     r9, aFailedToAddUni; "Failed to add uninstall tag [%d]"
0x1800244e4  mov     r8d, 16Bh
0x1800244ea  jmp     loc_18002446B
0x1800244ef  mov     ecx, [rbp+440h+arg_38]
0x1800244f5  cmp     ecx, 8
0x1800244f8  jg      loc_180024598
0x1800244fe  jz      loc_18002458F
0x180024504  test    ecx, ecx
0x180024506  jz      short loc_180024583
0x180024508  sub     ecx, 1
0x18002450b  jz      short loc_180024577
0x18002450d  sub     ecx, 1
0x180024510  jz      short loc_18002456B
0x180024512  sub     ecx, 1
0x180024515  jz      short loc_18002455F
0x180024517  sub     ecx, 1
0x18002451a  jz      short loc_180024553
0x18002451c  sub     ecx, 1
0x18002451f  jz      short loc_180024547
0x180024521  sub     ecx, 1
0x180024524  jz      short loc_18002453B
0x180024526  cmp     ecx, 1
0x180024529  jnz     loc_1800245C0
0x18002452f  lea     r9, aDemoshield_0; "DemoShield"
0x180024536  jmp     loc_18002460F
0x18002453b  lea     r9, aAdvancedinstal_0; "AdvancedInstaller"
0x180024542  jmp     loc_18002460F
0x180024547  lea     r9, aInno; "Inno"
0x18002454e  jmp     loc_18002460F
0x180024553  lea     r9, aNullsoft; "NullSoft"
0x18002455a  jmp     loc_18002460F
0x18002455f  lea     r9, aInstallaware; "InstallAware"
0x180024566  jmp     loc_18002460F
0x18002456b  lea     r9, aInstallshield_0; "InstallShield"
0x180024572  jmp     loc_18002460F
0x180024577  lea     r9, aMsi; "MSI"
0x18002457e  jmp     loc_18002460F
0x180024583  lea     r9, aOther_0; "Other"
0x18002458a  jmp     loc_18002460F
0x18002458f  lea     r9, a7Zip; "7-Zip"
0x180024596  jmp     short loc_18002460F
0x180024598  sub     ecx, 9
0x18002459b  jz      short loc_180024608
0x18002459d  sub     ecx, 1
0x1800245a0  jz      short loc_1800245FF
0x1800245a2  sub     ecx, 1
0x1800245a5  jz      short loc_1800245F6
0x1800245a7  sub     ecx, 1
0x1800245aa  jz      short loc_1800245ED
0x1800245ac  sub     ecx, 1
0x1800245af  jz      short loc_1800245E4
0x1800245b1  sub     ecx, 1
0x1800245b4  jz      short loc_1800245DB
0x1800245b6  sub     ecx, 1
0x1800245b9  jz      short loc_1800245D2
0x1800245bb  cmp     ecx, 1
0x1800245be  jz      short loc_1800245C9
0x1800245c0  lea     r9, aUnknown_0; "Unknown"
0x1800245c7  jmp     short loc_18002460F
0x1800245c9  lea     r9, aWise_0; "Wise"
0x1800245d0  jmp     short loc_18002460F
0x1800245d2  lea     r9, aGentee_0; "Gentee"
0x1800245d9  jmp     short loc_18002460F
0x1800245db  lea     r9, aRaphael; "Raphael"
0x1800245e2  jmp     short loc_18002460F
0x1800245e4  lea     r9, aAstrum; "Astrum"
0x1800245eb  jmp     short loc_18002460F
0x1800245ed  lea     r9, aWinrar_0; "WinRAR"
0x1800245f4  jmp     short loc_18002460F
0x1800245f6  lea     r9, aIllustratespoo_0; "IllustrateSpoon"
0x1800245fd  jmp     short loc_18002460F
0x1800245ff  lea     r9, aSonic; "Sonic"
0x180024606  jmp     short loc_18002460F
0x180024608  lea     r9, aWinzip_0; "WinZip"
0x18002460f  mov     rax, [rbp+440h+var_4A8]
0x180024613  mov     [rsp+540h+var_520], rax; unsigned __int64
0x180024618  lea     r8, aInstallertype; "InstallerType"
0x18002461f  lea     rcx, [rbp+440h+HeapHandle]; this
0x180024623  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x180024628  mov     ebx, eax
0x18002462a  test    eax, eax
0x18002462c  jz      short loc_180024640
0x18002462e  lea     r9, aFailedToAddIns; "Failed to add InstallerType [%d]"
0x180024635  mov     r8d, 1C1h
0x18002463b  jmp     loc_18002446B
0x180024640  lea     rax, a0_0; "0"
0x180024647  cmp     [rbp+440h+arg_40], 0
0x18002464e  cmovz   rdi, rax
0x180024652  mov     rax, [rbp+440h+var_4A8]
0x180024656  mov     [rsp+540h+var_520], rax; unsigned __int64
0x18002465b  mov     r9, rdi; unsigned __int16 *
0x18002465e  lea     r8, aMsidetected; "MsiDetected"
0x180024665  lea     rcx, [rbp+440h+HeapHandle]; this
0x180024669  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18002466e  mov     ebx, eax
0x180024670  test    eax, eax
0x180024672  jz      short loc_180024686
0x180024674  lea     r9, aFailedToAddMsi_1; "Failed to add MsiDetected [%d]"
0x18002467b  mov     r8d, 1CBh
0x180024681  jmp     loc_18002446B
0x180024686  xor     r12d, r12d
0x180024689  xor     edi, edi
0x18002468b  cmp     rdi, [rsi+10h]
0x18002468f  jnb     short loc_180024708
0x180024691  mov     [rbp+440h+pullResult], 0
0x180024699  lea     r8, [rbp+440h+pullResult]; pullResult
0x18002469d  mov     rdx, rdi; ullMultiplier
0x1800246a0  mov     rcx, [rsi+8]; ullMultiplicand
0x1800246a4  call    ULongLongMult
0x1800246a9  test    eax, eax
0x1800246ab  js      short loc_1800246BB
0x1800246ad  mov     rdx, [rbp+440h+pullResult]
0x1800246b1  add     rdx, [rsi+28h]
0x1800246b5  cmp     rdx, [rsi+28h]
0x1800246b9  jnb     short loc_1800246BD
0x1800246bb  xor     edx, edx
0x1800246bd  mov     rbx, [rdx]
0x1800246c0  mov     rcx, rbx; unsigned __int16 *
0x1800246c3  call    ?PcaUtilityIsInventoryFile@@YAHPEBG@Z; PcaUtilityIsInventoryFile(ushort const *)
0x1800246c8  test    eax, eax
0x1800246ca  jz      short loc_1800246F1
0x1800246cc  mov     rax, [rbp+440h+var_4A8]
0x1800246d0  mov     [rsp+540h+var_520], rax; unsigned __int64
0x1800246d5  mov     r9, rbx; unsigned __int16 *
0x1800246d8  lea     r8, aFilecreate; "FileCreate"
0x1800246df  lea     rcx, [rbp+440h+HeapHandle]; this
0x1800246e3  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800246e8  mov     ebx, eax
0x1800246ea  test    eax, eax
0x1800246ec  jnz     short loc_1800246F6
0x1800246ee  inc     r12d
0x1800246f1  inc     rdi
0x1800246f4  jmp     short loc_18002468B
0x1800246f6  lea     r9, aFailedToAddFil; "Failed to add file name to report [%d]"
0x1800246fd  mov     r8d, 1E7h
0x180024703  jmp     loc_18002446B
0x180024708  xor     edi, edi
0x18002470a  cmp     rdi, [r14+10h]
0x18002470e  jnb     short loc_180024787
0x180024710  mov     [rbp+440h+pullResult], 0
0x180024718  lea     r8, [rbp+440h+pullResult]; pullResult
0x18002471c  mov     rdx, rdi; ullMultiplier
0x18002471f  mov     rcx, [r14+8]; ullMultiplicand
0x180024723  call    ULongLongMult
0x180024728  test    eax, eax
0x18002472a  js      short loc_18002473A
0x18002472c  mov     rdx, [rbp+440h+pullResult]
0x180024730  add     rdx, [r14+28h]
0x180024734  cmp     rdx, [r14+28h]
0x180024738  jnb     short loc_18002473C
0x18002473a  xor     edx, edx
0x18002473c  mov     rbx, [rdx]
0x18002473f  mov     rcx, rbx; unsigned __int16 *
0x180024742  call    ?PcaUtilityIsInventoryFile@@YAHPEBG@Z; PcaUtilityIsInventoryFile(ushort const *)
0x180024747  test    eax, eax
0x180024749  jz      short loc_180024770
0x18002474b  mov     rax, [rbp+440h+var_4A8]
0x18002474f  mov     [rsp+540h+var_520], rax; unsigned __int64
0x180024754  mov     r9, rbx; unsigned __int16 *
0x180024757  lea     r8, aFilecreate; "FileCreate"
0x18002475e  lea     rcx, [rbp+440h+HeapHandle]; this
0x180024762  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x180024767  mov     ebx, eax
0x180024769  test    eax, eax
0x18002476b  jnz     short loc_180024775
0x18002476d  inc     r12d
0x180024770  inc     rdi
0x180024773  jmp     short loc_18002470A
0x180024775  lea     r9, aFailedToAddFil; "Failed to add file name to report [%d]"
0x18002477c  mov     r8d, 1FAh
0x180024782  jmp     loc_18002446B
0x180024787  xor     r15d, r15d
0x18002478a  xor     edi, edi
0x18002478c  cmp     rdi, [r13+10h]
0x180024790  jnb     short loc_1800247FB
0x180024792  mov     [rbp+440h+pullResult], 0
0x18002479a  lea     r8, [rbp+440h+pullResult]; pullResult
0x18002479e  mov     rdx, rdi; ullMultiplier
0x1800247a1  mov     rcx, [r13+8]; ullMultiplicand
0x1800247a5  call    ULongLongMult
0x1800247aa  test    eax, eax
0x1800247ac  js      short loc_1800247BC
0x1800247ae  mov     r9, [rbp+440h+pullResult]
0x1800247b2  add     r9, [r13+28h]
0x1800247b6  cmp     r9, [r13+28h]
0x1800247ba  jnb     short loc_1800247BF
0x1800247bc  xor     r9d, r9d
0x1800247bf  mov     rax, [rbp+440h+var_4A8]
0x1800247c3  mov     [rsp+540h+var_520], rax; unsigned __int64
0x1800247c8  mov     r9, [r9]; unsigned __int16 *
0x1800247cb  lea     r8, aArpcreate; "ArpCreate"
0x1800247d2  lea     rcx, [rbp+440h+HeapHandle]; this
0x1800247d6  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800247db  mov     ebx, eax
0x1800247dd  test    eax, eax
0x1800247df  jnz     short loc_1800247E9
0x1800247e1  inc     r15d
0x1800247e4  inc     rdi
0x1800247e7  jmp     short loc_18002478C
0x1800247e9  lea     r9, aFailedToAddArp; "Failed to add arp key to report [%d]"
0x1800247f0  mov     r8d, 215h
0x1800247f6  jmp     loc_18002446B
0x1800247fb  cmp     qword ptr [r13+10h], 0
0x180024800  jnz     short loc_180024879
0x180024802  xor     edi, edi
0x180024804  mov     r9, [rbp+440h+var_488]
0x180024808  cmp     rdi, [r9+10h]
0x18002480c  jnb     short loc_180024879
0x18002480e  mov     [rbp+440h+pullResult], 0
0x180024816  lea     r8, [rbp+440h+pullResult]; pullResult
0x18002481a  mov     rdx, rdi; ullMultiplier
0x18002481d  mov     rcx, [r9+8]; ullMultiplicand
0x180024821  call    ULongLongMult
0x180024826  test    eax, eax
0x180024828  js      short loc_18002483A
0x18002482a  mov     rcx, [r9+28h]
0x18002482e  mov     r9, [rbp+440h+pullResult]
0x180024832  add     r9, rcx
0x180024835  cmp     r9, rcx
0x180024838  jnb     short loc_18002483D
0x18002483a  xor     r9d, r9d
0x18002483d  mov     rax, [rbp+440h+var_4A8]
0x180024841  mov     [rsp+540h+var_520], rax; unsigned __int64
  ... truncated ...
```
