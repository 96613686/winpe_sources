# MpWatchDog::Wd1dsManager::~Wd1dsManager(void)

- ea: `0x1400aa6f4`
- end: `0x1400aa7f8`
- name: `??1Wd1dsManager@MpWatchDog@@UEAA@XZ`
- size: `260`
- prototype: `void __fastcall(MpWatchDog::Wd1dsManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400ab9b0`

## callees

- `0x14003a130`
- `0x1400848c8`
- `0x140084970`
- `0x140084a8c`
- `0x1400876a0`
- `0x14008d448`
- `0x1400aa2b0`
- `0x1400aa6f4`
- `0x140166250`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1400aa752`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400aa769`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400aa752`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400aa769`

## pseudocode

```c
void __fastcall MpWatchDog::Wd1dsManager::~Wd1dsManager(MpWatchDog::Wd1dsManager *this)
{
  void *v2; // rdx
  void *v3; // rdx
  __int64 v4; // rdx
  _QWORD *v5; // rdi
  __int64 v6; // rcx

  std::vector<std::wstring>::_Tidy((char *)this + 448);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wchar_t const * const,CommonUtil::AutoRefWrapper<CommonUtil::CCmdOptionsLookupMap::CSimpleMapItem>>>>>>>::_Tidy((char *)this + 408);
  __1__list_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__V__unordered_set_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2__std__V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__V__unordered_set_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2__std___2__std__QEAA_XZ((char *)this + 392);
  std::vector<std::wstring>::_Tidy((char *)this + 360);
  std::vector<CsProtocol::M365a>::_Tidy((char *)this + 336);
  v2 = (void *)*((_QWORD *)this + 40);
  if ( v2 )
    DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v3 = (void *)*((_QWORD *)this + 39);
  if ( v3 )
    DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  std::_Optional_destruct_base<std::variant<MpWatchDog::details::mp_common_raw_metric,MpWatchDog::details::mp_common_agg_metric>,0>::~_Optional_destruct_base<std::variant<MpWatchDog::details::mp_common_raw_metric,MpWatchDog::details::mp_common_agg_metric>,0>((char *)this + 96);
  v5 = (_QWORD *)*((_QWORD *)this + 11);
  if ( v5 )
  {
    std::wstring::_Tidy_deallocate(v5 + 2);
    if ( *v5 )
      (**(void (__fastcall ***)(_QWORD, __int64))*v5)(*v5, 1);
    operator delete(v5, (const struct std::nothrow_t *)0x38);
  }
  v6 = *((_QWORD *)this + 10);
  if ( v6 )
  {
    LOBYTE(v4) = v6 != (_QWORD)this + 24;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 32LL))(v6, v4);
    *((_QWORD *)this + 10) = 0;
  }
  *((_QWORD *)this + 1) = &CommonUtil::CRefObject::`vftable';
  *(_QWORD *)this = &I1dsListenerEvents::`vftable';
}

```

## disassembly

```asm
0x1400aa6f4  mov     [rsp+arg_0], rbx
0x1400aa6f9  push    rdi
0x1400aa6fa  sub     rsp, 20h
0x1400aa6fe  mov     rbx, rcx
0x1400aa701  add     rcx, 1C0h
0x1400aa708  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1400aa70d  lea     rcx, [rbx+198h]
0x1400aa714  call    ?_Tidy@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEB_WV?$AutoRefWrapper@VCSimpleMapItem@CCmdOptionsLookupMap@CommonUtil@@@CommonUtil@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAXXZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wchar_t const * const,CommonUtil::AutoRefWrapper<CommonUtil::CCmdOptionsLookupMap::CSimpleMapItem>>>>>>>::_Tidy(void)
0x1400aa719  lea     rcx, [rbx+188h]
0x1400aa720  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unordered_set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unordered_set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ
0x1400aa725  lea     rcx, [rbx+168h]
0x1400aa72c  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1400aa731  lea     rcx, [rbx+150h]
0x1400aa738  call    ?_Tidy@?$vector@UM365a@CsProtocol@@V?$allocator@UM365a@CsProtocol@@@std@@@std@@AEAAXXZ; std::vector<CsProtocol::M365a>::_Tidy(void)
0x1400aa73d  mov     rdx, [rbx+140h]; Timer
0x1400aa744  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400aa748  test    rdx, rdx
0x1400aa74b  jz      short loc_1400AA758
0x1400aa74d  mov     r8, rdi; CompletionEvent
0x1400aa750  xor     ecx, ecx; TimerQueue
0x1400aa752  call    cs:__imp_DeleteTimerQueueTimer
0x1400aa758  mov     rdx, [rbx+138h]; Timer
0x1400aa75f  test    rdx, rdx
0x1400aa762  jz      short loc_1400AA76F
0x1400aa764  mov     r8, rdi; CompletionEvent
0x1400aa767  xor     ecx, ecx; TimerQueue
0x1400aa769  call    cs:__imp_DeleteTimerQueueTimer
0x1400aa76f  lea     rcx, [rbx+60h]
0x1400aa773  call    ??1?$_Optional_destruct_base@V?$variant@Ump_common_raw_metric@details@MpWatchDog@@Ump_common_agg_metric@23@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::variant<MpWatchDog::details::mp_common_raw_metric,MpWatchDog::details::mp_common_agg_metric>,0>::~_Optional_destruct_base<std::variant<MpWatchDog::details::mp_common_raw_metric,MpWatchDog::details::mp_common_agg_metric>,0>(void)
0x1400aa778  mov     rdi, [rbx+58h]
0x1400aa77c  test    rdi, rdi
0x1400aa77f  jz      short loc_1400AA7B0
0x1400aa781  lea     rcx, [rdi+10h]
0x1400aa785  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400aa78a  mov     rcx, [rdi]
0x1400aa78d  test    rcx, rcx
0x1400aa790  jz      short loc_1400AA7A3
0x1400aa792  mov     rax, [rcx]
0x1400aa795  mov     edx, 1
0x1400aa79a  mov     rax, [rax]
0x1400aa79d  call    cs:__guard_dispatch_icall_fptr
0x1400aa7a3  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x1400aa7a8  mov     rcx, rdi; void *
0x1400aa7ab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400aa7b0  lea     rdi, [rbx+18h]
0x1400aa7b4  mov     rcx, [rdi+38h]
0x1400aa7b8  test    rcx, rcx
0x1400aa7bb  jz      short loc_1400AA7D8
0x1400aa7bd  mov     rax, [rcx]
0x1400aa7c0  cmp     rcx, rdi
0x1400aa7c3  setnz   dl
0x1400aa7c6  mov     rax, [rax+20h]
0x1400aa7ca  call    cs:__guard_dispatch_icall_fptr
0x1400aa7d0  mov     qword ptr [rdi+38h], 0
0x1400aa7d8  lea     rax, ??_7CRefObject@CommonUtil@@6B@; const CommonUtil::CRefObject::`vftable'
0x1400aa7df  mov     [rbx+8], rax
0x1400aa7e3  lea     rax, ??_7I1dsListenerEvents@@6B@; const I1dsListenerEvents::`vftable'
0x1400aa7ea  mov     [rbx], rax
0x1400aa7ed  mov     rbx, [rsp+28h+arg_0]
0x1400aa7f2  add     rsp, 20h
0x1400aa7f6  pop     rdi
0x1400aa7f7  retn
```
