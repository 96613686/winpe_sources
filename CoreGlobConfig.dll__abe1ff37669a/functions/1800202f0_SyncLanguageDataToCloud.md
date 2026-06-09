# SyncLanguageDataToCloud

- ea: `0x1800202f0`
- end: `0x1800203a4`
- name: `SyncLanguageDataToCloud`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180002380`
- `0x180008294`
- `0x18000f35c`
- `0x180011b78`
- `0x180019c7c`
- `0x180019f30`
- `0x18001b34c`
- `0x1800202f0`

## string_xrefs

- `0x18002034b`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 SyncLanguageDataToCloud()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-178h]
  _QWORD v4[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v4,
    (__int64)"SyncLanguageDataToCloudActivity");
  v4[0] = &CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity::`vftable';
  CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity::StartActivity((CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity *)v4);
  v0 = SyncLanguageDataToCDSWorker(0);
  v1 = v0;
  if ( v0 >= 0 )
  {
    wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v4,
      0);
    CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity::~SyncLanguageDataToCloudActivity((CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity *)v4);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52F,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)v0,
      v3);
    CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity::~SyncLanguageDataToCloudActivity((CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity *)v4);
    return v1;
  }
}

```

## disassembly

```asm
0x1800202f0  push    rbx
0x1800202f2  sub     rsp, 190h
0x1800202f9  mov     rax, cs:__security_cookie
0x180020300  xor     rax, rsp
0x180020303  mov     [rsp+198h+var_18], rax
0x18002030b  lea     rdx, aSynclanguageda_4; "SyncLanguageDataToCloudActivity"
0x180020312  lea     rcx, [rsp+198h+var_168]
0x180020317  call    ??0?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002031c  lea     rax, ??_7SyncLanguageDataToCloudActivity@CoreGlobConfigTraceLogging@@6B@; const CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity::`vftable'
0x180020323  mov     [rsp+198h+var_168], rax
0x180020328  lea     rcx, [rsp+198h+var_168]; this
0x18002032d  call    ?StartActivity@SyncLanguageDataToCloudActivity@CoreGlobConfigTraceLogging@@QEAAXXZ; CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity::StartActivity(void)
0x180020332  nop
0x180020333  xor     ecx, ecx
0x180020335  call    ?SyncLanguageDataToCDSWorker@@YAJPEAV?$slim_event_t@$0A@@wil@@@Z; SyncLanguageDataToCDSWorker(wil::slim_event_t<0> *)
0x18002033a  mov     ebx, eax
0x18002033c  test    eax, eax
0x18002033e  jns     short loc_18002036B
0x180020340  mov     rcx, [rsp+198h]; this
0x180020348  mov     r9d, eax; char *
0x18002034b  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180020352  mov     edx, 52Fh; void *
0x180020357  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002035c  nop
0x18002035d  lea     rcx, [rsp+198h+var_168]; this
0x180020362  call    ??1SyncLanguageDataToCloudActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity::~SyncLanguageDataToCloudActivity(void)
0x180020367  mov     eax, ebx
0x180020369  jmp     short loc_18002038A
0x18002036b  xor     edx, edx
0x18002036d  lea     rcx, [rsp+198h+var_168]
0x180020372  call    ?Stop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180020377  nop
0x180020378  lea     rcx, [rsp+198h+var_168]; this
0x18002037d  call    ??1SyncLanguageDataToCloudActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity::~SyncLanguageDataToCloudActivity(void)
0x180020382  xor     eax, eax
0x180020384  jmp     short loc_18002038A
0x180020386  mov     eax, [rsp+198h+var_178]
0x18002038a  mov     rcx, [rsp+198h+var_18]
0x180020392  xor     rcx, rsp; StackCookie
0x180020395  call    __security_check_cookie
0x18002039a  add     rsp, 190h
0x1800203a1  pop     rbx
0x1800203a2  retn
```
