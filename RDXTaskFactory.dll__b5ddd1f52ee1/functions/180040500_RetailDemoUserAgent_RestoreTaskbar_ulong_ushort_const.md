# RetailDemoUserAgent::RestoreTaskbar(ulong,ushort const * *)

- ea: `0x180040500`
- end: `0x18004068c`
- name: `?RestoreTaskbar@RetailDemoUserAgent@@UEAAJKPEAPEBG@Z`
- size: `396`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, unsigned int, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000aa7c`
- `0x180012b30`
- `0x180018840`
- `0x180018b58`
- `0x18001ff9c`
- `0x180034488`
- `0x18003677c`
- `0x18003692c`
- `0x1800369dc`
- `0x18003982c`
- `0x18003fd08`
- `0x180040500`
- `0x180041148`
- `0x180042118`
- `0x180042dc0`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800405d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800405d2`
- `SHCORE!SHTaskPoolQueueTask` at `0x180040622`
- `SHCORE!SHTaskPoolQueueTask` at `0x180040622`

## string_xrefs

- `0x180040567`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18004064a`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RetailDemoUserAgent::RestoreTaskbar(RetailDemoUserAgent *this, int a2, const unsigned __int16 **a3)
{
  RetailDemoUserAgent *v6; // rcx
  int updated; // eax
  int v8; // edi
  __int64 v9; // rbx
  RetailDemoUserAgent *v10; // rsi
  DWORD CurrentThreadId; // ebx
  __int64 *v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // ebx
  int v18; // [rsp+20h] [rbp-50h]
  RetailDemoUserAgent *v19; // [rsp+30h] [rbp-40h] BYREF
  int v20; // [rsp+38h] [rbp-38h]
  const unsigned __int16 **v21; // [rsp+40h] [rbp-30h]
  unsigned int *v22; // [rsp+48h] [rbp-28h]
  __int64 v23; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  __int64 v25; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v26; // [rsp+A8h] [rbp+38h] BYREF

  v26 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_DismissStartOnIdle>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RDX_DismissStartOnIdle>::GetImpl'::`2'::impl) )
  {
    v25 = 0;
    tip2::tip_test<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>::start_and_watch_errors(
      &v25,
      &v19);
    wil::com_ptr_t<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>,wil::err_returncode_policy>(&v25);
    updated = RetailDemoUserAgent::SuppressWindowsUpdateNotifications(v6);
    v8 = updated;
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6BD,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)updated,
        v18);
    v9 = v23;
    v25 = v23;
    if ( v23 )
      _InterlockedIncrement((volatile signed __int32 *)(v23 + 280));
    tip2::details::shared_data<1,0,0>::begin_update(v9 + 8);
    *(_DWORD *)(v9 + 272) = v8;
    tip2::test_data_control<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>(&v25);
    tip2::details::shared_data<1,0,0>::complete_without_lock(v23 + 8);
    tip2::test_watcher<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>(&v19);
  }
  v10 = (RetailDemoUserAgent *)((char *)this - 72);
  v19 = v10;
  v20 = a2;
  v21 = a3;
  v22 = &v26;
  CurrentThreadId = GetCurrentThreadId();
  v12 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_51d4d9cb9f6458094cf331f7e0905cb6_____lambda_51d4d9cb9f6458094cf331f7e0905cb6___(
                     &v25,
                     &v19);
  v13 = *v12;
  *v12 = 0;
  v14 = v25;
  if ( v25 )
  {
    v25 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v14);
  }
  v16 = SHTaskPoolQueueTask(1, 32, CurrentThreadId);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v16 >= 0 )
  {
    LOBYTE(v15) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_VirtualDesktopCleanup>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RDX_VirtualDesktopCleanup>::GetImpl'::`2'::impl,
      v15);
    RetailDemoUserAgent::CleanupVirtualDesktops(v10);
    return v26;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6EF,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v16,
      v13);
    return (unsigned int)v16;
  }
}

```

## disassembly

```asm
0x180040500  mov     [rsp-28h+arg_10], rbx
0x180040505  push    rbp
0x180040506  push    rsi
0x180040507  push    rdi
0x180040508  push    r14
0x18004050a  push    r15
0x18004050c  mov     rbp, rsp
0x18004050f  sub     rsp, 70h
0x180040513  mov     r14, r8
0x180040516  mov     r15d, edx
0x180040519  mov     rsi, rcx
0x18004051c  mov     [rbp+arg_8], 0
0x180040523  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_DismissStartOnIdle@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_DismissStartOnIdle@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_DismissStartOnIdle> `wil::Feature<__WilFeatureTraits_Feature_RDX_DismissStartOnIdle>::GetImpl(void)'::`2'::impl
0x18004052a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_DismissStartOnIdle@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_DismissStartOnIdle>::__private_IsEnabled(void)
0x18004052f  test    al, al
0x180040531  jz      loc_1800405BA
0x180040537  mov     [rbp+arg_0], 0
0x18004053f  lea     rdx, [rbp+var_40]
0x180040543  lea     rcx, [rbp+arg_0]
0x180040547  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>::start_and_watch_errors(void)
0x18004054c  lea     rcx, [rbp+arg_0]
0x180040550  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>,wil::err_returncode_policy>(void)
0x180040555  call    ?SuppressWindowsUpdateNotifications@RetailDemoUserAgent@@AEAAJXZ; RetailDemoUserAgent::SuppressWindowsUpdateNotifications(void)
0x18004055a  mov     edi, eax
0x18004055c  mov     rcx, [rbp+28h]; this
0x180040560  test    eax, eax
0x180040562  jns     short loc_180040578
0x180040564  mov     r9d, eax; char *
0x180040567  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18004056e  mov     edx, 6BDh; void *
0x180040573  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040578  mov     rbx, [rbp+var_8]
0x18004057c  mov     [rbp+arg_0], rbx
0x180040580  test    rbx, rbx
0x180040583  jz      short loc_18004058C
0x180040585  lock inc dword ptr [rbx+118h]
0x18004058c  lea     rcx, [rbx+8]
0x180040590  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180040595  mov     [rbx+110h], edi
0x18004059b  lea     rcx, [rbp+arg_0]
0x18004059f  call    ??1?$test_data_control@V?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>(void)
0x1800405a4  mov     rcx, [rbp+var_8]
0x1800405a8  add     rcx, 8
0x1800405ac  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x1800405b1  lea     rcx, [rbp+var_40]
0x1800405b5  call    ??1?$test_watcher@V?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>(void)
0x1800405ba  add     rsi, 0FFFFFFFFFFFFFFB8h
0x1800405be  mov     [rbp+var_40], rsi
0x1800405c2  mov     [rbp+var_38], r15d
0x1800405c6  mov     [rbp+var_30], r14
0x1800405ca  lea     rax, [rbp+arg_8]
0x1800405ce  mov     [rbp+var_28], rax
0x1800405d2  call    cs:__imp_GetCurrentThreadId
0x1800405d8  mov     ebx, eax
0x1800405da  lea     rdx, [rbp+var_40]
0x1800405de  lea     rcx, [rbp+arg_0]
0x1800405e2  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_51d4d9cb9f6458094cf331f7e0905cb6_____lambda_51d4d9cb9f6458094cf331f7e0905cb6___
0x1800405e7  mov     rdi, [rax]
0x1800405ea  mov     qword ptr [rax], 0
0x1800405f1  mov     rcx, [rbp+arg_0]
0x1800405f5  test    rcx, rcx
0x1800405f8  jz      short loc_180040607
0x1800405fa  mov     [rbp+arg_0], 0
0x180040602  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180040607  mov     [rsp+70h+var_48], 0
0x180040610  mov     qword ptr [rsp+70h+var_50], rdi; int
0x180040615  xor     r9d, r9d
0x180040618  mov     r8d, ebx
0x18004061b  lea     edx, [r9+20h]
0x18004061f  lea     ecx, [rdx-1Fh]
0x180040622  call    cs:__imp_SHTaskPoolQueueTask
0x180040628  mov     ebx, eax
0x18004062a  test    rdi, rdi
0x18004062d  jz      short loc_18004063F
0x18004062f  mov     rdx, [rdi]
0x180040632  mov     rcx, rdi
0x180040635  mov     rax, [rdx+10h]
0x180040639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004063e  nop
0x18004063f  test    ebx, ebx
0x180040641  jns     short loc_18004065F
0x180040643  mov     rcx, [rbp+28h]; this
0x180040647  mov     r9d, ebx; char *
0x18004064a  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180040651  mov     edx, 6EFh; void *
0x180040656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004065b  mov     eax, ebx
0x18004065d  jmp     short loc_180040678
0x18004065f  mov     dl, 1
0x180040661  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_VirtualDesktopCleanup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_VirtualDesktopCleanup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_VirtualDesktopCleanup> `wil::Feature<__WilFeatureTraits_Feature_RDX_VirtualDesktopCleanup>::GetImpl(void)'::`2'::impl
0x180040668  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_VirtualDesktopCleanup@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_VirtualDesktopCleanup>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004066d  mov     rcx, rsi; this
0x180040670  call    ?CleanupVirtualDesktops@RetailDemoUserAgent@@AEAAXXZ; RetailDemoUserAgent::CleanupVirtualDesktops(void)
0x180040675  mov     eax, [rbp+arg_8]
0x180040678  mov     rbx, [rsp+70h+arg_10]
0x180040680  add     rsp, 70h
0x180040684  pop     r15
0x180040686  pop     r14
0x180040688  pop     rdi
0x180040689  pop     rsi
0x18004068a  pop     rbp
0x18004068b  retn
```
