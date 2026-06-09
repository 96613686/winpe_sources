# WinReGetCustomization

- ea: `0x1800224f0`
- end: `0x1800227a3`
- name: `WinReGetCustomization`
- size: `691`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000edec`
- `0x1800109f8`
- `0x18001c56c`
- `0x1800224f0`
- `0x18003f0f0`
- `0x18003f618`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180022774`
- `KERNEL32!SetLastError` at `0x180022774`
- `ole32!CoTaskMemFree` at `0x18002274c`
- `ole32!CoTaskMemFree` at `0x18002274c`

## string_xrefs

- `0x1800225f4`: `failed to get recovery file path`
- `0x1800225c6`: `ReCustomization.xml`
- `0x1800225dd`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18002263b`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x1800226ba`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18002270b`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x1800226d1`: `failed to copy string`
- `0x180022722`: `failed to copy string`
- `0x18002257f`: `Parameters: configWinDir: %s, pwszLocale: %s`
- `0x180022634`: `failed to init agent customization`
- `0x18002267b`: `failed to parse config file`

## pseudocode

```c
_BOOL8 __fastcall WinReGetCustomization(__int64 a1, unsigned __int16 *a2, __int64 a3)
{
  void *v6; // rbx
  const unsigned __int16 *v7; // r9
  const unsigned __int16 *v8; // r8
  DWORD RecoveryFilePath; // edi
  const wchar_t *v10; // r8
  unsigned __int64 v11; // r11
  int v12; // r14d
  int v13; // esi
  int v15; // [rsp+28h] [rbp-D8h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v19[302]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v20[306]; // [rsp+2ACh] [rbp+1ACh] BYREF

  v17 = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  memset_0(v20, 0, 0x25Cu);
  v6 = 0;
  pv = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReGetCustomization");
  v7 = a2;
  if ( !a2 )
    v7 = L"NULL";
  v8 = (const unsigned __int16 *)a1;
  if ( !a1 )
    v8 = L"NULL";
  UnattendLogW(0, L"Parameters: configWinDir: %s, pwszLocale: %s", v8, v7);
  if ( a3 && *(_QWORD *)a3 == 1216 )
  {
    PrivateFreePartitionList(0);
    RecoveryFilePath = winreGetRecoveryFilePath(a1, 1, 1, (wchar_t *)L"ReCustomization.xml", (unsigned __int16 **)&pv);
    if ( RecoveryFilePath )
    {
      UnattendLogW(
        2,
        L"WinReGetCustomization %s (0x%x) in file %S line %d",
        L"failed to get recovery file path",
        RecoveryFilePath,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        1959);
      v6 = pv;
      goto LABEL_19;
    }
    v6 = pv;
    RecoveryFilePath = ReAgentCustomization::Init((ReAgentCustomization *)&v17, (unsigned __int16 *)pv);
    if ( RecoveryFilePath )
    {
      v15 = 1961;
      v10 = L"failed to init agent customization";
LABEL_11:
      UnattendLogW(
        2,
        L"WinReGetCustomization %s (0x%x) in file %S line %d",
        v10,
        RecoveryFilePath,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        v15);
      goto LABEL_19;
    }
    RecoveryFilePath = ReAgentCustomization::ParseConfigFile((ReAgentCustomization *)&v17, a2);
    if ( RecoveryFilePath )
    {
      v15 = 1963;
      v10 = L"failed to parse config file";
      goto LABEL_11;
    }
    memset_0((void *)(a3 + 8), 0, 0x4B8u);
    *(_QWORD *)a3 = 1216;
    v12 = StringCchCopyW((unsigned __int16 *)(a3 + 8), 0x12Eu, v19);
    if ( v12 >= 0 )
    {
      v13 = StringCchCopyW((unsigned __int16 *)(a3 + 612), v11, v20);
      if ( v13 < 0 )
      {
        UnattendLogW(
          2,
          L"WinReGetCustomization %s (0x%x) in file %S line %d",
          L"failed to copy string",
          (unsigned int)v13,
          "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
          1978);
        RecoveryFilePath = (unsigned __int16)v13;
      }
    }
    else
    {
      UnattendLogW(
        2,
        L"WinReGetCustomization %s (0x%x) in file %S line %d",
        L"failed to copy string",
        (unsigned int)v12,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        1974);
      RecoveryFilePath = (unsigned __int16)v12;
    }
  }
  else
  {
    RecoveryFilePath = 87;
  }
LABEL_19:
  if ( v6 )
    CoTaskMemFree(v6);
  UnattendLogW(
    0,
    L"Exit WinReGetCustomization return value: %d, last error: 0x%x",
    RecoveryFilePath == 0,
    RecoveryFilePath);
  UnattendFinalizeLog();
  SetLastError(RecoveryFilePath);
  ResetConfigXMLParser::~ResetConfigXMLParser((ResetConfigXMLParser *)&v17);
  return RecoveryFilePath == 0;
}

```

## disassembly

```asm
0x1800224f0  push    rbp
0x1800224f2  push    rbx
0x1800224f3  push    rsi
0x1800224f4  push    rdi
0x1800224f5  push    r14
0x1800224f7  lea     rbp, [rsp-420h]
0x1800224ff  sub     rsp, 520h
0x180022506  mov     rax, cs:__security_cookie
0x18002250d  xor     rax, rsp
0x180022510  mov     [rbp+440h+var_30], rax
0x180022517  mov     rsi, r8
0x18002251a  mov     [rsp+540h+var_500], 0
0x180022522  mov     r14, rdx
0x180022525  mov     [rsp+540h+var_4F8], 0
0x18002252e  mov     rdi, rcx
0x180022531  mov     ebx, 25Ch
0x180022536  mov     r8d, ebx; Size
0x180022539  lea     rcx, [rsp+540h+var_4F0]; void *
0x18002253e  xor     edx, edx; Val
0x180022540  call    memset_0
0x180022545  mov     r8d, ebx; Size
0x180022548  lea     rcx, [rbp+440h+var_294]; void *
0x18002254f  xor     edx, edx; Val
0x180022551  call    memset_0
0x180022556  xor     ebx, ebx
0x180022558  xor     ecx, ecx
0x18002255a  mov     [rsp+540h+pv], rbx
0x18002255f  call    UnattendInitializeLogEx2
0x180022564  lea     rdx, aEnterWinregetc; "Enter WinReGetCustomization"
0x18002256b  xor     ecx, ecx
0x18002256d  call    UnattendLogW
0x180022572  lea     rax, aNull_0; "NULL"
0x180022579  test    r14, r14
0x18002257c  mov     r9, r14
0x18002257f  lea     rdx, aParametersConf_0; "Parameters: configWinDir: %s, pwszLocal"...
0x180022586  cmovz   r9, rax
0x18002258a  mov     r8, rdi
0x18002258d  test    rdi, rdi
0x180022590  cmovz   r8, rax
0x180022594  xor     ecx, ecx
0x180022596  call    UnattendLogW
0x18002259b  test    rsi, rsi
0x18002259e  jz      loc_18002273F
0x1800225a4  cmp     qword ptr [rsi], 4C0h
0x1800225ab  jnz     loc_18002273F
0x1800225b1  xor     ecx, ecx; pv
0x1800225b3  call    PrivateFreePartitionList
0x1800225b8  lea     edx, [rbx+1]
0x1800225bb  mov     rcx, rdi
0x1800225be  lea     rax, [rsp+540h+pv]
0x1800225c3  mov     r8d, edx
0x1800225c6  lea     r9, aRecustomizatio_0; "ReCustomization.xml"
0x1800225cd  mov     [rsp+540h+var_520], rax
0x1800225d2  call    winreGetRecoveryFilePath
0x1800225d7  mov     edi, eax
0x1800225d9  test    eax, eax
0x1800225db  jz      short loc_180022614
0x1800225dd  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800225e4  mov     [rsp+540h+var_518], 7A7h
0x1800225ec  mov     r9d, edi
0x1800225ef  mov     [rsp+540h+var_520], rax
0x1800225f4  lea     r8, aFailedToGetRec; "failed to get recovery file path"
0x1800225fb  lea     rdx, aWinregetcustom_0; "WinReGetCustomization %s (0x%x) in file"...
0x180022602  lea     ecx, [rbx+2]
0x180022605  call    UnattendLogW
0x18002260a  mov     rbx, [rsp+540h+pv]
0x18002260f  jmp     loc_180022744
0x180022614  mov     rbx, [rsp+540h+pv]
0x180022619  lea     rcx, [rsp+540h+var_500]; this
0x18002261e  mov     rdx, rbx; unsigned __int16 *
0x180022621  call    ?Init@ReAgentCustomization@@QEAAKPEAG@Z; ReAgentCustomization::Init(ushort *)
0x180022626  mov     edi, eax
0x180022628  test    eax, eax
0x18002262a  jz      short loc_180022660
0x18002262c  mov     [rsp+540h+var_518], 7A9h
0x180022634  lea     r8, aFailedToInitAg; "failed to init agent customization"
0x18002263b  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180022642  mov     r9d, edi
0x180022645  lea     rdx, aWinregetcustom_0; "WinReGetCustomization %s (0x%x) in file"...
0x18002264c  mov     [rsp+540h+var_520], rax
0x180022651  mov     ecx, 2
0x180022656  call    UnattendLogW
0x18002265b  jmp     loc_180022744
0x180022660  mov     rdx, r14; unsigned __int16 *
0x180022663  lea     rcx, [rsp+540h+var_500]; this
0x180022668  call    ?ParseConfigFile@ReAgentCustomization@@QEAAKPEAG@Z; ReAgentCustomization::ParseConfigFile(ushort *)
0x18002266d  mov     edi, eax
0x18002266f  test    eax, eax
0x180022671  jz      short loc_180022684
0x180022673  mov     [rsp+540h+var_518], 7ABh
0x18002267b  lea     r8, aFailedToParseC; "failed to parse config file"
0x180022682  jmp     short loc_18002263B
0x180022684  lea     rcx, [rsi+8]; void *
0x180022688  xor     edx, edx; Val
0x18002268a  mov     r8d, 4B8h; Size
0x180022690  call    memset_0
0x180022695  mov     r11d, 12Eh
0x18002269b  mov     qword ptr [rsi], 4C0h
0x1800226a2  mov     edx, r11d; unsigned __int64
0x1800226a5  lea     rcx, [rsi+8]; unsigned __int16 *
0x1800226a9  lea     r8, [rsp+540h+var_4F0]; unsigned __int16 *
0x1800226ae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800226b3  mov     r14d, eax
0x1800226b6  test    eax, eax
0x1800226b8  jns     short loc_1800226EF
0x1800226ba  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800226c1  mov     [rsp+540h+var_518], 7B6h
0x1800226c9  mov     r9d, r14d
0x1800226cc  mov     [rsp+540h+var_520], rax
0x1800226d1  lea     r8, aFailedToCopySt; "failed to copy string"
0x1800226d8  mov     ecx, 2
0x1800226dd  lea     rdx, aWinregetcustom_0; "WinReGetCustomization %s (0x%x) in file"...
0x1800226e4  call    UnattendLogW
0x1800226e9  movzx   edi, r14w
0x1800226ed  jmp     short loc_180022744
0x1800226ef  lea     rcx, [rsi+264h]; unsigned __int16 *
0x1800226f6  mov     rdx, r11; unsigned __int64
0x1800226f9  lea     r8, [rbp+440h+var_294]; unsigned __int16 *
0x180022700  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022705  mov     esi, eax
0x180022707  test    eax, eax
0x180022709  jns     short loc_180022744
0x18002270b  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180022712  mov     [rsp+540h+var_518], 7BAh
0x18002271a  mov     r9d, esi
0x18002271d  mov     [rsp+540h+var_520], rax
0x180022722  lea     r8, aFailedToCopySt; "failed to copy string"
0x180022729  mov     ecx, 2
0x18002272e  lea     rdx, aWinregetcustom_0; "WinReGetCustomization %s (0x%x) in file"...
0x180022735  call    UnattendLogW
0x18002273a  movzx   edi, si
0x18002273d  jmp     short loc_180022744
0x18002273f  mov     edi, 57h ; 'W'
0x180022744  test    rbx, rbx
0x180022747  jz      short loc_180022752
0x180022749  mov     rcx, rbx; pv
0x18002274c  call    cs:__imp_CoTaskMemFree
0x180022752  xor     ebx, ebx
0x180022754  lea     rdx, aExitWinregetcu; "Exit WinReGetCustomization return value"...
0x18002275b  test    edi, edi
0x18002275d  mov     r9d, edi
0x180022760  setz    bl
0x180022763  xor     ecx, ecx
0x180022765  mov     r8d, ebx
0x180022768  call    UnattendLogW
0x18002276d  call    UnattendFinalizeLog
0x180022772  mov     ecx, edi; dwErrCode
0x180022774  call    cs:__imp_SetLastError
0x18002277a  lea     rcx, [rsp+540h+var_500]; this
0x18002277f  call    ??1ResetConfigXMLParser@@QEAA@XZ; ResetConfigXMLParser::~ResetConfigXMLParser(void)
0x180022784  mov     eax, ebx
0x180022786  mov     rcx, [rbp+440h+var_30]
0x18002278d  xor     rcx, rsp; StackCookie
0x180022790  call    __security_check_cookie
0x180022795  add     rsp, 520h
0x18002279c  pop     r14
0x18002279e  pop     rdi
0x18002279f  pop     rsi
0x1800227a0  pop     rbx
0x1800227a1  pop     rbp
0x1800227a2  retn
```
