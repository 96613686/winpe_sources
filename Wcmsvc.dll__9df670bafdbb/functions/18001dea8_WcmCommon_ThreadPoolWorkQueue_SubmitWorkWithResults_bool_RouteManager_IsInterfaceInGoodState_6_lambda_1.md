# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::IsInterfaceInGoodState_::_6_::_lambda_1___

- ea: `0x18001dea8`
- end: `0x18001e010`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::IsInterfaceInGoodState_::_6_::_lambda_1___`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001efec`

## callees

- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x18001dea8`
- `0x18001e018`
- `0x18006de30`
- `0x18008534c`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dee2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dee2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dfd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dfd2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001df8f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001df8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RouteManager::IsInterfaceInGoodState_::_6_::_lambda_1___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  char *v7; // r14
  char *v9; // [rsp+20h] [rbp-49h] BYREF
  std::_Ref_count_base *v10; // [rsp+28h] [rbp-41h]
  __int128 v11; // [rsp+30h] [rbp-39h] BYREF
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+48h] [rbp-21h]
  _BYTE v13[80]; // [rsp+50h] [rbp-19h] BYREF

  v11 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v12 = v6;
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
    v9 = v7;
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable';
    WcmCommon::ThreadPoolWaitableResult_bool_::ThreadPoolWaitableResult_bool___RouteManager::IsInterfaceInGoodState_::_6_::_lambda_1___(
      v7 + 16,
      a3);
    *(_QWORD *)&v11 = v7 + 16;
    *((_QWORD *)&v11 + 1) = v7;
    if ( *(_DWORD *)a1 == 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
      v9 = v7 + 16;
      v10 = (std::_Ref_count_base *)v7;
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(a1 + 192, &v9);
      if ( v10 )
        std::_Ref_count_base::_Decref(v10);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
        v13,
        &v11);
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(
        a1 + 232,
        v13);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v13);
    }
    if ( v6 )
      LeaveCriticalSection(v6);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *a2 = v7 + 16;
    a2[1] = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x18001dea8  mov     [rsp-8+arg_10], rbx
0x18001dead  mov     [rsp-8+arg_18], rsi
0x18001deb2  push    rbp
0x18001deb3  push    rdi
0x18001deb4  push    r12
0x18001deb6  push    r14
0x18001deb8  push    r15
0x18001deba  lea     rbp, [rsp-37h]
0x18001debf  sub     rsp, 0A0h
0x18001dec6  mov     r12, r8
0x18001dec9  mov     rbx, rdx
0x18001decc  mov     rsi, rcx
0x18001decf  mov     [rbp+57h+var_78], rdx
0x18001ded3  xorps   xmm1, xmm1
0x18001ded6  movdqu  [rbp+57h+var_90], xmm1
0x18001dedb  lea     rdi, [rcx+8]
0x18001dedf  mov     rcx, rdi; lpCriticalSection
0x18001dee2  call    cs:__imp_EnterCriticalSection
0x18001dee8  mov     [rbp+57h+var_78], rdi
0x18001deec  cmp     byte ptr [rsi+110h], 0
0x18001def3  jnz     loc_18001DFBB
0x18001def9  mov     ecx, 78h ; 'x'; Size
0x18001defe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001df03  mov     r14, rax
0x18001df06  mov     [rbp+57h+var_A0], rax
0x18001df0a  xorps   xmm0, xmm0
0x18001df0d  movups  xmmword ptr [rax], xmm0
0x18001df10  mov     dword ptr [rax+8], 1
0x18001df17  mov     dword ptr [rax+0Ch], 1
0x18001df1e  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable'
0x18001df25  mov     [r14], rax
0x18001df28  lea     r15, [r14+10h]
0x18001df2c  mov     rdx, r12
0x18001df2f  mov     rcx, r15
0x18001df32  call    WcmCommon__ThreadPoolWaitableResult_bool___ThreadPoolWaitableResult_bool___RouteManager__IsInterfaceInGoodState____6____lambda_1___
0x18001df37  nop
0x18001df38  mov     qword ptr [rbp+57h+var_90], r15
0x18001df3c  mov     qword ptr [rbp+57h+var_90+8], r14
0x18001df40  cmp     dword ptr [rsi], 1
0x18001df43  jz      loc_18001DFDA
0x18001df49  lea     rdx, [rbp+57h+var_90]
0x18001df4d  lea     rcx, [rbp+57h+var_70]
0x18001df51  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x18001df56  nop
0x18001df57  lea     rdx, [rbp+57h+var_70]
0x18001df5b  lea     rcx, [rsi+0E8h]
0x18001df62  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18001df67  nop
0x18001df68  lea     rcx, [rbp+57h+var_70]
0x18001df6c  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x18001df71  nop
0x18001df72  test    rdi, rdi
0x18001df75  jz      short loc_18001DF80
0x18001df77  mov     rcx, rdi; lpCriticalSection
0x18001df7a  call    cs:__imp_LeaveCriticalSection
0x18001df80  lock inc qword ptr [rsi+88h]
0x18001df88  mov     rcx, [rsi+80h]; pwk
0x18001df8f  call    cs:__imp_SubmitThreadpoolWork
0x18001df95  mov     [rbx], r15
0x18001df98  mov     [rbx+8], r14
0x18001df9c  mov     rax, rbx
0x18001df9f  lea     r11, [rsp+0C0h+var_20]
0x18001dfa7  mov     rbx, [r11+40h]
0x18001dfab  mov     rsi, [r11+48h]
0x18001dfaf  mov     rsp, r11
0x18001dfb2  pop     r15
0x18001dfb4  pop     r14
0x18001dfb6  pop     r12
0x18001dfb8  pop     rdi
0x18001dfb9  pop     rbp
0x18001dfba  retn
0x18001dfbb  mov     qword ptr [rbx], 0
0x18001dfc2  mov     qword ptr [rbx+8], 0
0x18001dfca  test    rdi, rdi
0x18001dfcd  jz      short loc_18001DF9C
0x18001dfcf  mov     rcx, rdi; lpCriticalSection
0x18001dfd2  call    cs:__imp_LeaveCriticalSection
0x18001dfd8  jmp     short loc_18001DF9C
0x18001dfda  lea     rcx, [rsi+0C0h]
0x18001dfe1  lock inc dword ptr [r14+8]
0x18001dfe6  mov     [rbp+57h+var_A0], r15
0x18001dfea  mov     [rbp+57h+var_98], r14
0x18001dfee  lea     rdx, [rbp+57h+var_A0]
0x18001dff2  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18001dff7  nop
0x18001dff8  mov     rcx, [rbp+57h+var_98]; this
0x18001dffc  test    rcx, rcx
0x18001dfff  jz      loc_18001DF72
0x18001e005  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e00a  jmp     loc_18001DF72
```
