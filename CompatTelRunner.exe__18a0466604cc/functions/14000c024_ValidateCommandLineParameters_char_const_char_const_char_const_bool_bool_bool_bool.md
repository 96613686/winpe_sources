# ValidateCommandLineParameters(char const *,char const *,char const *,bool,bool,bool,bool)

- ea: `0x14000c024`
- end: `0x14000c1f7`
- name: `?ValidateCommandLineParameters@@YAJPEBD00_N111@Z`
- size: `467`
- prototype: `__int64 __fastcall(const char *, const char *, const char *, char, bool, bool, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000c2f8`

## callees

- `0x14000c024`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x14000c1a8`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x14000c1a8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x14000c1cb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x14000c1cb`

## string_xrefs

- `0x14000c045`: `DoScheduledTelemetryRun`
- `0x14000c050`: `UpdateAvStatus`
- `0x14000c07c`: `RunUpdate`
- `0x14000c092`: `CreateDeviceInventory`
- `0x14000c09d`: `UpdateSoftwareInventoryW`
- `0x14000c0a8`: `UpdateSoftwareInventory`
- `0x14000c0df`: `appraiser.dll`
- `0x14000c0eb`: `generaltel.dll`
- `0x14000c0f7`: `invagent.dll`
- `0x14000c103`: `devinv.dll`
- `0x14000c10f`: `aeinv.dll`
- `0x14000c11b`: `aepic.dll`
- `0x14000c126`: `aemarebackup.dll`

## pseudocode

```c
__int64 __fastcall ValidateCommandLineParameters(
        const char *a1,
        const char *a2,
        const char *a3,
        char a4,
        bool a5,
        bool a6,
        bool a7)
{
  __int64 v10; // rdi
  char v11; // bl
  char v12; // si
  __int64 v13; // rdi
  _QWORD v14[8]; // [rsp+20h] [rbp-A1h]
  LPCSTR lpString2[20]; // [rsp+60h] [rbp-61h]

  lpString2[0] = "ContainerSetupWrapper";
  lpString2[1] = "DoScheduledTelemetryRun";
  lpString2[2] = "UpdateAvStatus";
  lpString2[3] = "RunGeneralTelemetry";
  lpString2[4] = "DoCensusRun";
  lpString2[5] = "RunInUserCxtW";
  lpString2[6] = "RunUpdate";
  lpString2[7] = "GetFileSigningInfo";
  lpString2[8] = "CreateDeviceInventory";
  lpString2[9] = "UpdateSoftwareInventoryW";
  lpString2[10] = "UpdateSoftwareInventory";
  lpString2[11] = "ProcessRestoreApps";
  lpString2[12] = "GetCITData";
  lpString2[13] = "GetApplicationKBs";
  lpString2[14] = "BackupMareData";
  v14[0] = "appraiser.dll";
  v14[1] = "generaltel.dll";
  v14[2] = "invagent.dll";
  v14[3] = "devinv.dll";
  v14[4] = "aeinv.dll";
  v14[5] = "aepic.dll";
  v14[6] = "aemarebackup.dll";
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a4 )
      {
        if ( a5 )
        {
LABEL_18:
          v10 = 0;
          v11 = 1;
          while ( (unsigned int)_o__stricmp(a1, v14[v10], a3) )
          {
            v10 = (unsigned int)(v10 + 1);
            if ( (unsigned int)v10 >= 7 )
            {
              v12 = 0;
              goto LABEL_23;
            }
          }
          v12 = 1;
LABEL_23:
          v13 = 0;
          while ( lstrcmpA(a2, lpString2[v13]) )
          {
            v13 = (unsigned int)(v13 + 1);
            if ( (unsigned int)v13 >= 0xF )
            {
              v11 = 0;
              break;
            }
          }
          if ( !v12 )
            return 2147942487LL;
          return v11 == 0 ? 0x80070057 : 0;
        }
      }
      else if ( !a5 )
      {
        goto LABEL_18;
      }
    }
    return 2147942487LL;
  }
  if ( a2 || a3 )
    return 2147942487LL;
  if ( a4 )
  {
    if ( !a5 || a6 || a7 )
      return 2147942487LL;
  }
  else if ( a5 || a6 || !a7 )
  {
    return 2147942487LL;
  }
  return 0;
}

```

## disassembly

```asm
0x14000c024  push    rbp
0x14000c026  push    rbx
0x14000c027  push    rsi
0x14000c028  push    rdi
0x14000c029  push    r14
0x14000c02b  lea     rbp, [rsp-1Fh]
0x14000c030  sub     rsp, 0E0h
0x14000c037  lea     rax, aContainersetup; "ContainerSetupWrapper"
0x14000c03e  mov     r14, rdx
0x14000c041  mov     [rbp+3Fh+lpString2], rax
0x14000c045  lea     rax, aDoscheduledtel; "DoScheduledTelemetryRun"
0x14000c04c  mov     [rbp+3Fh+var_98], rax
0x14000c050  lea     rax, aUpdateavstatus; "UpdateAvStatus"
0x14000c057  mov     [rbp+3Fh+var_90], rax
0x14000c05b  lea     rax, aRungeneraltele; "RunGeneralTelemetry"
0x14000c062  mov     [rbp+3Fh+var_88], rax
0x14000c066  lea     rax, aDocensusrun; "DoCensusRun"
0x14000c06d  mov     [rbp+3Fh+var_80], rax
0x14000c071  lea     rax, aRuninusercxtw; "RunInUserCxtW"
0x14000c078  mov     [rbp+3Fh+var_78], rax
0x14000c07c  lea     rax, aRunupdate; "RunUpdate"
0x14000c083  mov     [rbp+3Fh+var_70], rax
0x14000c087  lea     rax, aGetfilesigning; "GetFileSigningInfo"
0x14000c08e  mov     [rbp+3Fh+var_68], rax
0x14000c092  lea     rax, aCreatedevicein; "CreateDeviceInventory"
0x14000c099  mov     [rbp+3Fh+var_60], rax
0x14000c09d  lea     rax, aUpdatesoftware_0; "UpdateSoftwareInventoryW"
0x14000c0a4  mov     [rbp+3Fh+var_58], rax
0x14000c0a8  lea     rax, aUpdatesoftware; "UpdateSoftwareInventory"
0x14000c0af  mov     [rbp+3Fh+var_50], rax
0x14000c0b3  lea     rax, aProcessrestore; "ProcessRestoreApps"
0x14000c0ba  mov     [rbp+3Fh+var_48], rax
0x14000c0be  lea     rax, aGetcitdata; "GetCITData"
0x14000c0c5  mov     [rbp+3Fh+var_40], rax
0x14000c0c9  lea     rax, aGetapplication; "GetApplicationKBs"
0x14000c0d0  mov     [rbp+3Fh+var_38], rax
0x14000c0d4  lea     rax, aBackupmaredata; "BackupMareData"
0x14000c0db  mov     [rbp+3Fh+var_30], rax
0x14000c0df  lea     rax, aAppraiserDll; "appraiser.dll"
0x14000c0e6  mov     [rsp+100h+var_E0], rax
0x14000c0eb  lea     rax, aGeneraltelDll; "generaltel.dll"
0x14000c0f2  mov     [rsp+100h+var_D8], rax
0x14000c0f7  lea     rax, aInvagentDll; "invagent.dll"
0x14000c0fe  mov     [rsp+100h+var_D0], rax
0x14000c103  lea     rax, aDevinvDll; "devinv.dll"
0x14000c10a  mov     [rsp+100h+var_C8], rax
0x14000c10f  lea     rax, aAeinvDll; "aeinv.dll"
0x14000c116  mov     [rsp+100h+var_C0], rax
0x14000c11b  lea     rax, aAepicDll; "aepic.dll"
0x14000c122  mov     [rbp+3Fh+var_B8], rax
0x14000c126  lea     rax, aAemarebackupDl; "aemarebackup.dll"
0x14000c12d  mov     [rbp+3Fh+var_B0], rax
0x14000c131  mov     rsi, rcx
0x14000c134  test    rcx, rcx
0x14000c137  jnz     short loc_14000C183
0x14000c139  test    rdx, rdx
0x14000c13c  jnz     short loc_14000C15A
0x14000c13e  test    r8, r8
0x14000c141  jnz     short loc_14000C15A
0x14000c143  test    r9b, r9b
0x14000c146  jz      short loc_14000C16D
0x14000c148  cmp     [rbp+3Fh+arg_20], r8b
0x14000c14c  jz      short loc_14000C15A
0x14000c14e  cmp     [rbp+3Fh+arg_28], r8b
0x14000c152  jnz     short loc_14000C15A
0x14000c154  cmp     [rbp+3Fh+arg_30], r8b
0x14000c158  jz      short loc_14000C17F
0x14000c15a  mov     eax, 80070057h
0x14000c15f  add     rsp, 0E0h
0x14000c166  pop     r14
0x14000c168  pop     rdi
0x14000c169  pop     rsi
0x14000c16a  pop     rbx
0x14000c16b  pop     rbp
0x14000c16c  retn
0x14000c16d  cmp     [rbp+3Fh+arg_20], 0
0x14000c171  jnz     short loc_14000C15A
0x14000c173  cmp     [rbp+3Fh+arg_28], 0
0x14000c177  jnz     short loc_14000C15A
0x14000c179  cmp     [rbp+3Fh+arg_30], 0
0x14000c17d  jz      short loc_14000C15A
0x14000c17f  xor     eax, eax
0x14000c181  jmp     short loc_14000C15F
0x14000c183  test    r14, r14
0x14000c186  jz      short loc_14000C15A
0x14000c188  test    r9b, r9b
0x14000c18b  jz      short loc_14000C195
0x14000c18d  cmp     [rbp+3Fh+arg_20], 0
0x14000c191  jz      short loc_14000C15A
0x14000c193  jmp     short loc_14000C19B
0x14000c195  cmp     [rbp+3Fh+arg_20], 0
0x14000c199  jnz     short loc_14000C15A
0x14000c19b  xor     edi, edi
0x14000c19d  lea     ebx, [rdi+1]
0x14000c1a0  mov     rdx, [rsp+rdi*8+100h+var_E0]
0x14000c1a5  mov     rcx, rsi
0x14000c1a8  call    cs:__imp__o__stricmp
0x14000c1ae  test    eax, eax
0x14000c1b0  jz      short loc_14000C1BE
0x14000c1b2  add     edi, ebx
0x14000c1b4  cmp     edi, 7
0x14000c1b7  jb      short loc_14000C1A0
0x14000c1b9  xor     sil, sil
0x14000c1bc  jmp     short loc_14000C1C1
0x14000c1be  mov     sil, bl
0x14000c1c1  xor     edi, edi
0x14000c1c3  mov     rdx, [rbp+rdi*8+3Fh+lpString2]; lpString2
0x14000c1c8  mov     rcx, r14; lpString1
0x14000c1cb  call    cs:__imp_lstrcmpA
0x14000c1d1  test    eax, eax
0x14000c1d3  jz      short loc_14000C1DE
0x14000c1d5  add     edi, ebx
0x14000c1d7  cmp     edi, 0Fh
0x14000c1da  jb      short loc_14000C1C3
0x14000c1dc  xor     bl, bl
0x14000c1de  test    sil, sil
0x14000c1e1  jz      loc_14000C15A
0x14000c1e7  neg     bl
0x14000c1e9  sbb     eax, eax
0x14000c1eb  not     eax
0x14000c1ed  and     eax, 80070057h
0x14000c1f2  jmp     loc_14000C15F
```
