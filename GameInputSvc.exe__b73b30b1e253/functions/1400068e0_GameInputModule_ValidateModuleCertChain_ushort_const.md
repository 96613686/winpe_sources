# GameInputModule::ValidateModuleCertChain(ushort const *)

- ea: `0x1400068e0`
- end: `0x140006a6f`
- name: `?ValidateModuleCertChain@GameInputModule@@CAJPEBG@Z`
- size: `399`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140006750`

## callees

- `0x1400066d0`
- `0x1400068e0`
- `0x140007735`
- `0x140007750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a11`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1400069f5`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1400069f5`
- `WINTRUST!WinVerifyTrust` at `0x140006989`
- `WINTRUST!WinVerifyTrust` at `0x140006a39`
- `WINTRUST!WinVerifyTrust` at `0x140006989`
- `WINTRUST!WinVerifyTrust` at `0x140006a39`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x1400069a4`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x1400069a4`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1400069ba`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1400069ba`

## pseudocode

```c
__int64 __fastcall GameInputModule::ValidateModuleCertChain(const unsigned __int16 *a1)
{
  int dwError; // ebx
  unsigned int v4; // edi
  CRYPT_PROVIDER_DATA *v5; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  const CERT_CHAIN_CONTEXT *pChainContext; // rdx
  int dwError_low; // ebx
  signed int LastError; // eax
  bool v10; // sf
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+20h] [rbp-79h] BYREF
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v13[2]; // [rsp+48h] [rbp-51h] BYREF
  __int128 v14; // [rsp+58h] [rbp-41h]
  _DWORD pWVTData[10]; // [rsp+70h] [rbp-29h] BYREF
  _QWORD *v16; // [rsp+98h] [rbp-1h]
  int v17; // [rsp+A0h] [rbp+7h]
  HANDLE hStateData; // [rsp+A8h] [rbp+Fh]
  int v19; // [rsp+B8h] [rbp+1Fh]
  GUID pgActionID; // [rsp+D0h] [rbp+37h] BYREF

  if ( GameInputModule::IsXbox() )
    return 0;
  v13[1] = a1;
  v13[0] = 32;
  v14 = 0;
  memset_0(pWVTData, 0, 0x58u);
  pWVTData[0] = 88;
  pWVTData[8] = 1;
  v17 = 1;
  pWVTData[6] = 2;
  v16 = v13;
  v19 = 4160;
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  dwError = WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, pWVTData);
  v4 = -2147467259;
  if ( dwError )
  {
    v10 = dwError < 0;
LABEL_17:
    if ( v10 )
      return (unsigned int)dwError;
    return v4;
  }
  dwError = -2147467259;
  v5 = WTHelperProvDataFromStateData(hStateData);
  if ( v5 )
  {
    ProvSignerFromChain = WTHelperGetProvSignerFromChain(v5, 0, 0, 0);
    if ( ProvSignerFromChain )
    {
      pChainContext = ProvSignerFromChain->pChainContext;
      memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
      pPolicyStatus.cbSize = 24;
      pPolicyPara = 0;
      pPolicyPara.cbSize = 16;
      if ( CertVerifyCertificateChainPolicy((LPCSTR)7, pChainContext, &pPolicyPara, &pPolicyStatus) )
      {
        dwError = pPolicyStatus.dwError;
        if ( !pPolicyStatus.dwError )
        {
          dwError = 0;
          goto LABEL_14;
        }
        if ( (int)pPolicyStatus.dwError <= 0 )
          goto LABEL_14;
        dwError_low = LOWORD(pPolicyStatus.dwError);
      }
      else
      {
        LastError = GetLastError();
        dwError = LastError;
        if ( LastError <= 0 )
          goto LABEL_14;
        dwError_low = (unsigned __int16)LastError;
      }
      dwError = dwError_low | 0x80070000;
    }
  }
LABEL_14:
  v17 = 2;
  WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, pWVTData);
  v10 = dwError < 0;
  if ( dwError )
    goto LABEL_17;
  return 0;
}

```

## disassembly

```asm
0x1400068e0  mov     [rsp-8+arg_8], rbx
0x1400068e5  mov     [rsp-8+arg_10], rdi
0x1400068ea  push    rbp
0x1400068eb  lea     rbp, [rsp-57h]
0x1400068f0  sub     rsp, 0F0h
0x1400068f7  mov     rax, cs:__security_cookie
0x1400068fe  xor     rax, rsp
0x140006901  mov     [rbp+57h+var_10], rax
0x140006905  mov     rbx, rcx
0x140006908  call    ?IsXbox@GameInputModule@@CA_NXZ; GameInputModule::IsXbox(void)
0x14000690d  test    al, al
0x14000690f  jz      short loc_140006918
0x140006911  xor     eax, eax
0x140006913  jmp     loc_140006A4E
0x140006918  xorps   xmm0, xmm0
0x14000691b  mov     [rbp+57h+var_A0], rbx
0x14000691f  mov     ebx, 58h ; 'X'
0x140006924  mov     [rbp+57h+var_A8], 20h ; ' '
0x14000692c  mov     r8d, ebx; Size
0x14000692f  lea     rcx, [rbp+57h+pWVTData]; void *
0x140006933  xor     edx, edx; Val
0x140006935  movdqu  [rbp+57h+var_98], xmm0
0x14000693a  call    memset_0
0x14000693f  lea     eax, [rbx-57h]
0x140006942  mov     [rbp+57h+pWVTData], ebx
0x140006945  mov     [rbp+57h+var_60], eax
0x140006948  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x14000694c  mov     [rbp+57h+var_50], eax
0x14000694f  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x140006953  lea     rax, [rbp+57h+var_A8]
0x140006957  mov     [rbp+57h+var_68], 2
0x14000695e  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x140006962  mov     [rbp+57h+var_58], rax
0x140006966  mov     [rbp+57h+var_38], 1040h
0x14000696d  mov     [rbp+57h+pgActionID.Data1], 0AAC56Bh
0x140006974  mov     dword ptr [rbp+57h+pgActionID.Data2], 11D0CD44h
0x14000697b  mov     dword ptr [rbp+57h+pgActionID.Data4], 0C000C28Ch
0x140006982  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0EE95C24Fh
0x140006989  call    cs:__imp_WinVerifyTrust
0x14000698f  mov     ebx, eax
0x140006991  mov     edi, 80004005h
0x140006996  test    eax, eax
0x140006998  jnz     loc_140006A47
0x14000699e  mov     rcx, [rbp+57h+hStateData]; hStateData
0x1400069a2  mov     ebx, edi
0x1400069a4  call    cs:__imp_WTHelperProvDataFromStateData
0x1400069aa  test    rax, rax
0x1400069ad  jz      short loc_140006A26
0x1400069af  xor     r9d, r9d; idxCounterSigner
0x1400069b2  xor     r8d, r8d; fCounterSigner
0x1400069b5  xor     edx, edx; idxSigner
0x1400069b7  mov     rcx, rax; pProvData
0x1400069ba  call    cs:__imp_WTHelperGetProvSignerFromChain
0x1400069c0  test    rax, rax
0x1400069c3  jz      short loc_140006A26
0x1400069c5  mov     rdx, [rax+38h]; pChainContext
0x1400069c9  lea     r9, [rbp+57h+pPolicyStatus]; pPolicyStatus
0x1400069cd  xor     ecx, ecx
0x1400069cf  lea     r8, [rbp+57h+pPolicyPara]; pPolicyPara
0x1400069d3  xorps   xmm0, xmm0
0x1400069d6  mov     [rbp+57h+pPolicyStatus.pvExtraPolicyStatus], rcx
0x1400069da  movups  xmmword ptr [rbp+57h+pPolicyStatus.cbSize], xmm0
0x1400069de  mov     ecx, 7; pszPolicyOID
0x1400069e3  mov     [rbp+57h+pPolicyStatus.cbSize], 18h
0x1400069ea  movups  xmmword ptr [rbp+57h+pPolicyPara.cbSize], xmm0
0x1400069ee  mov     [rbp+57h+pPolicyPara.cbSize], 10h
0x1400069f5  call    cs:__imp_CertVerifyCertificateChainPolicy
0x1400069fb  test    eax, eax
0x1400069fd  jz      short loc_140006A11
0x1400069ff  mov     ebx, [rbp+57h+pPolicyStatus.dwError]
0x140006a02  test    ebx, ebx
0x140006a04  jz      short loc_140006A0D
0x140006a06  jle     short loc_140006A26
0x140006a08  movzx   ebx, bx
0x140006a0b  jmp     short loc_140006A20
0x140006a0d  xor     ebx, ebx
0x140006a0f  jmp     short loc_140006A26
0x140006a11  call    cs:__imp_GetLastError
0x140006a17  mov     ebx, eax
0x140006a19  test    eax, eax
0x140006a1b  jle     short loc_140006A26
0x140006a1d  movzx   ebx, ax
0x140006a20  or      ebx, 80070000h
0x140006a26  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x140006a2a  mov     [rbp+57h+var_50], 2
0x140006a31  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x140006a35  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x140006a39  call    cs:__imp_WinVerifyTrust
0x140006a3f  test    ebx, ebx
0x140006a41  jnz     short loc_140006A49
0x140006a43  xor     edi, edi
0x140006a45  jmp     short loc_140006A4C
0x140006a47  test    ebx, ebx
0x140006a49  cmovs   edi, ebx
0x140006a4c  mov     eax, edi
0x140006a4e  mov     rcx, [rbp+57h+var_10]
0x140006a52  xor     rcx, rsp; StackCookie
0x140006a55  call    __security_check_cookie
0x140006a5a  lea     r11, [rsp+0F0h+var_s0]
0x140006a62  mov     rbx, [r11+18h]
0x140006a66  mov     rdi, [r11+20h]
0x140006a6a  mov     rsp, r11
0x140006a6d  pop     rbp
0x140006a6e  retn
```
