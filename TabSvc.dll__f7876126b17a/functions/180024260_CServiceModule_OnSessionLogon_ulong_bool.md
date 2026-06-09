# CServiceModule::OnSessionLogon(ulong,bool)

- ea: `0x180024260`
- end: `0x180024459`
- name: `?OnSessionLogon@CServiceModule@@QEAAXK_N@Z`
- size: `505`
- prototype: `void __fastcall(CServiceModule *Context, ULONG, char)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18000fa00`

## callees

- `0x180001ec0`
- `0x180012560`
- `0x180013950`
- `0x1800141d4`
- `0x18001506c`
- `0x180015630`
- `0x1800186a0`
- `0x1800186c0`
- `0x18001a570`
- `0x18001a610`
- `0x180024260`
- `0x1800282a0`
- `0x180028578`
- `0x1800286b0`
- `0x180028a24`
- `0x18002b3a8`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024333`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024333`
- `WTSAPI32!WTSQueryUserToken` at `0x180024314`
- `WTSAPI32!WTSQueryUserToken` at `0x180024314`

## string_xrefs

- `0x180024444`: `drivers\tablet\platform\pen\penservice\penservice.cpp`
- `0x1800242ae`: `PENSERVICE_CServiceModule::OnSessionLogon`
- `0x1800243ad`: `PENSERVICE_CServiceModule::OnSessionLogon`
- `0x18002440c`: `PENSERVICE_CServiceModule::OnSessionLogon`

## pseudocode

```c
void __fastcall CServiceModule::OnSessionLogon(CServiceModule *Context, ULONG a2, char a3)
{
  const char *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  struct CPenSession *v10; // rax
  struct CPenSession *v11; // rbx
  int v12; // [rsp+20h] [rbp-38h]
  HLOCAL hMem; // [rsp+40h] [rbp-18h] BYREF
  void *phToken[2]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  ULONG v16; // [rsp+A8h] [rbp+50h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_59994706>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x895,
      (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
      v6);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      101,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnSessionLogon");
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v16 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v7,
      (int)word_18003A3B2,
      v8,
      v9,
      (__int64)&v16);
  }
  hMem = 0;
  phToken[0] = 0;
  if ( WTSQueryUserToken(a2, phToken) )
  {
    hMem = 0;
    GetLogonSessionSid(phToken[0], (LPWSTR *)&hMem);
  }
  if ( IsWizardOnlyAccount((const unsigned __int16 *)hMem) || !a3 || !CServiceModule::_DelayStartTabtip(Context, a2) )
  {
    v10 = CServiceModule::EnsurePenSession(Context, a2);
    v11 = v10;
    if ( v10 && *((_BYTE *)v10 + 9) )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_sd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          102,
          (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          (unsigned int)"PENSERVICE_CServiceModule::OnSessionLogon",
          *((_DWORD *)v10 + 1));
      CServiceModule::_RemovePenProcessesWorker(Context, 1, 0x28u, *((_DWORD *)v11 + 1));
      *((_BYTE *)v11 + 9) = 0;
    }
    CServiceModule::_StartPenProcessesWorker(Context, a2, 0, 0, v12, 0);
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      103,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnSessionLogon");
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(phToken);
}

```

## disassembly

```asm
0x180024260  push    rbp
0x180024262  push    rbx
0x180024263  push    rsi
0x180024264  push    rdi
0x180024265  push    r13
0x180024267  push    r14
0x180024269  mov     rbp, rsp
0x18002426c  sub     rsp, 58h
0x180024270  mov     r14b, r8b
0x180024273  mov     edi, edx
0x180024275  mov     rsi, rcx
0x180024278  mov     rbx, [rbp+30h]
0x18002427c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_59994706@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59994706@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_59994706>::GetImpl(void)'::`2'::impl
0x180024283  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59994706@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::__private_IsEnabled(void)
0x180024288  test    al, al
0x18002428a  jnz     loc_180024444
0x180024290  lea     r13, WPP_GLOBAL_Control
0x180024297  mov     rcx, cs:WPP_GLOBAL_Control
0x18002429e  cmp     rcx, r13
0x1800242a1  jz      short loc_1800242C5
0x1800242a3  test    byte ptr [rcx+1Ch], 10h
0x1800242a7  jz      short loc_1800242C5
0x1800242a9  mov     edx, 65h ; 'e'
0x1800242ae  lea     r9, aPenserviceCser_11; "PENSERVICE_CServiceModule::OnSessionLog"...
0x1800242b5  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800242bc  mov     rcx, [rcx+10h]
0x1800242c0  call    WPP_SF_s
0x1800242c5  mov     eax, cs:dword_1800411A8
0x1800242cb  cmp     eax, 5
0x1800242ce  jbe     short loc_1800242FE
0x1800242d0  mov     edx, 4000000h
0x1800242d5  lea     rcx, dword_1800411A8
0x1800242dc  call    _tlgKeywordOn
0x1800242e1  test    al, al
0x1800242e3  jz      short loc_1800242FE
0x1800242e5  mov     [rbp+arg_18], edi
0x1800242e8  lea     rax, [rbp+arg_18]
0x1800242ec  mov     qword ptr [rsp+58h+var_38], rax
0x1800242f1  lea     rdx, word_18003A3B2
0x1800242f8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800242fd  nop
0x1800242fe  mov     [rbp+hMem], 0
0x180024306  mov     [rbp+phToken], 0
0x18002430e  lea     rdx, [rbp+phToken]; phToken
0x180024312  mov     ecx, edi; SessionId
0x180024314  call    cs:__imp_WTSQueryUserToken
0x18002431a  test    eax, eax
0x18002431c  jz      short loc_180024357
0x18002431e  mov     rbx, [rbp+hMem]
0x180024322  test    rbx, rbx
0x180024325  jz      short loc_180024342
0x180024327  lea     rcx, [rbp+arg_18]; this
0x18002432b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180024330  mov     rcx, rbx; hMem
0x180024333  call    cs:__imp_LocalFree
0x180024339  lea     rcx, [rbp+arg_18]; this
0x18002433d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180024342  mov     [rbp+hMem], 0
0x18002434a  lea     rdx, [rbp+hMem]; StringSid
0x18002434e  mov     rcx, [rbp+phToken]; TokenHandle
0x180024352  call    ?GetLogonSessionSid@@YAJPEAXPEAPEAG@Z; GetLogonSessionSid(void *,ushort * *)
0x180024357  mov     rcx, [rbp+hMem]; unsigned __int16 *
0x18002435b  call    ?IsWizardOnlyAccount@@YA_NPEBG@Z; IsWizardOnlyAccount(ushort const *)
0x180024360  test    al, al
0x180024362  jnz     short loc_180024377
0x180024364  test    r14b, r14b
0x180024367  jz      short loc_180024377
0x180024369  mov     edx, edi; unsigned int
0x18002436b  mov     rcx, rsi; this
0x18002436e  call    ?_DelayStartTabtip@CServiceModule@@AEAA_NK@Z; CServiceModule::_DelayStartTabtip(ulong)
0x180024373  test    al, al
0x180024375  jnz     short loc_1800243F5
0x180024377  mov     edx, edi; unsigned int
0x180024379  mov     rcx, rsi; this
0x18002437c  call    ?EnsurePenSession@CServiceModule@@QEAAPEAVCPenSession@@K@Z; CServiceModule::EnsurePenSession(ulong)
0x180024381  mov     rbx, rax
0x180024384  test    rax, rax
0x180024387  jz      short loc_1800243DD
0x180024389  cmp     byte ptr [rax+9], 0
0x18002438d  jz      short loc_1800243DD
0x18002438f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024396  cmp     rcx, r13
0x180024399  jz      short loc_1800243C4
0x18002439b  test    byte ptr [rcx+1Ch], 10h
0x18002439f  jz      short loc_1800243C4
0x1800243a1  mov     edx, 66h ; 'f'
0x1800243a6  mov     eax, [rax+4]
0x1800243a9  mov     [rsp+58h+var_38], eax; int
0x1800243ad  lea     r9, aPenserviceCser_11; "PENSERVICE_CServiceModule::OnSessionLog"...
0x1800243b4  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800243bb  mov     rcx, [rcx+10h]
0x1800243bf  call    WPP_SF_sd
0x1800243c4  mov     r9d, [rbx+4]; unsigned int
0x1800243c8  mov     edx, 1; unsigned int
0x1800243cd  lea     r8d, [rdx+27h]; unsigned int
0x1800243d1  mov     rcx, rsi; this
0x1800243d4  call    ?_RemovePenProcessesWorker@CServiceModule@@AEAAXKKK@Z; CServiceModule::_RemovePenProcessesWorker(ulong,ulong,ulong)
0x1800243d9  mov     byte ptr [rbx+9], 0
0x1800243dd  mov     [rsp+58h+var_30], 0; int
0x1800243e5  xor     r9d, r9d; int
0x1800243e8  xor     r8d, r8d; enum _WTS_CONNECTSTATE_CLASS
0x1800243eb  mov     edx, edi; unsigned int
0x1800243ed  mov     rcx, rsi; Context
0x1800243f0  call    ?_StartPenProcessesWorker@CServiceModule@@AEAAXKW4_WTS_CONNECTSTATE_CLASS@@HHHH@Z; CServiceModule::_StartPenProcessesWorker(ulong,_WTS_CONNECTSTATE_CLASS,int,int,int,int)
0x1800243f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243fc  cmp     rcx, r13
0x1800243ff  jz      short loc_180024424
0x180024401  test    byte ptr [rcx+1Ch], 10h
0x180024405  jz      short loc_180024424
0x180024407  mov     edx, 67h ; 'g'
0x18002440c  lea     r9, aPenserviceCser_11; "PENSERVICE_CServiceModule::OnSessionLog"...
0x180024413  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18002441a  mov     rcx, [rcx+10h]
0x18002441e  call    WPP_SF_s
0x180024423  nop
0x180024424  lea     rcx, [rbp+hMem]
0x180024428  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002442d  nop
0x18002442e  lea     rcx, [rbp+phToken]
0x180024432  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024437  add     rsp, 58h
0x18002443b  pop     r14
0x18002443d  pop     r13
0x18002443f  pop     rdi
0x180024440  pop     rsi
0x180024441  pop     rbx
0x180024442  pop     rbp
0x180024443  retn
0x180024444  lea     r8, aDriversTabletP_1; "drivers\\tablet\\platform\\pen\\penserv"...
0x18002444b  mov     edx, 895h; void *
0x180024450  mov     rcx, rbx; this
0x180024453  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
