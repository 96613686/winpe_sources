# CRemoteTextAppIntegration::SetRemoteIntegrationStatus(int)

- ea: `0x180025460`
- end: `0x180025622`
- name: `?SetRemoteIntegrationStatus@CRemoteTextAppIntegration@@UEAAJH@Z`
- size: `450`
- prototype: `__int64 __fastcall(CRemoteTextAppIntegration *__hidden this, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006a14`
- `0x18000c454`
- `0x180010540`
- `0x180019810`
- `0x18001a0ac`
- `0x18001a138`
- `0x18001a948`
- `0x180025460`
- `0x180026128`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800255a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800255a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002557f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002557f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255fa`

## pseudocode

```c
__int64 __fastcall CRemoteTextAppIntegration::SetRemoteIntegrationStatus(__int64 **this, unsigned int a2)
{
  unsigned int v4; // r8d
  __int64 *v5; // rcx
  __int128 v6; // xmm0
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // edi
  void *v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  void *v12; // rbx
  __int128 v14; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v15[8]; // [rsp+50h] [rbp+17h] BYREF
  _BYTE v16[48]; // [rsp+58h] [rbp+1Fh] BYREF
  LPVOID pv; // [rsp+88h] [rbp+4Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]
  LPVOID v19; // [rsp+B0h] [rbp+77h] BYREF
  __int64 v20; // [rsp+B8h] [rbp+7Fh] BYREF

  v4 = *(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor;
  if ( (*(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor & 4) == 0 )
  {
    v20 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(
                       this,
                       &v20);
    v4 = v20;
  }
  LODWORD(v19) = 0;
  WORD2(v19) = 3;
  wil::details::ReportUsageToService(&unk_1800827F8, 42936120, (v4 >> 10) & 1, (v4 >> 11) & 1);
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>>((__int64)v15);
  v5 = this[14];
  v6 = *((_OWORD *)this + 56);
  *((_BYTE *)this + 912) = a2 != 0;
  v7 = *v5;
  v14 = v6;
  (*(void (__fastcall **)(__int64 *, __int128 *))(v7 + 528))(v5, &v14);
  v8 = ((__int64 (__fastcall *)(char *, _QWORD))this[2][31])((char *)this + 16, a2);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v11 = (struct _RTL_CRITICAL_SECTION *)pv;
    v19 = pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 68);
    EnterCriticalSection(v11 + 5);
    ++LODWORD(v11[6].DebugInfo);
    LODWORD(v11[1].SpinCount) |= 0xB00u;
    if ( *(_QWORD *)&v11[6].LockCount )
      tip2::details::shared_data<0,0,0>::complete_helper(&v11->LockCount, 10);
    tip2::test_data_control<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>(&v19);
    v12 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>(v12);
      CoTaskMemFree(v12);
    }
    v9 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29D,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)(unsigned int)v8,
      (int)&v19);
    v10 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>(v10);
      CoTaskMemFree(v10);
    }
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v16);
  return v9;
}

```

## disassembly

```asm
0x180025460  mov     [rsp-8+arg_0], rbx
0x180025465  mov     [rsp-8+arg_8], rdi
0x18002546a  push    rbp
0x18002546b  lea     rbp, [rsp-57h]
0x180025470  sub     rsp, 90h
0x180025477  mov     edi, edx
0x180025479  mov     rbx, rcx
0x18002547c  mov     rax, cs:Feature_TextVirtPostNiBugFix__descriptor
0x180025483  mov     r8d, [rax]
0x180025486  test    r8b, 4
0x18002548a  jnz     short loc_18002549F
0x18002548c  lea     rdx, [rbp+57h+arg_18]
0x180025490  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TextVirtPostNiBugFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(void)
0x180025495  mov     rdx, [rax]
0x180025498  mov     [rbp+57h+arg_18], rdx
0x18002549c  mov     r8d, edx
0x18002549f  mov     r9d, r8d
0x1800254a2  mov     [rsp+90h+var_60], 3
0x1800254aa  xor     eax, eax
0x1800254ac  shr     r9d, 0Bh
0x1800254b0  mov     dword ptr [rbp+57h+arg_10], eax
0x1800254b3  lea     rcx, unk_1800827F8
0x1800254ba  shr     r8d, 0Ah
0x1800254be  lea     rax, [rbp+57h+arg_10]
0x1800254c2  and     r9d, 1
0x1800254c6  mov     [rsp+90h+var_68], 1
0x1800254ce  and     r8d, 1
0x1800254d2  mov     qword ptr [rsp+90h+var_70], rax; int
0x1800254d7  mov     edx, 28F2738h
0x1800254dc  mov     word ptr [rbp+57h+arg_10+4], 3
0x1800254e2  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800254e7  lea     rcx, [rbp+57h+var_40]
0x1800254eb  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800254f0  mov     rcx, [rbx+70h]
0x1800254f4  lea     rdx, [rbp+57h+var_50]
0x1800254f8  movups  xmm0, xmmword ptr [rbx+380h]
0x1800254ff  test    edi, edi
0x180025501  setnz   r8b
0x180025505  mov     [rbx+390h], r8b
0x18002550c  mov     rax, [rcx]
0x18002550f  movdqu  [rbp+57h+var_50], xmm0
0x180025514  mov     rax, [rax+210h]
0x18002551b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025520  lea     rcx, [rbx+10h]
0x180025524  mov     edx, edi
0x180025526  mov     rax, [rcx]
0x180025529  mov     rax, [rax+0F8h]
0x180025530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025535  mov     edi, eax
0x180025537  test    eax, eax
0x180025539  jns     short loc_180025587
0x18002553b  mov     rcx, [rbp+5Fh]; this
0x18002553f  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x180025546  mov     r9d, eax; char *
0x180025549  mov     edx, 29Dh; void *
0x18002554e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025553  mov     rbx, [rbp+57h+pv]
0x180025557  test    rbx, rbx
0x18002555a  jz      loc_180025602
0x180025560  or      eax, 0FFFFFFFFh
0x180025563  lock xadd [rbx+110h], eax
0x18002556b  cmp     eax, 1
0x18002556e  jnz     loc_180025602
0x180025574  mov     rcx, rbx
0x180025577  call    ??1?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>(void)
0x18002557c  mov     rcx, rbx; pv
0x18002557f  call    cs:__imp_CoTaskMemFree
0x180025585  jmp     short loc_180025602
0x180025587  mov     rbx, [rbp+57h+pv]
0x18002558b  mov     [rbp+57h+arg_10], rbx
0x18002558f  test    rbx, rbx
0x180025592  jz      short loc_18002559B
0x180025594  lock inc dword ptr [rbx+110h]
0x18002559b  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800255a2  call    cs:__imp_EnterCriticalSection
0x1800255a8  inc     dword ptr [rbx+0F0h]
0x1800255ae  or      dword ptr [rbx+48h], 0B00h
0x1800255b5  cmp     qword ptr [rbx+0F8h], 0
0x1800255bd  jz      short loc_1800255CD
0x1800255bf  mov     edx, 0Ah
0x1800255c4  lea     rcx, [rbx+8]
0x1800255c8  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800255cd  lea     rcx, [rbp+57h+arg_10]
0x1800255d1  call    ??1?$test_data_control@V?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>>(void)
0x1800255d6  mov     rbx, [rbp+57h+pv]
0x1800255da  test    rbx, rbx
0x1800255dd  jz      short loc_180025600
0x1800255df  or      eax, 0FFFFFFFFh
0x1800255e2  lock xadd [rbx+110h], eax
0x1800255ea  cmp     eax, 1
0x1800255ed  jnz     short loc_180025600
0x1800255ef  mov     rcx, rbx
0x1800255f2  call    ??1?$merged_data@U_tip_RtaiEnabledTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>::~merged_data<_tip_RtaiEnabledTipTest,_tip_RtaiEnabledTipTest>(void)
0x1800255f7  mov     rcx, rbx; pv
0x1800255fa  call    cs:__imp_CoTaskMemFree
0x180025600  xor     edi, edi
0x180025602  lea     rcx, [rbp+57h+var_38]; this
0x180025606  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18002560b  lea     r11, [rsp+90h+var_s0]
0x180025613  mov     eax, edi
0x180025615  mov     rbx, [r11+10h]
0x180025619  mov     rdi, [r11+18h]
0x18002561d  mov     rsp, r11
0x180025620  pop     rbp
0x180025621  retn
```
