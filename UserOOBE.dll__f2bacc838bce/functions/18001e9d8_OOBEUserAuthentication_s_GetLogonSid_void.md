# OOBEUserAuthentication::s_GetLogonSid(void)

- ea: `0x18001e9d8`
- end: `0x18001eb28`
- name: `?s_GetLogonSid@OOBEUserAuthentication@@CAPEAXXZ`
- size: `336`
- prototype: `static void *(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dcc0`

## callees

- `0x18000a5e8`
- `0x18000e2a0`
- `0x18000e2bc`
- `0x18001d73c`
- `0x18001db6c`
- `0x18001e9d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001eb14`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001eb14`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001e9e2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001e9e2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001ead4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001ead4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ea86`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ea86`

## string_xrefs

- `0x18001e9f4`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001ea2a`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001ea71`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001eab5`: `shell\oobe\user\dll\oobeuserauthentication.cpp`
- `0x18001eae3`: `shell\oobe\user\dll\oobeuserauthentication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PSID OOBEUserAuthentication::s_GetLogonSid(void)
{
  HRESULT v0; // eax
  __int64 v1; // rdx
  __int64 v2; // r8
  int v3; // eax
  void *v4; // rbx
  unsigned int i; // ecx
  DWORD LengthSid; // edi
  void *v7; // rcx
  int v8; // eax
  void *v9; // r8
  PSID v10; // rbx
  const char *v11; // r9
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSID pDestinationSid; // [rsp+38h] [rbp+10h] BYREF
  unsigned int *v16; // [rsp+40h] [rbp+18h] BYREF

  v0 = CoImpersonateClient();
  if ( v0 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
      (const char *)(unsigned int)v0,
      v13);
  v16 = 0;
  v3 = SHQueryToken<_TOKEN_GROUPS>(retaddr, v1, v2, &v16);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
      (const char *)(unsigned int)v3,
      v13);
  v4 = 0;
  for ( i = 0; i < *v16; ++i )
  {
    if ( (v16[4 * i + 4] & 0xC0000000) != 0 )
    {
      v4 = *(void **)&v16[4 * i + 2];
      break;
    }
  }
  if ( !v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
      (const char *)0x8000FFFFLL,
      v13);
  LengthSid = GetLengthSid(v4);
  pDestinationSid = 0;
  v8 = CTLocalAllocPolicy::Alloc(v7, 0x40u, LengthSid, &pDestinationSid);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x110,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
      (const char *)(unsigned int)v8,
      v13);
  v9 = v4;
  v10 = pDestinationSid;
  if ( !CopySid(LengthSid, pDestinationSid, v9) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x111,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserauthentication.cpp",
      v11);
  pDestinationSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&pDestinationSid);
  wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&v16);
  CoRevertToSelf();
  return v10;
}

```

## disassembly

```asm
0x18001e9d8  mov     [rsp+arg_18], rbx
0x18001e9dd  push    rdi; int
0x18001e9de  sub     rsp, 20h
0x18001e9e2  call    cs:__imp_CoImpersonateClient
0x18001e9e8  mov     rcx, [rsp+28h]; this
0x18001e9ed  test    eax, eax
0x18001e9ef  jns     short loc_18001EA06
0x18001e9f1  mov     r9d, eax; char *
0x18001e9f4  lea     r8, aShellOobeUserD_5; "shell\\oobe\\user\\dll\\oobeuserauthent"...
0x18001e9fb  mov     edx, 0F8h; void *
0x18001ea00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ea06  mov     [rsp+28h+arg_1], 1
0x18001ea0b  mov     [rsp+28h+arg_10], 0
0x18001ea14  lea     r9, [rsp+28h+arg_10]
0x18001ea19  call    ??$SHQueryToken@U_TOKEN_GROUPS@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_GROUPS@@@Z; SHQueryToken<_TOKEN_GROUPS>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_GROUPS * *)
0x18001ea1e  mov     rcx, [rsp+28h]; this
0x18001ea23  test    eax, eax
0x18001ea25  jns     short loc_18001EA3C
0x18001ea27  mov     r9d, eax; char *
0x18001ea2a  lea     r8, aShellOobeUserD_5; "shell\\oobe\\user\\dll\\oobeuserauthent"...
0x18001ea31  mov     edx, 100h; void *
0x18001ea36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ea3c  xor     ebx, ebx
0x18001ea3e  mov     rax, [rsp+28h+arg_10]
0x18001ea43  xor     ecx, ecx
0x18001ea45  cmp     ecx, [rax]
0x18001ea47  jnb     short loc_18001EA61
0x18001ea49  mov     edx, ecx
0x18001ea4b  add     rdx, rdx
0x18001ea4e  test    dword ptr [rax+rdx*8+10h], 0C0000000h
0x18001ea56  jnz     short loc_18001EA5C
0x18001ea58  inc     ecx
0x18001ea5a  jmp     short loc_18001EA45
0x18001ea5c  mov     rbx, [rax+rdx*8+8]
0x18001ea61  mov     rcx, [rsp+28h]; this
0x18001ea66  test    rbx, rbx
0x18001ea69  jnz     short loc_18001EA83
0x18001ea6b  mov     r9d, 8000FFFFh; char *
0x18001ea71  lea     r8, aShellOobeUserD_5; "shell\\oobe\\user\\dll\\oobeuserauthent"...
0x18001ea78  mov     edx, 10Bh; void *
0x18001ea7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ea83  mov     rcx, rbx; pSid
0x18001ea86  call    cs:__imp_GetLengthSid
0x18001ea8c  mov     edi, eax
0x18001ea8e  mov     [rsp+28h+pDestinationSid], 0
0x18001ea97  mov     r8d, eax; unsigned __int64
0x18001ea9a  lea     r9, [rsp+28h+pDestinationSid]; void **
0x18001ea9f  mov     edx, 40h ; '@'; unsigned int
0x18001eaa4  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001eaa9  mov     rcx, [rsp+28h]; this
0x18001eaae  test    eax, eax
0x18001eab0  jns     short loc_18001EAC7
0x18001eab2  mov     r9d, eax; char *
0x18001eab5  lea     r8, aShellOobeUserD_5; "shell\\oobe\\user\\dll\\oobeuserauthent"...
0x18001eabc  mov     edx, 110h; void *
0x18001eac1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eac7  mov     r8, rbx; pSourceSid
0x18001eaca  mov     rbx, [rsp+28h+pDestinationSid]
0x18001eacf  mov     rdx, rbx; pDestinationSid
0x18001ead2  mov     ecx, edi; nDestinationSidLength
0x18001ead4  call    cs:__imp_CopySid
0x18001eada  mov     rcx, [rsp+28h]; this
0x18001eadf  test    eax, eax
0x18001eae1  jnz     short loc_18001EAF5
0x18001eae3  lea     r8, aShellOobeUserD_5; "shell\\oobe\\user\\dll\\oobeuserauthent"...
0x18001eaea  mov     edx, 111h; void *
0x18001eaef  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001eaf5  mov     [rsp+28h+pDestinationSid], 0
0x18001eafe  lea     rcx, [rsp+28h+pDestinationSid]
0x18001eb03  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18001eb08  nop
0x18001eb09  lea     rcx, [rsp+28h+arg_10]
0x18001eb0e  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18001eb13  nop
0x18001eb14  call    cs:__imp_CoRevertToSelf
0x18001eb1a  mov     rax, rbx
0x18001eb1d  mov     rbx, [rsp+28h+arg_18]
0x18001eb22  add     rsp, 20h
0x18001eb26  pop     rdi
0x18001eb27  retn
```
