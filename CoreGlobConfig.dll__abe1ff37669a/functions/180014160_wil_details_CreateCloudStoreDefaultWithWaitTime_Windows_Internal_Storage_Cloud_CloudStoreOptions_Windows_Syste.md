# wil::details::CreateCloudStoreDefaultWithWaitTime(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,ushort const *,Windows::Internal::Storage::Cloud::WaitTimes const &)

- ea: `0x180014160`
- end: `0x1800142cc`
- name: `?CreateCloudStoreDefaultWithWaitTime@details@wil@@YA?AV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@W4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@8@PEAUIWebAccount@Credentials@Security@8@PEBGAEBUWaitTimes@5678@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e580`

## callees

- `0x180002380`
- `0x180006c38`
- `0x1800096ec`
- `0x18000a52c`
- `0x18001106c`
- `0x180011180`
- `0x180014160`
- `0x18001b4e4`
- `0x180025010`

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
      (int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      a4);
  if ( (a2 & 2) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xBE,
      (int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
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
  wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>((__int64)v16);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v14);
  return a1;
}

```

## disassembly

```asm
0x180014160  push    rbp
0x180014162  push    rbx
0x180014163  push    rsi
0x180014164  push    rdi
0x180014165  push    r12
0x180014167  push    r13
0x180014169  push    r14
0x18001416b  push    r15
0x18001416d  lea     rbp, [rsp-0Fh]
0x180014172  sub     rsp, 0A8h
0x180014179  mov     rax, cs:__security_cookie
0x180014180  xor     rax, rsp
0x180014183  mov     [rbp+47h+var_48], rax
0x180014187  mov     r13, r9
0x18001418a  mov     r12, r8
0x18001418d  mov     r15d, edx
0x180014190  mov     r14, rcx
0x180014193  mov     [rbp+47h+var_70], rcx
0x180014197  mov     rax, [rbp+47h+arg_20]
0x18001419b  mov     [rbp+47h+var_90], rax
0x18001419f  mov     rbx, [rbp+47h+arg_28]
0x1800141a3  mov     [rbp+47h+var_A0], 0
0x1800141aa  mov     rcx, [rbp+4Fh]; this
0x1800141ae  test    dl, 1
0x1800141b1  jnz     loc_1800142A8
0x1800141b7  mov     rcx, [rbp+4Fh]; this
0x1800141bb  test    r15b, 2
0x1800141bf  jnz     loc_1800142BA
0x1800141c5  lea     rcx, [rbp+47h+var_98]
0x1800141c9  call    ??$GetActivationFactory@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z; wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(ushort const *)
0x1800141ce  nop
0x1800141cf  mov     qword ptr [r14], 0
0x1800141d6  mov     [rbp+47h+var_A0], 1
0x1800141dd  mov     rsi, [rbp+47h+var_98]
0x1800141e1  mov     rax, [rsi]
0x1800141e4  mov     rdi, [rax+38h]
0x1800141e8  mov     [rbp+47h+var_88], r14
0x1800141ec  mov     [rbp+47h+var_80], 0
0x1800141f4  mov     [rbp+47h+var_78], 1
0x1800141f8  mov     rbx, [rbx]
0x1800141fb  lea     rdx, [rbp+47h+var_90]
0x1800141ff  lea     rcx, [rbp+47h+var_68]
0x180014203  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180014208  mov     r10, rax
0x18001420b  mov     rax, r13
0x18001420e  neg     rax
0x180014211  sbb     edx, edx
0x180014213  not     edx
0x180014215  and     edx, 2
0x180014218  xor     eax, eax
0x18001421a  test    r12, r12
0x18001421d  setz    al
0x180014220  or      edx, eax
0x180014222  or      edx, r15d
0x180014225  lea     rax, [rbp+47h+var_80]
0x180014229  mov     [rsp+0E0h+var_B0], rax
0x18001422e  mov     [rsp+0E0h+var_B8], rbx
0x180014233  mov     rax, [r10+18h]
0x180014237  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001423c  mov     r9, r13
0x18001423f  mov     r8, r12
0x180014242  mov     rcx, rsi
0x180014245  mov     rax, rdi
0x180014248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001424d  mov     rcx, [rbp+4Fh]; this
0x180014251  test    eax, eax
0x180014253  js      short loc_180014293
0x180014255  mov     [rbp+47h+var_50], 0
0x18001425d  lea     rcx, [rbp+47h+var_88]
0x180014261  call    ??1?$out_param_t@V?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>(void)
0x180014266  nop
0x180014267  lea     rcx, [rbp+47h+var_98]
0x18001426b  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180014270  mov     rax, r14
0x180014273  mov     rcx, [rbp+47h+var_48]
0x180014277  xor     rcx, rsp; StackCookie
0x18001427a  call    __security_check_cookie
0x18001427f  add     rsp, 0A8h
0x180014286  pop     r15
0x180014288  pop     r14
0x18001428a  pop     r13
0x18001428c  pop     r12
0x18001428e  pop     rdi
0x18001428f  pop     rsi
0x180014290  pop     rbx
0x180014291  pop     rbp
0x180014292  retn
0x180014293  mov     r9d, eax; char *
0x180014296  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001429d  mov     edx, 0CBh; void *
0x1800142a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800142a8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800142af  mov     edx, 0BDh; void *
0x1800142b4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800142ba  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800142c1  mov     edx, 0BEh; void *
0x1800142c6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
