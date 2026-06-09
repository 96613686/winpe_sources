# WinReSetupInstall

- ea: `0x18001ab30`
- end: `0x18001af16`
- name: `WinReSetupInstall`
- size: `998`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000fe58`
- `0x1800193e8`
- `0x18001ab30`
- `0x180030f18`
- `0x180031bb8`
- `0x180031e10`
- `0x18003bea8`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18001aeac`
- `KERNEL32!CopyFileW` at `0x18001aeac`
- `KERNEL32!GetLastError` at `0x18001aeb6`
- `KERNEL32!GetLastError` at `0x18001aeb6`
- `KERNEL32!RemoveDirectoryW` at `0x18001ae11`
- `KERNEL32!RemoveDirectoryW` at `0x18001ae11`
- `KERNEL32!SetLastError` at `0x18001aeeb`
- `KERNEL32!SetLastError` at `0x18001aeeb`
- `KERNEL32!DeleteFileW` at `0x18001ae04`
- `KERNEL32!DeleteFileW` at `0x18001ae04`

## string_xrefs

- `0x18001abfa`: `Enter WinReSetupInstall`
- `0x18001addc`: `get downlevel config file path by guid failed: 0x%x`
- `0x18001adf1`: `Downlevel WinRE config file path: %s`
- `0x18001ae1c`: ` Failed to install WinRE. Copying winre.wim to the target OS staging location`
- `0x18001ae46`: ` Failed to construct source winre.wim path: 0x%x`
- `0x18001ae76`: ` Failed to construct destination winre.wim path: 0x%x`
- `0x18001ae8f`: `() Copy file %s to %s`
- `0x18001aebc`: ` Failed to copy winre.wim to the target OS staging location: 0X%X `
- `0x18001aed3`: `Exit WinReSetupInstall return value: %d, last error: 0x%x`

## pseudocode

```c
__int64 __fastcall WinReSetupInstall(__int64 a1, unsigned __int16 *a2, unsigned int a3, __int64 a4, _BYTE *a5)
{
  unsigned int v9; // esi
  const unsigned __int16 *v10; // r8
  DWORD v11; // ebx
  int v12; // edi
  int v13; // eax
  __int128 v14; // xmm0
  __int64 v15; // r11
  DWORD DownlevelConfigFilePathByGuid; // eax
  DWORD v17; // eax
  DWORD SourceFile; // eax
  DWORD LastError; // eax
  _DWORD v21[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[17]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+81h] [rbp-7Fh]
  int v24; // [rsp+89h] [rbp-77h]
  __int16 v25; // [rsp+8Dh] [rbp-73h]
  char v26; // [rsp+8Fh] [rbp-71h]
  int v27; // [rsp+90h] [rbp-70h]
  __int128 v28; // [rsp+94h] [rbp-6Ch]
  unsigned __int16 v29[302]; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned __int16 v30[304]; // [rsp+300h] [rbp+200h] BYREF
  __int64 v31; // [rsp+560h] [rbp+460h]
  __int64 v32; // [rsp+568h] [rbp+468h]
  int v33; // [rsp+580h] [rbp+480h]
  int v34; // [rsp+584h] [rbp+484h]
  int v35; // [rsp+588h] [rbp+488h]
  int v36; // [rsp+58Ch] [rbp+48Ch]
  int v37; // [rsp+590h] [rbp+490h]
  int v38; // [rsp+594h] [rbp+494h]
  int v39; // [rsp+598h] [rbp+498h]
  GUID v40; // [rsp+5A0h] [rbp+4A0h] BYREF
  WCHAR FileName; // [rsp+5B0h] [rbp+4B0h] BYREF
  _BYTE v42[606]; // [rsp+5B2h] [rbp+4B2h] BYREF
  WCHAR NewFileName; // [rsp+810h] [rbp+710h] BYREF
  _BYTE v44[606]; // [rsp+812h] [rbp+712h] BYREF
  WCHAR ExistingFileName; // [rsp+A70h] [rbp+970h] BYREF
  _BYTE v46[606]; // [rsp+A72h] [rbp+972h] BYREF
  WCHAR PathName; // [rsp+CD0h] [rbp+BD0h] BYREF
  _BYTE v48[606]; // [rsp+CD2h] [rbp+BD2h] BYREF

  PathName = 0;
  v40 = GUID_NULL;
  v9 = 0;
  memset_0(v48, 0, 0x25Au);
  FileName = 0;
  memset_0(v42, 0, 0x25Au);
  v21[0] = 0;
  ExistingFileName = 0;
  memset_0(v46, 0, 0x25Au);
  NewFileName = 0;
  memset_0(v44, 0, 0x25Au);
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetupInstall");
  v10 = a2;
  if ( !a2 )
    v10 = L"NULL";
  UnattendLogW(0, L"Parameters: StagedWinRELocation: %s, AllowDiskPartitionChanges: %d", v10, a3);
  LogGuid(L"newOSBCDGuid", a1);
  if ( a5 )
    memset_0(a5, 0, 0x510u);
  if ( (unsigned int)winreGetOSGuidOrDefault(a1, &v40) )
  {
    memset_0(v22, 0, 0x530u);
    if ( (unsigned int)WinReInstallOnTargetOSInternal(0, 0, &v40, 1, a2, a3, 0, 0, a4, v21, v22) )
    {
      UnattendLogW(0, L" Failed to install WinRE. Copying winre.wim to the target OS staging location");
      v17 = winreAddFileToDirPath(a2, L"Winre.wim", &ExistingFileName);
      v11 = v17;
      if ( v17 )
      {
        UnattendLogW(2, L" Failed to construct source winre.wim path: 0x%x", v17);
      }
      else
      {
        SourceFile = winreGetSourceFile(&v40, &cchOriginalDestLength, L"Winre.wim", &NewFileName);
        v11 = SourceFile;
        if ( SourceFile )
        {
          UnattendLogW(2, L" Failed to construct destination winre.wim path: 0x%x", SourceFile);
        }
        else
        {
          UnattendLogW(0, L"() Copy file %s to %s", &ExistingFileName, &NewFileName);
          if ( !CopyFileW(&ExistingFileName, &NewFileName, 0) )
          {
            LastError = GetLastError();
            UnattendLogW(2, L" Failed to copy winre.wim to the target OS staging location: 0X%X ", LastError);
          }
        }
      }
    }
    else
    {
      v9 = 1;
      if ( a5 && v31 )
      {
        v12 = v36;
        *a5 = v22[16];
        if ( !v12 )
        {
          v13 = v24;
          *(_QWORD *)(a5 + 1) = v23;
          *(_DWORD *)(a5 + 9) = v13;
          *(_WORD *)(a5 + 13) = v25;
          a5[15] = v26;
        }
        v14 = v28;
        *((_DWORD *)a5 + 4) = v27;
        *(_OWORD *)(a5 + 20) = v14;
        StringCchCopyW((unsigned __int16 *)a5 + 18, 0x12Eu, v29);
        StringCchCopyW((unsigned __int16 *)a5 + 320, 0x12Eu, v30);
        *((_QWORD *)a5 + 157) = v32;
        *((_DWORD *)a5 + 316) = v33;
        *((_DWORD *)a5 + 317) = v34;
        *((_DWORD *)a5 + 318) = v35;
        *((_DWORD *)a5 + 320) = v37;
        *((_DWORD *)a5 + 321) = v38;
        *((_DWORD *)a5 + 322) = v39;
        *((_QWORD *)a5 + 156) = v15;
        *((_DWORD *)a5 + 319) = v12;
      }
      DownlevelConfigFilePathByGuid = winreGetDownlevelConfigFilePathByGuid(&v40, &PathName, &FileName);
      v11 = DownlevelConfigFilePathByGuid;
      if ( DownlevelConfigFilePathByGuid )
      {
        UnattendLogW(2, L"get downlevel config file path by guid failed: 0x%x", DownlevelConfigFilePathByGuid);
      }
      else
      {
        UnattendLogW(0, L"Downlevel WinRE config file path: %s", &FileName);
        DeleteFileW(&FileName);
        RemoveDirectoryW(&PathName);
      }
    }
  }
  else
  {
    v11 = 0;
    UnattendLogW(2, L"failed to get os guid or default");
  }
  UnattendLogW(0, L"Exit WinReSetupInstall return value: %d, last error: 0x%x", v9, v11);
  UnattendFinalizeLog();
  SetLastError(v11);
  return v9;
}

```

## disassembly

```asm
0x18001ab30  push    rbp
0x18001ab32  push    rbx
0x18001ab33  push    rsi
0x18001ab34  push    rdi
0x18001ab35  push    r12
0x18001ab37  push    r13
0x18001ab39  push    r14
0x18001ab3b  push    r15
0x18001ab3d  lea     rbp, [rsp-0E48h]
0x18001ab45  sub     rsp, 0F48h
0x18001ab4c  mov     rax, cs:__security_cookie
0x18001ab53  xor     rax, rsp
0x18001ab56  mov     [rbp+0E80h+var_50], rax
0x18001ab5d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001ab64  mov     rbx, [rbp+0E80h+arg_20]
0x18001ab6b  mov     r15d, r8d
0x18001ab6e  mov     rdi, rdx
0x18001ab71  mov     r14, rcx
0x18001ab74  xor     eax, eax
0x18001ab76  lea     rcx, [rbp+0E80h+var_2AE]; void *
0x18001ab7d  mov     r13d, 25Ah
0x18001ab83  mov     [rbp+0E80h+PathName], ax
0x18001ab8a  mov     r8d, r13d; Size
0x18001ab8d  xor     edx, edx; Val
0x18001ab8f  movdqu  [rbp+0E80h+var_9E0], xmm0
0x18001ab97  mov     r12, r9
0x18001ab9a  xor     esi, esi
0x18001ab9c  call    memset_0
0x18001aba1  xor     eax, eax
0x18001aba3  lea     rcx, [rbp+0E80h+var_9CE]; void *
0x18001abaa  mov     r8d, r13d; Size
0x18001abad  mov     [rbp+0E80h+FileName], ax
0x18001abb4  xor     edx, edx; Val
0x18001abb6  call    memset_0
0x18001abbb  xor     eax, eax
0x18001abbd  mov     [rsp+0F80h+var_F20], esi
0x18001abc1  mov     r8d, r13d; Size
0x18001abc4  mov     [rbp+0E80h+ExistingFileName], ax
0x18001abcb  xor     edx, edx; Val
0x18001abcd  lea     rcx, [rbp+0E80h+var_50E]; void *
0x18001abd4  call    memset_0
0x18001abd9  xor     eax, eax
0x18001abdb  lea     rcx, [rbp+0E80h+var_76E]; void *
0x18001abe2  mov     r8d, r13d; Size
0x18001abe5  mov     [rbp+0E80h+NewFileName], ax
0x18001abec  xor     edx, edx; Val
0x18001abee  call    memset_0
0x18001abf3  xor     ecx, ecx
0x18001abf5  call    UnattendInitializeLogEx2
0x18001abfa  lea     rdx, aEnterWinresetu_2; "Enter WinReSetupInstall"
0x18001ac01  xor     ecx, ecx
0x18001ac03  call    UnattendLogW
0x18001ac08  lea     rax, aNull_0; "NULL"
0x18001ac0f  test    rdi, rdi
0x18001ac12  mov     r8, rdi
0x18001ac15  lea     rdx, aParametersStag; "Parameters: StagedWinRELocation: %s, Al"...
0x18001ac1c  cmovz   r8, rax
0x18001ac20  mov     r9d, r15d
0x18001ac23  xor     ecx, ecx
0x18001ac25  call    UnattendLogW
0x18001ac2a  mov     rdx, r14
0x18001ac2d  lea     rcx, aNewosbcdguid; "newOSBCDGuid"
0x18001ac34  call    LogGuid
0x18001ac39  test    rbx, rbx
0x18001ac3c  jz      short loc_18001AC4E
0x18001ac3e  xor     edx, edx; Val
0x18001ac40  mov     r8d, 510h; Size
0x18001ac46  mov     rcx, rbx; void *
0x18001ac49  call    memset_0
0x18001ac4e  lea     rdx, [rbp+0E80h+var_9E0]
0x18001ac55  mov     rcx, r14
0x18001ac58  call    winreGetOSGuidOrDefault
0x18001ac5d  test    eax, eax
0x18001ac5f  jnz     short loc_18001AC77
0x18001ac61  xor     ebx, ebx
0x18001ac63  lea     rdx, aFailedToGetOsG_0; "failed to get os guid or default"
0x18001ac6a  lea     ecx, [rax+2]
0x18001ac6d  call    UnattendLogW
0x18001ac72  jmp     loc_18001AED0
0x18001ac77  xor     edx, edx; Val
0x18001ac79  lea     rcx, [rsp+0F80h+var_F10]; void *
0x18001ac7e  mov     r8d, 530h; Size
0x18001ac84  call    memset_0
0x18001ac89  lea     rax, [rsp+0F80h+var_F10]
0x18001ac8e  mov     r14d, 1
0x18001ac94  mov     [rsp+0F80h+var_F30], rax
0x18001ac99  lea     r8, [rbp+0E80h+var_9E0]
0x18001aca0  lea     rax, [rsp+0F80h+var_F20]
0x18001aca5  mov     r9d, r14d
0x18001aca8  mov     [rsp+0F80h+var_F38], rax
0x18001acad  xor     edx, edx
0x18001acaf  mov     [rsp+0F80h+var_F40], r12
0x18001acb4  xor     ecx, ecx
0x18001acb6  mov     [rsp+0F80h+var_F48], esi
0x18001acba  mov     [rsp+0F80h+var_F50], esi
0x18001acbe  mov     [rsp+0F80h+var_F58], r15d
0x18001acc3  mov     [rsp+0F80h+var_F60], rdi
0x18001acc8  call    ?WinReInstallOnTargetOSInternal@@YAKHPEAHPEAU_GUID@@HPEBGHKW4_WINRE_PARTITION_LOCATION@@20PEAUPartitionNode@@@Z; WinReInstallOnTargetOSInternal(int,int *,_GUID *,int,ushort const *,int,ulong,_WINRE_PARTITION_LOCATION,ushort const *,int *,PartitionNode *)
0x18001accd  test    eax, eax
0x18001accf  jnz     loc_18001AE1C
0x18001acd5  mov     esi, r14d
0x18001acd8  test    rbx, rbx
0x18001acdb  jz      loc_18001ADBC
0x18001ace1  mov     r11, [rbp+0E80h+var_A20]
0x18001ace8  test    r11, r11
0x18001aceb  jz      loc_18001ADBC
0x18001acf1  mov     edi, [rbp+0E80h+var_9F4]
0x18001acf7  mov     al, [rbp+0E80h+var_F00]
0x18001acfa  mov     [rbx], al
0x18001acfc  test    edi, edi
0x18001acfe  jnz     short loc_18001AD1E
0x18001ad00  mov     eax, [rbp+0E80h+var_EF7]
0x18001ad03  movsd   xmm0, [rbp+0E80h+var_EFF]
0x18001ad08  movsd   qword ptr [rbx+1], xmm0
0x18001ad0d  mov     [rbx+9], eax
0x18001ad10  movzx   eax, [rbp+0E80h+var_EF3]
0x18001ad14  mov     [rbx+0Dh], ax
0x18001ad18  mov     al, [rbp+0E80h+var_EF1]
0x18001ad1b  mov     [rbx+0Fh], al
0x18001ad1e  mov     eax, [rbp+0E80h+var_EF0]
0x18001ad21  lea     rcx, [rbx+24h]; unsigned __int16 *
0x18001ad25  movups  xmm0, [rbp+0E80h+var_EEC]
0x18001ad29  mov     r14d, 12Eh
0x18001ad2f  mov     [rbx+10h], eax
0x18001ad32  lea     r8, [rbp+0E80h+var_EDC]; unsigned __int16 *
0x18001ad36  mov     edx, r14d; unsigned __int64
0x18001ad39  movdqu  xmmword ptr [rbx+14h], xmm0
0x18001ad3e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ad43  lea     rcx, [rbx+280h]; unsigned __int16 *
0x18001ad4a  mov     edx, r14d; unsigned __int64
0x18001ad4d  lea     r8, [rbp+0E80h+var_C80]; unsigned __int16 *
0x18001ad54  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ad59  mov     rax, [rbp+0E80h+var_A18]
0x18001ad60  mov     [rbx+4E8h], rax
0x18001ad67  mov     eax, [rbp+0E80h+var_A00]
0x18001ad6d  mov     [rbx+4F0h], eax
0x18001ad73  mov     eax, [rbp+0E80h+var_9FC]
0x18001ad79  mov     [rbx+4F4h], eax
0x18001ad7f  mov     eax, [rbp+0E80h+var_9F8]
0x18001ad85  mov     [rbx+4F8h], eax
0x18001ad8b  mov     eax, [rbp+0E80h+var_9F0]
0x18001ad91  mov     [rbx+500h], eax
0x18001ad97  mov     eax, [rbp+0E80h+var_9EC]
0x18001ad9d  mov     [rbx+504h], eax
0x18001ada3  mov     eax, [rbp+0E80h+var_9E8]
0x18001ada9  mov     [rbx+508h], eax
0x18001adaf  mov     [rbx+4E0h], r11
0x18001adb6  mov     [rbx+4FCh], edi
0x18001adbc  lea     r8, [rbp+0E80h+FileName]
0x18001adc3  lea     rdx, [rbp+0E80h+PathName]
0x18001adca  lea     rcx, [rbp+0E80h+var_9E0]
0x18001add1  call    winreGetDownlevelConfigFilePathByGuid
0x18001add6  mov     ebx, eax
0x18001add8  test    eax, eax
0x18001adda  jz      short loc_18001ADE8
0x18001addc  lea     rdx, aGetDownlevelCo; "get downlevel config file path by guid "...
0x18001ade3  jmp     loc_18001AEC3
0x18001ade8  lea     r8, [rbp+0E80h+FileName]
0x18001adef  xor     ecx, ecx
0x18001adf1  lea     rdx, aDownlevelWinre; "Downlevel WinRE config file path: %s"
0x18001adf8  call    UnattendLogW
0x18001adfd  lea     rcx, [rbp+0E80h+FileName]; lpFileName
0x18001ae04  call    cs:__imp_DeleteFileW
0x18001ae0a  lea     rcx, [rbp+0E80h+PathName]; lpPathName
0x18001ae11  call    cs:__imp_RemoveDirectoryW
0x18001ae17  jmp     loc_18001AED0
0x18001ae1c  lea     rdx, aFailedToInstal; " Failed to install WinRE. Copying winre"...
0x18001ae23  xor     ecx, ecx
0x18001ae25  call    UnattendLogW
0x18001ae2a  lea     r8, [rbp+0E80h+ExistingFileName]; unsigned __int16 *
0x18001ae31  mov     rcx, rdi; unsigned __int16 *
0x18001ae34  lea     rdx, aWinreWim; "Winre.wim"
0x18001ae3b  call    winreAddFileToDirPath
0x18001ae40  mov     ebx, eax
0x18001ae42  test    eax, eax
0x18001ae44  jz      short loc_18001AE4F
0x18001ae46  lea     rdx, aFailedToConstr_2; " Failed to construct source winre.wim p"...
0x18001ae4d  jmp     short loc_18001AEC3
0x18001ae4f  lea     r9, [rbp+0E80h+NewFileName]
0x18001ae56  lea     r8, aWinreWim; "Winre.wim"
0x18001ae5d  lea     rdx, cchOriginalDestLength
0x18001ae64  lea     rcx, [rbp+0E80h+var_9E0]
0x18001ae6b  call    winreGetSourceFile
0x18001ae70  mov     ebx, eax
0x18001ae72  test    eax, eax
0x18001ae74  jz      short loc_18001AE7F
0x18001ae76  lea     rdx, aFailedToConstr_0; " Failed to construct destination winre."...
0x18001ae7d  jmp     short loc_18001AEC3
0x18001ae7f  lea     r9, [rbp+0E80h+NewFileName]
0x18001ae86  xor     ecx, ecx
0x18001ae88  lea     r8, [rbp+0E80h+ExistingFileName]
0x18001ae8f  lea     rdx, aCopyFileSToS; "() Copy file %s to %s"
0x18001ae96  call    UnattendLogW
0x18001ae9b  xor     r8d, r8d; bFailIfExists
0x18001ae9e  lea     rdx, [rbp+0E80h+NewFileName]; lpNewFileName
0x18001aea5  lea     rcx, [rbp+0E80h+ExistingFileName]; lpExistingFileName
0x18001aeac  call    cs:__imp_CopyFileW
0x18001aeb2  test    eax, eax
0x18001aeb4  jnz     short loc_18001AED0
0x18001aeb6  call    cs:__imp_GetLastError
0x18001aebc  lea     rdx, aFailedToCopyWi_1; " Failed to copy winre.wim to the target"...
0x18001aec3  mov     r8d, eax
0x18001aec6  mov     ecx, 2
0x18001aecb  call    UnattendLogW
0x18001aed0  mov     r9d, ebx
0x18001aed3  lea     rdx, aExitWinresetup; "Exit WinReSetupInstall return value: %d"...
0x18001aeda  mov     r8d, esi
0x18001aedd  xor     ecx, ecx
0x18001aedf  call    UnattendLogW
0x18001aee4  call    UnattendFinalizeLog
0x18001aee9  mov     ecx, ebx; dwErrCode
0x18001aeeb  call    cs:__imp_SetLastError
0x18001aef1  mov     eax, esi
0x18001aef3  mov     rcx, [rbp+0E80h+var_50]
0x18001aefa  xor     rcx, rsp; StackCookie
0x18001aefd  call    __security_check_cookie
0x18001af02  add     rsp, 0F48h
0x18001af09  pop     r15
0x18001af0b  pop     r14
0x18001af0d  pop     r13
0x18001af0f  pop     r12
0x18001af11  pop     rdi
0x18001af12  pop     rsi
0x18001af13  pop     rbx
0x18001af14  pop     rbp
0x18001af15  retn
```
