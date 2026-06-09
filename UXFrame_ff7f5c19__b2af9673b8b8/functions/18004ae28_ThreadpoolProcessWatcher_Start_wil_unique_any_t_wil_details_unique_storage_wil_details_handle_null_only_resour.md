# ThreadpoolProcessWatcher::Start(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::function<void (void)> &&,_FILETIME *)

- ea: `0x18004ae28`
- end: `0x18004af23`
- name: `?Start@ThreadpoolProcessWatcher@@QEAAXV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV?$function@$$A6AXXZ@std@@PEAU_FILETIME@@@Z`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180049bf8`

## callees

- `0x1800088e4`
- `0x18000e2a0`
- `0x18001049c`
- `0x180017008`
- `0x18002d484`
- `0x18003e968`
- `0x18003ef1c`
- `0x18004ae28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ae48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ae48`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004aec3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004aec3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004aefc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004aefc`

## string_xrefs

- `0x18004ae5e`: `Internal\Shell\Inc\ThreadpoolWaitHelpers.h`
- `0x18004aee3`: `Internal\Shell\Inc\ThreadpoolWaitHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ThreadpoolProcessWatcher::Start(RTL_SRWLOCK *a1, HANDLE *a2, __int64 a3)
{
  __int64 *v6; // rbx
  const char *v7; // r9
  _DWORD *Ptr; // rax
  volatile signed __int32 *v9; // rax
  PVOID v10; // rcx
  std::_Ref_count_base *v11; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v13; // r9
  struct _TP_WAIT *v14; // rcx
  _QWORD v16[7]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v16[1] = a2;
  v6 = (__int64 *)&a1[2];
  AcquireSRWLockExclusive(a1 + 2);
  v16[0] = v6;
  if ( LOBYTE(a1[11].Ptr) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x54,
      (unsigned int)"Internal\\Shell\\Inc\\ThreadpoolWaitHelpers.h",
      v7);
  Ptr = a1[13].Ptr;
  if ( !Ptr || !Ptr[2] )
  {
    v9 = (volatile signed __int32 *)a1[1].Ptr;
    if ( v9 )
    {
      v10 = a1->Ptr;
      _InterlockedIncrement(v9 + 3);
    }
    else
    {
      v10 = 0;
    }
    a1[12].Ptr = v10;
    v11 = (std::_Ref_count_base *)a1[13].Ptr;
    a1[13].Ptr = (PVOID)v9;
    if ( v11 )
      std::_Ref_count_base::_Decwref(v11);
  }
  std::function<void (void)>::operator=(&a1[3], a3);
  ThreadpoolWait = CreateThreadpoolWait(
                     _lambda_8b0b9dbd4459d626ffc8152be8328efc_::_lambda_invoker_cdecl_<_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,unsigned long>,
                     &a1[12],
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    &a1[14],
    ThreadpoolWait);
  v14 = (struct _TP_WAIT *)a1[14].Ptr;
  if ( !v14 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x77,
      (unsigned int)"Internal\\Shell\\Inc\\ThreadpoolWaitHelpers.h",
      v13);
  SetThreadpoolWait(v14, *a2, 0);
  LOBYTE(a1[11].Ptr) = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v16);
  return wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
}

```

## disassembly

```asm
0x18004ae28  push    rbx
0x18004ae2a  push    rbp
0x18004ae2b  push    rsi
0x18004ae2c  push    rdi
0x18004ae2d  push    r14
0x18004ae2f  sub     rsp, 30h
0x18004ae33  mov     rbp, r8
0x18004ae36  mov     r14, rdx
0x18004ae39  mov     rdi, rcx
0x18004ae3c  mov     [rsp+58h+var_30], rdx
0x18004ae41  lea     rbx, [rcx+10h]
0x18004ae45  mov     rcx, rbx; SRWLock
0x18004ae48  call    cs:__imp_AcquireSRWLockExclusive
0x18004ae4e  mov     [rsp+58h+var_38], rbx
0x18004ae53  mov     rcx, [rsp+58h]; this
0x18004ae58  cmp     byte ptr [rdi+58h], 0
0x18004ae5c  jz      short loc_18004AE70
0x18004ae5e  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\ThreadpoolWaitHel"...
0x18004ae65  mov     edx, 54h ; 'T'; void *
0x18004ae6a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004ae70  mov     rax, [rdi+68h]
0x18004ae74  test    rax, rax
0x18004ae77  jz      short loc_18004AE7F
0x18004ae79  cmp     dword ptr [rax+8], 0
0x18004ae7d  jnz     short loc_18004AEA9
0x18004ae7f  mov     rax, [rdi+8]
0x18004ae83  test    rax, rax
0x18004ae86  jz      short loc_18004AE91
0x18004ae88  mov     rcx, [rdi]
0x18004ae8b  lock inc dword ptr [rax+0Ch]
0x18004ae8f  jmp     short loc_18004AE93
0x18004ae91  xor     ecx, ecx
0x18004ae93  mov     [rdi+60h], rcx
0x18004ae97  mov     rcx, [rdi+68h]; this
0x18004ae9b  mov     [rdi+68h], rax
0x18004ae9f  test    rcx, rcx
0x18004aea2  jz      short loc_18004AEA9
0x18004aea4  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18004aea9  lea     rcx, [rdi+18h]
0x18004aead  mov     rdx, rbp
0x18004aeb0  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18004aeb5  xor     r8d, r8d; pcbe
0x18004aeb8  lea     rdx, [rdi+60h]; pv
0x18004aebc  lea     rcx, ??$_lambda_invoker_cdecl_@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@_lambda_8b0b9dbd4459d626ffc8152be8328efc_@@CA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18004aec3  call    cs:__imp_CreateThreadpoolWait
0x18004aec9  mov     rdx, rax
0x18004aecc  lea     rcx, [rdi+70h]
0x18004aed0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18004aed5  mov     rcx, [rdi+70h]; pwa
0x18004aed9  mov     rax, [rsp+58h]
0x18004aede  test    rcx, rcx
0x18004aee1  jnz     short loc_18004AEF6
0x18004aee3  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\ThreadpoolWaitHel"...
0x18004aeea  lea     edx, [rcx+77h]; void *
0x18004aeed  mov     rcx, rax; this
0x18004aef0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004aef6  xor     r8d, r8d; pftTimeout
0x18004aef9  mov     rdx, [r14]; h
0x18004aefc  call    cs:__imp_SetThreadpoolWait
0x18004af02  mov     byte ptr [rdi+58h], 1
0x18004af06  lea     rcx, [rsp+58h+var_38]
0x18004af0b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004af10  nop
0x18004af11  mov     rcx, r14
0x18004af14  add     rsp, 30h
0x18004af18  pop     r14
0x18004af1a  pop     rdi
0x18004af1b  pop     rsi
0x18004af1c  pop     rbp
0x18004af1d  pop     rbx
0x18004af1e  jmp     ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
```
