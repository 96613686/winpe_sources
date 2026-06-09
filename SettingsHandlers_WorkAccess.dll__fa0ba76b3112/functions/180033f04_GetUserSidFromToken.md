# GetUserSidFromToken

- ea: `0x180033f04`
- end: `0x1800340ac`
- name: `GetUserSidFromToken`
- size: `424`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032cb4`

## callees

- `0x1800096cc`
- `0x1800096ec`
- `0x18001bf08`
- `0x1800236d8`
- `0x180024ef8`
- `0x180033f04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f78`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180033f49`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180033ff2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180033f49`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180033ff2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003401e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003401e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180034069`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180034069`

## string_xrefs

- `0x180033f5d`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180033f8d`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x18003400b`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x18003404c`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
__int64 __fastcall GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
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
      (void *)0x7D,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
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
                  (void *)0x7F,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
                  v6);
    goto LABEL_5;
  }
  v8 = CTLocalAllocPolicy::Alloc(v5, 0x40u, TokenInformationLength, &TokenInformation);
  v9 = (PSID *)TokenInformation;
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 129;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
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
      v11 = 134;
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
    v13 = 136;
  }
  else
  {
    v13 = 131;
  }
  v10 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)v13,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
          v12);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pDestinationSid);
  CTContainer_PolicyLocalMem::DestroyMem(v9);
  return v10;
}

```

## disassembly

```asm
0x180033f04  push    rbp
0x180033f06  push    rbx
0x180033f07  push    rsi
0x180033f08  push    rdi
0x180033f09  push    r14
0x180033f0b  mov     rbp, rsp
0x180033f0e  sub     rsp, 30h
0x180033f12  xor     r9d, r9d; TokenInformationLength
0x180033f15  mov     qword ptr [rdx], 0
0x180033f1c  mov     r14, rdx
0x180033f1f  mov     [rbp+TokenInformationLength], 0
0x180033f26  lea     rax, [rbp+TokenInformationLength]
0x180033f2a  mov     [rbp+TokenInformation], 0
0x180033f32  xor     r8d, r8d; TokenInformation
0x180033f35  mov     [rbp+pDestinationSid], 0
0x180033f3d  lea     edx, [r9+1]; TokenInformationClass
0x180033f41  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x180033f46  mov     rsi, rcx
0x180033f49  call    cs:__imp_GetTokenInformation
0x180033f50  nop     dword ptr [rax+rax+00h]
0x180033f55  test    eax, eax
0x180033f57  jz      short loc_180033F78
0x180033f59  mov     rcx, [rbp+28h]; this
0x180033f5d  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180033f64  mov     ebx, 8000FFFFh
0x180033f69  mov     edx, 7Dh ; '}'; void *
0x180033f6e  mov     r9d, ebx; char *
0x180033f71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f76  jmp     short loc_180033FA0
0x180033f78  call    cs:__imp_GetLastError
0x180033f7f  nop     dword ptr [rax+rax+00h]
0x180033f84  cmp     eax, 7Ah ; 'z'
0x180033f87  jz      short loc_180033FB7
0x180033f89  mov     rcx, [rbp+28h]; this
0x180033f8d  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180033f94  mov     edx, 7Fh; void *
0x180033f99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033f9e  mov     ebx, eax
0x180033fa0  lea     rcx, [rbp+pDestinationSid]
0x180033fa4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180033fa9  xor     ecx, ecx; void *
0x180033fab  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180033fb0  mov     eax, ebx
0x180033fb2  jmp     loc_1800340A0
0x180033fb7  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x180033fbb  lea     r9, [rbp+TokenInformation]; void **
0x180033fbf  mov     edx, 40h ; '@'; unsigned int
0x180033fc4  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180033fc9  mov     rbx, [rbp+TokenInformation]
0x180033fcd  mov     edi, eax
0x180033fcf  test    eax, eax
0x180033fd1  jns     short loc_180033FDA
0x180033fd3  mov     edx, 81h
0x180033fd8  jmp     short loc_180034048
0x180033fda  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180033fde  lea     rax, [rbp+TokenInformationLength]
0x180033fe2  mov     r8, rbx; TokenInformation
0x180033fe5  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x180033fea  mov     edx, 1; TokenInformationClass
0x180033fef  mov     rcx, rsi; TokenHandle
0x180033ff2  call    cs:__imp_GetTokenInformation
0x180033ff9  nop     dword ptr [rax+rax+00h]
0x180033ffe  test    eax, eax
0x180034000  jnz     short loc_18003401B
0x180034002  mov     edx, 83h; void *
0x180034007  mov     rcx, [rbp+28h]; this
0x18003400b  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180034012  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034017  mov     edi, eax
0x180034019  jmp     short loc_18003408D
0x18003401b  mov     rcx, [rbx]; pSid
0x18003401e  call    cs:__imp_GetLengthSid
0x180034025  nop     dword ptr [rax+rax+00h]
0x18003402a  mov     r8d, eax; unsigned __int64
0x18003402d  lea     r9, [rbp+pDestinationSid]; void **
0x180034031  mov     edx, 40h ; '@'; unsigned int
0x180034036  mov     esi, eax
0x180034038  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003403d  mov     edi, eax
0x18003403f  test    eax, eax
0x180034041  jns     short loc_18003405D
0x180034043  mov     edx, 86h; void *
0x180034048  mov     rcx, [rbp+28h]; this
0x18003404c  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180034053  mov     r9d, eax; char *
0x180034056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003405b  jmp     short loc_18003408D
0x18003405d  mov     rdi, [rbp+pDestinationSid]
0x180034061  mov     ecx, esi; nDestinationSidLength
0x180034063  mov     r8, [rbx]; pSourceSid
0x180034066  mov     rdx, rdi; pDestinationSid
0x180034069  call    cs:__imp_CopySid
0x180034070  nop     dword ptr [rax+rax+00h]
0x180034075  test    eax, eax
0x180034077  jnz     short loc_180034080
0x180034079  mov     edx, 88h
0x18003407e  jmp     short loc_180034007
0x180034080  mov     [r14], rdi
0x180034083  xor     edi, edi
0x180034085  mov     [rbp+pDestinationSid], 0
0x18003408d  lea     rcx, [rbp+pDestinationSid]
0x180034091  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034096  mov     rcx, rbx; void *
0x180034099  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x18003409e  mov     eax, edi
0x1800340a0  add     rsp, 30h
0x1800340a4  pop     r14
0x1800340a6  pop     rdi
0x1800340a7  pop     rsi
0x1800340a8  pop     rbx
0x1800340a9  pop     rbp
0x1800340aa  retn
```
