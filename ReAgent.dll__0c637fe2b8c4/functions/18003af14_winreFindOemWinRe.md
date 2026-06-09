# winreFindOemWinRe

- ea: `0x18003af14`
- end: `0x18003b981`
- name: `winreFindOemWinRe`
- size: `2669`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017960`

## callees

- `0x180002ba8`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x180010010`
- `0x180010e78`
- `0x180011974`
- `0x180014754`
- `0x1800187e0`
- `0x18001df60`
- `0x18003af14`
- `0x18003b988`
- `0x18004d0a4`
- `0x18004d3a0`
- `0x18004d52c`
- `0x18004d828`
- `0x18004f8d0`
- `0x18005ced6`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003b1dd`
- `msvcrt!_wcsicmp` at `0x18003b1dd`
- `KERNEL32!GetLastError` at `0x18003b139`
- `KERNEL32!GetLastError` at `0x18003b139`
- `KERNEL32!CreateFileW` at `0x18003b286`
- `KERNEL32!CreateFileW` at `0x18003b286`
- `KERNEL32!CloseHandle` at `0x18003b162`
- `KERNEL32!CloseHandle` at `0x18003b931`
- `KERNEL32!CloseHandle` at `0x18003b162`
- `KERNEL32!CloseHandle` at `0x18003b931`
- `KERNEL32!DeviceIoControl` at `0x18003b2cc`
- `KERNEL32!DeviceIoControl` at `0x18003b30d`
- `KERNEL32!DeviceIoControl` at `0x18003b2cc`
- `KERNEL32!DeviceIoControl` at `0x18003b30d`
- `KERNEL32!GetDriveTypeW` at `0x18003b172`
- `KERNEL32!GetDriveTypeW` at `0x18003b172`
- `KERNEL32!FindFirstVolumeW` at `0x18003b12a`
- `KERNEL32!FindFirstVolumeW` at `0x18003b12a`
- `KERNEL32!FindNextVolumeW` at `0x18003b68d`
- `KERNEL32!FindNextVolumeW` at `0x18003b68d`
- `KERNEL32!FindVolumeClose` at `0x18003b91e`
- `KERNEL32!FindVolumeClose` at `0x18003b91e`

## string_xrefs

- `0x18003b875`: `install.wim`
- `0x18003b096`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003b717`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003b7b1`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003b710`: `failed to append OEM install directory`
- `0x18003b741`: `failed to copy winre path`
- `0x18003b647`: `failed to copy pbr image path`
- `0x18003b6ff`: `failed to convert winre.wim directory name to offset`
- `0x18003b8df`: `Updating config xml`

## pseudocode

```c
__int64 __fastcall winreFindOemWinRe(struct _GUID *a1, ReAgentXMLParser *a2)
{
  int WindowsVolume; // ebx
  const wchar_t *v5; // r8
  HANDLE FirstVolumeW; // r15
  __int64 v7; // rsi
  int v8; // r13d
  int v9; // r12d
  unsigned __int64 v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  const unsigned __int16 *v13; // r8
  unsigned int DoesFileExist; // eax
  __int64 v15; // r11
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  const unsigned __int16 *v18; // r8
  const wchar_t *v19; // r8
  const wchar_t *v20; // r8
  int v21; // ebx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  unsigned int v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v28; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+54h] [rbp-ACh]
  unsigned __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  struct ReAgentConfigInfo *ConfigInfo; // [rsp+60h] [rbp-A0h]
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v34[24]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v35; // [rsp+90h] [rbp-70h]
  struct _GUID v36; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned __int64 v37; // [rsp+560h] [rbp+460h]
  DWORD BytesReturned[4]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _DWORD v39[8]; // [rsp+5B0h] [rbp+4B0h] BYREF
  _BYTE Buf1[112]; // [rsp+5D0h] [rbp+4D0h] BYREF
  int OutBuffer; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v42[92]; // [rsp+644h] [rbp+544h] BYREF
  WCHAR szVolumeName; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v44[606]; // [rsp+6A2h] [rbp+5A2h] BYREF
  WCHAR szFileName; // [rsp+900h] [rbp+800h] BYREF
  _BYTE v46[606]; // [rsp+902h] [rbp+802h] BYREF
  unsigned __int16 v47; // [rsp+B60h] [rbp+A60h] BYREF
  _BYTE v48[606]; // [rsp+B62h] [rbp+A62h] BYREF
  WCHAR v49; // [rsp+DC0h] [rbp+CC0h] BYREF
  _BYTE v50[606]; // [rsp+DC2h] [rbp+CC2h] BYREF
  unsigned __int16 v51; // [rsp+1020h] [rbp+F20h] BYREF
  _BYTE v52[606]; // [rsp+1022h] [rbp+F22h] BYREF
  unsigned __int16 v53; // [rsp+1280h] [rbp+1180h] BYREF
  _BYTE v54[606]; // [rsp+1282h] [rbp+1182h] BYREF
  wchar_t String1; // [rsp+14E0h] [rbp+13E0h] BYREF
  _BYTE v56[606]; // [rsp+14E2h] [rbp+13E2h] BYREF

  szVolumeName = 0;
  memset_0(v44, 0, 0x25Au);
  v31 = 0;
  BytesReturned[0] = 0;
  v30 = 0;
  String1 = 0;
  memset_0(v56, 0, 0x25Au);
  v51 = 0;
  memset_0(v52, 0, 0x25Au);
  szFileName = 0;
  memset_0(v46, 0, 0x25Au);
  v47 = 0;
  memset_0(v48, 0, 0x25Au);
  v49 = 0;
  memset_0(v50, 0, 0x25Au);
  v53 = 0;
  memset_0(v54, 0, 0x25Au);
  v33 = 0;
  memset_0(v34, 0, 0x528u);
  OutBuffer = 0;
  memset_0(v42, 0, sizeof(v42));
  memset_0(v39, 0, 0x90u);
  v27 = 0;
  v26[0] = 0;
  v28 = 0;
  v29 = 0;
  WindowsVolume = winreGetWindowsVolume(a1, &String1);
  if ( WindowsVolume )
  {
    dwFlagsAndAttributesa = 267;
    v5 = L"failed to get windows volume";
LABEL_3:
    UnattendLogW(
      2,
      L"winreFindOemWinRe %s (0x%x) in file %S line %d",
      v5,
      (unsigned int)WindowsVolume,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      dwFlagsAndAttributesa);
    goto LABEL_102;
  }
  WindowsVolume = Utils::GetDiskAndPartitionNumber(&String1, &v27, v26);
  if ( WindowsVolume )
  {
    dwFlagsAndAttributesa = 274;
    v5 = L"failed to get disk and partition number of windwos volume";
    goto LABEL_3;
  }
  UnattendLogW(0, L"Windows volume is on disk %u partition %u", v27, v26[0]);
  memset_0(v39, 0, 0x90u);
  ConfigInfo = ReAgentXMLParser::GetConfigInfo(a2);
  FirstVolumeW = FindFirstVolumeW(&szVolumeName, 0x12Eu);
  if ( FirstVolumeW == (HANDLE)-1LL )
  {
    WindowsVolume = GetLastError();
    goto LABEL_101;
  }
  v7 = -1;
  v8 = 0;
  v9 = 0;
  do
  {
    if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle((HANDLE)v7);
      v7 = 0;
    }
    if ( GetDriveTypeW(&szVolumeName) != 3 )
      continue;
    WindowsVolume = StringCchLengthW(&szVolumeName, 0x12Eu, &v31);
    if ( WindowsVolume < 0 )
    {
      LODWORD(dwFlagsAndAttributes) = 301;
      v19 = L"failed to get the length of volume root";
      goto LABEL_84;
    }
    if ( !v31 )
      continue;
    v10 = 2 * v31 - 2;
    if ( v10 >= 0x25C )
      _report_rangecheckfailure();
    *(_WORD *)&v44[v10 - 2] = 0;
    if ( !_wcsicmp(&String1, &szVolumeName) )
    {
      UnattendLogW(0, L"Skipping OS volume");
      continue;
    }
    if ( Utils::GetDiskAndPartitionNumber(&szVolumeName, &v28, &v29) )
    {
      UnattendLogW(1, L"Failed to get disk and partition number of volume [%s]", &szVolumeName);
      continue;
    }
    dwCreationDisposition[0] = v29;
    UnattendLogW(0, L"Volume [%s] is on disk %u partition %u", &szVolumeName, v28, *(_QWORD *)dwCreationDisposition);
    if ( v27 != v28 )
    {
      UnattendLogW(0, L"Skipping volume on different disk");
      continue;
    }
    v7 = (__int64)CreateFileW(&szVolumeName, 1u, 7u, 0, 3u, 0x2000000u, 0);
    if ( v7 == -1 || !DeviceIoControl((HANDLE)v7, 0x90064u, 0, 0, &OutBuffer, 0x60u, BytesReturned, 0) )
      continue;
    if ( DeviceIoControl((HANDLE)v7, 0x70048u, 0, 0, v39, 0x90u, BytesReturned, 0) )
    {
      if ( v39[0] )
      {
        if ( v39[0] != 1 )
          continue;
        if ( memcmp_0(Buf1, &PARTITION_MSFT_RECOVERY_GUID, 0x10u) )
          goto LABEL_27;
        UnattendLogW(0, L"Valid GPT partition found");
      }
      else
      {
        if ( Buf1[0] != 39 && !Buf1[1] )
        {
LABEL_27:
          UnattendLogW(0, L"Skipping volume %s", &szVolumeName);
          continue;
        }
        UnattendLogW(0, L"Valid MBR parition found");
      }
    }
    UnattendLogW(0, L" Scanning volume %s", &szVolumeName);
    *(_QWORD *)v26 = 0;
    WindowsVolume = StringCchLengthW(&szVolumeName, 0x7FFFFFFFu, (unsigned __int64 *)v26);
    if ( WindowsVolume >= 0 )
    {
      if ( !*(_QWORD *)v26 || (v13 = L"%s\\%s", *(_WORD *)&v42[2 * *(_QWORD *)v26 + 90] == 92) )
        v13 = L"%s%s";
      WindowsVolume = StringCchPrintfW(&v47, 0x12Eu, v13, &szVolumeName, L"Recovery\\WindowsRE");
      if ( WindowsVolume >= 0 )
        goto LABEL_45;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v12 = 15;
        goto LABEL_43;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v12 = 14;
LABEL_43:
        WPP_SF_d(v11[2], v12, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)WindowsVolume);
      }
    }
    WindowsVolume = (unsigned __int16)WindowsVolume;
    if ( (_WORD)WindowsVolume )
    {
      LODWORD(dwFlagsAndAttributes) = 402;
      v20 = L"failed to append OEM install directory";
      goto LABEL_76;
    }
LABEL_45:
    DoesFileExist = Utils::DoesFileExist(&v47, L"Winre.wim");
    v15 = 0;
    if ( DoesFileExist )
      goto LABEL_50;
    UnattendLogW(0, L"winreFindOemWinRe WINRE located at %s", &v47);
    if ( Utils::CompareFileNames(&v47, (const unsigned __int16 *)ConfigInfo + 3116) )
    {
      UnattendLogW(0, L"winreFindOemWinRe Ignoring downlevel WINRE located at %s", &v47);
      v15 = 0;
      goto LABEL_50;
    }
    if ( v8 )
    {
      UnattendLogW(2, L"winreFindOemWinRe Multiple winre.wims found");
      WindowsVolume = StringCchCopyW(&szFileName, 0x12Eu, &cchOriginalDestLength);
      if ( WindowsVolume >= 0 )
      {
LABEL_96:
        WindowsVolume = 2;
        goto LABEL_97;
      }
      LODWORD(dwFlagsAndAttributes) = 417;
      goto LABEL_78;
    }
    v8 = 1;
    WindowsVolume = StringCchCopyW(&szFileName, 0x12Eu, &v47);
    if ( WindowsVolume < 0 )
    {
      LODWORD(dwFlagsAndAttributes) = 424;
LABEL_78:
      v19 = L"failed to copy winre path";
      goto LABEL_84;
    }
LABEL_50:
    *(_QWORD *)v26 = v15;
    WindowsVolume = StringCchLengthW(&szVolumeName, 0x7FFFFFFFu, (unsigned __int64 *)v26);
    if ( WindowsVolume >= 0 )
    {
      if ( !*(_QWORD *)v26 || (v18 = L"%s\\%s", *(_WORD *)&v42[2 * *(_QWORD *)v26 + 90] == 92) )
        v18 = L"%s%s";
      WindowsVolume = StringCchPrintfW(&v51, 0x12Eu, v18, &szVolumeName, L"RecoveryImage");
      if ( WindowsVolume >= 0 )
        goto LABEL_63;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 15;
        goto LABEL_61;
      }
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 14;
LABEL_61:
        WPP_SF_d(v16[2], v17, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)WindowsVolume);
      }
    }
    WindowsVolume = (unsigned __int16)WindowsVolume;
    if ( (_WORD)WindowsVolume )
    {
      LODWORD(dwFlagsAndAttributes) = 430;
      v20 = L"failed to append PBR image dir";
      goto LABEL_76;
    }
LABEL_63:
    if ( !Utils::DoesPathExist(&v51) )
    {
      UnattendLogW(0, L"winreFindOemWinRe PBR image located at %s", &v51);
      if ( v9 )
      {
        UnattendLogW(2, L"winreFindOemWinRe Multiple PBR images found");
        WindowsVolume = StringCchCopyW(&v49, 0x12Eu, &cchOriginalDestLength);
        if ( WindowsVolume < 0 )
        {
          LODWORD(dwFlagsAndAttributes) = 438;
LABEL_67:
          v19 = L"failed to copy pbr image path";
LABEL_84:
          UnattendLogW(
            2,
            L"winreFindOemWinRe %s (0x%x) in file %S line %d",
            v19,
            (unsigned int)WindowsVolume,
            "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
            dwFlagsAndAttributes);
          WindowsVolume = (unsigned __int16)WindowsVolume;
          goto LABEL_97;
        }
      }
      else
      {
        WindowsVolume = StringCchCopyW(&v49, 0x12Eu, &v51);
        if ( WindowsVolume < 0 )
        {
          LODWORD(dwFlagsAndAttributes) = 442;
          goto LABEL_67;
        }
        v9 = 1;
      }
    }
  }
  while ( FindNextVolumeW(FirstVolumeW, &szVolumeName, 0x12Eu) );
  if ( !v8 || !szFileName )
  {
    UnattendLogW(1, L"Winre not found");
    goto LABEL_96;
  }
  UnattendLogW(0, L"Found winre at location %s", &szFileName);
  WindowsVolume = winreConvertDirNameToOffset(&szFileName, (__int64)L"winre.wim", &v33, 0, (__int64)&v53);
  if ( WindowsVolume )
  {
    LODWORD(dwFlagsAndAttributes) = 459;
    v20 = L"failed to convert winre.wim directory name to offset";
LABEL_76:
    UnattendLogW(
      2,
      L"winreFindOemWinRe %s (0x%x) in file %S line %d",
      v20,
      (unsigned int)WindowsVolume,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      dwFlagsAndAttributes);
    goto LABEL_97;
  }
  UnattendLogW(0, L"Setting staging location to %s", &szFileName);
  WindowsVolume = ReAgentConfig::SetImageLocationPath(a2, v37, &v36, v35, &v53);
  if ( WindowsVolume )
  {
    LODWORD(dwFlagsAndAttributes) = 461;
    v20 = L"failed to set image location";
    goto LABEL_76;
  }
  if ( v9 )
  {
    if ( v49 )
    {
      if ( !(unsigned int)winreGetPBRImageIndex(&v49) )
      {
        v21 = v30;
        if ( v30 )
        {
          if ( !(unsigned int)winreConvertDirNameToOffset(&v49, (__int64)L"install.wim", &v33, 0, (__int64)&v53) )
          {
            UnattendLogW(0, L"Setting PBR image location to %s", &szFileName);
            ReAgentConfig::SetOsInstallLocationPath(a2, v37, &v36, v35, &v53, v21);
          }
        }
      }
    }
  }
  else
  {
    UnattendLogW(1, L"PBRImage was not set");
  }
  *(_DWORD *)(*((_QWORD *)a2 + 8) + 5612LL) = 4;
  UnattendLogW(0, L"Updating config xml");
  WindowsVolume = ReAgentXMLParser::Update(a2);
LABEL_97:
  if ( FirstVolumeW )
    FindVolumeClose(FirstVolumeW);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v7);
LABEL_101:
  if ( WindowsVolume )
LABEL_102:
    UnattendLogW(1, L"winreFindOemWinRe failed: 0x%x", (unsigned int)WindowsVolume);
  return (unsigned int)WindowsVolume;
}

```

## disassembly

```asm
0x18003af14  mov     [rsp-8+arg_10], rbx
0x18003af19  push    rbp
0x18003af1a  push    rsi
0x18003af1b  push    rdi
0x18003af1c  push    r12
0x18003af1e  push    r13
0x18003af20  push    r14
0x18003af22  push    r15
0x18003af24  lea     rbp, [rsp-1650h]
0x18003af2c  mov     eax, 1750h
0x18003af31  call    _alloca_probe
0x18003af36  sub     rsp, rax
0x18003af39  mov     rax, cs:__security_cookie
0x18003af40  xor     rax, rsp
0x18003af43  mov     [rbp+1680h+var_40], rax
0x18003af4a  mov     r14, rdx
0x18003af4d  mov     rbx, rcx
0x18003af50  mov     edi, 25Ah
0x18003af55  lea     rcx, [rbp+1680h+var_10DE]; void *
0x18003af5c  xor     r15d, r15d
0x18003af5f  mov     r8d, edi; Size
0x18003af62  xor     edx, edx; Val
0x18003af64  mov     [rbp+1680h+szVolumeName], r15w
0x18003af6c  call    memset_0
0x18003af71  mov     r8d, edi; Size
0x18003af74  mov     [rsp+1780h+var_1728], r15
0x18003af79  xor     edx, edx; Val
0x18003af7b  mov     [rbp+1680h+BytesReturned], r15d
0x18003af82  lea     rcx, [rbp+1680h+var_29E]; void *
0x18003af89  mov     [rsp+1780h+var_172C], r15d
0x18003af8e  mov     [rbp+1680h+String1], r15w
0x18003af96  call    memset_0
0x18003af9b  mov     r8d, edi; Size
0x18003af9e  mov     [rbp+1680h+var_760], r15w
0x18003afa6  xor     edx, edx; Val
0x18003afa8  lea     rcx, [rbp+1680h+var_75E]; void *
0x18003afaf  call    memset_0
0x18003afb4  mov     r8d, edi; Size
0x18003afb7  mov     [rbp+1680h+szFileName], r15w
0x18003afbf  xor     edx, edx; Val
0x18003afc1  lea     rcx, [rbp+1680h+var_E7E]; void *
0x18003afc8  call    memset_0
0x18003afcd  mov     r8d, edi; Size
0x18003afd0  mov     [rbp+1680h+var_C20], r15w
0x18003afd8  xor     edx, edx; Val
0x18003afda  lea     rcx, [rbp+1680h+var_C1E]; void *
0x18003afe1  call    memset_0
0x18003afe6  mov     r8d, edi; Size
0x18003afe9  mov     [rbp+1680h+var_9C0], r15w
0x18003aff1  xor     edx, edx; Val
0x18003aff3  lea     rcx, [rbp+1680h+var_9BE]; void *
0x18003affa  call    memset_0
0x18003afff  mov     r8d, edi; Size
0x18003b002  mov     [rbp+1680h+var_500], r15w
0x18003b00a  xor     edx, edx; Val
0x18003b00c  lea     rcx, [rbp+1680h+var_4FE]; void *
0x18003b013  call    memset_0
0x18003b018  xor     edx, edx; Val
0x18003b01a  mov     [rsp+1780h+var_1710], r15
0x18003b01f  mov     r8d, 528h; Size
0x18003b025  lea     rcx, [rsp+1780h+var_1708]; void *
0x18003b02a  call    memset_0
0x18003b02f  xor     edx, edx; Val
0x18003b031  mov     [rbp+1680h+OutBuffer], r15d
0x18003b038  lea     r8d, [r15+5Ch]; Size
0x18003b03c  lea     rcx, [rbp+1680h+var_113C]; void *
0x18003b043  call    memset_0
0x18003b048  mov     edi, 90h
0x18003b04d  lea     rcx, [rbp+1680h+var_11D0]; void *
0x18003b054  mov     r8d, edi; Size
0x18003b057  xor     edx, edx; Val
0x18003b059  call    memset_0
0x18003b05e  lea     rdx, [rbp+1680h+String1]
0x18003b065  mov     [rsp+1780h+var_1738], r15d
0x18003b06a  mov     rcx, rbx
0x18003b06d  mov     [rsp+1780h+var_1740], r15d
0x18003b072  mov     [rsp+1780h+var_1734], r15d
0x18003b077  mov     [rsp+1780h+var_1730], r15d
0x18003b07c  call    winreGetWindowsVolume
0x18003b081  mov     ebx, eax
0x18003b083  test    eax, eax
0x18003b085  jz      short loc_18003B0BB
0x18003b087  mov     dword ptr [rsp+1780h+dwFlagsAndAttributes], 10Bh
0x18003b08f  lea     r8, aFailedToGetWin_10; "failed to get windows volume"
0x18003b096  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003b09d  mov     r9d, ebx
0x18003b0a0  lea     rdx, aWinrefindoemwi_1; "winreFindOemWinRe %s (0x%x) in file %S "...
0x18003b0a7  mov     qword ptr [rsp+1780h+dwCreationDisposition], rax
0x18003b0ac  mov     ecx, 2
0x18003b0b1  call    UnattendLogW
0x18003b0b6  jmp     loc_18003B93B
0x18003b0bb  lea     r8, [rsp+1780h+var_1740]; unsigned int *
0x18003b0c0  lea     rdx, [rsp+1780h+var_1738]; unsigned int *
0x18003b0c5  lea     rcx, [rbp+1680h+String1]; unsigned __int16 *
0x18003b0cc  call    ?GetDiskAndPartitionNumber@Utils@@SAKPEBGPEAK1@Z; Utils::GetDiskAndPartitionNumber(ushort const *,ulong *,ulong *)
0x18003b0d1  mov     ebx, eax
0x18003b0d3  test    eax, eax
0x18003b0d5  jz      short loc_18003B0E8
0x18003b0d7  mov     dword ptr [rsp+1780h+dwFlagsAndAttributes], 112h
0x18003b0df  lea     r8, aFailedToGetDis; "failed to get disk and partition number"...
0x18003b0e6  jmp     short loc_18003B096
0x18003b0e8  mov     r9d, [rsp+1780h+var_1740]
0x18003b0ed  lea     rdx, aWindowsVolumeI; "Windows volume is on disk %u partition "...
0x18003b0f4  mov     r8d, [rsp+1780h+var_1738]
0x18003b0f9  xor     ecx, ecx
0x18003b0fb  call    UnattendLogW
0x18003b100  mov     r8, rdi; Size
0x18003b103  lea     rcx, [rbp+1680h+var_11D0]; void *
0x18003b10a  xor     edx, edx; Val
0x18003b10c  call    memset_0
0x18003b111  mov     rcx, r14; this
0x18003b114  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18003b119  mov     edx, 12Eh; cchBufferLength
0x18003b11e  mov     [rsp+1780h+var_1720], rax
0x18003b123  lea     rcx, [rbp+1680h+szVolumeName]; lpszVolumeName
0x18003b12a  call    cs:__imp_FindFirstVolumeW
0x18003b130  mov     r15, rax
0x18003b133  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b137  jnz     short loc_18003B146
0x18003b139  call    cs:__imp_GetLastError
0x18003b13f  mov     ebx, eax
0x18003b141  jmp     loc_18003B937
0x18003b146  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003b14a  xor     ebx, ebx
0x18003b14c  mov     r13d, ebx
0x18003b14f  mov     r12d, ebx
0x18003b152  lea     edi, [rsi+3]
0x18003b155  lea     rax, [rsi-1]
0x18003b159  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b15d  ja      short loc_18003B16B
0x18003b15f  mov     rcx, rsi; hObject
0x18003b162  call    cs:__imp_CloseHandle
0x18003b168  mov     rsi, rbx
0x18003b16b  lea     rcx, [rbp+1680h+szVolumeName]; lpRootPathName
0x18003b172  call    cs:__imp_GetDriveTypeW
0x18003b178  cmp     eax, 3
0x18003b17b  jnz     loc_18003B67D
0x18003b181  lea     r8, [rsp+1780h+var_1728]; unsigned __int64 *
0x18003b186  mov     edx, 12Eh; unsigned __int64
0x18003b18b  lea     rcx, [rbp+1680h+szVolumeName]; unsigned __int16 *
0x18003b192  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003b197  mov     ebx, eax
0x18003b199  test    eax, eax
0x18003b19b  js      loc_18003B7A2
0x18003b1a1  mov     rax, [rsp+1780h+var_1728]
0x18003b1a6  cmp     rax, 1
0x18003b1aa  jb      loc_18003B67B
0x18003b1b0  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18003b1b8  cmp     rcx, 25Ch
0x18003b1bf  jnb     loc_18003B97B
0x18003b1c5  xor     ebx, ebx
0x18003b1c7  lea     rdx, [rbp+1680h+szVolumeName]; String2
0x18003b1ce  mov     [rbp+rcx+1680h+szVolumeName], bx
0x18003b1d6  lea     rcx, [rbp+1680h+String1]; String1
0x18003b1dd  call    cs:__imp__wcsicmp
0x18003b1e3  test    eax, eax
0x18003b1e5  jnz     short loc_18003B1FA
0x18003b1e7  lea     rdx, aSkippingOsVolu; "Skipping OS volume"
0x18003b1ee  xor     ecx, ecx
0x18003b1f0  call    UnattendLogW
0x18003b1f5  jmp     loc_18003B67D
0x18003b1fa  lea     r8, [rsp+1780h+var_1730]; unsigned int *
0x18003b1ff  lea     rdx, [rsp+1780h+var_1734]; unsigned int *
0x18003b204  lea     rcx, [rbp+1680h+szVolumeName]; unsigned __int16 *
0x18003b20b  call    ?GetDiskAndPartitionNumber@Utils@@SAKPEBGPEAK1@Z; Utils::GetDiskAndPartitionNumber(ushort const *,ulong *,ulong *)
0x18003b210  lea     r8, [rbp+1680h+szVolumeName]
0x18003b217  test    eax, eax
0x18003b219  jz      short loc_18003B231
0x18003b21b  lea     rdx, aFailedToGetDis_0; "Failed to get disk and partition number"...
0x18003b222  mov     ecx, 1
0x18003b227  call    UnattendLogW
0x18003b22c  jmp     loc_18003B67D
0x18003b231  mov     eax, [rsp+1780h+var_1730]
0x18003b235  lea     rdx, aVolumeSIsOnDis; "Volume [%s] is on disk %u partition %u"
0x18003b23c  mov     r9d, [rsp+1780h+var_1734]
0x18003b241  xor     ecx, ecx
0x18003b243  mov     [rsp+1780h+dwCreationDisposition], eax
0x18003b247  call    UnattendLogW
0x18003b24c  mov     eax, [rsp+1780h+var_1738]
0x18003b250  cmp     eax, [rsp+1780h+var_1734]
0x18003b254  jz      short loc_18003B25F
0x18003b256  lea     rdx, aSkippingVolume; "Skipping volume on different disk"
0x18003b25d  jmp     short loc_18003B1EE
0x18003b25f  xor     r9d, r9d; lpSecurityAttributes
0x18003b262  mov     [rsp+1780h+hTemplateFile], rbx; hTemplateFile
0x18003b267  mov     dword ptr [rsp+1780h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18003b26f  lea     rcx, [rbp+1680h+szVolumeName]; lpFileName
0x18003b276  mov     [rsp+1780h+dwCreationDisposition], 3; dwCreationDisposition
0x18003b27e  lea     edx, [r9+1]; dwDesiredAccess
0x18003b282  lea     r8d, [r9+7]; dwShareMode
0x18003b286  call    cs:__imp_CreateFileW
0x18003b28c  mov     rsi, rax
0x18003b28f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b293  jz      loc_18003B67D
0x18003b299  mov     [rsp+1780h+lpOverlapped], rbx; lpOverlapped
0x18003b29e  lea     rax, [rbp+1680h+BytesReturned]
0x18003b2a5  mov     [rsp+1780h+hTemplateFile], rax; lpBytesReturned
0x18003b2aa  xor     r9d, r9d; nInBufferSize
0x18003b2ad  lea     rax, [rbp+1680h+OutBuffer]
0x18003b2b4  mov     dword ptr [rsp+1780h+dwFlagsAndAttributes], 60h ; '`'; nOutBufferSize
0x18003b2bc  xor     r8d, r8d; lpInBuffer
0x18003b2bf  mov     qword ptr [rsp+1780h+dwCreationDisposition], rax; lpOutBuffer
0x18003b2c4  mov     edx, 90064h; dwIoControlCode
0x18003b2c9  mov     rcx, rsi; hDevice
0x18003b2cc  call    cs:__imp_DeviceIoControl
0x18003b2d2  test    eax, eax
0x18003b2d4  jz      loc_18003B67D
0x18003b2da  mov     [rsp+1780h+lpOverlapped], rbx; lpOverlapped
0x18003b2df  lea     rax, [rbp+1680h+BytesReturned]
0x18003b2e6  mov     [rsp+1780h+hTemplateFile], rax; lpBytesReturned
0x18003b2eb  xor     r9d, r9d; nInBufferSize
0x18003b2ee  lea     rax, [rbp+1680h+var_11D0]
0x18003b2f5  mov     dword ptr [rsp+1780h+dwFlagsAndAttributes], 90h; nOutBufferSize
0x18003b2fd  xor     r8d, r8d; lpInBuffer
0x18003b300  mov     qword ptr [rsp+1780h+dwCreationDisposition], rax; lpOutBuffer
0x18003b305  mov     edx, 70048h; dwIoControlCode
0x18003b30a  mov     rcx, rsi; hDevice
0x18003b30d  call    cs:__imp_DeviceIoControl
0x18003b313  test    eax, eax
0x18003b315  jz      short loc_18003B389
0x18003b317  mov     eax, [rbp+1680h+var_11D0]
0x18003b31d  test    eax, eax
0x18003b31f  jnz     short loc_18003B357
0x18003b321  cmp     [rbp+1680h+Buf1], 27h ; '''
0x18003b328  jz      short loc_18003B34C
0x18003b32a  cmp     [rbp+1680h+var_11AF], bl
0x18003b330  jnz     short loc_18003B34C
0x18003b332  xor     ecx, ecx
0x18003b334  lea     rdx, aSkippingVolume_0; "Skipping volume %s"
0x18003b33b  lea     r8, [rbp+1680h+szVolumeName]
0x18003b342  call    UnattendLogW
0x18003b347  jmp     loc_18003B67D
0x18003b34c  lea     rdx, aValidMbrPariti; "Valid MBR parition found"
0x18003b353  xor     ecx, ecx
0x18003b355  jmp     short loc_18003B384
0x18003b357  cmp     eax, 1
0x18003b35a  jnz     loc_18003B67D
0x18003b360  lea     r8d, [rax+0Fh]; Size
0x18003b364  lea     rdx, PARTITION_MSFT_RECOVERY_GUID; Buf2
0x18003b36b  lea     rcx, [rbp+1680h+Buf1]; Buf1
0x18003b372  call    memcmp_0
0x18003b377  xor     ecx, ecx
0x18003b379  test    eax, eax
0x18003b37b  jnz     short loc_18003B334
0x18003b37d  lea     rdx, aValidGptPartit; "Valid GPT partition found"
0x18003b384  call    UnattendLogW
0x18003b389  lea     r8, [rbp+1680h+szVolumeName]
0x18003b390  xor     ecx, ecx
0x18003b392  lea     rdx, aScanningVolume; " Scanning volume %s"
0x18003b399  call    UnattendLogW
0x18003b39e  lea     r8, [rsp+1780h+var_1740]; unsigned __int64 *
0x18003b3a3  mov     qword ptr [rsp+1780h+var_1740], rbx
0x18003b3a8  mov     edx, 7FFFFFFFh; unsigned __int64
0x18003b3ad  lea     rcx, [rbp+1680h+szVolumeName]; unsigned __int16 *
0x18003b3b4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003b3b9  mov     ebx, eax
0x18003b3bb  test    eax, eax
0x18003b3bd  jns     short loc_18003B3E7
0x18003b3bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3c6  lea     rax, WPP_GLOBAL_Control
0x18003b3cd  cmp     rcx, rax
0x18003b3d0  jz      loc_18003B469
0x18003b3d6  test    [rcx+1Ch], dil
0x18003b3da  jz      loc_18003B469
0x18003b3e0  mov     edx, 0Eh
0x18003b3e5  jmp     short loc_18003B456
0x18003b3e7  mov     rax, qword ptr [rsp+1780h+var_1740]
0x18003b3ec  test    rax, rax
0x18003b3ef  jz      short loc_18003B407
0x18003b3f1  mov     ecx, 5Ch ; '\'
0x18003b3f6  lea     r8, aSS_1; "%s\\%s"
0x18003b3fd  cmp     [rbp+rax*2+1680h+var_10E2], cx
0x18003b405  jnz     short loc_18003B40E
0x18003b407  lea     r8, aSS_2; "%s%s"
0x18003b40e  lea     rax, aRecoveryWindow+2; "Recovery\\WindowsRE"
0x18003b415  mov     edx, 12Eh; unsigned __int64
0x18003b41a  lea     r9, [rbp+1680h+szVolumeName]
0x18003b421  mov     qword ptr [rsp+1780h+dwCreationDisposition], rax
0x18003b426  lea     rcx, [rbp+1680h+var_C20]; unsigned __int16 *
0x18003b42d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b432  mov     ebx, eax
0x18003b434  test    eax, eax
0x18003b436  jns     short loc_18003B474
0x18003b438  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b43f  lea     rax, WPP_GLOBAL_Control
0x18003b446  cmp     rcx, rax
0x18003b449  jz      short loc_18003B469
0x18003b44b  test    [rcx+1Ch], dil
0x18003b44f  jz      short loc_18003B469
0x18003b451  mov     edx, 0Fh
0x18003b456  mov     rcx, [rcx+10h]
0x18003b45a  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18003b461  mov     r9d, ebx
0x18003b464  call    WPP_SF_d
0x18003b469  movzx   ebx, bx
0x18003b46c  test    ebx, ebx
0x18003b46e  jnz     loc_18003B708
0x18003b474  lea     rdx, aWinreWim; "Winre.wim"
0x18003b47b  lea     rcx, [rbp+1680h+var_C20]; unsigned __int16 *
0x18003b482  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
  ... truncated ...
```
