# BasePolicyEngine::DeleteUserAccount(IUserAccount *,EvaluationTrigger)

- ea: `0x18001d110`
- end: `0x18001d2b7`
- name: `?DeleteUserAccount@BasePolicyEngine@@IEAA_NPEAUIUserAccount@@W4EvaluationTrigger@@@Z`
- size: `423`
- prototype: `char __fastcall(_QWORD **, __int64, int)`
- caller_count: `6`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001d2c0`
- `0x18001eca0`
- `0x18001f490`
- `0x18001fcf4`
- `0x180020070`
- `0x1800218d0`

## callees

- `0x180003530`
- `0x18000ccd4`
- `0x18000cd50`
- `0x18000ec14`
- `0x180012f64`
- `0x180013dcc`
- `0x1800154cc`
- `0x180019b18`
- `0x180019fbc`
- `0x18001d110`
- `0x18001deac`
- `0x180026010`

## string_xrefs

- `0x18001d177`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\basePolicyEngine.h`
- `0x18001d1cd`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\basePolicyEngine.h`
- `0x18001d273`: `Deleted a user profile. Engine: %ws. User SID: %ws. Extra Information: %ws.`

## pseudocode

```c
char __fastcall BasePolicyEngine::DeleteUserAccount(_QWORD **a1, __int64 a2, int a3)
{
  char v5; // di
  __int64 (__fastcall *v6)(__int64, LPCWCH *); // rbx
  int v7; // eax
  bool v8; // bl
  int v9; // eax
  wil::TraceLoggingProvider *v10; // rax
  unsigned __int64 v11; // r8
  int (__fastcall *v12)(__int64, LPCWCH *); // rbx
  __int64 v13; // rbx
  LPCWCH v14; // rdi
  __int64 v15; // rax
  int v17; // [rsp+20h] [rbp-40h] BYREF
  LPCWCH lpString1; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v19[32]; // [rsp+30h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v5 = 1;
  if ( a3 == 1 )
  {
    lpString1 = 0;
    v6 = *(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)a2 + 24LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpString1,
      0);
    v7 = v6(a2, &lpString1);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\basePolicyEngine.h",
        (const char *)(unsigned int)v7,
        v17);
    v8 = IsUserLoggedOn(lpString1);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
    v5 = !v8;
  }
  LOBYTE(v17) = 0;
  if ( v5 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64, int *))(*a1[8] + 24LL))(a1[8], a2, &v17);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\basePolicyEngine.h",
        (const char *)(unsigned int)v9,
        v17);
    if ( (_BYTE)v17 )
    {
      v10 = (wil::TraceLoggingProvider *)wil::details::static_lazy<SharedPCAccountManagerLogging>::get(
                                           retaddr,
                                           _lambda_b274f51942286cd361d3a3bb29f15d14_::_lambda_invoker_cdecl_);
      if ( wil::TraceLoggingProvider::IsEnabled_(v10, 0, v11) )
      {
        lpString1 = 0;
        v12 = *(int (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)a2 + 24LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &lpString1,
          0);
        if ( v12(a2, &lpString1) >= 0 )
        {
          ((void (__fastcall *)(_QWORD **, _BYTE *, __int64))(*a1)[8])(a1, v19, a2);
          v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
          v14 = lpString1;
          v15 = ((__int64 (__fastcall *)(_QWORD **))(*a1)[7])(a1);
          PolicyTelemetry::TraceLoggingInfo(
            "Deleted a user profile. Engine: %ws. User SID: %ws. Extra Information: %ws.",
            v15,
            v14,
            v13);
          std::wstring::_Tidy_deallocate(v19);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
      }
    }
  }
  return v17;
}

```

## disassembly

```asm
0x18001d110  mov     [rsp-18h+arg_10], rbx
0x18001d115  mov     [rsp-18h+arg_18], rsi
0x18001d11a  push    rbp
0x18001d11b  push    rdi
0x18001d11c  push    r14
0x18001d11e  mov     rbp, rsp
0x18001d121  sub     rsp, 60h
0x18001d125  mov     rax, cs:__security_cookie
0x18001d12c  xor     rax, rsp
0x18001d12f  mov     [rbp+var_10], rax
0x18001d133  mov     rsi, rdx
0x18001d136  mov     r14, rcx
0x18001d139  mov     edi, 1
0x18001d13e  cmp     r8d, edi
0x18001d141  jnz     short loc_18001D19E
0x18001d143  mov     [rbp+lpString1], 0
0x18001d14b  mov     rax, [rdx]
0x18001d14e  mov     rbx, [rax+18h]
0x18001d152  xor     edx, edx
0x18001d154  lea     rcx, [rbp+lpString1]
0x18001d158  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001d15d  lea     rdx, [rbp+lpString1]
0x18001d161  mov     rcx, rsi
0x18001d164  mov     rax, rbx
0x18001d167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d16c  mov     rcx, [rbp+18h]; this
0x18001d170  test    eax, eax
0x18001d172  jns     short loc_18001D187
0x18001d174  mov     r9d, eax; char *
0x18001d177  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001d17e  lea     edx, [rdi+42h]; void *
0x18001d181  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001d187  mov     rcx, [rbp+lpString1]; lpString1
0x18001d18b  call    ?IsUserLoggedOn@@YA_NPEBG@Z; IsUserLoggedOn(ushort const *)
0x18001d190  mov     bl, al
0x18001d192  lea     rcx, [rbp+lpString1]
0x18001d196  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d19b  xor     dil, bl
0x18001d19e  mov     byte ptr [rbp+var_40], 0
0x18001d1a2  test    dil, dil
0x18001d1a5  jz      loc_18001D293
0x18001d1ab  mov     rcx, [r14+40h]
0x18001d1af  mov     rax, [rcx]
0x18001d1b2  lea     r8, [rbp+var_40]
0x18001d1b6  mov     rdx, rsi
0x18001d1b9  mov     rax, [rax+18h]
0x18001d1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1c2  mov     rcx, [rbp+18h]; this
0x18001d1c6  test    eax, eax
0x18001d1c8  jns     short loc_18001D1DF
0x18001d1ca  mov     r9d, eax; char *
0x18001d1cd  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001d1d4  mov     edx, 4Ah ; 'J'; void *
0x18001d1d9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001d1df  cmp     byte ptr [rbp+var_40], 0
0x18001d1e3  jz      loc_18001D293
0x18001d1e9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_b274f51942286cd361d3a3bb29f15d14_@@CA@XZ; _lambda_b274f51942286cd361d3a3bb29f15d14_::_lambda_invoker_cdecl_(void)
0x18001d1f0  call    ?get@?$static_lazy@VSharedPCAccountManagerLogging@@@details@wil@@QEAAPEAVSharedPCAccountManagerLogging@@P6AXXZ@Z; wil::details::static_lazy<SharedPCAccountManagerLogging>::get(void (*)(void))
0x18001d1f5  xor     edx, edx; unsigned __int8
0x18001d1f7  mov     rcx, rax; this
0x18001d1fa  call    ?IsEnabled_@TraceLoggingProvider@wil@@IEBA_NE_K@Z; wil::TraceLoggingProvider::IsEnabled_(uchar,unsigned __int64)
0x18001d1ff  test    al, al
0x18001d201  jz      loc_18001D293
0x18001d207  mov     [rbp+lpString1], 0
0x18001d20f  mov     rax, [rsi]
0x18001d212  mov     rbx, [rax+18h]
0x18001d216  xor     edx, edx
0x18001d218  lea     rcx, [rbp+lpString1]
0x18001d21c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001d221  lea     rdx, [rbp+lpString1]
0x18001d225  mov     rcx, rsi
0x18001d228  mov     rax, rbx
0x18001d22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d230  test    eax, eax
0x18001d232  js      short loc_18001D28A
0x18001d234  mov     rax, [r14]
0x18001d237  mov     r8, rsi
0x18001d23a  lea     rdx, [rbp+var_30]
0x18001d23e  mov     rcx, r14
0x18001d241  mov     rax, [rax+40h]
0x18001d245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d24a  nop
0x18001d24b  lea     rcx, [rbp+var_30]
0x18001d24f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d254  mov     rbx, rax
0x18001d257  mov     rdi, [rbp+lpString1]
0x18001d25b  mov     rdx, [r14]
0x18001d25e  mov     rcx, r14
0x18001d261  mov     rax, [rdx+38h]
0x18001d265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d26a  mov     r9, rbx
0x18001d26d  mov     r8, rdi
0x18001d270  mov     rdx, rax
0x18001d273  lea     rcx, aDeletedAUserPr; "Deleted a user profile. Engine: %ws. Us"...
0x18001d27a  call    ?TraceLoggingInfo@PolicyTelemetry@@SAXPEBDZZ; PolicyTelemetry::TraceLoggingInfo(char const *,...)
0x18001d27f  nop
0x18001d280  lea     rcx, [rbp+var_30]
0x18001d284  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d289  nop
0x18001d28a  lea     rcx, [rbp+lpString1]
0x18001d28e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d293  mov     al, byte ptr [rbp+var_40]
0x18001d296  mov     rcx, [rbp+var_10]
0x18001d29a  xor     rcx, rsp; StackCookie
0x18001d29d  call    __security_check_cookie
0x18001d2a2  lea     r11, [rsp+60h+var_s0]
0x18001d2a7  mov     rbx, [r11+30h]
0x18001d2ab  mov     rsi, [r11+38h]
0x18001d2af  mov     rsp, r11
0x18001d2b2  pop     r14
0x18001d2b4  pop     rdi
0x18001d2b5  pop     rbp
0x18001d2b6  retn
```
