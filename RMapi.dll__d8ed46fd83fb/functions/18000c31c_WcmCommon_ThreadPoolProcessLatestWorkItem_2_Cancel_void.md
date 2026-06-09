# WcmCommon::ThreadPoolProcessLatestWorkItem<2>::Cancel(void)

- ea: `0x18000c31c`
- end: `0x18000c3f3`
- name: `?Cancel@?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@QEAAXXZ`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cd5c`

## callees

- `0x180003550`
- `0x180005530`
- `0x18000c2a4`
- `0x18000c31c`
- `0x18000c580`
- `0x18000c5f8`
- `0x18001966c`
- `0x1800196c0`
- `0x180028010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000c36f`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000c36f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c328`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c328`

## pseudocode

```c
__int64 __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem<2>::Cancel(__int64 a1)
{
  std::any *v2; // rbx
  void ***v3; // rcx
  __int64 v5; // [rsp+20h] [rbp-48h] BYREF
  std::_Ref_count_base *v6[2]; // [rsp+28h] [rbp-40h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  v5 = a1;
  v2 = (std::any *)(a1 + 152);
  *(_BYTE *)(a1 + 280) = 1;
  if ( *(_QWORD *)(a1 + 120) )
  {
    while ( v2 != (std::any *)(a1 + 280) )
    {
      v3 = &void `RTTI Type Descriptor';
      if ( (*((_QWORD *)v2 + 7) & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
        v3 = (void ***)(*((_QWORD *)v2 + 7) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( !(unsigned int)__std_type_info_compare(v3 + 1, &qword_180037708) )
      {
        *(_OWORD *)v6 = 0;
        std::any_cast<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v6, v2);
        (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v6[0] + 16LL))(v6[0]);
        if ( v6[1] )
          std::_Ref_count_base::_Decref(v6[1]);
      }
      std::any::reset(v2);
      v2 = (std::any *)((char *)v2 + 64);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
      &v5,
      0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      (struct _TP_WORK **)(a1 + 120),
      0);
    WcmCommon::details::TPEnvironment::reset((WcmCommon::details::TPEnvironment *)(a1 + 40));
  }
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v5);
}

```

## disassembly

```asm
0x18000c31c  push    rbx
0x18000c31e  push    rbp
0x18000c31f  push    rsi
0x18000c320  push    rdi
0x18000c321  sub     rsp, 48h
0x18000c325  mov     rdi, rcx
0x18000c328  call    cs:__imp_EnterCriticalSection
0x18000c32e  mov     [rsp+68h+var_48], rdi
0x18000c333  lea     rbx, [rdi+98h]
0x18000c33a  lea     rsi, [rbx+80h]
0x18000c341  mov     byte ptr [rsi], 1
0x18000c344  cmp     qword ptr [rdi+78h], 0
0x18000c349  jz      loc_18000C3DF
0x18000c34f  jmp     short loc_18000C3BA
0x18000c351  mov     rax, [rbx+38h]
0x18000c355  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000c359  lea     rcx, ??_R0X@8; void `RTTI Type Descriptor'
0x18000c360  cmovnz  rcx, rax
0x18000c364  add     rcx, 8
0x18000c368  lea     rdx, qword_180037708
0x18000c36f  call    cs:__imp___std_type_info_compare
0x18000c375  test    eax, eax
0x18000c377  jnz     short loc_18000C3AE
0x18000c379  xorps   xmm0, xmm0
0x18000c37c  movups  xmmword ptr [rsp+68h+var_40], xmm0
0x18000c381  mov     rdx, rbx
0x18000c384  lea     rcx, [rsp+68h+var_40]
0x18000c389  call    ??$any_cast@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@std@@YA?AV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@0@AEAVany@0@@Z; std::any_cast<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::any &)
0x18000c38e  mov     rcx, [rsp+68h+var_40]
0x18000c393  mov     rax, [rcx]
0x18000c396  mov     rax, [rax+10h]
0x18000c39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c39f  mov     rcx, [rsp+68h+var_40+8]; this
0x18000c3a4  test    rcx, rcx
0x18000c3a7  jz      short loc_18000C3AE
0x18000c3a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c3ae  mov     rcx, rbx; this
0x18000c3b1  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x18000c3b6  add     rbx, 40h ; '@'
0x18000c3ba  cmp     rbx, rsi
0x18000c3bd  jnz     short loc_18000C351
0x18000c3bf  xor     edx, edx
0x18000c3c1  lea     rcx, [rsp+68h+var_48]
0x18000c3c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18000c3cb  xor     edx, edx
0x18000c3cd  lea     rcx, [rdi+78h]
0x18000c3d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18000c3d6  lea     rcx, [rdi+28h]; this
0x18000c3da  call    ?reset@TPEnvironment@details@WcmCommon@@QEAAXXZ; WcmCommon::details::TPEnvironment::reset(void)
0x18000c3df  lea     rcx, [rsp+68h+var_48]
0x18000c3e4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000c3e9  nop
0x18000c3ea  add     rsp, 48h
0x18000c3ee  pop     rdi
0x18000c3ef  pop     rsi
0x18000c3f0  pop     rbp
0x18000c3f1  pop     rbx
0x18000c3f2  retn
```
