# BasePolicyEngine::DeleteTemporaryLocalAccounts(std::vector<Microsoft::WRL::ComPtr<IUserAccount>,std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>> const &,EvaluationTrigger,_GUID const &)

- ea: `0x18001fcf4`
- end: `0x18001ffba`
- name: `?DeleteTemporaryLocalAccounts@BasePolicyEngine@@IEAAXAEBV?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@W4EvaluationTrigger@@AEBU_GUID@@@Z`
- size: `710`
- prototype: `void __fastcall(__int64, __int64 **, int, __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020070`
- `0x1800218d0`

## callees

- `0x180003530`
- `0x18000ccd4`
- `0x18000f454`
- `0x180012294`
- `0x180013dcc`
- `0x180014360`
- `0x1800154cc`
- `0x18001993c`
- `0x180019b18`
- `0x18001d110`
- `0x18001d900`
- `0x18001fc9c`
- `0x18001fcf4`
- `0x180020244`
- `0x18002039c`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001feca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001feca`

## string_xrefs

- `0x18001fd93`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\basePolicyEngine.h`
- `0x18001fdd1`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\basePolicyEngine.h`
- `0x18001ff7e`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\basePolicyEngine.h`
- `0x18001ff93`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\basePolicyEngine.h`
- `0x18001ffa8`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\basePolicyEngine.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall BasePolicyEngine::DeleteTemporaryLocalAccounts(__int64 a1, __int64 **a2, int a3, __int64 a4)
{
  unsigned int v8; // r14d
  int v9; // eax
  int v10; // eax
  __int64 *v11; // rsi
  __int64 *v12; // r15
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, LPCWCH *); // rbx
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rdi
  const WCHAR *v20; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  LPCWCH lpString1; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h]
  _QWORD v27[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v27,
    (__int64)"LocalPolicyEvaluation");
  v27[0] = &PolicyTelemetry::LocalPolicyEvaluation::`vftable';
  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
    v27,
    a4);
  PolicyTelemetry::LocalPolicyEvaluation::StartActivity((PolicyTelemetry::LocalPolicyEvaluation *)v27);
  v8 = 0;
  if ( *a2 != a2[1] )
  {
    if ( !*(_QWORD *)(a1 + 56) )
    {
      v9 = Microsoft::WRL::Details::MakeAndInitialize<LocalAccountController,ILocalAccountController,>(a1 + 56);
      if ( v9 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x6B,
          (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\basePolicyEngine.h",
          (const char *)(unsigned int)v9,
          bIgnoreCase);
    }
    std::vector<SessionUserInfo>::vector<SessionUserInfo>(&v25);
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 56) + 24LL))(*(_QWORD *)(a1 + 56), &v25);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x70,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\basePolicyEngine.h",
        (const char *)(unsigned int)v10,
        bIgnoreCase);
    v11 = *a2;
    v12 = a2[1];
    while ( v11 != v12 )
    {
      v22 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)*v11 + 80LL))(*v11, &v22);
      if ( v13 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x77,
          (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\basePolicyEngine.h",
          (const char *)(unsigned int)v13,
          bIgnoreCase);
      if ( !v22 )
      {
        v23 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)*v11 + 40LL))(*v11, &v23);
        if ( v14 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x7C,
            (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\basePolicyEngine.h",
            (const char *)(unsigned int)v14,
            bIgnoreCase);
        if ( v23 == 1 )
        {
          lpString1 = 0;
          v15 = *v11;
          v16 = *(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)*v11 + 32LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &lpString1,
            0);
          v17 = v16(v15, &lpString1);
          if ( v17 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x80,
              (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\basePolicyEngine.h",
              (const char *)(unsigned int)v17,
              bIgnoreCase);
          v18 = v25;
          v19 = v26;
          if ( v25 != v26 )
          {
            do
            {
              v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
              if ( CompareStringOrdinal(lpString1, -1, v20, -1, 1) == 2 )
                break;
              v18 += 32;
            }
            while ( v18 != v19 );
            if ( v18 != v26 && BasePolicyEngine::DeleteUserAccount((_QWORD **)a1, *v11, a3) )
              ++v8;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpString1);
        }
        else if ( !v23 && BasePolicyEngine::DeleteUserAccount((_QWORD **)a1, *v11, a3) )
        {
          ++v8;
        }
      }
      ++v11;
    }
    std::vector<std::wstring>::_Tidy(&v25);
  }
  PolicyTelemetry::LocalPolicyEvaluation::Stop((PolicyTelemetry::LocalPolicyEvaluation *)v27, v8);
  PolicyTelemetry::LocalPolicyEvaluation::~LocalPolicyEvaluation((PolicyTelemetry::LocalPolicyEvaluation *)v27);
}

```

## disassembly

```asm
0x18001fcf4  mov     [rsp-8+arg_10], rbx
0x18001fcf9  push    rbp
0x18001fcfa  push    rsi
0x18001fcfb  push    rdi
0x18001fcfc  push    r12
0x18001fcfe  push    r13
0x18001fd00  push    r14
0x18001fd02  push    r15
0x18001fd04  lea     rbp, [rsp-0C0h]
0x18001fd0c  sub     rsp, 1C0h
0x18001fd13  mov     rax, cs:__security_cookie
0x18001fd1a  xor     rax, rsp
0x18001fd1d  mov     [rbp+0F0h+var_40], rax
0x18001fd24  mov     rbx, r9
0x18001fd27  mov     r12d, r8d
0x18001fd2a  mov     rdi, rdx
0x18001fd2d  mov     r13, rcx
0x18001fd30  lea     rdx, aLocalpolicyeva; "LocalPolicyEvaluation"
0x18001fd37  lea     rcx, [rsp+1F0h+var_190]
0x18001fd3c  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001fd41  lea     rax, ??_7LocalPolicyEvaluation@PolicyTelemetry@@6B@; const PolicyTelemetry::LocalPolicyEvaluation::`vftable'
0x18001fd48  mov     [rsp+1F0h+var_190], rax
0x18001fd4d  mov     rdx, rbx
0x18001fd50  lea     rcx, [rsp+1F0h+var_190]
0x18001fd55  call    ?SetRelatedActivityId@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18001fd5a  lea     rcx, [rsp+1F0h+var_190]; this
0x18001fd5f  call    ?StartActivity@LocalPolicyEvaluation@PolicyTelemetry@@QEAAXXZ; PolicyTelemetry::LocalPolicyEvaluation::StartActivity(void)
0x18001fd64  xor     r14d, r14d
0x18001fd67  mov     rax, [rdi+8]
0x18001fd6b  cmp     [rdi], rax
0x18001fd6e  jz      loc_18001FF39
0x18001fd74  lea     rbx, [r13+38h]
0x18001fd78  cmp     [rbx], r14
0x18001fd7b  jnz     short loc_18001FDA4
0x18001fd7d  mov     rcx, rbx
0x18001fd80  call    ??$MakeAndInitialize@VLocalAccountController@@UILocalAccountController@@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UILocalAccountController@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<LocalAccountController,ILocalAccountController,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILocalAccountController>>)
0x18001fd85  mov     rcx, [rbp+0F8h]; this
0x18001fd8c  test    eax, eax
0x18001fd8e  jns     short loc_18001FDA4
0x18001fd90  mov     r9d, eax; char *
0x18001fd93  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001fd9a  lea     edx, [r14+6Bh]; void *
0x18001fd9e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001fda4  lea     rcx, [rsp+1F0h+var_1B0]
0x18001fda9  call    ??0?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@QEAA@XZ; std::vector<SessionUserInfo>::vector<SessionUserInfo>(void)
0x18001fdae  nop
0x18001fdaf  mov     rcx, [rbx]
0x18001fdb2  mov     rax, [rcx]
0x18001fdb5  lea     rdx, [rsp+1F0h+var_1B0]
0x18001fdba  mov     rax, [rax+18h]
0x18001fdbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdc3  mov     rcx, [rbp+0F8h]; this
0x18001fdca  test    eax, eax
0x18001fdcc  jns     short loc_18001FDE3
0x18001fdce  mov     r9d, eax; char *
0x18001fdd1  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001fdd8  mov     edx, 70h ; 'p'; void *
0x18001fddd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001fde3  mov     rsi, [rdi]
0x18001fde6  mov     r15, [rdi+8]
0x18001fdea  jmp     loc_18001FF26
0x18001fdef  mov     [rsp+1F0h+var_1C0], 0
0x18001fdf7  mov     rcx, [rsi]
0x18001fdfa  mov     rax, [rcx]
0x18001fdfd  lea     rdx, [rsp+1F0h+var_1C0]
0x18001fe02  mov     rax, [rax+50h]
0x18001fe06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe0b  mov     rcx, [rbp+0F8h]; this
0x18001fe12  test    eax, eax
0x18001fe14  js      loc_18001FFA5
0x18001fe1a  cmp     [rsp+1F0h+var_1C0], 0
0x18001fe1f  jnz     loc_18001FF22
0x18001fe25  mov     [rsp+1F0h+var_1BC], 0
0x18001fe2d  mov     rcx, [rsi]
0x18001fe30  mov     rax, [rcx]
0x18001fe33  lea     rdx, [rsp+1F0h+var_1BC]
0x18001fe38  mov     rax, [rax+28h]
0x18001fe3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe41  mov     rcx, [rbp+0F8h]; this
0x18001fe48  test    eax, eax
0x18001fe4a  js      loc_18001FF90
0x18001fe50  mov     eax, [rsp+1F0h+var_1BC]
0x18001fe54  cmp     eax, 1
0x18001fe57  jnz     loc_18001FF09
0x18001fe5d  mov     [rsp+1F0h+lpString1], 0
0x18001fe66  mov     rdi, [rsi]
0x18001fe69  mov     rax, [rdi]
0x18001fe6c  mov     rbx, [rax+20h]
0x18001fe70  xor     edx, edx
0x18001fe72  lea     rcx, [rsp+1F0h+lpString1]
0x18001fe77  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001fe7c  lea     rdx, [rsp+1F0h+lpString1]
0x18001fe81  mov     rcx, rdi
0x18001fe84  mov     rax, rbx
0x18001fe87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe8c  mov     rcx, [rbp+0F8h]; this
0x18001fe93  test    eax, eax
0x18001fe95  js      loc_18001FF7B
0x18001fe9b  mov     rbx, [rsp+1F0h+var_1B0]
0x18001fea0  mov     rdi, [rsp+1F0h+var_1A8]
0x18001fea5  cmp     rbx, rdi
0x18001fea8  jz      short loc_18001FEFD
0x18001feaa  mov     rcx, rbx
0x18001fead  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001feb2  mov     [rsp+1F0h+bIgnoreCase], 1; bIgnoreCase
0x18001feba  or      ecx, 0FFFFFFFFh
0x18001febd  mov     r9d, ecx; cchCount2
0x18001fec0  mov     r8, rax; lpString2
0x18001fec3  mov     edx, ecx; cchCount1
0x18001fec5  mov     rcx, [rsp+1F0h+lpString1]; lpString1
0x18001feca  call    cs:__imp_CompareStringOrdinal
0x18001fed0  cmp     eax, 2
0x18001fed3  jz      short loc_18001FEDE
0x18001fed5  add     rbx, 20h ; ' '
0x18001fed9  cmp     rbx, rdi
0x18001fedc  jnz     short loc_18001FEAA
0x18001fede  mov     rdi, [rsp+1F0h+var_1A8]
0x18001fee3  cmp     rbx, rdi
0x18001fee6  jz      short loc_18001FEFD
0x18001fee8  mov     r8d, r12d
0x18001feeb  mov     rdx, [rsi]
0x18001feee  mov     rcx, r13
0x18001fef1  call    ?DeleteUserAccount@BasePolicyEngine@@IEAA_NPEAUIUserAccount@@W4EvaluationTrigger@@@Z; BasePolicyEngine::DeleteUserAccount(IUserAccount *,EvaluationTrigger)
0x18001fef6  test    al, al
0x18001fef8  jz      short loc_18001FEFD
0x18001fefa  inc     r14d
0x18001fefd  lea     rcx, [rsp+1F0h+lpString1]
0x18001ff02  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ff07  jmp     short loc_18001FF22
0x18001ff09  test    eax, eax
0x18001ff0b  jnz     short loc_18001FF22
0x18001ff0d  mov     r8d, r12d
0x18001ff10  mov     rdx, [rsi]
0x18001ff13  mov     rcx, r13
0x18001ff16  call    ?DeleteUserAccount@BasePolicyEngine@@IEAA_NPEAUIUserAccount@@W4EvaluationTrigger@@@Z; BasePolicyEngine::DeleteUserAccount(IUserAccount *,EvaluationTrigger)
0x18001ff1b  test    al, al
0x18001ff1d  jz      short loc_18001FF22
0x18001ff1f  inc     r14d
0x18001ff22  add     rsi, 8
0x18001ff26  cmp     rsi, r15
0x18001ff29  jnz     loc_18001FDEF
0x18001ff2f  lea     rcx, [rsp+1F0h+var_1B0]
0x18001ff34  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001ff39  mov     edx, r14d; unsigned int
0x18001ff3c  lea     rcx, [rsp+1F0h+var_190]; this
0x18001ff41  call    ?Stop@LocalPolicyEvaluation@PolicyTelemetry@@QEAAXI@Z; PolicyTelemetry::LocalPolicyEvaluation::Stop(uint)
0x18001ff46  nop
0x18001ff47  lea     rcx, [rsp+1F0h+var_190]; this
0x18001ff4c  call    ??1LocalPolicyEvaluation@PolicyTelemetry@@QEAA@XZ; PolicyTelemetry::LocalPolicyEvaluation::~LocalPolicyEvaluation(void)
0x18001ff51  mov     rcx, [rbp+0F0h+var_40]
0x18001ff58  xor     rcx, rsp; StackCookie
0x18001ff5b  call    __security_check_cookie
0x18001ff60  mov     rbx, [rsp+1F0h+arg_10]
0x18001ff68  add     rsp, 1C0h
0x18001ff6f  pop     r15
0x18001ff71  pop     r14
0x18001ff73  pop     r13
0x18001ff75  pop     r12
0x18001ff77  pop     rdi
0x18001ff78  pop     rsi
0x18001ff79  pop     rbp
0x18001ff7a  retn
0x18001ff7b  mov     r9d, eax; char *
0x18001ff7e  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001ff85  mov     edx, 80h; void *
0x18001ff8a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ff90  mov     r9d, eax; char *
0x18001ff93  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001ff9a  mov     edx, 7Ch ; '|'; void *
0x18001ff9f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ffa5  mov     r9d, eax; char *
0x18001ffa8  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001ffaf  mov     edx, 77h ; 'w'; void *
0x18001ffb4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
