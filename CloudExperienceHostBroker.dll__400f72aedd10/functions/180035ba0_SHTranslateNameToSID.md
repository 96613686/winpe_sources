# SHTranslateNameToSID

- ea: `0x180035ba0`
- end: `0x180035cf6`
- name: `SHTranslateNameToSID`
- size: `342`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d318`

## callees

- `0x180035768`
- `0x180035ba0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180035c23`
- `ntdll!RtlInitUnicodeString` at `0x180035c23`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x180035c4e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x180035c4e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180035cde`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180035cde`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180035bf1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180035bf1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180035cca`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180035cd4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180035cca`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180035cd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035cb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035cb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035c7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035c7a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180035c95`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180035c95`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035c70`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035c70`

## pseudocode

```c
__int64 __fastcall SHTranslateNameToSID(PCWSTR SourceString, _QWORD *a2)
{
  unsigned int Error; // ebx
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  DWORD LengthSid; // ebx
  void *v8; // rax
  void *v9; // rdi
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PLSA_TRANSLATED_SID2 Sids; // [rsp+90h] [rbp+20h] BYREF
  PVOID PolicyHandle; // [rsp+98h] [rbp+28h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+A0h] [rbp+30h] BYREF

  *a2 = 0;
  Error = -2147024809;
  if ( SourceString )
  {
    PolicyHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v5 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
    Error = v5 | 0x10000000;
    if ( v5 >= 0 )
    {
      ReferencedDomains = 0;
      Sids = 0;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      v6 = LsaLookupNames2(
             PolicyHandle,
             0x80000000,
             1u,
             (PLSA_UNICODE_STRING)&DestinationString,
             &ReferencedDomains,
             &Sids);
      Error = v6 | 0x10000000;
      if ( v6 >= 0 )
      {
        if ( (unsigned int)(Sids->Use - 7) <= 1 )
        {
          Error = -2147467259;
        }
        else
        {
          LengthSid = GetLengthSid(Sids->Sid);
          v8 = CoTaskMemAlloc(LengthSid);
          v9 = v8;
          if ( v8 )
          {
            if ( CopySid(LengthSid, v8, Sids->Sid) )
            {
              *a2 = v9;
              v9 = 0;
              Error = 0;
            }
            else
            {
              Error = ResultFromKnownLastError();
            }
            CoTaskMemFree(v9);
          }
          else
          {
            Error = -2147024882;
          }
        }
      }
      LsaFreeMemory(ReferencedDomains);
      LsaFreeMemory(Sids);
      LsaClose(PolicyHandle);
    }
  }
  return Error;
}

```

## disassembly

```asm
0x180035ba0  mov     [rsp-18h+arg_18], rbx
0x180035ba5  push    rbp
0x180035ba6  push    rsi
0x180035ba7  push    rdi
0x180035ba8  mov     rbp, rsp
0x180035bab  sub     rsp, 70h
0x180035baf  mov     qword ptr [rdx], 0
0x180035bb6  mov     rsi, rdx
0x180035bb9  mov     rdi, rcx
0x180035bbc  mov     ebx, 80070057h
0x180035bc1  test    rcx, rcx
0x180035bc4  jz      loc_180035CE4
0x180035bca  xorps   xmm0, xmm0
0x180035bcd  mov     [rbp+PolicyHandle], 0
0x180035bd5  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180035bd9  mov     r8d, 800h; DesiredAccess
0x180035bdf  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180035be3  xor     ecx, ecx; SystemName
0x180035be5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180035be9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180035bed  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180035bf1  call    cs:__imp_LsaOpenPolicy
0x180035bf7  mov     ebx, eax
0x180035bf9  or      ebx, 10000000h
0x180035bff  jl      loc_180035CE4
0x180035c05  xorps   xmm0, xmm0
0x180035c08  mov     [rbp+arg_10], 0
0x180035c10  mov     rdx, rdi; SourceString
0x180035c13  mov     [rbp+arg_0], 0
0x180035c1b  lea     rcx, [rbp+DestinationString]; DestinationString
0x180035c1f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180035c23  call    cs:__imp_RtlInitUnicodeString
0x180035c29  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180035c2d  lea     rax, [rbp+arg_0]
0x180035c31  mov     [rsp+70h+Sids], rax; Sids
0x180035c36  lea     r9, [rbp+DestinationString]; Names
0x180035c3a  lea     rax, [rbp+arg_10]
0x180035c3e  mov     edx, 80000000h; Flags
0x180035c43  mov     r8d, 1; Count
0x180035c49  mov     [rsp+70h+ReferencedDomains], rax; ReferencedDomains
0x180035c4e  call    cs:__imp_LsaLookupNames2
0x180035c54  mov     ebx, eax
0x180035c56  or      ebx, 10000000h
0x180035c5c  jl      short loc_180035CC6
0x180035c5e  mov     rcx, [rbp+arg_0]
0x180035c62  mov     eax, [rcx]
0x180035c64  sub     eax, 7
0x180035c67  cmp     eax, 1
0x180035c6a  jbe     short loc_180035CC1
0x180035c6c  mov     rcx, [rcx+8]; pSid
0x180035c70  call    cs:__imp_GetLengthSid
0x180035c76  mov     ecx, eax; cb
0x180035c78  mov     ebx, eax
0x180035c7a  call    cs:__imp_CoTaskMemAlloc
0x180035c80  mov     rdi, rax
0x180035c83  test    rax, rax
0x180035c86  jz      short loc_180035CBA
0x180035c88  mov     r8, [rbp+arg_0]
0x180035c8c  mov     rdx, rax; pDestinationSid
0x180035c8f  mov     ecx, ebx; nDestinationSidLength
0x180035c91  mov     r8, [r8+8]; pSourceSid
0x180035c95  call    cs:__imp_CopySid
0x180035c9b  test    eax, eax
0x180035c9d  jz      short loc_180035CA8
0x180035c9f  mov     [rsi], rdi
0x180035ca2  xor     edi, edi
0x180035ca4  xor     ebx, ebx
0x180035ca6  jmp     short loc_180035CAF
0x180035ca8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180035cad  mov     ebx, eax
0x180035caf  mov     rcx, rdi; pv
0x180035cb2  call    cs:__imp_CoTaskMemFree
0x180035cb8  jmp     short loc_180035CC6
0x180035cba  mov     ebx, 8007000Eh
0x180035cbf  jmp     short loc_180035CC6
0x180035cc1  mov     ebx, 80004005h
0x180035cc6  mov     rcx, [rbp+arg_10]; Buffer
0x180035cca  call    cs:__imp_LsaFreeMemory
0x180035cd0  mov     rcx, [rbp+arg_0]; Buffer
0x180035cd4  call    cs:__imp_LsaFreeMemory
0x180035cda  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180035cde  call    cs:__imp_LsaClose
0x180035ce4  mov     eax, ebx
0x180035ce6  mov     rbx, [rsp+70h+arg_18]
0x180035cee  add     rsp, 70h
0x180035cf2  pop     rdi
0x180035cf3  pop     rsi
0x180035cf4  pop     rbp
0x180035cf5  retn
```
