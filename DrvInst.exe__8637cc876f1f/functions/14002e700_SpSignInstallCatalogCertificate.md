# SpSignInstallCatalogCertificate

- ea: `0x14002e700`
- end: `0x14002e913`
- name: `SpSignInstallCatalogCertificate`
- size: `531`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140014e08`

## callees

- `0x14000a614`
- `0x14000a630`
- `0x14002c954`
- `0x14002ca24`
- `0x14002e700`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x14002e813`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002e8be`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002e813`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002e8be`
- `WINTRUST!WinVerifyTrust` at `0x14002e7cd`
- `WINTRUST!WinVerifyTrust` at `0x14002e7cd`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x14002e81e`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x14002e81e`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x14002e86a`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x14002e86a`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x14002e847`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x14002e847`

## string_xrefs

- `0x14002e803`: `Failed to install driver package certificate (WinVerifyTrust). Error = 0x%08X`
- `0x14002e85c`: `Failed to install driver package certificate (WTHelperGetProvSignerFromChain). Error = 0x%08X`
- `0x14002e833`: `Failed to install driver package certificate (WTHelperProvDataFromStateData). Error = 0x%08X`
- `0x14002e8a5`: `Failed to install driver package certificate. Error = 0x%08X`
- `0x14002e87f`: `Failed to install driver package certificate (WTHelperGetProvCertFromChain). Error = 0x%08X`
- `0x14002e8b1`: `Driver package certificate was successfully installed.`

## pseudocode

```c
__int64 __fastcall SpSignInstallCatalogCertificate(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  const char *v6; // r9
  CRYPT_PROVIDER_DATA *v7; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  unsigned int v10; // eax
  int v12; // [rsp+20h] [rbp-D8h]
  _QWORD v13[2]; // [rsp+38h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+48h] [rbp-B0h]
  _DWORD pWVTData[10]; // [rsp+60h] [rbp-98h] BYREF
  _QWORD *v16; // [rsp+88h] [rbp-70h]
  int v17; // [rsp+90h] [rbp-68h]
  HANDLE hStateData; // [rsp+98h] [rbp-60h]
  int v19; // [rsp+A8h] [rbp-50h]
  GUID pgActionID; // [rsp+C0h] [rbp-38h] BYREF

  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  memset_0(pWVTData, 0, 0x58u);
  pWVTData[0] = 88;
  pWVTData[6] = 2;
  pWVTData[8] = 1;
  v16 = v13;
  v19 = 4224;
  v13[0] = 32;
  v14 = 0;
  v13[1] = a1;
  v17 = 1;
  v4 = WinVerifyTrust(0, &pgActionID, pWVTData);
  if ( v4 || (hStateData ? (v5 = 0) : (v4 = 1287, v5 = 1287), v5) )
  {
    v12 = v4;
    v6 = "Failed to install driver package certificate (WinVerifyTrust). Error = 0x%08X";
LABEL_7:
    DevRtlWriteTextLog(a2, 32, 1, v6, v12);
    goto LABEL_18;
  }
  v7 = WTHelperProvDataFromStateData(hStateData);
  if ( !v7 )
  {
    v4 = 1287;
    v12 = 1287;
    v6 = "Failed to install driver package certificate (WTHelperProvDataFromStateData). Error = 0x%08X";
    goto LABEL_7;
  }
  ProvSignerFromChain = WTHelperGetProvSignerFromChain(v7, 0, 0, 0);
  if ( !ProvSignerFromChain )
  {
    v4 = 1287;
    v12 = 1287;
    v6 = "Failed to install driver package certificate (WTHelperGetProvSignerFromChain). Error = 0x%08X";
    goto LABEL_7;
  }
  ProvCertFromChain = WTHelperGetProvCertFromChain(ProvSignerFromChain, 0);
  if ( !ProvCertFromChain )
  {
    v4 = 1287;
    v12 = 1287;
    v6 = "Failed to install driver package certificate (WTHelperGetProvCertFromChain). Error = 0x%08X";
    goto LABEL_7;
  }
  v10 = SpSignInstallCertificate(ProvCertFromChain->pCert);
  v4 = v10;
  if ( v10 )
    DevRtlWriteTextLog(a2, 32, 1, "Failed to install driver package certificate. Error = 0x%08X", v10);
  else
    DevRtlWriteTextLog(a2, 32, 4, "Driver package certificate was successfully installed.");
LABEL_18:
  if ( hStateData )
    SpSignCloseWVTStateData(hStateData);
  return v4;
}

```

## disassembly

```asm
0x14002e700  mov     r11, rsp
0x14002e703  mov     [r11+8], rbx
0x14002e707  mov     [r11+18h], rsi
0x14002e70b  push    rdi
0x14002e70c  push    r14
0x14002e70e  push    r15
0x14002e710  sub     rsp, 0E0h
0x14002e717  mov     rax, cs:__security_cookie
0x14002e71e  xor     rax, rsp
0x14002e721  mov     [rsp+0F8h+var_28], rax
0x14002e729  mov     rsi, rdx
0x14002e72c  mov     rbx, rcx
0x14002e72f  mov     [rsp+0F8h+var_C8], 0
0x14002e737  mov     dword ptr [r11-38h], 0AAC56Bh
0x14002e73f  mov     dword ptr [r11-34h], 11D0CD44h
0x14002e747  mov     dword ptr [r11-30h], 0C000C28Ch
0x14002e74f  mov     dword ptr [r11-2Ch], 0EE95C24Fh
0x14002e757  mov     edi, 58h ; 'X'
0x14002e75c  mov     r8d, edi; Size
0x14002e75f  xor     edx, edx; Val
0x14002e761  lea     rcx, [rsp+0F8h+pWVTData]; void *
0x14002e766  call    memset_0
0x14002e76b  mov     [rsp+0F8h+pWVTData], edi
0x14002e76f  mov     [rsp+0F8h+var_80], 2
0x14002e777  lea     r15d, [rdi-57h]
0x14002e77b  mov     [rsp+0F8h+var_78], r15d
0x14002e783  lea     rax, [rsp+0F8h+var_C0]
0x14002e788  mov     [rsp+0F8h+var_70], rax
0x14002e790  mov     [rsp+0F8h+var_50], 1080h
0x14002e79b  mov     [rsp+0F8h+var_C0], 20h ; ' '
0x14002e7a4  xorps   xmm0, xmm0
0x14002e7a7  movdqu  [rsp+0F8h+var_B0], xmm0
0x14002e7ad  lea     r14d, [rdi-38h]
0x14002e7b1  mov     [rsp+0F8h+var_B8], rbx
0x14002e7b6  mov     [rsp+0F8h+var_68], r15d
0x14002e7be  lea     r8, [rsp+0F8h+pWVTData]; pWVTData
0x14002e7c3  lea     rdx, [rsp+0F8h+pgActionID]; pgActionID
0x14002e7cb  xor     ecx, ecx; hwnd
0x14002e7cd  call    cs:__imp_WinVerifyTrust
0x14002e7d3  mov     ebx, eax
0x14002e7d5  mov     [rsp+0F8h+var_C8], eax
0x14002e7d9  mov     rcx, [rsp+0F8h+hStateData]; hStateData
0x14002e7e1  mov     edi, 507h
0x14002e7e6  test    eax, eax
0x14002e7e8  jnz     short loc_14002E7FF
0x14002e7ea  test    rcx, rcx
0x14002e7ed  jnz     short loc_14002E7F9
0x14002e7ef  mov     ebx, edi
0x14002e7f1  mov     [rsp+0F8h+var_C8], ebx
0x14002e7f5  mov     eax, edi
0x14002e7f7  jmp     short loc_14002E7FB
0x14002e7f9  xor     eax, eax
0x14002e7fb  test    eax, eax
0x14002e7fd  jz      short loc_14002E81E
0x14002e7ff  mov     [rsp+0F8h+var_D8], ebx
0x14002e803  lea     r9, aFailedToInstal; "Failed to install driver package certif"...
0x14002e80a  mov     edx, r14d
0x14002e80d  mov     rcx, rsi
0x14002e810  mov     r8d, r15d
0x14002e813  call    cs:__imp_DevRtlWriteTextLog
0x14002e819  jmp     loc_14002E8C4
0x14002e81e  call    cs:__imp_WTHelperProvDataFromStateData
0x14002e824  test    rax, rax
0x14002e827  jnz     short loc_14002E83C
0x14002e829  mov     ebx, edi
0x14002e82b  mov     [rsp+0F8h+var_C8], ebx
0x14002e82f  mov     [rsp+0F8h+var_D8], edi
0x14002e833  lea     r9, aFailedToInstal_1; "Failed to install driver package certif"...
0x14002e83a  jmp     short loc_14002E80A
0x14002e83c  xor     r9d, r9d; idxCounterSigner
0x14002e83f  xor     r8d, r8d; fCounterSigner
0x14002e842  xor     edx, edx; idxSigner
0x14002e844  mov     rcx, rax; pProvData
0x14002e847  call    cs:__imp_WTHelperGetProvSignerFromChain
0x14002e84d  test    rax, rax
0x14002e850  jnz     short loc_14002E865
0x14002e852  mov     ebx, edi
0x14002e854  mov     [rsp+0F8h+var_C8], ebx
0x14002e858  mov     [rsp+0F8h+var_D8], edi
0x14002e85c  lea     r9, aFailedToInstal_4; "Failed to install driver package certif"...
0x14002e863  jmp     short loc_14002E80A
0x14002e865  xor     edx, edx; idxCert
0x14002e867  mov     rcx, rax; pSgnr
0x14002e86a  call    cs:__imp_WTHelperGetProvCertFromChain
0x14002e870  test    rax, rax
0x14002e873  jnz     short loc_14002E888
0x14002e875  mov     ebx, edi
0x14002e877  mov     [rsp+0F8h+var_C8], ebx
0x14002e87b  mov     [rsp+0F8h+var_D8], edi
0x14002e87f  lea     r9, aFailedToInstal_5; "Failed to install driver package certif"...
0x14002e886  jmp     short loc_14002E80A
0x14002e888  mov     rcx, [rax+8]; pCertContext
0x14002e88c  call    SpSignInstallCertificate
0x14002e891  mov     ebx, eax
0x14002e893  mov     [rsp+0F8h+var_C8], eax
0x14002e897  mov     edx, r14d
0x14002e89a  mov     rcx, rsi
0x14002e89d  test    eax, eax
0x14002e89f  jz      short loc_14002E8B1
0x14002e8a1  mov     [rsp+0F8h+var_D8], eax
0x14002e8a5  lea     r9, aFailedToInstal_0; "Failed to install driver package certif"...
0x14002e8ac  jmp     loc_14002E810
0x14002e8b1  lea     r9, aDriverPackageC_2; "Driver package certificate was successf"...
0x14002e8b8  mov     r8d, 4
0x14002e8be  call    cs:__imp_DevRtlWriteTextLog
0x14002e8c4  jmp     short loc_14002E8D6
0x14002e8c6  mov     ecx, eax
0x14002e8c8  lea     r8, [rsp+0F8h+var_C8]
0x14002e8cd  call    pSetupExceptionHandler
0x14002e8d2  mov     ebx, [rsp+0F8h+var_C8]
0x14002e8d6  mov     rcx, [rsp+0F8h+hStateData]
0x14002e8de  test    rcx, rcx
0x14002e8e1  jz      short loc_14002E8E8
0x14002e8e3  call    SpSignCloseWVTStateData
0x14002e8e8  mov     eax, ebx
0x14002e8ea  mov     rcx, [rsp+0F8h+var_28]
0x14002e8f2  xor     rcx, rsp; StackCookie
0x14002e8f5  call    __security_check_cookie
0x14002e8fa  lea     r11, [rsp+0F8h+var_18]
0x14002e902  mov     rbx, [r11+20h]
0x14002e906  mov     rsi, [r11+30h]
0x14002e90a  mov     rsp, r11
0x14002e90d  pop     r15
0x14002e90f  pop     r14
0x14002e911  pop     rdi
0x14002e912  retn
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
