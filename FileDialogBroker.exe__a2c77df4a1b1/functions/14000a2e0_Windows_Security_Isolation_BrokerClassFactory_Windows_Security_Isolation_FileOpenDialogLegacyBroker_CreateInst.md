# Windows::Security::Isolation::BrokerClassFactory<Windows::Security::Isolation::FileOpenDialogLegacyBroker>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x14000a2e0`
- end: `0x14000a388`
- name: `?CreateInstance@?$BrokerClassFactory@VFileOpenDialogLegacyBroker@Isolation@Security@Windows@@@Isolation@Security@Windows@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005084`
- `0x1400066d0`
- `0x1400085fc`
- `0x140009174`
- `0x14000a2e0`
- `0x14000f99c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a2fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a2fc`

## string_xrefs

- `0x14000a349`: `onecoreuap\ds\security\isolation\inc\BrokerClassFactory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::BrokerClassFactory<Windows::Security::Isolation::FileOpenDialogLegacyBroker>::CreateInstance(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  RTL_SRWLOCK *v6; // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v13; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v14; // [rsp+48h] [rbp+20h] BYREF

  v6 = a1 + 3;
  AcquireSRWLockExclusive(a1 + 3);
  v14 = v6;
  *a4 = 0;
  v13 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileOpenDialogLegacyBroker,IUnknown,>(&v13);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v7 = wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to((__int64 (__fastcall ****)(_QWORD))&v13, a3, a4);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v8 = 0;
      goto LABEL_7;
    }
    v9 = 29;
  }
  else
  {
    v9 = 28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\ds\\security\\isolation\\inc\\BrokerClassFactory.h",
    (const char *)(unsigned int)v7,
    v11);
LABEL_7:
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>((__int64 *)&v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  return v8;
}

```

## disassembly

```asm
0x14000a2e0  mov     [rsp+arg_8], rbx
0x14000a2e5  mov     [rsp+arg_10], rsi
0x14000a2ea  push    rdi; int
0x14000a2eb  sub     rsp, 20h
0x14000a2ef  mov     rdi, r9
0x14000a2f2  mov     rsi, r8
0x14000a2f5  lea     rbx, [rcx+18h]
0x14000a2f9  mov     rcx, rbx; SRWLock
0x14000a2fc  call    cs:__imp_AcquireSRWLockExclusive
0x14000a302  mov     [rsp+28h+arg_18], rbx
0x14000a307  mov     qword ptr [rdi], 0
0x14000a30e  mov     [rsp+28h+arg_0], 0
0x14000a317  lea     rcx, [rsp+28h+arg_0]
0x14000a31c  call    ??$MakeAndInitialize@VFileOpenDialogLegacyBroker@Isolation@Security@Windows@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileOpenDialogLegacyBroker,IUnknown,>(IUnknown * *)
0x14000a321  mov     ebx, eax
0x14000a323  test    eax, eax
0x14000a325  jns     short loc_14000A32E
0x14000a327  mov     edx, 1Ch
0x14000a32c  jmp     short loc_14000A349
0x14000a32e  mov     r8, rdi
0x14000a331  mov     rdx, rsi
0x14000a334  lea     rcx, [rsp+28h+arg_0]
0x14000a339  call    ?copy_to@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEBAJAEBU_GUID@@PEAPEAX@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(_GUID const &,void * *)
0x14000a33e  mov     ebx, eax
0x14000a340  test    eax, eax
0x14000a342  jns     short loc_14000A35F
0x14000a344  mov     edx, 1Dh; void *
0x14000a349  lea     r8, aOnecoreuapDsSe_2; "onecoreuap\\ds\\security\\isolation\\in"...
0x14000a350  mov     r9d, eax; char *
0x14000a353  mov     rcx, [rsp+28h]; this
0x14000a358  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a35d  jmp     short loc_14000A361
0x14000a35f  xor     ebx, ebx
0x14000a361  lea     rcx, [rsp+28h+arg_0]
0x14000a366  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000a36b  nop
0x14000a36c  lea     rcx, [rsp+28h+arg_18]
0x14000a371  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000a376  mov     eax, ebx
0x14000a378  mov     rbx, [rsp+28h+arg_8]
0x14000a37d  mov     rsi, [rsp+28h+arg_10]
0x14000a382  add     rsp, 20h
0x14000a386  pop     rdi
0x14000a387  retn
```
