# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180005be0`
- end: `0x180005dbe`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001024`
- `0x180001064`
- `0x180005be0`
- `0x18000839c`
- `0x180008538`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005c32`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005c32`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180005d8e`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180005d8e`
- `iisutil!PuCreateDebugPrintsObject` at `0x180005c19`
- `iisutil!PuCreateDebugPrintsObject` at `0x180005c19`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180005c5e`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180005c5e`
- `iisutil!IISGetPlatformType` at `0x180005c6a`
- `iisutil!IISGetPlatformType` at `0x180005c6a`
- `wkscli!NetGetJoinInformation` at `0x180005d44`
- `wkscli!NetGetJoinInformation` at `0x180005d44`
- `netutils!NetApiBufferFree` at `0x180005d63`
- `netutils!NetApiBufferFree` at `0x180005d63`

## string_xrefs

- `0x180005c2b`: `Unable to Create Debug Print Object \n`
- `0x180005c57`: `System\CurrentControlSet\Services\W3SVC\Parameters\sspi_auth`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 DebugPrintsObject; // rax
  _QWORD *v6; // rax
  __int64 result; // rax
  int v8; // ebx
  _DWORD *v9; // rax
  _DWORD *v10; // rbx
  void *v11; // rbx
  _NETSETUP_JOIN_STATUS BufferType; // [rsp+48h] [rbp+10h] BYREF
  LPWSTR NameBuffer; // [rsp+50h] [rbp+18h] BYREF

  s_ModuleId = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  s_pGlobalInfo = a3;
  DebugPrintsObject = PuCreateDebugPrintsObject("sspi_auth", 1);
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
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\sspi_auth", 0);
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
    qword_18000E688 = (__int64)&SSPI_CREDENTIAL::sm_CredentialListHead;
    SSPI_CREDENTIAL::sm_CredentialListHead.Flink = &SSPI_CREDENTIAL::sm_CredentialListHead;
    v8 = SSPI_SECURITY_CONTEXT::Initialize();
    if ( v8 < 0 )
    {
      SSPI_CREDENTIAL::Terminate();
      return (unsigned int)v8;
    }
    v9 = operator new(0x18u);
    v10 = v9;
    if ( v9 )
    {
      v9[4] = 1;
      *(_QWORD *)v9 = &SSPI_AUTH_PROVIDER::`vftable';
      v9[5] = 1;
      s_pSSPIAuthProvider = v9;
      ((void (__fastcall *)(_DWORD *, __int64))AUTH_PROVIDER::SetTracingAuthType)(v9, 4);
      BufferType = NetSetupUnknownStatus;
      NameBuffer = 0;
      if ( !NetGetJoinInformation(0, &NameBuffer, &BufferType) )
        v10[5] = BufferType == NetSetupDomainName;
      if ( NameBuffer )
        NetApiBufferFree(NameBuffer);
      return 0;
    }
    s_pSSPIAuthProvider = 0;
    SSPI_CREDENTIAL::Terminate();
    v11 = SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext;
    if ( SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext )
    {
      ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext);
      operator delete(v11);
    }
    SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext = 0;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180005be0  mov     [rsp+arg_0], rbx
0x180005be5  push    rdi
0x180005be6  sub     rsp, 30h
0x180005bea  mov     rax, [rdx]
0x180005bed  mov     rcx, rdx
0x180005bf0  mov     rbx, r8
0x180005bf3  mov     rdi, rdx
0x180005bf6  mov     rax, [rax+8]
0x180005bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bff  mov     edx, 1
0x180005c04  mov     cs:?s_ModuleId@@3PEAXEA, rax; void * s_ModuleId
0x180005c0b  lea     rcx, aSspiAuth; "sspi_auth"
0x180005c12  mov     cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * s_pGlobalInfo
0x180005c19  call    cs:__imp_PuCreateDebugPrintsObject
0x180005c1f  mov     cs:g_pDebug, rax
0x180005c26  test    rax, rax
0x180005c29  jnz     short loc_180005C48
0x180005c2b  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180005c32  call    cs:__imp_OutputDebugStringA
0x180005c38  mov     rax, cs:g_pDebug
0x180005c3f  test    rax, rax
0x180005c42  jz      loc_180005DAE
0x180005c48  cmp     dword ptr [rax+280h], 0
0x180005c4f  jz      loc_180005DAE
0x180005c55  xor     edx, edx
0x180005c57  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180005c5e  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180005c64  mov     cs:g_dwDebugFlags, eax
0x180005c6a  call    cs:__imp_IISGetPlatformType
0x180005c70  mov     ecx, 10h; Size
0x180005c75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c7a  mov     rdx, rax
0x180005c7d  test    rax, rax
0x180005c80  jz      loc_180005DA7
0x180005c86  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x180005c8d  xor     r9d, r9d
0x180005c90  mov     [rdx], rax
0x180005c93  mov     r8d, 8000002h
0x180005c99  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180005ca0  mov     [rdx+8], rax
0x180005ca4  mov     rcx, [rdi]
0x180005ca7  mov     rax, [rcx+10h]
0x180005cab  mov     rcx, rdi
0x180005cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cb3  test    eax, eax
0x180005cb5  js      loc_180005DB3
0x180005cbb  lea     rax, ?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180005cc2  mov     cs:qword_18000E688, rax
0x180005cc9  mov     cs:?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180005cd0  call    ?Initialize@SSPI_SECURITY_CONTEXT@@SAJXZ; SSPI_SECURITY_CONTEXT::Initialize(void)
0x180005cd5  mov     ebx, eax
0x180005cd7  test    eax, eax
0x180005cd9  jns     short loc_180005CE5
0x180005cdb  call    ?Terminate@SSPI_CREDENTIAL@@SAXXZ; SSPI_CREDENTIAL::Terminate(void)
0x180005ce0  jmp     loc_180005D6B
0x180005ce5  mov     ecx, 18h; Size
0x180005cea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005cef  mov     rbx, rax
0x180005cf2  test    rax, rax
0x180005cf5  jz      short loc_180005D6F
0x180005cf7  lea     rax, ??_7SSPI_AUTH_PROVIDER@@6B@; const SSPI_AUTH_PROVIDER::`vftable'
0x180005cfe  mov     dword ptr [rbx+10h], 1
0x180005d05  mov     [rbx], rax
0x180005d08  mov     edx, 4
0x180005d0d  mov     rax, [rax+40h]
0x180005d11  mov     rcx, rbx
0x180005d14  mov     dword ptr [rbx+14h], 1
0x180005d1b  mov     cs:?s_pSSPIAuthProvider@@3PEAVSSPI_AUTH_PROVIDER@@EA, rbx; SSPI_AUTH_PROVIDER * s_pSSPIAuthProvider
0x180005d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d27  lea     r8, [rsp+38h+BufferType]; BufferType
0x180005d2c  mov     [rsp+38h+BufferType], 0
0x180005d34  lea     rdx, [rsp+38h+NameBuffer]; lpNameBuffer
0x180005d39  mov     [rsp+38h+NameBuffer], 0
0x180005d42  xor     ecx, ecx; lpServer
0x180005d44  call    cs:__imp_NetGetJoinInformation
0x180005d4a  test    eax, eax
0x180005d4c  jnz     short loc_180005D59
0x180005d4e  cmp     [rsp+38h+BufferType], 3
0x180005d53  setz    al
0x180005d56  mov     [rbx+14h], eax
0x180005d59  mov     rcx, [rsp+38h+NameBuffer]; Buffer
0x180005d5e  test    rcx, rcx
0x180005d61  jz      short loc_180005D69
0x180005d63  call    cs:__imp_NetApiBufferFree
0x180005d69  xor     ebx, ebx
0x180005d6b  mov     eax, ebx
0x180005d6d  jmp     short loc_180005DB3
0x180005d6f  mov     cs:?s_pSSPIAuthProvider@@3PEAVSSPI_AUTH_PROVIDER@@EA, 0; SSPI_AUTH_PROVIDER * s_pSSPIAuthProvider
0x180005d7a  call    ?Terminate@SSPI_CREDENTIAL@@SAXXZ; SSPI_CREDENTIAL::Terminate(void)
0x180005d7f  mov     rbx, cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180005d86  test    rbx, rbx
0x180005d89  jz      short loc_180005D9C
0x180005d8b  mov     rcx, rbx
0x180005d8e  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180005d94  mov     rcx, rbx; Block
0x180005d97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005d9c  mov     cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180005da7  mov     eax, 80070008h
0x180005dac  jmp     short loc_180005DB3
0x180005dae  mov     eax, 80004005h
0x180005db3  mov     rbx, [rsp+38h+arg_0]
0x180005db8  add     rsp, 30h
0x180005dbc  pop     rdi
0x180005dbd  retn
```
