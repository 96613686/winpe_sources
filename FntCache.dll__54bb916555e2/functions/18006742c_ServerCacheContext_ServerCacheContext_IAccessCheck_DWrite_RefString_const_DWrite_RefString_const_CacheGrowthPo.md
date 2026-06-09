# ServerCacheContext::ServerCacheContext(IAccessCheck *,DWrite::RefString const &,DWrite::RefString const &,CacheGrowthPolicy const &,CacheType,IDWriteFontFileLoader *,wchar_t const *)

- ea: `0x18006742c`
- end: `0x18006752f`
- name: `??0ServerCacheContext@@QEAA@PEAVIAccessCheck@@AEBVRefString@DWrite@@1AEBUCacheGrowthPolicy@@W4CacheType@@PEAUIDWriteFontFileLoader@@PEB_W@Z`
- size: `259`
- prototype: `__int64 __fastcall(__int64, __int64, volatile signed __int32 **, volatile signed __int32 **, _QWORD *, unsigned int, __int64, wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800a4b4c`
- `0x1800b58cc`

## callees

- `0x180067538`
- `0x180067750`
- `0x180068e24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180067479`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800674b4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180067479`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800674b4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006751a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006751a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServerCacheContext::ServerCacheContext(
        __int64 a1,
        __int64 a2,
        volatile signed __int32 **a3,
        volatile signed __int32 **a4,
        _QWORD *a5,
        unsigned int a6,
        __int64 a7,
        wchar_t *a8)
{
  CacheContextImpl::CacheContextImpl(a1, a2, a3, a4, a5, a6, a8);
  *(_QWORD *)a1 = &ServerCacheContext::`vftable';
  *(_DWORD *)(a1 + 368) = a6;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 376));
  *(_QWORD *)(a1 + 448) = a1 + 416;
  *(_QWORD *)(a1 + 456) = 4;
  *(_QWORD *)(a1 + 464) = 0;
  *(_QWORD *)(a1 + 472) = 0;
  *(_OWORD *)(a1 + 416) = 0;
  *(_OWORD *)(a1 + 432) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 480));
  *(_QWORD *)(a1 + 520) = 0;
  *(_QWORD *)(a1 + 528) = 0;
  *(_BYTE *)(a1 + 536) = 0;
  *(_QWORD *)(a1 + 544) = 0;
  FontLoaderManagerBase<IDWriteFontFileLoader,3>::SetStandardLoader(a1 + 32, 0x8000000000000002uLL, a7);
  ThreadpoolWork::Initialize(
    (ThreadpoolWork *)(a1 + 520),
    (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))ServerCacheContext::CacheInitializationProc,
    *(void **)(a1 + 352));
  SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 520));
  return a1;
}

```

## disassembly

```asm
0x18006742c  mov     r11, rsp
0x18006742f  mov     [r11+10h], rbx
0x180067433  mov     [r11+8], rcx
0x180067437  push    rdi
0x180067438  sub     rsp, 40h
0x18006743c  mov     rdi, rcx
0x18006743f  mov     rax, [rsp+48h+arg_38]
0x180067447  mov     [r11-18h], rax
0x18006744b  mov     ebx, [rsp+48h+arg_28]
0x18006744f  mov     [rsp+48h+var_20], ebx
0x180067453  mov     rax, [rsp+48h+arg_20]
0x180067458  mov     [r11-28h], rax
0x18006745c  call    ??0CacheContextImpl@@IEAA@PEAVIAccessCheck@@AEBVRefString@DWrite@@1AEBUCacheGrowthPolicy@@W4CacheType@@PEB_W@Z; CacheContextImpl::CacheContextImpl(IAccessCheck *,DWrite::RefString const &,DWrite::RefString const &,CacheGrowthPolicy const &,CacheType,wchar_t const *)
0x180067461  nop
0x180067462  lea     rax, ??_7ServerCacheContext@@6B@; const ServerCacheContext::`vftable'
0x180067469  mov     [rdi], rax
0x18006746c  mov     [rdi+170h], ebx
0x180067472  lea     rcx, [rdi+178h]; lpCriticalSection
0x180067479  call    cs:__imp_InitializeCriticalSection
0x18006747f  nop
0x180067480  lea     rax, [rdi+1A0h]
0x180067487  mov     [rax+20h], rax
0x18006748b  mov     qword ptr [rax+28h], 4
0x180067493  mov     qword ptr [rax+30h], 0
0x18006749b  mov     qword ptr [rax+38h], 0
0x1800674a3  xorps   xmm0, xmm0
0x1800674a6  movups  xmmword ptr [rax], xmm0
0x1800674a9  movups  xmmword ptr [rax+10h], xmm0
0x1800674ad  lea     rcx, [rdi+1E0h]; lpCriticalSection
0x1800674b4  call    cs:__imp_InitializeCriticalSection
0x1800674ba  nop
0x1800674bb  lea     rbx, [rdi+208h]
0x1800674c2  mov     qword ptr [rbx], 0
0x1800674c9  mov     qword ptr [rdi+210h], 0
0x1800674d4  mov     byte ptr [rdi+218h], 0
0x1800674db  mov     qword ptr [rdi+220h], 0
0x1800674e6  lea     rcx, [rdi+20h]
0x1800674ea  mov     r8, [rsp+48h+arg_30]
0x1800674f2  mov     rdx, 8000000000000002h
0x1800674fc  call    ?SetStandardLoader@?$FontLoaderManagerBase@UIDWriteFontFileLoader@@$02@@IEAAX_KPEAUIDWriteFontFileLoader@@@Z; FontLoaderManagerBase<IDWriteFontFileLoader,3>::SetStandardLoader(unsigned __int64,IDWriteFontFileLoader *)
0x180067501  mov     r8, [rdi+160h]; void *
0x180067508  lea     rdx, ?CacheInitializationProc@ServerCacheContext@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x18006750f  mov     rcx, rbx; this
0x180067512  call    ?Initialize@ThreadpoolWork@@QEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; ThreadpoolWork::Initialize(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x180067517  mov     rcx, [rbx]; pwk
0x18006751a  call    cs:__imp_SubmitThreadpoolWork
0x180067520  nop
0x180067521  mov     rax, rdi
0x180067524  mov     rbx, [rsp+48h+arg_8]
0x180067529  add     rsp, 40h
0x18006752d  pop     rdi
0x18006752e  retn
```
