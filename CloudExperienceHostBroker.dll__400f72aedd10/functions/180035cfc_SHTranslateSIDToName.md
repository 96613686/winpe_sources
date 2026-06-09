# SHTranslateSIDToName

- ea: `0x180035cfc`
- end: `0x180035f1a`
- name: `SHTranslateSIDToName`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180035a5c`

## callees

- `0x1800359b0`
- `0x180035a08`
- `0x180035cfc`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180035f05`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180035f05`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180035d4b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180035d4b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x180035d88`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x180035d88`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180035ef1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180035efb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180035ef1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180035efb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035edc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035edc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035dd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035dd8`

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
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-40h] BYREF
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
          v3 = StringCopyWorkerW_0(
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
              v3 = StringCopyWorkerW_0(&v10[pcchDestLength], v11 - pcchDestLength, v12, L"\\", 0x7FFFFFFEu);
          }
        }
        if ( v3 < 0 )
          goto LABEL_21;
      }
      pcchDestLength = 0;
      v3 = StringValidateDestAndLengthW(v10, v11, &pcchDestLength, v9);
      if ( v3 >= 0 )
        v3 = StringCopyWorkerW_0(
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
0x180035cfc  mov     [rsp-20h+Sids], rcx
0x180035d01  push    rbp
0x180035d02  push    rbx
0x180035d03  push    rsi
0x180035d04  push    rdi
0x180035d05  mov     rbp, rsp
0x180035d08  sub     rsp, 78h
0x180035d0c  mov     qword ptr [rdx], 0
0x180035d13  mov     rsi, rdx
0x180035d16  mov     ebx, 80070057h
0x180035d1b  test    rcx, rcx
0x180035d1e  jz      loc_180035F0F
0x180035d24  xorps   xmm0, xmm0
0x180035d27  mov     [rbp+PolicyHandle], 0
0x180035d2f  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180035d33  mov     r8d, 800h; DesiredAccess
0x180035d39  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180035d3d  xor     ecx, ecx; SystemName
0x180035d3f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180035d43  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180035d47  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180035d4b  call    cs:__imp_LsaOpenPolicy
0x180035d51  mov     edi, 10000000h
0x180035d56  or      eax, edi
0x180035d58  jl      loc_180035F0D
0x180035d5e  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180035d62  lea     rax, [rbp+arg_8]
0x180035d66  lea     r9, [rbp+ReferencedDomains]; ReferencedDomains
0x180035d6a  mov     [rsp+78h+Names], rax; Names
0x180035d6f  lea     r8, [rbp+Sids]; Sids
0x180035d73  mov     [rbp+ReferencedDomains], 0
0x180035d7b  mov     edx, 1; Count
0x180035d80  mov     [rbp+arg_8], 0
0x180035d88  call    cs:__imp_LsaLookupSids
0x180035d8e  or      eax, edi
0x180035d90  jl      loc_180035EEB
0x180035d96  mov     rcx, [rbp+arg_8]
0x180035d9a  mov     eax, [rcx]
0x180035d9c  sub     eax, 7
0x180035d9f  cmp     eax, 1
0x180035da2  jbe     loc_180035EE4
0x180035da8  movzx   r8d, word ptr [rcx+8]
0x180035dad  add     r8d, 2
0x180035db1  cmp     dword ptr [rcx+18h], 0
0x180035db5  jl      short loc_180035DD2
0x180035db7  movsxd  rax, dword ptr [rcx+18h]
0x180035dbb  add     r8d, 2
0x180035dbf  lea     rdx, [rax+rax*2]
0x180035dc3  mov     rax, [rbp+ReferencedDomains]
0x180035dc7  mov     rcx, [rax+8]
0x180035dcb  movzx   eax, word ptr [rcx+rdx*8]
0x180035dcf  add     r8d, eax
0x180035dd2  mov     ecx, r8d; cb
0x180035dd5  mov     edi, r8d
0x180035dd8  call    cs:__imp_CoTaskMemAlloc
0x180035dde  mov     r11, rax
0x180035de1  test    rax, rax
0x180035de4  jz      loc_180035ED4
0x180035dea  mov     rax, [rbp+arg_8]
0x180035dee  shr     rdi, 1
0x180035df1  cmp     dword ptr [rax+18h], 0
0x180035df5  jl      loc_180035E7B
0x180035dfb  test    rdi, rdi
0x180035dfe  jz      short loc_180035E75
0x180035e00  movsxd  rax, dword ptr [rax+18h]
0x180035e04  mov     rdx, rdi; cchDest
0x180035e07  lea     rcx, [rax+rax*2]
0x180035e0b  mov     rax, [rbp+ReferencedDomains]
0x180035e0f  mov     r9, [rax+8]
0x180035e13  movzx   eax, word ptr [r9+rcx*8]
0x180035e18  mov     r9, [r9+rcx*8+8]; pszSrc
0x180035e1d  mov     rcx, r11; pszDest
0x180035e20  shr     rax, 1
0x180035e23  mov     [rsp+78h+Names], rax; cchToCopy
0x180035e28  call    StringCopyWorkerW_0
0x180035e2d  mov     ebx, eax
0x180035e2f  test    eax, eax
0x180035e31  js      short loc_180035E75
0x180035e33  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x180035e37  mov     [rbp+pcchDestLength], 0
0x180035e3f  mov     rdx, rdi; cchDest
0x180035e42  mov     rcx, r11; pszDest
0x180035e45  call    StringValidateDestAndLengthW
0x180035e4a  mov     ebx, eax
0x180035e4c  test    eax, eax
0x180035e4e  js      short loc_180035E75
0x180035e50  mov     rax, [rbp+pcchDestLength]
0x180035e54  lea     r9, pszSrc; "\\"
0x180035e5b  mov     rdx, rdi
0x180035e5e  mov     [rsp+78h+Names], 7FFFFFFEh; cchToCopy
0x180035e67  sub     rdx, rax; cchDest
0x180035e6a  lea     rcx, [r11+rax*2]; pszDest
0x180035e6e  call    StringCopyWorkerW_0
0x180035e73  mov     ebx, eax
0x180035e75  test    ebx, ebx
0x180035e77  jns     short loc_180035E81
0x180035e79  jmp     short loc_180035ED9
0x180035e7b  xor     eax, eax
0x180035e7d  mov     [r11], ax
0x180035e81  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x180035e85  mov     [rbp+pcchDestLength], 0
0x180035e8d  mov     rdx, rdi; cchDest
0x180035e90  mov     rcx, r11; pszDest
0x180035e93  call    StringValidateDestAndLengthW
0x180035e98  mov     ebx, eax
0x180035e9a  test    eax, eax
0x180035e9c  js      short loc_180035EC8
0x180035e9e  mov     r9, [rbp+arg_8]
0x180035ea2  mov     rax, [rbp+pcchDestLength]
0x180035ea6  sub     rdi, rax
0x180035ea9  mov     rdx, rdi; cchDest
0x180035eac  movzx   r8d, word ptr [r9+8]
0x180035eb1  mov     r9, [r9+10h]; pszSrc
0x180035eb5  lea     rcx, [r11+rax*2]; pszDest
0x180035eb9  shr     r8, 1; pcchNewDestLength
0x180035ebc  mov     [rsp+78h+Names], r8; cchToCopy
0x180035ec1  call    StringCopyWorkerW_0
0x180035ec6  mov     ebx, eax
0x180035ec8  test    ebx, ebx
0x180035eca  js      short loc_180035ED9
0x180035ecc  mov     [rsi], r11
0x180035ecf  xor     r11d, r11d
0x180035ed2  jmp     short loc_180035ED9
0x180035ed4  mov     ebx, 8007000Eh
0x180035ed9  mov     rcx, r11; pv
0x180035edc  call    cs:__imp_CoTaskMemFree
0x180035ee2  jmp     short loc_180035EED
0x180035ee4  mov     ebx, 80004005h
0x180035ee9  jmp     short loc_180035EED
0x180035eeb  mov     ebx, eax
0x180035eed  mov     rcx, [rbp+ReferencedDomains]; Buffer
0x180035ef1  call    cs:__imp_LsaFreeMemory
0x180035ef7  mov     rcx, [rbp+arg_8]; Buffer
0x180035efb  call    cs:__imp_LsaFreeMemory
0x180035f01  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180035f05  call    cs:__imp_LsaClose
0x180035f0b  jmp     short loc_180035F0F
0x180035f0d  mov     ebx, eax
0x180035f0f  mov     eax, ebx
0x180035f11  add     rsp, 78h
0x180035f15  pop     rdi
0x180035f16  pop     rsi
0x180035f17  pop     rbx
0x180035f18  pop     rbp
0x180035f19  retn
```
