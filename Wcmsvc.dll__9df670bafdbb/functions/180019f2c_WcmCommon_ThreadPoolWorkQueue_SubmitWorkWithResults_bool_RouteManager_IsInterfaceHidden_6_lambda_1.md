# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::IsInterfaceHidden_::_6_::_lambda_1___

- ea: `0x180019f2c`
- end: `0x18001a0eb`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::IsInterfaceHidden_::_6_::_lambda_1___`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180019cdc`

## callees

- `0x180010560`
- `0x180019f2c`
- `0x18001a0f4`
- `0x180066548`
- `0x18006de30`
- `0x18008534c`
- `0x180098260`
- `0x1800a1320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a042`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a091`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a042`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a091`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001a057`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001a057`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::IsInterfaceHidden_::_6_::_lambda_1___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  char *v7; // rsi
  char *v8; // r12
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-59h]
  __int128 v13; // [rsp+28h] [rbp-51h] BYREF
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+40h] [rbp-39h]
  char *v15; // [rsp+48h] [rbp-31h]
  char *v16; // [rsp+50h] [rbp-29h]
  _BYTE v17[120]; // [rsp+58h] [rbp-21h] BYREF

  v13 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v14 = v6;
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( v6 )
      LeaveCriticalSection(v6);
  }
  else
  {
    v7 = (char *)operator new(0x78u);
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable';
    v8 = v7 + 16;
    WcmCommon::ThreadPoolWaitableResult_bool_::ThreadPoolWaitableResult_bool___RouteManager::IsInterfaceHidden_::_6_::_lambda_1___(
      (__int64)(v7 + 16),
      a3);
    *(_QWORD *)&v13 = v7 + 16;
    *((_QWORD *)&v13 + 1) = v7;
    if ( *(_DWORD *)a1 == 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
      v15 = v7 + 16;
      v16 = v7;
      if ( *(_QWORD *)(a1 + 208) <= (unsigned __int64)(*(_QWORD *)(a1 + 224) + 1LL) )
        std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Growmap(a1 + 192);
      v9 = *(_QWORD *)(a1 + 208) - 1LL;
      *(_QWORD *)(a1 + 216) &= v9;
      v12 = *(_QWORD *)(a1 + 216) + *(_QWORD *)(a1 + 224);
      if ( !*(_QWORD *)(*(_QWORD *)(a1 + 200) + 8 * (v9 & v12)) )
        *(_QWORD *)(*(_QWORD *)(a1 + 200) + 8 * (v9 & v12)) = std::_Allocate<16,std::_Default_allocate_traits>(16);
      v10 = *(_QWORD **)(*(_QWORD *)(a1 + 200) + 8 * (v12 & (*(_QWORD *)(a1 + 208) - 1LL)));
      *v10 = v8;
      v10[1] = v7;
      ++*(_QWORD *)(a1 + 224);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
        v17,
        &v13);
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(
        a1 + 232,
        v17);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v17);
    }
    if ( v6 )
      LeaveCriticalSection(v6);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *a2 = v8;
    a2[1] = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x180019f2c  mov     [rsp-8+arg_10], rbx
0x180019f31  push    rbp
0x180019f32  push    rsi
0x180019f33  push    rdi
0x180019f34  push    r12
0x180019f36  push    r13
0x180019f38  push    r14
0x180019f3a  push    r15
0x180019f3c  lea     rbp, [rsp-27h]
0x180019f41  sub     rsp, 0A0h
0x180019f48  mov     rdi, r8
0x180019f4b  mov     rbx, rdx
0x180019f4e  mov     r14, rcx
0x180019f51  mov     [rbp+57h+var_B0], rdx
0x180019f55  xor     esi, esi
0x180019f57  xorps   xmm1, xmm1
0x180019f5a  movdqu  [rbp+57h+var_A8], xmm1
0x180019f5f  lea     r15, [rcx+8]
0x180019f63  mov     rcx, r15; lpCriticalSection
0x180019f66  call    cs:__imp_EnterCriticalSection
0x180019f6c  mov     [rbp+57h+var_90], r15
0x180019f70  cmp     [r14+110h], sil
0x180019f77  jnz     loc_18001A082
0x180019f7d  lea     ecx, [rsi+78h]; Size
0x180019f80  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019f85  mov     rsi, rax
0x180019f88  mov     [rbp+57h+var_B0], rax
0x180019f8c  xorps   xmm0, xmm0
0x180019f8f  movups  xmmword ptr [rax], xmm0
0x180019f92  mov     dword ptr [rax+8], 1
0x180019f99  mov     dword ptr [rax+0Ch], 1
0x180019fa0  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable'
0x180019fa7  mov     [rsi], rax
0x180019faa  lea     r12, [rsi+10h]
0x180019fae  mov     rdx, rdi
0x180019fb1  mov     rcx, r12
0x180019fb4  call    WcmCommon__ThreadPoolWaitableResult_bool___ThreadPoolWaitableResult_bool___RouteManager__IsInterfaceHidden____6____lambda_1___
0x180019fb9  nop
0x180019fba  mov     qword ptr [rbp+57h+var_A8], r12
0x180019fbe  mov     qword ptr [rbp+57h+var_A8+8], rsi
0x180019fc2  cmp     dword ptr [r14], 1
0x180019fc6  jnz     loc_18001A099
0x180019fcc  lea     rdi, [r14+0C0h]
0x180019fd3  lock inc dword ptr [rsi+8]
0x180019fd7  mov     [rbp+57h+var_88], r12
0x180019fdb  mov     [rbp+57h+var_80], rsi
0x180019fdf  mov     rax, [rdi+20h]
0x180019fe3  inc     rax
0x180019fe6  cmp     [rdi+10h], rax
0x180019fea  jbe     loc_18001A0C6
0x180019ff0  mov     rdx, [rdi+10h]
0x180019ff4  dec     rdx
0x180019ff7  and     [rdi+18h], rdx
0x180019ffb  mov     rax, [rdi+20h]
0x180019fff  add     rax, [rdi+18h]
0x18001a003  mov     [rbp+57h+var_B0], rax
0x18001a007  mov     r13, rax
0x18001a00a  and     r13, rdx
0x18001a00d  mov     rax, [rdi+8]
0x18001a011  cmp     qword ptr [rax+r13*8], 0
0x18001a016  jz      loc_18001A0D3
0x18001a01c  mov     rcx, [rdi+10h]
0x18001a020  dec     rcx
0x18001a023  and     rcx, [rbp+57h+var_B0]
0x18001a027  mov     rax, [rdi+8]
0x18001a02b  mov     rcx, [rax+rcx*8]
0x18001a02f  mov     [rcx], r12
0x18001a032  mov     [rcx+8], rsi
0x18001a036  inc     qword ptr [rdi+20h]
0x18001a03a  test    r15, r15
0x18001a03d  jz      short loc_18001A048
0x18001a03f  mov     rcx, r15; lpCriticalSection
0x18001a042  call    cs:__imp_LeaveCriticalSection
0x18001a048  lock inc qword ptr [r14+88h]
0x18001a050  mov     rcx, [r14+80h]; pwk
0x18001a057  call    cs:__imp_SubmitThreadpoolWork
0x18001a05d  mov     [rbx], r12
0x18001a060  mov     [rbx+8], rsi
0x18001a064  mov     rax, rbx
0x18001a067  mov     rbx, [rsp+0D0h+arg_10]
0x18001a06f  add     rsp, 0A0h
0x18001a076  pop     r15
0x18001a078  pop     r14
0x18001a07a  pop     r13
0x18001a07c  pop     r12
0x18001a07e  pop     rdi
0x18001a07f  pop     rsi
0x18001a080  pop     rbp
0x18001a081  retn
0x18001a082  mov     [rbx], rsi
0x18001a085  mov     [rbx+8], rsi
0x18001a089  test    r15, r15
0x18001a08c  jz      short loc_18001A064
0x18001a08e  mov     rcx, r15; lpCriticalSection
0x18001a091  call    cs:__imp_LeaveCriticalSection
0x18001a097  jmp     short loc_18001A064
0x18001a099  lea     rdx, [rbp+57h+var_A8]
0x18001a09d  lea     rcx, [rbp+57h+var_78]
0x18001a0a1  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x18001a0a6  nop
0x18001a0a7  lea     rdx, [rbp+57h+var_78]
0x18001a0ab  lea     rcx, [r14+0E8h]
0x18001a0b2  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18001a0b7  nop
0x18001a0b8  lea     rcx, [rbp+57h+var_78]
0x18001a0bc  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x18001a0c1  jmp     loc_18001A03A
0x18001a0c6  mov     rcx, rdi
0x18001a0c9  call    ?_Growmap@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Growmap(unsigned __int64)
0x18001a0ce  jmp     loc_180019FF0
0x18001a0d3  mov     ecx, 10h
0x18001a0d8  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001a0dd  mov     rcx, [rdi+8]
0x18001a0e1  mov     [rcx+r13*8], rax
0x18001a0e5  jmp     loc_18001A01C
```
