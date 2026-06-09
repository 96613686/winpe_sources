# SystemSettings::WorkAccess::GetUserSidFromToken

- ea: `0x18003ea30`
- end: `0x18003ebd4`
- name: `SystemSettings::WorkAccess::GetUserSidFromToken`
- size: `420`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003e154`

## callees

- `0x1800096cc`
- `0x1800096ec`
- `0x18001bf08`
- `0x1800236d8`
- `0x180024ef8`
- `0x18003ea30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eaa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eaa4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003ea75`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003eb1e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003ea75`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003eb1e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003eb48`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003eb48`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003eb93`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003eb93`

## string_xrefs

- `0x18003ea89`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003eab9`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003eb35`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003eb76`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  unsigned int LastError; // ebx
  void *v5; // rcx
  const char *v6; // r9
  int v8; // eax
  PSID *v9; // rbx
  unsigned int v10; // edi
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 v13; // rdx
  DWORD LengthSid; // esi
  void *v15; // rcx
  PSID v16; // rdi
  int ReturnLength; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  PSID pDestinationSid; // [rsp+70h] [rbp+40h] BYREF
  LPVOID TokenInformation; // [rsp+78h] [rbp+48h] BYREF

  *a2 = 0;
  TokenInformationLength = 0;
  TokenInformation = 0;
  pDestinationSid = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLength);
LABEL_5:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pDestinationSid);
    CTContainer_PolicyLocalMem::DestroyMem(0);
    return LastError;
  }
  if ( GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x63,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
                  v6);
    goto LABEL_5;
  }
  v8 = CTLocalAllocPolicy::Alloc(v5, 0x40u, TokenInformationLength, &TokenInformation);
  v9 = (PSID *)TokenInformation;
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 101;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)(unsigned int)v8,
      ReturnLength);
    goto LABEL_17;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    LengthSid = GetLengthSid(*v9);
    v8 = CTLocalAllocPolicy::Alloc(v15, 0x40u, LengthSid, &pDestinationSid);
    v10 = v8;
    if ( v8 < 0 )
    {
      v11 = 106;
      goto LABEL_13;
    }
    v16 = pDestinationSid;
    if ( CopySid(LengthSid, pDestinationSid, *v9) )
    {
      *a2 = v16;
      v10 = 0;
      pDestinationSid = 0;
      goto LABEL_17;
    }
    v13 = 108;
  }
  else
  {
    v13 = 103;
  }
  v10 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)v13,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
          v12);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pDestinationSid);
  CTContainer_PolicyLocalMem::DestroyMem(v9);
  return v10;
}

```

## disassembly

```asm
0x18003ea30  push    rbp
0x18003ea32  push    rbx
0x18003ea33  push    rsi
0x18003ea34  push    rdi
0x18003ea35  push    r14
0x18003ea37  mov     rbp, rsp
0x18003ea3a  sub     rsp, 30h
0x18003ea3e  xor     r9d, r9d; TokenInformationLength
0x18003ea41  mov     qword ptr [rdx], 0
0x18003ea48  mov     r14, rdx
0x18003ea4b  mov     [rbp+TokenInformationLength], 0
0x18003ea52  lea     rax, [rbp+TokenInformationLength]
0x18003ea56  mov     [rbp+TokenInformation], 0
0x18003ea5e  xor     r8d, r8d; TokenInformation
0x18003ea61  mov     [rbp+pDestinationSid], 0
0x18003ea69  lea     edx, [r9+1]; TokenInformationClass
0x18003ea6d  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x18003ea72  mov     rsi, rcx
0x18003ea75  call    cs:__imp_GetTokenInformation
0x18003ea7c  nop     dword ptr [rax+rax+00h]
0x18003ea81  test    eax, eax
0x18003ea83  jz      short loc_18003EAA4
0x18003ea85  mov     rcx, [rbp+28h]; this
0x18003ea89  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003ea90  mov     ebx, 8000FFFFh
0x18003ea95  mov     edx, 61h ; 'a'; void *
0x18003ea9a  mov     r9d, ebx; char *
0x18003ea9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eaa2  jmp     short loc_18003EACC
0x18003eaa4  call    cs:__imp_GetLastError
0x18003eaab  nop     dword ptr [rax+rax+00h]
0x18003eab0  cmp     eax, 7Ah ; 'z'
0x18003eab3  jz      short loc_18003EAE3
0x18003eab5  mov     rcx, [rbp+28h]; this
0x18003eab9  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003eac0  mov     edx, 63h ; 'c'; void *
0x18003eac5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003eaca  mov     ebx, eax
0x18003eacc  lea     rcx, [rbp+pDestinationSid]
0x18003ead0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ead5  xor     ecx, ecx; void *
0x18003ead7  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x18003eadc  mov     eax, ebx
0x18003eade  jmp     loc_18003EBC8
0x18003eae3  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18003eae7  lea     r9, [rbp+TokenInformation]; void **
0x18003eaeb  mov     edx, 40h ; '@'; unsigned int
0x18003eaf0  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003eaf5  mov     rbx, [rbp+TokenInformation]
0x18003eaf9  mov     edi, eax
0x18003eafb  test    eax, eax
0x18003eafd  jns     short loc_18003EB06
0x18003eaff  mov     edx, 65h ; 'e'
0x18003eb04  jmp     short loc_18003EB72
0x18003eb06  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003eb0a  lea     rax, [rbp+TokenInformationLength]
0x18003eb0e  mov     r8, rbx; TokenInformation
0x18003eb11  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x18003eb16  mov     edx, 1; TokenInformationClass
0x18003eb1b  mov     rcx, rsi; TokenHandle
0x18003eb1e  call    cs:__imp_GetTokenInformation
0x18003eb25  nop     dword ptr [rax+rax+00h]
0x18003eb2a  test    eax, eax
0x18003eb2c  jnz     short loc_18003EB45
0x18003eb2e  lea     edx, [rax+67h]; void *
0x18003eb31  mov     rcx, [rbp+28h]; this
0x18003eb35  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003eb3c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003eb41  mov     edi, eax
0x18003eb43  jmp     short loc_18003EBB5
0x18003eb45  mov     rcx, [rbx]; pSid
0x18003eb48  call    cs:__imp_GetLengthSid
0x18003eb4f  nop     dword ptr [rax+rax+00h]
0x18003eb54  mov     r8d, eax; unsigned __int64
0x18003eb57  lea     r9, [rbp+pDestinationSid]; void **
0x18003eb5b  mov     edx, 40h ; '@'; unsigned int
0x18003eb60  mov     esi, eax
0x18003eb62  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003eb67  mov     edi, eax
0x18003eb69  test    eax, eax
0x18003eb6b  jns     short loc_18003EB87
0x18003eb6d  mov     edx, 6Ah ; 'j'; void *
0x18003eb72  mov     rcx, [rbp+28h]; this
0x18003eb76  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003eb7d  mov     r9d, eax; char *
0x18003eb80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eb85  jmp     short loc_18003EBB5
0x18003eb87  mov     rdi, [rbp+pDestinationSid]
0x18003eb8b  mov     ecx, esi; nDestinationSidLength
0x18003eb8d  mov     r8, [rbx]; pSourceSid
0x18003eb90  mov     rdx, rdi; pDestinationSid
0x18003eb93  call    cs:__imp_CopySid
0x18003eb9a  nop     dword ptr [rax+rax+00h]
0x18003eb9f  test    eax, eax
0x18003eba1  jnz     short loc_18003EBA8
0x18003eba3  lea     edx, [rax+6Ch]
0x18003eba6  jmp     short loc_18003EB31
0x18003eba8  mov     [r14], rdi
0x18003ebab  xor     edi, edi
0x18003ebad  mov     [rbp+pDestinationSid], 0
0x18003ebb5  lea     rcx, [rbp+pDestinationSid]
0x18003ebb9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ebbe  mov     rcx, rbx; void *
0x18003ebc1  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x18003ebc6  mov     eax, edi
0x18003ebc8  add     rsp, 30h
0x18003ebcc  pop     r14
0x18003ebce  pop     rdi
0x18003ebcf  pop     rsi
0x18003ebd0  pop     rbx
0x18003ebd1  pop     rbp
0x18003ebd2  retn
```
