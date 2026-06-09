# LanguageOverlayServiceModule::ServiceMain(ulong,ushort const * *)

- ea: `0x18001021c`
- end: `0x180010335`
- name: `?ServiceMain@LanguageOverlayServiceModule@@QEAAJKPEAPEBG@Z`
- size: `281`
- prototype: `__int64 __fastcall(LanguageOverlayServiceModule *__hidden this, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013140`

## callees

- `0x180003a00`
- `0x18000b86c`
- `0x18000bd94`
- `0x18000d140`
- `0x18001021c`
- `0x18001046c`
- `0x180010738`
- `0x180011ccc`
- `0x1800120d0`
- `0x1800121a8`
- `0x180012a98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010276`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010276`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800102d2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800102d2`
- `combase!__imp_CoReleaseSharedService` at `0x1800102cb`
- `combase!__imp_CoReleaseSharedService` at `0x1800102cb`

## string_xrefs

- `0x18001024a`: `ServiceStartActivity`
- `0x180010322`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LanguageOverlayServiceModule::ServiceMain(
        LanguageOverlayServiceModule *this,
        __int64 a2,
        const unsigned __int16 **a3)
{
  char *v4; // rbx
  HRESULT v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  unsigned int v8[4]; // [rsp+20h] [rbp-178h] BYREF
  _QWORD v9[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v4 = (char *)_service;
  wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v9,
    "ServiceStartActivity");
  v9[0] = &LanguageOverlayTraceProvider::ServiceStartActivity::`vftable';
  LanguageOverlayTraceProvider::ServiceStartActivity::StartActivity((LanguageOverlayTraceProvider::ServiceStartActivity *)v9);
  v5 = CoInitializeEx(0, 0);
  try
  {
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.cpp",
        (const char *)(unsigned int)v5,
        v8[0]);
    v8[1] = 1;
    LanguageOverlayServiceModule::_Initialize(v4, v8, *a3);
    LanguageOverlayServiceModule::_OnStarting((LanguageOverlayServiceModule *)v4);
    LanguageOverlayServiceModule::_OnStarted((LanguageOverlayServiceModule *)v4, *a3);
    wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v9);
    if ( v8[0] )
      CoReleaseSharedService();
    CoUninitialize();
    v9[0] = &LanguageOverlayTraceProvider::ServiceStartActivity::`vftable';
    wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v9);
    wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v9);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x70,
                           (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\language"
                                         "overlayservicemodule.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18001021c  mov     [rsp+arg_0], rbx
0x180010221  mov     [rsp+arg_8], rsi
0x180010226  push    rdi
0x180010227  sub     rsp, 190h
0x18001022e  mov     rax, cs:__security_cookie
0x180010235  xor     rax, rsp
0x180010238  mov     [rsp+198h+var_18], rax
0x180010240  mov     rdi, r8
0x180010243  mov     rbx, cs:?_service@@3AEAVLanguageOverlayServiceModule@@EA; LanguageOverlayServiceModule & _service
0x18001024a  lea     rdx, aServicestartac; "ServiceStartActivity"
0x180010251  lea     rcx, [rsp+198h+var_168]
0x180010256  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001025b  lea     rsi, ??_7ServiceStartActivity@LanguageOverlayTraceProvider@@6B@; const LanguageOverlayTraceProvider::ServiceStartActivity::`vftable'
0x180010262  mov     [rsp+198h+var_168], rsi
0x180010267  lea     rcx, [rsp+198h+var_168]; this
0x18001026c  call    ?StartActivity@ServiceStartActivity@LanguageOverlayTraceProvider@@QEAAXXZ; LanguageOverlayTraceProvider::ServiceStartActivity::StartActivity(void)
0x180010271  nop
0x180010272  xor     edx, edx; dwCoInit
0x180010274  xor     ecx, ecx; pvReserved
0x180010276  call    cs:__imp_CoInitializeEx
0x18001027c  mov     rcx, [rsp+198h]; this
0x180010284  test    eax, eax
0x180010286  js      loc_18001031F
0x18001028c  mov     [rsp+198h+var_174], 1
0x180010294  mov     r8, [rdi]
0x180010297  lea     rdx, [rsp+198h+var_178]
0x18001029c  mov     rcx, rbx; lpContext
0x18001029f  call    ?_Initialize@LanguageOverlayServiceModule@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@KP6AXK@Z$1?_ReleaseSharedService@details@raii@@YAXK@ZU?$integral_constant@_K$0A@@wistd@@KK$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; LanguageOverlayServiceModule::_Initialize(ushort const *)
0x1800102a4  nop
0x1800102a5  mov     rcx, rbx; this
0x1800102a8  call    ?_OnStarting@LanguageOverlayServiceModule@@AEAAXXZ; LanguageOverlayServiceModule::_OnStarting(void)
0x1800102ad  mov     rdx, [rdi]; unsigned __int16 *
0x1800102b0  mov     rcx, rbx; this
0x1800102b3  call    ?_OnStarted@LanguageOverlayServiceModule@@AEAAXPEBG@Z; LanguageOverlayServiceModule::_OnStarted(ushort const *)
0x1800102b8  lea     rcx, [rsp+198h+var_168]
0x1800102bd  call    ?Stop@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800102c2  nop
0x1800102c3  mov     ecx, [rsp+198h+var_178]
0x1800102c7  test    ecx, ecx
0x1800102c9  jz      short loc_1800102D2
0x1800102cb  call    cs:__imp_CoReleaseSharedService
0x1800102d1  nop
0x1800102d2  call    cs:__imp_CoUninitialize
0x1800102d8  nop
0x1800102d9  mov     [rsp+198h+var_168], rsi
0x1800102de  lea     rcx, [rsp+198h+var_168]
0x1800102e3  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800102e8  lea     rcx, [rsp+198h+var_168]
0x1800102ed  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800102f2  xor     eax, eax
0x1800102f4  jmp     short loc_1800102FA
0x1800102f6  mov     eax, [rsp+198h+var_178]
0x1800102fa  mov     rcx, [rsp+198h+var_18]
0x180010302  xor     rcx, rsp; StackCookie
0x180010305  call    __security_check_cookie
0x18001030a  lea     r11, [rsp+198h+var_8]
0x180010312  mov     rbx, [r11+10h]
0x180010316  mov     rsi, [r11+18h]
0x18001031a  mov     rsp, r11
0x18001031d  pop     rdi
0x18001031e  retn
0x18001031f  mov     r9d, eax; char *
0x180010322  lea     r8, aOnecoreBaseLan_1; "onecore\\base\\languageoverlay\\service"...
0x180010329  mov     edx, 12h; void *
0x18001032e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
