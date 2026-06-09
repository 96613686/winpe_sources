# Windows::Security::Isolation::BrokerClassFactory<Windows::Security::Isolation::FileSaveDialogLegacyBroker>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x14000a440`
- end: `0x14000a4e8`
- name: `?CreateInstance@?$BrokerClassFactory@VFileSaveDialogLegacyBroker@Isolation@Security@Windows@@@Isolation@Security@Windows@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005084`
- `0x1400066d0`
- `0x14000876c`
- `0x140009174`
- `0x14000a440`
- `0x14000f99c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a45c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a45c`

## string_xrefs

- `0x14000a4a9`: `onecoreuap\ds\security\isolation\inc\BrokerClassFactory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::BrokerClassFactory<Windows::Security::Isolation::FileSaveDialogLegacyBroker>::CreateInstance(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileSaveDialogLegacyBroker,IUnknown,>(&v13);
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
0x14000a440  mov     [rsp+arg_8], rbx
0x14000a445  mov     [rsp+arg_10], rsi
0x14000a44a  push    rdi; int
0x14000a44b  sub     rsp, 20h
0x14000a44f  mov     rdi, r9
0x14000a452  mov     rsi, r8
0x14000a455  lea     rbx, [rcx+18h]
0x14000a459  mov     rcx, rbx; SRWLock
0x14000a45c  call    cs:__imp_AcquireSRWLockExclusive
0x14000a462  mov     [rsp+28h+arg_18], rbx
0x14000a467  mov     qword ptr [rdi], 0
0x14000a46e  mov     [rsp+28h+arg_0], 0
0x14000a477  lea     rcx, [rsp+28h+arg_0]
0x14000a47c  call    ??$MakeAndInitialize@VFileSaveDialogLegacyBroker@Isolation@Security@Windows@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileSaveDialogLegacyBroker,IUnknown,>(IUnknown * *)
0x14000a481  mov     ebx, eax
0x14000a483  test    eax, eax
0x14000a485  jns     short loc_14000A48E
0x14000a487  mov     edx, 1Ch
0x14000a48c  jmp     short loc_14000A4A9
0x14000a48e  mov     r8, rdi
0x14000a491  mov     rdx, rsi
0x14000a494  lea     rcx, [rsp+28h+arg_0]
0x14000a499  call    ?copy_to@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEBAJAEBU_GUID@@PEAPEAX@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(_GUID const &,void * *)
0x14000a49e  mov     ebx, eax
0x14000a4a0  test    eax, eax
0x14000a4a2  jns     short loc_14000A4BF
0x14000a4a4  mov     edx, 1Dh; void *
0x14000a4a9  lea     r8, aOnecoreuapDsSe_2; "onecoreuap\\ds\\security\\isolation\\in"...
0x14000a4b0  mov     r9d, eax; char *
0x14000a4b3  mov     rcx, [rsp+28h]; this
0x14000a4b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a4bd  jmp     short loc_14000A4C1
0x14000a4bf  xor     ebx, ebx
0x14000a4c1  lea     rcx, [rsp+28h+arg_0]
0x14000a4c6  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000a4cb  nop
0x14000a4cc  lea     rcx, [rsp+28h+arg_18]
0x14000a4d1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000a4d6  mov     eax, ebx
0x14000a4d8  mov     rbx, [rsp+28h+arg_8]
0x14000a4dd  mov     rsi, [rsp+28h+arg_10]
0x14000a4e2  add     rsp, 20h
0x14000a4e6  pop     rdi
0x14000a4e7  retn
```
