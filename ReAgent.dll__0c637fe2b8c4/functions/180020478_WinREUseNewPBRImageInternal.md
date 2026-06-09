# WinREUseNewPBRImageInternal

- ea: `0x180020478`
- end: `0x180020751`
- name: `WinREUseNewPBRImageInternal`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x180020400`

## callees

- `0x1800059fc`
- `0x18001e4c8`
- `0x18001f75c`
- `0x180020478`
- `0x180028cc4`
- `0x180031a00`
- `0x180031e10`
- `0x180031fa4`
- `0x18004d52c`
- `0x18004df64`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800206df`
- `KERNEL32!GetLastError` at `0x1800206df`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180020698`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180020698`
- `ole32!CoTaskMemFree` at `0x180020703`
- `ole32!CoTaskMemFree` at `0x180020703`

## string_xrefs

- `0x18002051e`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180020532`: `Failed to get WinRE config file path`
- `0x180020590`: ` (WinRE)WinREUseNewPBRImageInternal() WimBoot is enabled, replace the old PBR image`
- `0x1800205c2`: ` (WinRE)WinREUseNewPBRImageInternal() winreGetConfigByGuid failed, assuming no existing PBR image`

## pseudocode

```c
__int64 __fastcall WinREUseNewPBRImageInternal(const struct _GUID *a1)
{
  unsigned int v2; // ebx
  unsigned int ConfigFilePathFromOsGuid; // eax
  unsigned int WinDir; // eax
  unsigned int WimImageInfo; // eax
  DWORD LastError; // eax
  const wchar_t *v7; // r8
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+38h] [rbp-C8h] BYREF
  struct _GUID v10; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v11; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v12[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v13; // [rsp+70h] [rbp-90h]
  unsigned __int16 v14[302]; // [rsp+544h] [rbp+444h] BYREF
  unsigned int v15; // [rsp+7A0h] [rbp+6A0h]
  WCHAR DirectoryName[304]; // [rsp+F00h] [rbp+E00h] BYREF
  unsigned __int16 v17[304]; // [rsp+1160h] [rbp+1060h] BYREF

  v2 = 0;
  memset_0(v12, 0, 0xEA0u);
  v10 = 0;
  memset_0(DirectoryName, 0, 0x25Cu);
  TotalNumberOfFreeBytes.QuadPart = 0;
  if ( !(unsigned int)winreGetOSGuidOrDefault(a1, &v10) )
  {
    UnattendLogW(2, L" (WinRE)WinREUseNewPBRImageInternal() winreGetOSGuidOrDefault failed");
    goto LABEL_26;
  }
  ConfigFilePathFromOsGuid = winreGetConfigFilePathFromOsGuid(&v10);
  if ( ConfigFilePathFromOsGuid )
  {
    UnattendLogW(
      2,
      L"WinREUseNewPBRImageInternal %s (0x%x) in file %S line %d",
      L"Failed to get WinRE config file path",
      ConfigFilePathFromOsGuid,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      5417);
    goto LABEL_26;
  }
  WinDir = winreGetWinDir(&v10, DirectoryName);
  if ( WinDir )
  {
    UnattendLogW(1, L" (WinRE)WinREUseNewPBRImageInternal() winreGetWinDir failed. Error: 0x%08X", WinDir);
    goto LABEL_26;
  }
  if ( (unsigned int)WinReIsWimBootEnabledInternal(DirectoryName) )
  {
    UnattendLogW(0, L" (WinRE)WinREUseNewPBRImageInternal() WimBoot is enabled, replace the old PBR image");
LABEL_9:
    v2 = 1;
    goto LABEL_26;
  }
  v12[0] = 3744;
  if ( (unsigned int)winreGetConfigByGuid(a1, (struct _WINRE_CONFIG *)v12) )
  {
    if ( v13 && !Utils::DoesPathExist(v14) )
    {
      v11 = 0;
      memset_0(v17, 0, 0x25Cu);
      if ( (unsigned int)winReGetPBRImageFullPath(v14, v17) )
      {
        WimImageInfo = Utils::GetWimImageInfo(v17, v15, (struct _WIM_IMAGE_INFO *)&v11);
        if ( WimImageInfo )
        {
          UnattendLogW(
            1,
            L" (WinRE)WinREUseNewPBRImageInternal() Unable to get the WIM image info. Error: 0x%08X",
            WimImageInfo);
        }
        else if ( (unsigned int)v11 > 6 || DWORD1(v11) >= 4 )
        {
          v2 = 1;
          UnattendLogW(0, L" (WinRE)WinREUseNewPBRImageInternal() Windows 10 PBR image found");
        }
        else
        {
          UnattendLogW(0, L" (WinRE)WinREUseNewPBRImageInternal() Windows 8.x PBR image found. Preserve it.");
        }
        goto LABEL_26;
      }
      UnattendLogW(1, L" (WinRE)WinREUseNewPBRImageInternal() PBR image not found. Use the new PBR image");
      goto LABEL_9;
    }
    if ( GetDiskFreeSpaceExW(DirectoryName, 0, 0, &TotalNumberOfFreeBytes) )
    {
      UnattendLogW(
        0,
        L" (WinRE)WinREUseNewPBRImageInternal() Free space on %s : %I64u",
        0,
        TotalNumberOfFreeBytes.QuadPart);
      if ( TotalNumberOfFreeBytes.QuadPart > 0x280000000LL )
        goto LABEL_9;
      UnattendLogW(0, L" (WinRE)WinREUseNewPBRImageInternal() Not enough free space, don't use the new PBR image");
    }
    else
    {
      LastError = GetLastError();
      UnattendLogW(0, L" (WinRE) GetDiskFreeSpaceEx failed. Error: 0x%08X", LastError);
    }
  }
  else
  {
    UnattendLogW(
      2,
      L" (WinRE)WinREUseNewPBRImageInternal() winreGetConfigByGuid failed, assuming no existing PBR image");
  }
LABEL_26:
  v7 = L"TRUE";
  if ( !v2 )
    v7 = L"FALSE";
  UnattendLogW(0, L" (WinRE)WinREUseNewPBRImageInternal() returning %s", v7);
  return v2;
}

```

## disassembly

```asm
0x180020478  mov     [rsp-8+arg_0], rbx
0x18002047d  mov     [rsp-8+arg_8], rsi
0x180020482  push    rbp
0x180020483  lea     rbp, [rsp-12D0h]
0x18002048b  mov     eax, 13D0h
0x180020490  call    _alloca_probe
0x180020495  sub     rsp, rax
0x180020498  mov     rax, cs:__security_cookie
0x18002049f  xor     rax, rsp
0x1800204a2  mov     [rbp+12D0h+var_10], rax
0x1800204a9  mov     rsi, rcx
0x1800204ac  xor     edx, edx; Val
0x1800204ae  lea     rcx, [rsp+13D0h+var_1370]; void *
0x1800204b3  mov     r8d, 0EA0h; Size
0x1800204b9  xor     ebx, ebx
0x1800204bb  call    memset_0
0x1800204c0  xorps   xmm0, xmm0
0x1800204c3  mov     [rsp+13D0h+pv], rbx
0x1800204c8  xor     edx, edx; Val
0x1800204ca  lea     rcx, [rbp+12D0h+DirectoryName]; void *
0x1800204d1  mov     r8d, 25Ch; Size
0x1800204d7  movups  [rsp+13D0h+var_1390], xmm0
0x1800204dc  call    memset_0
0x1800204e1  lea     rdx, [rsp+13D0h+var_1390]
0x1800204e6  mov     qword ptr [rsp+13D0h+TotalNumberOfFreeBytes], rbx
0x1800204eb  mov     rcx, rsi
0x1800204ee  call    winreGetOSGuidOrDefault
0x1800204f3  test    eax, eax
0x1800204f5  jnz     short loc_18002050B
0x1800204f7  lea     rdx, aWinreWinreusen_1; " (WinRE)WinREUseNewPBRImageInternal() w"...
0x1800204fe  lea     ecx, [rbx+2]
0x180020501  call    UnattendLogW
0x180020506  jmp     loc_180020709
0x18002050b  lea     r8, [rsp+13D0h+pv]
0x180020510  lea     rcx, [rsp+13D0h+var_1390]
0x180020515  call    winreGetConfigFilePathFromOsGuid
0x18002051a  test    eax, eax
0x18002051c  jz      short loc_180020552
0x18002051e  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180020525  mov     [rsp+13D0h+var_13A8], 1529h
0x18002052d  mov     [rsp+13D0h+var_13B0], rcx
0x180020532  lea     r8, aFailedToGetWin_2; "Failed to get WinRE config file path"
0x180020539  mov     ecx, 2
0x18002053e  lea     rdx, aWinreusenewpbr_0; "WinREUseNewPBRImageInternal %s (0x%x) i"...
0x180020545  mov     r9d, eax
0x180020548  call    UnattendLogW
0x18002054d  jmp     loc_1800206F6
0x180020552  lea     rdx, [rbp+12D0h+DirectoryName]
0x180020559  lea     rcx, [rsp+13D0h+var_1390]
0x18002055e  call    winreGetWinDir
0x180020563  test    eax, eax
0x180020565  jz      short loc_180020580
0x180020567  lea     rdx, aWinreWinreusen_3; " (WinRE)WinREUseNewPBRImageInternal() w"...
0x18002056e  mov     r8d, eax
0x180020571  mov     ecx, 1
0x180020576  call    UnattendLogW
0x18002057b  jmp     loc_1800206F6
0x180020580  lea     rcx, [rbp+12D0h+DirectoryName]; lpFileName
0x180020587  call    ?WinReIsWimBootEnabledInternal@@YAHPEAG@Z; WinReIsWimBootEnabledInternal(ushort *)
0x18002058c  test    eax, eax
0x18002058e  jz      short loc_1800205A8
0x180020590  lea     rdx, aWinreWinreusen_2; " (WinRE)WinREUseNewPBRImageInternal() W"...
0x180020597  xor     ecx, ecx
0x180020599  call    UnattendLogW
0x18002059e  mov     ebx, 1
0x1800205a3  jmp     loc_1800206F6
0x1800205a8  lea     rdx, [rsp+13D0h+var_1370]; struct _WINRE_CONFIG *
0x1800205ad  mov     [rsp+13D0h+var_1370], 0EA0h
0x1800205b6  mov     rcx, rsi; struct _GUID *
0x1800205b9  call    ?winreGetConfigByGuid@@YAHPEBU_GUID@@PEAU_WINRE_CONFIG@@@Z; winreGetConfigByGuid(_GUID const *,_WINRE_CONFIG *)
0x1800205be  test    eax, eax
0x1800205c0  jnz     short loc_1800205D6
0x1800205c2  lea     rdx, aWinreWinreusen_6; " (WinRE)WinREUseNewPBRImageInternal() w"...
0x1800205c9  lea     ecx, [rax+2]
0x1800205cc  call    UnattendLogW
0x1800205d1  jmp     loc_1800206F6
0x1800205d6  cmp     [rsp+13D0h+var_1360], ebx
0x1800205da  jz      loc_180020687
0x1800205e0  lea     rcx, [rbp+12D0h+var_E8C]; unsigned __int16 *
0x1800205e7  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x1800205ec  test    eax, eax
0x1800205ee  jnz     loc_180020687
0x1800205f4  xorps   xmm0, xmm0
0x1800205f7  lea     rcx, [rbp+12D0h+var_270]; void *
0x1800205fe  xor     edx, edx; Val
0x180020600  mov     r8d, 25Ch; Size
0x180020606  movups  [rsp+13D0h+var_1380], xmm0
0x18002060b  call    memset_0
0x180020610  lea     rdx, [rbp+12D0h+var_270]
0x180020617  lea     rcx, [rbp+12D0h+var_E8C]
0x18002061e  call    winReGetPBRImageFullPath
0x180020623  test    eax, eax
0x180020625  jnz     short loc_18002063B
0x180020627  lea     rdx, aWinreWinreusen_9; " (WinRE)WinREUseNewPBRImageInternal() P"...
0x18002062e  lea     ecx, [rax+1]
0x180020631  call    UnattendLogW
0x180020636  jmp     loc_18002059E
0x18002063b  mov     edx, [rbp+12D0h+var_C30]; unsigned int
0x180020641  lea     r8, [rsp+13D0h+var_1380]; struct _WIM_IMAGE_INFO *
0x180020646  lea     rcx, [rbp+12D0h+var_270]; unsigned __int16 *
0x18002064d  call    ?GetWimImageInfo@Utils@@SAKPEBGKPEAU_WIM_IMAGE_INFO@@@Z; Utils::GetWimImageInfo(ushort const *,ulong,_WIM_IMAGE_INFO *)
0x180020652  test    eax, eax
0x180020654  jz      short loc_180020662
0x180020656  lea     rdx, aWinreWinreusen_8; " (WinRE)WinREUseNewPBRImageInternal() U"...
0x18002065d  jmp     loc_18002056E
0x180020662  cmp     dword ptr [rsp+13D0h+var_1380], 6
0x180020667  ja      short loc_180020679
0x180020669  cmp     dword ptr [rsp+13D0h+var_1380+4], 4
0x18002066e  jnb     short loc_180020679
0x180020670  lea     rdx, aWinreWinreusen_5; " (WinRE)WinREUseNewPBRImageInternal() W"...
0x180020677  jmp     short loc_1800206D6
0x180020679  mov     ebx, 1
0x18002067e  lea     rdx, aWinreWinreusen_0; " (WinRE)WinREUseNewPBRImageInternal() W"...
0x180020685  jmp     short loc_1800206D6
0x180020687  lea     r9, [rsp+13D0h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x18002068c  xor     r8d, r8d; lpTotalNumberOfBytes
0x18002068f  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180020691  lea     rcx, [rbp+12D0h+DirectoryName]; lpDirectoryName
0x180020698  call    cs:__imp_GetDiskFreeSpaceExW
0x18002069e  test    eax, eax
0x1800206a0  jz      short loc_1800206DF
0x1800206a2  mov     r9, qword ptr [rsp+13D0h+TotalNumberOfFreeBytes]
0x1800206a7  lea     rdx, aWinreWinreusen_7; " (WinRE)WinREUseNewPBRImageInternal() F"...
0x1800206ae  mov     r8, [rsp+13D0h+pv]
0x1800206b3  xor     ecx, ecx
0x1800206b5  call    UnattendLogW
0x1800206ba  mov     rax, 280000000h
0x1800206c4  cmp     qword ptr [rsp+13D0h+TotalNumberOfFreeBytes], rax
0x1800206c9  ja      loc_18002059E
0x1800206cf  lea     rdx, aWinreWinreusen_4; " (WinRE)WinREUseNewPBRImageInternal() N"...
0x1800206d6  xor     ecx, ecx
0x1800206d8  call    UnattendLogW
0x1800206dd  jmp     short loc_1800206F6
0x1800206df  call    cs:__imp_GetLastError
0x1800206e5  lea     rdx, aWinreGetdiskfr; " (WinRE) GetDiskFreeSpaceEx failed. Err"...
0x1800206ec  xor     ecx, ecx
0x1800206ee  mov     r8d, eax
0x1800206f1  call    UnattendLogW
0x1800206f6  cmp     [rsp+13D0h+pv], 0
0x1800206fc  jz      short loc_180020709
0x1800206fe  mov     rcx, [rsp+13D0h+pv]; pv
0x180020703  call    cs:__imp_CoTaskMemFree
0x180020709  test    ebx, ebx
0x18002070b  lea     rax, aFalse_0; "FALSE"
0x180020712  lea     r8, aTrue_0; "TRUE"
0x180020719  cmovz   r8, rax
0x18002071d  lea     rdx, aWinreWinreusen; " (WinRE)WinREUseNewPBRImageInternal() r"...
0x180020724  xor     ecx, ecx
0x180020726  call    UnattendLogW
0x18002072b  mov     eax, ebx
0x18002072d  mov     rcx, [rbp+12D0h+var_10]
0x180020734  xor     rcx, rsp; StackCookie
0x180020737  call    __security_check_cookie
0x18002073c  lea     r11, [rsp+13D0h+var_s0]
0x180020744  mov     rbx, [r11+10h]
0x180020748  mov     rsi, [r11+18h]
0x18002074c  mov     rsp, r11
0x18002074f  pop     rbp
0x180020750  retn
```
