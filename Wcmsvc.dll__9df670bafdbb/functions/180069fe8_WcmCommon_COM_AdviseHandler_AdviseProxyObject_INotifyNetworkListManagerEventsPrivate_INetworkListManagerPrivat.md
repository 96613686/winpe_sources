# WcmCommon::COM::AdviseHandler::AdviseProxyObject<INotifyNetworkListManagerEventsPrivate,INetworkListManagerPrivate,INotifyNetworkListManagerEventsPrivate>(Microsoft::WRL::ComPtr<INetworkListManagerPrivate>,INotifyNetworkListManagerEventsPrivate *)

- ea: `0x180069fe8`
- end: `0x18006a1a7`
- name: `??$AdviseProxyObject@UINotifyNetworkListManagerEventsPrivate@@UINetworkListManagerPrivate@@U1@@AdviseHandler@COM@WcmCommon@@QEAAXV?$ComPtr@UINetworkListManagerPrivate@@@WRL@Microsoft@@PEAUINotifyNetworkListManagerEventsPrivate@@@Z`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180069f88`

## callees

- `0x18001c11c`
- `0x180069fe8`
- `0x18006a3f8`
- `0x18006a448`
- `0x18006a474`
- `0x18006a4cc`
- `0x180084f50`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006a081`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006a10b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006a081`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006a10b`

## string_xrefs

- `0x18006a040`: `onecore\private\net\inc\wcm\wcm_com.h`
- `0x18006a092`: `onecore\private\net\inc\wcm\wcm_com.h`
- `0x18006a0ca`: `onecore\private\net\inc\wcm\wcm_com.h`
- `0x18006a11c`: `onecore\private\net\inc\wcm\wcm_com.h`
- `0x18006a150`: `onecore\private\net\inc\wcm\wcm_com.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WcmCommon::COM::AdviseHandler::AdviseProxyObject<INotifyNetworkListManagerEventsPrivate,INetworkListManagerPrivate,INotifyNetworkListManagerEventsPrivate>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v6; // eax
  HRESULT v7; // eax
  int v8; // eax
  HRESULT v9; // eax
  int v10; // eax
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-50h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-50h]
  DWORD dwAuthnLevelb; // [rsp+20h] [rbp-50h]
  IUnknown *pProxy; // [rsp+48h] [rbp-28h] BYREF
  IUnknown *v16; // [rsp+50h] [rbp-20h] BYREF
  int v17; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v16 = 0;
  v17 = 0;
  pProxy = 0;
  v6 = Microsoft::WRL::ComPtr<INetworkListManagerPrivate>::As<IConnectionPointContainer>(a2, &pProxy);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_com.h",
      (const char *)(unsigned int)v6,
      dwAuthnLevel);
  v7 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_com.h",
      (const char *)(unsigned int)v7,
      dwAuthnLevela);
  v8 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl[1].AddRef)(
         pProxy,
         &GUID_1299cf18_c4f5_4b6a_bb0f_2299f0398e27,
         &v16);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_com.h",
      (const char *)(unsigned int)v8,
      dwAuthnLevela);
  v9 = CoSetProxyBlanket(v16, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_com.h",
      (const char *)(unsigned int)v9,
      dwAuthnLevelb);
  v10 = ((__int64 (__fastcall *)(IUnknown *, __int64, int *))v16->lpVtbl[1].Release)(v16, a3, &v17);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_com.h",
      (const char *)(unsigned int)v10,
      dwAuthnLevelb);
  std::vector<WcmCommon::COM::AdviseHandler::AdviseInstance>::emplace_back<WcmCommon::COM::AdviseHandler::AdviseInstance>(
    a1,
    &v16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  WcmCommon::COM::AdviseHandler::AdviseInstance::~AdviseInstance((WcmCommon::COM::AdviseHandler::AdviseInstance *)&v16);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
}

```

## disassembly

```asm
0x180069fe8  mov     [rsp-18h+arg_18], rbx
0x180069fed  push    rbp
0x180069fee  push    rsi
0x180069fef  push    rdi
0x180069ff0  mov     rbp, rsp
0x180069ff3  sub     rsp, 70h
0x180069ff7  mov     rax, cs:__security_cookie
0x180069ffe  xor     rax, rsp
0x18006a001  mov     [rbp+var_10], rax
0x18006a005  mov     rsi, r8
0x18006a008  mov     rbx, rdx
0x18006a00b  mov     rdi, rcx
0x18006a00e  mov     [rbp+var_30], rdx
0x18006a012  mov     [rbp+var_20], 0
0x18006a01a  mov     [rbp+var_18], 0
0x18006a021  mov     [rbp+pProxy], 0
0x18006a029  lea     rdx, [rbp+pProxy]
0x18006a02d  mov     rcx, rbx
0x18006a030  call    ??$As@UIConnectionPointContainer@@@?$ComPtr@UINetworkListManagerPrivate@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIConnectionPointContainer@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<INetworkListManagerPrivate>::As<IConnectionPointContainer>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IConnectionPointContainer>>)
0x18006a035  mov     rcx, [rbp+18h]; this
0x18006a039  test    eax, eax
0x18006a03b  jns     short loc_18006A052
0x18006a03d  mov     r9d, eax; char *
0x18006a040  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_co"...
0x18006a047  mov     edx, 0F8h; void *
0x18006a04c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006a052  mov     [rsp+70h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18006a05a  mov     [rsp+70h+pAuthInfo], 0; pAuthInfo
0x18006a063  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x18006a06b  mov     [rsp+70h+dwAuthnLevel], 0; int
0x18006a073  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18006a077  xor     r8d, r8d; dwAuthzSvc
0x18006a07a  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18006a07d  mov     rcx, [rbp+pProxy]; pProxy
0x18006a081  call    cs:__imp_CoSetProxyBlanket
0x18006a087  mov     rcx, [rbp+18h]; this
0x18006a08b  test    eax, eax
0x18006a08d  jns     short loc_18006A0A4
0x18006a08f  mov     r9d, eax; char *
0x18006a092  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_co"...
0x18006a099  mov     edx, 101h; void *
0x18006a09e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006a0a4  mov     rcx, [rbp+pProxy]
0x18006a0a8  mov     rax, [rcx]
0x18006a0ab  lea     r8, [rbp+var_20]
0x18006a0af  lea     rdx, _GUID_1299cf18_c4f5_4b6a_bb0f_2299f0398e27
0x18006a0b6  mov     rax, [rax+20h]
0x18006a0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a0bf  mov     rcx, [rbp+18h]; this
0x18006a0c3  test    eax, eax
0x18006a0c5  jns     short loc_18006A0DC
0x18006a0c7  mov     r9d, eax; char *
0x18006a0ca  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_co"...
0x18006a0d1  mov     edx, 103h; void *
0x18006a0d6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006a0dc  mov     [rsp+70h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18006a0e4  mov     [rsp+70h+pAuthInfo], 0; pAuthInfo
0x18006a0ed  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x18006a0f5  mov     [rsp+70h+dwAuthnLevel], 0; int
0x18006a0fd  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18006a101  xor     r8d, r8d; dwAuthzSvc
0x18006a104  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18006a107  mov     rcx, [rbp+var_20]; pProxy
0x18006a10b  call    cs:__imp_CoSetProxyBlanket
0x18006a111  mov     rcx, [rbp+18h]; this
0x18006a115  test    eax, eax
0x18006a117  jns     short loc_18006A12E
0x18006a119  mov     r9d, eax; char *
0x18006a11c  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_co"...
0x18006a123  mov     edx, 10Ch; void *
0x18006a128  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006a12e  mov     rcx, [rbp+var_20]
0x18006a132  mov     rax, [rcx]
0x18006a135  lea     r8, [rbp+var_18]
0x18006a139  mov     rdx, rsi
0x18006a13c  mov     rax, [rax+28h]
0x18006a140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a145  mov     rcx, [rbp+18h]; this
0x18006a149  test    eax, eax
0x18006a14b  jns     short loc_18006A162
0x18006a14d  mov     r9d, eax; char *
0x18006a150  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_co"...
0x18006a157  mov     edx, 10Eh; void *
0x18006a15c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006a162  lea     rdx, [rbp+var_20]
0x18006a166  mov     rcx, rdi
0x18006a169  call    ??$emplace_back@UAdviseInstance@AdviseHandler@COM@WcmCommon@@@?$vector@UAdviseInstance@AdviseHandler@COM@WcmCommon@@V?$allocator@UAdviseInstance@AdviseHandler@COM@WcmCommon@@@std@@@std@@QEAAAEAUAdviseInstance@AdviseHandler@COM@WcmCommon@@$$QEAU2345@@Z; std::vector<WcmCommon::COM::AdviseHandler::AdviseInstance>::emplace_back<WcmCommon::COM::AdviseHandler::AdviseInstance>(WcmCommon::COM::AdviseHandler::AdviseInstance &&)
0x18006a16e  nop
0x18006a16f  lea     rcx, [rbp+pProxy]
0x18006a173  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006a178  nop
0x18006a179  lea     rcx, [rbp+var_20]; this
0x18006a17d  call    ??1AdviseInstance@AdviseHandler@COM@WcmCommon@@QEAA@XZ; WcmCommon::COM::AdviseHandler::AdviseInstance::~AdviseInstance(void)
0x18006a182  nop
0x18006a183  mov     rcx, rbx
0x18006a186  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006a18b  mov     rcx, [rbp+var_10]
0x18006a18f  xor     rcx, rsp; StackCookie
0x18006a192  call    __security_check_cookie
0x18006a197  mov     rbx, [rsp+70h+arg_18]
0x18006a19f  add     rsp, 70h
0x18006a1a3  pop     rdi
0x18006a1a4  pop     rsi
0x18006a1a5  pop     rbp
0x18006a1a6  retn
```
