# SHTranslateSIDToName

- ea: `0x140069c7c`
- end: `0x140069e6a`
- name: `SHTranslateSIDToName`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140024fd4`

## callees

- `0x140069a84`
- `0x140069ae4`
- `0x140069b3c`
- `0x140069c7c`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x140069d5c`
- `ole32!CoTaskMemAlloc` at `0x140069d5c`
- `ole32!CoTaskMemFree` at `0x140069e28`
- `ole32!CoTaskMemFree` at `0x140069e28`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140069e51`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140069e51`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x140069e3d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x140069e47`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x140069e3d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x140069e47`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x140069d0c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x140069d0c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x140069ccf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x140069ccf`

## pseudocode

```c
__int64 __fastcall SHTranslateSIDToName(void *a1, wchar_t **a2)
{
  HRESULT v3; // ebx
  int v4; // eax
  int v5; // eax
  unsigned int v6; // r8d
  unsigned int v7; // r14d
  wchar_t *v8; // rdi
  size_t *v9; // r8
  size_t v10; // r9
  unsigned __int64 v11; // rsi
  const unsigned __int16 *v12; // r8
  size_t pcchDestLength; // [rsp+30h] [rbp-48h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-40h] BYREF
  PSID Sids; // [rsp+B0h] [rbp+38h] BYREF
  PLSA_TRANSLATED_NAME Names; // [rsp+B8h] [rbp+40h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+C0h] [rbp+48h] BYREF
  PVOID PolicyHandle; // [rsp+C8h] [rbp+50h] BYREF

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
      goto LABEL_23;
    }
    if ( (unsigned int)(Names->Use - 7) <= 1 )
    {
      v3 = -2147467259;
      goto LABEL_23;
    }
    v6 = Names->Name.Length + 2;
    if ( Names->DomainIndex >= 0 )
      v6 = ReferencedDomains->Domains[Names->DomainIndex].Name.Length + Names->Name.Length + 4;
    v7 = v6;
    v8 = (wchar_t *)CoTaskMemAlloc(v6);
    if ( v8 )
    {
      v11 = (unsigned __int64)v7 >> 1;
      if ( Names->DomainIndex < 0 )
      {
        *v8 = 0;
      }
      else
      {
        if ( v11 )
        {
          v3 = StringCopyWorkerW_0(
                 v8,
                 (unsigned __int64)v7 >> 1,
                 v9,
                 ReferencedDomains->Domains[Names->DomainIndex].Name.Buffer,
                 (unsigned __int64)ReferencedDomains->Domains[Names->DomainIndex].Name.Length >> 1);
          if ( v3 >= 0 )
            v3 = StringCbCatW(v8, v7, v12);
        }
        if ( v3 < 0 )
          goto LABEL_20;
      }
      pcchDestLength = 0;
      v3 = StringValidateDestAndLengthW(v8, (unsigned __int64)v7 >> 1, &pcchDestLength, v10);
      if ( v3 >= 0 )
        v3 = StringCopyWorkerW_0(
               &v8[pcchDestLength],
               v11 - pcchDestLength,
               (size_t *)((unsigned __int64)Names->Name.Length >> 1),
               Names->Name.Buffer,
               (unsigned __int64)Names->Name.Length >> 1);
      if ( v3 >= 0 )
      {
        *a2 = v8;
        v8 = 0;
      }
    }
    else
    {
      v3 = -2147024882;
    }
LABEL_20:
    CoTaskMemFree(v8);
LABEL_23:
    LsaFreeMemory(ReferencedDomains);
    LsaFreeMemory(Names);
    LsaClose(PolicyHandle);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140069c7c  mov     [rsp-30h+Sids], rcx
0x140069c81  push    rbp
0x140069c82  push    rbx
0x140069c83  push    rsi
0x140069c84  push    rdi
0x140069c85  push    r14
0x140069c87  push    r15
0x140069c89  mov     rbp, rsp
0x140069c8c  sub     rsp, 78h
0x140069c90  mov     qword ptr [rdx], 0
0x140069c97  mov     r15, rdx
0x140069c9a  mov     ebx, 80070057h
0x140069c9f  test    rcx, rcx
0x140069ca2  jz      loc_140069E5B
0x140069ca8  xorps   xmm0, xmm0
0x140069cab  mov     [rbp+PolicyHandle], 0
0x140069cb3  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x140069cb7  mov     r8d, 800h; DesiredAccess
0x140069cbd  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x140069cc1  xor     ecx, ecx; SystemName
0x140069cc3  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140069cc7  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140069ccb  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140069ccf  call    cs:__imp_LsaOpenPolicy
0x140069cd5  mov     edi, 10000000h
0x140069cda  or      eax, edi
0x140069cdc  jl      loc_140069E59
0x140069ce2  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x140069ce6  lea     rax, [rbp+arg_8]
0x140069cea  lea     r9, [rbp+ReferencedDomains]; ReferencedDomains
0x140069cee  mov     [rsp+78h+Names], rax; Names
0x140069cf3  lea     r8, [rbp+Sids]; Sids
0x140069cf7  mov     [rbp+ReferencedDomains], 0
0x140069cff  mov     edx, 1; Count
0x140069d04  mov     [rbp+arg_8], 0
0x140069d0c  call    cs:__imp_LsaLookupSids
0x140069d12  or      eax, edi
0x140069d14  jl      loc_140069E37
0x140069d1a  mov     rcx, [rbp+arg_8]
0x140069d1e  mov     eax, [rcx]
0x140069d20  sub     eax, 7
0x140069d23  cmp     eax, 1
0x140069d26  jbe     loc_140069E30
0x140069d2c  movzx   r8d, word ptr [rcx+8]
0x140069d31  add     r8d, 2
0x140069d35  cmp     dword ptr [rcx+18h], 0
0x140069d39  jl      short loc_140069D56
0x140069d3b  movsxd  rax, dword ptr [rcx+18h]
0x140069d3f  add     r8d, 2
0x140069d43  lea     rdx, [rax+rax*2]
0x140069d47  mov     rax, [rbp+ReferencedDomains]
0x140069d4b  mov     rcx, [rax+8]
0x140069d4f  movzx   eax, word ptr [rcx+rdx*8]
0x140069d53  add     r8d, eax
0x140069d56  mov     ecx, r8d; cb
0x140069d59  mov     r14d, r8d
0x140069d5c  call    cs:__imp_CoTaskMemAlloc
0x140069d62  mov     rdi, rax
0x140069d65  test    rax, rax
0x140069d68  jz      loc_140069E20
0x140069d6e  mov     rax, [rbp+arg_8]
0x140069d72  mov     esi, r14d
0x140069d75  shr     rsi, 1
0x140069d78  cmp     dword ptr [rax+18h], 0
0x140069d7c  jl      short loc_140069DC9
0x140069d7e  test    rsi, rsi
0x140069d81  jz      short loc_140069DC3
0x140069d83  movsxd  rax, dword ptr [rax+18h]
0x140069d87  mov     rdx, rsi; cchDest
0x140069d8a  lea     rcx, [rax+rax*2]
0x140069d8e  mov     rax, [rbp+ReferencedDomains]
0x140069d92  mov     r9, [rax+8]
0x140069d96  movzx   eax, word ptr [r9+rcx*8]
0x140069d9b  mov     r9, [r9+rcx*8+8]; pszSrc
0x140069da0  mov     rcx, rdi; pszDest
0x140069da3  shr     rax, 1
0x140069da6  mov     [rsp+78h+Names], rax; cchToCopy
0x140069dab  call    StringCopyWorkerW_0
0x140069db0  mov     ebx, eax
0x140069db2  test    eax, eax
0x140069db4  js      short loc_140069DC3
0x140069db6  mov     edx, r14d; unsigned __int64
0x140069db9  mov     rcx, rdi; unsigned __int16 *
0x140069dbc  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140069dc1  mov     ebx, eax
0x140069dc3  test    ebx, ebx
0x140069dc5  jns     short loc_140069DCE
0x140069dc7  jmp     short loc_140069E25
0x140069dc9  xor     eax, eax
0x140069dcb  mov     [rdi], ax
0x140069dce  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x140069dd2  mov     [rbp+pcchDestLength], 0
0x140069dda  mov     rdx, rsi; cchDest
0x140069ddd  mov     rcx, rdi; pszDest
0x140069de0  call    StringValidateDestAndLengthW
0x140069de5  mov     ebx, eax
0x140069de7  test    eax, eax
0x140069de9  js      short loc_140069E15
0x140069deb  mov     r9, [rbp+arg_8]
0x140069def  mov     rax, [rbp+pcchDestLength]
0x140069df3  sub     rsi, rax
0x140069df6  mov     rdx, rsi; cchDest
0x140069df9  movzx   r8d, word ptr [r9+8]
0x140069dfe  mov     r9, [r9+10h]; pszSrc
0x140069e02  lea     rcx, [rdi+rax*2]; pszDest
0x140069e06  shr     r8, 1; pcchNewDestLength
0x140069e09  mov     [rsp+78h+Names], r8; cchToCopy
0x140069e0e  call    StringCopyWorkerW_0
0x140069e13  mov     ebx, eax
0x140069e15  test    ebx, ebx
0x140069e17  js      short loc_140069E25
0x140069e19  mov     [r15], rdi
0x140069e1c  xor     edi, edi
0x140069e1e  jmp     short loc_140069E25
0x140069e20  mov     ebx, 8007000Eh
0x140069e25  mov     rcx, rdi; pv
0x140069e28  call    cs:__imp_CoTaskMemFree
0x140069e2e  jmp     short loc_140069E39
0x140069e30  mov     ebx, 80004005h
0x140069e35  jmp     short loc_140069E39
0x140069e37  mov     ebx, eax
0x140069e39  mov     rcx, [rbp+ReferencedDomains]; Buffer
0x140069e3d  call    cs:__imp_LsaFreeMemory
0x140069e43  mov     rcx, [rbp+arg_8]; Buffer
0x140069e47  call    cs:__imp_LsaFreeMemory
0x140069e4d  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x140069e51  call    cs:__imp_LsaClose
0x140069e57  jmp     short loc_140069E5B
0x140069e59  mov     ebx, eax
0x140069e5b  mov     eax, ebx
0x140069e5d  add     rsp, 78h
0x140069e61  pop     r15
0x140069e63  pop     r14
0x140069e65  pop     rdi
0x140069e66  pop     rsi
0x140069e67  pop     rbx
0x140069e68  pop     rbp
0x140069e69  retn
```
