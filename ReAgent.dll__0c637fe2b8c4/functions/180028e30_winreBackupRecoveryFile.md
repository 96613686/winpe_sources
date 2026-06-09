# winreBackupRecoveryFile

- ea: `0x180028e30`
- end: `0x18002906d`
- name: `winreBackupRecoveryFile`
- size: `573`
- prototype: `__int64 __fastcall(unsigned __int16 *, ReAgentXMLParser *this, unsigned __int16 *)`
- caller_count: `10`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180018870`
- `0x180019a90`
- `0x18001a1ac`
- `0x18001e0e0`
- `0x180024a10`
- `0x180025a60`
- `0x180026158`
- `0x180026460`
- `0x180026670`
- `0x18002cab4`

## callees

- `0x1800059fc`
- `0x18000ffcc`
- `0x180011974`
- `0x18001c598`
- `0x180028e30`
- `0x180032728`
- `0x18004cfa0`
- `0x18004d0a4`
- `0x18004d230`
- `0x18004d52c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180028fb5`
- `KERNEL32!GetLastError` at `0x180028fb5`
- `KERNEL32!CopyFileExW` at `0x180028fab`
- `KERNEL32!CopyFileExW` at `0x180028fab`
- `ole32!CoTaskMemFree` at `0x180029023`
- `ole32!CoTaskMemFree` at `0x180029023`

## string_xrefs

- `0x180028f2f`: `failed to allocate path`
- `0x180028fe7`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180028ec0`: `WinRE is not installed, nothing to back up`
- `0x180028eea`: `WinRe directory(%s) not found`
- `0x180028f5b`: `failed to append path`
- `0x180028fbb`: `failed to copy file`
- `0x180028fda`: `failed to set ACL`

## pseudocode

```c
__int64 __fastcall winreBackupRecoveryFile(unsigned __int16 *a1, ReAgentXMLParser *this, unsigned __int16 *a3)
{
  struct ReAgentConfigInfo *ConfigInfo; // rax
  unsigned int appended; // ebx
  const unsigned __int16 *v7; // r14
  unsigned int v8; // eax
  unsigned __int16 *v9; // rdi
  const wchar_t *v10; // r8
  int v11; // r9d
  DWORD LastError; // eax
  LPBOOL pbCancel; // [rsp+20h] [rbp-39h]
  __int64 dwCopyFlags; // [rsp+28h] [rbp-31h]
  void **v16; // [rsp+30h] [rbp-29h] BYREF
  __int64 v17; // [rsp+38h] [rbp-21h]
  __int64 v18; // [rsp+40h] [rbp-19h]
  __int64 v19; // [rsp+48h] [rbp-11h]
  __int128 v20; // [rsp+50h] [rbp-9h]
  __int128 v21; // [rsp+60h] [rbp+7h]
  __int64 v22; // [rsp+70h] [rbp+17h]
  int v23; // [rsp+78h] [rbp+1Fh]
  __int64 v24; // [rsp+80h] [rbp+27h]
  LPCWSTR lpNewFileName; // [rsp+D8h] [rbp+7Fh] BYREF

  lpNewFileName = 0;
  v17 = 0;
  v20 = 0;
  v21 = 0;
  v16 = &ReAgentReload::`vftable';
  v18 = 0;
  v19 = 0x200000000LL;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  ConfigInfo = ReAgentXMLParser::GetConfigInfo(this);
  if ( !*((_DWORD *)ConfigInfo + 1397) )
  {
    UnattendLogW(0, L"WinRE is not installed, nothing to back up");
    appended = 0;
    goto LABEL_25;
  }
  v7 = (const unsigned __int16 *)((char *)ConfigInfo + 16);
  if ( Utils::DoesPathExist((const unsigned __int16 *)ConfigInfo + 8) )
  {
    appended = 3;
    UnattendLogW(2, L"WinRe directory(%s) not found", v7);
    goto LABEL_24;
  }
  if ( Utils::DoesPathExist(a1) )
  {
    appended = 2;
    UnattendLogW(2, L"Recovery file not found at %s", a1);
LABEL_24:
    LODWORD(pbCancel) = appended;
    UnattendLogW(2, L"winreBackupRecoveryFile (%s, %s) failed, Err: %lu", a1, a3, pbCancel);
    goto LABEL_25;
  }
  v8 = winreAllocPath(&lpNewFileName);
  v9 = (unsigned __int16 *)lpNewFileName;
  appended = v8;
  if ( v8 )
  {
    v10 = L"failed to allocate path";
    v11 = 1327;
  }
  else
  {
    appended = Utils::AppendPath(v7, a3, (unsigned __int16 *)lpNewFileName, 0x12Eu);
    if ( appended )
    {
      v10 = L"failed to append path";
      v11 = 1331;
    }
    else
    {
      if ( !v9 )
        goto LABEL_25;
      if ( Utils::CompareFileNames(a1, v9) )
        goto LABEL_21;
      Utils::DeleteReadOnlyFile(v9);
      if ( CopyFileExW(a1, v9, 0, 0, 0, 0x1000u) )
      {
        appended = winreSetACL(v9);
        if ( !appended )
          goto LABEL_21;
        v10 = L"failed to set ACL";
        v11 = 1343;
      }
      else
      {
        LastError = GetLastError();
        v10 = L"failed to copy file";
        v11 = 1342;
        appended = LastError;
      }
    }
  }
  LODWORD(dwCopyFlags) = v11;
  UnattendLogW(
    2,
    L"winreBackupRecoveryFile %s (0x%x) in file %S line %d",
    v10,
    appended,
    "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
    dwCopyFlags,
    v16,
    v17,
    v18,
    v19,
    (_QWORD)v20);
  if ( appended )
  {
    if ( !v9 )
      goto LABEL_24;
    Utils::DeleteReadOnlyFile(v9);
  }
LABEL_21:
  if ( v9 )
    CoTaskMemFree(v9);
  if ( appended )
    goto LABEL_24;
LABEL_25:
  ReAgentReload::~ReAgentReload((ReAgentReload *)&v16);
  return appended;
}

```

## disassembly

```asm
0x180028e30  mov     [rsp-8+arg_0], rbx
0x180028e35  mov     [rsp-8+arg_8], rsi
0x180028e3a  push    rbp
0x180028e3b  push    rdi
0x180028e3c  push    r13
0x180028e3e  push    r14
0x180028e40  push    r15
0x180028e42  lea     rbp, [rsp-37h]
0x180028e47  sub     rsp, 90h
0x180028e4e  mov     rsi, rcx
0x180028e51  mov     [rbp+57h+lpNewFileName], 0
0x180028e59  xorps   xmm0, xmm0
0x180028e5c  mov     [rbp+57h+var_78], 0
0x180028e64  xorps   xmm1, xmm1
0x180028e67  movdqa  [rbp+57h+var_60], xmm0
0x180028e6c  lea     rax, ??_7ReAgentReload@@6B@; const ReAgentReload::`vftable'
0x180028e73  movdqa  [rbp+57h+var_50], xmm1
0x180028e78  mov     r13d, 2
0x180028e7e  mov     [rbp+57h+var_80], rax
0x180028e82  mov     rcx, rdx; this
0x180028e85  mov     [rbp+57h+var_64], r13d
0x180028e89  mov     r15, r8
0x180028e8c  mov     [rbp+57h+var_70], 0
0x180028e94  mov     [rbp+57h+var_68], 0
0x180028e9b  mov     [rbp+57h+var_40], 0
0x180028ea3  mov     [rbp+57h+var_38], 0
0x180028eaa  mov     [rbp+57h+var_30], 0
0x180028eb2  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x180028eb7  cmp     dword ptr [rax+15D4h], 0
0x180028ebe  jnz     short loc_180028ED5
0x180028ec0  lea     rdx, aWinreIsNotInst; "WinRE is not installed, nothing to back"...
0x180028ec7  xor     ecx, ecx
0x180028ec9  call    UnattendLogW
0x180028ece  xor     ebx, ebx
0x180028ed0  jmp     loc_180029046
0x180028ed5  lea     r14, [rax+10h]
0x180028ed9  mov     rcx, r14; unsigned __int16 *
0x180028edc  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180028ee1  test    eax, eax
0x180028ee3  jz      short loc_180028F01
0x180028ee5  mov     ebx, 3
0x180028eea  lea     rdx, aWinreDirectory; "WinRe directory(%s) not found"
0x180028ef1  mov     r8, r14
0x180028ef4  mov     ecx, r13d
0x180028ef7  call    UnattendLogW
0x180028efc  jmp     loc_18002902D
0x180028f01  mov     rcx, rsi; unsigned __int16 *
0x180028f04  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180028f09  test    eax, eax
0x180028f0b  jz      short loc_180028F1C
0x180028f0d  mov     ebx, r13d
0x180028f10  lea     rdx, aRecoveryFileNo; "Recovery file not found at %s"
0x180028f17  mov     r8, rsi
0x180028f1a  jmp     short loc_180028EF4
0x180028f1c  lea     rcx, [rbp+57h+lpNewFileName]
0x180028f20  call    winreAllocPath
0x180028f25  mov     rdi, [rbp+57h+lpNewFileName]
0x180028f29  mov     ebx, eax
0x180028f2b  test    eax, eax
0x180028f2d  jz      short loc_180028F41
0x180028f2f  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180028f36  mov     r9d, 52Fh
0x180028f3c  jmp     loc_180028FE7
0x180028f41  mov     r9d, 12Eh; unsigned int
0x180028f47  mov     r8, rdi; unsigned __int16 *
0x180028f4a  mov     rdx, r15; unsigned __int16 *
0x180028f4d  mov     rcx, r14; unsigned __int16 *
0x180028f50  call    ?AppendPath@Utils@@SAKPEBG0PEAGK@Z; Utils::AppendPath(ushort const *,ushort const *,ushort *,ulong)
0x180028f55  mov     ebx, eax
0x180028f57  test    eax, eax
0x180028f59  jz      short loc_180028F6A
0x180028f5b  lea     r8, aFailedToAppend_7; "failed to append path"
0x180028f62  mov     r9d, 533h
0x180028f68  jmp     short loc_180028FE7
0x180028f6a  test    rdi, rdi
0x180028f6d  jz      loc_180029046
0x180028f73  mov     rdx, rdi; unsigned __int16 *
0x180028f76  mov     rcx, rsi; unsigned __int16 *
0x180028f79  call    ?CompareFileNames@Utils@@SAHPEBG0@Z; Utils::CompareFileNames(ushort const *,ushort const *)
0x180028f7e  test    eax, eax
0x180028f80  jnz     loc_18002901B
0x180028f86  mov     rcx, rdi; unsigned __int16 *
0x180028f89  call    ?DeleteReadOnlyFile@Utils@@SAKPEAG@Z; Utils::DeleteReadOnlyFile(ushort *)
0x180028f8e  xor     r9d, r9d; lpData
0x180028f91  mov     dword ptr [rsp+0B0h+dwCopyFlags], 1000h; dwCopyFlags
0x180028f99  xor     r8d, r8d; lpProgressRoutine
0x180028f9c  mov     [rsp+0B0h+pbCancel], 0; pbCancel
0x180028fa5  mov     rdx, rdi; lpNewFileName
0x180028fa8  mov     rcx, rsi; lpExistingFileName
0x180028fab  call    cs:__imp_CopyFileExW
0x180028fb1  test    eax, eax
0x180028fb3  jnz     short loc_180028FCC
0x180028fb5  call    cs:__imp_GetLastError
0x180028fbb  lea     r8, aFailedToCopyFi; "failed to copy file"
0x180028fc2  mov     r9d, 53Eh
0x180028fc8  mov     ebx, eax
0x180028fca  jmp     short loc_180028FE7
0x180028fcc  mov     rcx, rdi; lpFileName
0x180028fcf  call    winreSetACL
0x180028fd4  mov     ebx, eax
0x180028fd6  test    eax, eax
0x180028fd8  jz      short loc_18002901B
0x180028fda  lea     r8, aFailedToSetAcl_1; "failed to set ACL"
0x180028fe1  mov     r9d, 53Fh
0x180028fe7  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180028fee  mov     ecx, r13d
0x180028ff1  lea     rdx, aWinrebackuprec; "winreBackupRecoveryFile %s (0x%x) in fi"...
0x180028ff8  mov     dword ptr [rsp+0B0h+dwCopyFlags], r9d
0x180028ffd  mov     r9d, ebx
0x180029000  mov     [rsp+0B0h+pbCancel], rax
0x180029005  call    UnattendLogW
0x18002900a  test    ebx, ebx
0x18002900c  jz      short loc_18002901B
0x18002900e  test    rdi, rdi
0x180029011  jz      short loc_18002902D
0x180029013  mov     rcx, rdi; unsigned __int16 *
0x180029016  call    ?DeleteReadOnlyFile@Utils@@SAKPEAG@Z; Utils::DeleteReadOnlyFile(ushort *)
0x18002901b  test    rdi, rdi
0x18002901e  jz      short loc_180029029
0x180029020  mov     rcx, rdi; pv
0x180029023  call    cs:__imp_CoTaskMemFree
0x180029029  test    ebx, ebx
0x18002902b  jz      short loc_180029046
0x18002902d  mov     r9, r15
0x180029030  mov     dword ptr [rsp+0B0h+pbCancel], ebx
0x180029034  mov     r8, rsi
0x180029037  lea     rdx, aWinrebackuprec_0; "winreBackupRecoveryFile (%s, %s) failed"...
0x18002903e  mov     ecx, r13d
0x180029041  call    UnattendLogW
0x180029046  lea     rcx, [rbp+57h+var_80]; this
0x18002904a  call    ??1ReAgentReload@@UEAA@XZ; ReAgentReload::~ReAgentReload(void)
0x18002904f  lea     r11, [rsp+0B0h+var_20]
0x180029057  mov     eax, ebx
0x180029059  mov     rbx, [r11+30h]
0x18002905d  mov     rsi, [r11+38h]
0x180029061  mov     rsp, r11
0x180029064  pop     r15
0x180029066  pop     r14
0x180029068  pop     r13
0x18002906a  pop     rdi
0x18002906b  pop     rbp
0x18002906c  retn
```
