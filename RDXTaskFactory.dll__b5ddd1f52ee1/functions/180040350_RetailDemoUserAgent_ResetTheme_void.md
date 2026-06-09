# RetailDemoUserAgent::ResetTheme(void)

- ea: `0x180040350`
- end: `0x1800403a2`
- name: `?ResetTheme@RetailDemoUserAgent@@UEAAJXZ`
- size: `82`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180034b74`
- `0x180034ddc`
- `0x180040350`
- `0x180042190`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040386`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040386`

## pseudocode

```c
__int64 __fastcall RetailDemoUserAgent::ResetTheme(RetailDemoUserAgent *this)
{
  DWORD CurrentThreadId; // eax
  __int64 v2; // rdx
  __int64 v3; // rcx
  DWORD v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF
  unsigned int *v9; // [rsp+40h] [rbp+18h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_OS_Theme_Setup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RDX_OS_Theme_Setup>::GetImpl'::`2'::impl) )
  {
    CurrentThreadId = GetCurrentThreadId();
    return Windows::Internal::ComTaskPool::QueueTask__lambda_77cf094aea33988ccb229d7365e0e1b2___(
             v3,
             v2,
             CurrentThreadId);
  }
  else
  {
    v8 = 0;
    v9 = &v8;
    v5 = GetCurrentThreadId();
    Windows::Internal::ComTaskPool::QueueTask__lambda_d9eb9fdc385074818c94944c7f345152___(v7, v6, v5, &v9);
    return v8;
  }
}

```

## disassembly

```asm
0x180040350  sub     rsp, 28h
0x180040354  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_OS_Theme_Setup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_OS_Theme_Setup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_OS_Theme_Setup> `wil::Feature<__WilFeatureTraits_Feature_RDX_OS_Theme_Setup>::GetImpl(void)'::`2'::impl
0x18004035b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_OS_Theme_Setup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_OS_Theme_Setup>::__private_IsEnabled(void)
0x180040360  test    al, al
0x180040362  jz      short loc_180040374
0x180040364  call    cs:__imp_GetCurrentThreadId
0x18004036a  mov     r8d, eax
0x18004036d  call    Windows__Internal__ComTaskPool__QueueTask__lambda_77cf094aea33988ccb229d7365e0e1b2___
0x180040372  jmp     short loc_18004039D
0x180040374  lea     rax, [rsp+28h+arg_8]
0x180040379  mov     [rsp+28h+arg_8], 0
0x180040381  mov     [rsp+28h+arg_10], rax
0x180040386  call    cs:__imp_GetCurrentThreadId
0x18004038c  mov     r8d, eax
0x18004038f  lea     r9, [rsp+28h+arg_10]
0x180040394  call    Windows__Internal__ComTaskPool__QueueTask__lambda_d9eb9fdc385074818c94944c7f345152___
0x180040399  mov     eax, [rsp+28h+arg_8]
0x18004039d  add     rsp, 28h
0x1800403a1  retn
```
