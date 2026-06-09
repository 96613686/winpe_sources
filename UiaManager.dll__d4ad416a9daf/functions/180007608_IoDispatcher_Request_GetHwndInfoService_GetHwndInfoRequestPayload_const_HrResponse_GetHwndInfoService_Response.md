# IoDispatcher::Request<GetHwndInfoService>(GetHwndInfoRequestPayload const &,HrResponse<GetHwndInfoService::ResponsePayload> &,uint)

- ea: `0x180007608`
- end: `0x1800078be`
- name: `??$Request@UGetHwndInfoService@@@IoDispatcher@@QEAA?AW4ResponseStatus@@AEBUGetHwndInfoRequestPayload@@AEAU?$HrResponse@UResponsePayload@GetHwndInfoService@@@@I@Z`
- size: `694`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800078ec`

## callees

- `0x180007344`
- `0x180007608`
- `0x1800078c4`
- `0x180007a8c`
- `0x180007d14`
- `0x1800160fc`
- `0x18001d97c`
- `0x18001d9c4`
- `0x18001d9e4`
- `0x18002a514`
- `0x18002cc40`
- `0x180043a8c`
- `0x1800441ac`
- `0x18004b190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000764c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000764c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007788`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000765e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000765e`

## string_xrefs

- `0x1800078ac`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall IoDispatcher::Request<GetHwndInfoService>(__int64 a1, __int64 a2, _DWORD *a3)
{
  HANDLE Event; // rbx
  const char *v5; // r9
  char *v6; // rdi
  unsigned int *v7; // r13
  char *v8; // rsi
  std::_Ref_count_base *v9; // rbx
  void **v10; // r14
  void *v11; // rcx
  DWORD v12; // eax
  unsigned int v13; // r8d
  const char *v14; // r9
  unsigned int v15; // ebx
  __int128 v17; // [rsp+30h] [rbp-B1h] BYREF
  char *v18; // [rsp+40h] [rbp-A1h] BYREF
  std::_Ref_count_base *v19; // [rsp+48h] [rbp-99h]
  char *v20; // [rsp+50h] [rbp-91h]
  std::_Ref_count_base *v21; // [rsp+58h] [rbp-89h]
  _QWORD v22[2]; // [rsp+60h] [rbp-81h] BYREF
  _BYTE v23[24]; // [rsp+70h] [rbp-71h] BYREF
  char *v24; // [rsp+88h] [rbp-59h]
  char *v25; // [rsp+90h] [rbp-51h]
  char *v26; // [rsp+98h] [rbp-49h]
  char *v27; // [rsp+A0h] [rbp-41h]
  _BYTE v28[56]; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v29; // [rsp+E0h] [rbp-1h]
  __int128 v30; // [rsp+E8h] [rbp+7h]
  __int128 v31; // [rsp+F8h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+5Fh]

  v17 = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v5);
  GetLastError();
  _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Event);
  v6 = (char *)operator new(0x18u);
  *(_OWORD *)v6 = 0;
  *((_DWORD *)v6 + 2) = 1;
  *((_DWORD *)v6 + 3) = 1;
  *(_QWORD *)v6 = &std::_Ref_count_obj2<enum ResponseStatus>::`vftable';
  v7 = (unsigned int *)(v6 + 16);
  *((_DWORD *)v6 + 4) = 2;
  v24 = v6 + 16;
  v25 = v6;
  v8 = (char *)operator new(0xA0u);
  *(_OWORD *)v8 = 0;
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 3) = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<HrResponse<GetHwndInfoService::ResponsePayload>>::`vftable';
  memset_0(v8 + 16, 0, 0x90u);
  *((_QWORD *)v8 + 7) = 7;
  v26 = v8 + 16;
  v27 = v8;
  _InterlockedAdd((volatile signed __int32 *)v8 + 3, 1u);
  _InterlockedAdd((volatile signed __int32 *)v6 + 3, 1u);
  v18 = v6 + 16;
  v19 = (std::_Ref_count_base *)v6;
  v30 = 0;
  v20 = v8 + 16;
  v21 = (std::_Ref_count_base *)v8;
  v31 = 0;
  v9 = (std::_Ref_count_base *)*((_QWORD *)&v17 + 1);
  if ( *((_QWORD *)&v17 + 1) )
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 1u);
  v10 = (void **)v17;
  v22[0] = v17;
  v22[1] = v9;
  v29 = 0;
  v29 = std::_Func_impl_no_alloc<_lambda_3bd3959c9e18b522a12097649a662f1a_,void,enum ResponseStatus,HrResponse<GetHwndInfoService::ResponsePayload>>::_Func_impl_no_alloc<_lambda_3bd3959c9e18b522a12097649a662f1a_,void,enum ResponseStatus,HrResponse<GetHwndInfoService::ResponsePayload>>(
          v28,
          &v18);
  IoDispatcher::RequestAsync<GetHwndInfoService>(a1, v23, a2, v28, v8);
  if ( v10 )
    v11 = *v10;
  else
    v11 = 0;
  v12 = WaitForSingleObjectEx(v11, 0x1388u, 0);
  if ( v12 == 258 )
  {
    IoDispatcher::RequestGuard::~RequestGuard((IoDispatcher::RequestGuard *)v23);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v22);
    if ( v21 )
      std::_Ref_count_base::_Decwref(v21);
    if ( v19 )
      std::_Ref_count_base::_Decwref(v19);
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v8);
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    return 1;
  }
  else
  {
    if ( v12 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v13, v14);
    v15 = *v7;
    if ( *v7 )
    {
      IoDispatcher::RequestGuard::~RequestGuard((IoDispatcher::RequestGuard *)v23);
      _lambda_94b77262ebff4f65993754fe9ef6d8c7_::~_lambda_94b77262ebff4f65993754fe9ef6d8c7_((_lambda_94b77262ebff4f65993754fe9ef6d8c7_ *)&v18);
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v8);
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
      std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v17);
      return v15;
    }
    else
    {
      *a3 = *((_DWORD *)v8 + 4);
      GetHwndInfoService::ResponsePayload::operator=(a3 + 2, v8 + 24);
      IoDispatcher::RequestGuard::~RequestGuard((IoDispatcher::RequestGuard *)v23);
      _lambda_94b77262ebff4f65993754fe9ef6d8c7_::~_lambda_94b77262ebff4f65993754fe9ef6d8c7_((_lambda_94b77262ebff4f65993754fe9ef6d8c7_ *)&v18);
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v8);
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
      std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v17);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180007608  mov     rax, rsp
0x18000760b  mov     [rax+18h], rbx
0x18000760f  mov     [rax+10h], rdx
0x180007613  mov     [rax+8], rcx
0x180007617  push    rbp
0x180007618  push    rsi
0x180007619  push    rdi
0x18000761a  push    r12
0x18000761c  push    r13
0x18000761e  push    r14
0x180007620  push    r15
0x180007622  lea     rbp, [rax-5Fh]
0x180007626  sub     rsp, 100h
0x18000762d  mov     r12, r8
0x180007630  xorps   xmm0, xmm0
0x180007633  movdqu  [rsp+130h+var_110+8], xmm0
0x180007639  mov     r9d, 1F0003h; dwDesiredAccess
0x18000763f  mov     r14d, 1
0x180007645  mov     r8d, r14d; dwFlags
0x180007648  xor     edx, edx; lpName
0x18000764a  xor     ecx, ecx; lpEventAttributes
0x18000764c  call    cs:__imp_CreateEventExW
0x180007652  mov     rbx, rax
0x180007655  test    rax, rax
0x180007658  jz      loc_1800078A8
0x18000765e  call    cs:__imp_GetLastError
0x180007664  mov     rdx, rbx
0x180007667  lea     rcx, [rsp+130h+var_110+8]
0x18000766c  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x180007671  nop
0x180007672  lea     ecx, [r14+17h]; Size
0x180007676  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000767b  mov     rdi, rax
0x18000767e  mov     qword ptr [rsp+130h+var_110], rax
0x180007683  xorps   xmm0, xmm0
0x180007686  movups  xmmword ptr [rax], xmm0
0x180007689  mov     [rax+8], r14d
0x18000768d  mov     [rax+0Ch], r14d
0x180007691  lea     rax, ??_7?$_Ref_count_obj2@W4ResponseStatus@@@std@@6B@; const std::_Ref_count_obj2<ResponseStatus>::`vftable'
0x180007698  mov     [rdi], rax
0x18000769b  lea     r13, [rdi+10h]
0x18000769f  mov     dword ptr [r13+0], 2
0x1800076a7  mov     [rbp+57h+var_B0], r13
0x1800076ab  mov     [rbp+57h+var_A8], rdi
0x1800076af  mov     ecx, 0A0h; Size
0x1800076b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800076b9  mov     rsi, rax
0x1800076bc  mov     qword ptr [rsp+130h+var_110], rax
0x1800076c1  xorps   xmm0, xmm0
0x1800076c4  movups  xmmword ptr [rax], xmm0
0x1800076c7  mov     [rax+8], r14d
0x1800076cb  mov     [rax+0Ch], r14d
0x1800076cf  lea     rax, ??_7?$_Ref_count_obj2@U?$HrResponse@UResponsePayload@GetHwndInfoService@@@@@std@@6B@; const std::_Ref_count_obj2<HrResponse<GetHwndInfoService::ResponsePayload>>::`vftable'
0x1800076d6  mov     [rsi], rax
0x1800076d9  lea     r15, [rsi+10h]
0x1800076dd  xor     edx, edx; Val
0x1800076df  mov     r8d, 90h; Size
0x1800076e5  mov     rcx, r15; void *
0x1800076e8  call    memset_0
0x1800076ed  mov     qword ptr [r15+28h], 7
0x1800076f5  mov     [rbp+57h+var_A0], r15
0x1800076f9  mov     [rbp+57h+var_98], rsi
0x1800076fd  lock add [rsi+0Ch], r14d
0x180007702  lock add [rdi+0Ch], r14d
0x180007707  mov     [rsp+130h+var_F8], r13
0x18000770c  mov     [rsp+130h+var_F0], rdi
0x180007711  xorps   xmm0, xmm0
0x180007714  movdqu  [rbp+57h+var_50], xmm0
0x180007719  mov     [rsp+130h+var_E8], r15
0x18000771e  mov     [rsp+130h+var_E0], rsi
0x180007723  movdqu  [rbp+57h+var_40], xmm0
0x180007728  mov     rbx, [rsp+130h+var_100]
0x18000772d  test    rbx, rbx
0x180007730  jz      short loc_180007737
0x180007732  lock add [rbx+8], r14d
0x180007737  mov     r14, qword ptr [rsp+130h+var_110+8]
0x18000773c  mov     [rsp+58h], r14
0x180007741  mov     [rbp+57h+var_D0], rbx
0x180007745  mov     [rbp+57h+var_58], 0
0x18000774d  lea     rdx, [rsp+130h+var_F8]
0x180007752  lea     rcx, [rbp+57h+var_90]
0x180007756  call    ??$?0V_lambda_3bd3959c9e18b522a12097649a662f1a_@@$0A@@?$_Func_impl_no_alloc@V_lambda_3bd3959c9e18b522a12097649a662f1a_@@XW4ResponseStatus@@U?$HrResponse@UResponsePayload@GetHwndInfoService@@@@@std@@QEAA@$$QEAV_lambda_3bd3959c9e18b522a12097649a662f1a_@@@Z; std::_Func_impl_no_alloc<_lambda_3bd3959c9e18b522a12097649a662f1a_,void,ResponseStatus,HrResponse<GetHwndInfoService::ResponsePayload>>::_Func_impl_no_alloc<_lambda_3bd3959c9e18b522a12097649a662f1a_,void,ResponseStatus,HrResponse<GetHwndInfoService::ResponsePayload>>(_lambda_3bd3959c9e18b522a12097649a662f1a_ &&)
0x18000775b  mov     [rbp+57h+var_58], rax
0x18000775f  lea     r9, [rbp+57h+var_90]
0x180007763  mov     r8, [rbp+57h+arg_8]
0x180007767  lea     rdx, [rbp+57h+var_C8]
0x18000776b  mov     rcx, [rbp+57h+arg_0]
0x18000776f  call    ??$RequestAsync@UGetHwndInfoService@@@IoDispatcher@@QEAA?AVRequestGuard@0@AEBUGetHwndInfoRequestPayload@@V?$function@$$A6AXW4ResponseStatus@@U?$HrResponse@UResponsePayload@GetHwndInfoService@@@@@Z@std@@@Z; IoDispatcher::RequestAsync<GetHwndInfoService>(GetHwndInfoRequestPayload const &,std::function<void (ResponseStatus,HrResponse<GetHwndInfoService::ResponsePayload>)>)
0x180007774  test    r14, r14
0x180007777  jz      short loc_18000777E
0x180007779  mov     rcx, [r14]
0x18000777c  jmp     short loc_180007780
0x18000777e  xor     ecx, ecx; hHandle
0x180007780  xor     r8d, r8d; bAlertable
0x180007783  mov     edx, 1388h; dwMilliseconds
0x180007788  call    cs:__imp_WaitForSingleObjectEx
0x18000778e  cmp     eax, 102h
0x180007793  jz      loc_18000784C
0x180007799  test    eax, eax
0x18000779b  jz      short loc_1800077AC
0x18000779d  mov     rcx, [rbp+5Fh]; this
0x1800077a1  mov     edx, 0B0Fh; void *
0x1800077a6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800077ac  mov     ebx, [r13+0]
0x1800077b0  test    ebx, ebx
0x1800077b2  jnz     short loc_180007817
0x1800077b4  mov     eax, [r15]
0x1800077b7  mov     [r12], eax
0x1800077bb  lea     rdx, [r15+8]
0x1800077bf  lea     rcx, [r12+8]
0x1800077c4  call    ??4ResponsePayload@GetHwndInfoService@@QEAAAEAU01@$$QEAU01@@Z; GetHwndInfoService::ResponsePayload::operator=(GetHwndInfoService::ResponsePayload &&)
0x1800077c9  lea     rcx, [rbp+57h+var_C8]; this
0x1800077cd  call    ??1RequestGuard@IoDispatcher@@QEAA@XZ; IoDispatcher::RequestGuard::~RequestGuard(void)
0x1800077d2  nop
0x1800077d3  lea     rcx, [rsp+130h+var_F8]; this
0x1800077d8  call    ??1_lambda_94b77262ebff4f65993754fe9ef6d8c7_@@QEAA@XZ; _lambda_94b77262ebff4f65993754fe9ef6d8c7_::~_lambda_94b77262ebff4f65993754fe9ef6d8c7_(void)
0x1800077dd  nop
0x1800077de  mov     rcx, rsi; this
0x1800077e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800077e6  nop
0x1800077e7  mov     rcx, rdi; this
0x1800077ea  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800077ef  nop
0x1800077f0  lea     rcx, [rsp+130h+var_110+8]
0x1800077f5  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x1800077fa  xor     eax, eax
0x1800077fc  mov     rbx, [rsp+130h+arg_10]
0x180007804  add     rsp, 100h
0x18000780b  pop     r15
0x18000780d  pop     r14
0x18000780f  pop     r13
0x180007811  pop     r12
0x180007813  pop     rdi
0x180007814  pop     rsi
0x180007815  pop     rbp
0x180007816  retn
0x180007817  lea     rcx, [rbp+57h+var_C8]; this
0x18000781b  call    ??1RequestGuard@IoDispatcher@@QEAA@XZ; IoDispatcher::RequestGuard::~RequestGuard(void)
0x180007820  nop
0x180007821  lea     rcx, [rsp+130h+var_F8]; this
0x180007826  call    ??1_lambda_94b77262ebff4f65993754fe9ef6d8c7_@@QEAA@XZ; _lambda_94b77262ebff4f65993754fe9ef6d8c7_::~_lambda_94b77262ebff4f65993754fe9ef6d8c7_(void)
0x18000782b  nop
0x18000782c  mov     rcx, rsi; this
0x18000782f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180007834  nop
0x180007835  mov     rcx, rdi; this
0x180007838  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000783d  nop
0x18000783e  lea     rcx, [rsp+130h+var_110+8]
0x180007843  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x180007848  mov     eax, ebx
0x18000784a  jmp     short loc_1800077FC
0x18000784c  lea     rcx, [rbp+57h+var_C8]; this
0x180007850  call    ??1RequestGuard@IoDispatcher@@QEAA@XZ; IoDispatcher::RequestGuard::~RequestGuard(void)
0x180007855  nop
0x180007856  lea     rcx, [rsp+58h]
0x18000785b  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x180007860  mov     rcx, [rsp+130h+var_E0]; this
0x180007865  test    rcx, rcx
0x180007868  jz      short loc_18000786F
0x18000786a  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000786f  mov     rcx, [rsp+130h+var_F0]; this
0x180007874  test    rcx, rcx
0x180007877  jz      short loc_18000787F
0x180007879  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000787e  nop
0x18000787f  mov     rcx, rsi; this
0x180007882  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180007887  nop
0x180007888  mov     rcx, rdi; this
0x18000788b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180007890  nop
0x180007891  test    rbx, rbx
0x180007894  jz      short loc_18000789E
0x180007896  mov     rcx, rbx; this
0x180007899  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000789e  mov     eax, 1
0x1800078a3  jmp     loc_1800077FC
0x1800078a8  mov     rcx, [rbp+5Fh]; this
0x1800078ac  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800078b3  mov     edx, 1CC8h; void *
0x1800078b8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
