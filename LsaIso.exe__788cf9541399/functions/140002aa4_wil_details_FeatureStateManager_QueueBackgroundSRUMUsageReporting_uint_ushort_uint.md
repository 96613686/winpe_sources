# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140002aa4`
- end: `0x140002b93`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14000cfd0`

## callees

- `0x140001fe0`
- `0x1400029d0`
- `0x140002aa4`
- `0x140002c64`
- `0x140002c84`
- `0x140002ca8`
- `0x140002cec`
- `0x14000db00`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002ae7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002ae7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140002b43`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140002b43`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  char *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = pv + 40;
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v11, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x140002aa4  push    rbx
0x140002aa6  push    rbp
0x140002aa7  push    rsi
0x140002aa8  push    rdi
0x140002aa9  push    r14
0x140002aab  sub     rsp, 50h
0x140002aaf  mov     rax, cs:__security_cookie
0x140002ab6  xor     rax, rsp
0x140002ab9  mov     [rsp+78h+var_38], rax
0x140002abe  mov     r14d, r9d
0x140002ac1  movzx   ebp, r8w
0x140002ac5  mov     esi, edx
0x140002ac7  mov     rdi, rcx
0x140002aca  cmp     byte ptr [rcx], 0
0x140002acd  jz      loc_140002B7B
0x140002ad3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140002ad8  test    al, al
0x140002ada  jnz     loc_140002B7B
0x140002ae0  lea     rbx, [rdi+28h]
0x140002ae4  mov     rcx, rbx; SRWLock
0x140002ae7  call    cs:__imp_AcquireSRWLockExclusive
0x140002aed  mov     [rsp+78h+var_50], rbx
0x140002af2  xor     eax, eax
0x140002af4  mov     [rsp+78h+var_42], ax
0x140002af9  mov     [rsp+78h+var_48], esi
0x140002afd  mov     [rsp+78h+var_44], bp
0x140002b02  mov     [rsp+78h+var_40], r14d
0x140002b07  lea     rcx, [rdi+0E8h]; this
0x140002b0e  lea     r8d, [rax+0Ch]; unsigned __int64
0x140002b12  lea     rdx, [rsp+78h+var_48]; void *
0x140002b17  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140002b1c  cmp     byte ptr [rdi+40h], 0
0x140002b20  jnz     short loc_140002B70
0x140002b22  lea     rbx, [rdi+38h]
0x140002b26  cmp     qword ptr [rbx], 0
0x140002b2a  jnz     short loc_140002B5E
0x140002b2c  lea     rcx, [rsp+78h+var_58]; this
0x140002b31  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140002b36  xor     r8d, r8d; pcbe
0x140002b39  mov     rdx, rdi; pv
0x140002b3c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140002b43  call    cs:__imp_CreateThreadpoolTimer
0x140002b49  mov     rdx, rax
0x140002b4c  mov     rcx, rbx
0x140002b4f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140002b54  lea     rcx, [rsp+78h+var_58]; this
0x140002b59  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140002b5e  mov     r8d, 1388h
0x140002b64  lea     rdx, [rdi+40h]
0x140002b68  mov     rcx, rbx
0x140002b6b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140002b70  lea     rcx, [rsp+78h+var_50]
0x140002b75  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140002b7a  nop
0x140002b7b  mov     rcx, [rsp+78h+var_38]
0x140002b80  xor     rcx, rsp; StackCookie
0x140002b83  call    __security_check_cookie
0x140002b88  add     rsp, 50h
0x140002b8c  pop     r14
0x140002b8e  pop     rdi
0x140002b8f  pop     rsi
0x140002b90  pop     rbp
0x140002b91  pop     rbx
0x140002b92  retn
```
