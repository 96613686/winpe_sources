# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults<CspLoader::unique_csploader_out_params<uchar>,`CspLoader::GetProperty(_GUID const *,ushort const *,WCM_CSP_PROPERTY,ulong,uchar *,ulong *,uchar * *,ulong)'::`12'::_lambda_1_>(`CspLoader::GetProperty(_GUID const *,ushort const *,WCM_CSP_PROPERTY,ulong,uchar *,ulong *,uchar * *,ulong)'::`12'::_lambda_1_ &&)

- ea: `0x180010e28`
- end: `0x180010fe6`
- name: `??$SubmitWorkWithResults@U?$unique_csploader_out_params@E@CspLoader@@V_lambda_1_@?M@??GetProperty@2@QEAAKPEBU_GUID@@PEBGW4WCM_CSP_PROPERTY@@KPEAEPEAKPEAPEAEK@Z@@ThreadPoolWorkQueue@WcmCommon@@QEAA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@E@CspLoader@@@WcmCommon@@@std@@$$QEAV_lambda_1_@?M@??GetProperty@CspLoader@@QEAAKPEBU_GUID@@PEBGW4WCM_CSP_PROPERTY@@KPEAEPEAKPEAPEAEK@Z@@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180010900`

## callees

- `0x180010560`
- `0x180010e28`
- `0x180011e14`
- `0x180066548`
- `0x18006de30`
- `0x18008534c`
- `0x180098260`
- `0x1800a1320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010e62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010e62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010f40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010fb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010f40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010fb9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180010f55`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180010f55`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Z::SubmitWorkWithResults<CspLoader::unique_csploader_out_params<unsigned char>,`CspLoader::GetProperty'::`12'::_lambda_1_,AKPEBU_GUID * const,unsigned short const *,enum WCM_CSP_PROPERTY,unsigned long,unsigned char *,unsigned long *,unsigned char * *,unsigned long>(
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
    v7 = (char *)operator new(0x88u);
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<_WCM_CSP_PROFILE_LIST>>>::`vftable';
    v8 = v7 + 16;
    ____0V_lambda_1___M___GetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEAEPEAKPEAPEAEK_Z____ThreadPoolWaitableResult_U__unique_csploader_out_params_E_CspLoader___WcmCommon__QEAA___QEAV_lambda_1___M___GetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEAEPEAKPEAPEAEK_Z__Z(
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
0x180010e28  mov     [rsp-8+arg_18], rbx
0x180010e2d  push    rbp
0x180010e2e  push    rsi
0x180010e2f  push    rdi
0x180010e30  push    r12
0x180010e32  push    r13
0x180010e34  push    r14
0x180010e36  push    r15
0x180010e38  lea     rbp, [rsp-27h]
0x180010e3d  sub     rsp, 0A0h
0x180010e44  mov     rdi, r8
0x180010e47  mov     rbx, rdx
0x180010e4a  mov     r14, rcx
0x180010e4d  mov     [rbp+57h+var_B0], rdx
0x180010e51  xor     esi, esi
0x180010e53  xorps   xmm1, xmm1
0x180010e56  movdqu  [rbp+57h+var_A8], xmm1
0x180010e5b  lea     r15, [rcx+8]
0x180010e5f  mov     rcx, r15; lpCriticalSection
0x180010e62  call    cs:__imp_EnterCriticalSection
0x180010e68  mov     [rbp+57h+var_90], r15
0x180010e6c  cmp     [r14+110h], sil
0x180010e73  jnz     loc_180010FAA
0x180010e79  mov     ecx, 88h; Size
0x180010e7e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010e83  mov     rsi, rax
0x180010e86  mov     [rbp+57h+var_B0], rax
0x180010e8a  xorps   xmm0, xmm0
0x180010e8d  movups  xmmword ptr [rax], xmm0
0x180010e90  mov     dword ptr [rax+8], 1
0x180010e97  mov     dword ptr [rax+0Ch], 1
0x180010e9e  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@U_WCM_CSP_PROFILE_LIST@@@CspLoader@@@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<_WCM_CSP_PROFILE_LIST>>>::`vftable'
0x180010ea5  mov     [rsi], rax
0x180010ea8  lea     r12, [rsi+10h]
0x180010eac  mov     rdx, rdi
0x180010eaf  mov     rcx, r12
0x180010eb2  call    ??$?0V_lambda_1_@?M@??GetProperty@CspLoader@@QEAAKPEBU_GUID@@PEBGW4WCM_CSP_PROPERTY@@KPEAEPEAKPEAPEAEK@Z@@?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@E@CspLoader@@@WcmCommon@@QEAA@$$QEAV_lambda_1_@?M@??GetProperty@CspLoader@@QEAAKPEBU_GUID@@PEBGW4WCM_CSP_PROPERTY@@KPEAEPEAKPEAPEAEK@Z@@Z; WcmCommon::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<uchar>>::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<uchar>>(`CspLoader::GetProperty(_GUID const *,ushort const *,WCM_CSP_PROPERTY,ulong,uchar *,ulong *,uchar * *,ulong)'::`12'::_lambda_1_ &&)
0x180010eb7  nop
0x180010eb8  mov     qword ptr [rbp+57h+var_A8], r12
0x180010ebc  mov     qword ptr [rbp+57h+var_A8+8], rsi
0x180010ec0  cmp     dword ptr [r14], 1
0x180010ec4  jnz     loc_180010F80
0x180010eca  lea     rdi, [r14+0C0h]
0x180010ed1  lock inc dword ptr [rsi+8]
0x180010ed5  mov     [rbp+57h+var_88], r12
0x180010ed9  mov     [rbp+57h+var_80], rsi
0x180010edd  mov     rax, [rdi+20h]
0x180010ee1  inc     rax
0x180010ee4  cmp     [rdi+10h], rax
0x180010ee8  jbe     loc_180010FC1
0x180010eee  mov     rdx, [rdi+10h]
0x180010ef2  dec     rdx
0x180010ef5  and     [rdi+18h], rdx
0x180010ef9  mov     rax, [rdi+20h]
0x180010efd  add     rax, [rdi+18h]
0x180010f01  mov     [rbp+57h+var_B0], rax
0x180010f05  mov     r13, rax
0x180010f08  and     r13, rdx
0x180010f0b  mov     rax, [rdi+8]
0x180010f0f  cmp     qword ptr [rax+r13*8], 0
0x180010f14  jz      loc_180010FCE
0x180010f1a  mov     rcx, [rdi+10h]
0x180010f1e  dec     rcx
0x180010f21  and     rcx, [rbp+57h+var_B0]
0x180010f25  mov     rax, [rdi+8]
0x180010f29  mov     rcx, [rax+rcx*8]
0x180010f2d  mov     [rcx], r12
0x180010f30  mov     [rcx+8], rsi
0x180010f34  inc     qword ptr [rdi+20h]
0x180010f38  test    r15, r15
0x180010f3b  jz      short loc_180010F46
0x180010f3d  mov     rcx, r15; lpCriticalSection
0x180010f40  call    cs:__imp_LeaveCriticalSection
0x180010f46  lock inc qword ptr [r14+88h]
0x180010f4e  mov     rcx, [r14+80h]; pwk
0x180010f55  call    cs:__imp_SubmitThreadpoolWork
0x180010f5b  mov     [rbx], r12
0x180010f5e  mov     [rbx+8], rsi
0x180010f62  mov     rax, rbx
0x180010f65  mov     rbx, [rsp+0D0h+arg_18]
0x180010f6d  add     rsp, 0A0h
0x180010f74  pop     r15
0x180010f76  pop     r14
0x180010f78  pop     r13
0x180010f7a  pop     r12
0x180010f7c  pop     rdi
0x180010f7d  pop     rsi
0x180010f7e  pop     rbp
0x180010f7f  retn
0x180010f80  lea     rdx, [rbp+57h+var_A8]
0x180010f84  lea     rcx, [rbp+57h+var_78]
0x180010f88  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x180010f8d  nop
0x180010f8e  lea     rdx, [rbp+57h+var_78]
0x180010f92  lea     rcx, [r14+0E8h]
0x180010f99  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x180010f9e  nop
0x180010f9f  lea     rcx, [rbp+57h+var_78]
0x180010fa3  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x180010fa8  jmp     short loc_180010F38
0x180010faa  mov     [rbx], rsi
0x180010fad  mov     [rbx+8], rsi
0x180010fb1  test    r15, r15
0x180010fb4  jz      short loc_180010F62
0x180010fb6  mov     rcx, r15; lpCriticalSection
0x180010fb9  call    cs:__imp_LeaveCriticalSection
0x180010fbf  jmp     short loc_180010F62
0x180010fc1  mov     rcx, rdi
0x180010fc4  call    ?_Growmap@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Growmap(unsigned __int64)
0x180010fc9  jmp     loc_180010EEE
0x180010fce  mov     ecx, 10h
0x180010fd3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180010fd8  mov     rcx, [rdi+8]
0x180010fdc  mov     [rcx+r13*8], rax
0x180010fe0  jmp     loc_180010F1A
```
