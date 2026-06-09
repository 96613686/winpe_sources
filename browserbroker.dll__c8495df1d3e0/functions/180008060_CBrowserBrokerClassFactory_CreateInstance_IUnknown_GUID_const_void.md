# CBrowserBrokerClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180008060`
- end: `0x1800082d3`
- name: `?CreateInstance@CBrowserBrokerClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `627`
- prototype: `__int64 __fastcall(CBrowserBrokerClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005844`
- `0x180006938`
- `0x180007858`
- `0x180007a04`
- `0x180007a8c`
- `0x180008060`
- `0x180008b94`
- `0x18000a4fc`
- `0x18000b6d0`
- `0x18000ba70`
- `0x18000dc74`
- `0x18000e4b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008178`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008178`

## string_xrefs

- `0x18000822b`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x180008244`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x180008267`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x18000828c`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x1800082a5`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x1800082be`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x180008276`: `Invalid call to request the broker.`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerClassFactory::CreateInstance(
        CBrowserBrokerClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v7; // eax
  signed __int32 v8; // edi
  int v9; // eax
  HRESULT v10; // eax
  unsigned int Interface; // edi
  int v12; // eax
  unsigned int v13; // edx
  int Instance; // eax
  unsigned int v16; // eax
  int ppv; // [rsp+20h] [rbp-28h]
  int ppva; // [rsp+20h] [rbp-28h]
  const char *v19; // [rsp+28h] [rbp-20h]
  int v20; // [rsp+30h] [rbp-18h] BYREF
  int v21; // [rsp+34h] [rbp-14h] BYREF
  int v22; // [rsp+38h] [rbp-10h] BYREF
  _DWORD v23[3]; // [rsp+3Ch] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  struct IUnknown *v25; // [rsp+98h] [rbp+50h] BYREF

  v23[0] = 4;
  *a4 = 0;
  LODWORD(v25) = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<enum CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(
    v23,
    &v22,
    &v21,
    &v20);
  v7 = BrokerAuthenticateCOMCaller((unsigned int *)&v25, 0, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  if ( g_fTerminateThisProcess || (v8 = (int)v25, (_DWORD)v25 == 255) || !IsBrokerCreatedByManager() )
  {
    v16 = wil::verify_hresult<long>(2147942405LL);
    wil::details::in1diag3::FailFast_HrMsg(
      retaddr,
      (void *)0x108,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
      (const char *)v16,
      (int)"Invalid call to request the broker.",
      v19);
  }
  if ( *((_DWORD *)this + 5) == v8 || _InterlockedCompareExchange((volatile signed __int32 *)this + 5, v8, 255) == 255 )
  {
    v13 = *((_DWORD *)this + 6);
    v25 = 0;
    Instance = CBrowserBrokerInstance_CreateInstance((struct CBrowserBrokerInstance **)&v25, v13);
    if ( Instance < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x141,
        (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
    Interface = CBrowserBrokerInstance::QueryInterface(v25, a3, a4);
    CBrowserBrokerInstance::Release((CBrowserBrokerInstance *)v25);
  }
  else
  {
    LODWORD(v25) = 0;
    v23[0] = 0;
    v22 = 0;
    v21 = 6;
    DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<enum CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(
      &v21,
      &v22,
      v23,
      &v25);
    v9 = CBrowserBrokerClassFactory::CoRevokeClassFactory(this);
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
        (const char *)(unsigned int)v9,
        ppv);
    LODWORD(v25) = 0;
    v23[0] = 0;
    v22 = 0;
    v21 = 7;
    DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<enum CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(
      &v21,
      &v22,
      v23,
      &v25);
    v10 = CoCreateInstance(&CLSID_BrowserBroker, 0, 4u, a3, a4);
    Interface = v10;
    if ( v10 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
        (const char *)(unsigned int)v10,
        ppva);
    LODWORD(v25) = 0;
    v23[0] = 0;
    v22 = 0;
    v21 = 8;
    DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<enum CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(
      &v21,
      &v22,
      v23,
      &v25);
    v12 = CBrowserBrokerClassFactory::CoRegisterClassFactory((LPUNKNOWN)this);
    if ( v12 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x133,
        (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
        (const char *)(unsigned int)v12,
        ppva);
  }
  LODWORD(v25) = 0;
  v23[0] = 0;
  v22 = 0;
  v21 = 5;
  DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<enum CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(
    &v21,
    &v22,
    v23,
    &v25);
  return Interface;
}

```

## disassembly

```asm
0x180008060  push    rbp
0x180008062  push    rbx
0x180008063  push    rsi
0x180008064  push    rdi
0x180008065  push    r14
0x180008067  push    r15
0x180008069  mov     rbp, rsp
0x18000806c  sub     rsp, 48h
0x180008070  xor     r15d, r15d
0x180008073  mov     [rbp+var_C], 4
0x18000807a  mov     [r9], r15
0x18000807d  lea     rdx, [rbp+var_10]
0x180008081  mov     rsi, r9
0x180008084  mov     dword ptr [rbp+arg_18], r15d
0x180008088  mov     r14, r8
0x18000808b  mov     [rbp+var_18], r15d
0x18000808f  mov     rbx, rcx
0x180008092  mov     [rbp+var_14], r15d
0x180008096  lea     r9, [rbp+var_18]
0x18000809a  mov     [rbp+var_10], r15d
0x18000809e  lea     r8, [rbp+var_14]
0x1800080a2  lea     rcx, [rbp+var_C]
0x1800080a6  call    ??$CBrowserBrokerClassFactoryEvent@W4CBrowserBrokerClassFactoryEvent_Trigger@@HHH@DesktopBrokerTelemetry@@SAX$$QEAW4CBrowserBrokerClassFactoryEvent_Trigger@@$$QEAH11@Z; DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(CBrowserBrokerClassFactoryEvent_Trigger &&,int &&,int &&,int &&)
0x1800080ab  xor     r8d, r8d; unsigned int *
0x1800080ae  lea     rcx, [rbp+arg_18]; unsigned int *
0x1800080b2  xor     edx, edx; unsigned __int16 **
0x1800080b4  call    ?BrokerAuthenticateCOMCaller@@YAJPEAKPEAPEBG0@Z; BrokerAuthenticateCOMCaller(ulong *,ushort const * *,ulong *)
0x1800080b9  test    eax, eax
0x1800080bb  js      loc_180008288
0x1800080c1  cmp     cs:?g_fTerminateThisProcess@@3_NA, r15b; bool g_fTerminateThisProcess
0x1800080c8  jnz     loc_180008259
0x1800080ce  mov     edi, dword ptr [rbp+arg_18]
0x1800080d1  cmp     edi, 0FFh
0x1800080d7  jz      loc_180008259
0x1800080dd  call    ?IsBrokerCreatedByManager@@YA_NXZ; IsBrokerCreatedByManager(void)
0x1800080e2  test    al, al
0x1800080e4  jz      loc_180008259
0x1800080ea  cmp     [rbx+14h], edi
0x1800080ed  jz      loc_1800081C2
0x1800080f3  mov     eax, 0FFh
0x1800080f8  lock cmpxchg [rbx+14h], edi
0x1800080fd  jz      loc_1800081C2
0x180008103  lea     r9, [rbp+arg_18]
0x180008107  mov     dword ptr [rbp+arg_18], r15d
0x18000810b  lea     r8, [rbp+var_C]
0x18000810f  mov     [rbp+var_C], r15d
0x180008113  lea     rdx, [rbp+var_10]
0x180008117  mov     [rbp+var_10], r15d
0x18000811b  lea     rcx, [rbp+var_14]
0x18000811f  mov     [rbp+var_14], 6
0x180008126  call    ??$CBrowserBrokerClassFactoryEvent@W4CBrowserBrokerClassFactoryEvent_Trigger@@HHH@DesktopBrokerTelemetry@@SAX$$QEAW4CBrowserBrokerClassFactoryEvent_Trigger@@$$QEAH11@Z; DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(CBrowserBrokerClassFactoryEvent_Trigger &&,int &&,int &&,int &&)
0x18000812b  mov     rcx, rbx; this
0x18000812e  call    ?CoRevokeClassFactory@CBrowserBrokerClassFactory@@QEAAJXZ; CBrowserBrokerClassFactory::CoRevokeClassFactory(void)
0x180008133  test    eax, eax
0x180008135  js      loc_1800082A1
0x18000813b  lea     r9, [rbp+arg_18]
0x18000813f  mov     dword ptr [rbp+arg_18], r15d
0x180008143  lea     r8, [rbp+var_C]
0x180008147  mov     [rbp+var_C], r15d
0x18000814b  lea     rdx, [rbp+var_10]
0x18000814f  mov     [rbp+var_10], r15d
0x180008153  lea     rcx, [rbp+var_14]
0x180008157  mov     [rbp+var_14], 7
0x18000815e  call    ??$CBrowserBrokerClassFactoryEvent@W4CBrowserBrokerClassFactoryEvent_Trigger@@HHH@DesktopBrokerTelemetry@@SAX$$QEAW4CBrowserBrokerClassFactoryEvent_Trigger@@$$QEAH11@Z; DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(CBrowserBrokerClassFactoryEvent_Trigger &&,int &&,int &&,int &&)
0x180008163  mov     r9, r14; riid
0x180008166  mov     [rsp+48h+ppv], rsi; int
0x18000816b  xor     edx, edx; pUnkOuter
0x18000816d  lea     r8d, [r15+4]; dwClsContext
0x180008171  lea     rcx, CLSID_BrowserBroker; rclsid
0x180008178  call    cs:__imp_CoCreateInstance
0x18000817e  mov     edi, eax
0x180008180  test    eax, eax
0x180008182  js      loc_1800082BA
0x180008188  lea     r9, [rbp+arg_18]
0x18000818c  mov     dword ptr [rbp+arg_18], r15d
0x180008190  lea     r8, [rbp+var_C]
0x180008194  mov     [rbp+var_C], r15d
0x180008198  lea     rdx, [rbp+var_10]
0x18000819c  mov     [rbp+var_10], r15d
0x1800081a0  lea     rcx, [rbp+var_14]
0x1800081a4  mov     [rbp+var_14], 8
0x1800081ab  call    ??$CBrowserBrokerClassFactoryEvent@W4CBrowserBrokerClassFactoryEvent_Trigger@@HHH@DesktopBrokerTelemetry@@SAX$$QEAW4CBrowserBrokerClassFactoryEvent_Trigger@@$$QEAH11@Z; DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(CBrowserBrokerClassFactoryEvent_Trigger &&,int &&,int &&,int &&)
0x1800081b0  mov     rcx, rbx; pUnk
0x1800081b3  call    ?CoRegisterClassFactory@CBrowserBrokerClassFactory@@QEAAJXZ; CBrowserBrokerClassFactory::CoRegisterClassFactory(void)
0x1800081b8  test    eax, eax
0x1800081ba  js      loc_180008240
0x1800081c0  jmp     short loc_1800081F0
0x1800081c2  mov     edx, [rbx+18h]; unsigned int
0x1800081c5  lea     rcx, [rbp+arg_18]; struct CBrowserBrokerInstance **
0x1800081c9  mov     [rbp+arg_18], r15
0x1800081cd  call    ?CBrowserBrokerInstance_CreateInstance@@YAJPEAPEAVCBrowserBrokerInstance@@K@Z; CBrowserBrokerInstance_CreateInstance(CBrowserBrokerInstance * *,ulong)
0x1800081d2  test    eax, eax
0x1800081d4  js      short loc_180008227
0x1800081d6  mov     rcx, [rbp+arg_18]; this
0x1800081da  mov     r8, rsi; void **
0x1800081dd  mov     rdx, r14; struct _GUID *
0x1800081e0  call    ?QueryInterface@CBrowserBrokerInstance@@UEAAJAEBU_GUID@@PEAPEAX@Z; CBrowserBrokerInstance::QueryInterface(_GUID const &,void * *)
0x1800081e5  mov     rcx, [rbp+arg_18]; this
0x1800081e9  mov     edi, eax
0x1800081eb  call    ?Release@CBrowserBrokerInstance@@UEAAKXZ; CBrowserBrokerInstance::Release(void)
0x1800081f0  lea     r9, [rbp+arg_18]
0x1800081f4  mov     dword ptr [rbp+arg_18], r15d
0x1800081f8  lea     r8, [rbp+var_C]
0x1800081fc  mov     [rbp+var_C], r15d
0x180008200  lea     rdx, [rbp+var_10]
0x180008204  mov     [rbp+var_10], r15d
0x180008208  lea     rcx, [rbp+var_14]
0x18000820c  mov     [rbp+var_14], 5
0x180008213  call    ??$CBrowserBrokerClassFactoryEvent@W4CBrowserBrokerClassFactoryEvent_Trigger@@HHH@DesktopBrokerTelemetry@@SAX$$QEAW4CBrowserBrokerClassFactoryEvent_Trigger@@$$QEAH11@Z; DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(CBrowserBrokerClassFactoryEvent_Trigger &&,int &&,int &&,int &&)
0x180008218  mov     eax, edi
0x18000821a  add     rsp, 48h
0x18000821e  pop     r15
0x180008220  pop     r14
0x180008222  pop     rdi
0x180008223  pop     rsi
0x180008224  pop     rbx
0x180008225  pop     rbp
0x180008226  retn
0x180008227  mov     rcx, [rbp+30h]; this
0x18000822b  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180008232  mov     r9d, eax; char *
0x180008235  mov     edx, 141h; void *
0x18000823a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180008240  mov     rcx, [rbp+30h]; this
0x180008244  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18000824b  mov     r9d, eax; char *
0x18000824e  mov     edx, 133h; void *
0x180008253  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180008259  mov     ecx, 80070005h
0x18000825e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180008263  mov     rcx, [rbp+30h]; this
0x180008267  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18000826e  mov     r9d, eax; char *
0x180008271  mov     edx, 108h; void *
0x180008276  lea     rax, aInvalidCallToR; "Invalid call to request the broker."
0x18000827d  mov     [rsp+48h+ppv], rax; int
0x180008282  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180008288  mov     rcx, [rbp+30h]; this
0x18000828c  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180008293  mov     r9d, eax; char *
0x180008296  mov     edx, 102h; void *
0x18000829b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800082a1  mov     rcx, [rbp+30h]; this
0x1800082a5  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1800082ac  mov     r9d, eax; char *
0x1800082af  mov     edx, 129h; void *
0x1800082b4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800082ba  mov     rcx, [rbp+30h]; this
0x1800082be  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1800082c5  mov     r9d, eax; char *
0x1800082c8  mov     edx, 130h; void *
0x1800082cd  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
