# wil::details::CreateCloudStoreDefaultWithWaitTime(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,wchar_t const *,Windows::Internal::Storage::Cloud::WaitTimes const &)

- ea: `0x18001f1f0`
- end: `0x18001f35c`
- name: `?CreateCloudStoreDefaultWithWaitTime@details@wil@@YA?AV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@W4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@8@PEAUIWebAccount@Credentials@Security@8@PEB_WAEBUWaitTimes@5678@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024000`

## callees

- `0x180003560`
- `0x180005478`
- `0x180009388`
- `0x18000cac0`
- `0x18001b128`
- `0x18001b1ec`
- `0x18001f1f0`
- `0x180022b80`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall wil::details::CreateCloudStoreDefaultWithWaitTime(
        _QWORD *a1,
        int a2,
        __int64 a3,
        const char *a4,
        const WCHAR *a5)
{
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64, const char *); // rdi
  int v11; // eax
  PVOID Reserved1; // [rsp+20h] [rbp-79h]
  __int64 v14; // [rsp+48h] [rbp-51h] BYREF
  const WCHAR *v15; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v16[2]; // [rsp+58h] [rbp-41h] BYREF
  char v17; // [rsp+68h] [rbp-31h]
  _QWORD *v18; // [rsp+70h] [rbp-29h]
  HSTRING_HEADER v19; // [rsp+78h] [rbp-21h] BYREF
  __int64 v20; // [rsp+90h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  v18 = a1;
  v15 = a5;
  if ( (a2 & 1) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      a4);
  if ( (a2 & 2) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      a4);
  wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>((HSTRING)&v14);
  *a1 = 0;
  v9 = v14;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, const char *))(*(_QWORD *)v14 + 56LL);
  v16[0] = a1;
  v16[1] = 0;
  v17 = 1;
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v19, &v15)[1].Reserved.Reserved1;
  v11 = v10(v9, a2 | (a3 == 0) | (unsigned int)(a4 == 0 ? 2 : 0), a3, a4);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v11,
      (int)Reserved1);
  v20 = 0;
  wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>(v16);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v14);
  return a1;
}

```

## disassembly

```asm
0x18001f1f0  push    rbp
0x18001f1f2  push    rbx
0x18001f1f3  push    rsi
0x18001f1f4  push    rdi
0x18001f1f5  push    r12
0x18001f1f7  push    r13
0x18001f1f9  push    r14
0x18001f1fb  push    r15
0x18001f1fd  lea     rbp, [rsp-0Fh]
0x18001f202  sub     rsp, 0A8h
0x18001f209  mov     rax, cs:__security_cookie
0x18001f210  xor     rax, rsp
0x18001f213  mov     [rbp+47h+var_48], rax
0x18001f217  mov     r13, r9
0x18001f21a  mov     r12, r8
0x18001f21d  mov     r15d, edx
0x18001f220  mov     r14, rcx
0x18001f223  mov     [rbp+47h+var_70], rcx
0x18001f227  mov     rax, [rbp+47h+arg_20]
0x18001f22b  mov     [rbp+47h+var_90], rax
0x18001f22f  mov     rbx, [rbp+47h+arg_28]
0x18001f233  mov     [rbp+47h+var_A0], 0
0x18001f23a  mov     rcx, [rbp+4Fh]; this
0x18001f23e  test    dl, 1
0x18001f241  jnz     loc_18001F338
0x18001f247  mov     rcx, [rbp+4Fh]; this
0x18001f24b  test    r15b, 2
0x18001f24f  jnz     loc_18001F34A
0x18001f255  lea     rcx, [rbp+47h+var_98]
0x18001f259  call    ??$GetActivationFactory@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEB_W@Z; wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(wchar_t const *)
0x18001f25e  nop
0x18001f25f  mov     qword ptr [r14], 0
0x18001f266  mov     [rbp+47h+var_A0], 1
0x18001f26d  mov     rsi, [rbp+47h+var_98]
0x18001f271  mov     rax, [rsi]
0x18001f274  mov     rdi, [rax+38h]
0x18001f278  mov     [rbp+47h+var_88], r14
0x18001f27c  mov     [rbp+47h+var_80], 0
0x18001f284  mov     [rbp+47h+var_78], 1
0x18001f288  mov     rbx, [rbx]
0x18001f28b  lea     rdx, [rbp+47h+var_90]
0x18001f28f  lea     rcx, [rbp+47h+var_68]
0x18001f293  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18001f298  mov     r10, rax
0x18001f29b  mov     rax, r13
0x18001f29e  neg     rax
0x18001f2a1  sbb     edx, edx
0x18001f2a3  not     edx
0x18001f2a5  and     edx, 2
0x18001f2a8  xor     eax, eax
0x18001f2aa  test    r12, r12
0x18001f2ad  setz    al
0x18001f2b0  or      edx, eax
0x18001f2b2  or      edx, r15d
0x18001f2b5  lea     rax, [rbp+47h+var_80]
0x18001f2b9  mov     [rsp+0E0h+var_B0], rax
0x18001f2be  mov     [rsp+0E0h+var_B8], rbx
0x18001f2c3  mov     rax, [r10+18h]
0x18001f2c7  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001f2cc  mov     r9, r13
0x18001f2cf  mov     r8, r12
0x18001f2d2  mov     rcx, rsi
0x18001f2d5  mov     rax, rdi
0x18001f2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2dd  mov     rcx, [rbp+4Fh]; this
0x18001f2e1  test    eax, eax
0x18001f2e3  js      short loc_18001F323
0x18001f2e5  mov     [rbp+47h+var_50], 0
0x18001f2ed  lea     rcx, [rbp+47h+var_88]
0x18001f2f1  call    ??1?$out_param_t@V?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>(void)
0x18001f2f6  nop
0x18001f2f7  lea     rcx, [rbp+47h+var_98]
0x18001f2fb  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18001f300  mov     rax, r14
0x18001f303  mov     rcx, [rbp+47h+var_48]
0x18001f307  xor     rcx, rsp; StackCookie
0x18001f30a  call    __security_check_cookie
0x18001f30f  add     rsp, 0A8h
0x18001f316  pop     r15
0x18001f318  pop     r14
0x18001f31a  pop     r13
0x18001f31c  pop     r12
0x18001f31e  pop     rdi
0x18001f31f  pop     rsi
0x18001f320  pop     rbx
0x18001f321  pop     rbp
0x18001f322  retn
0x18001f323  mov     r9d, eax; char *
0x18001f326  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001f32d  mov     edx, 0CBh; void *
0x18001f332  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f338  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001f33f  mov     edx, 0BDh; void *
0x18001f344  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001f34a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001f351  mov     edx, 0BEh; void *
0x18001f356  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
