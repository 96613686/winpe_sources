# SREnsureCacheIsInitialized

- ea: `0x18000d090`
- end: `0x18000d0f0`
- name: `SREnsureCacheIsInitialized`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800075e4`
- `0x180008e8c`
- `0x180008f5c`
- `0x18000c5bc`
- `0x18000d090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0ce`

## pseudocode

```c
__int64 SREnsureCacheIsInitialized()
{
  __int64 v0; // rcx
  int v1; // ebx
  __int64 v2; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_UseRunSynchronousOnNonSTAThread>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StateRepository_UseRunSynchronousOnNonSTAThread>::GetImpl'::`2'::impl) )
  {
    v1 = Windows::Internal::ComTaskPool::RunSynchronousWorker__lambda_05cf11f314a8364087938dfc5c03809e___(v0);
    if ( v1 < 0 )
    {
      v2 = 411;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v2,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
        (const char *)(unsigned int)v1,
        v7);
      return (unsigned int)v1;
    }
  }
  else
  {
    CurrentThreadId = GetCurrentThreadId();
    v1 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_59a6c6d953810fa64ec91989aa41a75a___(
           v5,
           CurrentThreadId,
           v6);
    if ( v1 < 0 )
    {
      v2 = 420;
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000d090  push    rbx; int
0x18000d092  sub     rsp, 20h
0x18000d096  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StateRepository_UseRunSynchronousOnNonSTAThread@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_UseRunSynchronousOnNonSTAThread@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_UseRunSynchronousOnNonSTAThread> `wil::Feature<__WilFeatureTraits_Feature_StateRepository_UseRunSynchronousOnNonSTAThread>::GetImpl(void)'::`2'::impl
0x18000d09d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_UseRunSynchronousOnNonSTAThread@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_UseRunSynchronousOnNonSTAThread>::__private_IsEnabled(void)
0x18000d0a2  test    al, al
0x18000d0a4  jz      short loc_18000D0CE
0x18000d0a6  call    Windows__Internal__ComTaskPool__RunSynchronousWorker__lambda_05cf11f314a8364087938dfc5c03809e___
0x18000d0ab  mov     ebx, eax
0x18000d0ad  test    eax, eax
0x18000d0af  jns     short loc_18000D0E8
0x18000d0b1  mov     edx, 19Bh; void *
0x18000d0b6  mov     rcx, [rsp+28h]; this
0x18000d0bb  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d0c2  mov     r9d, ebx; char *
0x18000d0c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d0ca  mov     eax, ebx
0x18000d0cc  jmp     short loc_18000D0EA
0x18000d0ce  call    cs:__imp_GetCurrentThreadId
0x18000d0d4  mov     edx, eax
0x18000d0d6  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_59a6c6d953810fa64ec91989aa41a75a___
0x18000d0db  mov     ebx, eax
0x18000d0dd  test    eax, eax
0x18000d0df  jns     short loc_18000D0E8
0x18000d0e1  mov     edx, 1A4h
0x18000d0e6  jmp     short loc_18000D0B6
0x18000d0e8  xor     eax, eax
0x18000d0ea  add     rsp, 20h
0x18000d0ee  pop     rbx
0x18000d0ef  retn
```
