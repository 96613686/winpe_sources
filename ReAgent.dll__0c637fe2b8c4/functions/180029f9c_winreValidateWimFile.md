# winreValidateWimFile

- ea: `0x180029f9c`
- end: `0x18002a56a`
- name: `winreValidateWimFile`
- size: `1486`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800282d4`
- `0x180028780`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18001dffc`
- `0x18001f850`
- `0x180029f9c`
- `0x18004f8d0`
- `0x18005abe8`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002a296`
- `msvcrt!_wcsicmp` at `0x18002a296`
- `KERNEL32!GetLastError` at `0x18002a0a4`
- `KERNEL32!GetLastError` at `0x18002a23e`
- `KERNEL32!GetLastError` at `0x18002a2bf`
- `KERNEL32!GetLastError` at `0x18002a434`
- `KERNEL32!GetLastError` at `0x18002a47c`
- `KERNEL32!GetLastError` at `0x18002a0a4`
- `KERNEL32!GetLastError` at `0x18002a23e`
- `KERNEL32!GetLastError` at `0x18002a2bf`
- `KERNEL32!GetLastError` at `0x18002a434`
- `KERNEL32!GetLastError` at `0x18002a47c`
- `KERNEL32!HeapFree` at `0x18002a4c7`
- `KERNEL32!HeapFree` at `0x18002a4c7`
- `KERNEL32!GetProcessHeap` at `0x18002a4b9`
- `KERNEL32!GetProcessHeap` at `0x18002a4b9`
- `KERNEL32!GetTickCount64` at `0x18002a070`
- `KERNEL32!GetTickCount64` at `0x18002a524`
- `KERNEL32!GetTickCount64` at `0x18002a070`
- `KERNEL32!GetTickCount64` at `0x18002a524`
- `KERNEL32!RemoveDirectoryW` at `0x18002a51e`
- `KERNEL32!RemoveDirectoryW` at `0x18002a51e`
- `KERNEL32!DeleteFileW` at `0x18002a511`
- `KERNEL32!DeleteFileW` at `0x18002a511`
- `WIMGAPI!WIMCloseHandle` at `0x18002a42a`
- `WIMGAPI!WIMCloseHandle` at `0x18002a472`
- `WIMGAPI!WIMCloseHandle` at `0x18002a4f2`
- `WIMGAPI!WIMCloseHandle` at `0x18002a502`
- `WIMGAPI!WIMCloseHandle` at `0x18002a42a`
- `WIMGAPI!WIMCloseHandle` at `0x18002a472`
- `WIMGAPI!WIMCloseHandle` at `0x18002a4f2`
- `WIMGAPI!WIMCloseHandle` at `0x18002a502`
- `WIMGAPI!WIMExtractImagePath` at `0x18002a234`
- `WIMGAPI!WIMExtractImagePath` at `0x18002a2b5`
- `WIMGAPI!WIMExtractImagePath` at `0x18002a234`
- `WIMGAPI!WIMExtractImagePath` at `0x18002a2b5`
- `ADVAPI32!RegGetValueW` at `0x18002a207`
- `ADVAPI32!RegGetValueW` at `0x18002a207`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18002a35b`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18002a35b`
- `WINTRUST!WinVerifyTrust` at `0x18002a335`
- `WINTRUST!WinVerifyTrust` at `0x18002a4e4`
- `WINTRUST!WinVerifyTrust` at `0x18002a335`
- `WINTRUST!WinVerifyTrust` at `0x18002a4e4`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18002a37d`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18002a37d`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18002a3e8`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18002a3e8`

## string_xrefs

- `0x18002a0c0`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18002a25c`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18002a2dd`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18002a452`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18002a1c0`: `failed to append path`
- `0x18002a0b2`: `failed to open recovery wim`
- `0x18002a1da`: `SkipWinpeShellCheckDuringValidation`
- `0x18002a22a`: `\windows\system32\winpeshl.ini`
- `0x18002a24c`: `failed to extract winpe shell .ini path`
- `0x18002a2cd`: `failed to extract recenv mount path`

## pseudocode

```c
__int64 __fastcall winreValidateWimFile(unsigned __int16 *a1, _DWORD *a2)
{
  ULONGLONG TickCount64; // rax
  ULONGLONG v5; // r13
  int v6; // r12d
  DWORD LastError; // eax
  const wchar_t *v8; // r8
  __int64 v9; // rbx
  void *v10; // r14
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  const unsigned __int16 *v13; // r8
  LSTATUS ValueW; // eax
  wchar_t *v15; // r15
  const wchar_t *Str; // rax
  unsigned int v17; // eax
  CRYPT_PROVIDER_DATA *v18; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_SGNR *v20; // r13
  struct _CRYPT_PROVIDER_CERT *pasCertChain; // rcx
  DWORD v22; // eax
  const wchar_t *v23; // r8
  HANDLE ProcessHeap; // rax
  ULONGLONG v25; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  int pvData; // [rsp+28h] [rbp-D8h]
  PVOID pvDataa; // [rsp+28h] [rbp-D8h]
  ULONGLONG v30; // [rsp+40h] [rbp-C0h]
  void *v31; // [rsp+48h] [rbp-B8h] BYREF
  void *v32; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD pWVTData[6]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+80h] [rbp-80h]
  GUID *v36; // [rsp+88h] [rbp-78h]
  int v37; // [rsp+90h] [rbp-70h]
  HANDLE hStateData; // [rsp+98h] [rbp-68h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  GUID v40[2]; // [rsp+C0h] [rbp-40h] BYREF
  GUID pgActionID; // [rsp+E0h] [rbp-20h] BYREF
  int v42; // [rsp+F0h] [rbp-10h] BYREF
  DWORD v43[2]; // [rsp+F8h] [rbp-8h] BYREF
  DWORD pcbData; // [rsp+100h] [rbp+0h] BYREF
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+108h] [rbp+8h] BYREF
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+118h] [rbp+18h] BYREF
  WCHAR FileName; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v48[606]; // [rsp+132h] [rbp+32h] BYREF
  WCHAR PathName; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v50[606]; // [rsp+392h] [rbp+292h] BYREF

  PathName = 0;
  memset_0(v50, 0, 0x25Au);
  FileName = 0;
  memset_0(v48, 0, 0x25Au);
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  memset(v40, 0, sizeof(v40));
  memset_0(pWVTData, 0, 0x58u);
  v32 = 0;
  v31 = 0;
  v42 = 0;
  pPolicyPara = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  pcbData = 4;
  TickCount64 = GetTickCount64();
  *a2 = 0;
  v30 = TickCount64;
  v5 = TickCount64;
  if ( !winreOpenRecoveryWim(a1, &v32, &v31, &PathName, pdwType) )
  {
    v6 = 0;
    LastError = GetLastError();
    pvData = 3553;
    v8 = L"failed to open recovery wim";
    LODWORD(v9) = LastError;
LABEL_3:
    UnattendLogW(
      2,
      L"winreValidateWimFile %s (0x%x) in file %S line %d",
      v8,
      (unsigned int)v9,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      pvData);
    v10 = v31;
    goto LABEL_52;
  }
  *(_QWORD *)v43 = 0;
  v6 = 1;
  LODWORD(v9) = StringCchLengthW(&PathName, 0x7FFFFFFFu, (unsigned __int64 *)v43);
  if ( (int)v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 14;
LABEL_15:
      WPP_SF_d(v11[2], v12, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v9);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  if ( !*(_QWORD *)v43 || (v13 = L"%s\\%s", *(_WORD *)&v48[2 * *(_QWORD *)v43 + 604] == 92) )
    v13 = L"%s%s";
  LODWORD(v9) = StringCchPrintfW(&FileName, 0x12Eu, v13, &PathName, L"ExtractedFromWim");
  if ( (int)v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 15;
      goto LABEL_15;
    }
LABEL_16:
    LODWORD(v9) = (unsigned __int16)v9;
    if ( (_WORD)v9 )
    {
      pvData = 3560;
      v8 = L"failed to append path";
      goto LABEL_3;
    }
  }
  v43[0] = 16;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\RecoveryEnvironment",
             L"SkipWinpeShellCheckDuringValidation",
             0x10u,
             v43,
             &v42,
             &pcbData);
  v10 = v31;
  if ( ValueW || (v15 = 0, v42 != 1) )
  {
    if ( !(unsigned int)WIMExtractImagePath(v31, L"\\windows\\system32\\winpeshl.ini", &FileName, 0) )
    {
      LODWORD(pvDataa) = 3575;
      v9 = GetLastError();
      UnattendLogW(
        2,
        L"winreValidateWimFile %s (0x%x) in file %S line %d",
        L"failed to extract winpe shell .ini path",
        v9,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        pvDataa);
      goto LABEL_52;
    }
    Str = (const wchar_t *)IniGetStr(&FileName);
    v15 = (wchar_t *)Str;
    if ( !Str || _wcsicmp(Str, L"%SystemDrive%\\sources\\recovery\\recenv.exe") )
    {
      UnattendLogW(0, L"WIM file not trusted:  RecEnv.exe is not the launch app.");
      goto LABEL_49;
    }
  }
  if ( !(unsigned int)WIMExtractImagePath(v10, L"\\sources\\recovery\\recenv.exe", &FileName, 0) )
  {
    LODWORD(pvDataa) = 3596;
    v9 = GetLastError();
    UnattendLogW(
      2,
      L"winreValidateWimFile %s (0x%x) in file %S line %d",
      L"failed to extract recenv mount path",
      v9,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      pvDataa);
    goto LABEL_50;
  }
  v40[0].Data1 = 32;
  *(_QWORD *)v40[0].Data4 = &FileName;
  pWVTData[0] = 88;
  v36 = v40;
  v34 = 2;
  v37 = 1;
  v39 = 16;
  v35 = 1;
  v17 = WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, pWVTData);
  LODWORD(v9) = v17;
  if ( !v17 )
  {
    v18 = WTHelperProvDataFromStateData(hStateData);
    if ( !v18 )
    {
      UnattendLogW(0, L"Failed to get provider data of of RecEnv.exe");
      goto LABEL_49;
    }
    ProvSignerFromChain = WTHelperGetProvSignerFromChain(v18, 0, 0, 0);
    v20 = ProvSignerFromChain;
    if ( !ProvSignerFromChain )
    {
      UnattendLogW(0, L"Failed to get provider signer of of RecEnv.exe");
LABEL_32:
      v5 = v30;
      goto LABEL_49;
    }
    pasCertChain = ProvSignerFromChain->pasCertChain;
    if ( !pasCertChain || (int)ValidateSignerIsNt5(pasCertChain->pCert) < 0 )
    {
      UnattendLogW(0, L"Failed to get certification chain of of RecEnv.exe");
      goto LABEL_32;
    }
    pPolicyPara.cbSize = 16;
    pPolicyPara.dwFlags = 0x10000;
    pPolicyStatus.cbSize = 24;
    if ( CertVerifyCertificateChainPolicy((LPCSTR)7, v20->pChainContext, &pPolicyPara, &pPolicyStatus) )
    {
      if ( !pPolicyStatus.dwError )
      {
        if ( (unsigned int)WIMCloseHandle(v10) )
        {
          v10 = 0;
          if ( (unsigned int)WIMCloseHandle(v32) )
          {
            v32 = 0;
            *a2 = 1;
            goto LABEL_47;
          }
          v22 = GetLastError();
          v23 = L"failed to close wim handle";
          LODWORD(pvDataa) = 3709;
        }
        else
        {
          v22 = GetLastError();
          v23 = L"failed to close recovery wim handle";
          LODWORD(pvDataa) = 3706;
        }
        LODWORD(v9) = v22;
        UnattendLogW(
          2,
          L"winreValidateWimFile %s (0x%x) in file %S line %d",
          v23,
          v22,
          "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
          pvDataa);
LABEL_47:
        v5 = v30;
        goto LABEL_50;
      }
      UnattendLogW(0, L"Failed to get certification chain of of RecEnv.exe error: 0x%x");
    }
    else
    {
      UnattendLogW(0, L"Failed to get certification policy of of RecEnv.exe");
    }
    *a2 = 0;
    LODWORD(v9) = 0;
    goto LABEL_47;
  }
  UnattendLogW(0, L"Failed to verify trust of RecEnv.exe: 0x%x", v17);
LABEL_49:
  LODWORD(v9) = 0;
  *a2 = 0;
LABEL_50:
  if ( v15 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v15);
  }
LABEL_52:
  if ( hStateData )
  {
    v37 = 2;
    WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, pWVTData);
  }
  if ( v10 )
    WIMCloseHandle(v10);
  if ( v32 )
    WIMCloseHandle(v32);
  if ( v6 )
  {
    DeleteFileW(&FileName);
    RemoveDirectoryW(&PathName);
  }
  v25 = GetTickCount64();
  UnattendLogW(0, L"winreValidateWimFile took %llu ms.", v25 - v5);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029f9c  mov     [rsp-8+arg_10], rbx
0x180029fa1  push    rbp
0x180029fa2  push    rsi
0x180029fa3  push    rdi
0x180029fa4  push    r12
0x180029fa6  push    r13
0x180029fa8  push    r14
0x180029faa  push    r15
0x180029fac  lea     rbp, [rsp-500h]
0x180029fb4  sub     rsp, 600h
0x180029fbb  mov     rax, cs:__security_cookie
0x180029fc2  xor     rax, rsp
0x180029fc5  mov     [rbp+530h+var_40], rax
0x180029fcc  mov     rsi, rdx
0x180029fcf  mov     rbx, rcx
0x180029fd2  xor     eax, eax
0x180029fd4  lea     rcx, [rbp+530h+var_29E]; void *
0x180029fdb  mov     edi, 25Ah
0x180029fe0  mov     [rbp+530h+PathName], ax
0x180029fe7  mov     r8d, edi; Size
0x180029fea  xor     edx, edx; Val
0x180029fec  call    memset_0
0x180029ff1  xor     eax, eax
0x180029ff3  lea     rcx, [rbp+530h+var_4FE]; void *
0x180029ff7  mov     r8d, edi; Size
0x180029ffa  mov     [rbp+530h+FileName], ax
0x180029ffe  xor     edx, edx; Val
0x18002a000  call    memset_0
0x18002a005  xorps   xmm0, xmm0
0x18002a008  mov     [rbp+530h+pgActionID.Data1], 0AAC56Bh
0x18002a00f  xor     edx, edx; Val
0x18002a011  mov     dword ptr [rbp+530h+pgActionID.Data2], 11D0CD44h
0x18002a018  lea     rcx, [rsp+630h+pWVTData]; void *
0x18002a01d  mov     dword ptr [rbp+530h+pgActionID.Data4], 0C000C28Ch
0x18002a024  mov     dword ptr [rbp+530h+pgActionID.Data4+4], 0EE95C24Fh
0x18002a02b  movups  [rbp+530h+var_570], xmm0
0x18002a02f  lea     r8d, [rdx+58h]; Size
0x18002a033  movups  [rbp+530h+var_560], xmm0
0x18002a037  call    memset_0
0x18002a03c  xorps   xmm0, xmm0
0x18002a03f  mov     [rsp+630h+var_5E0], 0
0x18002a048  xorps   xmm1, xmm1
0x18002a04b  mov     [rsp+630h+var_5E8], 0
0x18002a054  xor     eax, eax
0x18002a056  mov     [rbp+530h+var_540], 0
0x18002a05d  movups  xmmword ptr [rbp+530h+pPolicyPara.cbSize], xmm0
0x18002a061  mov     [rbp+530h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18002a065  movups  xmmword ptr [rbp+530h+pPolicyStatus.cbSize], xmm1
0x18002a069  mov     [rbp+530h+var_530], 4
0x18002a070  call    cs:__imp_GetTickCount64
0x18002a076  lea     r9, [rbp+530h+PathName]; unsigned __int16 *
0x18002a07d  mov     dword ptr [rsi], 0
0x18002a083  lea     r8, [rsp+630h+var_5E8]; void **
0x18002a088  mov     [rsp+630h+var_5F0], rax
0x18002a08d  lea     rdx, [rsp+630h+var_5E0]; void **
0x18002a092  mov     rcx, rbx; unsigned __int16 *
0x18002a095  mov     r13, rax
0x18002a098  call    ?winreOpenRecoveryWim@@YAHPEBGPEAPEAX1PEAGK@Z; winreOpenRecoveryWim(ushort const *,void * *,void * *,ushort *,ulong)
0x18002a09d  test    eax, eax
0x18002a09f  jnz     short loc_18002A0E7
0x18002a0a1  xor     r12d, r12d
0x18002a0a4  call    cs:__imp_GetLastError
0x18002a0aa  mov     dword ptr [rsp+630h+pvData], 0DE1h
0x18002a0b2  lea     r8, aFailedToOpenRe_3; "failed to open recovery wim"
0x18002a0b9  mov     ebx, eax
0x18002a0bb  lea     edi, [r12+2]
0x18002a0c0  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002a0c7  mov     r9d, ebx
0x18002a0ca  lea     rdx, aWinrevalidatew_1; "winreValidateWimFile %s (0x%x) in file "...
0x18002a0d1  mov     [rsp+630h+pdwType], rax
0x18002a0d6  mov     ecx, edi
0x18002a0d8  call    UnattendLogW
0x18002a0dd  mov     r14, [rsp+630h+var_5E8]
0x18002a0e2  jmp     loc_18002A4CD
0x18002a0e7  lea     r8, [rbp+530h+var_538]; unsigned __int64 *
0x18002a0eb  mov     qword ptr [rbp+530h+var_538], 0
0x18002a0f3  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002a0f8  lea     rcx, [rbp+530h+PathName]; unsigned __int16 *
0x18002a0ff  mov     r12d, 1
0x18002a105  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002a10a  lea     edi, [r12+1]
0x18002a10f  mov     ebx, eax
0x18002a111  test    eax, eax
0x18002a113  jns     short loc_18002A137
0x18002a115  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a11c  lea     rax, WPP_GLOBAL_Control
0x18002a123  cmp     rcx, rax
0x18002a126  jz      loc_18002A1B1
0x18002a12c  test    [rcx+1Ch], dil
0x18002a130  jz      short loc_18002A1B1
0x18002a132  lea     edx, [rdi+0Ch]
0x18002a135  jmp     short loc_18002A19E
0x18002a137  mov     rax, qword ptr [rbp+530h+var_538]
0x18002a13b  test    rax, rax
0x18002a13e  jz      short loc_18002A152
0x18002a140  cmp     [rbp+rax*2+530h+var_2A2], 5Ch ; '\'
0x18002a149  lea     r8, aSS_1; "%s\\%s"
0x18002a150  jnz     short loc_18002A159
0x18002a152  lea     r8, aSS_2; "%s%s"
0x18002a159  lea     rax, aExtractedfromw; "ExtractedFromWim"
0x18002a160  mov     edx, 12Eh; unsigned __int64
0x18002a165  lea     r9, [rbp+530h+PathName]
0x18002a16c  mov     [rsp+630h+pdwType], rax
0x18002a171  lea     rcx, [rbp+530h+FileName]; unsigned __int16 *
0x18002a175  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a17a  mov     ebx, eax
0x18002a17c  test    eax, eax
0x18002a17e  jns     short loc_18002A1CC
0x18002a180  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a187  lea     rax, WPP_GLOBAL_Control
0x18002a18e  cmp     rcx, rax
0x18002a191  jz      short loc_18002A1B1
0x18002a193  test    [rcx+1Ch], dil
0x18002a197  jz      short loc_18002A1B1
0x18002a199  mov     edx, 0Fh
0x18002a19e  mov     rcx, [rcx+10h]
0x18002a1a2  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18002a1a9  mov     r9d, ebx
0x18002a1ac  call    WPP_SF_d
0x18002a1b1  movzx   ebx, bx
0x18002a1b4  test    ebx, ebx
0x18002a1b6  jz      short loc_18002A1CC
0x18002a1b8  mov     dword ptr [rsp+630h+pvData], 0DE8h
0x18002a1c0  lea     r8, aFailedToAppend_7; "failed to append path"
0x18002a1c7  jmp     loc_18002A0C0
0x18002a1cc  lea     rax, [rbp+530h+var_530]
0x18002a1d0  mov     ebx, 10h
0x18002a1d5  mov     [rsp+630h+pcbData], rax; pcbData
0x18002a1da  lea     r8, aSkipwinpeshell; "SkipWinpeShellCheckDuringValidation"
0x18002a1e1  lea     rax, [rbp+530h+var_540]
0x18002a1e5  mov     [rbp+530h+var_538], ebx
0x18002a1e8  mov     [rsp+630h+pvData], rax; pvData
0x18002a1ed  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x18002a1f4  lea     rax, [rbp+530h+var_538]
0x18002a1f8  mov     r9d, ebx; dwFlags
0x18002a1fb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002a202  mov     [rsp+630h+pdwType], rax; pdwType
0x18002a207  call    cs:__imp_RegGetValueW
0x18002a20d  mov     r14, [rsp+630h+var_5E8]
0x18002a212  test    eax, eax
0x18002a214  jnz     short loc_18002A223
0x18002a216  xor     r15d, r15d
0x18002a219  cmp     [rbp+530h+var_540], r12d
0x18002a21d  jz      loc_18002A2A4
0x18002a223  xor     r9d, r9d
0x18002a226  lea     r8, [rbp+530h+FileName]
0x18002a22a  lea     rdx, aWindowsSystem3_3; "\\windows\\system32\\winpeshl.ini"
0x18002a231  mov     rcx, r14
0x18002a234  call    cs:__imp_WIMExtractImagePath
0x18002a23a  test    eax, eax
0x18002a23c  jnz     short loc_18002A277
0x18002a23e  call    cs:__imp_GetLastError
0x18002a244  mov     dword ptr [rsp+630h+pvData], 0DF7h
0x18002a24c  lea     r8, aFailedToExtrac; "failed to extract winpe shell .ini path"
0x18002a253  mov     ebx, eax
0x18002a255  lea     rdx, aWinrevalidatew_1; "winreValidateWimFile %s (0x%x) in file "...
0x18002a25c  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002a263  mov     r9d, ebx
0x18002a266  mov     ecx, edi
0x18002a268  mov     [rsp+630h+pdwType], rax
0x18002a26d  call    UnattendLogW
0x18002a272  jmp     loc_18002A4CD
0x18002a277  lea     rcx, [rbp+530h+FileName]; lpFileName
0x18002a27b  call    IniGetStr
0x18002a280  mov     r15, rax
0x18002a283  test    rax, rax
0x18002a286  jz      loc_18002A4A2
0x18002a28c  lea     rdx, aSystemdriveSou; "%SystemDrive%\\sources\\recovery\\recen"...
0x18002a293  mov     rcx, rax; String1
0x18002a296  call    cs:__imp__wcsicmp
0x18002a29c  test    eax, eax
0x18002a29e  jnz     loc_18002A4A2
0x18002a2a4  xor     r9d, r9d
0x18002a2a7  lea     r8, [rbp+530h+FileName]
0x18002a2ab  lea     rdx, aSourcesRecover_0; "\\sources\\recovery\\recenv.exe"
0x18002a2b2  mov     rcx, r14
0x18002a2b5  call    cs:__imp_WIMExtractImagePath
0x18002a2bb  test    eax, eax
0x18002a2bd  jnz     short loc_18002A2F8
0x18002a2bf  call    cs:__imp_GetLastError
0x18002a2c5  mov     dword ptr [rsp+630h+pvData], 0E0Ch
0x18002a2cd  lea     r8, aFailedToExtrac_0; "failed to extract recenv mount path"
0x18002a2d4  mov     ebx, eax
0x18002a2d6  lea     rdx, aWinrevalidatew_1; "winreValidateWimFile %s (0x%x) in file "...
0x18002a2dd  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002a2e4  mov     r9d, ebx
0x18002a2e7  mov     ecx, edi
0x18002a2e9  mov     [rsp+630h+pdwType], rax
0x18002a2ee  call    UnattendLogW
0x18002a2f3  jmp     loc_18002A4B4
0x18002a2f8  lea     rax, [rbp+530h+FileName]
0x18002a2fc  mov     dword ptr [rbp+530h+var_570], 20h ; ' '
0x18002a303  mov     qword ptr [rbp+530h+var_570+8], rax
0x18002a307  lea     r8, [rsp+630h+pWVTData]; pWVTData
0x18002a30c  lea     rax, [rbp+530h+var_570]
0x18002a310  mov     [rsp+630h+pWVTData], 58h ; 'X'
0x18002a318  lea     rdx, [rbp+530h+pgActionID]; pgActionID
0x18002a31c  mov     [rbp+530h+var_5A8], rax
0x18002a320  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x18002a324  mov     [rsp+630h+var_5B8], rdi
0x18002a329  mov     [rbp+530h+var_5A0], r12d
0x18002a32d  mov     [rbp+530h+var_588], rbx
0x18002a331  mov     [rbp+530h+var_5B0], r12d
0x18002a335  call    cs:__imp_WinVerifyTrust
0x18002a33b  mov     ebx, eax
0x18002a33d  test    eax, eax
0x18002a33f  jz      short loc_18002A357
0x18002a341  mov     r8d, eax
0x18002a344  lea     rdx, aFailedToVerify; "Failed to verify trust of RecEnv.exe: 0"...
0x18002a34b  xor     ecx, ecx
0x18002a34d  call    UnattendLogW
0x18002a352  jmp     loc_18002A4B0
0x18002a357  mov     rcx, [rbp+530h+hStateData]; hStateData
0x18002a35b  call    cs:__imp_WTHelperProvDataFromStateData
0x18002a361  test    rax, rax
0x18002a364  jnz     short loc_18002A372
0x18002a366  lea     rdx, aFailedToGetPro_0; "Failed to get provider data of of RecEn"...
0x18002a36d  jmp     loc_18002A4A9
0x18002a372  xor     r9d, r9d; idxCounterSigner
0x18002a375  xor     r8d, r8d; fCounterSigner
0x18002a378  xor     edx, edx; idxSigner
0x18002a37a  mov     rcx, rax; pProvData
0x18002a37d  call    cs:__imp_WTHelperGetProvSignerFromChain
0x18002a383  mov     r13, rax
0x18002a386  test    rax, rax
0x18002a389  jnz     short loc_18002A3A3
0x18002a38b  lea     rdx, aFailedToGetPro; "Failed to get provider signer of of Rec"...
0x18002a392  xor     ecx, ecx
0x18002a394  call    UnattendLogW
0x18002a399  mov     r13, [rsp+630h+var_5F0]
0x18002a39e  jmp     loc_18002A4B0
0x18002a3a3  mov     rcx, [rax+10h]
0x18002a3a7  test    rcx, rcx
0x18002a3aa  jnz     short loc_18002A3B5
0x18002a3ac  lea     rdx, aFailedToGetCer_0; "Failed to get certification chain of of"...
0x18002a3b3  jmp     short loc_18002A392
0x18002a3b5  mov     rcx, [rcx+8]; pCertContext
0x18002a3b9  call    ?ValidateSignerIsNt5@@YAJPEBU_CERT_CONTEXT@@@Z; ValidateSignerIsNt5(_CERT_CONTEXT const *)
0x18002a3be  test    eax, eax
0x18002a3c0  js      short loc_18002A3AC
0x18002a3c2  mov     [rbp+530h+pPolicyPara.cbSize], 10h
0x18002a3c9  lea     r9, [rbp+530h+pPolicyStatus]; pPolicyStatus
0x18002a3cd  mov     [rbp+530h+pPolicyPara.dwFlags], 10000h
0x18002a3d4  lea     r8, [rbp+530h+pPolicyPara]; pPolicyPara
0x18002a3d8  mov     [rbp+530h+pPolicyStatus.cbSize], 18h
0x18002a3df  mov     ecx, 7; pszPolicyOID
0x18002a3e4  mov     rdx, [r13+38h]; pChainContext
0x18002a3e8  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18002a3ee  xor     r13d, r13d
0x18002a3f1  test    eax, eax
0x18002a3f3  jnz     short loc_18002A40E
0x18002a3f5  lea     rdx, aFailedToGetCer_1; "Failed to get certification policy of o"...
0x18002a3fc  xor     ecx, ecx
0x18002a3fe  call    UnattendLogW
0x18002a403  mov     [rsi], r13d
0x18002a406  mov     ebx, r13d
0x18002a409  jmp     loc_18002A49B
0x18002a40e  mov     r8d, [rbp+530h+pPolicyStatus.dwError]
0x18002a412  test    r8d, r8d
0x18002a415  jz      short loc_18002A427
0x18002a417  lea     rdx, aFailedToGetCer; "Failed to get certification chain of of"...
0x18002a41e  xor     ecx, ecx
0x18002a420  call    UnattendLogW
0x18002a425  jmp     short loc_18002A403
0x18002a427  mov     rcx, r14
0x18002a42a  call    cs:__imp_WIMCloseHandle
0x18002a430  test    eax, eax
0x18002a432  jnz     short loc_18002A46A
0x18002a434  call    cs:__imp_GetLastError
0x18002a43a  lea     r8, aFailedToCloseR; "failed to close recovery wim handle"
0x18002a441  mov     dword ptr [rsp+630h+pvData], 0E7Ah
0x18002a449  mov     ebx, eax
0x18002a44b  lea     rdx, aWinrevalidatew_1; "winreValidateWimFile %s (0x%x) in file "...
0x18002a452  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002a459  mov     r9d, ebx
0x18002a45c  mov     ecx, edi
0x18002a45e  mov     [rsp+630h+pdwType], rax
0x18002a463  call    UnattendLogW
0x18002a468  jmp     short loc_18002A49B
0x18002a46a  mov     rcx, [rsp+630h+var_5E0]
0x18002a46f  mov     r14, r13
0x18002a472  call    cs:__imp_WIMCloseHandle
0x18002a478  test    eax, eax
0x18002a47a  jnz     short loc_18002A493
0x18002a47c  call    cs:__imp_GetLastError
0x18002a482  lea     r8, aFailedToCloseW; "failed to close wim handle"
0x18002a489  mov     dword ptr [rsp+630h+pvData], 0E7Dh
0x18002a491  jmp     short loc_18002A449
0x18002a493  mov     [rsp+630h+var_5E0], r13
0x18002a498  mov     [rsi], r12d
0x18002a49b  mov     r13, [rsp+630h+var_5F0]
0x18002a4a0  jmp     short loc_18002A4B4
0x18002a4a2  lea     rdx, aWimFileNotTrus; "WIM file not trusted:  RecEnv.exe is no"...
0x18002a4a9  xor     ecx, ecx
0x18002a4ab  call    UnattendLogW
0x18002a4b0  xor     ebx, ebx
0x18002a4b2  mov     [rsi], ebx
0x18002a4b4  test    r15, r15
0x18002a4b7  jz      short loc_18002A4CD
0x18002a4b9  call    cs:__imp_GetProcessHeap
  ... truncated ...
```
