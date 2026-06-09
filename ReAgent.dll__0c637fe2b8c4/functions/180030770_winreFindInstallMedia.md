# winreFindInstallMedia

- ea: `0x180030770`
- end: `0x180030a64`
- name: `winreFindInstallMedia`
- size: `756`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, service_task, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18000c658`
- `0x18000fe58`
- `0x18000ffcc`
- `0x1800103f4`
- `0x180030770`
- `0x1800318c0`
- `0x180031a7c`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003085a`
- `KERNEL32!GetLastError` at `0x180030918`
- `KERNEL32!GetLastError` at `0x1800309cb`
- `KERNEL32!GetLastError` at `0x18003085a`
- `KERNEL32!GetLastError` at `0x180030918`
- `KERNEL32!GetLastError` at `0x1800309cb`
- `KERNEL32!GetDriveTypeW` at `0x18003086f`
- `KERNEL32!GetDriveTypeW` at `0x18003086f`
- `KERNEL32!FindFirstVolumeW` at `0x18003084b`
- `KERNEL32!FindFirstVolumeW` at `0x18003084b`
- `KERNEL32!FindNextVolumeW` at `0x180030905`
- `KERNEL32!FindNextVolumeW` at `0x180030905`
- `KERNEL32!FindVolumeClose` at `0x180030a14`
- `KERNEL32!FindVolumeClose` at `0x180030a14`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18003088f`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18003088f`
- `ole32!CoTaskMemFree` at `0x180030a22`
- `ole32!CoTaskMemFree` at `0x180030a22`

## string_xrefs

- `0x18003094b`: `failed to allocate path`
- `0x1800308d1`: `install.wim`
- `0x1800307c3`: `Enter winreFindInstallMedia`
- `0x1800307de`: `Parameters: volPath: %s, DosPath: %s`
- `0x180030811`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x180030934`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x180030994`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x18003082f`: `winreFindInstallMedia %s (0x%x) in file %S line %d`
- `0x180030954`: `winreFindInstallMedia %s (0x%x) in file %S line %d`
- `0x18003099e`: `winreFindInstallMedia %s (0x%x) in file %S line %d`
- `0x18003098d`: `failed to add setup.exe to directory path`
- `0x180030a2b`: `Exit winreFindInstallMedia return error code: 0x%x`

## pseudocode

```c
__int64 __fastcall winreFindInstallMedia(unsigned __int16 *a1, _DWORD *a2, WCHAR *a3)
{
  unsigned __int16 *v4; // r14
  const unsigned __int16 *v7; // r9
  const unsigned __int16 *v8; // r8
  DWORD CurrentOsArch; // ebx
  HANDLE FirstVolumeW; // r15
  const wchar_t *v11; // r8
  DWORD LastError; // eax
  int v14; // [rsp+28h] [rbp-38h]
  int v15; // [rsp+30h] [rbp-30h] BYREF
  int v16; // [rsp+34h] [rbp-2Ch] BYREF
  int v17; // [rsp+38h] [rbp-28h] BYREF
  int v18; // [rsp+3Ch] [rbp-24h] BYREF
  int v19; // [rsp+40h] [rbp-20h] BYREF
  int v20; // [rsp+44h] [rbp-1Ch] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp-18h] BYREF
  DWORD cchReturnLength; // [rsp+50h] [rbp-10h] BYREF

  v21 = 0;
  v4 = 0;
  v20 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v15 = 0;
  v17 = 0;
  cchReturnLength = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter winreFindInstallMedia");
  v7 = a3;
  if ( !a3 )
    v7 = L"NULL";
  v8 = a1;
  if ( !a1 )
    v8 = L"NULL";
  UnattendLogW(0, L"Parameters: volPath: %s, DosPath: %s", v8, v7);
  CurrentOsArch = winreGetCurrentOsArch(&v19, &v15, &v17);
  if ( CurrentOsArch )
  {
    UnattendLogW(
      2,
      L"winreFindInstallMedia %s (0x%x) in file %S line %d",
      L"failed to get current OS architecture",
      CurrentOsArch,
      "base\\diagnosis\\srt\\reagent2\\reagent\\setup.cpp",
      62);
    goto LABEL_35;
  }
  FirstVolumeW = FindFirstVolumeW(a1, 0x12Eu);
  if ( FirstVolumeW == (HANDLE)-1LL )
  {
    CurrentOsArch = GetLastError();
    goto LABEL_35;
  }
  while ( GetDriveTypeW(a1) != 5 )
  {
LABEL_17:
    if ( !FindNextVolumeW(FirstVolumeW, a1, 0x12Eu) )
      goto LABEL_33;
  }
  if ( a3 )
  {
    if ( !GetVolumePathNamesForVolumeNameW(a1, a3, 0x104u, &cchReturnLength) )
    {
      CurrentOsArch = GetLastError();
      goto LABEL_33;
    }
    if ( StringCchCatW(a3, 0x12Eu, L"sources") < 0 )
      goto LABEL_32;
  }
  if ( StringCchCatW(a1, 0x12Eu, L"sources") < 0 )
  {
LABEL_32:
    CurrentOsArch = 2;
    goto LABEL_33;
  }
  if ( !(unsigned int)winreDoesFileExist(a1, L"install.wim") || !(unsigned int)winreDoesFileExist(a1, L"setup.exe") )
  {
    CurrentOsArch = 2;
    goto LABEL_17;
  }
  CurrentOsArch = winreAllocPath(&v21);
  if ( CurrentOsArch )
  {
    UnattendLogW(
      2,
      L"winreFindInstallMedia %s (0x%x) in file %S line %d",
      L"failed to allocate path",
      CurrentOsArch,
      "base\\diagnosis\\srt\\reagent2\\reagent\\setup.cpp",
      123);
    v4 = v21;
    goto LABEL_33;
  }
  v4 = v21;
  CurrentOsArch = winreAddFileToDirPath(a1, L"setup.exe", v21);
  if ( CurrentOsArch )
  {
    v14 = 127;
    v11 = L"failed to add setup.exe to directory path";
LABEL_24:
    UnattendLogW(
      2,
      L"winreFindInstallMedia %s (0x%x) in file %S line %d",
      v11,
      CurrentOsArch,
      "base\\diagnosis\\srt\\reagent2\\reagent\\setup.cpp",
      v14);
    goto LABEL_33;
  }
  if ( !(unsigned int)winreGetBinaryArch(v4, &v20, &v16, &v18) )
  {
    LastError = GetLastError();
    v14 = 131;
    v11 = L"failed to get binary architecture";
    CurrentOsArch = LastError;
    goto LABEL_24;
  }
  if ( v16 == v15 && v18 == v17 && v20 == v19 )
  {
    CurrentOsArch = 0;
    *a2 = 1;
  }
  else
  {
    CurrentOsArch = 216;
  }
LABEL_33:
  FindVolumeClose(FirstVolumeW);
  if ( v4 )
    CoTaskMemFree(v4);
LABEL_35:
  UnattendLogW(0, L"Exit winreFindInstallMedia return error code: 0x%x", CurrentOsArch);
  UnattendFinalizeLog();
  return CurrentOsArch;
}

```

## disassembly

```asm
0x180030770  mov     [rsp-38h+arg_18], rbx
0x180030775  push    rbp
0x180030776  push    rsi
0x180030777  push    rdi
0x180030778  push    r12
0x18003077a  push    r13
0x18003077c  push    r14
0x18003077e  push    r15
0x180030780  mov     rbp, rsp
0x180030783  sub     rsp, 60h
0x180030787  mov     rax, cs:__security_cookie
0x18003078e  xor     rax, rsp
0x180030791  mov     [rbp+var_8], rax
0x180030795  xor     edi, edi
0x180030797  mov     rsi, rcx
0x18003079a  xor     ecx, ecx
0x18003079c  mov     [rbp+var_18], rdi
0x1800307a0  mov     r14d, edi
0x1800307a3  mov     [rbp+var_1C], edi
0x1800307a6  mov     [rbp+var_2C], edi
0x1800307a9  mov     r12, r8
0x1800307ac  mov     [rbp+var_24], edi
0x1800307af  mov     r13, rdx
0x1800307b2  mov     [rbp+var_20], edi
0x1800307b5  mov     [rbp+var_30], edi
0x1800307b8  mov     [rbp+var_28], edi
0x1800307bb  mov     [rbp+cchReturnLength], edi
0x1800307be  call    UnattendInitializeLogEx2
0x1800307c3  lea     rdx, aEnterWinrefind; "Enter winreFindInstallMedia"
0x1800307ca  xor     ecx, ecx
0x1800307cc  call    UnattendLogW
0x1800307d1  lea     rax, aNull_0; "NULL"
0x1800307d8  test    r12, r12
0x1800307db  mov     r9, r12
0x1800307de  lea     rdx, aParametersVolp; "Parameters: volPath: %s, DosPath: %s"
0x1800307e5  cmovz   r9, rax
0x1800307e9  mov     r8, rsi
0x1800307ec  test    rsi, rsi
0x1800307ef  cmovz   r8, rax
0x1800307f3  xor     ecx, ecx
0x1800307f5  call    UnattendLogW
0x1800307fa  lea     r8, [rbp+var_28]
0x1800307fe  lea     rdx, [rbp+var_30]
0x180030802  lea     rcx, [rbp+var_20]
0x180030806  call    winreGetCurrentOsArch
0x18003080b  mov     ebx, eax
0x18003080d  test    eax, eax
0x18003080f  jz      short loc_180030843
0x180030811  lea     rax, aBaseDiagnosisS_5; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180030818  mov     [rsp+60h+var_38], 3Eh ; '>'
0x180030820  mov     r9d, ebx
0x180030823  mov     [rsp+60h+var_40], rax
0x180030828  lea     r8, aFailedToGetCur; "failed to get current OS architecture"
0x18003082f  lea     rdx, aWinrefindinsta_0; "winreFindInstallMedia %s (0x%x) in file"...
0x180030836  lea     ecx, [rdi+2]
0x180030839  call    UnattendLogW
0x18003083e  jmp     loc_180030A28
0x180030843  mov     edx, 12Eh; cchBufferLength
0x180030848  mov     rcx, rsi; lpszVolumeName
0x18003084b  call    cs:__imp_FindFirstVolumeW
0x180030851  mov     r15, rax
0x180030854  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030858  jnz     short loc_180030867
0x18003085a  call    cs:__imp_GetLastError
0x180030860  mov     ebx, eax
0x180030862  jmp     loc_180030A28
0x180030867  mov     edi, 2
0x18003086c  mov     rcx, rsi; lpRootPathName
0x18003086f  call    cs:__imp_GetDriveTypeW
0x180030875  cmp     eax, 5
0x180030878  jnz     short loc_1800308F9
0x18003087a  test    r12, r12
0x18003087d  jz      short loc_1800308B5
0x18003087f  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x180030883  mov     r8d, 104h; cchBufferLength
0x180030889  mov     rdx, r12; lpszVolumePathNames
0x18003088c  mov     rcx, rsi; lpszVolumeName
0x18003088f  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180030895  test    eax, eax
0x180030897  jz      short loc_180030918
0x180030899  lea     r8, aSources; "sources"
0x1800308a0  mov     edx, 12Eh; unsigned __int64
0x1800308a5  mov     rcx, r12; unsigned __int16 *
0x1800308a8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800308ad  test    eax, eax
0x1800308af  js      loc_180030A0F
0x1800308b5  lea     r8, aSources; "sources"
0x1800308bc  mov     edx, 12Eh; unsigned __int64
0x1800308c1  mov     rcx, rsi; unsigned __int16 *
0x1800308c4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800308c9  test    eax, eax
0x1800308cb  js      loc_180030A0F
0x1800308d1  lea     rdx, aInstallWim; "install.wim"
0x1800308d8  mov     rcx, rsi; unsigned __int16 *
0x1800308db  call    winreDoesFileExist
0x1800308e0  test    eax, eax
0x1800308e2  jz      short loc_1800308F7
0x1800308e4  lea     rdx, aSetupExe; "setup.exe"
0x1800308eb  mov     rcx, rsi; unsigned __int16 *
0x1800308ee  call    winreDoesFileExist
0x1800308f3  test    eax, eax
0x1800308f5  jnz     short loc_180030925
0x1800308f7  mov     ebx, edi
0x1800308f9  mov     r8d, 12Eh; cchBufferLength
0x1800308ff  mov     rdx, rsi; lpszVolumeName
0x180030902  mov     rcx, r15; hFindVolume
0x180030905  call    cs:__imp_FindNextVolumeW
0x18003090b  test    eax, eax
0x18003090d  jnz     loc_18003086C
0x180030913  jmp     loc_180030A11
0x180030918  call    cs:__imp_GetLastError
0x18003091e  mov     ebx, eax
0x180030920  jmp     loc_180030A11
0x180030925  lea     rcx, [rbp+var_18]
0x180030929  call    winreAllocPath
0x18003092e  mov     ebx, eax
0x180030930  test    eax, eax
0x180030932  jz      short loc_180030969
0x180030934  lea     rax, aBaseDiagnosisS_5; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003093b  mov     [rsp+60h+var_38], 7Bh ; '{'
0x180030943  mov     r9d, ebx
0x180030946  mov     [rsp+60h+var_40], rax
0x18003094b  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180030952  mov     ecx, edi
0x180030954  lea     rdx, aWinrefindinsta_0; "winreFindInstallMedia %s (0x%x) in file"...
0x18003095b  call    UnattendLogW
0x180030960  mov     r14, [rbp+var_18]
0x180030964  jmp     loc_180030A11
0x180030969  mov     r14, [rbp+var_18]
0x18003096d  lea     rdx, aSetupExe; "setup.exe"
0x180030974  mov     r8, r14; unsigned __int16 *
0x180030977  mov     rcx, rsi; unsigned __int16 *
0x18003097a  call    winreAddFileToDirPath
0x18003097f  mov     ebx, eax
0x180030981  test    eax, eax
0x180030983  jz      short loc_1800309B3
0x180030985  mov     [rsp+60h+var_38], 7Fh
0x18003098d  lea     r8, aFailedToAddSet; "failed to add setup.exe to directory pa"...
0x180030994  lea     rax, aBaseDiagnosisS_5; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003099b  mov     r9d, ebx
0x18003099e  lea     rdx, aWinrefindinsta_0; "winreFindInstallMedia %s (0x%x) in file"...
0x1800309a5  mov     [rsp+60h+var_40], rax
0x1800309aa  mov     ecx, edi
0x1800309ac  call    UnattendLogW
0x1800309b1  jmp     short loc_180030A11
0x1800309b3  lea     r9, [rbp+var_24]
0x1800309b7  mov     rcx, r14
0x1800309ba  lea     r8, [rbp+var_2C]
0x1800309be  lea     rdx, [rbp+var_1C]
0x1800309c2  call    winreGetBinaryArch
0x1800309c7  test    eax, eax
0x1800309c9  jnz     short loc_1800309E4
0x1800309cb  call    cs:__imp_GetLastError
0x1800309d1  mov     [rsp+60h+var_38], 83h
0x1800309d9  lea     r8, aFailedToGetBin; "failed to get binary architecture"
0x1800309e0  mov     ebx, eax
0x1800309e2  jmp     short loc_180030994
0x1800309e4  mov     eax, [rbp+var_30]
0x1800309e7  cmp     [rbp+var_2C], eax
0x1800309ea  jnz     short loc_180030A08
0x1800309ec  mov     eax, [rbp+var_28]
0x1800309ef  cmp     [rbp+var_24], eax
0x1800309f2  jnz     short loc_180030A08
0x1800309f4  mov     eax, [rbp+var_20]
0x1800309f7  cmp     [rbp+var_1C], eax
0x1800309fa  jnz     short loc_180030A08
0x1800309fc  xor     ebx, ebx
0x1800309fe  mov     dword ptr [r13+0], 1
0x180030a06  jmp     short loc_180030A11
0x180030a08  mov     ebx, 0D8h
0x180030a0d  jmp     short loc_180030A11
0x180030a0f  mov     ebx, edi
0x180030a11  mov     rcx, r15; hFindVolume
0x180030a14  call    cs:__imp_FindVolumeClose
0x180030a1a  test    r14, r14
0x180030a1d  jz      short loc_180030A28
0x180030a1f  mov     rcx, r14; pv
0x180030a22  call    cs:__imp_CoTaskMemFree
0x180030a28  mov     r8d, ebx
0x180030a2b  lea     rdx, aExitWinrefindi; "Exit winreFindInstallMedia return error"...
0x180030a32  xor     ecx, ecx
0x180030a34  call    UnattendLogW
0x180030a39  call    UnattendFinalizeLog
0x180030a3e  mov     eax, ebx
0x180030a40  mov     rcx, [rbp+var_8]
0x180030a44  xor     rcx, rsp; StackCookie
0x180030a47  call    __security_check_cookie
0x180030a4c  mov     rbx, [rsp+60h+arg_18]
0x180030a54  add     rsp, 60h
0x180030a58  pop     r15
0x180030a5a  pop     r14
0x180030a5c  pop     r13
0x180030a5e  pop     r12
0x180030a60  pop     rdi
0x180030a61  pop     rsi
0x180030a62  pop     rbp
0x180030a63  retn
```
