# IsFileMicrosoftTrusted(ushort const *,int)

- ea: `0x18001031c`
- end: `0x180010666`
- name: `?IsFileMicrosoftTrusted@@YAHPEBGH@Z`
- size: `842`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000cc50`
- `0x18000d060`

## callees

- `0x180004dc4`
- `0x180004dec`
- `0x18000bf9c`
- `0x18001031c`
- `0x1800135cc`
- `0x1800136c6`
- `0x180013700`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180010635`
- `KERNEL32!SetLastError` at `0x180010635`
- `KERNEL32!GetLastError` at `0x1800103cf`
- `KERNEL32!GetLastError` at `0x1800103cf`
- `KERNEL32!CreateFileW` at `0x1800103be`
- `KERNEL32!CreateFileW` at `0x1800103be`
- `KERNEL32!CloseHandle` at `0x18001062d`
- `KERNEL32!CloseHandle` at `0x18001062d`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180010562`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180010562`
- `WINTRUST!WinVerifyTrust` at `0x18001045a`
- `WINTRUST!WinVerifyTrust` at `0x1800105af`
- `WINTRUST!WinVerifyTrust` at `0x18001045a`
- `WINTRUST!WinVerifyTrust` at `0x1800105af`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18001046e`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18001046e`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800104c0`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800104c0`

## pseudocode

```c
__int64 __fastcall IsFileMicrosoftTrusted(LPCWSTR lpFileName, int a2)
{
  unsigned int v4; // r15d
  DWORD LastError; // eax
  DWORD v6; // edi
  DWORD dwError; // eax
  CRYPT_PROVIDER_DATA *v8; // rax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rsi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v16; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject[2]; // [rsp+60h] [rbp-A0h]
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+70h] [rbp-90h] BYREF
  _DWORD pWVTData[6]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-58h]
  int v21; // [rsp+B0h] [rbp-50h]
  __int128 *v22; // [rsp+B8h] [rbp-48h]
  int v23; // [rsp+C0h] [rbp-40h]
  HANDLE hStateData; // [rsp+C8h] [rbp-38h]
  int v25; // [rsp+D8h] [rbp-28h]
  int v26; // [rsp+DCh] [rbp-24h]
  GUID pgActionID; // [rsp+F0h] [rbp-10h] BYREF

  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  memset_0(pWVTData, 0, 0x58u);
  v4 = 0;
  v16 = 0;
  *(_OWORD *)hObject = 0;
  if ( !lpFileName )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  hObject[0] = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( hObject[0] == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_4fc6193fea0d3010ecfa3fd6d69a525c_Traceguids,
        (_DWORD)lpFileName,
        LastError);
    goto LABEL_37;
  }
  pWVTData[0] = 88;
  LODWORD(v16) = 32;
  v25 = 16;
  *((_QWORD *)&v16 + 1) = lpFileName;
  v20 = 2;
  v23 = 1;
  v26 = 1;
  v21 = 1;
  v22 = &v16;
  dwError = WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, pWVTData);
  v6 = dwError;
  if ( dwError )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v13 = 17;
LABEL_36:
    WPP_SF_d(v12[2], v13, WPP_4fc6193fea0d3010ecfa3fd6d69a525c_Traceguids, dwError);
    goto LABEL_37;
  }
  v8 = WTHelperProvDataFromStateData(hStateData);
  if ( !v8 )
  {
    v6 = 13;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v10 = 11;
    goto LABEL_12;
  }
  ProvSignerFromChain = WTHelperGetProvSignerFromChain(v8, 0, 0, 0);
  if ( !ProvSignerFromChain )
  {
    v6 = 13;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v10 = 12;
    goto LABEL_12;
  }
  pPolicyPara = 0;
  pPolicyPara.cbSize = 16;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  pPolicyStatus.cbSize = 24;
  if ( a2 )
  {
    pPolicyPara.dwFlags = 0x10000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4fc6193fea0d3010ecfa3fd6d69a525c_Traceguids);
  }
  if ( !CertVerifyCertificateChainPolicy((LPCSTR)7, ProvSignerFromChain->pChainContext, &pPolicyPara, &pPolicyStatus) )
  {
    v6 = 13;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_37;
    v10 = 16;
LABEL_12:
    WPP_SF_(v9[2], v10, WPP_4fc6193fea0d3010ecfa3fd6d69a525c_Traceguids);
    goto LABEL_37;
  }
  dwError = pPolicyStatus.dwError;
  if ( pPolicyStatus.dwError )
  {
    v6 = pPolicyStatus.dwError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_37;
    v13 = 15;
    goto LABEL_36;
  }
  v4 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      pPolicyStatus.dwError + 14,
      WPP_4fc6193fea0d3010ecfa3fd6d69a525c_Traceguids);
  v23 = 2;
  WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, pWVTData);
LABEL_37:
  if ( hObject[0] != (HANDLE)-1LL )
    CloseHandle(hObject[0]);
  SetLastError(v6);
  return v4;
}

```

## disassembly

```asm
0x18001031c  mov     [rsp-8+arg_8], rbx
0x180010321  mov     [rsp-8+arg_10], rsi
0x180010326  push    rbp
0x180010327  push    rdi
0x180010328  push    r12
0x18001032a  push    r14
0x18001032c  push    r15
0x18001032e  lea     rbp, [rsp-10h]
0x180010333  sub     rsp, 110h
0x18001033a  mov     rax, cs:__security_cookie
0x180010341  xor     rax, rsp
0x180010344  mov     [rbp+30h+var_30], rax
0x180010348  mov     r14d, edx
0x18001034b  mov     [rbp+30h+pgActionID.Data1], 0AAC56Bh
0x180010352  mov     rsi, rcx
0x180010355  mov     dword ptr [rbp+30h+pgActionID.Data2], 11D0CD44h
0x18001035c  mov     ebx, 58h ; 'X'
0x180010361  mov     dword ptr [rbp+30h+pgActionID.Data4], 0C000C28Ch
0x180010368  mov     r8d, ebx; Size
0x18001036b  mov     dword ptr [rbp+30h+pgActionID.Data4+4], 0EE95C24Fh
0x180010372  xor     edx, edx; Val
0x180010374  lea     rcx, [rbp+30h+pWVTData]; void *
0x180010378  call    memset_0
0x18001037d  xorps   xmm0, xmm0
0x180010380  xor     r15d, r15d
0x180010383  movups  [rsp+130h+var_E0], xmm0
0x180010388  movups  xmmword ptr [rsp+130h+hObject], xmm0
0x18001038d  test    rsi, rsi
0x180010390  jnz     short loc_180010397
0x180010392  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010397  xor     r9d, r9d; lpSecurityAttributes
0x18001039a  mov     [rsp+130h+hTemplateFile], r15; hTemplateFile
0x18001039f  mov     [rsp+130h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800103a7  mov     edx, 80000000h; dwDesiredAccess
0x1800103ac  mov     rcx, rsi; lpFileName
0x1800103af  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x1800103b7  lea     r12d, [r9+1]
0x1800103bb  mov     r8d, r12d; dwShareMode
0x1800103be  call    cs:__imp_CreateFileW
0x1800103c4  mov     [rsp+130h+hObject], rax
0x1800103c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800103cd  jnz     short loc_180010419
0x1800103cf  call    cs:__imp_GetLastError
0x1800103d5  mov     edi, eax
0x1800103d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103de  lea     rbx, WPP_GLOBAL_Control
0x1800103e5  cmp     rcx, rbx
0x1800103e8  jz      loc_180010622
0x1800103ee  test    [rcx+1Ch], r12b
0x1800103f2  jz      loc_180010622
0x1800103f8  mov     rcx, [rcx+10h]
0x1800103fc  lea     edx, [r12+9]
0x180010401  mov     r9, rsi
0x180010404  mov     [rsp+130h+dwCreationDisposition], eax
0x180010408  lea     r8, WPP_4fc6193fea0d3010ecfa3fd6d69a525c_Traceguids
0x18001040f  call    WPP_SF_SD
0x180010414  jmp     loc_180010622
0x180010419  mov     [rbp+30h+pWVTData], ebx
0x18001041c  lea     rax, [rsp+130h+var_E0]
0x180010421  mov     ebx, 10h
0x180010426  mov     dword ptr [rsp+130h+var_E0], 20h ; ' '
0x18001042e  lea     r8, [rbp+30h+pWVTData]; pWVTData
0x180010432  mov     [rbp+30h+var_58], ebx
0x180010435  lea     rdx, [rbp+30h+pgActionID]; pgActionID
0x180010439  mov     qword ptr [rsp+130h+var_E0+8], rsi
0x18001043e  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x180010442  mov     [rbp+30h+var_88], 2
0x18001044a  mov     [rbp+30h+var_70], r12d
0x18001044e  mov     [rbp+30h+var_54], r12d
0x180010452  mov     [rbp+30h+var_80], r12d
0x180010456  mov     [rbp+30h+var_78], rax
0x18001045a  call    cs:__imp_WinVerifyTrust
0x180010460  mov     edi, eax
0x180010462  test    eax, eax
0x180010464  jnz     loc_1800105F1
0x18001046a  mov     rcx, [rbp+30h+hStateData]; hStateData
0x18001046e  call    cs:__imp_WTHelperProvDataFromStateData
0x180010474  test    rax, rax
0x180010477  jnz     short loc_1800104B5
0x180010479  lea     edi, [rbx-3]
0x18001047c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010483  lea     rbx, WPP_GLOBAL_Control
0x18001048a  cmp     rcx, rbx
0x18001048d  jz      loc_180010622
0x180010493  test    [rcx+1Ch], r12b
0x180010497  jz      loc_180010622
0x18001049d  lea     edx, [rax+0Bh]
0x1800104a0  mov     rcx, [rcx+10h]
0x1800104a4  lea     r8, WPP_4fc6193fea0d3010ecfa3fd6d69a525c_Traceguids
0x1800104ab  call    WPP_SF_
0x1800104b0  jmp     loc_180010622
0x1800104b5  xor     r9d, r9d; idxCounterSigner
0x1800104b8  xor     r8d, r8d; fCounterSigner
0x1800104bb  xor     edx, edx; idxSigner
0x1800104bd  mov     rcx, rax; pProvData
0x1800104c0  call    cs:__imp_WTHelperGetProvSignerFromChain
0x1800104c6  mov     rsi, rax
0x1800104c9  test    rax, rax
0x1800104cc  jnz     short loc_1800104F7
0x1800104ce  lea     edi, [rax+0Dh]
0x1800104d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104d8  lea     rbx, WPP_GLOBAL_Control
0x1800104df  cmp     rcx, rbx
0x1800104e2  jz      loc_180010622
0x1800104e8  test    [rcx+1Ch], r12b
0x1800104ec  jz      loc_180010622
0x1800104f2  lea     edx, [rax+0Ch]
0x1800104f5  jmp     short loc_1800104A0
0x1800104f7  xorps   xmm0, xmm0
0x1800104fa  xor     eax, eax
0x1800104fc  mov     [rbp+30h+pPolicyStatus.pvExtraPolicyStatus], rax
0x180010500  movups  xmmword ptr [rsp+130h+pPolicyPara.cbSize], xmm0
0x180010505  mov     [rsp+130h+pPolicyPara.cbSize], ebx
0x180010509  lea     rbx, WPP_GLOBAL_Control
0x180010510  movups  xmmword ptr [rsp+130h+pPolicyStatus.cbSize], xmm0
0x180010515  mov     [rsp+130h+pPolicyStatus.cbSize], 18h
0x18001051d  test    r14d, r14d
0x180010520  jz      short loc_18001054F
0x180010522  mov     [rsp+130h+pPolicyPara.dwFlags], 10000h
0x18001052a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010531  cmp     rcx, rbx
0x180010534  jz      short loc_18001054F
0x180010536  test    byte ptr [rcx+1Ch], 8
0x18001053a  jz      short loc_18001054F
0x18001053c  mov     rcx, [rcx+10h]
0x180010540  lea     edx, [rax+0Dh]
0x180010543  lea     r8, WPP_4fc6193fea0d3010ecfa3fd6d69a525c_Traceguids
0x18001054a  call    WPP_SF_
0x18001054f  mov     rdx, [rsi+38h]; pChainContext
0x180010553  lea     r9, [rsp+130h+pPolicyStatus]; pPolicyStatus
0x180010558  lea     r8, [rsp+130h+pPolicyPara]; pPolicyPara
0x18001055d  mov     ecx, 7; pszPolicyOID
0x180010562  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180010568  test    eax, eax
0x18001056a  jz      short loc_1800105D2
0x18001056c  mov     eax, [rsp+130h+pPolicyStatus.dwError]
0x180010570  test    eax, eax
0x180010572  jnz     short loc_1800105B7
0x180010574  mov     r15d, r12d
0x180010577  mov     rcx, cs:WPP_GLOBAL_Control
0x18001057e  cmp     rcx, rbx
0x180010581  jz      short loc_18001059C
0x180010583  test    byte ptr [rcx+1Ch], 8
0x180010587  jz      short loc_18001059C
0x180010589  mov     rcx, [rcx+10h]
0x18001058d  lea     edx, [rax+0Eh]
0x180010590  lea     r8, WPP_4fc6193fea0d3010ecfa3fd6d69a525c_Traceguids
0x180010597  call    WPP_SF_
0x18001059c  lea     r8, [rbp+30h+pWVTData]; pWVTData
0x1800105a0  mov     [rbp+30h+var_70], 2
0x1800105a7  lea     rdx, [rbp+30h+pgActionID]; pgActionID
0x1800105ab  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x1800105af  call    cs:__imp_WinVerifyTrust
0x1800105b5  jmp     short loc_180010622
0x1800105b7  mov     edi, eax
0x1800105b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105c0  cmp     rcx, rbx
0x1800105c3  jz      short loc_180010622
0x1800105c5  test    byte ptr [rcx+1Ch], 8
0x1800105c9  jz      short loc_180010622
0x1800105cb  mov     edx, 0Fh
0x1800105d0  jmp     short loc_18001060F
0x1800105d2  mov     edi, 0Dh
0x1800105d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105de  cmp     rcx, rbx
0x1800105e1  jz      short loc_180010622
0x1800105e3  test    byte ptr [rcx+1Ch], 8
0x1800105e7  jz      short loc_180010622
0x1800105e9  lea     edx, [rdi+3]
0x1800105ec  jmp     loc_1800104A0
0x1800105f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105f8  lea     rbx, WPP_GLOBAL_Control
0x1800105ff  cmp     rcx, rbx
0x180010602  jz      short loc_180010622
0x180010604  test    [rcx+1Ch], r12b
0x180010608  jz      short loc_180010622
0x18001060a  mov     edx, 11h
0x18001060f  mov     rcx, [rcx+10h]
0x180010613  lea     r8, WPP_4fc6193fea0d3010ecfa3fd6d69a525c_Traceguids
0x18001061a  mov     r9d, eax
0x18001061d  call    WPP_SF_d
0x180010622  mov     rcx, [rsp+130h+hObject]; hObject
0x180010627  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001062b  jz      short loc_180010633
0x18001062d  call    cs:__imp_CloseHandle
0x180010633  mov     ecx, edi; dwErrCode
0x180010635  call    cs:__imp_SetLastError
0x18001063b  mov     eax, r15d
0x18001063e  mov     rcx, [rbp+30h+var_30]
0x180010642  xor     rcx, rsp; StackCookie
0x180010645  call    __security_check_cookie
0x18001064a  lea     r11, [rsp+130h+var_20]
0x180010652  mov     rbx, [r11+38h]
0x180010656  mov     rsi, [r11+40h]
0x18001065a  mov     rsp, r11
0x18001065d  pop     r15
0x18001065f  pop     r14
0x180010661  pop     r12
0x180010663  pop     rdi
0x180010664  pop     rbp
0x180010665  retn
```
