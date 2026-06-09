# wil::details::CreateCloudStoreDefaultWithWaitTime(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,ushort const *,Windows::Internal::Storage::Cloud::WaitTimes const &)

- ea: `0x18002d124`
- end: `0x18002d289`
- name: `?CreateCloudStoreDefaultWithWaitTime@details@wil@@YA?AV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@W4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@8@PEAUIWebAccount@Credentials@Security@8@PEBGAEBUWaitTimes@5678@@Z`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004540`
- `0x1800075bc`

## callees

- `0x18000d700`
- `0x1800169bc`
- `0x18001ad14`
- `0x18001e1c0`
- `0x18002a030`
- `0x18002c138`
- `0x18002d124`
- `0x18002e2d0`
- `0x180041010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall wil::details::CreateCloudStoreDefaultWithWaitTime(
        __int64 *a1,
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
  __int64 *v16[2]; // [rsp+58h] [rbp-41h] BYREF
  char v17; // [rsp+68h] [rbp-31h]
  __int64 *v18; // [rsp+70h] [rbp-29h]
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
    wil::details::in1diag3::Throw_Hr(
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
0x18002d124  push    rbp
0x18002d126  push    rbx
0x18002d127  push    rsi
0x18002d128  push    rdi
0x18002d129  push    r12
0x18002d12b  push    r13
0x18002d12d  push    r14
0x18002d12f  push    r15
0x18002d131  lea     rbp, [rsp-0Fh]
0x18002d136  sub     rsp, 0A8h
0x18002d13d  mov     rax, cs:__security_cookie
0x18002d144  xor     rax, rsp
0x18002d147  mov     [rbp+47h+var_48], rax
0x18002d14b  mov     r13, r9
0x18002d14e  mov     r12, r8
0x18002d151  mov     r15d, edx
0x18002d154  mov     r14, rcx
0x18002d157  mov     [rbp+47h+var_70], rcx
0x18002d15b  mov     rax, [rbp+47h+arg_20]
0x18002d15f  mov     [rbp+47h+var_90], rax
0x18002d163  mov     rbx, [rbp+47h+arg_28]
0x18002d167  mov     [rbp+47h+var_A0], 0
0x18002d16e  mov     rcx, [rbp+4Fh]; this
0x18002d172  test    dl, 1
0x18002d175  jz      short loc_18002D189
0x18002d177  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18002d17e  mov     edx, 0BDh; void *
0x18002d183  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002d189  mov     rcx, [rbp+4Fh]; this
0x18002d18d  test    r15b, 2
0x18002d191  jz      short loc_18002D1A5
0x18002d193  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18002d19a  mov     edx, 0BEh; void *
0x18002d19f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002d1a5  lea     rcx, [rbp+47h+var_98]
0x18002d1a9  call    ??$GetActivationFactory@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z; wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(ushort const *)
0x18002d1ae  nop
0x18002d1af  mov     qword ptr [r14], 0
0x18002d1b6  mov     [rbp+47h+var_A0], 1
0x18002d1bd  mov     rsi, [rbp+47h+var_98]
0x18002d1c1  mov     rax, [rsi]
0x18002d1c4  mov     rdi, [rax+38h]
0x18002d1c8  mov     [rbp+47h+var_88], r14
0x18002d1cc  mov     [rbp+47h+var_80], 0
0x18002d1d4  mov     [rbp+47h+var_78], 1
0x18002d1d8  mov     rbx, [rbx]
0x18002d1db  lea     rdx, [rbp+47h+var_90]
0x18002d1df  lea     rcx, [rbp+47h+var_68]
0x18002d1e3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002d1e8  mov     r10, rax
0x18002d1eb  mov     rax, r13
0x18002d1ee  neg     rax
0x18002d1f1  sbb     edx, edx
0x18002d1f3  not     edx
0x18002d1f5  and     edx, 2
0x18002d1f8  xor     eax, eax
0x18002d1fa  test    r12, r12
0x18002d1fd  setz    al
0x18002d200  or      edx, eax
0x18002d202  or      edx, r15d
0x18002d205  lea     rax, [rbp+47h+var_80]
0x18002d209  mov     [rsp+0E0h+var_B0], rax
0x18002d20e  mov     [rsp+0E0h+var_B8], rbx
0x18002d213  mov     rax, [r10+18h]
0x18002d217  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18002d21c  mov     r9, r13
0x18002d21f  mov     r8, r12
0x18002d222  mov     rcx, rsi
0x18002d225  mov     rax, rdi
0x18002d228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d22d  mov     rcx, [rbp+4Fh]; this
0x18002d231  test    eax, eax
0x18002d233  jns     short loc_18002D24A
0x18002d235  mov     r9d, eax; char *
0x18002d238  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18002d23f  mov     edx, 0CBh; void *
0x18002d244  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d24a  mov     [rbp+47h+var_50], 0
0x18002d252  lea     rcx, [rbp+47h+var_88]
0x18002d256  call    ??1?$out_param_t@V?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>(void)
0x18002d25b  nop
0x18002d25c  lea     rcx, [rbp+47h+var_98]
0x18002d260  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18002d265  mov     rax, r14
0x18002d268  mov     rcx, [rbp+47h+var_48]
0x18002d26c  xor     rcx, rsp; StackCookie
0x18002d26f  call    __security_check_cookie
0x18002d274  add     rsp, 0A8h
0x18002d27b  pop     r15
0x18002d27d  pop     r14
0x18002d27f  pop     r13
0x18002d281  pop     r12
0x18002d283  pop     rdi
0x18002d284  pop     rsi
0x18002d285  pop     rbx
0x18002d286  pop     rbp
0x18002d287  retn
```
