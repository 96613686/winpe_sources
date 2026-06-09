# SpSignVerifyCatalogFile

- ea: `0x14002ccdc`
- end: `0x14002d151`
- name: `SpSignVerifyCatalogFile`
- size: `1141`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002d158`

## callees

- `0x14000a614`
- `0x14000a630`
- `0x14000ac68`
- `0x14000bd0c`
- `0x14000c7a0`
- `0x140013d70`
- `0x14002c954`
- `0x14002ca24`
- `0x14002ccdc`
- `0x14002e3cc`
- `0x14002f3f8`
- `0x14002f4a4`
- `0x14002f62c`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ce97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ce97`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002ceb8`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002d050`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002ceb8`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002d050`
- `DEVRTL!DevRtlWriteTextLogError` at `0x14002d080`
- `DEVRTL!DevRtlWriteTextLogError` at `0x14002d080`
- `WINTRUST!WinVerifyTrust` at `0x14002cf3a`
- `WINTRUST!WinVerifyTrust` at `0x14002cf3a`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x14002cf74`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x14002cf74`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x14002cf9a`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x14002cf9a`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x14002cf8a`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x14002cf8a`
- `CRYPT32!CertGetNameStringW` at `0x14002d01e`
- `CRYPT32!CertGetNameStringW` at `0x14002d01e`
- `CRYPT32!CertFreeCertificateContext` at `0x14002d0f2`
- `CRYPT32!CertFreeCertificateContext` at `0x14002d0f2`

## string_xrefs

- `0x14002d068`: `An Authenticode(tm) signing certificate could not be automatically installed during system setup. (Publisher is '%ws'.)`
- `0x14002d043`: `An Authenticode(tm) signing certificate was automatically installed during system setup. (Publisher is '%ws'.)`

## pseudocode

```c
__int64 __fastcall SpSignVerifyCatalogFile(__int64 a1, const WCHAR *a2, char a3, __int64 a4, HANDLE *a5)
{
  int v9; // r14d
  GUID *v10; // rdx
  unsigned int v11; // ebx
  CRYPT_PROVIDER_DATA *v12; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  CRYPT_PROVIDER_CERT *v15; // rbx
  int v16; // r12d
  unsigned int v17; // eax
  __int64 v18; // [rsp+30h] [rbp-858h]
  DWORD LastError; // [rsp+30h] [rbp-858h]
  __m256i v21; // [rsp+48h] [rbp-840h] BYREF
  _DWORD pWVTData[2]; // [rsp+70h] [rbp-818h] BYREF
  int *v23; // [rsp+78h] [rbp-810h]
  int v24; // [rsp+88h] [rbp-800h]
  int v25; // [rsp+90h] [rbp-7F8h]
  __m256i *v26; // [rsp+98h] [rbp-7F0h]
  int v27; // [rsp+A0h] [rbp-7E8h]
  HANDLE hStateData; // [rsp+A8h] [rbp-7E0h]
  int v29; // [rsp+B8h] [rbp-7D0h]
  int v30; // [rsp+D0h] [rbp-7B8h] BYREF
  _DWORD v31[267]; // [rsp+D4h] [rbp-7B4h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+500h] [rbp-388h]
  __int64 v33; // [rsp+508h] [rbp-380h]
  int v34; // [rsp+510h] [rbp-378h]
  int v35; // [rsp+514h] [rbp-374h]
  int v36; // [rsp+518h] [rbp-370h]
  int v37; // [rsp+51Ch] [rbp-36Ch]
  _BYTE v38[4]; // [rsp+520h] [rbp-368h] BYREF
  int v39; // [rsp+524h] [rbp-364h]
  int v40; // [rsp+528h] [rbp-360h]
  int v41; // [rsp+52Ch] [rbp-35Ch]
  WCHAR pszNameString[264]; // [rsp+640h] [rbp-248h] BYREF

  pWVTData[1] = 0;
  memset_0(pWVTData, 0, 0x54u);
  memset(&v21, 0, 28);
  v31[0] = 0;
  memset_0(&v30, 0, 0x44Cu);
  memset_0(v38, 0, 0x114u);
  if ( a5 )
    *a5 = 0;
  if ( (unsigned int)SpSignSkipValidation() )
    return 0;
  if ( !(unsigned int)pSetupFileExists(a2) )
    return 3758096943LL;
  v9 = a3 & 4;
  HIDWORD(v18) = v9;
  memset_0(&v30, 0, 0x450u);
  memset_0(pWVTData, 0, 0x58u);
  pWVTData[0] = 88;
  v24 = 2;
  v25 = 1;
  v26 = &v21;
  v29 = 4224;
  v21.m256i_i64[0] = 32;
  *(_OWORD *)&v21.m256i_u64[2] = 0;
  v21.m256i_i64[1] = (__int64)a2;
  if ( (a3 & 4) != 0 )
  {
    v27 = 1;
    if ( (a3 & 8) != 0 )
      v29 = 36992;
  }
  else
  {
    memset_0(v31, 0, 0x44Cu);
    v30 = 1104;
    memset_0(v38, 0, 0x114u);
    if ( !(unsigned int)pSetupGetOsVersionInfo(v38) )
    {
      LastError = GetLastError();
      DevRtlWriteTextLog(a1, 32, 1, "Failed to get OS version info. Error = 0x%08X", LastError);
    }
    v31[5] = 2;
    v31[6] = v39;
    v33 = 5;
    v36 = 0;
    v34 = v39;
    v35 = v40;
    v37 = v41;
    v23 = &v30;
  }
  v10 = &SpSignAuthenticodeVerifyGuid;
  if ( (a3 & 4) == 0 )
    v10 = &SpSignDriverVerifyGuid;
  v11 = WinVerifyTrust(0, v10, pWVTData);
  LODWORD(v18) = v11;
  if ( v11 )
  {
    if ( (a3 & 4) != 0 )
      goto LABEL_39;
LABEL_37:
    if ( v11 == 1151 )
      v11 = -536870332;
    goto LABEL_39;
  }
  if ( (a3 & 4) == 0 )
    goto LABEL_37;
  if ( hStateData )
  {
    v12 = WTHelperProvDataFromStateData(hStateData);
    if ( v12 )
    {
      ProvSignerFromChain = WTHelperGetProvSignerFromChain(v12, 0, 0, 0);
      if ( ProvSignerFromChain )
      {
        ProvCertFromChain = WTHelperGetProvCertFromChain(ProvSignerFromChain, 0);
        v15 = ProvCertFromChain;
        if ( ProvCertFromChain )
        {
          if ( (unsigned int)pSetupIsAuthenticodePublisherTrusted(ProvCertFromChain->pCert, a4) )
          {
LABEL_23:
            v11 = -536870335;
            goto LABEL_34;
          }
          if ( !(unsigned int)pSpSignGetGuiSetupInProgress()
            || !(unsigned int)pSpSignGetPnpSetupInProgress()
            || (unsigned int)pSpSignGetIsInteractive()
            || (v16 = 1, !(unsigned int)pSetupIsLocalSystem()) )
          {
            v16 = 0;
          }
          if ( v16 )
          {
            CertGetNameStringW(v15->pCert, 4u, 0, 0, pszNameString, 0x104u);
            v17 = SpSignInstallCertificate(v15->pCert);
            if ( !v17 )
            {
              DevRtlWriteTextLog(
                a1,
                32,
                4,
                "An Authenticode(tm) signing certificate was automatically installed during system setup. (Publisher is '%ws'.)",
                pszNameString);
              goto LABEL_23;
            }
            DevRtlWriteTextLogError(
              a1,
              32,
              2,
              v17,
              "An Authenticode(tm) signing certificate could not be automatically installed during system setup. (Publisher is '%ws'.)",
              pszNameString,
              v18);
          }
          v11 = -536870334;
LABEL_34:
          if ( a5 )
          {
            *a5 = hStateData;
            hStateData = 0;
          }
          goto LABEL_39;
        }
      }
    }
  }
  v11 = 1287;
LABEL_39:
  if ( !v9 && pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v11 + 536870335 > 1 && a5 && *a5 )
  {
    SpSignCloseWVTStateData(*a5);
    *a5 = 0;
  }
  if ( hStateData )
    SpSignCloseWVTStateData(hStateData);
  return v11;
}

```

## disassembly

```asm
0x14002ccdc  push    rbx
0x14002ccde  push    rsi
0x14002ccdf  push    r12
0x14002cce1  push    r13
0x14002cce3  push    r14
0x14002cce5  sub     rsp, 860h
0x14002ccec  mov     rax, cs:__security_cookie
0x14002ccf3  xor     rax, rsp
0x14002ccf6  mov     [rsp+888h+var_38], rax
0x14002ccfe  mov     [rsp+888h+var_850], r9
0x14002cd03  mov     r12d, r8d
0x14002cd06  mov     rbx, rdx
0x14002cd09  mov     r13, rcx
0x14002cd0c  mov     rsi, [rsp+888h+arg_20]
0x14002cd14  mov     [rsp+888h+var_848], rsi
0x14002cd19  xor     eax, eax
0x14002cd1b  mov     [rsp+888h+var_814], eax
0x14002cd1f  xor     edx, edx; Val
0x14002cd21  lea     r8d, [rax+54h]; Size
0x14002cd25  lea     rcx, [rsp+888h+pWVTData]; void *
0x14002cd2a  call    memset_0
0x14002cd2f  xor     eax, eax
0x14002cd31  xorps   xmm0, xmm0
0x14002cd34  movups  [rsp+888h+var_840], xmm0
0x14002cd39  movups  [rsp+888h+var_840+0Ch], xmm0
0x14002cd3e  mov     [rsp+888h+var_7B4], eax
0x14002cd45  xor     edx, edx; Val
0x14002cd47  mov     r8d, 44Ch; Size
0x14002cd4d  lea     rcx, [rsp+888h+var_7B8]; void *
0x14002cd55  call    memset_0
0x14002cd5a  xor     edx, edx; Val
0x14002cd5c  mov     r8d, 114h; Size
0x14002cd62  lea     rcx, [rsp+888h+var_368]; void *
0x14002cd6a  call    memset_0
0x14002cd6f  mov     [rsp+888h+var_858], 0
0x14002cd77  test    rsi, rsi
0x14002cd7a  jz      short loc_14002CD83
0x14002cd7c  mov     qword ptr [rsi], 0
0x14002cd83  call    SpSignSkipValidation
0x14002cd88  test    eax, eax
0x14002cd8a  jz      short loc_14002CD93
0x14002cd8c  xor     eax, eax
0x14002cd8e  jmp     loc_14002D131
0x14002cd93  mov     rcx, rbx; lpFileName
0x14002cd96  call    pSetupFileExists
0x14002cd9b  test    eax, eax
0x14002cd9d  jnz     short loc_14002CDA9
0x14002cd9f  mov     eax, 0E000022Fh
0x14002cda4  jmp     loc_14002D131
0x14002cda9  mov     r14d, r12d
0x14002cdac  and     r14d, 4
0x14002cdb0  mov     [rsp+888h+var_854], r14d
0x14002cdb5  xor     edx, edx; Val
0x14002cdb7  mov     r8d, 450h; Size
0x14002cdbd  lea     rcx, [rsp+888h+var_7B8]; void *
0x14002cdc5  call    memset_0
0x14002cdca  xor     edx, edx; Val
0x14002cdcc  lea     r8d, [rdx+58h]; Size
0x14002cdd0  lea     rcx, [rsp+888h+pWVTData]; void *
0x14002cdd5  call    memset_0
0x14002cdda  mov     [rsp+888h+pWVTData], 58h ; 'X'
0x14002cde2  mov     [rsp+888h+var_800], 2
0x14002cded  mov     [rsp+888h+var_7F8], 1
0x14002cdf8  lea     rax, [rsp+888h+var_840]
0x14002cdfd  mov     [rsp+888h+var_7F0], rax
0x14002ce05  mov     [rsp+888h+var_7D0], 1080h
0x14002ce10  mov     qword ptr [rsp+888h+var_840], 20h ; ' '
0x14002ce19  xorps   xmm0, xmm0
0x14002ce1c  movdqu  [rsp+888h+var_830], xmm0
0x14002ce22  mov     qword ptr [rsp+888h+var_840+8], rbx
0x14002ce27  test    r14d, r14d
0x14002ce2a  jz      short loc_14002CE51
0x14002ce2c  mov     [rsp+888h+var_7E8], 1
0x14002ce37  test    r12b, 8
0x14002ce3b  jz      loc_14002CF1E
0x14002ce41  mov     [rsp+888h+var_7D0], 9080h
0x14002ce4c  jmp     loc_14002CF1E
0x14002ce51  xor     edx, edx; Val
0x14002ce53  mov     r8d, 44Ch; Size
0x14002ce59  lea     rcx, [rsp+888h+var_7B4]; void *
0x14002ce61  call    memset_0
0x14002ce66  mov     [rsp+888h+var_7B8], 450h
0x14002ce71  xor     edx, edx; Val
0x14002ce73  mov     r8d, 114h; Size
0x14002ce79  lea     rcx, [rsp+888h+var_368]; void *
0x14002ce81  call    memset_0
0x14002ce86  lea     rcx, [rsp+888h+var_368]
0x14002ce8e  call    pSetupGetOsVersionInfo
0x14002ce93  test    eax, eax
0x14002ce95  jnz     short loc_14002CEBE
0x14002ce97  call    cs:__imp_GetLastError
0x14002ce9d  mov     [rsp+888h+var_858], eax
0x14002cea1  mov     dword ptr [rsp+888h+pszNameString], eax
0x14002cea5  lea     r9, aFailedToGetOsV; "Failed to get OS version info. Error = "...
0x14002ceac  mov     edx, 20h ; ' '
0x14002ceb1  lea     r8d, [rdx-1Fh]
0x14002ceb5  mov     rcx, r13
0x14002ceb8  call    cs:__imp_DevRtlWriteTextLog
0x14002cebe  mov     [rsp+888h+var_7A0], 2
0x14002cec9  mov     eax, [rsp+888h+var_364]
0x14002ced0  mov     [rsp+888h+var_79C], eax
0x14002ced7  mov     [rsp+888h+var_380], 5
0x14002cee3  mov     [rsp+888h+var_370], 0
0x14002ceee  mov     [rsp+888h+var_378], eax
0x14002cef5  mov     eax, [rsp+888h+var_360]
0x14002cefc  mov     [rsp+888h+var_374], eax
0x14002cf03  mov     eax, [rsp+888h+var_35C]
0x14002cf0a  mov     [rsp+888h+var_36C], eax
0x14002cf11  lea     rax, [rsp+888h+var_7B8]
0x14002cf19  mov     [rsp+888h+var_810], rax
0x14002cf1e  lea     rax, SpSignDriverVerifyGuid
0x14002cf25  lea     rdx, SpSignAuthenticodeVerifyGuid
0x14002cf2c  test    r14d, r14d
0x14002cf2f  cmovz   rdx, rax; pgActionID
0x14002cf33  lea     r8, [rsp+888h+pWVTData]; pWVTData
0x14002cf38  xor     ecx, ecx; hwnd
0x14002cf3a  call    cs:__imp_WinVerifyTrust
0x14002cf40  mov     ebx, eax
0x14002cf42  mov     [rsp+888h+var_858], eax
0x14002cf46  test    eax, eax
0x14002cf48  jnz     loc_14002D0AD
0x14002cf4e  test    r14d, r14d
0x14002cf51  jz      loc_14002D0B2
0x14002cf57  cmp     [rsp+888h+hStateData], 0
0x14002cf60  jnz     short loc_14002CF6C
0x14002cf62  mov     ebx, 507h
0x14002cf67  jmp     loc_14002D0C0
0x14002cf6c  mov     rcx, [rsp+888h+hStateData]; hStateData
0x14002cf74  call    cs:__imp_WTHelperProvDataFromStateData
0x14002cf7a  test    rax, rax
0x14002cf7d  jz      short loc_14002CF62
0x14002cf7f  xor     r9d, r9d; idxCounterSigner
0x14002cf82  xor     r8d, r8d; fCounterSigner
0x14002cf85  xor     edx, edx; idxSigner
0x14002cf87  mov     rcx, rax; pProvData
0x14002cf8a  call    cs:__imp_WTHelperGetProvSignerFromChain
0x14002cf90  test    rax, rax
0x14002cf93  jz      short loc_14002CF62
0x14002cf95  xor     edx, edx; idxCert
0x14002cf97  mov     rcx, rax; pSgnr
0x14002cf9a  call    cs:__imp_WTHelperGetProvCertFromChain
0x14002cfa0  mov     rbx, rax
0x14002cfa3  test    rax, rax
0x14002cfa6  jz      short loc_14002CF62
0x14002cfa8  mov     rdx, [rsp+888h+var_850]
0x14002cfad  mov     rcx, [rax+8]
0x14002cfb1  call    pSetupIsAuthenticodePublisherTrusted
0x14002cfb6  test    eax, eax
0x14002cfb8  jz      short loc_14002CFC4
0x14002cfba  mov     ebx, 0E0000241h
0x14002cfbf  jmp     loc_14002D08B
0x14002cfc4  call    pSpSignGetGuiSetupInProgress
0x14002cfc9  test    eax, eax
0x14002cfcb  jz      short loc_14002CFEC
0x14002cfcd  call    pSpSignGetPnpSetupInProgress
0x14002cfd2  test    eax, eax
0x14002cfd4  jz      short loc_14002CFEC
0x14002cfd6  call    pSpSignGetIsInteractive
0x14002cfdb  test    eax, eax
0x14002cfdd  jnz     short loc_14002CFEC
0x14002cfdf  lea     r12d, [rax+1]
0x14002cfe3  call    pSetupIsLocalSystem
0x14002cfe8  test    eax, eax
0x14002cfea  jnz     short loc_14002CFEF
0x14002cfec  xor     r12d, r12d
0x14002cfef  test    r12d, r12d
0x14002cff2  jz      loc_14002D086
0x14002cff8  mov     [rsp+888h+cchNameString], 104h; cchNameString
0x14002d000  lea     rax, [rsp+888h+var_248]
0x14002d008  mov     [rsp+888h+pszNameString], rax; pszNameString
0x14002d00d  xor     r9d, r9d; pvTypePara
0x14002d010  xor     r8d, r8d; dwFlags
0x14002d013  lea     r12d, [r9+4]
0x14002d017  mov     edx, r12d; dwType
0x14002d01a  mov     rcx, [rbx+8]; pCertContext
0x14002d01e  call    cs:__imp_CertGetNameStringW
0x14002d024  mov     rcx, [rbx+8]; pCertContext
0x14002d028  call    SpSignInstallCertificate
0x14002d02d  lea     edx, [r12+1Ch]
0x14002d032  test    eax, eax
0x14002d034  jnz     short loc_14002D05B
0x14002d036  lea     rax, [rsp+888h+var_248]
0x14002d03e  mov     [rsp+888h+pszNameString], rax
0x14002d043  lea     r9, aAnAuthenticode_0; "An Authenticode(tm) signing certificate"...
0x14002d04a  mov     r8d, r12d
0x14002d04d  mov     rcx, r13
0x14002d050  call    cs:__imp_DevRtlWriteTextLog
0x14002d056  jmp     loc_14002CFBA
0x14002d05b  lea     rcx, [rsp+888h+var_248]
0x14002d063  mov     qword ptr [rsp+888h+cchNameString], rcx
0x14002d068  lea     rcx, aAnAuthenticode; "An Authenticode(tm) signing certificate"...
0x14002d06f  mov     [rsp+888h+pszNameString], rcx
0x14002d074  mov     r9d, eax
0x14002d077  mov     r8d, 2
0x14002d07d  mov     rcx, r13
0x14002d080  call    cs:__imp_DevRtlWriteTextLogError
0x14002d086  mov     ebx, 0E0000242h
0x14002d08b  mov     [rsp+888h+var_858], ebx
0x14002d08f  test    rsi, rsi
0x14002d092  jz      short loc_14002D0C4
0x14002d094  mov     rax, [rsp+888h+hStateData]
0x14002d09c  mov     [rsi], rax
0x14002d09f  mov     [rsp+888h+hStateData], 0
0x14002d0ab  jmp     short loc_14002D0C4
0x14002d0ad  test    r14d, r14d
0x14002d0b0  jnz     short loc_14002D0C4
0x14002d0b2  mov     eax, 0E0000244h
0x14002d0b7  cmp     ebx, 47Fh
0x14002d0bd  cmovz   ebx, eax
0x14002d0c0  mov     [rsp+888h+var_858], ebx
0x14002d0c4  jmp     short loc_14002D0E0
0x14002d0c6  mov     ecx, eax
0x14002d0c8  lea     r8, [rsp+888h+var_858]
0x14002d0cd  call    pSetupExceptionHandler
0x14002d0d2  mov     ebx, [rsp+888h+var_858]
0x14002d0d6  mov     rsi, [rsp+888h+var_848]
0x14002d0db  mov     r14d, [rsp+888h+var_854]
0x14002d0e0  test    r14d, r14d
0x14002d0e3  jnz     short loc_14002D0F8
0x14002d0e5  mov     rcx, [rsp+888h+pCertContext]; pCertContext
0x14002d0ed  test    rcx, rcx
0x14002d0f0  jz      short loc_14002D0F8
0x14002d0f2  call    cs:__imp_CertFreeCertificateContext
0x14002d0f8  lea     eax, [rbx+1FFFFDBFh]
0x14002d0fe  cmp     eax, 1
0x14002d101  jbe     short loc_14002D11D
0x14002d103  test    rsi, rsi
0x14002d106  jz      short loc_14002D11D
0x14002d108  cmp     qword ptr [rsi], 0
0x14002d10c  jz      short loc_14002D11D
0x14002d10e  mov     rcx, [rsi]
0x14002d111  call    SpSignCloseWVTStateData
0x14002d116  mov     qword ptr [rsi], 0
0x14002d11d  mov     rcx, [rsp+888h+hStateData]
0x14002d125  test    rcx, rcx
0x14002d128  jz      short loc_14002D12F
0x14002d12a  call    SpSignCloseWVTStateData
0x14002d12f  mov     eax, ebx
0x14002d131  mov     rcx, [rsp+888h+var_38]
0x14002d139  xor     rcx, rsp; StackCookie
0x14002d13c  call    __security_check_cookie
0x14002d141  add     rsp, 860h
0x14002d148  pop     r14
0x14002d14a  pop     r13
0x14002d14c  pop     r12
0x14002d14e  pop     rsi
0x14002d14f  pop     rbx
0x14002d150  retn
0x1400460d7  push    rbp
0x1400460d9  sub     rsp, 30h
0x1400460dd  mov     rbp, rdx
0x1400460e0  mov     rcx, [rcx]
0x1400460e3  mov     ecx, [rcx]
0x1400460e5  call    pSetupExceptionFilter
0x1400460ea  nop
0x1400460eb  add     rsp, 30h
0x1400460ef  pop     rbp
0x1400460f0  retn
```
