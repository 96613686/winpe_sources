# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x1800042d0`
- end: `0x180004455`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001024`
- `0x180002fb0`
- `0x1800042d0`
- `0x180004b1c`
- `0x180004c44`
- `0x180005e2c`
- `0x180005fc8`
- `0x180006078`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004322`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004322`
- `iisutil!PuCreateDebugPrintsObject` at `0x180004309`
- `iisutil!PuCreateDebugPrintsObject` at `0x180004309`
- `iisutil!IISGetPlatformType` at `0x18000435a`
- `iisutil!IISGetPlatformType` at `0x18000435a`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000434e`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000434e`

## string_xrefs

- `0x18000431b`: `Unable to Create Debug Print Object \n`
- `0x180004347`: `System\CurrentControlSet\Services\W3SVC\Parameters\digest_auth`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 DebugPrintsObject; // rax
  _QWORD *v6; // rax
  __int64 result; // rax
  int v8; // ebx
  DIGEST_AUTH_PROVIDER *v9; // rax

  s_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  s_pGlobalInfo = a3;
  DebugPrintsObject = PuCreateDebugPrintsObject("Digest_auth", 1);
  g_pDebug = DebugPrintsObject;
  if ( !DebugPrintsObject )
  {
    OutputDebugStringA("Unable to Create Debug Print Object \n");
    DebugPrintsObject = g_pDebug;
    if ( !g_pDebug )
      return 2147500037LL;
  }
  if ( !*(_DWORD *)(DebugPrintsObject + 640) )
    return 2147500037LL;
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\digest_auth", 0);
  IISGetPlatformType();
  v6 = operator new(0x10u);
  if ( v6 )
  {
    *v6 = &CIISModuleFactory::`vftable';
    v6[1] = &CIISHttpModule::`vftable';
    result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
               a2,
               v6,
               134217730,
               0);
    if ( (int)result < 0 )
      return result;
    qword_18000C6A8 = (__int64)&SSPI_CREDENTIAL::sm_CredentialListHead;
    SSPI_CREDENTIAL::sm_CredentialListHead.Flink = &SSPI_CREDENTIAL::sm_CredentialListHead;
    v8 = SSPI_SECURITY_CONTEXT::Initialize();
    if ( v8 < 0 )
    {
      SSPI_CREDENTIAL::Terminate();
      return (unsigned int)v8;
    }
    v8 = DIGEST_CONTEXT_CACHE_ENTRY::Initialize();
    if ( v8 >= 0 )
    {
      v9 = (DIGEST_AUTH_PROVIDER *)operator new(0x20u);
      if ( !v9 )
      {
        s_pDigestAuthProvider = 0;
        DIGEST_CONTEXT_CACHE_ENTRY::Terminate();
        SSPI_CREDENTIAL::Terminate();
        SSPI_SECURITY_CONTEXT::Terminate();
        return (unsigned int)-2147024888;
      }
      s_pDigestAuthProvider = v9;
      *(_QWORD *)v9 = &DIGEST_AUTH_PROVIDER::`vftable';
      v8 = DIGEST_AUTH_PROVIDER::InitializeInstance((DIGEST_AUTH_PROVIDER *)&DIGEST_AUTH_PROVIDER::`vftable');
      if ( v8 >= 0 )
        return (unsigned int)v8;
      DIGEST_CONTEXT_CACHE_ENTRY::Terminate();
    }
    SSPI_CREDENTIAL::Terminate();
    SSPI_SECURITY_CONTEXT::Terminate();
    return (unsigned int)v8;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x1800042d0  mov     [rsp+arg_0], rbx
0x1800042d5  push    rdi
0x1800042d6  sub     rsp, 30h
0x1800042da  mov     rax, [rdx]
0x1800042dd  mov     rcx, rdx
0x1800042e0  mov     rbx, r8
0x1800042e3  mov     rdi, rdx
0x1800042e6  mov     rax, [rax+8]
0x1800042ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ef  mov     edx, 1
0x1800042f4  mov     cs:?s_pModuleContext@@3PEAXEA, rax; void * s_pModuleContext
0x1800042fb  lea     rcx, aDigestAuth; "Digest_auth"
0x180004302  mov     cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * s_pGlobalInfo
0x180004309  call    cs:__imp_PuCreateDebugPrintsObject
0x18000430f  mov     cs:g_pDebug, rax
0x180004316  test    rax, rax
0x180004319  jnz     short loc_180004338
0x18000431b  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180004322  call    cs:__imp_OutputDebugStringA
0x180004328  mov     rax, cs:g_pDebug
0x18000432f  test    rax, rax
0x180004332  jz      loc_180004445
0x180004338  cmp     dword ptr [rax+280h], 0
0x18000433f  jz      loc_180004445
0x180004345  xor     edx, edx
0x180004347  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\W3"...
0x18000434e  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180004354  mov     cs:g_dwDebugFlags, eax
0x18000435a  call    cs:__imp_IISGetPlatformType
0x180004360  mov     ecx, 10h; Size
0x180004365  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000436a  mov     rdx, rax
0x18000436d  test    rax, rax
0x180004370  jz      loc_18000443E
0x180004376  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x18000437d  xor     r9d, r9d
0x180004380  mov     [rdx], rax
0x180004383  mov     r8d, 8000002h
0x180004389  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180004390  mov     [rdx+8], rax
0x180004394  mov     rcx, [rdi]
0x180004397  mov     rax, [rcx+10h]
0x18000439b  mov     rcx, rdi
0x18000439e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a3  test    eax, eax
0x1800043a5  js      loc_18000444A
0x1800043ab  lea     rax, ?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x1800043b2  mov     cs:qword_18000C6A8, rax
0x1800043b9  mov     cs:?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x1800043c0  call    ?Initialize@SSPI_SECURITY_CONTEXT@@SAJXZ; SSPI_SECURITY_CONTEXT::Initialize(void)
0x1800043c5  mov     ebx, eax
0x1800043c7  test    eax, eax
0x1800043c9  jns     short loc_1800043D2
0x1800043cb  call    ?Terminate@SSPI_CREDENTIAL@@SAXXZ; SSPI_CREDENTIAL::Terminate(void)
0x1800043d0  jmp     short loc_18000443A
0x1800043d2  call    ?Initialize@DIGEST_CONTEXT_CACHE_ENTRY@@SAJXZ; DIGEST_CONTEXT_CACHE_ENTRY::Initialize(void)
0x1800043d7  mov     ebx, eax
0x1800043d9  test    eax, eax
0x1800043db  jns     short loc_1800043E9
0x1800043dd  call    ?Terminate@SSPI_CREDENTIAL@@SAXXZ; SSPI_CREDENTIAL::Terminate(void)
0x1800043e2  call    ?Terminate@SSPI_SECURITY_CONTEXT@@SAXXZ; SSPI_SECURITY_CONTEXT::Terminate(void)
0x1800043e7  jmp     short loc_18000443A
0x1800043e9  mov     ecx, 20h ; ' '; Size
0x1800043ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800043f3  test    rax, rax
0x1800043f6  jz      short loc_18000441B
0x1800043f8  lea     rcx, ??_7DIGEST_AUTH_PROVIDER@@6B@; this
0x1800043ff  mov     cs:?s_pDigestAuthProvider@@3PEAVDIGEST_AUTH_PROVIDER@@EA, rax; DIGEST_AUTH_PROVIDER * s_pDigestAuthProvider
0x180004406  mov     [rax], rcx
0x180004409  call    ?InitializeInstance@DIGEST_AUTH_PROVIDER@@QEAAJXZ; DIGEST_AUTH_PROVIDER::InitializeInstance(void)
0x18000440e  mov     ebx, eax
0x180004410  test    eax, eax
0x180004412  jns     short loc_18000443A
0x180004414  call    ?Terminate@DIGEST_CONTEXT_CACHE_ENTRY@@SAXXZ; DIGEST_CONTEXT_CACHE_ENTRY::Terminate(void)
0x180004419  jmp     short loc_1800043DD
0x18000441b  mov     cs:?s_pDigestAuthProvider@@3PEAVDIGEST_AUTH_PROVIDER@@EA, 0; DIGEST_AUTH_PROVIDER * s_pDigestAuthProvider
0x180004426  call    ?Terminate@DIGEST_CONTEXT_CACHE_ENTRY@@SAXXZ; DIGEST_CONTEXT_CACHE_ENTRY::Terminate(void)
0x18000442b  call    ?Terminate@SSPI_CREDENTIAL@@SAXXZ; SSPI_CREDENTIAL::Terminate(void)
0x180004430  call    ?Terminate@SSPI_SECURITY_CONTEXT@@SAXXZ; SSPI_SECURITY_CONTEXT::Terminate(void)
0x180004435  mov     ebx, 80070008h
0x18000443a  mov     eax, ebx
0x18000443c  jmp     short loc_18000444A
0x18000443e  mov     eax, 80070008h
0x180004443  jmp     short loc_18000444A
0x180004445  mov     eax, 80004005h
0x18000444a  mov     rbx, [rsp+38h+arg_0]
0x18000444f  add     rsp, 30h
0x180004453  pop     rdi
0x180004454  retn
```
