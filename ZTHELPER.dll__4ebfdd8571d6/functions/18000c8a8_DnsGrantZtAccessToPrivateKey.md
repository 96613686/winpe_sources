# DnsGrantZtAccessToPrivateKey

- ea: `0x18000c8a8`
- end: `0x18000cb05`
- name: `DnsGrantZtAccessToPrivateKey`
- size: `605`
- prototype: `__int64 __fastcall(const CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bbbc`

## callees

- `0x1800014b0`
- `0x18000bc50`
- `0x18000c224`
- `0x18000c8a8`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9af`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c9a5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c9a5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000ca50`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000ca50`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000ca61`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000ca61`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000ca0b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000ca0b`
- `ncrypt!NCryptGetProperty` at `0x18000c93b`
- `ncrypt!NCryptGetProperty` at `0x18000c986`
- `ncrypt!NCryptGetProperty` at `0x18000c93b`
- `ncrypt!NCryptGetProperty` at `0x18000c986`
- `ncrypt!NCryptSetProperty` at `0x18000ca83`
- `ncrypt!NCryptSetProperty` at `0x18000ca83`
- `ncrypt!NCryptFreeObject` at `0x18000ca96`
- `ncrypt!NCryptFreeObject` at `0x18000ca96`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18000c9f0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18000c9f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cab0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cab0`

## string_xrefs

- `0x18000c929`: `Security Descr`
- `0x18000c96f`: `Security Descr`
- `0x18000ca6b`: `Security Descr`

## pseudocode

```c
__int64 __fastcall DnsGrantZtAccessToPrivateKey(const CERT_CONTEXT *a1)
{
  BYTE *v1; // rdi
  DWORD KeyHandle; // ebx
  DWORD LastError; // eax
  DWORD cbOutput; // [rsp+40h] [rbp-29h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-21h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-19h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+58h] [rbp-11h] BYREF
  WORD pControl[2]; // [rsp+88h] [rbp+1Fh] BYREF
  WINBOOL bDaclDefaulted; // [rsp+8Ch] [rbp+23h] BYREF
  WINBOOL bDaclPresent; // [rsp+90h] [rbp+27h] BYREF
  DWORD dwRevision; // [rsp+94h] [rbp+2Bh] BYREF

  v1 = 0;
  dwRevision = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  NewAcl = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  pControl[0] = 0;
  cbOutput = 0;
  KeyHandle = GetKeyHandle(a1);
  if ( !KeyHandle )
  {
    KeyHandle = NCryptGetProperty(0, L"Security Descr", 0, 0, &cbOutput, 4u);
    if ( !KeyHandle )
    {
      v1 = (BYTE *)Dns_Allocate(cbOutput);
      if ( v1 )
      {
        KeyHandle = NCryptGetProperty(0, L"Security Descr", v1, cbOutput, &cbOutput, 4u);
        if ( !KeyHandle )
        {
          if ( !GetSecurityDescriptorDacl(v1, &bDaclPresent, &pDacl, &bDaclDefaulted) )
            goto LABEL_7;
          pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)qword_18001AF10;
          pListOfExplicitEntries.grfAccessPermissions = -2147352551;
          *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
          pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
          pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
          KeyHandle = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, &NewAcl);
          if ( KeyHandle )
            goto LABEL_16;
          if ( !GetSecurityDescriptorControl(v1, pControl, &dwRevision) )
            goto LABEL_7;
          if ( (pControl[0] & 0x8000u) != 0 )
          {
            KeyHandle = ConvertRelativeSDToAbsoluteSD(v1);
            if ( KeyHandle )
              goto LABEL_16;
            Dns_Free(v1);
            v1 = 0;
          }
          if ( SetSecurityDescriptorDacl(v1, 1, NewAcl, 0) )
          {
            cbOutput = GetSecurityDescriptorLength(v1);
            LastError = NCryptSetProperty(0, L"Security Descr", v1, cbOutput, 4u);
          }
          else
          {
LABEL_7:
            LastError = GetLastError();
          }
          KeyHandle = LastError;
        }
      }
      else
      {
        KeyHandle = 14;
      }
    }
  }
LABEL_16:
  Dns_Free(v1);
  Dns_Free(0);
  LocalFree(NewAcl);
  NewAcl = 0;
  if ( KeyHandle && (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 59, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, KeyHandle);
  return KeyHandle;
}

```

## disassembly

```asm
0x18000c8a8  push    rbp
0x18000c8aa  push    rbx
0x18000c8ab  push    rdi
0x18000c8ac  push    r14
0x18000c8ae  lea     rbp, [rsp-3Fh]
0x18000c8b3  sub     rsp, 0A8h
0x18000c8ba  mov     rax, cs:__security_cookie
0x18000c8c1  xor     rax, rsp
0x18000c8c4  mov     [rbp+57h+var_28], rax
0x18000c8c8  xor     edi, edi
0x18000c8ca  mov     [rbp+57h+dwRevision], 0
0x18000c8d1  xorps   xmm0, xmm0
0x18000c8d4  mov     [rbp+57h+hObject], rdi
0x18000c8d8  xor     eax, eax
0x18000c8da  mov     [rbp+57h+bDaclPresent], edi
0x18000c8dd  xor     r14d, r14d
0x18000c8e0  mov     [rbp+57h+bDaclDefaulted], edi
0x18000c8e3  lea     rdx, [rbp+57h+hObject]
0x18000c8e7  mov     [rbp+57h+var_88], r14
0x18000c8eb  mov     [rbp+57h+pDacl], rdi
0x18000c8ef  mov     [rbp+57h+NewAcl], rdi
0x18000c8f3  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18000c8f7  mov     [rbp+57h+pControl], ax
0x18000c8fb  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18000c8ff  mov     [rbp+57h+cbOutput], 0
0x18000c906  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18000c90a  call    GetKeyHandle
0x18000c90f  mov     ebx, eax
0x18000c911  test    eax, eax
0x18000c913  jnz     loc_18000CA8B
0x18000c919  mov     rcx, [rbp+57h+hObject]; hObject
0x18000c91d  lea     rax, [rbp+57h+cbOutput]
0x18000c921  mov     [rsp+0C0h+dwFlags], 4; dwFlags
0x18000c929  lea     rdx, pszProperty; "Security Descr"
0x18000c930  xor     r9d, r9d; cbOutput
0x18000c933  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x18000c938  xor     r8d, r8d; pbOutput
0x18000c93b  call    cs:__imp_NCryptGetProperty
0x18000c941  mov     ebx, eax
0x18000c943  test    eax, eax
0x18000c945  jnz     loc_18000CA8B
0x18000c94b  mov     ecx, [rbp+57h+cbOutput]
0x18000c94e  call    Dns_Allocate
0x18000c953  mov     rdi, rax
0x18000c956  test    rax, rax
0x18000c959  jnz     short loc_18000C963
0x18000c95b  lea     ebx, [rax+0Eh]
0x18000c95e  jmp     loc_18000CA8B
0x18000c963  mov     r9d, [rbp+57h+cbOutput]; cbOutput
0x18000c967  lea     rax, [rbp+57h+cbOutput]
0x18000c96b  mov     rcx, [rbp+57h+hObject]; hObject
0x18000c96f  lea     rdx, pszProperty; "Security Descr"
0x18000c976  mov     [rsp+0C0h+dwFlags], 4; dwFlags
0x18000c97e  mov     r8, rdi; pbOutput
0x18000c981  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x18000c986  call    cs:__imp_NCryptGetProperty
0x18000c98c  mov     ebx, eax
0x18000c98e  test    eax, eax
0x18000c990  jnz     loc_18000CA8B
0x18000c996  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18000c99a  mov     rcx, rdi; pSecurityDescriptor
0x18000c99d  lea     r8, [rbp+57h+pDacl]; pDacl
0x18000c9a1  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18000c9a5  call    cs:__imp_GetSecurityDescriptorDacl
0x18000c9ab  test    eax, eax
0x18000c9ad  jnz     short loc_18000C9BA
0x18000c9af  call    cs:__imp_GetLastError
0x18000c9b5  jmp     loc_18000CA89
0x18000c9ba  mov     r8, [rbp+57h+pDacl]; OldAcl
0x18000c9be  lea     rax, qword_18001AF10
0x18000c9c5  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18000c9c9  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18000c9cd  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18000c9d1  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 80020019h
0x18000c9d8  mov     ecx, 1; cCountOfExplicitEntries
0x18000c9dd  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x18000c9e5  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x18000c9e9  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x18000c9f0  call    cs:__imp_SetEntriesInAclW
0x18000c9f6  mov     ebx, eax
0x18000c9f8  test    eax, eax
0x18000c9fa  jnz     loc_18000CA8B
0x18000ca00  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18000ca04  mov     rcx, rdi; pSecurityDescriptor
0x18000ca07  lea     rdx, [rbp+57h+pControl]; pControl
0x18000ca0b  call    cs:__imp_GetSecurityDescriptorControl
0x18000ca11  test    eax, eax
0x18000ca13  jz      short loc_18000C9AF
0x18000ca15  mov     eax, 8000h
0x18000ca1a  test    [rbp+57h+pControl], ax
0x18000ca1e  jz      short loc_18000CA42
0x18000ca20  lea     rdx, [rbp+57h+var_88]
0x18000ca24  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x18000ca27  call    ConvertRelativeSDToAbsoluteSD
0x18000ca2c  mov     ebx, eax
0x18000ca2e  test    eax, eax
0x18000ca30  jnz     loc_18000CAFF
0x18000ca36  mov     rcx, rdi; lpMem
0x18000ca39  call    Dns_Free
0x18000ca3e  mov     rdi, [rbp+57h+var_88]
0x18000ca42  mov     r8, [rbp+57h+NewAcl]; pDacl
0x18000ca46  xor     r9d, r9d; bDaclDefaulted
0x18000ca49  mov     rcx, rdi; pSecurityDescriptor
0x18000ca4c  lea     edx, [r9+1]; bDaclPresent
0x18000ca50  call    cs:__imp_SetSecurityDescriptorDacl
0x18000ca56  test    eax, eax
0x18000ca58  jz      loc_18000C9AF
0x18000ca5e  mov     rcx, rdi; pSecurityDescriptor
0x18000ca61  call    cs:__imp_GetSecurityDescriptorLength
0x18000ca67  mov     rcx, [rbp+57h+hObject]; hObject
0x18000ca6b  lea     rdx, pszProperty; "Security Descr"
0x18000ca72  mov     r9d, eax; cbInput
0x18000ca75  mov     [rbp+57h+cbOutput], eax
0x18000ca78  mov     r8, rdi; pbInput
0x18000ca7b  mov     dword ptr [rsp+0C0h+pcbResult], 4; dwFlags
0x18000ca83  call    cs:__imp_NCryptSetProperty
0x18000ca89  mov     ebx, eax
0x18000ca8b  cmp     [rbp+57h+hObject], 0
0x18000ca90  jz      short loc_18000CA9C
0x18000ca92  mov     rcx, [rbp+57h+hObject]; hObject
0x18000ca96  call    cs:__imp_NCryptFreeObject
0x18000ca9c  mov     rcx, rdi; lpMem
0x18000ca9f  call    Dns_Free
0x18000caa4  mov     rcx, r14; lpMem
0x18000caa7  call    Dns_Free
0x18000caac  mov     rcx, [rbp+57h+NewAcl]; hMem
0x18000cab0  call    cs:__imp_LocalFree
0x18000cab6  mov     [rbp+57h+NewAcl], 0
0x18000cabe  test    ebx, ebx
0x18000cac0  jz      short loc_18000CAE4
0x18000cac2  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000cac9  jz      short loc_18000CAE4
0x18000cacb  mov     edx, 3Bh ; ';'
0x18000cad0  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000cad7  mov     ecx, 40Bh
0x18000cadc  mov     r9d, ebx
0x18000cadf  call    WPP_SF_d
0x18000cae4  mov     eax, ebx
0x18000cae6  mov     rcx, [rbp+57h+var_28]
0x18000caea  xor     rcx, rsp; StackCookie
0x18000caed  call    __security_check_cookie
0x18000caf2  add     rsp, 0A8h
0x18000caf9  pop     r14
0x18000cafb  pop     rdi
0x18000cafc  pop     rbx
0x18000cafd  pop     rbp
0x18000cafe  retn
0x18000caff  mov     r14, [rbp+57h+var_88]
0x18000cb03  jmp     short loc_18000CA8B
```
