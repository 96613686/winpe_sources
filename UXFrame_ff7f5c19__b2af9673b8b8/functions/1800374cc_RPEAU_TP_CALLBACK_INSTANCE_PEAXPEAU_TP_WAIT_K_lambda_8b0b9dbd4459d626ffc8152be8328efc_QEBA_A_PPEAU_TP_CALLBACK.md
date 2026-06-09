# ??$?RPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@_lambda_8b0b9dbd4459d626ffc8152be8328efc_@@QEBA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z

- ea: `0x1800374cc`
- end: `0x1800375bd`
- name: `??$?RPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@_lambda_8b0b9dbd4459d626ffc8152be8328efc_@@QEBA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800370a0`

## callees

- `0x180002b20`
- `0x1800088ac`
- `0x18000890c`
- `0x18000e2a0`
- `0x180017044`
- `0x1800374cc`
- `0x18003ef1c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003756d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003756d`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x180037558`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x180037558`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003759a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003759a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _lambda_8b0b9dbd4459d626ffc8152be8328efc_::operator()<_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,unsigned long>(
        __int64 a1,
        struct _TP_CALLBACK_INSTANCE *a2,
        __int64 a3)
{
  struct _TP_CALLBACK_INSTANCE *v3; // r9
  std::_Ref_count_base *v4; // rcx
  __int64 *v5; // r8
  __int64 v6; // rsi
  std::_Ref_count_base *v7; // rdi
  __int64 v8; // [rsp+30h] [rbp-21h] BYREF
  _BYTE v9[56]; // [rsp+40h] [rbp-11h] BYREF
  __int64 v10; // [rsp+78h] [rbp+27h]

  v3 = a2;
  v4 = *(std::_Ref_count_base **)(a3 + 8);
  if ( v4 && std::_Ref_count_base::_Incref_nz(v4) )
  {
    v6 = *v5;
    v7 = (std::_Ref_count_base *)v5[1];
  }
  else
  {
    v7 = 0;
    v6 = 0;
  }
  if ( v6 )
  {
    DisassociateCurrentThreadFromCallback(v3);
    v10 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(v6 + 16));
    v8 = v6 + 16;
    *(_BYTE *)(v6 + 88) = 0;
    std::function<void (void)>::operator=(v9, v6 + 24);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
    if ( !v10 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    std::_Func_class<void,>::_Tidy(v9);
  }
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
}

```

## disassembly

```asm
0x1800374cc  mov     [rsp-8+arg_0], rbx
0x1800374d1  push    rbp
0x1800374d2  push    rsi
0x1800374d3  push    rdi
0x1800374d4  lea     rbp, [rsp-3Fh]
0x1800374d9  sub     rsp, 90h
0x1800374e0  mov     rax, cs:__security_cookie
0x1800374e7  xor     rax, rsp
0x1800374ea  mov     [rbp+4Fh+var_20], rax
0x1800374ee  mov     r9, rdx
0x1800374f1  xorps   xmm1, xmm1
0x1800374f4  movdqu  [rbp+4Fh+var_80], xmm1
0x1800374f9  mov     rcx, [r8+8]; this
0x1800374fd  test    rcx, rcx
0x180037500  jz      short loc_18003751C
0x180037502  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x180037507  test    al, al
0x180037509  jz      short loc_18003751C
0x18003750b  mov     rsi, [r8]
0x18003750e  mov     qword ptr [rbp+4Fh+var_80], rsi
0x180037512  mov     rdi, [r8+8]
0x180037516  mov     qword ptr [rbp+4Fh+var_80+8], rdi
0x18003751a  jmp     short loc_180037524
0x18003751c  mov     rdi, qword ptr [rbp+4Fh+var_80+8]
0x180037520  mov     rsi, qword ptr [rbp+4Fh+var_80]
0x180037524  test    rsi, rsi
0x180037527  jnz     short loc_180037555
0x180037529  test    rdi, rdi
0x18003752c  jz      short loc_180037536
0x18003752e  mov     rcx, rdi; this
0x180037531  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037536  mov     rcx, [rbp+4Fh+var_20]
0x18003753a  xor     rcx, rsp; StackCookie
0x18003753d  call    __security_check_cookie
0x180037542  mov     rbx, [rsp+0A0h+arg_0]
0x18003754a  add     rsp, 90h
0x180037551  pop     rdi
0x180037552  pop     rsi
0x180037553  pop     rbp
0x180037554  retn
0x180037555  mov     rcx, r9; pci
0x180037558  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x18003755e  mov     [rbp+4Fh+var_28], 0
0x180037566  lea     rbx, [rsi+10h]
0x18003756a  mov     rcx, rbx; SRWLock
0x18003756d  call    cs:__imp_AcquireSRWLockExclusive
0x180037573  mov     [rbp+4Fh+var_70], rbx
0x180037577  mov     byte ptr [rsi+58h], 0
0x18003757b  lea     rdx, [rsi+18h]
0x18003757f  lea     rcx, [rbp+4Fh+var_60]
0x180037583  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x180037588  lea     rcx, [rbp+4Fh+var_70]
0x18003758c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180037591  mov     rcx, [rbp+4Fh+var_28]
0x180037595  test    rcx, rcx
0x180037598  jnz     short loc_1800375A1
0x18003759a  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800375a0  int     3; Trap to Debugger
0x1800375a1  mov     rax, [rcx]
0x1800375a4  mov     rax, [rax+10h]
0x1800375a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375ad  nop
0x1800375ae  lea     rcx, [rbp+4Fh+var_60]
0x1800375b2  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800375b7  jmp     loc_180037529
```
