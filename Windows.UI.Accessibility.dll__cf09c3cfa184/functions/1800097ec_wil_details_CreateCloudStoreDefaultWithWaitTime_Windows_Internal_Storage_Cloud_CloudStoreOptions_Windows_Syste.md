# wil::details::CreateCloudStoreDefaultWithWaitTime(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,ushort const *,Windows::Internal::Storage::Cloud::WaitTimes const &)

- ea: `0x1800097ec`
- end: `0x180009958`
- name: `?CreateCloudStoreDefaultWithWaitTime@details@wil@@YA?AV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@W4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@8@PEAUIWebAccount@Credentials@Security@8@PEBGAEBUWaitTimes@5678@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016e90`

## callees

- `0x180003980`
- `0x18000842c`
- `0x1800085b8`
- `0x180008ebc`
- `0x180008f04`
- `0x1800097ec`
- `0x180009cc8`
- `0x18000cf94`
- `0x180035010`

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
0x1800097ec  push    rbp
0x1800097ee  push    rbx
0x1800097ef  push    rsi
0x1800097f0  push    rdi
0x1800097f1  push    r12
0x1800097f3  push    r13
0x1800097f5  push    r14
0x1800097f7  push    r15
0x1800097f9  lea     rbp, [rsp-0Fh]
0x1800097fe  sub     rsp, 0A8h
0x180009805  mov     rax, cs:__security_cookie
0x18000980c  xor     rax, rsp
0x18000980f  mov     [rbp+47h+var_48], rax
0x180009813  mov     r13, r9
0x180009816  mov     r12, r8
0x180009819  mov     r15d, edx
0x18000981c  mov     r14, rcx
0x18000981f  mov     [rbp+47h+var_70], rcx
0x180009823  mov     rax, [rbp+47h+arg_20]
0x180009827  mov     [rbp+47h+var_90], rax
0x18000982b  mov     rbx, [rbp+47h+arg_28]
0x18000982f  mov     [rbp+47h+var_A0], 0
0x180009836  mov     rcx, [rbp+4Fh]; this
0x18000983a  test    dl, 1
0x18000983d  jnz     loc_180009934
0x180009843  mov     rcx, [rbp+4Fh]; this
0x180009847  test    r15b, 2
0x18000984b  jnz     loc_180009946
0x180009851  lea     rcx, [rbp+47h+var_98]
0x180009855  call    ??$GetActivationFactory@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z; wil::details::GetActivationFactory<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(ushort const *)
0x18000985a  nop
0x18000985b  mov     qword ptr [r14], 0
0x180009862  mov     [rbp+47h+var_A0], 1
0x180009869  mov     rsi, [rbp+47h+var_98]
0x18000986d  mov     rax, [rsi]
0x180009870  mov     rdi, [rax+38h]
0x180009874  mov     [rbp+47h+var_88], r14
0x180009878  mov     [rbp+47h+var_80], 0
0x180009880  mov     [rbp+47h+var_78], 1
0x180009884  mov     rbx, [rbx]
0x180009887  lea     rdx, [rbp+47h+var_90]
0x18000988b  lea     rcx, [rbp+47h+var_68]
0x18000988f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180009894  mov     r10, rax
0x180009897  mov     rax, r13
0x18000989a  neg     rax
0x18000989d  sbb     edx, edx
0x18000989f  not     edx
0x1800098a1  and     edx, 2
0x1800098a4  xor     eax, eax
0x1800098a6  test    r12, r12
0x1800098a9  setz    al
0x1800098ac  or      edx, eax
0x1800098ae  or      edx, r15d
0x1800098b1  lea     rax, [rbp+47h+var_80]
0x1800098b5  mov     [rsp+0E0h+var_B0], rax
0x1800098ba  mov     [rsp+0E0h+var_B8], rbx
0x1800098bf  mov     rax, [r10+18h]
0x1800098c3  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800098c8  mov     r9, r13
0x1800098cb  mov     r8, r12
0x1800098ce  mov     rcx, rsi
0x1800098d1  mov     rax, rdi
0x1800098d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098d9  mov     rcx, [rbp+4Fh]; this
0x1800098dd  test    eax, eax
0x1800098df  js      short loc_18000991F
0x1800098e1  mov     [rbp+47h+var_50], 0
0x1800098e9  lea     rcx, [rbp+47h+var_88]
0x1800098ed  call    ??1?$out_param_t@V?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>>(void)
0x1800098f2  nop
0x1800098f3  lea     rcx, [rbp+47h+var_98]
0x1800098f7  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x1800098fc  mov     rax, r14
0x1800098ff  mov     rcx, [rbp+47h+var_48]
0x180009903  xor     rcx, rsp; StackCookie
0x180009906  call    __security_check_cookie
0x18000990b  add     rsp, 0A8h
0x180009912  pop     r15
0x180009914  pop     r14
0x180009916  pop     r13
0x180009918  pop     r12
0x18000991a  pop     rdi
0x18000991b  pop     rsi
0x18000991c  pop     rbx
0x18000991d  pop     rbp
0x18000991e  retn
0x18000991f  mov     r9d, eax; char *
0x180009922  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180009929  mov     edx, 0CBh; void *
0x18000992e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009934  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18000993b  mov     edx, 0BDh; void *
0x180009940  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009946  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18000994d  mov     edx, 0BEh; void *
0x180009952  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
