# DoDeleteProfile(_GUID const &,ushort const *)

- ea: `0x180016460`
- end: `0x180016554`
- name: `?DoDeleteProfile@@YAJAEBU_GUID@@PEBG@Z`
- size: `244`
- prototype: `__int64 __fastcall(const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015ee0`

## callees

- `0x180003530`
- `0x180008a38`
- `0x18000a5c4`
- `0x18000db9c`
- `0x1800150e8`
- `0x1800155e0`
- `0x180016460`
- `0x180018070`
- `0x180018400`
- `0x180018564`

## import_xrefs

- `USERENV!DeleteProfileW` at `0x1800164e1`
- `USERENV!DeleteProfileW` at `0x1800164e1`

## string_xrefs

- `0x180016485`: `PolicyDrivenProfileDelete`
- `0x180016505`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DoDeleteProfile(const struct _GUID *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  int Error; // eax
  unsigned int v6; // ebx
  int v8[4]; // [rsp+20h] [rbp-178h] BYREF
  _QWORD v9[34]; // [rsp+30h] [rbp-168h] BYREF
  __int64 v10; // [rsp+140h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v9,
    "PolicyDrivenProfileDelete");
  v9[0] = &AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete::`vftable';
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    v9,
    v8);
  v4 = v10;
  *(struct _GUID *)(v10 + 24) = *a1;
  *(_BYTE *)(v4 + 4) = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v8);
  AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete::StartActivity((AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete *)v9);
  if ( DeleteProfileW(a2, 0, 0) || (Error = ResultFromKnownLastError(), v6 = Error, Error == -2147024894) )
  {
    wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v9);
    v6 = 0;
  }
  else if ( Error < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      (const char *)(unsigned int)Error,
      v8[0]);
  }
  AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete::~PolicyDrivenProfileDelete((AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete *)v9);
  return v6;
}

```

## disassembly

```asm
0x180016460  mov     [rsp+arg_0], rbx
0x180016465  push    rdi
0x180016466  sub     rsp, 190h
0x18001646d  mov     rax, cs:__security_cookie
0x180016474  xor     rax, rsp
0x180016477  mov     [rsp+198h+var_18], rax
0x18001647f  mov     rdi, rdx
0x180016482  mov     rbx, rcx
0x180016485  lea     rdx, aPolicydrivenpr; "PolicyDrivenProfileDelete"
0x18001648c  lea     rcx, [rsp+198h+var_168]
0x180016491  call    ??0?$ActivityBase@VAccountManagerUserModelTelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016496  lea     rax, ??_7PolicyDrivenProfileDelete@AccountManagerUserModelTelemetry@@6B@; const AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete::`vftable'
0x18001649d  lea     rdx, [rsp+198h+var_178]
0x1800164a2  mov     [rsp+198h+var_168], rax
0x1800164a7  lea     rcx, [rsp+198h+var_168]
0x1800164ac  call    ?LockExclusive@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800164b1  mov     rax, [rsp+198h+var_58]
0x1800164b9  lea     rcx, [rsp+198h+var_178]
0x1800164be  movups  xmm0, xmmword ptr [rbx]
0x1800164c1  movdqu  xmmword ptr [rax+18h], xmm0
0x1800164c6  mov     byte ptr [rax+4], 1
0x1800164ca  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800164cf  lea     rcx, [rsp+198h+var_168]; this
0x1800164d4  call    ?StartActivity@PolicyDrivenProfileDelete@AccountManagerUserModelTelemetry@@QEAAXXZ; AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete::StartActivity(void)
0x1800164d9  xor     r8d, r8d; lpComputerName
0x1800164dc  xor     edx, edx; lpProfilePath
0x1800164de  mov     rcx, rdi; lpSidString
0x1800164e1  call    cs:__imp_DeleteProfileW
0x1800164e7  test    eax, eax
0x1800164e9  jnz     short loc_18001651B
0x1800164eb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800164f0  mov     ebx, eax
0x1800164f2  cmp     eax, 80070002h
0x1800164f7  jz      short loc_18001651B
0x1800164f9  test    eax, eax
0x1800164fb  jns     short loc_180016527
0x1800164fd  mov     rcx, [rsp+198h]; this
0x180016505  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001650c  mov     r9d, eax; char *
0x18001650f  mov     edx, 63h ; 'c'; void *
0x180016514  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016519  jmp     short loc_180016527
0x18001651b  lea     rcx, [rsp+198h+var_168]
0x180016520  call    ?Stop@?$ActivityBase@VAccountManagerUserModelTelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180016525  xor     ebx, ebx
0x180016527  lea     rcx, [rsp+198h+var_168]; this
0x18001652c  call    ??1PolicyDrivenProfileDelete@AccountManagerUserModelTelemetry@@QEAA@XZ; AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete::~PolicyDrivenProfileDelete(void)
0x180016531  mov     eax, ebx
0x180016533  mov     rcx, [rsp+198h+var_18]
0x18001653b  xor     rcx, rsp; StackCookie
0x18001653e  call    __security_check_cookie
0x180016543  mov     rbx, [rsp+198h+arg_0]
0x18001654b  add     rsp, 190h
0x180016552  pop     rdi
0x180016553  retn
```
