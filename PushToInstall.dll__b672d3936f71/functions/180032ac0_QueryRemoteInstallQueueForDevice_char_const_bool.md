# QueryRemoteInstallQueueForDevice(char const *,bool &)

- ea: `0x180032ac0`
- end: `0x180032cf6`
- name: `?QueryRemoteInstallQueueForDevice@@YAXPEBDAEA_N@Z`
- size: `566`
- prototype: `void __fastcall(const char *, bool *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18002fb4c`

## callees

- `0x1800026b0`
- `0x180002b50`
- `0x180005fa0`
- `0x18000d75c`
- `0x180022810`
- `0x18002c4b8`
- `0x180030a68`
- `0x180031cb8`
- `0x180031d28`
- `0x180031f1c`
- `0x1800322d8`
- `0x180032ac0`
- `0x180034bd4`
- `0x18003571c`
- `0x180036bfc`
- `0x180036ec8`
- `0x1800374d4`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180032b5e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180032b5e`

## string_xrefs

- `0x180032bfd`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x180032c86`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x180032ce4`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x180032c69`: `No storeIds returned to install.`
- `0x180032bdd`: `Retrieved %Iu store ids to install.`
- `0x180032bf0`: `QueryRemoteInstallQueueForDevice`
- `0x180032c79`: `QueryRemoteInstallQueueForDevice`
- `0x180032ccf`: `onecoreuap\enduser\winstore\pushtoinstall\lib\nexus.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall QueryRemoteInstallQueueForDevice(const char *a1, bool *a2)
{
  struct HttpRequest *v3; // rbx
  const char *v4; // r9
  _QWORD *v5; // rax
  const char *v6; // r9
  struct web::json::value *v7; // r9
  _QWORD *v8; // rax
  __int64 v9; // r8
  __int128 v10; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v11; // [rsp+50h] [rbp-B0h] BYREF
  struct HttpRequest *v12; // [rsp+60h] [rbp-A0h]
  _BYTE v13[272]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *a2 = 0;
  v3 = TraceLoggingCorrelationVector::Extend(a1, (bool)a2);
  v12 = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
      v4);
  v11 = 0;
  v5 = operator new(0x68u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *(_QWORD *)&v11 = v5;
  web::json::value::value((web::json::value *)&v10);
  if ( !InitOnceExecuteOnce(&InitOnce, Nexus::InitializeOnce, &g_nexus, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\nexus.cpp",
      v6);
  PTIUtils::CreateHttpRequest(v13, qword_1800664F0, L"GET");
  PTIUtils::SendRequest((PTIUtils *)v13, v3, (struct TraceLoggingCorrelationVector *)&v10, v7);
  PTIUtils::ParseStoreIds(&v10, &v11, a2);
  HttpRequest::~HttpRequest((HttpRequest *)v13);
  if ( (_QWORD)v10 )
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v10 + 192LL))(v10, 1);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
    0x9Cu,
    "QueryRemoteInstallQueueForDevice",
    -1,
    L"Retrieved %Iu store ids to install.",
    *((_QWORD *)&v11 + 1));
  if ( *((_QWORD *)&v11 + 1) )
  {
    v10 = 0;
    v8 = operator new(0x48u);
    *v8 = v8;
    v8[1] = v8;
    v8[2] = v8;
    *((_WORD *)v8 + 12) = 257;
    *(_QWORD *)&v10 = v8;
    InstallItems(v3, (__int64 ***)&v11, v9, &v10);
    QueryPTIServiceToRemoveStoreIds(v3, &v10);
    std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>(&v10);
  }
  else
  {
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
      0xAAu,
      "QueryRemoteInstallQueueForDevice",
      -1,
      L"No storeIds returned to install.");
  }
  std::_Tree<std::_Tmap_traits<std::wstring,ProductInstallRequest,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ProductInstallRequest>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ProductInstallRequest,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ProductInstallRequest>>,0>>(&v11);
  operator delete(v3, (const struct std::nothrow_t *)0x90);
}

```

## disassembly

```asm
0x180032ac0  mov     [rsp-8+arg_10], rbx
0x180032ac5  push    rbp
0x180032ac6  push    rsi
0x180032ac7  push    rdi
0x180032ac8  lea     rbp, [rsp-90h]
0x180032ad0  sub     rsp, 190h
0x180032ad7  mov     rax, cs:__security_cookie
0x180032ade  xor     rax, rsp
0x180032ae1  mov     [rbp+0A0h+var_20], rax
0x180032ae8  mov     rdi, rdx
0x180032aeb  mov     byte ptr [rdx], 0
0x180032aee  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x180032af3  mov     rbx, rax
0x180032af6  mov     [rsp+1A0h+var_140], rax
0x180032afb  mov     rcx, [rbp+0A8h]; this
0x180032b02  test    rax, rax
0x180032b05  jz      loc_180032CE4
0x180032b0b  xorps   xmm0, xmm0
0x180032b0e  movdqu  [rsp+1A0h+var_150], xmm0
0x180032b14  mov     ecx, 68h ; 'h'; Size
0x180032b19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032b1e  mov     [rax], rax
0x180032b21  mov     [rax+8], rax
0x180032b25  mov     [rax+10h], rax
0x180032b29  mov     word ptr [rax+18h], 101h
0x180032b2f  mov     qword ptr [rsp+1A0h+var_150], rax
0x180032b34  lea     rcx, [rsp+1A0h+var_160]; this
0x180032b39  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x180032b3e  nop
0x180032b3f  mov     rsi, [rbp+0A8h]
0x180032b46  xor     r9d, r9d; Context
0x180032b49  lea     r8, ?g_nexus@@3VNexus@@A; Parameter
0x180032b50  lea     rdx, ?InitializeOnce@Nexus@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180032b57  lea     rcx, InitOnce; InitOnce
0x180032b5e  call    cs:__imp_InitOnceExecuteOnce
0x180032b64  test    eax, eax
0x180032b66  jz      loc_180032CCF
0x180032b6c  lea     r8, aGet; "GET"
0x180032b73  lea     rdx, qword_1800664F0
0x180032b7a  lea     rcx, [rsp+1A0h+var_130]
0x180032b7f  call    ?CreateHttpRequest@PTIUtils@@YA?AVHttpRequest@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; PTIUtils::CreateHttpRequest(std::wstring const &,ushort const *)
0x180032b84  nop
0x180032b85  lea     r8, [rsp+1A0h+var_160]; struct TraceLoggingCorrelationVector *
0x180032b8a  mov     rdx, rbx; struct HttpRequest *
0x180032b8d  lea     rcx, [rsp+1A0h+var_130]; this
0x180032b92  call    ?SendRequest@PTIUtils@@YAXAEAVHttpRequest@@PEAVTraceLoggingCorrelationVector@@PEAVvalue@json@web@@@Z; PTIUtils::SendRequest(HttpRequest &,TraceLoggingCorrelationVector *,web::json::value *)
0x180032b97  mov     r8, rdi
0x180032b9a  lea     rdx, [rsp+1A0h+var_150]
0x180032b9f  lea     rcx, [rsp+1A0h+var_160]
0x180032ba4  call    ?ParseStoreIds@PTIUtils@@YAXAEBVvalue@json@web@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@@std@@@2@@std@@AEA_N@Z; PTIUtils::ParseStoreIds(web::json::value const &,std::map<std::wstring,ProductInstallRequest> &,bool &)
0x180032ba9  nop
0x180032baa  lea     rcx, [rsp+1A0h+var_130]; this
0x180032baf  call    ??1HttpRequest@@QEAA@XZ; HttpRequest::~HttpRequest(void)
0x180032bb4  nop
0x180032bb5  mov     rcx, qword ptr [rsp+1A0h+var_160]
0x180032bba  test    rcx, rcx
0x180032bbd  jz      short loc_180032BD3
0x180032bbf  mov     rax, [rcx]
0x180032bc2  mov     edx, 1
0x180032bc7  mov     rax, [rax+0C0h]
0x180032bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bd3  mov     rax, qword ptr [rsp+1A0h+var_150+8]
0x180032bd8  mov     [rsp+1A0h+var_170], rax
0x180032bdd  lea     rax, aRetrievedIuSto; "Retrieved %Iu store ids to install."
0x180032be4  mov     [rsp+1A0h+var_178], rax; unsigned __int16 *
0x180032be9  or      edi, 0FFFFFFFFh
0x180032bec  mov     [rsp+1A0h+var_180], edi; int
0x180032bf0  lea     r9, aQueryremoteins; "QueryRemoteInstallQueueForDevice"
0x180032bf7  mov     r8d, 9Ch; unsigned int
0x180032bfd  lea     rdx, aOnecoreuapEndu_9; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180032c04  lea     esi, [rdi+4]
0x180032c07  mov     ecx, esi; unsigned int
0x180032c09  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x180032c0e  cmp     qword ptr [rsp+1A0h+var_150+8], 0
0x180032c14  jbe     short loc_180032C69
0x180032c16  xorps   xmm0, xmm0
0x180032c19  movdqu  [rsp+1A0h+var_160], xmm0
0x180032c1f  lea     ecx, [rdi+49h]; Size
0x180032c22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032c27  mov     [rax], rax
0x180032c2a  mov     [rax+8], rax
0x180032c2e  mov     [rax+10h], rax
0x180032c32  mov     word ptr [rax+18h], 101h
0x180032c38  mov     qword ptr [rsp+1A0h+var_160], rax
0x180032c3d  lea     r9, [rsp+1A0h+var_160]
0x180032c42  lea     rdx, [rsp+1A0h+var_150]
0x180032c47  mov     rcx, rbx; this
0x180032c4a  call    ?InstallItems@@YAXPEAVTraceLoggingCorrelationVector@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@@std@@@2@@std@@_KAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@3@@Z; InstallItems(TraceLoggingCorrelationVector *,std::map<std::wstring,ProductInstallRequest> const &,unsigned __int64,std::map<std::wstring,long> &)
0x180032c4f  lea     rdx, [rsp+1A0h+var_160]
0x180032c54  mov     rcx, rbx
0x180032c57  call    ?QueryPTIServiceToRemoveStoreIds@@YAXPEAVTraceLoggingCorrelationVector@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@@Z; QueryPTIServiceToRemoveStoreIds(TraceLoggingCorrelationVector *,std::map<std::wstring,long> const &)
0x180032c5c  nop
0x180032c5d  lea     rcx, [rsp+1A0h+var_160]
0x180032c62  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>(void)
0x180032c67  jmp     short loc_180032C95
0x180032c69  lea     rax, aNoStoreidsRetu; "No storeIds returned to install."
0x180032c70  mov     [rsp+1A0h+var_178], rax; unsigned __int16 *
0x180032c75  mov     [rsp+1A0h+var_180], edi; int
0x180032c79  lea     r9, aQueryremoteins; "QueryRemoteInstallQueueForDevice"
0x180032c80  mov     r8d, 0AAh; unsigned int
0x180032c86  lea     rdx, aOnecoreuapEndu_9; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180032c8d  mov     ecx, esi; unsigned int
0x180032c8f  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x180032c94  nop
0x180032c95  lea     rcx, [rsp+1A0h+var_150]
0x180032c9a  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ProductInstallRequest,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ProductInstallRequest>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ProductInstallRequest,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ProductInstallRequest>>,0>>(void)
0x180032c9f  nop
0x180032ca0  mov     edx, 90h; struct std::nothrow_t *
0x180032ca5  mov     rcx, rbx; void *
0x180032ca8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032cad  mov     rcx, [rbp+0A0h+var_20]
0x180032cb4  xor     rcx, rsp; StackCookie
0x180032cb7  call    __security_check_cookie
0x180032cbc  mov     rbx, [rsp+1A0h+arg_10]
0x180032cc4  add     rsp, 190h
0x180032ccb  pop     rdi
0x180032ccc  pop     rsi
0x180032ccd  pop     rbp
0x180032cce  retn
0x180032ccf  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180032cd6  mov     edx, 49h ; 'I'; void *
0x180032cdb  mov     rcx, rsi; this
0x180032cde  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180032ce4  lea     r8, aOnecoreuapEndu_9; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180032ceb  mov     edx, 95h; void *
0x180032cf0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
