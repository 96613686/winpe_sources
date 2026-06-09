# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180049dd0`
- end: `0x180049ec7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `247`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800702f0`

## callees

- `0x180043ea4`
- `0x180044324`
- `0x180049dd0`
- `0x18004a270`
- `0x18004a2d0`
- `0x18004a3e4`
- `0x1800539fc`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049ea8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049ea8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049e1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049e1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180049e73`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180049e73`

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
  __int64 v10; // [rsp+28h] [rbp-50h]
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  v10 = -2;
  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
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
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x180049dd0  push    rbx
0x180049dd2  push    rbp
0x180049dd3  push    rsi
0x180049dd4  push    rdi
0x180049dd5  push    r14
0x180049dd7  sub     rsp, 50h
0x180049ddb  mov     [rsp+78h+var_50], 0FFFFFFFFFFFFFFFEh
0x180049de4  mov     rax, cs:__security_cookie
0x180049deb  xor     rax, rsp
0x180049dee  mov     [rsp+78h+var_38], rax
0x180049df3  mov     r14d, r9d
0x180049df6  movzx   ebp, r8w
0x180049dfa  mov     edi, edx
0x180049dfc  mov     rbx, rcx
0x180049dff  cmp     byte ptr [rcx], 0
0x180049e02  jz      loc_180049EAF
0x180049e08  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180049e0d  test    al, al
0x180049e0f  jnz     loc_180049EAF
0x180049e15  lea     rsi, [rbx+28h]
0x180049e19  mov     rcx, rsi; SRWLock
0x180049e1c  call    cs:__imp_AcquireSRWLockExclusive
0x180049e22  xor     eax, eax
0x180049e24  mov     [rsp+78h+var_42], ax
0x180049e29  mov     [rsp+78h+var_48], edi
0x180049e2d  mov     [rsp+78h+var_44], bp
0x180049e32  mov     [rsp+78h+var_40], r14d
0x180049e37  lea     rcx, [rbx+0E8h]; this
0x180049e3e  lea     r8d, [rax+0Ch]; unsigned __int64
0x180049e42  lea     rdx, [rsp+78h+var_48]; void *
0x180049e47  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180049e4c  cmp     byte ptr [rbx+40h], 0
0x180049e50  jnz     short loc_180049EA0
0x180049e52  lea     rdi, [rbx+38h]
0x180049e56  cmp     qword ptr [rdi], 0
0x180049e5a  jnz     short loc_180049E8E
0x180049e5c  lea     rcx, [rsp+78h+var_58]; this
0x180049e61  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180049e66  xor     r8d, r8d; pcbe
0x180049e69  mov     rdx, rbx; pv
0x180049e6c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180049e73  call    cs:__imp_CreateThreadpoolTimer
0x180049e79  mov     rdx, rax
0x180049e7c  mov     rcx, rdi
0x180049e7f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180049e84  lea     rcx, [rsp+78h+var_58]; this
0x180049e89  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180049e8e  mov     r8d, 1388h
0x180049e94  lea     rdx, [rbx+40h]
0x180049e98  mov     rcx, rdi
0x180049e9b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180049ea0  test    rsi, rsi
0x180049ea3  jz      short loc_180049EAF
0x180049ea5  mov     rcx, rsi; SRWLock
0x180049ea8  call    cs:__imp_ReleaseSRWLockExclusive
0x180049eae  nop
0x180049eaf  mov     rcx, [rsp+78h+var_38]
0x180049eb4  xor     rcx, rsp; StackCookie
0x180049eb7  call    __security_check_cookie
0x180049ebc  add     rsp, 50h
0x180049ec0  pop     r14
0x180049ec2  pop     rdi
0x180049ec3  pop     rsi
0x180049ec4  pop     rbp
0x180049ec5  pop     rbx
0x180049ec6  retn
```
