# NTUserCapabilityHandler::ProcessBelongsToUser(void *,ushort const *)

- ea: `0x180010c20`
- end: `0x180010d09`
- name: `?ProcessBelongsToUser@NTUserCapabilityHandler@@AEBA_NPEAXPEBG@Z`
- size: `233`
- prototype: `bool __fastcall(NTUserCapabilityHandler *this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800103c0`

## callees

- `0x1800102dc`
- `0x180010c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c61`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010c57`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010ca2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010c57`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010ca2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010cd0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180010cd0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010c78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010c78`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180010cbb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180010cbb`

## pseudocode

```c
bool __fastcall NTUserCapabilityHandler::ProcessBelongsToUser(
        NTUserCapabilityHandler *this,
        void *a2,
        const unsigned __int16 *a3)
{
  bool v5; // bl
  LPVOID v7[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp+20h] BYREF
  int v9; // [rsp+64h] [rbp+24h]
  PSID Sid; // [rsp+78h] [rbp+38h] BYREF

  v9 = HIDWORD(this);
  TokenInformationLength = 0;
  if ( !GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
    return 0;
  v7[0] = LocalAlloc(0x40u, TokenInformationLength);
  if ( !v7[0] || !GetTokenInformation(a2, TokenUser, v7[0], TokenInformationLength, &TokenInformationLength) )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(v7);
    return 0;
  }
  Sid = 0;
  v5 = ConvertStringSidToSidW(a3, &Sid) && EqualSid(Sid, *(PSID *)v7[0]);
  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&Sid);
  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(v7);
  return v5;
}

```

## disassembly

```asm
0x180010c20  mov     [rsp-18h+arg_8], rbx
0x180010c25  mov     qword ptr [rsp-18h+TokenInformationLength], rcx
0x180010c2a  push    rbp
0x180010c2b  push    rsi
0x180010c2c  push    rdi
0x180010c2d  mov     rbp, rsp
0x180010c30  sub     rsp, 40h
0x180010c34  mov     rsi, rdx
0x180010c37  mov     [rbp+TokenInformationLength], 0
0x180010c3e  xor     r9d, r9d; TokenInformationLength
0x180010c41  lea     rax, [rbp+TokenInformationLength]
0x180010c45  mov     rdi, r8
0x180010c48  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180010c4d  xor     r8d, r8d; TokenInformation
0x180010c50  mov     rcx, rsi; TokenHandle
0x180010c53  lea     edx, [r9+1]; TokenInformationClass
0x180010c57  call    cs:__imp_GetTokenInformation
0x180010c5d  test    eax, eax
0x180010c5f  jnz     short loc_180010C70
0x180010c61  call    cs:__imp_GetLastError
0x180010c67  cmp     eax, 7Ah ; 'z'
0x180010c6a  jnz     loc_180010CFA
0x180010c70  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180010c73  mov     ecx, 40h ; '@'; uFlags
0x180010c78  call    cs:__imp_LocalAlloc
0x180010c7e  mov     [rbp+var_10], rax
0x180010c82  mov     rbx, rax
0x180010c85  test    rax, rax
0x180010c88  jz      short loc_180010CF1
0x180010c8a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180010c8e  lea     rax, [rbp+TokenInformationLength]
0x180010c92  mov     r8, rbx; TokenInformation
0x180010c95  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180010c9a  mov     edx, 1; TokenInformationClass
0x180010c9f  mov     rcx, rsi; TokenHandle
0x180010ca2  call    cs:__imp_GetTokenInformation
0x180010ca8  test    eax, eax
0x180010caa  jz      short loc_180010CF1
0x180010cac  lea     rdx, [rbp+Sid]; Sid
0x180010cb0  mov     [rbp+Sid], 0
0x180010cb8  mov     rcx, rdi; StringSid
0x180010cbb  call    cs:__imp_ConvertStringSidToSidW
0x180010cc1  test    eax, eax
0x180010cc3  jnz     short loc_180010CC9
0x180010cc5  xor     ebx, ebx
0x180010cc7  jmp     short loc_180010CDB
0x180010cc9  mov     rdx, [rbx]; pSid2
0x180010ccc  mov     rcx, [rbp+Sid]; pSid1
0x180010cd0  call    cs:__imp_EqualSid
0x180010cd6  test    eax, eax
0x180010cd8  setnz   bl
0x180010cdb  lea     rcx, [rbp+Sid]
0x180010cdf  call    ??1?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x180010ce4  lea     rcx, [rbp+var_10]
0x180010ce8  call    ??1?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x180010ced  mov     al, bl
0x180010cef  jmp     short loc_180010CFC
0x180010cf1  lea     rcx, [rbp+var_10]
0x180010cf5  call    ??1?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x180010cfa  xor     al, al
0x180010cfc  mov     rbx, [rsp+40h+arg_8]
0x180010d01  add     rsp, 40h
0x180010d05  pop     rdi
0x180010d06  pop     rsi
0x180010d07  pop     rbp
0x180010d08  retn
```
