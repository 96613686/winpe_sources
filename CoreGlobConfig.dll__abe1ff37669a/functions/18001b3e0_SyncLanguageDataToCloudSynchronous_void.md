# SyncLanguageDataToCloudSynchronous(void)

- ea: `0x18001b3e0`
- end: `0x18001b4dd`
- name: `?SyncLanguageDataToCloudSynchronous@@YAJXZ`
- size: `253`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002380`
- `0x180006c38`
- `0x180008294`
- `0x18000c0f4`
- `0x180011ba4`
- `0x180019f30`
- `0x18001b34c`
- `0x18001b3e0`
- `0x18001b54c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b47d`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001b473`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001b473`

## string_xrefs

- `0x18001b492`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001b429`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 SyncLanguageDataToCloudSynchronous(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  const char *v3; // r9
  int Address; // [rsp+20h] [rbp-178h] BYREF
  _DWORD CompareAddress[3]; // [rsp+24h] [rbp-174h] BYREF
  _QWORD v6[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  CoreGlobConfigTraceLogging::SyncLanguageDataToCloudSynchronousActivity::Start<>((CoreGlobConfigTraceLogging::SyncLanguageDataToCloudSynchronousActivity *)v6);
  Address = 0;
  v0 = SyncLanguageDataToCDSWorker(&Address);
  v1 = v0;
  if ( v0 >= 0 )
  {
    while ( !(unsigned __int8)wil::slim_event_t<0>::TryAcquireEvent(&Address) )
    {
      CompareAddress[0] = 0;
      if ( !WaitOnAddress(&Address, CompareAddress, 4u, 0xFFFFFFFF) )
      {
        if ( GetLastError() != 1460 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xDBF,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v3);
        break;
      }
    }
    wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v6,
      0);
    CoreGlobConfigTraceLogging::SyncLanguageDataToCloudSynchronousActivity::~SyncLanguageDataToCloudSynchronousActivity((CoreGlobConfigTraceLogging::SyncLanguageDataToCloudSynchronousActivity *)v6);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53D,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)v0,
      Address);
    CoreGlobConfigTraceLogging::SyncLanguageDataToCloudSynchronousActivity::~SyncLanguageDataToCloudSynchronousActivity((CoreGlobConfigTraceLogging::SyncLanguageDataToCloudSynchronousActivity *)v6);
    return v1;
  }
}

```

## disassembly

```asm
0x18001b3e0  push    rbx
0x18001b3e2  sub     rsp, 190h
0x18001b3e9  mov     rax, cs:__security_cookie
0x18001b3f0  xor     rax, rsp
0x18001b3f3  mov     [rsp+198h+var_18], rax
0x18001b3fb  lea     rcx, [rsp+198h+var_168]; this
0x18001b400  call    ??$Start@$$V@SyncLanguageDataToCloudSynchronousActivity@CoreGlobConfigTraceLogging@@SA?AV01@XZ; CoreGlobConfigTraceLogging::SyncLanguageDataToCloudSynchronousActivity::Start<>(void)
0x18001b405  nop
0x18001b406  mov     [rsp+198h+Address], 0; int
0x18001b40e  lea     rcx, [rsp+198h+Address]
0x18001b413  call    ?SyncLanguageDataToCDSWorker@@YAJPEAV?$slim_event_t@$0A@@wil@@@Z; SyncLanguageDataToCDSWorker(wil::slim_event_t<0> *)
0x18001b418  mov     ebx, eax
0x18001b41a  test    eax, eax
0x18001b41c  jns     short loc_18001B449
0x18001b41e  mov     rcx, [rsp+198h]; this
0x18001b426  mov     r9d, eax; char *
0x18001b429  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001b430  mov     edx, 53Dh; void *
0x18001b435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b43a  nop
0x18001b43b  lea     rcx, [rsp+198h+var_168]; this
0x18001b440  call    ??1SyncLanguageDataToCloudSynchronousActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SyncLanguageDataToCloudSynchronousActivity::~SyncLanguageDataToCloudSynchronousActivity(void)
0x18001b445  mov     eax, ebx
0x18001b447  jmp     short loc_18001B4C3
0x18001b449  lea     rcx, [rsp+198h+Address]
0x18001b44e  call    ?TryAcquireEvent@?$slim_event_t@$0A@@wil@@AEAA_NXZ; wil::slim_event_t<0>::TryAcquireEvent(void)
0x18001b453  test    al, al
0x18001b455  jnz     short loc_18001B4A4
0x18001b457  mov     [rsp+198h+CompareAddress], 0
0x18001b45f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001b463  mov     r8d, 4; AddressSize
0x18001b469  lea     rdx, [rsp+198h+CompareAddress]; CompareAddress
0x18001b46e  lea     rcx, [rsp+198h+Address]; Address
0x18001b473  call    cs:__imp_WaitOnAddress
0x18001b479  test    eax, eax
0x18001b47b  jnz     short loc_18001B449
0x18001b47d  call    cs:__imp_GetLastError
0x18001b483  cmp     eax, 5B4h
0x18001b488  jz      short loc_18001B4A4
0x18001b48a  mov     rcx, [rsp+198h]; this
0x18001b492  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001b499  mov     edx, 0DBFh; void *
0x18001b49e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001b4a4  xor     edx, edx
0x18001b4a6  lea     rcx, [rsp+198h+var_168]
0x18001b4ab  call    ?Stop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001b4b0  nop
0x18001b4b1  lea     rcx, [rsp+198h+var_168]; this
0x18001b4b6  call    ??1SyncLanguageDataToCloudSynchronousActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SyncLanguageDataToCloudSynchronousActivity::~SyncLanguageDataToCloudSynchronousActivity(void)
0x18001b4bb  xor     eax, eax
0x18001b4bd  jmp     short loc_18001B4C3
0x18001b4bf  mov     eax, [rsp+198h+CompareAddress]
0x18001b4c3  mov     rcx, [rsp+198h+var_18]
0x18001b4cb  xor     rcx, rsp; StackCookie
0x18001b4ce  call    __security_check_cookie
0x18001b4d3  add     rsp, 190h
0x18001b4da  pop     rbx
0x18001b4db  retn
```
