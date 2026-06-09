# ExemptionPolicyEngine::RunPolicyEvaluation(EvaluationTrigger,std::vector<Microsoft::WRL::ComPtr<IUserAccount>,std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>> &,_GUID const &)

- ea: `0x180020e10`
- end: `0x180020fec`
- name: `?RunPolicyEvaluation@ExemptionPolicyEngine@@UEAAJW4EvaluationTrigger@@AEAV?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEBU_GUID@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(ExemptionPolicyEngine *this, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000ccd4`
- `0x18000cd50`
- `0x180012294`
- `0x1800154cc`
- `0x180019b18`
- `0x18001d900`
- `0x18001deac`
- `0x180020ccc`
- `0x180020cf8`
- `0x180020e10`
- `0x180020ff4`
- `0x1800210a0`
- `0x18002152c`
- `0x180026010`

## string_xrefs

- `0x180020efa`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\exemptionpolicyengine.cpp`
- `0x180020f65`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\exemptionpolicyengine.cpp`
- `0x180020f7e`: `Exempted a profile from deletion: User SID: %ws`

## pseudocode

```c
__int64 __fastcall ExemptionPolicyEngine::RunPolicyEvaluation(
        ExemptionPolicyEngine *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rbx
  ExemptionPolicyEngine *v6; // rsi
  ExemptionPolicyEngine *v7; // r15
  const char *v8; // r9
  unsigned int v9; // r12d
  _QWORD *v10; // r14
  _QWORD *v11; // r13
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, int *); // rbx
  int v14; // eax
  int v15; // eax
  int v17[2]; // [rsp+20h] [rbp-1C8h] BYREF
  __int64 v18; // [rsp+28h] [rbp-1C0h] BYREF
  __int64 v19; // [rsp+30h] [rbp-1B8h]
  _BYTE v20[40]; // [rsp+38h] [rbp-1B0h] BYREF
  _QWORD v21[42]; // [rsp+60h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v5 = a3;
  v6 = this;
  *(_QWORD *)v17 = this;
  v7 = this;
  v19 = a3;
  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v21,
    "ExemptionPolicyEvaluation");
  v21[0] = &PolicyTelemetry::ExemptionPolicyEvaluation::`vftable';
  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
    v21,
    a4);
  PolicyTelemetry::ExemptionPolicyEvaluation::StartActivity((PolicyTelemetry::ExemptionPolicyEvaluation *)v21);
  try
  {
    ExemptionPolicyEngine::EnsureExemptionsLoaded(v7);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x18,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\exemptionpolicyengine.cpp",
      v8);
    v6 = *(ExemptionPolicyEngine **)v17;
    v5 = v19;
    v7 = *(ExemptionPolicyEngine **)v17;
  }
  v9 = 0;
  if ( *((_QWORD *)v7 + 12) )
  {
    v10 = *(_QWORD **)v5;
    v11 = *(_QWORD **)(v5 + 8);
    while ( v10 != v11 )
    {
      *(_QWORD *)v17 = 0;
      v12 = *v10;
      v13 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)*v10 + 24LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v17,
        0);
      v14 = v13(v12, v17);
      if ( v14 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x21,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\exemptionpolicyengine.cpp",
          (const char *)(unsigned int)v14,
          v17[0]);
      std::wstring::wstring(v20, *(_QWORD *)v17);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
        (char *)v6 + 80,
        &v18,
        v20);
      std::wstring::_Tidy_deallocate(v20);
      if ( v18 != *((_QWORD *)v7 + 11) )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v10 + 88LL))(*v10, 2);
        if ( v15 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x27,
            (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\exemptionpolicyengine.cpp",
            (const char *)(unsigned int)v15,
            v17[0]);
        ++v9;
        PolicyTelemetry::TraceLoggingInfo("Exempted a profile from deletion: User SID: %ws", *(_QWORD *)v17);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v17);
      ++v10;
    }
  }
  PolicyTelemetry::ExemptionPolicyEvaluation::Stop((PolicyTelemetry::ExemptionPolicyEvaluation *)v21, v9);
  PolicyTelemetry::ExemptionPolicyEvaluation::~ExemptionPolicyEvaluation((PolicyTelemetry::ExemptionPolicyEvaluation *)v21);
  return 0;
}

```

## disassembly

```asm
0x180020e10  mov     [rsp+arg_8], rbx
0x180020e15  mov     [rsp+arg_18], rsi
0x180020e1a  push    rdi
0x180020e1b  push    r12
0x180020e1d  push    r13
0x180020e1f  push    r14
0x180020e21  push    r15
0x180020e23  sub     rsp, 1C0h
0x180020e2a  mov     rax, cs:__security_cookie
0x180020e31  xor     rax, rsp
0x180020e34  mov     [rsp+1E8h+var_38], rax
0x180020e3c  mov     rdi, r9
0x180020e3f  mov     rbx, r8
0x180020e42  mov     rsi, rcx
0x180020e45  mov     qword ptr [rsp+1E8h+var_1C8], rcx
0x180020e4a  mov     r15, rcx
0x180020e4d  mov     [rsp+1E8h+var_1B8], rbx
0x180020e52  lea     rdx, aExemptionpolic; "ExemptionPolicyEvaluation"
0x180020e59  lea     rcx, [rsp+1E8h+var_188]
0x180020e5e  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180020e63  lea     rax, ??_7ExemptionPolicyEvaluation@PolicyTelemetry@@6B@; const PolicyTelemetry::ExemptionPolicyEvaluation::`vftable'
0x180020e6a  mov     [rsp+1E8h+var_188], rax
0x180020e6f  mov     rdx, rdi
0x180020e72  lea     rcx, [rsp+1E8h+var_188]
0x180020e77  call    ?SetRelatedActivityId@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x180020e7c  lea     rcx, [rsp+1E8h+var_188]; this
0x180020e81  call    ?StartActivity@ExemptionPolicyEvaluation@PolicyTelemetry@@QEAAXXZ; PolicyTelemetry::ExemptionPolicyEvaluation::StartActivity(void)
0x180020e86  nop
0x180020e87  mov     rcx, r15; this
0x180020e8a  call    ?EnsureExemptionsLoaded@ExemptionPolicyEngine@@AEAAXXZ; ExemptionPolicyEngine::EnsureExemptionsLoaded(void)
0x180020e8f  nop
0x180020e90  jmp     short loc_180020E9F
0x180020e92  mov     rsi, qword ptr [rsp+1E8h+var_1C8]
0x180020e97  mov     rbx, [rsp+1E8h+var_1B8]
0x180020e9c  mov     r15, rsi
0x180020e9f  xor     r12d, r12d
0x180020ea2  cmp     [r15+60h], r12
0x180020ea6  jz      loc_180020F9E
0x180020eac  mov     r14, [rbx]
0x180020eaf  mov     r13, [rbx+8]
0x180020eb3  cmp     r14, r13
0x180020eb6  jz      loc_180020F9E
0x180020ebc  mov     qword ptr [rsp+1E8h+var_1C8], 0; int
0x180020ec5  mov     rdi, [r14]
0x180020ec8  mov     rax, [rdi]
0x180020ecb  mov     rbx, [rax+18h]
0x180020ecf  xor     edx, edx
0x180020ed1  lea     rcx, [rsp+1E8h+var_1C8]
0x180020ed6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180020edb  lea     rdx, [rsp+1E8h+var_1C8]
0x180020ee0  mov     rcx, rdi
0x180020ee3  mov     rax, rbx
0x180020ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020eeb  mov     rcx, [rsp+1E8h]; this
0x180020ef3  test    eax, eax
0x180020ef5  jns     short loc_180020F0B
0x180020ef7  mov     r9d, eax; char *
0x180020efa  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\sharedpc\\accountma"...
0x180020f01  mov     edx, 21h ; '!'; void *
0x180020f06  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020f0b  mov     rdx, qword ptr [rsp+1E8h+var_1C8]
0x180020f10  lea     rcx, [rsp+1E8h+var_1B0]
0x180020f15  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180020f1a  lea     r8, [rsp+1E8h+var_1B0]
0x180020f1f  lea     rdx, [rsp+1E8h+var_1C0]
0x180020f24  lea     rcx, [rsi+50h]
0x180020f28  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180020f2d  lea     rcx, [rsp+1E8h+var_1B0]
0x180020f32  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020f37  mov     rax, [r15+58h]
0x180020f3b  cmp     [rsp+1E8h+var_1C0], rax
0x180020f40  jz      short loc_180020F8B
0x180020f42  mov     rcx, [r14]
0x180020f45  mov     rax, [rcx]
0x180020f48  mov     edx, 2
0x180020f4d  mov     rax, [rax+58h]
0x180020f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f56  mov     rcx, [rsp+1E8h]; this
0x180020f5e  test    eax, eax
0x180020f60  jns     short loc_180020F76
0x180020f62  mov     r9d, eax; char *
0x180020f65  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\sharedpc\\accountma"...
0x180020f6c  mov     edx, 27h ; '''; void *
0x180020f71  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020f76  inc     r12d
0x180020f79  mov     rdx, qword ptr [rsp+1E8h+var_1C8]
0x180020f7e  lea     rcx, aExemptedAProfi; "Exempted a profile from deletion: User "...
0x180020f85  call    ?TraceLoggingInfo@PolicyTelemetry@@SAXPEBDZZ; PolicyTelemetry::TraceLoggingInfo(char const *,...)
0x180020f8a  nop
0x180020f8b  lea     rcx, [rsp+1E8h+var_1C8]
0x180020f90  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020f95  add     r14, 8
0x180020f99  jmp     loc_180020EB3
0x180020f9e  mov     edx, r12d; unsigned int
0x180020fa1  lea     rcx, [rsp+1E8h+var_188]; this
0x180020fa6  call    ?Stop@ExemptionPolicyEvaluation@PolicyTelemetry@@QEAAXI@Z; PolicyTelemetry::ExemptionPolicyEvaluation::Stop(uint)
0x180020fab  nop
0x180020fac  lea     rcx, [rsp+1E8h+var_188]; this
0x180020fb1  call    ??1ExemptionPolicyEvaluation@PolicyTelemetry@@QEAA@XZ; PolicyTelemetry::ExemptionPolicyEvaluation::~ExemptionPolicyEvaluation(void)
0x180020fb6  xor     eax, eax
0x180020fb8  jmp     short loc_180020FBE
0x180020fba  mov     eax, [rsp+1E8h+var_1C8]
0x180020fbe  mov     rcx, [rsp+1E8h+var_38]
0x180020fc6  xor     rcx, rsp; StackCookie
0x180020fc9  call    __security_check_cookie
0x180020fce  lea     r11, [rsp+1E8h+var_28]
0x180020fd6  mov     rbx, [r11+38h]
0x180020fda  mov     rsi, [r11+48h]
0x180020fde  mov     rsp, r11
0x180020fe1  pop     r15
0x180020fe3  pop     r14
0x180020fe5  pop     r13
0x180020fe7  pop     r12
0x180020fe9  pop     rdi
0x180020fea  retn
```
