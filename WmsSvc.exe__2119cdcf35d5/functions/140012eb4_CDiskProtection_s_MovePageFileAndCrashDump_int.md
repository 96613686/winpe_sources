# CDiskProtection::s_MovePageFileAndCrashDump(int *)

- ea: `0x140012eb4`
- end: `0x140013658`
- name: `?s_MovePageFileAndCrashDump@CDiskProtection@@KAJPEAH@Z`
- size: `1956`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140009af0`

## callees

- `0x14000f664`
- `0x140010538`
- `0x140011148`
- `0x140011534`
- `0x1400119f4`
- `0x140011b70`
- `0x140012158`
- `0x1400125c4`
- `0x140012eb4`
- `0x14001381c`
- `0x140014f04`
- `0x140015134`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140067254`
- `0x14006c434`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x14001329f`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x14001329f`
- `KERNEL32!GetLastError` at `0x1400132ad`
- `KERNEL32!GetLastError` at `0x1400132ad`
- `KERNEL32!IsDebuggerPresent` at `0x140012fa3`
- `KERNEL32!IsDebuggerPresent` at `0x14001305e`
- `KERNEL32!IsDebuggerPresent` at `0x1400130e6`
- `KERNEL32!IsDebuggerPresent` at `0x14001319b`
- `KERNEL32!IsDebuggerPresent` at `0x140013257`
- `KERNEL32!IsDebuggerPresent` at `0x140013308`
- `KERNEL32!IsDebuggerPresent` at `0x1400133cd`
- `KERNEL32!IsDebuggerPresent` at `0x140012fa3`
- `KERNEL32!IsDebuggerPresent` at `0x14001305e`
- `KERNEL32!IsDebuggerPresent` at `0x1400130e6`
- `KERNEL32!IsDebuggerPresent` at `0x14001319b`
- `KERNEL32!IsDebuggerPresent` at `0x140013257`
- `KERNEL32!IsDebuggerPresent` at `0x140013308`
- `KERNEL32!IsDebuggerPresent` at `0x1400133cd`
- `ole32!CoCreateInstance` at `0x140012f5b`
- `ole32!CoCreateInstance` at `0x140012f5b`

## string_xrefs

- `0x140012ee1`: `CDiskProtection::s_MovePageFileAndCrashDump\n`
- `0x140012f76`: `CDiskProtection::s_MovePageFileAndCrashDump`
- `0x140013031`: `CDiskProtection::s_MovePageFileAndCrashDump`
- `0x1400130b9`: `CDiskProtection::s_MovePageFileAndCrashDump`
- `0x140013172`: `CDiskProtection::s_MovePageFileAndCrashDump`
- `0x14001322e`: `CDiskProtection::s_MovePageFileAndCrashDump`
- `0x1400132d0`: `CDiskProtection::s_MovePageFileAndCrashDump`
- `0x140013380`: `CDiskProtection::s_MovePageFileAndCrashDump`
- `0x14001344f`: `CDiskProtection::s_MovePageFileAndCrashDump`
- `0x14001307e`: `CDiskProtection::s_MovePageFileAndCrashDump - calling pService->WaitForServiceReady ()\n`
- `0x14001309c`: `CDiskProtection::s_MovePageFileAndCrashDump - pService->WaitForServiceReady () returned 0x%08x\n`
- `0x140013286`: `CDiskProtection::s_MovePageFileAndCrashDump - Found existing reserve volume %s\n`
- `0x1400134d9`: `Unable to create the DpReserved partition; no more partitions can be created on this disk.`
- `0x140013509`: `CDiskProtection::s_MovePageFileAndCrashDump - Shrunk the system volume by %I64u GB (%I64u bytes)\n`
- `0x1400135bd`: `CDiskProtection::s_MovePageFileAndCrashDump - Replacing VDS error code 0x%X with ERROR_DISK_FULL.\n`
- `0x1400135d0`: `CDiskProtection::s_MovePageFileAndCrashDump - Exiting, hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_MovePageFileAndCrashDump(int *a1)
{
  struct IVdsVolume *v2; // r12
  struct IVdsDisk *v3; // r13
  HRESULT v4; // eax
  __int64 v5; // rbx
  __int64 v6; // r9
  __int64 v7; // r8
  int v8; // eax
  WCHAR v9; // di
  unsigned __int16 v10; // si
  bool v11; // zf
  const unsigned __int16 *v12; // rax
  __int64 v13; // r9
  __int64 v14; // r8
  signed int LastError; // eax
  const wchar_t *v16; // rax
  __int64 v17; // r9
  int Volume; // eax
  int DiskFromVolume; // eax
  unsigned __int64 v20; // r14
  enum _ACCESS_MODE v21; // r8d
  enum _ACCESS_MODE v22; // r8d
  unsigned __int16 v24[2]; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 v25; // [rsp+44h] [rbp-45h] BYREF
  unsigned __int16 v26[2]; // [rsp+48h] [rbp-41h] BYREF
  int v27; // [rsp+4Ch] [rbp-3Dh] BYREF
  struct IVdsService *v28; // [rsp+50h] [rbp-39h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-31h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int64 v31; // [rsp+68h] [rbp-21h] BYREF
  struct IVdsDisk *v32; // [rsp+70h] [rbp-19h] BYREF
  struct IVdsVolume *v33; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int64 v34; // [rsp+80h] [rbp-9h] BYREF
  WCHAR DirectoryName[4]; // [rsp+88h] [rbp-1h] BYREF

  v24[0] = 0;
  v26[0] = 0;
  v2 = 0;
  v25 = 0;
  v3 = 0;
  v27 = 0;
  wcscpy(DirectoryName, L"C:\\");
  v31 = 0;
  v34 = 0;
  TotalNumberOfBytes.QuadPart = 0;
  v28 = 0;
  ppv = 0;
  v33 = 0;
  v32 = 0;
  DEBUGMSG(L"CDiskProtection::s_MovePageFileAndCrashDump\n");
  v4 = CoCreateInstance(&CLSID_VdsLoader, 0, 4u, &GUID_e0393303_90d4_4a97_ab71_e9b671ee2729, &ppv);
  LODWORD(v5) = v4;
  if ( v4 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x1649u,
      L"CDiskProtection::s_MovePageFileAndCrashDump",
      L"CHRA",
      L"hr",
      v4);
    if ( IsDebuggerPresent() )
    {
      v6 = 5705;
LABEL_4:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v6,
        L"CDiskProtection::s_MovePageFileAndCrashDump",
        L"CHRA",
        L"hr",
        v5);
      goto LABEL_62;
    }
    v7 = 5705;
    goto LABEL_7;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IVdsService **))(*(_QWORD *)ppv + 24LL))(ppv, 0, &v28);
  LODWORD(v5) = v8;
  if ( v8 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x164Cu,
      L"CDiskProtection::s_MovePageFileAndCrashDump",
      L"CHRA",
      L"hr",
      v8);
    if ( IsDebuggerPresent() )
    {
      v6 = 5708;
      goto LABEL_4;
    }
    v7 = 5708;
LABEL_7:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v7,
      L"CDiskProtection::s_MovePageFileAndCrashDump",
      L"CHRA",
      L"hr",
      v5);
    goto LABEL_62;
  }
  DEBUGMSG(L"CDiskProtection::s_MovePageFileAndCrashDump - calling pService->WaitForServiceReady ()\n");
  v5 = ((unsigned int (__fastcall *)(struct IVdsService *))v28->lpVtbl->WaitForServiceReady)(v28);
  DEBUGMSG(L"CDiskProtection::s_MovePageFileAndCrashDump - pService->WaitForServiceReady () returned 0x%08x\n", v5);
  if ( (int)v5 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x1651u,
      L"CDiskProtection::s_MovePageFileAndCrashDump",
      L"CHRA",
      L"hr",
      v5);
    if ( IsDebuggerPresent() )
    {
      v6 = 5713;
      goto LABEL_4;
    }
    v7 = 5713;
    goto LABEL_7;
  }
  LODWORD(v5) = GetSystemVolumeDriveLetter(v24);
  if ( (int)v5 >= 0 )
  {
    LODWORD(v5) = CDiskProtection::s_GetMinimumReservedVolumeSize(&v31);
    if ( (int)v5 >= 0 )
    {
      LODWORD(v5) = CDiskProtection::s_GetReserveVolume(&v25);
      if ( (int)v5 >= 0 )
      {
        v9 = v25;
        v10 = v24[0];
        if ( v25 )
        {
          if ( v25 == v24[0] )
          {
            LODWORD(v5) = -2147418113;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              0x1665u,
              L"CDiskProtection::s_MovePageFileAndCrashDump",
              L"CBRAEx",
              L"chExistingReserveVolume != chSystemVolumeDriveLetter",
              -2147418113);
            v11 = !IsDebuggerPresent();
            v12 = L"chExistingReserveVolume != chSystemVolumeDriveLetter";
            if ( !v11 )
            {
              v13 = 5733;
LABEL_24:
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                v13,
                L"CDiskProtection::s_MovePageFileAndCrashDump",
                L"CBRAEx",
                v12,
                -2147418113);
              goto LABEL_66;
            }
            v14 = 5733;
            goto LABEL_27;
          }
          if ( v25 <= 0x43u )
          {
            LODWORD(v5) = -2147418113;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              0x1666u,
              L"CDiskProtection::s_MovePageFileAndCrashDump",
              L"CBRAEx",
              L"chExistingReserveVolume > L'C'",
              -2147418113);
            v11 = !IsDebuggerPresent();
            v12 = L"chExistingReserveVolume > L'C'";
            if ( !v11 )
            {
              v13 = 5734;
              goto LABEL_24;
            }
            v14 = 5734;
LABEL_27:
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              v14,
              L"CDiskProtection::s_MovePageFileAndCrashDump",
              L"CBRAEx",
              v12,
              -2147418113);
            goto LABEL_66;
          }
          DirectoryName[0] = v25;
          DEBUGMSG(L"CDiskProtection::s_MovePageFileAndCrashDump - Found existing reserve volume %s\n", DirectoryName);
          if ( !GetDiskFreeSpaceExW(DirectoryName, 0, &TotalNumberOfBytes, 0) )
          {
            LastError = GetLastError();
            LODWORD(v5) = LastError;
            if ( LastError > 0 )
              LODWORD(v5) = (unsigned __int16)LastError | 0x80070000;
            if ( (int)v5 >= 0 )
              LODWORD(v5) = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              0x166Du,
              L"CDiskProtection::s_MovePageFileAndCrashDump",
              L"CBRAEx",
              L"fSuccess",
              v5);
            if ( IsDebuggerPresent() )
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                5741,
                L"CDiskProtection::s_MovePageFileAndCrashDump",
                L"CBRAEx",
                L"fSuccess",
                v5);
            else
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                5741,
                L"CDiskProtection::s_MovePageFileAndCrashDump",
                L"CBRAEx",
                L"fSuccess",
                v5);
            goto LABEL_62;
          }
          if ( TotalNumberOfBytes.QuadPart < v31 - v31 / 0xA )
          {
            LODWORD(v5) = -2147024784;
            DEBUGMSGLEVEL(
              4u,
              L"%s(%d) - %s - Test failed:  %s\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              5744,
              L"CDiskProtection::s_MovePageFileAndCrashDump",
              L"Existing reserve volume is too small.");
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              0x1670u,
              L"CDiskProtection::s_MovePageFileAndCrashDump",
              L"CBRLAEx",
              L"cbExistingReservedVolumeSize.QuadPart >= (cbMinimumReservedVolumeSize - cbMinimumReservedVolumeSize/10)",
              -2147024784);
            if ( IsDebuggerPresent() )
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                5744,
                L"CDiskProtection::s_MovePageFileAndCrashDump",
                L"CBRLAEx",
                L"cbExistingReservedVolumeSize.QuadPart >= (cbMinimumReservedVolumeSize - cbMinimumReservedVolumeSize/10)",
                -2147024784);
            else
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                5744,
                L"CDiskProtection::s_MovePageFileAndCrashDump",
                L"CBRLAEx",
                L"cbExistingReservedVolumeSize.QuadPart >= (cbMinimumReservedVolumeSize - cbMinimumReservedVolumeSize/10)",
                -2147024784);
            goto LABEL_66;
          }
          LODWORD(v5) = CDiskProtection::s_DoesVolumeContainPageFileAndCrashDump(v9, 0, &v27);
          if ( (int)v5 >= 0 )
          {
            if ( v27 )
            {
              LODWORD(v5) = 0;
              v16 = L"Specified volume contains page file and crash dump - OK!";
              v17 = 5749;
LABEL_48:
              DEBUGMSGLEVEL(
                4u,
                L"%s(%d) - %s - Test failed:  %s\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                v17,
                L"CDiskProtection::s_MovePageFileAndCrashDump",
                v16);
              goto LABEL_66;
            }
LABEL_58:
            LODWORD(v5) = CDiskProtection::s_PopulateReserveVolume(v10, v9);
            if ( (int)v5 >= 0 )
            {
              LODWORD(v5) = CDiskProtection::s_SetReserveVolume(v9);
              if ( (int)v5 >= 0 )
              {
                *a1 = 1;
                LODWORD(v5) = CUserManagement::s_SetFileAccessForWellKnownSid(DirectoryName, WinBuiltinUsersSid, v21);
                if ( (int)v5 >= 0 )
                  LODWORD(v5) = CUserManagement::s_SetFileAccessForWellKnownSid(DirectoryName, WinWorldSid, v22);
              }
            }
          }
        }
        else
        {
          v27 = 0;
          Volume = CDiskProtection::s_GetVolume(v28, v24[0], &v33);
          v2 = v33;
          LODWORD(v5) = Volume;
          if ( Volume >= 0 )
          {
            DiskFromVolume = CDiskProtection::s_GetDiskFromVolume(v28, v33, &v32);
            v3 = v32;
            LODWORD(v5) = DiskFromVolume;
            if ( DiskFromVolume >= 0 )
            {
              LODWORD(v5) = CDiskProtection::s_GetDataPartitionCount(v32, &v27);
              if ( (int)v5 >= 0 )
              {
                if ( v27 >= 4 )
                {
                  LODWORD(v5) = -2147212281;
                  v16 = L"Unable to create the DpReserved partition; no more partitions can be created on this disk.";
                  v17 = 5770;
                  goto LABEL_48;
                }
                LODWORD(v5) = CDiskProtection::s_ShrinkVolume(v2, v31, &v34);
                if ( (int)v5 >= 0 )
                {
                  v20 = v34;
                  DEBUGMSG(
                    L"CDiskProtection::s_MovePageFileAndCrashDump - Shrunk the system volume by %I64u GB (%I64u bytes)\n",
                    v34 >> 30,
                    v34);
                  LODWORD(v5) = CDiskProtection::s_GetNextAvailableDriveLetter(v28, v26);
                  if ( (int)v5 >= 0 )
                  {
                    v9 = v26[0];
                    LODWORD(v5) = CDiskProtection::s_CreateAndFormatPrimaryPartition(v28, v3, v20, v26[0]);
                    if ( (int)v5 >= 0 )
                    {
                      DirectoryName[0] = v9;
                      goto LABEL_58;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_62:
  if ( (unsigned int)(v5 + 2147211917) <= 1 || (unsigned int)(v5 + 2147211242) <= 1 || (_DWORD)v5 == -2147210974 )
  {
    DEBUGMSG(
      L"CDiskProtection::s_MovePageFileAndCrashDump - Replacing VDS error code 0x%X with ERROR_DISK_FULL.\n",
      (unsigned int)v5);
    LODWORD(v5) = -2147024784;
  }
LABEL_66:
  DEBUGMSG(L"CDiskProtection::s_MovePageFileAndCrashDump - Exiting, hr = 0x%08X\n", (unsigned int)v5);
  if ( v3 )
    ((void (__fastcall *)(struct IVdsDisk *))v3->lpVtbl->Release)(v3);
  if ( v2 )
    ((void (__fastcall *)(struct IVdsVolume *))v2->lpVtbl->Release)(v2);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v28 )
    ((void (__fastcall *)(struct IVdsService *))v28->lpVtbl->Release)(v28);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140012eb4  push    rbp
0x140012eb6  push    rbx
0x140012eb7  push    rsi
0x140012eb8  push    rdi
0x140012eb9  push    r12
0x140012ebb  push    r13
0x140012ebd  push    r14
0x140012ebf  push    r15
0x140012ec1  lea     rbp, [rsp-1Fh]
0x140012ec6  sub     rsp, 0A8h
0x140012ecd  mov     rax, cs:__security_cookie
0x140012ed4  xor     rax, rsp
0x140012ed7  mov     [rbp+57h+var_50], rax
0x140012edb  xor     r14d, r14d
0x140012ede  mov     r15, rcx
0x140012ee1  lea     rcx, aCdiskprotectio_161; "CDiskProtection::s_MovePageFileAndCrash"...
0x140012ee8  mov     [rbp+57h+var_A0], r14w
0x140012eed  mov     [rbp+57h+var_98], r14w
0x140012ef2  mov     r12d, r14d
0x140012ef5  mov     [rbp+57h+var_9C], r14w
0x140012efa  mov     r13d, r14d
0x140012efd  lea     eax, [r14+43h]
0x140012f01  mov     [rbp+57h+var_94], r14d
0x140012f05  mov     [rbp+57h+DirectoryName], ax
0x140012f09  mov     eax, dword ptr cs:aC_0+2; ":\\"
0x140012f0f  mov     [rbp+57h+var_56], eax
0x140012f12  movzx   eax, word ptr cs:aC_0+6; ""
0x140012f19  mov     [rbp+57h+var_52], ax
0x140012f1d  mov     [rbp+57h+var_78], r14
0x140012f21  mov     [rbp+57h+var_60], r14
0x140012f25  mov     qword ptr [rbp+57h+TotalNumberOfBytes], r14
0x140012f29  mov     [rbp+57h+var_90], r14
0x140012f2d  mov     [rbp+57h+var_88], r14
0x140012f31  mov     [rbp+57h+var_68], r14
0x140012f35  mov     [rbp+57h+var_70], r14
0x140012f39  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140012f3e  lea     rax, [rbp+57h+var_88]
0x140012f42  xor     edx, edx; pUnkOuter
0x140012f44  lea     r9, _GUID_e0393303_90d4_4a97_ab71_e9b671ee2729; riid
0x140012f4b  mov     [rsp+0E0h+ppv], rax; ppv
0x140012f50  lea     r8d, [r14+4]; dwClsContext
0x140012f54  lea     rcx, CLSID_VdsLoader; rclsid
0x140012f5b  call    cs:__imp_CoCreateInstance
0x140012f61  mov     ebx, eax
0x140012f63  test    eax, eax
0x140012f65  jns     loc_14001300A
0x140012f6b  mov     [rsp+0E0h+var_B8], eax; int
0x140012f6f  lea     r15, aChra; "CHRA"
0x140012f76  lea     rsi, aCdiskprotectio_54; "CDiskProtection::s_MovePageFileAndCrash"...
0x140012f7d  mov     r9, r15; unsigned __int16 *
0x140012f80  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140012f87  mov     r8, rsi; unsigned __int16 *
0x140012f8a  lea     r14, aHr; "hr"
0x140012f91  mov     rcx, rdi; unsigned __int16 *
0x140012f94  mov     edx, 1649h; unsigned int
0x140012f99  mov     [rsp+0E0h+ppv], r14; unsigned __int16 *
0x140012f9e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140012fa3  call    cs:__imp_IsDebuggerPresent
0x140012fa9  test    eax, eax
0x140012fab  jz      short loc_140012FDF
0x140012fad  mov     r9d, 1649h
0x140012fb3  mov     [rsp+0E0h+var_A8], ebx
0x140012fb7  mov     [rsp+0E0h+var_B0], r14
0x140012fbc  mov     qword ptr [rsp+0E0h+var_B8], r15
0x140012fc1  mov     r8, rdi
0x140012fc4  mov     [rsp+0E0h+ppv], rsi
0x140012fc9  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140012fd0  mov     ecx, 2; unsigned __int8
0x140012fd5  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140012fda  jmp     loc_14001359D
0x140012fdf  mov     r8d, 1649h
0x140012fe5  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x140012fe9  mov     qword ptr [rsp+0E0h+var_B8], r14
0x140012fee  mov     [rsp+0E0h+ppv], r15
0x140012ff3  mov     r9, rsi
0x140012ff6  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140012ffd  mov     rdx, rdi
0x140013000  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140013005  jmp     loc_14001359D
0x14001300a  mov     rcx, [rbp+57h+var_88]
0x14001300e  lea     r8, [rbp+57h+var_90]
0x140013012  xor     edx, edx
0x140013014  mov     rax, [rcx]
0x140013017  mov     rax, [rax+18h]
0x14001301b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013020  mov     ebx, eax
0x140013022  test    eax, eax
0x140013024  jns     short loc_14001307E
0x140013026  mov     [rsp+0E0h+var_B8], eax; int
0x14001302a  lea     r15, aChra; "CHRA"
0x140013031  lea     rsi, aCdiskprotectio_54; "CDiskProtection::s_MovePageFileAndCrash"...
0x140013038  mov     r9, r15; unsigned __int16 *
0x14001303b  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013042  mov     r8, rsi; unsigned __int16 *
0x140013045  lea     r14, aHr; "hr"
0x14001304c  mov     rcx, rdi; unsigned __int16 *
0x14001304f  mov     edx, 164Ch; unsigned int
0x140013054  mov     [rsp+0E0h+ppv], r14; unsigned __int16 *
0x140013059  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001305e  call    cs:__imp_IsDebuggerPresent
0x140013064  test    eax, eax
0x140013066  jz      short loc_140013073
0x140013068  mov     r9d, 164Ch
0x14001306e  jmp     loc_140012FB3
0x140013073  mov     r8d, 164Ch
0x140013079  jmp     loc_140012FE5
0x14001307e  lea     rcx, aCdiskprotectio_94; "CDiskProtection::s_MovePageFileAndCrash"...
0x140013085  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001308a  mov     rcx, [rbp+57h+var_90]
0x14001308e  mov     rax, [rcx]
0x140013091  mov     rax, [rax+20h]
0x140013095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001309a  mov     edx, eax
0x14001309c  lea     rcx, aCdiskprotectio_44; "CDiskProtection::s_MovePageFileAndCrash"...
0x1400130a3  mov     ebx, eax
0x1400130a5  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400130aa  test    ebx, ebx
0x1400130ac  jns     short loc_140013106
0x1400130ae  lea     r15, aChra; "CHRA"
0x1400130b5  mov     [rsp+0E0h+var_B8], ebx; int
0x1400130b9  lea     rsi, aCdiskprotectio_54; "CDiskProtection::s_MovePageFileAndCrash"...
0x1400130c0  mov     r9, r15; unsigned __int16 *
0x1400130c3  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400130ca  mov     r8, rsi; unsigned __int16 *
0x1400130cd  lea     r14, aHr; "hr"
0x1400130d4  mov     rcx, rdi; unsigned __int16 *
0x1400130d7  mov     edx, 1651h; unsigned int
0x1400130dc  mov     [rsp+0E0h+ppv], r14; unsigned __int16 *
0x1400130e1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400130e6  call    cs:__imp_IsDebuggerPresent
0x1400130ec  test    eax, eax
0x1400130ee  jz      short loc_1400130FB
0x1400130f0  mov     r9d, 1651h
0x1400130f6  jmp     loc_140012FB3
0x1400130fb  mov     r8d, 1651h
0x140013101  jmp     loc_140012FE5
0x140013106  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 *
0x14001310a  call    ?GetSystemVolumeDriveLetter@@YAJPEAG@Z; GetSystemVolumeDriveLetter(ushort *)
0x14001310f  mov     ebx, eax
0x140013111  test    eax, eax
0x140013113  js      loc_14001359D
0x140013119  lea     rcx, [rbp+57h+var_78]; unsigned __int64 *
0x14001311d  call    ?s_GetMinimumReservedVolumeSize@CDiskProtection@@KAJPEA_K@Z; CDiskProtection::s_GetMinimumReservedVolumeSize(unsigned __int64 *)
0x140013122  mov     ebx, eax
0x140013124  test    eax, eax
0x140013126  js      loc_14001359D
0x14001312c  lea     rcx, [rbp+57h+var_9C]; unsigned __int16 *
0x140013130  call    ?s_GetReserveVolume@CDiskProtection@@SAJPEAG@Z; CDiskProtection::s_GetReserveVolume(ushort *)
0x140013135  mov     ebx, eax
0x140013137  test    eax, eax
0x140013139  js      loc_14001359D
0x14001313f  movzx   edi, [rbp+57h+var_9C]
0x140013143  movzx   esi, [rbp+57h+var_A0]
0x140013147  test    di, di
0x14001314a  jz      loc_140013478
0x140013150  cmp     di, si
0x140013153  jnz     loc_14001320B
0x140013159  mov     r15d, 8000FFFFh
0x14001315f  lea     rax, aChexistingrese_0; "chExistingReserveVolume != chSystemVolu"...
0x140013166  lea     r14, aCbraex; "CBRAEx"
0x14001316d  mov     [rsp+0E0h+var_B8], r15d; int
0x140013172  lea     rsi, aCdiskprotectio_54; "CDiskProtection::s_MovePageFileAndCrash"...
0x140013179  mov     [rsp+0E0h+ppv], rax; unsigned __int16 *
0x14001317e  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013185  mov     r9, r14; unsigned __int16 *
0x140013188  mov     r8, rsi; unsigned __int16 *
0x14001318b  mov     rcx, rdi; unsigned __int16 *
0x14001318e  mov     edx, 1665h; unsigned int
0x140013193  mov     ebx, r15d
0x140013196  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001319b  call    cs:__imp_IsDebuggerPresent
0x1400131a1  test    eax, eax
0x1400131a3  lea     rax, aChexistingrese_0; "chExistingReserveVolume != chSystemVolu"...
0x1400131aa  jz      short loc_1400131DF
0x1400131ac  mov     r9d, 1665h
0x1400131b2  mov     [rsp+0E0h+var_A8], r15d
0x1400131b7  mov     [rsp+0E0h+var_B0], rax
0x1400131bc  mov     qword ptr [rsp+0E0h+var_B8], r14
0x1400131c1  mov     r8, rdi
0x1400131c4  mov     [rsp+0E0h+ppv], rsi
0x1400131c9  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400131d0  mov     ecx, 2; unsigned __int8
0x1400131d5  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400131da  jmp     loc_1400135CE
0x1400131df  mov     r8d, 1665h
0x1400131e5  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x1400131ea  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400131ef  mov     [rsp+0E0h+ppv], r14
0x1400131f4  mov     r9, rsi
0x1400131f7  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400131fe  mov     rdx, rdi
0x140013201  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140013206  jmp     loc_1400135CE
0x14001320b  mov     eax, 43h ; 'C'
0x140013210  cmp     di, ax
0x140013213  ja      short loc_14001327E
0x140013215  mov     r15d, 8000FFFFh
0x14001321b  lea     rax, aChexistingrese; "chExistingReserveVolume > L'C'"
0x140013222  lea     r14, aCbraex; "CBRAEx"
0x140013229  mov     [rsp+0E0h+var_B8], r15d; int
0x14001322e  lea     rsi, aCdiskprotectio_54; "CDiskProtection::s_MovePageFileAndCrash"...
0x140013235  mov     [rsp+0E0h+ppv], rax; unsigned __int16 *
0x14001323a  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013241  mov     r9, r14; unsigned __int16 *
0x140013244  mov     r8, rsi; unsigned __int16 *
0x140013247  mov     rcx, rdi; unsigned __int16 *
0x14001324a  mov     edx, 1666h; unsigned int
0x14001324f  mov     ebx, r15d
0x140013252  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140013257  call    cs:__imp_IsDebuggerPresent
0x14001325d  test    eax, eax
0x14001325f  lea     rax, aChexistingrese; "chExistingReserveVolume > L'C'"
0x140013266  jz      short loc_140013273
0x140013268  mov     r9d, 1666h
0x14001326e  jmp     loc_1400131B2
0x140013273  mov     r8d, 1666h
0x140013279  jmp     loc_1400131E5
0x14001327e  lea     rdx, [rbp+57h+DirectoryName]
0x140013282  mov     [rbp+57h+DirectoryName], di
0x140013286  lea     rcx, aCdiskprotectio_143; "CDiskProtection::s_MovePageFileAndCrash"...
0x14001328d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140013292  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x140013295  lea     r8, [rbp+57h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x140013299  xor     edx, edx; lpFreeBytesAvailableToCaller
0x14001329b  lea     rcx, [rbp+57h+DirectoryName]; lpDirectoryName
0x14001329f  call    cs:__imp_GetDiskFreeSpaceExW
0x1400132a5  test    eax, eax
0x1400132a7  jnz     loc_140013345
0x1400132ad  call    cs:__imp_GetLastError
0x1400132b3  mov     ebx, eax
0x1400132b5  test    eax, eax
0x1400132b7  jle     short loc_1400132C2
0x1400132b9  movzx   ebx, ax
0x1400132bc  or      ebx, 80070000h
0x1400132c2  mov     eax, 80004005h
0x1400132c7  lea     r14, aCbraex; "CBRAEx"
0x1400132ce  test    ebx, ebx
0x1400132d0  lea     rsi, aCdiskprotectio_54; "CDiskProtection::s_MovePageFileAndCrash"...
0x1400132d7  mov     r15d, 166Dh
0x1400132dd  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400132e4  cmovns  ebx, eax
0x1400132e7  mov     r9, r14; unsigned __int16 *
0x1400132ea  lea     rax, aFsuccess; "fSuccess"
0x1400132f1  mov     [rsp+0E0h+var_B8], ebx; int
0x1400132f5  mov     r8, rsi; unsigned __int16 *
0x1400132f8  mov     [rsp+0E0h+ppv], rax; unsigned __int16 *
0x1400132fd  mov     edx, r15d; unsigned int
0x140013300  mov     rcx, rdi; unsigned __int16 *
0x140013303  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140013308  call    cs:__imp_IsDebuggerPresent
0x14001330e  test    eax, eax
0x140013310  lea     rax, aFsuccess; "fSuccess"
0x140013317  jz      short loc_14001332F
0x140013319  mov     [rsp+0E0h+var_A8], ebx
0x14001331d  mov     r9d, r15d
0x140013320  mov     [rsp+0E0h+var_B0], rax
0x140013325  mov     qword ptr [rsp+0E0h+var_B8], r14
0x14001332a  jmp     loc_140012FC1
0x14001332f  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x140013333  mov     r8d, r15d
0x140013336  mov     qword ptr [rsp+0E0h+var_B8], rax
0x14001333b  mov     [rsp+0E0h+ppv], r14
0x140013340  jmp     loc_140012FF3
0x140013345  mov     rcx, [rbp+57h+var_78]
0x140013349  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140013353  mul     rcx
0x140013356  shr     rdx, 3
0x14001335a  sub     rcx, rdx
0x14001335d  cmp     qword ptr [rbp+57h+TotalNumberOfBytes], rcx
0x140013361  jnb     loc_140013418
0x140013367  lea     rax, aExistingReserv; "Existing reserve volume is too small."
0x14001336e  mov     r15d, 1670h
0x140013374  mov     qword ptr [rsp+0E0h+var_B8], rax
0x140013379  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140013380  lea     rsi, aCdiskprotectio_54; "CDiskProtection::s_MovePageFileAndCrash"...
0x140013387  mov     r9d, r15d
0x14001338a  mov     r8, rdi
0x14001338d  mov     [rsp+0E0h+ppv], rsi
0x140013392  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140013399  mov     ecx, 4; unsigned __int8
0x14001339e  mov     ebx, 80070070h
0x1400133a3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400133a8  lea     rax, aCbexistingrese; "cbExistingReservedVolumeSize.QuadPart >"...
0x1400133af  mov     [rsp+0E0h+var_B8], ebx; int
0x1400133b3  lea     r9, aCbrlaex; "CBRLAEx"
0x1400133ba  mov     [rsp+0E0h+ppv], rax; unsigned __int16 *
0x1400133bf  mov     r8, rsi; unsigned __int16 *
0x1400133c2  mov     edx, r15d; unsigned int
0x1400133c5  mov     rcx, rdi; unsigned __int16 *
0x1400133c8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400133cd  call    cs:__imp_IsDebuggerPresent
0x1400133d3  test    eax, eax
0x1400133d5  lea     rax, aCbexistingrese; "cbExistingReservedVolumeSize.QuadPart >"...
0x1400133dc  jz      short loc_1400133FB
0x1400133de  mov     [rsp+0E0h+var_A8], ebx
0x1400133e2  mov     r9d, r15d
0x1400133e5  mov     [rsp+0E0h+var_B0], rax
0x1400133ea  lea     rax, aCbrlaex; "CBRLAEx"
0x1400133f1  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400133f6  jmp     loc_1400131C1
  ... truncated ...
```
