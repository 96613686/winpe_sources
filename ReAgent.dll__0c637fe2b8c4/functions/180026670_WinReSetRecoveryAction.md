# WinReSetRecoveryAction

- ea: `0x180026670`
- end: `0x180026a35`
- name: `WinReSetRecoveryAction`
- size: `965`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180023b50`
- `0x180024800`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180008b94`
- `0x18000f044`
- `0x1800109d0`
- `0x180011344`
- `0x1800121b0`
- `0x180014754`
- `0x1800227ac`
- `0x180026670`
- `0x180028e30`
- `0x180035c90`
- `0x18004d52c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800267ac`
- `KERNEL32!GetLastError` at `0x1800267ac`
- `KERNEL32!SetLastError` at `0x1800269f6`
- `KERNEL32!SetLastError` at `0x1800269f6`
- `ole32!CoTaskMemFree` at `0x1800269ce`
- `ole32!CoTaskMemFree` at `0x1800269ce`

## string_xrefs

- `0x180026872`: `failed to get config file path`
- `0x1800268ef`: `failed to init agent config`
- `0x1800269ab`: `ReAgent.xml`
- `0x1800267ca`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180026868`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x1800268f6`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180026998`: `failed to update agent config`
- `0x1800267ba`: `failed to get winre config`
- `0x1800267fd`: `WinRE not configured`
- `0x18002675a`: `Parameters: Operation: %d, OperationParam: %s, Permanent: %s, ConfigWinDir: %s`

## pseudocode

```c
_BOOL8 __fastcall WinReSetRecoveryAction(
        unsigned int a1,
        unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *LastError)
{
  unsigned __int16 *v8; // rbx
  const unsigned __int16 *v9; // rcx
  const wchar_t *v10; // rax
  const unsigned __int16 *v11; // r9
  __int64 v12; // r8
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  ReAgentXMLParser *v15; // rcx
  const wchar_t *v16; // r8
  unsigned __int16 *v17; // r8
  __int64 v18; // rcx
  __int64 v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+5Ch] [rbp-A4h]
  __int128 v26; // [rsp+60h] [rbp-A0h]
  __int128 v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+88h] [rbp-78h]
  __int64 v30; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v31[934]; // [rsp+98h] [rbp-68h] BYREF

  memset_0(v31, 0, sizeof(v31));
  v23[1] = 0;
  v26 = 0;
  v27 = 0;
  v8 = 0;
  v23[0] = &ReAgentConfig::`vftable';
  v23[2] = 0;
  v24 = 0;
  v25 = 2;
  v28 = 0;
  v29 = 0;
  pv = 0;
  v21 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetRecoveryAction");
  v9 = LastError;
  if ( !LastError )
    v9 = L"NULL";
  v10 = L"TRUE";
  v11 = a2;
  if ( !a3 )
    v10 = L"FALSE";
  if ( !a2 )
    v11 = L"NULL";
  UnattendLogW(0, L"Parameters: Operation: %d, OperationParam: %s, Permanent: %s, ConfigWinDir: %s", a1, v11, v10, v9);
  if ( a1 - 1 > 0x15 )
  {
    LODWORD(LastError) = 87;
  }
  else
  {
    WinReGetGroupPolicies(&v21);
    if ( !LastError )
    {
      v30 = 3744;
      if ( !(unsigned int)WinReGetConfigInternal(0, 0, (__int64)&v30) )
      {
        LODWORD(v20) = 768;
        LastError = (const unsigned __int16 *)GetLastError();
        UnattendLogW(
          2,
          L"WinReSetRecoveryAction %s (0x%x) in file %S line %d",
          L"failed to get winre config",
          LastError,
          "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
          v20);
        goto LABEL_45;
      }
      if ( !v31[0] )
      {
        if ( !ReAgentError )
          ReAgentError = 19;
        v13 = L"WinRE not configured";
        goto LABEL_15;
      }
      if ( a1 == 3 )
      {
        if ( v21 )
        {
LABEL_19:
          LODWORD(LastError) = 1260;
          UnattendLogW(1, L"Setup disabled by GP");
          goto LABEL_45;
        }
        if ( !v31[2] )
        {
          v13 = L"No Setup files are available";
LABEL_15:
          LODWORD(LastError) = 2;
          UnattendLogW(1, v13);
          goto LABEL_45;
        }
      }
      else if ( a1 == 6 && v21 )
      {
        goto LABEL_19;
      }
    }
    LODWORD(LastError) = winreGetConfigFilePathFromWinDir(LastError, 1, v12, &pv);
    if ( (_DWORD)LastError )
    {
      LODWORD(v20) = 819;
LABEL_26:
      UnattendLogW(
        2,
        L"WinReSetRecoveryAction %s (0x%x) in file %S line %d",
        L"failed to get config file path",
        (unsigned int)LastError,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        v20);
      v8 = (unsigned __int16 *)pv;
      goto LABEL_43;
    }
    v8 = (unsigned __int16 *)pv;
    if ( Utils::DoesPathExist((const unsigned __int16 *)pv) )
    {
      LODWORD(LastError) = winreGetConfigFilePathFromWinDir(0, 1, v14, &pv);
      if ( (_DWORD)LastError )
      {
        LODWORD(v20) = 829;
        goto LABEL_26;
      }
      v8 = (unsigned __int16 *)pv;
    }
    LODWORD(LastError) = ReAgentConfig::Init((ReAgentConfig *)v23, v8, 1);
    if ( (_DWORD)LastError )
    {
      LODWORD(v20) = 833;
      v16 = L"failed to init agent config";
LABEL_33:
      UnattendLogW(
        2,
        L"WinReSetRecoveryAction %s (0x%x) in file %S line %d",
        v16,
        (unsigned int)LastError,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        v20);
      goto LABEL_43;
    }
    *(_DWORD *)(v28 + 5612) = a1;
    v17 = (unsigned __int16 *)(v28 + 5616);
    if ( a2 )
    {
      LODWORD(LastError) = ReAgentXMLParser::CopyPathInfo(v15, a2, v17);
      if ( (_DWORD)LastError )
      {
        LODWORD(v20) = 846;
        v16 = L"failed to set operation param";
        goto LABEL_33;
      }
    }
    else
    {
      LODWORD(LastError) = ReAgentXMLParser::CopyPathInfo(v15, (unsigned __int16 *)&qword_180070D18, v17);
      if ( (_DWORD)LastError )
      {
        LODWORD(v20) = 842;
        v16 = L"failed to set emptry string operation param";
        goto LABEL_33;
      }
    }
    *(_DWORD *)(v28 + 6220) = a3;
    LODWORD(LastError) = ReAgentXMLParser::Update((ReAgentXMLParser *)v23);
    if ( (_DWORD)LastError )
    {
      LODWORD(v20) = 855;
      v16 = L"failed to update agent config";
      goto LABEL_33;
    }
    winreSetBCDDisplayMessage(v18, a1);
    winreBackupRecoveryFile(v8, (ReAgentXMLParser *)v23, L"ReAgent.xml");
  }
LABEL_43:
  if ( v8 )
    CoTaskMemFree(v8);
LABEL_45:
  UnattendLogW(
    0,
    L"Exit WinReSetRecoveryAction return value: %d, last error: 0x%x",
    (_DWORD)LastError == 0,
    (unsigned int)LastError);
  UnattendFinalizeLog();
  SetLastError((DWORD)LastError);
  v23[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v23);
  return (_DWORD)LastError == 0;
}

```

## disassembly

```asm
0x180026670  push    rbp
0x180026672  push    rbx
0x180026673  push    rsi
0x180026674  push    rdi
0x180026675  push    r13
0x180026677  push    r14
0x180026679  push    r15
0x18002667b  lea     rbp, [rsp-0E40h]
0x180026683  sub     rsp, 0F40h
0x18002668a  mov     rax, cs:__security_cookie
0x180026691  xor     rax, rsp
0x180026694  mov     [rbp+0E70h+var_40], rax
0x18002669b  mov     r15d, r8d
0x18002669e  mov     r14, rdx
0x1800266a1  mov     esi, ecx
0x1800266a3  xor     edx, edx; Val
0x1800266a5  mov     r8d, 0E98h; Size
0x1800266ab  lea     rcx, [rbp+0E70h+var_ED8]; void *
0x1800266af  mov     rdi, r9
0x1800266b2  call    memset_0
0x1800266b7  xorps   xmm0, xmm0
0x1800266ba  mov     [rsp+0F70h+var_F28], 0
0x1800266c3  xorps   xmm1, xmm1
0x1800266c6  movdqa  [rsp+0F70h+var_F10], xmm0
0x1800266cc  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x1800266d3  movdqa  [rsp+0F70h+var_F00], xmm1
0x1800266d9  xor     ebx, ebx
0x1800266db  mov     [rsp+0F70h+var_F30], rax
0x1800266e0  mov     r13d, 2
0x1800266e6  mov     [rsp+0F70h+var_F20], 0
0x1800266ef  xor     ecx, ecx
0x1800266f1  mov     [rsp+0F70h+var_F18], 0
0x1800266f9  mov     [rsp+0F70h+var_F14], r13d
0x1800266fe  mov     [rbp+0E70h+var_EF0], 0
0x180026706  mov     [rbp+0E70h+var_EE8], 0
0x18002670d  mov     [rsp+0F70h+pv], rbx
0x180026712  mov     [rsp+0F70h+var_F40], ebx
0x180026716  call    UnattendInitializeLogEx2
0x18002671b  lea     rdx, aEnterWinresetr; "Enter WinReSetRecoveryAction"
0x180026722  xor     ecx, ecx
0x180026724  call    UnattendLogW
0x180026729  lea     r8, aNull_0; "NULL"
0x180026730  test    rdi, rdi
0x180026733  lea     rdx, aFalse_0; "FALSE"
0x18002673a  mov     rcx, rdi
0x18002673d  cmovz   rcx, r8
0x180026741  lea     rax, aTrue_0; "TRUE"
0x180026748  mov     [rsp+0F70h+var_F48], rcx
0x18002674d  test    r15d, r15d
0x180026750  mov     r9, r14
0x180026753  cmovz   rax, rdx
0x180026757  test    r14, r14
0x18002675a  lea     rdx, aParametersOper; "Parameters: Operation: %d, OperationPar"...
0x180026761  mov     [rsp+0F70h+var_F50], rax
0x180026766  cmovz   r9, r8
0x18002676a  mov     r8d, esi
0x18002676d  xor     ecx, ecx
0x18002676f  call    UnattendLogW
0x180026774  lea     eax, [rsi-1]
0x180026777  cmp     eax, 15h
0x18002677a  ja      loc_1800269C1
0x180026780  lea     rcx, [rsp+0F70h+var_F40]
0x180026785  call    WinReGetGroupPolicies
0x18002678a  test    rdi, rdi
0x18002678d  jnz     loc_180026848
0x180026793  lea     r8, [rbp+0E70h+var_EE0]
0x180026797  mov     [rbp+0E70h+var_EE0], 0EA0h
0x18002679f  xor     edx, edx
0x1800267a1  xor     ecx, ecx
0x1800267a3  call    WinReGetConfigInternal
0x1800267a8  test    eax, eax
0x1800267aa  jnz     short loc_1800267E6
0x1800267ac  call    cs:__imp_GetLastError
0x1800267b2  mov     dword ptr [rsp+0F70h+var_F48], 300h
0x1800267ba  lea     r8, aFailedToGetWin_1; "failed to get winre config"
0x1800267c1  mov     edi, eax
0x1800267c3  lea     rdx, aWinresetrecove_4; "WinReSetRecoveryAction %s (0x%x) in fil"...
0x1800267ca  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800267d1  mov     r9d, edi
0x1800267d4  mov     ecx, r13d
0x1800267d7  mov     [rsp+0F70h+var_F50], rax
0x1800267dc  call    UnattendLogW
0x1800267e1  jmp     loc_1800269D4
0x1800267e6  cmp     [rbp+0E70h+var_ED8], ebx
0x1800267e9  jnz     short loc_180026816
0x1800267eb  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, ebx; _ReAgentErrorCodes ReAgentError
0x1800267f1  jnz     short loc_1800267FD
0x1800267f3  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 13h; _ReAgentErrorCodes ReAgentError
0x1800267fd  lea     rdx, aWinreNotConfig; "WinRE not configured"
0x180026804  mov     edi, r13d
0x180026807  mov     ecx, 1
0x18002680c  call    UnattendLogW
0x180026811  jmp     loc_1800269D4
0x180026816  cmp     esi, 3
0x180026819  jnz     short loc_18002683D
0x18002681b  cmp     [rsp+0F70h+var_F40], ebx
0x18002681f  jz      short loc_18002682F
0x180026821  mov     edi, 4ECh
0x180026826  lea     rdx, aSetupDisabledB; "Setup disabled by GP"
0x18002682d  jmp     short loc_180026807
0x18002682f  cmp     [rbp+0E70h+var_ED0], ebx
0x180026832  jnz     short loc_180026848
0x180026834  lea     rdx, aNoSetupFilesAr; "No Setup files are available"
0x18002683b  jmp     short loc_180026804
0x18002683d  cmp     esi, 6
0x180026840  jnz     short loc_180026848
0x180026842  cmp     [rsp+0F70h+var_F40], ebx
0x180026846  jnz     short loc_180026821
0x180026848  lea     r9, [rsp+0F70h+pv]
0x18002684d  mov     edx, 1
0x180026852  mov     rcx, rdi
0x180026855  call    winreGetConfigFilePathFromWinDir
0x18002685a  mov     edi, eax
0x18002685c  test    eax, eax
0x18002685e  jz      short loc_180026897
0x180026860  mov     dword ptr [rsp+0F70h+var_F48], 333h
0x180026868  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002686f  mov     r9d, edi
0x180026872  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x180026879  mov     [rsp+0F70h+var_F50], rax
0x18002687e  lea     rdx, aWinresetrecove_4; "WinReSetRecoveryAction %s (0x%x) in fil"...
0x180026885  mov     ecx, r13d
0x180026888  call    UnattendLogW
0x18002688d  mov     rbx, [rsp+0F70h+pv]
0x180026892  jmp     loc_1800269C6
0x180026897  mov     rbx, [rsp+0F70h+pv]
0x18002689c  mov     rcx, rbx; unsigned __int16 *
0x18002689f  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x1800268a4  test    eax, eax
0x1800268a6  jz      short loc_1800268CE
0x1800268a8  lea     r9, [rsp+0F70h+pv]
0x1800268ad  mov     edx, 1
0x1800268b2  xor     ecx, ecx
0x1800268b4  call    winreGetConfigFilePathFromWinDir
0x1800268b9  mov     edi, eax
0x1800268bb  test    eax, eax
0x1800268bd  jz      short loc_1800268C9
0x1800268bf  mov     dword ptr [rsp+0F70h+var_F48], 33Dh
0x1800268c7  jmp     short loc_180026868
0x1800268c9  mov     rbx, [rsp+0F70h+pv]
0x1800268ce  mov     r8d, 1; int
0x1800268d4  lea     rcx, [rsp+0F70h+var_F30]; this
0x1800268d9  mov     rdx, rbx; unsigned __int16 *
0x1800268dc  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x1800268e1  mov     edi, eax
0x1800268e3  test    eax, eax
0x1800268e5  jz      short loc_180026919
0x1800268e7  mov     dword ptr [rsp+0F70h+var_F48], 341h
0x1800268ef  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x1800268f6  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800268fd  mov     r9d, edi
0x180026900  lea     rdx, aWinresetrecove_4; "WinReSetRecoveryAction %s (0x%x) in fil"...
0x180026907  mov     [rsp+0F70h+var_F50], rax
0x18002690c  mov     ecx, r13d
0x18002690f  call    UnattendLogW
0x180026914  jmp     loc_1800269C6
0x180026919  mov     rax, [rbp+0E70h+var_EF0]
0x18002691d  mov     [rax+15ECh], esi
0x180026923  mov     r8, [rbp+0E70h+var_EF0]
0x180026927  add     r8, 15F0h; unsigned __int16 *
0x18002692e  test    r14, r14
0x180026931  jnz     short loc_180026956
0x180026933  lea     rdx, qword_180070D18; unsigned __int16 *
0x18002693a  call    ?CopyPathInfo@ReAgentXMLParser@@IEAAKPEAG0@Z; ReAgentXMLParser::CopyPathInfo(ushort *,ushort *)
0x18002693f  mov     edi, eax
0x180026941  test    eax, eax
0x180026943  jz      short loc_180026975
0x180026945  mov     dword ptr [rsp+0F70h+var_F48], 34Ah
0x18002694d  lea     r8, aFailedToSetEmp; "failed to set emptry string operation p"...
0x180026954  jmp     short loc_1800268F6
0x180026956  mov     rdx, r14; unsigned __int16 *
0x180026959  call    ?CopyPathInfo@ReAgentXMLParser@@IEAAKPEAG0@Z; ReAgentXMLParser::CopyPathInfo(ushort *,ushort *)
0x18002695e  mov     edi, eax
0x180026960  test    eax, eax
0x180026962  jz      short loc_180026975
0x180026964  mov     dword ptr [rsp+0F70h+var_F48], 34Eh
0x18002696c  lea     r8, aFailedToSetOpe; "failed to set operation param"
0x180026973  jmp     short loc_1800268F6
0x180026975  mov     rax, [rbp+0E70h+var_EF0]
0x180026979  lea     rcx, [rsp+0F70h+var_F30]; this
0x18002697e  mov     [rax+184Ch], r15d
0x180026985  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x18002698a  mov     edi, eax
0x18002698c  test    eax, eax
0x18002698e  jz      short loc_1800269A4
0x180026990  mov     dword ptr [rsp+0F70h+var_F48], 357h
0x180026998  lea     r8, aFailedToUpdate_7; "failed to update agent config"
0x18002699f  jmp     loc_1800268F6
0x1800269a4  mov     edx, esi
0x1800269a6  call    winreSetBCDDisplayMessage
0x1800269ab  lea     r8, aReagentXml_1; "ReAgent.xml"
0x1800269b2  mov     rcx, rbx; unsigned __int16 *
0x1800269b5  lea     rdx, [rsp+0F70h+var_F30]; this
0x1800269ba  call    winreBackupRecoveryFile
0x1800269bf  jmp     short loc_1800269C6
0x1800269c1  mov     edi, 57h ; 'W'
0x1800269c6  test    rbx, rbx
0x1800269c9  jz      short loc_1800269D4
0x1800269cb  mov     rcx, rbx; pv
0x1800269ce  call    cs:__imp_CoTaskMemFree
0x1800269d4  xor     ebx, ebx
0x1800269d6  lea     rdx, aExitWinresetre_0; "Exit WinReSetRecoveryAction return valu"...
0x1800269dd  test    edi, edi
0x1800269df  mov     r9d, edi
0x1800269e2  setz    bl
0x1800269e5  xor     ecx, ecx
0x1800269e7  mov     r8d, ebx
0x1800269ea  call    UnattendLogW
0x1800269ef  call    UnattendFinalizeLog
0x1800269f4  mov     ecx, edi; dwErrCode
0x1800269f6  call    cs:__imp_SetLastError
0x1800269fc  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180026a03  lea     rcx, [rsp+0F70h+var_F30]; this
0x180026a08  mov     [rsp+0F70h+var_F30], rax
0x180026a0d  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x180026a12  mov     eax, ebx
0x180026a14  mov     rcx, [rbp+0E70h+var_40]
0x180026a1b  xor     rcx, rsp; StackCookie
0x180026a1e  call    __security_check_cookie
0x180026a23  add     rsp, 0F40h
0x180026a2a  pop     r15
0x180026a2c  pop     r14
0x180026a2e  pop     r13
0x180026a30  pop     rdi
0x180026a31  pop     rsi
0x180026a32  pop     rbx
0x180026a33  pop     rbp
0x180026a34  retn
```
