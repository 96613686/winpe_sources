# IsDomainJoined

- ea: `0x18004a940`
- end: `0x18004aa90`
- name: `IsDomainJoined`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004a8e8`

## callees

- `0x18004a940`
- `0x18006c000`
- `0x18008e560`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004a9cf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004aa29`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004aa66`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004a9cf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004aa29`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004aa66`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18004a9a5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18004a9a5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18004a9e9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18004a9e9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004aa19`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004aa56`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004aa19`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004aa56`

## string_xrefs

- `0x18004a9b6`: `onecore\ds\security\umstartup\candidateaccountmanagerpolicy\candidateaccountmanagerpolicy.cpp`
- `0x18004a9fa`: `onecore\ds\security\umstartup\candidateaccountmanagerpolicy\candidateaccountmanagerpolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool IsDomainJoined()
{
  bool v0; // bl
  NTSTATUS v1; // eax
  NTSTATUS v2; // eax
  PVOID v3; // rcx
  PVOID v5; // rcx
  PVOID Buffer; // [rsp+20h] [rbp-60h] BYREF
  PVOID PolicyHandle; // [rsp+28h] [rbp-58h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-50h] BYREF
  _DWORD v9[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v9[2] = 1;
  v9[0] = 12;
  v9[1] = 2;
  v0 = 1;
  memset(&ObjectAttributes, 0, 40);
  ObjectAttributes.SecurityQualityOfService = v9;
  PolicyHandle = 0;
  v1 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v1 < 0 )
  {
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\ds\\security\\umstartup\\candidateaccountmanagerpolicy\\candidateaccountmanagerpolicy.cpp",
      (const char *)(unsigned int)v1,
      (int)Buffer);
    if ( PolicyHandle )
      LsaClose(PolicyHandle);
    return 0;
  }
  Buffer = 0;
  v2 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
  if ( v2 < 0 )
  {
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\ds\\security\\umstartup\\candidateaccountmanagerpolicy\\candidateaccountmanagerpolicy.cpp",
      (const char *)(unsigned int)v2,
      (int)Buffer);
    v3 = Buffer;
    Buffer = 0;
    if ( v3 )
      LsaFreeMemory(v3);
    if ( PolicyHandle )
      LsaClose(PolicyHandle);
    return 0;
  }
  v5 = Buffer;
  if ( !*((_WORD *)Buffer + 8) && !*((_WORD *)Buffer + 16) )
    v0 = *((_QWORD *)Buffer + 8) != 0;
  Buffer = 0;
  if ( v5 )
    LsaFreeMemory(v5);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v0;
}

```

## disassembly

```asm
0x18004a940  mov     [rsp-8+arg_0], rbx
0x18004a945  mov     [rsp-8+arg_8], rdi
0x18004a94a  push    rbp
0x18004a94b  mov     rbp, rsp
0x18004a94e  sub     rsp, 80h
0x18004a955  mov     rax, cs:__security_cookie
0x18004a95c  xor     rax, rsp
0x18004a95f  mov     [rbp+var_10], rax
0x18004a963  xor     edi, edi
0x18004a965  mov     [rbp+var_18], 1
0x18004a96c  mov     [rbp+var_20], 0Ch
0x18004a973  mov     [rbp+var_1C], 2
0x18004a97a  lea     ebx, [rdi+1]
0x18004a97d  xorps   xmm0, xmm0
0x18004a980  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18004a984  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18004a988  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004a98c  lea     rax, [rbp+var_20]
0x18004a990  mov     [rbp+ObjectAttributes.SecurityQualityOfService], rax
0x18004a994  mov     [rbp+PolicyHandle], rdi
0x18004a998  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18004a99c  mov     r8d, ebx; DesiredAccess
0x18004a99f  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18004a9a3  xor     ecx, ecx; SystemName
0x18004a9a5  call    cs:__imp_LsaOpenPolicy
0x18004a9ab  mov     rcx, [rbp+8]; this
0x18004a9af  test    eax, eax
0x18004a9b1  jns     short loc_18004A9D8
0x18004a9b3  mov     r9d, eax; char *
0x18004a9b6  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\umstartup\\candi"...
0x18004a9bd  lea     edx, [rdi+3Bh]; void *
0x18004a9c0  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18004a9c5  nop
0x18004a9c6  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18004a9ca  test    rcx, rcx
0x18004a9cd  jz      short loc_18004AA30
0x18004a9cf  call    cs:__imp_LsaClose
0x18004a9d5  nop
0x18004a9d6  jmp     short loc_18004AA30
0x18004a9d8  mov     [rbp+Buffer], rdi
0x18004a9dc  lea     r8, [rbp+Buffer]; Buffer
0x18004a9e0  mov     edx, 0Ch; InformationClass
0x18004a9e5  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18004a9e9  call    cs:__imp_LsaQueryInformationPolicy
0x18004a9ef  mov     rcx, [rbp+8]; this
0x18004a9f3  test    eax, eax
0x18004a9f5  jns     short loc_18004AA34
0x18004a9f7  mov     r9d, eax; char *
0x18004a9fa  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\umstartup\\candi"...
0x18004aa01  mov     edx, 43h ; 'C'; void *
0x18004aa06  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18004aa0b  nop
0x18004aa0c  mov     rcx, [rbp+Buffer]; Buffer
0x18004aa10  mov     [rbp+Buffer], rdi
0x18004aa14  test    rcx, rcx
0x18004aa17  jz      short loc_18004AA20
0x18004aa19  call    cs:__imp_LsaFreeMemory
0x18004aa1f  nop
0x18004aa20  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18004aa24  test    rcx, rcx
0x18004aa27  jz      short loc_18004AA30
0x18004aa29  call    cs:__imp_LsaClose
0x18004aa2f  nop
0x18004aa30  xor     al, al
0x18004aa32  jmp     short loc_18004AA6F
0x18004aa34  mov     rcx, [rbp+Buffer]; Buffer
0x18004aa38  cmp     [rcx+10h], di
0x18004aa3c  jnz     short loc_18004AA4D
0x18004aa3e  cmp     [rcx+20h], di
0x18004aa42  jnz     short loc_18004AA4D
0x18004aa44  cmp     [rcx+40h], rdi
0x18004aa48  jnz     short loc_18004AA4D
0x18004aa4a  mov     bl, dil
0x18004aa4d  mov     [rbp+Buffer], rdi
0x18004aa51  test    rcx, rcx
0x18004aa54  jz      short loc_18004AA5D
0x18004aa56  call    cs:__imp_LsaFreeMemory
0x18004aa5c  nop
0x18004aa5d  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18004aa61  test    rcx, rcx
0x18004aa64  jz      short loc_18004AA6D
0x18004aa66  call    cs:__imp_LsaClose
0x18004aa6c  nop
0x18004aa6d  mov     al, bl
0x18004aa6f  mov     rcx, [rbp+var_10]
0x18004aa73  xor     rcx, rsp; StackCookie
0x18004aa76  call    __security_check_cookie
0x18004aa7b  lea     r11, [rsp+80h+var_s0]
0x18004aa83  mov     rbx, [r11+10h]
0x18004aa87  mov     rdi, [r11+18h]
0x18004aa8b  mov     rsp, r11
0x18004aa8e  pop     rbp
0x18004aa8f  retn
```
