# CCertManager::UpdateDefaultCertificate(void)

- ea: `0x180003860`
- end: `0x180003c5c`
- name: `?UpdateDefaultCertificate@CCertManager@@AEAAJXZ`
- size: `1020`
- prototype: `__int64 __fastcall(CCertManager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x1800033e0`

## callees

- `0x180003860`
- `0x180003f30`
- `0x180004a50`
- `0x180019b60`
- `0x18001a280`
- `0x18001a8d0`
- `0x1800297e0`
- `0x18002a414`
- `0x18002a838`
- `0x18002a9b8`
- `0x18002ad30`
- `0x18002afd0`
- `0x18002b454`
- `0x18002c4dc`
- `0x18003e520`
- `0x18003e5f8`
- `0x18003f194`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800039be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800039be`

## string_xrefs

- `0x180003917`: `pReg->OpenKey failed: 0x%x in %s`
- `0x18000390d`: `CCertManager::GetHashFromTheRegistry`
- `0x18000395e`: `CCertManager::GetHashFromTheRegistry`
- `0x18000393b`: `TemplateCertificate`
- `0x180003a42`: `TemplateCertificate`
- `0x180003ade`: `TemplateCertificate`
- `0x180003bc0`: `TemplateCertificate`
- `0x180003b78`: `CCertManager::UpdateDefaultCertificate`
- `0x180003bd4`: `CCertManager::UpdateDefaultCertificate`
- `0x1800039f3`: `GetHashFromTheRegistry failed: 0x%x in %s`
- `0x180003a1d`: `m_CertEnrollment.RenewTemplateInfo failed: 0x%x in %s`
- `0x180003a99`: `IsCurrentCertificateNeedsUpdate failed: 0x%x in %s`
- `0x180003b42`: `m_CertEnrollment.EnrollForTemplate failed: 0x%x in %s`
- `0x180003bde`: `PutHashInTheRegistry failed: 0x%x in %s`
- `0x180003968`: `pReg->ReadRegBinary failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCertManager::UpdateDefaultCertificate(const unsigned __int16 **this)
{
  int v2; // r12d
  LSTATUS v3; // eax
  signed int IsCurrentCertificateNeedsUpdate; // ebx
  int v5; // eax
  unsigned int i; // ecx
  int v7; // esi
  CCertManager *v8; // rcx
  unsigned int v9; // r8d
  int v10; // r9d
  CCertManager *v12; // rcx
  unsigned int v13; // edx
  CCertManager *v14; // rcx
  int v15; // eax
  unsigned __int16 v16; // dx
  CCertManager *v17; // rcx
  DWORD pcbData; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-75h] BYREF
  int v20; // [rsp+58h] [rbp-71h] BYREF
  int v21; // [rsp+5Ch] [rbp-6Dh] BYREF
  struct _CRYPTOAPI_BLOB v22; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int8 *v23; // [rsp+70h] [rbp-59h] BYREF
  void **v24; // [rsp+78h] [rbp-51h] BYREF
  void *Block; // [rsp+80h] [rbp-49h]
  int v26; // [rsp+88h] [rbp-41h]
  HKEY hKey[2]; // [rsp+90h] [rbp-39h] BYREF
  unsigned __int8 pvData[24]; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int8 v29[16]; // [rsp+B8h] [rbp-11h] BYREF
  int v30; // [rsp+C8h] [rbp-1h]

  pcbData = 20;
  v22 = 0;
  v20 = 0;
  v2 = 0;
  v21 = 0;
  v24 = &CRegistry::`vftable';
  Block = 0;
  v26 = 0;
  hKey[0] = 0;
  hKey[1] = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v23 = 0;
  v19 = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0,
         0x20019u,
         hKey);
  IsCurrentCertificateNeedsUpdate = v3;
  if ( v3 )
  {
    hKey[0] = 0;
    if ( v3 > 0 )
      IsCurrentCertificateNeedsUpdate = (unsigned __int16)v3 | 0x80070000;
  }
  if ( IsCurrentCertificateNeedsUpdate >= 0 )
  {
    v5 = CRegistry::ReadReg((CRegistry *)&v24, L"TemplateCertificate", &v23, &v19, 3u);
    IsCurrentCertificateNeedsUpdate = v5;
    if ( v5 > 0 )
      IsCurrentCertificateNeedsUpdate = (unsigned __int16)v5 | 0x80070000;
    if ( IsCurrentCertificateNeedsUpdate >= 0 )
    {
      if ( v19 == 20 )
      {
        for ( i = 0; i < 0x14; ++i )
        {
          if ( v23[i] )
          {
            *(_OWORD *)v29 = *(_OWORD *)v23;
            v30 = *((_DWORD *)v23 + 4);
            goto LABEL_18;
          }
        }
        IsCurrentCertificateNeedsUpdate = -2147024894;
      }
      else
      {
        IsCurrentCertificateNeedsUpdate = -2147024883;
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "pReg->ReadRegBinary failed: 0x%x in %s",
        IsCurrentCertificateNeedsUpdate,
        "CCertManager::GetHashFromTheRegistry");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "pReg->OpenKey failed: 0x%x in %s",
      IsCurrentCertificateNeedsUpdate,
      "CCertManager::GetHashFromTheRegistry");
  }
LABEL_18:
  v24 = &CRegistry::`vftable';
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
  }
  if ( Block )
    operator delete(Block);
  if ( IsCurrentCertificateNeedsUpdate < 0 )
  {
    if ( IsCurrentCertificateNeedsUpdate != -2147024894 && IsCurrentCertificateNeedsUpdate != -2147024883 )
    {
      _DbgPrintMessage(
        8,
        "GetHashFromTheRegistry failed: 0x%x in %s",
        (unsigned int)IsCurrentCertificateNeedsUpdate,
        "CCertManager::UpdateDefaultCertificate");
LABEL_48:
      v13 = -1073740760;
      goto LABEL_54;
    }
    v7 = 0;
  }
  else
  {
    v7 = 1;
  }
  IsCurrentCertificateNeedsUpdate = CCertEnrollment::RenewTemplateInfo((CCertEnrollment *)(this + 209));
  if ( IsCurrentCertificateNeedsUpdate < 0 )
  {
    _DbgPrintMessage(
      8,
      "m_CertEnrollment.RenewTemplateInfo failed: 0x%x in %s",
      (unsigned int)IsCurrentCertificateNeedsUpdate,
      "CCertManager::UpdateDefaultCertificate");
    goto LABEL_48;
  }
  if ( *((_DWORD *)this + 426) )
  {
    if ( v7 )
    {
      IsCurrentCertificateNeedsUpdate = CCertManager::IsCurrentCertificateNeedsUpdate(
                                          (CCertManager *)this,
                                          v29,
                                          v9,
                                          0,
                                          1,
                                          0,
                                          0,
                                          1u,
                                          &v20,
                                          &v21);
      if ( IsCurrentCertificateNeedsUpdate < 0 )
      {
        _DbgPrintMessage(
          8,
          "IsCurrentCertificateNeedsUpdate failed: 0x%x in %s",
          (unsigned int)IsCurrentCertificateNeedsUpdate,
          "CCertManager::UpdateDefaultCertificate");
        goto LABEL_48;
      }
      if ( (unsigned int)CCertManager::MustFixCertificatePermissions((CCertManager *)this) )
      {
        v22.cbData = 20;
        v22.pbData = v29;
        CCertManager::FixCertificatePermissions(v12, &v22);
      }
      if ( !v20 )
        return (unsigned int)IsCurrentCertificateNeedsUpdate;
      CCertManager::PutHashInTheRegistry(v12, 0, L"TemplateCertificate", 0, 0);
    }
    IsCurrentCertificateNeedsUpdate = TsCryptFindTemplateCertificate(
                                        (int)this[210],
                                        (int)this[212],
                                        (int)this[202],
                                        v10,
                                        pvData,
                                        &pcbData);
    if ( IsCurrentCertificateNeedsUpdate == -2147024894 )
    {
      pcbData = 20;
      IsCurrentCertificateNeedsUpdate = CCertEnrollment::EnrollForTemplate(
                                          (CCertEnrollment *)(this + 209),
                                          pvData,
                                          &pcbData);
      if ( IsCurrentCertificateNeedsUpdate < 0 )
      {
        _DbgPrintMessage(
          8,
          "m_CertEnrollment.EnrollForTemplate failed: 0x%x in %s",
          (unsigned int)IsCurrentCertificateNeedsUpdate,
          "CCertManager::UpdateDefaultCertificate");
        goto LABEL_48;
      }
      v2 = 1;
      IsCurrentCertificateNeedsUpdate = CCertManager::ValidateDefaultCertAndLogProblems(
                                          (CCertManager *)this,
                                          pvData,
                                          pcbData);
      if ( IsCurrentCertificateNeedsUpdate < 0 )
      {
        _DbgPrintMessage(
          8,
          "ValidateDefaultCertAndLogProblems failed: 0x%x in %s",
          (unsigned int)IsCurrentCertificateNeedsUpdate,
          "CCertManager::UpdateDefaultCertificate");
        goto LABEL_48;
      }
    }
    else if ( IsCurrentCertificateNeedsUpdate < 0 )
    {
      _DbgPrintMessage(
        8,
        "FindCertInStore failed: 0x%x in %s",
        (unsigned int)IsCurrentCertificateNeedsUpdate,
        "CCertManager::UpdateDefaultCertificate");
      goto LABEL_48;
    }
    v22.cbData = pcbData;
    v22.pbData = pvData;
    if ( (unsigned int)TsCryptAclCertForNetworkService(&v22, 0) )
    {
      v15 = CCertManager::PutHashInTheRegistry(v14, 0, L"TemplateCertificate", pvData, pcbData);
      IsCurrentCertificateNeedsUpdate = v15;
      if ( v15 >= 0 )
      {
        CCertManager::SecLogEvent(v17, v16, 0xC0000427, this[202], pvData, pcbData);
        return (unsigned int)IsCurrentCertificateNeedsUpdate;
      }
      _DbgPrintMessage(8, "PutHashInTheRegistry failed: 0x%x in %s", v15, "CCertManager::UpdateDefaultCertificate");
    }
    else
    {
      IsCurrentCertificateNeedsUpdate = -2147024891;
    }
    v13 = -1073740759;
LABEL_54:
    CCertManager::SecLogFailure(1u, v13, IsCurrentCertificateNeedsUpdate);
    if ( v2 )
      TsCryptDeleteCertificate(L"My", pvData, pcbData);
    return (unsigned int)IsCurrentCertificateNeedsUpdate;
  }
  if ( v7 )
    CCertManager::PutHashInTheRegistry(v8, 0, L"TemplateCertificate", 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180003860  push    rbp
0x180003862  push    rbx
0x180003863  push    rsi
0x180003864  push    rdi
0x180003865  push    r12
0x180003867  push    r13
0x180003869  push    r14
0x18000386b  push    r15
0x18000386d  lea     rbp, [rsp-1Fh]
0x180003872  sub     rsp, 0E8h
0x180003879  mov     rax, cs:__security_cookie
0x180003880  xor     rax, rsp
0x180003883  mov     [rbp+57h+var_50], rax
0x180003887  mov     r13, rcx
0x18000388a  mov     [rbp+57h+var_D0], 14h
0x180003891  xorps   xmm0, xmm0
0x180003894  movups  xmmword ptr [rbp+57h+var_C0.cbData], xmm0
0x180003898  xor     edi, edi
0x18000389a  mov     [rbp+57h+var_C8], edi
0x18000389d  mov     r12d, edi
0x1800038a0  mov     [rbp+57h+var_C4], edi
0x1800038a3  lea     rsi, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x1800038aa  mov     [rbp+57h+var_A8], rsi
0x1800038ae  mov     [rbp+57h+Block], rdi
0x1800038b2  mov     [rbp+57h+var_98], edi
0x1800038b5  mov     [rbp+57h+hKey], rdi
0x1800038b9  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFFh
0x1800038c1  mov     [rbp+57h+var_B0], rdi
0x1800038c5  mov     [rbp+57h+var_CC], edi
0x1800038c8  lea     rax, [rbp+57h+hKey]
0x1800038cc  mov     [rsp+120h+phkResult], rax; phkResult
0x1800038d1  mov     r9d, 20019h; samDesired
0x1800038d7  xor     r8d, r8d; ulOptions
0x1800038da  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x1800038e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800038e8  call    cs:__imp_RegOpenKeyExW
0x1800038ee  mov     ebx, eax
0x1800038f0  test    eax, eax
0x1800038f2  jz      short loc_180003903
0x1800038f4  mov     [rbp+57h+hKey], rdi
0x1800038f8  jle     short loc_180003903
0x1800038fa  movzx   ebx, ax
0x1800038fd  or      ebx, 80070000h
0x180003903  mov     r14d, 8
0x180003909  test    ebx, ebx
0x18000390b  jns     short loc_18000392B
0x18000390d  lea     r9, aCcertmanagerGe_0; "CCertManager::GetHashFromTheRegistry"
0x180003914  mov     r8d, ebx
0x180003917  lea     rdx, aPregOpenkeyFai; "pReg->OpenKey failed: 0x%x in %s"
0x18000391e  mov     ecx, r14d; int
0x180003921  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003926  jmp     loc_1800039B1
0x18000392b  mov     dword ptr [rsp+120h+phkResult], 3; unsigned int
0x180003933  lea     r9, [rbp+57h+var_CC]; unsigned int *
0x180003937  lea     r8, [rbp+57h+var_B0]; unsigned __int8 **
0x18000393b  lea     rdx, aTemplatecertif; "TemplateCertificate"
0x180003942  lea     rcx, [rbp+57h+var_A8]; this
0x180003946  call    ?ReadReg@CRegistry@@QEAAKPEBGPEAPEAEPEAKK@Z; CRegistry::ReadReg(ushort const *,uchar * *,ulong *,ulong)
0x18000394b  mov     ebx, eax
0x18000394d  test    eax, eax
0x18000394f  jle     short loc_18000395A
0x180003951  movzx   ebx, ax
0x180003954  or      ebx, 80070000h
0x18000395a  test    ebx, ebx
0x18000395c  jns     short loc_180003979
0x18000395e  lea     r9, aCcertmanagerGe_0; "CCertManager::GetHashFromTheRegistry"
0x180003965  mov     r8d, ebx
0x180003968  lea     rdx, aPregReadregbin; "pReg->ReadRegBinary failed: 0x%x in %s"
0x18000396f  mov     ecx, r14d; int
0x180003972  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003977  jmp     short loc_1800039B1
0x180003979  cmp     [rbp+57h+var_CC], 14h
0x18000397d  jz      short loc_180003986
0x18000397f  mov     ebx, 8007000Dh
0x180003984  jmp     short loc_1800039B1
0x180003986  mov     ecx, edi
0x180003988  mov     rdx, [rbp+57h+var_B0]
0x18000398c  cmp     ecx, 14h
0x18000398f  jnb     short loc_1800039AC
0x180003991  mov     eax, ecx
0x180003993  cmp     byte ptr [rax+rdx], 0
0x180003997  jnz     short loc_18000399D
0x180003999  inc     ecx
0x18000399b  jmp     short loc_18000398C
0x18000399d  movups  xmm0, xmmword ptr [rdx]
0x1800039a0  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800039a4  mov     eax, [rdx+10h]
0x1800039a7  mov     [rbp+57h+var_58], eax
0x1800039aa  jmp     short loc_1800039B1
0x1800039ac  mov     ebx, 80070002h
0x1800039b1  mov     [rbp+57h+var_A8], rsi
0x1800039b5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800039b9  test    rcx, rcx
0x1800039bc  jz      short loc_1800039C8
0x1800039be  call    cs:__imp_RegCloseKey
0x1800039c4  mov     [rbp+57h+hKey], rdi
0x1800039c8  mov     rcx, [rbp+57h+Block]; Block
0x1800039cc  test    rcx, rcx
0x1800039cf  jz      short loc_1800039D6
0x1800039d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800039d6  test    ebx, ebx
0x1800039d8  js      short loc_1800039E3
0x1800039da  mov     edi, 1
0x1800039df  mov     esi, edi
0x1800039e1  jmp     short loc_180003A0B
0x1800039e3  cmp     ebx, 80070002h
0x1800039e9  jz      short loc_180003A04
0x1800039eb  cmp     ebx, 8007000Dh
0x1800039f1  jz      short loc_180003A04
0x1800039f3  lea     rdx, aGethashfromthe_0; "GetHashFromTheRegistry failed: 0x%x in "...
0x1800039fa  mov     edi, 1
0x1800039ff  jmp     loc_180003B78
0x180003a04  mov     esi, edi
0x180003a06  mov     edi, 1
0x180003a0b  lea     rcx, [r13+688h]; this
0x180003a12  call    ?RenewTemplateInfo@CCertEnrollment@@QEAAJXZ; CCertEnrollment::RenewTemplateInfo(void)
0x180003a17  mov     ebx, eax
0x180003a19  test    eax, eax
0x180003a1b  jns     short loc_180003A29
0x180003a1d  lea     rdx, aMCertenrollmen_0; "m_CertEnrollment.RenewTemplateInfo fail"...
0x180003a24  jmp     loc_180003B78
0x180003a29  cmp     dword ptr [r13+6A8h], 0
0x180003a31  jnz     short loc_180003A57
0x180003a33  test    esi, esi
0x180003a35  jz      short loc_180003A50
0x180003a37  mov     dword ptr [rsp+120h+phkResult], 0; unsigned int
0x180003a3f  xor     r9d, r9d; unsigned __int8 *
0x180003a42  lea     r8, aTemplatecertif; "TemplateCertificate"
0x180003a49  xor     edx, edx; struct CRegistry *
0x180003a4b  call    ?PutHashInTheRegistry@CCertManager@@AEAAJPEAVCRegistry@@PEBGPEAEK@Z; CCertManager::PutHashInTheRegistry(CRegistry *,ushort const *,uchar *,ulong)
0x180003a50  xor     eax, eax
0x180003a52  jmp     loc_180003C3C
0x180003a57  test    esi, esi
0x180003a59  jz      loc_180003AEC
0x180003a5f  xor     eax, eax
0x180003a61  lea     rcx, [rbp+57h+var_C4]
0x180003a65  mov     [rsp+120h+var_D8], rcx; int *
0x180003a6a  lea     rcx, [rbp+57h+var_C8]
0x180003a6e  mov     [rsp+120h+var_E0], rcx; int *
0x180003a73  mov     [rsp+120h+var_E8], edi; unsigned int
0x180003a77  mov     [rsp+120h+var_F0], ax; unsigned __int16
0x180003a7c  mov     dword ptr [rsp+120h+pcbData], eax; int
0x180003a80  mov     dword ptr [rsp+120h+phkResult], edi; int
0x180003a84  xor     r9d, r9d; unsigned __int16 *
0x180003a87  lea     rdx, [rbp+57h+var_68]; unsigned __int8 *
0x180003a8b  mov     rcx, r13; this
0x180003a8e  call    ?IsCurrentCertificateNeedsUpdate@CCertManager@@AEAAJPEAEKPEBGHHGKPEAH2@Z; CCertManager::IsCurrentCertificateNeedsUpdate(uchar *,ulong,ushort const *,int,int,ushort,ulong,int *,int *)
0x180003a93  mov     ebx, eax
0x180003a95  test    eax, eax
0x180003a97  jns     short loc_180003AA5
0x180003a99  lea     rdx, aIscurrentcerti; "IsCurrentCertificateNeedsUpdate failed:"...
0x180003aa0  jmp     loc_180003B78
0x180003aa5  mov     rcx, r13; this
0x180003aa8  call    ?MustFixCertificatePermissions@CCertManager@@AEAAHXZ; CCertManager::MustFixCertificatePermissions(void)
0x180003aad  test    eax, eax
0x180003aaf  jz      short loc_180003AC9
0x180003ab1  mov     [rbp+57h+var_C0.cbData], 14h
0x180003ab8  lea     rax, [rbp+57h+var_68]
0x180003abc  mov     [rbp+57h+var_C0.pbData], rax
0x180003ac0  lea     rdx, [rbp+57h+var_C0]; struct _CRYPTOAPI_BLOB *
0x180003ac4  call    ?FixCertificatePermissions@CCertManager@@AEAAHPEAU_CRYPTOAPI_BLOB@@@Z; CCertManager::FixCertificatePermissions(_CRYPTOAPI_BLOB *)
0x180003ac9  cmp     [rbp+57h+var_C8], 0
0x180003acd  jz      loc_180003C3A
0x180003ad3  mov     dword ptr [rsp+120h+phkResult], 0; unsigned int
0x180003adb  xor     r9d, r9d; unsigned __int8 *
0x180003ade  lea     r8, aTemplatecertif; "TemplateCertificate"
0x180003ae5  xor     edx, edx; struct CRegistry *
0x180003ae7  call    ?PutHashInTheRegistry@CCertManager@@AEAAJPEAVCRegistry@@PEBGPEAEK@Z; CCertManager::PutHashInTheRegistry(CRegistry *,ushort const *,uchar *,ulong)
0x180003aec  lea     rax, [rbp+57h+var_D0]
0x180003af0  mov     [rsp+120h+pcbData], rax; pcbData
0x180003af5  lea     rax, [rbp+57h+pvData]
0x180003af9  mov     [rsp+120h+phkResult], rax; pvData
0x180003afe  mov     r8, [r13+650h]; int
0x180003b05  mov     rdx, [r13+6A0h]; int
0x180003b0c  mov     rcx, [r13+690h]; int
0x180003b13  call    TsCryptFindTemplateCertificate
0x180003b18  mov     ebx, eax
0x180003b1a  cmp     eax, 80070002h
0x180003b1f  jnz     short loc_180003B6D
0x180003b21  mov     [rbp+57h+var_D0], 14h
0x180003b28  lea     r8, [rbp+57h+var_D0]; unsigned int *
0x180003b2c  lea     rdx, [rbp+57h+pvData]; unsigned __int8 *
0x180003b30  lea     rcx, [r13+688h]; this
0x180003b37  call    ?EnrollForTemplate@CCertEnrollment@@QEAAJPEAEPEAK@Z; CCertEnrollment::EnrollForTemplate(uchar *,ulong *)
0x180003b3c  mov     ebx, eax
0x180003b3e  test    eax, eax
0x180003b40  jns     short loc_180003B4B
0x180003b42  lea     rdx, aMCertenrollmen; "m_CertEnrollment.EnrollForTemplate fail"...
0x180003b49  jmp     short loc_180003B78
0x180003b4b  mov     r12d, edi
0x180003b4e  mov     r8d, [rbp+57h+var_D0]; unsigned int
0x180003b52  lea     rdx, [rbp+57h+pvData]; unsigned __int8 *
0x180003b56  mov     rcx, r13; this
0x180003b59  call    ?ValidateDefaultCertAndLogProblems@CCertManager@@AEAAJPEAEK@Z; CCertManager::ValidateDefaultCertAndLogProblems(uchar *,ulong)
0x180003b5e  mov     ebx, eax
0x180003b60  test    eax, eax
0x180003b62  jns     short loc_180003B91
0x180003b64  lea     rdx, aValidatedefaul; "ValidateDefaultCertAndLogProblems faile"...
0x180003b6b  jmp     short loc_180003B78
0x180003b6d  test    ebx, ebx
0x180003b6f  jns     short loc_180003B91
0x180003b71  lea     rdx, aFindcertinstor; "FindCertInStore failed: 0x%x in %s"
0x180003b78  lea     r9, aCcertmanagerUp_0; "CCertManager::UpdateDefaultCertificate"
0x180003b7f  mov     r8d, ebx
0x180003b82  mov     ecx, r14d; int
0x180003b85  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003b8a  mov     edx, 0C0000428h
0x180003b8f  jmp     short loc_180003BF2
0x180003b91  mov     eax, [rbp+57h+var_D0]
0x180003b94  mov     [rbp+57h+var_C0.cbData], eax
0x180003b97  lea     rax, [rbp+57h+pvData]
0x180003b9b  mov     [rbp+57h+var_C0.pbData], rax
0x180003b9f  xor     edx, edx
0x180003ba1  lea     rcx, [rbp+57h+var_C0]
0x180003ba5  call    TsCryptAclCertForNetworkService
0x180003baa  test    eax, eax
0x180003bac  jnz     short loc_180003BB5
0x180003bae  mov     ebx, 80070005h
0x180003bb3  jmp     short loc_180003BED
0x180003bb5  mov     eax, [rbp+57h+var_D0]
0x180003bb8  mov     dword ptr [rsp+120h+phkResult], eax; unsigned int
0x180003bbc  lea     r9, [rbp+57h+pvData]; unsigned __int8 *
0x180003bc0  lea     r8, aTemplatecertif; "TemplateCertificate"
0x180003bc7  xor     edx, edx; struct CRegistry *
0x180003bc9  call    ?PutHashInTheRegistry@CCertManager@@AEAAJPEAVCRegistry@@PEBGPEAEK@Z; CCertManager::PutHashInTheRegistry(CRegistry *,ushort const *,uchar *,ulong)
0x180003bce  mov     ebx, eax
0x180003bd0  test    eax, eax
0x180003bd2  jns     short loc_180003C18
0x180003bd4  lea     r9, aCcertmanagerUp_0; "CCertManager::UpdateDefaultCertificate"
0x180003bdb  mov     r8d, eax
0x180003bde  lea     rdx, aPuthashinthere_0; "PutHashInTheRegistry failed: 0x%x in %s"
0x180003be5  mov     ecx, r14d; int
0x180003be8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003bed  mov     edx, 0C0000429h; unsigned int
0x180003bf2  mov     r8d, ebx; int
0x180003bf5  movzx   ecx, di; unsigned __int16
0x180003bf8  call    ?SecLogFailure@CCertManager@@CAJGIJ@Z; CCertManager::SecLogFailure(ushort,uint,long)
0x180003bfd  test    r12d, r12d
0x180003c00  jz      short loc_180003C3A
0x180003c02  mov     r8d, [rbp+57h+var_D0]
0x180003c06  lea     rdx, [rbp+57h+pvData]
0x180003c0a  lea     rcx, aMy; "My"
0x180003c11  call    TsCryptDeleteCertificate
0x180003c16  jmp     short loc_180003C3A
0x180003c18  mov     eax, [rbp+57h+var_D0]
0x180003c1b  mov     dword ptr [rsp+120h+pcbData], eax; unsigned int
0x180003c1f  lea     rax, [rbp+57h+pvData]
0x180003c23  mov     [rsp+120h+phkResult], rax; unsigned __int8 *
0x180003c28  mov     r9, [r13+650h]; unsigned __int16 *
0x180003c2f  mov     r8d, 0C0000427h; unsigned int
0x180003c35  call    ?SecLogEvent@CCertManager@@AEAAJGIPEBGPEAEK@Z; CCertManager::SecLogEvent(ushort,uint,ushort const *,uchar *,ulong)
0x180003c3a  mov     eax, ebx
0x180003c3c  mov     rcx, [rbp+57h+var_50]
0x180003c40  xor     rcx, rsp; StackCookie
0x180003c43  call    __security_check_cookie
0x180003c48  add     rsp, 0E8h
0x180003c4f  pop     r15
0x180003c51  pop     r14
0x180003c53  pop     r13
0x180003c55  pop     r12
0x180003c57  pop     rdi
0x180003c58  pop     rsi
0x180003c59  pop     rbx
0x180003c5a  pop     rbp
0x180003c5b  retn
```
