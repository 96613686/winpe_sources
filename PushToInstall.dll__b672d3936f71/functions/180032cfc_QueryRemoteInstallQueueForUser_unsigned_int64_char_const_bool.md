# QueryRemoteInstallQueueForUser(unsigned __int64,char const *,bool &)

- ea: `0x180032cfc`
- end: `0x180032fa5`
- name: `?QueryRemoteInstallQueueForUser@@YAX_KPEBDAEA_N@Z`
- size: `681`
- prototype: `void __fastcall(__int64, const char *, bool *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18002f800`

## callees

- `0x180002b50`
- `0x18000d75c`
- `0x180022810`
- `0x18002c4b8`
- `0x180030a68`
- `0x180031cb8`
- `0x180031d28`
- `0x180031dd4`
- `0x180031f1c`
- `0x1800322d8`
- `0x180032cfc`
- `0x180034e24`
- `0x1800354bc`
- `0x18003571c`
- `0x180035e4c`
- `0x180036ec8`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180032ddd`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180032ddd`

## string_xrefs

- `0x180032e78`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x180032f20`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x180032f7f`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x180032e6b`: `QueryRemoteInstallQueueForUser`
- `0x180032f13`: `QueryRemoteInstallQueueForUser`
- `0x180032eff`: `No storeIds returned to install.`
- `0x180032f91`: `onecoreuap\enduser\winstore\pushtoinstall\lib\nexus.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall QueryRemoteInstallQueueForUser(__int64 a1, const char *a2, bool *a3)
{
  bool *v3; // rdi
  struct HttpRequest *v4; // rbx
  const char *v5; // r9
  _QWORD *v6; // rax
  const char *v7; // r9
  _QWORD *v8; // rax
  __int64 v9; // r8
  __int64 v10; // [rsp+30h] [rbp-68h] BYREF
  __int128 v11; // [rsp+38h] [rbp-60h] BYREF
  struct HttpRequest *v12; // [rsp+48h] [rbp-50h]
  const wil::ResultException *v13; // [rsp+50h] [rbp-48h] BYREF
  __int128 v14; // [rsp+58h] [rbp-40h] BYREF
  __int128 v15; // [rsp+68h] [rbp-30h] BYREF
  __int64 v16; // [rsp+78h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v19; // [rsp+B8h] [rbp+20h] BYREF

  v3 = a3;
  *a3 = 0;
  v4 = ((struct TraceLoggingCorrelationVector *(__fastcall *)(const char *, bool))TraceLoggingCorrelationVector::Extend)(
         a2,
         (bool)a2);
  v12 = v4;
  if ( !v4 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
      v5);
  v15 = 0;
  v16 = 0;
  v19 = 0;
  v14 = 0;
  v6 = operator new(0x68u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *(_QWORD *)&v14 = v6;
  while ( 2 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      GatherAllAccountTickets(&v15, &v19);
      if ( (__int64)(*((_QWORD *)&v15 + 1) - v15) >> 6 )
      {
        CreatePTIQueryRequestBody(&v11, (unsigned __int64 **)&v15);
        if ( !InitOnceExecuteOnce(&InitOnce, (PINIT_ONCE_FN)Nexus::InitializeOnce, &g_nexus, 0) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x49,
            (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\nexus.cpp",
            v7);
        MakePostRequest((struct TraceLoggingCorrelationVector *)&v10, v4);
        PTIUtils::ParseStoreIds(&v10, &v14, v3);
        if ( v10 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 192LL))(v10, 1);
        if ( (_QWORD)v11 )
          (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v11 + 192LL))(v11, 1);
      }
      else
      {
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
          0x6Cu,
          "QueryRemoteInstallQueueForUser",
          -1,
          L"Found no MSAs, no work to do.");
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &wil::ResultException `RTTI Type Descriptor', &v13) )
      {
        if ( *((_DWORD *)v13 + 8) != -2145844847 )
        {
          v4 = v12;
          __eh34_try_continuation(0, &wil::ResultException `RTTI Type Descriptor', &loc_180032E9D);
          break;
        }
        InvalidateCachedTokens(&v19);
        v3 = a3;
        v4 = v12;
        __eh34_try_continuation(0, &wil::ResultException `RTTI Type Descriptor', &loc_180032E8B);
        continue;
      }
    }
    break;
  }
  if ( *((_QWORD *)&v14 + 1) )
  {
    v11 = 0;
    v8 = operator new(0x48u);
    *v8 = v8;
    v8[1] = v8;
    v8[2] = v8;
    *((_WORD *)v8 + 12) = 257;
    *(_QWORD *)&v11 = v8;
    InstallItems(v4, (__int64 ***)&v14, v9, &v11);
    QueryPTIServiceToRemoveStoreIds(v4, &v11);
    std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>(&v11);
  }
  else
  {
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
      0x89u,
      "QueryRemoteInstallQueueForUser",
      -1,
      L"No storeIds returned to install.");
  }
  std::_Tree<std::_Tmap_traits<std::wstring,ProductInstallRequest,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ProductInstallRequest>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ProductInstallRequest,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ProductInstallRequest>>,0>>((void **)&v14);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  std::vector<StoredTicket>::~vector<StoredTicket>(&v15);
  if ( v4 )
    operator delete(v4, (const struct std::nothrow_t *)0x90);
}

```

## disassembly

```asm
0x180032cfc  mov     [rsp+arg_10], r8
0x180032d01  mov     [rsp+arg_0], rcx
0x180032d06  push    rbx
0x180032d07  push    rsi
0x180032d08  push    rdi
0x180032d09  sub     rsp, 80h
0x180032d10  mov     rdi, r8
0x180032d13  mov     byte ptr [r8], 0
0x180032d17  mov     rcx, rdx; char *
0x180032d1a  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x180032d1f  mov     rbx, rax
0x180032d22  mov     [rsp+98h+var_50], rax
0x180032d27  mov     rcx, [rsp+98h]; this
0x180032d2f  test    rax, rax
0x180032d32  jz      loc_180032F7F
0x180032d38  xorps   xmm0, xmm0
0x180032d3b  movdqu  [rsp+98h+var_30], xmm0
0x180032d41  mov     [rsp+98h+var_20], 0
0x180032d4a  mov     [rsp+98h+arg_18], 0
0x180032d56  movdqu  [rsp+98h+var_40], xmm0
0x180032d5c  mov     ecx, 68h ; 'h'; Size
0x180032d61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032d66  mov     [rax], rax
0x180032d69  mov     [rax+8], rax
0x180032d6d  mov     [rax+10h], rax
0x180032d71  mov     word ptr [rax+18h], 101h
0x180032d77  mov     qword ptr [rsp+98h+var_40], rax
0x180032d7c  mov     byte ptr [rsp+98h+arg_0], 0
0x180032d84  lea     rdx, [rsp+98h+arg_18]
0x180032d8c  lea     rcx, [rsp+98h+var_30]
0x180032d91  call    ?GatherAllAccountTickets@@YAXAEAV?$vector@UStoredTicket@@V?$allocator@UStoredTicket@@@std@@@std@@AEAV?$ComPtr@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; GatherAllAccountTickets(std::vector<StoredTicket> &,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<IInspectable *>> &)
0x180032d96  mov     rax, qword ptr [rsp+98h+var_30+8]
0x180032d9b  sub     rax, qword ptr [rsp+98h+var_30]
0x180032da0  sar     rax, 6
0x180032da4  test    rax, rax
0x180032da7  jz      loc_180032E57
0x180032dad  lea     rdx, [rsp+98h+var_30]
0x180032db2  lea     rcx, [rsp+98h+var_60]
0x180032db7  call    ?CreatePTIQueryRequestBody@@YA?AVvalue@json@web@@AEBV?$vector@UStoredTicket@@V?$allocator@UStoredTicket@@@std@@@std@@@Z; CreatePTIQueryRequestBody(std::vector<StoredTicket> const &)
0x180032dbc  nop
0x180032dbd  mov     rsi, [rsp+98h]
0x180032dc5  xor     r9d, r9d; Context
0x180032dc8  lea     r8, ?g_nexus@@3VNexus@@A; Parameter
0x180032dcf  lea     rdx, ?InitializeOnce@Nexus@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180032dd6  lea     rcx, InitOnce; InitOnce
0x180032ddd  call    cs:__imp_InitOnceExecuteOnce
0x180032de3  test    eax, eax
0x180032de5  jz      loc_180032F91
0x180032deb  lea     r9, [rsp+98h+var_60]
0x180032df0  lea     r8, qword_1800664D0
0x180032df7  mov     rdx, rbx
0x180032dfa  lea     rcx, [rsp+98h+var_68]
0x180032dff  call    ?MakePostRequest@@YA?AVvalue@json@web@@PEAVTraceLoggingCorrelationVector@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV123@@Z; MakePostRequest(TraceLoggingCorrelationVector *,std::wstring const &,web::json::value const &)
0x180032e04  nop
0x180032e05  mov     r8, rdi
0x180032e08  lea     rdx, [rsp+98h+var_40]
0x180032e0d  lea     rcx, [rsp+98h+var_68]
0x180032e12  call    ?ParseStoreIds@PTIUtils@@YAXAEBVvalue@json@web@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@@std@@@2@@std@@AEA_N@Z; PTIUtils::ParseStoreIds(web::json::value const &,std::map<std::wstring,ProductInstallRequest> &,bool &)
0x180032e17  nop
0x180032e18  mov     rcx, [rsp+98h+var_68]
0x180032e1d  test    rcx, rcx
0x180032e20  jz      short loc_180032E37
0x180032e22  mov     rax, [rcx]
0x180032e25  mov     edx, 1
0x180032e2a  mov     rax, [rax+0C0h]
0x180032e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e36  nop
0x180032e37  mov     rcx, qword ptr [rsp+98h+var_60]
0x180032e3c  test    rcx, rcx
0x180032e3f  jz      short loc_180032E89
0x180032e41  mov     rax, [rcx]
0x180032e44  mov     edx, 1
0x180032e49  mov     rax, [rax+0C0h]
0x180032e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e55  jmp     short loc_180032E89
0x180032e57  lea     rax, aFoundNoMsasNoW; "Found no MSAs, no work to do."
0x180032e5e  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x180032e63  mov     [rsp+98h+var_78], 0FFFFFFFFh; int
0x180032e6b  lea     r9, aQueryremoteins_0; "QueryRemoteInstallQueueForUser"
0x180032e72  mov     r8d, 6Ch ; 'l'; unsigned int
0x180032e78  lea     rdx, aOnecoreuapEndu_9; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180032e7f  lea     ecx, [r8-69h]; unsigned int
0x180032e83  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x180032e88  nop
0x180032e89  jmp     short loc_180032EA2
0x180032e8b  mov     rdi, [rsp+98h+arg_10]
0x180032e93  mov     rbx, [rsp+98h+var_50]
0x180032e98  jmp     loc_180032D84
0x180032e9d  mov     rbx, [rsp+98h+var_50]
0x180032ea2  cmp     qword ptr [rsp+98h+var_40+8], 0
0x180032ea8  jbe     short loc_180032EFF
0x180032eaa  xorps   xmm0, xmm0
0x180032ead  movdqu  [rsp+98h+var_60], xmm0
0x180032eb3  mov     ecx, 48h ; 'H'; Size
0x180032eb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032ebd  mov     [rax], rax
0x180032ec0  mov     [rax+8], rax
0x180032ec4  mov     [rax+10h], rax
0x180032ec8  mov     word ptr [rax+18h], 101h
0x180032ece  mov     qword ptr [rsp+98h+var_60], rax
0x180032ed3  lea     r9, [rsp+98h+var_60]
0x180032ed8  lea     rdx, [rsp+98h+var_40]
0x180032edd  mov     rcx, rbx; this
0x180032ee0  call    ?InstallItems@@YAXPEAVTraceLoggingCorrelationVector@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@@std@@@2@@std@@_KAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@3@@Z; InstallItems(TraceLoggingCorrelationVector *,std::map<std::wstring,ProductInstallRequest> const &,unsigned __int64,std::map<std::wstring,long> &)
0x180032ee5  lea     rdx, [rsp+98h+var_60]
0x180032eea  mov     rcx, rbx
0x180032eed  call    ?QueryPTIServiceToRemoveStoreIds@@YAXPEAVTraceLoggingCorrelationVector@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@@Z; QueryPTIServiceToRemoveStoreIds(TraceLoggingCorrelationVector *,std::map<std::wstring,long> const &)
0x180032ef2  nop
0x180032ef3  lea     rcx, [rsp+98h+var_60]
0x180032ef8  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>(void)
0x180032efd  jmp     short loc_180032F32
0x180032eff  lea     rax, aNoStoreidsRetu; "No storeIds returned to install."
0x180032f06  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x180032f0b  mov     [rsp+98h+var_78], 0FFFFFFFFh; int
0x180032f13  lea     r9, aQueryremoteins_0; "QueryRemoteInstallQueueForUser"
0x180032f1a  mov     r8d, 89h; unsigned int
0x180032f20  lea     rdx, aOnecoreuapEndu_9; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180032f27  mov     ecx, 3; unsigned int
0x180032f2c  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x180032f31  nop
0x180032f32  lea     rcx, [rsp+98h+var_40]
0x180032f37  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ProductInstallRequest,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ProductInstallRequest>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ProductInstallRequest,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ProductInstallRequest>>,0>>(void)
0x180032f3c  nop
0x180032f3d  mov     rcx, [rsp+98h+arg_18]
0x180032f45  test    rcx, rcx
0x180032f48  jz      short loc_180032F57
0x180032f4a  mov     rax, [rcx]
0x180032f4d  mov     rax, [rax+10h]
0x180032f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f56  nop
0x180032f57  lea     rcx, [rsp+98h+var_30]
0x180032f5c  call    ??1?$vector@UStoredTicket@@V?$allocator@UStoredTicket@@@std@@@std@@QEAA@XZ; std::vector<StoredTicket>::~vector<StoredTicket>(void)
0x180032f61  nop
0x180032f62  test    rbx, rbx
0x180032f65  jz      short loc_180032F74
0x180032f67  mov     edx, 90h; struct std::nothrow_t *
0x180032f6c  mov     rcx, rbx; void *
0x180032f6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032f74  add     rsp, 80h
0x180032f7b  pop     rdi
0x180032f7c  pop     rsi
0x180032f7d  pop     rbx
0x180032f7e  retn
0x180032f7f  lea     r8, aOnecoreuapEndu_9; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180032f86  mov     edx, 57h ; 'W'; void *
0x180032f8b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180032f91  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180032f98  lea     edx, [rax+49h]; void *
0x180032f9b  mov     rcx, rsi; this
0x180032f9e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
