# SHTranslateSIDToName

- ea: `0x1800d4c58`
- end: `0x1800d4e76`
- name: `SHTranslateSIDToName`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c51c0`

## callees

- `0x1800d4b08`
- `0x1800d4b60`
- `0x1800d4c58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d4d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d4d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d4e38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d4e38`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800d4ca7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800d4ca7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800d4e4d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800d4e57`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800d4e4d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800d4e57`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800d4e61`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800d4e61`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x1800d4ce4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x1800d4ce4`

## pseudocode

```c
__int64 __fastcall SHTranslateSIDToName(void *a1, wchar_t **a2)
{
  HRESULT v3; // ebx
  int v4; // eax
  int v5; // eax
  unsigned int v6; // r8d
  unsigned __int64 v7; // rdi
  size_t *v8; // r8
  size_t v9; // r9
  wchar_t *v10; // r11
  size_t v11; // rdi
  size_t *v12; // r8
  size_t pcchDestLength; // [rsp+30h] [rbp-48h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-40h] BYREF
  PSID Sids; // [rsp+A0h] [rbp+28h] BYREF
  PLSA_TRANSLATED_NAME Names; // [rsp+A8h] [rbp+30h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+B0h] [rbp+38h] BYREF
  PVOID PolicyHandle; // [rsp+B8h] [rbp+40h] BYREF

  Sids = a1;
  *a2 = 0;
  v3 = -2147024809;
  if ( a1 )
  {
    PolicyHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle) | 0x10000000;
    if ( v4 < 0 )
      return (unsigned int)v4;
    ReferencedDomains = 0;
    Names = 0;
    v5 = LsaLookupSids(PolicyHandle, 1u, &Sids, &ReferencedDomains, &Names) | 0x10000000;
    if ( v5 < 0 )
    {
      v3 = v5;
      goto LABEL_24;
    }
    if ( (unsigned int)(Names->Use - 7) <= 1 )
    {
      v3 = -2147467259;
      goto LABEL_24;
    }
    v6 = Names->Name.Length + 2;
    if ( Names->DomainIndex >= 0 )
      v6 = ReferencedDomains->Domains[Names->DomainIndex].Name.Length + Names->Name.Length + 4;
    v7 = v6;
    v10 = (wchar_t *)CoTaskMemAlloc(v6);
    if ( v10 )
    {
      v11 = v7 >> 1;
      if ( Names->DomainIndex < 0 )
      {
        *v10 = 0;
      }
      else
      {
        if ( v11 )
        {
          v3 = StringCopyWorkerW(
                 v10,
                 v11,
                 v8,
                 ReferencedDomains->Domains[Names->DomainIndex].Name.Buffer,
                 (unsigned __int64)ReferencedDomains->Domains[Names->DomainIndex].Name.Length >> 1);
          if ( v3 >= 0 )
          {
            pcchDestLength = 0;
            v3 = StringValidateDestAndLengthW(v10, v11, &pcchDestLength, v9);
            if ( v3 >= 0 )
              v3 = StringCopyWorkerW(&v10[pcchDestLength], v11 - pcchDestLength, v12, L"\\", 0x7FFFFFFEu);
          }
        }
        if ( v3 < 0 )
          goto LABEL_21;
      }
      pcchDestLength = 0;
      v3 = StringValidateDestAndLengthW(v10, v11, &pcchDestLength, v9);
      if ( v3 >= 0 )
        v3 = StringCopyWorkerW(
               &v10[pcchDestLength],
               v11 - pcchDestLength,
               (size_t *)((unsigned __int64)Names->Name.Length >> 1),
               Names->Name.Buffer,
               (unsigned __int64)Names->Name.Length >> 1);
      if ( v3 >= 0 )
      {
        *a2 = v10;
        v10 = 0;
      }
    }
    else
    {
      v3 = -2147024882;
    }
LABEL_21:
    CoTaskMemFree(v10);
LABEL_24:
    LsaFreeMemory(ReferencedDomains);
    LsaFreeMemory(Names);
    LsaClose(PolicyHandle);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800d4c58  mov     [rsp-20h+Sids], rcx
0x1800d4c5d  push    rbp
0x1800d4c5e  push    rbx
0x1800d4c5f  push    rsi
0x1800d4c60  push    rdi
0x1800d4c61  mov     rbp, rsp
0x1800d4c64  sub     rsp, 78h
0x1800d4c68  mov     qword ptr [rdx], 0
0x1800d4c6f  mov     rsi, rdx
0x1800d4c72  mov     ebx, 80070057h
0x1800d4c77  test    rcx, rcx
0x1800d4c7a  jz      loc_1800D4E6B
0x1800d4c80  xorps   xmm0, xmm0
0x1800d4c83  mov     [rbp+PolicyHandle], 0
0x1800d4c8b  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800d4c8f  mov     r8d, 800h; DesiredAccess
0x1800d4c95  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800d4c99  xor     ecx, ecx; SystemName
0x1800d4c9b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800d4c9f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800d4ca3  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d4ca7  call    cs:__imp_LsaOpenPolicy
0x1800d4cad  mov     edi, 10000000h
0x1800d4cb2  or      eax, edi
0x1800d4cb4  jl      loc_1800D4E69
0x1800d4cba  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800d4cbe  lea     rax, [rbp+arg_8]
0x1800d4cc2  lea     r9, [rbp+ReferencedDomains]; ReferencedDomains
0x1800d4cc6  mov     [rsp+78h+Names], rax; Names
0x1800d4ccb  lea     r8, [rbp+Sids]; Sids
0x1800d4ccf  mov     [rbp+ReferencedDomains], 0
0x1800d4cd7  mov     edx, 1; Count
0x1800d4cdc  mov     [rbp+arg_8], 0
0x1800d4ce4  call    cs:__imp_LsaLookupSids
0x1800d4cea  or      eax, edi
0x1800d4cec  jl      loc_1800D4E47
0x1800d4cf2  mov     rcx, [rbp+arg_8]
0x1800d4cf6  mov     eax, [rcx]
0x1800d4cf8  sub     eax, 7
0x1800d4cfb  cmp     eax, 1
0x1800d4cfe  jbe     loc_1800D4E40
0x1800d4d04  movzx   r8d, word ptr [rcx+8]
0x1800d4d09  add     r8d, 2
0x1800d4d0d  cmp     dword ptr [rcx+18h], 0
0x1800d4d11  jl      short loc_1800D4D2E
0x1800d4d13  movsxd  rax, dword ptr [rcx+18h]
0x1800d4d17  add     r8d, 2
0x1800d4d1b  lea     rdx, [rax+rax*2]
0x1800d4d1f  mov     rax, [rbp+ReferencedDomains]
0x1800d4d23  mov     rcx, [rax+8]
0x1800d4d27  movzx   eax, word ptr [rcx+rdx*8]
0x1800d4d2b  add     r8d, eax
0x1800d4d2e  mov     ecx, r8d; cb
0x1800d4d31  mov     edi, r8d
0x1800d4d34  call    cs:__imp_CoTaskMemAlloc
0x1800d4d3a  mov     r11, rax
0x1800d4d3d  test    rax, rax
0x1800d4d40  jz      loc_1800D4E30
0x1800d4d46  mov     rax, [rbp+arg_8]
0x1800d4d4a  shr     rdi, 1
0x1800d4d4d  cmp     dword ptr [rax+18h], 0
0x1800d4d51  jl      loc_1800D4DD7
0x1800d4d57  test    rdi, rdi
0x1800d4d5a  jz      short loc_1800D4DD1
0x1800d4d5c  movsxd  rax, dword ptr [rax+18h]
0x1800d4d60  mov     rdx, rdi; cchDest
0x1800d4d63  lea     rcx, [rax+rax*2]
0x1800d4d67  mov     rax, [rbp+ReferencedDomains]
0x1800d4d6b  mov     r9, [rax+8]
0x1800d4d6f  movzx   eax, word ptr [r9+rcx*8]
0x1800d4d74  mov     r9, [r9+rcx*8+8]; pszSrc
0x1800d4d79  mov     rcx, r11; pszDest
0x1800d4d7c  shr     rax, 1
0x1800d4d7f  mov     [rsp+78h+Names], rax; cchToCopy
0x1800d4d84  call    StringCopyWorkerW
0x1800d4d89  mov     ebx, eax
0x1800d4d8b  test    eax, eax
0x1800d4d8d  js      short loc_1800D4DD1
0x1800d4d8f  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x1800d4d93  mov     [rbp+pcchDestLength], 0
0x1800d4d9b  mov     rdx, rdi; cchDest
0x1800d4d9e  mov     rcx, r11; pszDest
0x1800d4da1  call    StringValidateDestAndLengthW
0x1800d4da6  mov     ebx, eax
0x1800d4da8  test    eax, eax
0x1800d4daa  js      short loc_1800D4DD1
0x1800d4dac  mov     rax, [rbp+pcchDestLength]
0x1800d4db0  lea     r9, pszSrc; "\\"
0x1800d4db7  mov     rdx, rdi
0x1800d4dba  mov     [rsp+78h+Names], 7FFFFFFEh; cchToCopy
0x1800d4dc3  sub     rdx, rax; cchDest
0x1800d4dc6  lea     rcx, [r11+rax*2]; pszDest
0x1800d4dca  call    StringCopyWorkerW
0x1800d4dcf  mov     ebx, eax
0x1800d4dd1  test    ebx, ebx
0x1800d4dd3  jns     short loc_1800D4DDD
0x1800d4dd5  jmp     short loc_1800D4E35
0x1800d4dd7  xor     eax, eax
0x1800d4dd9  mov     [r11], ax
0x1800d4ddd  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x1800d4de1  mov     [rbp+pcchDestLength], 0
0x1800d4de9  mov     rdx, rdi; cchDest
0x1800d4dec  mov     rcx, r11; pszDest
0x1800d4def  call    StringValidateDestAndLengthW
0x1800d4df4  mov     ebx, eax
0x1800d4df6  test    eax, eax
0x1800d4df8  js      short loc_1800D4E24
0x1800d4dfa  mov     r9, [rbp+arg_8]
0x1800d4dfe  mov     rax, [rbp+pcchDestLength]
0x1800d4e02  sub     rdi, rax
0x1800d4e05  mov     rdx, rdi; cchDest
0x1800d4e08  movzx   r8d, word ptr [r9+8]
0x1800d4e0d  mov     r9, [r9+10h]; pszSrc
0x1800d4e11  lea     rcx, [r11+rax*2]; pszDest
0x1800d4e15  shr     r8, 1; pcchNewDestLength
0x1800d4e18  mov     [rsp+78h+Names], r8; cchToCopy
0x1800d4e1d  call    StringCopyWorkerW
0x1800d4e22  mov     ebx, eax
0x1800d4e24  test    ebx, ebx
0x1800d4e26  js      short loc_1800D4E35
0x1800d4e28  mov     [rsi], r11
0x1800d4e2b  xor     r11d, r11d
0x1800d4e2e  jmp     short loc_1800D4E35
0x1800d4e30  mov     ebx, 8007000Eh
0x1800d4e35  mov     rcx, r11; pv
0x1800d4e38  call    cs:__imp_CoTaskMemFree
0x1800d4e3e  jmp     short loc_1800D4E49
0x1800d4e40  mov     ebx, 80004005h
0x1800d4e45  jmp     short loc_1800D4E49
0x1800d4e47  mov     ebx, eax
0x1800d4e49  mov     rcx, [rbp+ReferencedDomains]; Buffer
0x1800d4e4d  call    cs:__imp_LsaFreeMemory
0x1800d4e53  mov     rcx, [rbp+arg_8]; Buffer
0x1800d4e57  call    cs:__imp_LsaFreeMemory
0x1800d4e5d  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800d4e61  call    cs:__imp_LsaClose
0x1800d4e67  jmp     short loc_1800D4E6B
0x1800d4e69  mov     ebx, eax
0x1800d4e6b  mov     eax, ebx
0x1800d4e6d  add     rsp, 78h
0x1800d4e71  pop     rdi
0x1800d4e72  pop     rsi
0x1800d4e73  pop     rbx
0x1800d4e74  pop     rbp
0x1800d4e75  retn
```
