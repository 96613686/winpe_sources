# WcmCommon::ThreadPoolProcessLatestWorkItem<2>::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18000c400`
- end: `0x18000c577`
- name: `?WorkCallback@?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003550`
- `0x180005ef0`
- `0x180006df8`
- `0x18000c2a4`
- `0x18000c400`
- `0x18000c580`
- `0x18000c5f8`
- `0x18000d2a0`
- `0x18000df4c`
- `0x18000f760`
- `0x18001bad4`
- `0x18001c624`
- `0x180022aac`
- `0x180028010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000c4e4`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000c53e`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000c4e4`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000c53e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c435`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c435`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem<2>::WorkCallback(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2)
{
  ULONG_PTR *p_SpinCount; // rbx
  char *v4; // rax
  void ***v5; // rcx
  std::_Ref_count_base *v6[2]; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v7[40]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v8; // [rsp+58h] [rbp-11h]
  __int64 v9; // [rsp+68h] [rbp-1h]
  _BYTE v10[64]; // [rsp+70h] [rbp+7h] BYREF

  memset_0(v7, 0, 0x40u);
  EnterCriticalSection(a2);
  v6[0] = (std::_Ref_count_base *)a2;
  p_SpinCount = &a2[3].SpinCount;
  v4 = (char *)(p_SpinCount + 16);
  while ( 1 )
  {
    if ( p_SpinCount == (ULONG_PTR *)v4 )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v6);
      goto LABEL_6;
    }
    if ( p_SpinCount[7] )
      break;
    p_SpinCount += 8;
  }
  std::any::any((std::any *)v10, (struct std::any *)v7);
  std::any::operator=(v7, p_SpinCount);
  std::any::operator=(p_SpinCount, v10);
  std::any::reset((std::any *)v10);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v6);
  v5 = &void `RTTI Type Descriptor';
  if ( (v9 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
    v5 = (void ***)(v9 & 0xFFFFFFFFFFFFFFFCuLL);
  if ( (unsigned int)__std_type_info_compare(v5 + 1, &qword_180037760) )
  {
    *(_OWORD *)v6 = 0;
    std::any_cast<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v6, v7);
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v6[0] + 8LL))(v6[0]);
    if ( v6[1] )
      std::_Ref_count_base::_Decref(v6[1]);
  }
  else
  {
    if ( (v9 & 0xFFFFFFFFFFFFFFFCuLL) == 0
      || (unsigned int)__std_type_info_compare((v9 & 0xFFFFFFFFFFFFFFFCuLL) + 8, &qword_180037760)
      || !v8 )
    {
      std::_Throw_bad_any_cast();
    }
    std::function<void (void)>::function<void (void)>(v10);
    std::_Func_class<void,>::operator()(v10);
    std::_Func_class<void,>::~_Func_class<void,>(v10);
  }
LABEL_6:
  std::any::reset((std::any *)v7);
}

```

## disassembly

```asm
0x18000c400  mov     [rsp-8+arg_0], rbx
0x18000c405  push    rbp
0x18000c406  lea     rbp, [rsp-57h]
0x18000c40b  sub     rsp, 0C0h
0x18000c412  mov     rax, cs:__security_cookie
0x18000c419  xor     rax, rsp
0x18000c41c  mov     [rbp+57h+var_10], rax
0x18000c420  mov     rbx, rdx
0x18000c423  xor     edx, edx; Val
0x18000c425  lea     r8d, [rdx+40h]; Size
0x18000c429  lea     rcx, [rbp+57h+var_90]; void *
0x18000c42d  call    memset_0
0x18000c432  mov     rcx, rbx; lpCriticalSection
0x18000c435  call    cs:__imp_EnterCriticalSection
0x18000c43b  mov     [rbp+57h+var_A0], rbx
0x18000c43f  add     rbx, 98h
0x18000c446  lea     rax, [rbx+80h]
0x18000c44d  jmp     short loc_18000C45A
0x18000c44f  cmp     qword ptr [rbx+38h], 0
0x18000c454  jnz     short loc_18000C48F
0x18000c456  add     rbx, 40h ; '@'
0x18000c45a  cmp     rbx, rax
0x18000c45d  jnz     short loc_18000C44F
0x18000c45f  lea     rcx, [rbp+57h+var_A0]
0x18000c463  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000c468  lea     rcx, [rbp+57h+var_90]; this
0x18000c46c  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x18000c471  nop
0x18000c472  mov     rcx, [rbp+57h+var_10]
0x18000c476  xor     rcx, rsp; StackCookie
0x18000c479  call    __security_check_cookie
0x18000c47e  mov     rbx, [rsp+0C0h+arg_0]
0x18000c486  add     rsp, 0C0h
0x18000c48d  pop     rbp
0x18000c48e  retn
0x18000c48f  lea     rdx, [rbp+57h+var_90]; struct std::any *
0x18000c493  lea     rcx, [rbp+57h+var_50]; this
0x18000c497  call    ??0any@std@@QEAA@$$QEAV01@@Z; std::any::any(std::any &&)
0x18000c49c  mov     rdx, rbx
0x18000c49f  lea     rcx, [rbp+57h+var_90]
0x18000c4a3  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x18000c4a8  lea     rdx, [rbp+57h+var_50]
0x18000c4ac  mov     rcx, rbx
0x18000c4af  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x18000c4b4  lea     rcx, [rbp+57h+var_50]; this
0x18000c4b8  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x18000c4bd  lea     rcx, [rbp+57h+var_A0]
0x18000c4c1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000c4c6  mov     rax, [rbp+57h+var_58]
0x18000c4ca  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000c4ce  lea     rcx, ??_R0X@8; void `RTTI Type Descriptor'
0x18000c4d5  cmovnz  rcx, rax
0x18000c4d9  add     rcx, 8
0x18000c4dd  lea     rdx, qword_180037760
0x18000c4e4  call    cs:__imp___std_type_info_compare
0x18000c4ea  test    eax, eax
0x18000c4ec  jz      short loc_18000C529
0x18000c4ee  xorps   xmm0, xmm0
0x18000c4f1  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18000c4f5  lea     rdx, [rbp+57h+var_90]
0x18000c4f9  lea     rcx, [rbp+57h+var_A0]
0x18000c4fd  call    ??$any_cast@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@std@@YA?AV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@0@AEAVany@0@@Z; std::any_cast<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::any &)
0x18000c502  mov     rcx, [rbp+57h+var_A0]
0x18000c506  mov     rax, [rcx]
0x18000c509  mov     rax, [rax+8]
0x18000c50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c512  mov     rcx, [rbp+57h+var_A0+8]; this
0x18000c516  test    rcx, rcx
0x18000c519  jz      loc_18000C468
0x18000c51f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c524  jmp     loc_18000C468
0x18000c529  mov     rcx, [rbp+57h+var_58]
0x18000c52d  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000c531  jz      short loc_18000C571
0x18000c533  add     rcx, 8
0x18000c537  lea     rdx, qword_180037760
0x18000c53e  call    cs:__imp___std_type_info_compare
0x18000c544  test    eax, eax
0x18000c546  jnz     short loc_18000C571
0x18000c548  mov     rdx, [rbp+57h+var_68]
0x18000c54c  test    rdx, rdx
0x18000c54f  jz      short loc_18000C571
0x18000c551  lea     rcx, [rbp+57h+var_50]
0x18000c555  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x18000c55a  lea     rcx, [rbp+57h+var_50]
0x18000c55e  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18000c563  lea     rcx, [rbp+57h+var_50]
0x18000c567  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18000c56c  jmp     loc_18000C468
0x18000c571  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
```
