# WinReSetCustomizationInternal

- ea: `0x180026158`
- end: `0x18002645a`
- name: `WinReSetCustomizationInternal`
- size: `770`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x1800260c0`
- `0x180041de4`

## callees

- `0x1800059fc`
- `0x180008b94`
- `0x18000edec`
- `0x1800109d0`
- `0x1800109f8`
- `0x1800121b0`
- `0x18001c56c`
- `0x180026158`
- `0x180028e30`
- `0x180032728`
- `0x18003f0f0`
- `0x18003f618`
- `0x18004d230`
- `0x18004d52c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x180026325`
- `KERNEL32!CopyFileW` at `0x180026325`
- `KERNEL32!GetLastError` at `0x18002632f`
- `KERNEL32!GetLastError` at `0x18002632f`
- `KERNEL32!SetLastError` at `0x180026408`
- `KERNEL32!SetLastError` at `0x180026408`
- `ole32!CoTaskMemFree` at `0x1800263eb`
- `ole32!CoTaskMemFree` at `0x1800263f9`
- `ole32!CoTaskMemFree` at `0x1800263eb`
- `ole32!CoTaskMemFree` at `0x1800263f9`

## string_xrefs

- `0x1800262dc`: `failed to get recovery file path`
- `0x1800262ae`: `ReCustomization.xml`
- `0x1800263b9`: `ReCustomization.xml`
- `0x180026242`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x1800262e3`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18002633d`: `failed to copy file`
- `0x18002635e`: `failed to set ACL`
- `0x180026259`: `failed to init agent customization`
- `0x180026381`: `failed to get config file path from win dir: 0x%x`
- `0x1800263b0`: `AgentConfig.Init failed: 0x%x`

## pseudocode

```c
_BOOL8 __fastcall WinReSetCustomizationInternal(__int64 a1, unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rsi
  DWORD v5; // edi
  DWORD RecoveryFilePath; // eax
  unsigned __int16 *v7; // rbx
  const wchar_t *v8; // r8
  DWORD LastError; // eax
  __int64 v10; // r8
  unsigned int ConfigFilePathFromWinDir; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v15; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v18[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+5Ch] [rbp-A4h]
  __int128 v21; // [rsp+60h] [rbp-A0h]
  __int128 v22; // [rsp+70h] [rbp-90h]
  __int64 v23; // [rsp+80h] [rbp-80h]
  int v24; // [rsp+88h] [rbp-78h]
  int v25; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+98h] [rbp-68h]
  _BYTE v27[604]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v28[612]; // [rsp+2FCh] [rbp+1FCh] BYREF

  v25 = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  memset_0(v28, 0, 0x25Cu);
  v4 = 0;
  v18[1] = 0;
  v18[2] = 0;
  v21 = 0;
  v22 = 0;
  v18[0] = &ReAgentConfig::`vftable';
  v19 = 0;
  v20 = 2;
  v23 = 0;
  v24 = 0;
  lpNewFileName = 0;
  v17 = 0;
  if ( !a2 )
  {
    v5 = 87;
    goto LABEL_27;
  }
  v5 = ReAgentCustomization::Init((ReAgentCustomization *)&v25, a2);
  if ( v5 )
  {
    UnattendLogW(
      2,
      L"WinReSetCustomizationInternal %s (0x%x) in file %S line %d",
      L"failed to init agent customization",
      v5,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      2052);
    goto LABEL_27;
  }
  v5 = ReAgentCustomization::ParseConfigFile((ReAgentCustomization *)&v25, 0);
  if ( v5 )
  {
    if ( !ReAgentError )
      ReAgentError = 25;
    goto LABEL_27;
  }
  PrivateFreePartitionList(0);
  RecoveryFilePath = winreGetRecoveryFilePath(
                       a1,
                       1,
                       0,
                       (wchar_t *)L"ReCustomization.xml",
                       (unsigned __int16 **)&lpNewFileName);
  v7 = (unsigned __int16 *)lpNewFileName;
  v5 = RecoveryFilePath;
  if ( RecoveryFilePath )
  {
    v15 = 2076;
    v8 = L"failed to get recovery file path";
  }
  else
  {
    if ( !Utils::DoesPathExist(lpNewFileName) )
      Utils::DeleteReadOnlyFile(v7);
    if ( CopyFileW(a2, v7, 0) )
    {
      v5 = winreSetACL(v7);
      if ( !v5 )
      {
        ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(a1, 1, v10, &v17);
        if ( ConfigFilePathFromWinDir )
        {
          UnattendLogW(1, L"failed to get config file path from win dir: 0x%x", ConfigFilePathFromWinDir);
          v4 = v17;
        }
        else
        {
          v4 = v17;
          v12 = ReAgentConfig::Init((ReAgentConfig *)v18, v17, 1);
          if ( v12 )
          {
            UnattendLogW(1, L"AgentConfig.Init failed: 0x%x", v12);
          }
          else
          {
            v13 = winreBackupRecoveryFile(v7, (ReAgentXMLParser *)v18, L"ReCustomization.xml");
            if ( v13 )
              UnattendLogW(1, L"failed to back up recovery file: 0x%x", v13);
          }
        }
        goto LABEL_23;
      }
      v15 = 2089;
      v8 = L"failed to set ACL";
    }
    else
    {
      LastError = GetLastError();
      v15 = 2088;
      v8 = L"failed to copy file";
      v5 = LastError;
    }
  }
  UnattendLogW(
    2,
    L"WinReSetCustomizationInternal %s (0x%x) in file %S line %d",
    v8,
    v5,
    "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
    v15);
LABEL_23:
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v4 )
    CoTaskMemFree(v4);
LABEL_27:
  SetLastError(v5);
  v18[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v18);
  ResetConfigXMLParser::~ResetConfigXMLParser((ResetConfigXMLParser *)&v25);
  return v5 == 0;
}

```

## disassembly

```asm
0x180026158  mov     [rsp-8+arg_10], rbx
0x18002615d  mov     [rsp-8+arg_18], rsi
0x180026162  push    rbp
0x180026163  push    rdi
0x180026164  push    r13
0x180026166  push    r14
0x180026168  push    r15
0x18002616a  lea     rbp, [rsp-470h]
0x180026172  sub     rsp, 570h
0x180026179  mov     rax, cs:__security_cookie
0x180026180  xor     rax, rsp
0x180026183  mov     [rbp+490h+var_30], rax
0x18002618a  mov     r14, rdx
0x18002618d  mov     [rbp+490h+var_500], 0
0x180026194  mov     r15, rcx
0x180026197  mov     [rbp+490h+var_4F8], 0
0x18002619f  mov     ebx, 25Ch
0x1800261a4  lea     rcx, [rbp+490h+var_4F0]; void *
0x1800261a8  mov     r8d, ebx; Size
0x1800261ab  xor     edx, edx; Val
0x1800261ad  call    memset_0
0x1800261b2  mov     r8d, ebx; Size
0x1800261b5  lea     rcx, [rbp+490h+var_294]; void *
0x1800261bc  xor     edx, edx; Val
0x1800261be  call    memset_0
0x1800261c3  xor     esi, esi
0x1800261c5  mov     [rsp+590h+var_548], 0
0x1800261ce  mov     [rsp+590h+var_540], 0
0x1800261d7  xorps   xmm0, xmm0
0x1800261da  movdqa  [rsp+590h+var_530], xmm0
0x1800261e0  xorps   xmm1, xmm1
0x1800261e3  movdqa  [rsp+590h+var_520], xmm1
0x1800261e9  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x1800261f0  mov     [rsp+590h+var_550], rax
0x1800261f5  mov     ebx, 2
0x1800261fa  mov     [rsp+590h+var_538], 0
0x180026202  mov     [rsp+590h+var_534], ebx
0x180026206  mov     [rbp+490h+var_510], 0
0x18002620e  mov     [rbp+490h+var_508], 0
0x180026215  mov     [rsp+590h+lpNewFileName], 0
0x18002621e  mov     [rsp+590h+var_558], rsi
0x180026223  test    r14, r14
0x180026226  jnz     short loc_180026230
0x180026228  lea     edi, [rbx+55h]
0x18002622b  jmp     loc_1800263FF
0x180026230  mov     rdx, r14; unsigned __int16 *
0x180026233  lea     rcx, [rbp+490h+var_500]; this
0x180026237  call    ?Init@ReAgentCustomization@@QEAAKPEAG@Z; ReAgentCustomization::Init(ushort *)
0x18002623c  mov     edi, eax
0x18002623e  test    eax, eax
0x180026240  jz      short loc_180026273
0x180026242  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180026249  mov     [rsp+590h+var_568], 804h
0x180026251  mov     r9d, edi
0x180026254  mov     [rsp+590h+var_570], rax
0x180026259  lea     r8, aFailedToInitAg; "failed to init agent customization"
0x180026260  mov     ecx, ebx
0x180026262  lea     rdx, aWinresetcustom_0; "WinReSetCustomizationInternal %s (0x%x)"...
0x180026269  call    UnattendLogW
0x18002626e  jmp     loc_1800263FF
0x180026273  xor     edx, edx; unsigned __int16 *
0x180026275  lea     rcx, [rbp+490h+var_500]; this
0x180026279  call    ?ParseConfigFile@ReAgentCustomization@@QEAAKPEAG@Z; ReAgentCustomization::ParseConfigFile(ushort *)
0x18002627e  mov     edi, eax
0x180026280  test    eax, eax
0x180026282  jz      short loc_18002629F
0x180026284  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, esi; _ReAgentErrorCodes ReAgentError
0x18002628a  jnz     loc_1800263FF
0x180026290  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 19h; _ReAgentErrorCodes ReAgentError
0x18002629a  jmp     loc_1800263FF
0x18002629f  xor     ecx, ecx; pv
0x1800262a1  call    PrivateFreePartitionList
0x1800262a6  xor     r8d, r8d
0x1800262a9  lea     rax, [rsp+590h+lpNewFileName]
0x1800262ae  lea     r9, aRecustomizatio_0; "ReCustomization.xml"
0x1800262b5  mov     [rsp+590h+var_570], rax
0x1800262ba  mov     rcx, r15
0x1800262bd  lea     r13d, [r8+1]
0x1800262c1  mov     edx, r13d
0x1800262c4  call    winreGetRecoveryFilePath
0x1800262c9  mov     rbx, [rsp+590h+lpNewFileName]
0x1800262ce  mov     edi, eax
0x1800262d0  test    eax, eax
0x1800262d2  jz      short loc_180026308
0x1800262d4  mov     [rsp+590h+var_568], 81Ch
0x1800262dc  lea     r8, aFailedToGetRec; "failed to get recovery file path"
0x1800262e3  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800262ea  mov     r9d, edi
0x1800262ed  lea     rdx, aWinresetcustom_0; "WinReSetCustomizationInternal %s (0x%x)"...
0x1800262f4  mov     [rsp+590h+var_570], rax
0x1800262f9  mov     ecx, 2
0x1800262fe  call    UnattendLogW
0x180026303  jmp     loc_1800263E3
0x180026308  mov     rcx, rbx; unsigned __int16 *
0x18002630b  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180026310  test    eax, eax
0x180026312  jnz     short loc_18002631C
0x180026314  mov     rcx, rbx; unsigned __int16 *
0x180026317  call    ?DeleteReadOnlyFile@Utils@@SAKPEAG@Z; Utils::DeleteReadOnlyFile(ushort *)
0x18002631c  xor     r8d, r8d; bFailIfExists
0x18002631f  mov     rdx, rbx; lpNewFileName
0x180026322  mov     rcx, r14; lpExistingFileName
0x180026325  call    cs:__imp_CopyFileW
0x18002632b  test    eax, eax
0x18002632d  jnz     short loc_180026348
0x18002632f  call    cs:__imp_GetLastError
0x180026335  mov     [rsp+590h+var_568], 828h
0x18002633d  lea     r8, aFailedToCopyFi; "failed to copy file"
0x180026344  mov     edi, eax
0x180026346  jmp     short loc_1800262E3
0x180026348  mov     rcx, rbx; lpFileName
0x18002634b  call    winreSetACL
0x180026350  mov     edi, eax
0x180026352  test    eax, eax
0x180026354  jz      short loc_18002636A
0x180026356  mov     [rsp+590h+var_568], 829h
0x18002635e  lea     r8, aFailedToSetAcl_1; "failed to set ACL"
0x180026365  jmp     loc_1800262E3
0x18002636a  lea     r9, [rsp+590h+var_558]
0x18002636f  mov     edx, r13d
0x180026372  mov     rcx, r15
0x180026375  call    winreGetConfigFilePathFromWinDir
0x18002637a  test    eax, eax
0x18002637c  jz      short loc_180026397
0x18002637e  mov     r8d, eax
0x180026381  lea     rdx, aFailedToGetCon_0; "failed to get config file path from win"...
0x180026388  mov     ecx, r13d
0x18002638b  call    UnattendLogW
0x180026390  mov     rsi, [rsp+590h+var_558]
0x180026395  jmp     short loc_1800263E3
0x180026397  mov     rsi, [rsp+590h+var_558]
0x18002639c  lea     rcx, [rsp+590h+var_550]; this
0x1800263a1  mov     rdx, rsi; unsigned __int16 *
0x1800263a4  mov     r8d, r13d; int
0x1800263a7  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x1800263ac  test    eax, eax
0x1800263ae  jz      short loc_1800263B9
0x1800263b0  lea     rdx, aAgentconfigIni; "AgentConfig.Init failed: 0x%x"
0x1800263b7  jmp     short loc_1800263D8
0x1800263b9  lea     r8, aRecustomizatio_0; "ReCustomization.xml"
0x1800263c0  mov     rcx, rbx; unsigned __int16 *
0x1800263c3  lea     rdx, [rsp+590h+var_550]; this
0x1800263c8  call    winreBackupRecoveryFile
0x1800263cd  test    eax, eax
0x1800263cf  jz      short loc_1800263E3
0x1800263d1  lea     rdx, aFailedToBackUp_0; "failed to back up recovery file: 0x%x"
0x1800263d8  mov     r8d, eax
0x1800263db  mov     ecx, r13d
0x1800263de  call    UnattendLogW
0x1800263e3  test    rbx, rbx
0x1800263e6  jz      short loc_1800263F1
0x1800263e8  mov     rcx, rbx; pv
0x1800263eb  call    cs:__imp_CoTaskMemFree
0x1800263f1  test    rsi, rsi
0x1800263f4  jz      short loc_1800263FF
0x1800263f6  mov     rcx, rsi; pv
0x1800263f9  call    cs:__imp_CoTaskMemFree
0x1800263ff  xor     ebx, ebx
0x180026401  mov     ecx, edi; dwErrCode
0x180026403  test    edi, edi
0x180026405  setz    bl
0x180026408  call    cs:__imp_SetLastError
0x18002640e  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180026415  lea     rcx, [rsp+590h+var_550]; this
0x18002641a  mov     [rsp+590h+var_550], rax
0x18002641f  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x180026424  lea     rcx, [rbp+490h+var_500]; this
0x180026428  call    ??1ResetConfigXMLParser@@QEAA@XZ; ResetConfigXMLParser::~ResetConfigXMLParser(void)
0x18002642d  mov     eax, ebx
0x18002642f  mov     rcx, [rbp+490h+var_30]
0x180026436  xor     rcx, rsp; StackCookie
0x180026439  call    __security_check_cookie
0x18002643e  lea     r11, [rsp+590h+var_20]
0x180026446  mov     rbx, [r11+40h]
0x18002644a  mov     rsi, [r11+48h]
0x18002644e  mov     rsp, r11
0x180026451  pop     r15
0x180026453  pop     r14
0x180026455  pop     r13
0x180026457  pop     rdi
0x180026458  pop     rbp
0x180026459  retn
```
