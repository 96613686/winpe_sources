# Windows::Security::Isolation::BrokerClassFactory<Windows::Security::Isolation::ShellObjectBroker>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1400100f0`
- end: `0x140010198`
- name: `?CreateInstance@?$BrokerClassFactory@VShellObjectBroker@Isolation@Security@Windows@@@Isolation@Security@Windows@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005084`
- `0x1400066d0`
- `0x140009174`
- `0x14000f99c`
- `0x14000fb74`
- `0x1400100f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001010c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001010c`

## string_xrefs

- `0x140010159`: `onecoreuap\ds\security\isolation\inc\BrokerClassFactory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::BrokerClassFactory<Windows::Security::Isolation::ShellObjectBroker>::CreateInstance(
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
  __int64 v13; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v14; // [rsp+48h] [rbp+20h] BYREF

  v6 = a1 + 3;
  AcquireSRWLockExclusive(a1 + 3);
  v14 = v6;
  *a4 = 0;
  v13 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::ShellObjectBroker,IUnknown,>(&v13);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v7 = wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(&v13, a3, a4);
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
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  return v8;
}

```

## disassembly

```asm
0x1400100f0  mov     [rsp+arg_8], rbx
0x1400100f5  mov     [rsp+arg_10], rsi
0x1400100fa  push    rdi; int
0x1400100fb  sub     rsp, 20h
0x1400100ff  mov     rdi, r9
0x140010102  mov     rsi, r8
0x140010105  lea     rbx, [rcx+18h]
0x140010109  mov     rcx, rbx; SRWLock
0x14001010c  call    cs:__imp_AcquireSRWLockExclusive
0x140010112  mov     [rsp+28h+arg_18], rbx
0x140010117  mov     qword ptr [rdi], 0
0x14001011e  mov     [rsp+28h+arg_0], 0
0x140010127  lea     rcx, [rsp+28h+arg_0]
0x14001012c  call    ??$MakeAndInitialize@VShellObjectBroker@Isolation@Security@Windows@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::ShellObjectBroker,IUnknown,>(IUnknown * *)
0x140010131  mov     ebx, eax
0x140010133  test    eax, eax
0x140010135  jns     short loc_14001013E
0x140010137  mov     edx, 1Ch
0x14001013c  jmp     short loc_140010159
0x14001013e  mov     r8, rdi
0x140010141  mov     rdx, rsi
0x140010144  lea     rcx, [rsp+28h+arg_0]
0x140010149  call    ?copy_to@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEBAJAEBU_GUID@@PEAPEAX@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::copy_to(_GUID const &,void * *)
0x14001014e  mov     ebx, eax
0x140010150  test    eax, eax
0x140010152  jns     short loc_14001016F
0x140010154  mov     edx, 1Dh; void *
0x140010159  lea     r8, aOnecoreuapDsSe_2; "onecoreuap\\ds\\security\\isolation\\in"...
0x140010160  mov     r9d, eax; char *
0x140010163  mov     rcx, [rsp+28h]; this
0x140010168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001016d  jmp     short loc_140010171
0x14001016f  xor     ebx, ebx
0x140010171  lea     rcx, [rsp+28h+arg_0]
0x140010176  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14001017b  nop
0x14001017c  lea     rcx, [rsp+28h+arg_18]
0x140010181  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140010186  mov     eax, ebx
0x140010188  mov     rbx, [rsp+28h+arg_8]
0x14001018d  mov     rsi, [rsp+28h+arg_10]
0x140010192  add     rsp, 20h
0x140010196  pop     rdi
0x140010197  retn
```
