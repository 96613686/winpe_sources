# _GetDefaultAccount

- ea: `0x18001f668`
- end: `0x18001f811`
- name: `_GetDefaultAccount`
- size: `425`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dbe0`
- `0x180020030`

## callees

- `0x18001cea8`
- `0x18001f668`
- `0x18001f818`
- `0x180038c6c`
- `0x18004d010`

## string_xrefs

- `0x18001f746`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18001f78f`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18001f7e7`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`

## pseudocode

```c
__int64 __fastcall GetDefaultAccount(__int64 *a1, __int64 a2)
{
  __int64 v3; // rax
  int v4; // eax
  int DefaultSignInAccount; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdi
  int v8; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v12; // [rsp+40h] [rbp+20h] BYREF
  __int64 v13; // [rsp+50h] [rbp+30h] BYREF

  v12 = 0;
  v3 = *a1;
  v13 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v3 + 232))(a1, &v13);
  DefaultSignInAccount = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v4,
      savedregs);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return (unsigned int)DefaultSignInAccount;
  }
  v6 = v12;
  v12 = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = v13;
  DefaultSignInAccount = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(v13);
  if ( DefaultSignInAccount < 0
    || (DefaultSignInAccount = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 64LL))(v7, &v12),
        DefaultSignInAccount < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)DefaultSignInAccount,
      savedregs);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return (unsigned int)DefaultSignInAccount;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 48LL))(v12, a2);
  DefaultSignInAccount = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v8,
      savedregs);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v12);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v13);
    return (unsigned int)DefaultSignInAccount;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return 0;
}

```

## disassembly

```asm
0x18001f668  mov     [rsp-18h+arg_8], rbx
0x18001f66d  push    rbp
0x18001f66e  push    rsi
0x18001f66f  push    rdi; int
0x18001f670  mov     rbp, rsp
0x18001f673  sub     rsp, 20h
0x18001f677  mov     rsi, rdx
0x18001f67a  mov     [rbp+arg_0], 0
0x18001f682  mov     rax, [rcx]
0x18001f685  mov     [rbp+arg_10], 0
0x18001f68d  lea     rdx, [rbp+arg_10]
0x18001f691  mov     rax, [rax+0E8h]
0x18001f698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f69d  mov     ebx, eax
0x18001f69f  test    eax, eax
0x18001f6a1  js      loc_18001F788
0x18001f6a7  mov     rcx, [rbp+arg_0]
0x18001f6ab  mov     [rbp+arg_0], 0
0x18001f6b3  test    rcx, rcx
0x18001f6b6  jnz     loc_18001F7CF
0x18001f6bc  mov     rdi, [rbp+arg_10]
0x18001f6c0  mov     rcx, rdi
0x18001f6c3  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)
0x18001f6c8  mov     ebx, eax
0x18001f6ca  test    eax, eax
0x18001f6cc  js      short loc_18001F73F
0x18001f6ce  mov     rax, [rdi]
0x18001f6d1  lea     rdx, [rbp+arg_0]
0x18001f6d5  mov     rcx, rdi
0x18001f6d8  mov     rax, [rax+40h]
0x18001f6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6e1  mov     ebx, eax
0x18001f6e3  test    eax, eax
0x18001f6e5  js      short loc_18001F73F
0x18001f6e7  mov     rcx, [rbp+arg_0]
0x18001f6eb  mov     rax, [rcx]
0x18001f6ee  mov     rdx, rsi
0x18001f6f1  mov     rax, [rax+30h]
0x18001f6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6fa  mov     ebx, eax
0x18001f6fc  test    eax, eax
0x18001f6fe  js      loc_18001F7E0
0x18001f704  mov     rcx, [rbp+arg_0]
0x18001f708  test    rcx, rcx
0x18001f70b  jz      short loc_18001F71A
0x18001f70d  mov     rax, [rcx]
0x18001f710  mov     rax, [rax+10h]
0x18001f714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f719  nop
0x18001f71a  mov     rcx, [rbp+arg_10]
0x18001f71e  test    rcx, rcx
0x18001f721  jz      short loc_18001F730
0x18001f723  mov     rax, [rcx]
0x18001f726  mov     rax, [rax+10h]
0x18001f72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f72f  nop
0x18001f730  xor     eax, eax
0x18001f732  mov     rbx, [rsp+20h+arg_8]
0x18001f737  add     rsp, 20h
0x18001f73b  pop     rdi
0x18001f73c  pop     rsi
0x18001f73d  pop     rbp
0x18001f73e  retn
0x18001f73f  mov     rcx, [rbp+18h]; this
0x18001f743  mov     r9d, ebx; char *
0x18001f746  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18001f74d  mov     edx, 4Bh ; 'K'; void *
0x18001f752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f757  nop
0x18001f758  mov     rcx, [rbp+arg_0]
0x18001f75c  test    rcx, rcx
0x18001f75f  jz      short loc_18001F76E
0x18001f761  mov     rax, [rcx]
0x18001f764  mov     rax, [rax+10h]
0x18001f768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f76d  nop
0x18001f76e  mov     rcx, [rbp+arg_10]
0x18001f772  test    rcx, rcx
0x18001f775  jz      short loc_18001F784
0x18001f777  mov     rax, [rcx]
0x18001f77a  mov     rax, [rax+10h]
0x18001f77e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f783  nop
0x18001f784  mov     eax, ebx
0x18001f786  jmp     short loc_18001F732
0x18001f788  mov     rcx, [rbp+18h]; this
0x18001f78c  mov     r9d, ebx; char *
0x18001f78f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18001f796  mov     edx, 49h ; 'I'; void *
0x18001f79b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f7a0  nop
0x18001f7a1  mov     rcx, [rbp+arg_0]
0x18001f7a5  test    rcx, rcx
0x18001f7a8  jz      short loc_18001F7B7
0x18001f7aa  mov     rax, [rcx]
0x18001f7ad  mov     rax, [rax+10h]
0x18001f7b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7b6  nop
0x18001f7b7  mov     rcx, [rbp+arg_10]
0x18001f7bb  test    rcx, rcx
0x18001f7be  jz      short loc_18001F7CD
0x18001f7c0  mov     rax, [rcx]
0x18001f7c3  mov     rax, [rax+10h]
0x18001f7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7cc  nop
0x18001f7cd  jmp     short loc_18001F784
0x18001f7cf  mov     rax, [rcx]
0x18001f7d2  mov     rax, [rax+10h]
0x18001f7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7db  jmp     loc_18001F6BC
0x18001f7e0  mov     rcx, [rbp+18h]; this
0x18001f7e4  mov     r9d, ebx; char *
0x18001f7e7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18001f7ee  mov     edx, 4Dh ; 'M'; void *
0x18001f7f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f7f8  nop
0x18001f7f9  lea     rcx, [rbp+arg_0]
0x18001f7fd  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x18001f802  nop
0x18001f803  lea     rcx, [rbp+arg_10]
0x18001f807  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x18001f80c  jmp     loc_18001F784
```
