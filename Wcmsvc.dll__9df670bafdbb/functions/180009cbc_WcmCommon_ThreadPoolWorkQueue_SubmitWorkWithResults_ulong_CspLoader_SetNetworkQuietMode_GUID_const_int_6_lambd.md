# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults<ulong,`CspLoader::SetNetworkQuietMode(_GUID const *,int)'::`6'::_lambda_1_>(`CspLoader::SetNetworkQuietMode(_GUID const *,int)'::`6'::_lambda_1_ &&)

- ea: `0x180009cbc`
- end: `0x180009e78`
- name: `??$SubmitWorkWithResults@KV_lambda_1_@?5??SetNetworkQuietMode@CspLoader@@QEAAKPEBU_GUID@@H@Z@@ThreadPoolWorkQueue@WcmCommon@@QEAA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@K@WcmCommon@@@std@@$$QEAV_lambda_1_@?5??SetNetworkQuietMode@CspLoader@@QEAAKPEBU_GUID@@H@Z@@Z`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180009b7c`

## callees

- `0x180009cbc`
- `0x180009e80`
- `0x180010560`
- `0x180066548`
- `0x18006de30`
- `0x18008534c`
- `0x180098260`
- `0x1800a1320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009cf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009cf6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009dd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009dd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e4b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180009de7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180009de7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Z::SubmitWorkWithResults<unsigned long,`CspLoader::SetNetworkQuietMode'::`6'::_lambda_1_,AKPEBU_GUID * const,int>(
        __int64 a1,
        _QWORD *a2,
        _OWORD *a3)
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
    ____0V_lambda_1___5__SetNetworkQuietMode_CspLoader__QEAAKPEBU_GUID__H_Z____ThreadPoolWaitableResult_K_WcmCommon__QEAA___QEAV_lambda_1___5__SetNetworkQuietMode_CspLoader__QEAAKPEBU_GUID__H_Z__Z(
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
0x180009cbc  mov     [rsp-8+arg_10], rbx
0x180009cc1  push    rbp
0x180009cc2  push    rsi
0x180009cc3  push    rdi
0x180009cc4  push    r12
0x180009cc6  push    r13
0x180009cc8  push    r14
0x180009cca  push    r15
0x180009ccc  lea     rbp, [rsp-27h]
0x180009cd1  sub     rsp, 0A0h
0x180009cd8  mov     rdi, r8
0x180009cdb  mov     rbx, rdx
0x180009cde  mov     r14, rcx
0x180009ce1  mov     [rbp+57h+var_B0], rdx
0x180009ce5  xor     esi, esi
0x180009ce7  xorps   xmm1, xmm1
0x180009cea  movdqu  [rbp+57h+var_A8], xmm1
0x180009cef  lea     r15, [rcx+8]
0x180009cf3  mov     rcx, r15; lpCriticalSection
0x180009cf6  call    cs:__imp_EnterCriticalSection
0x180009cfc  mov     [rbp+57h+var_90], r15
0x180009d00  cmp     [r14+110h], sil
0x180009d07  jnz     loc_180009E3C
0x180009d0d  lea     ecx, [rsi+78h]; Size
0x180009d10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009d15  mov     rsi, rax
0x180009d18  mov     [rbp+57h+var_B0], rax
0x180009d1c  xorps   xmm0, xmm0
0x180009d1f  movups  xmmword ptr [rax], xmm0
0x180009d22  mov     dword ptr [rax+8], 1
0x180009d29  mov     dword ptr [rax+0Ch], 1
0x180009d30  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable'
0x180009d37  mov     [rsi], rax
0x180009d3a  lea     r12, [rsi+10h]
0x180009d3e  mov     rdx, rdi
0x180009d41  mov     rcx, r12
0x180009d44  call    ??$?0V_lambda_1_@?5??SetNetworkQuietMode@CspLoader@@QEAAKPEBU_GUID@@H@Z@@?$ThreadPoolWaitableResult@K@WcmCommon@@QEAA@$$QEAV_lambda_1_@?5??SetNetworkQuietMode@CspLoader@@QEAAKPEBU_GUID@@H@Z@@Z; WcmCommon::ThreadPoolWaitableResult<ulong>::ThreadPoolWaitableResult<ulong>(`CspLoader::SetNetworkQuietMode(_GUID const *,int)'::`6'::_lambda_1_ &&)
0x180009d49  nop
0x180009d4a  mov     qword ptr [rbp+57h+var_A8], r12
0x180009d4e  mov     qword ptr [rbp+57h+var_A8+8], rsi
0x180009d52  cmp     dword ptr [r14], 1
0x180009d56  jnz     loc_180009E12
0x180009d5c  lea     rdi, [r14+0C0h]
0x180009d63  lock inc dword ptr [rsi+8]
0x180009d67  mov     [rbp+57h+var_88], r12
0x180009d6b  mov     [rbp+57h+var_80], rsi
0x180009d6f  mov     rax, [rdi+20h]
0x180009d73  inc     rax
0x180009d76  cmp     [rdi+10h], rax
0x180009d7a  jbe     loc_180009E53
0x180009d80  mov     rdx, [rdi+10h]
0x180009d84  dec     rdx
0x180009d87  and     [rdi+18h], rdx
0x180009d8b  mov     rax, [rdi+20h]
0x180009d8f  add     rax, [rdi+18h]
0x180009d93  mov     [rbp+57h+var_B0], rax
0x180009d97  mov     r13, rax
0x180009d9a  and     r13, rdx
0x180009d9d  mov     rax, [rdi+8]
0x180009da1  cmp     qword ptr [rax+r13*8], 0
0x180009da6  jz      loc_180009E60
0x180009dac  mov     rcx, [rdi+10h]
0x180009db0  dec     rcx
0x180009db3  and     rcx, [rbp+57h+var_B0]
0x180009db7  mov     rax, [rdi+8]
0x180009dbb  mov     rcx, [rax+rcx*8]
0x180009dbf  mov     [rcx], r12
0x180009dc2  mov     [rcx+8], rsi
0x180009dc6  inc     qword ptr [rdi+20h]
0x180009dca  test    r15, r15
0x180009dcd  jz      short loc_180009DD8
0x180009dcf  mov     rcx, r15; lpCriticalSection
0x180009dd2  call    cs:__imp_LeaveCriticalSection
0x180009dd8  lock inc qword ptr [r14+88h]
0x180009de0  mov     rcx, [r14+80h]; pwk
0x180009de7  call    cs:__imp_SubmitThreadpoolWork
0x180009ded  mov     [rbx], r12
0x180009df0  mov     [rbx+8], rsi
0x180009df4  mov     rax, rbx
0x180009df7  mov     rbx, [rsp+0D0h+arg_10]
0x180009dff  add     rsp, 0A0h
0x180009e06  pop     r15
0x180009e08  pop     r14
0x180009e0a  pop     r13
0x180009e0c  pop     r12
0x180009e0e  pop     rdi
0x180009e0f  pop     rsi
0x180009e10  pop     rbp
0x180009e11  retn
0x180009e12  lea     rdx, [rbp+57h+var_A8]
0x180009e16  lea     rcx, [rbp+57h+var_78]
0x180009e1a  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x180009e1f  nop
0x180009e20  lea     rdx, [rbp+57h+var_78]
0x180009e24  lea     rcx, [r14+0E8h]
0x180009e2b  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x180009e30  nop
0x180009e31  lea     rcx, [rbp+57h+var_78]
0x180009e35  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x180009e3a  jmp     short loc_180009DCA
0x180009e3c  mov     [rbx], rsi
0x180009e3f  mov     [rbx+8], rsi
0x180009e43  test    r15, r15
0x180009e46  jz      short loc_180009DF4
0x180009e48  mov     rcx, r15; lpCriticalSection
0x180009e4b  call    cs:__imp_LeaveCriticalSection
0x180009e51  jmp     short loc_180009DF4
0x180009e53  mov     rcx, rdi
0x180009e56  call    ?_Growmap@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Growmap(unsigned __int64)
0x180009e5b  jmp     loc_180009D80
0x180009e60  mov     ecx, 10h
0x180009e65  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009e6a  mov     rcx, [rdi+8]
0x180009e6e  mov     [rcx+r13*8], rax
0x180009e72  jmp     loc_180009DAC
```
