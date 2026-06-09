# UninstallRecall(TaskType,DismUninstallState *)

- ea: `0x18001f1c4`
- end: `0x18001f5c1`
- name: `?UninstallRecall@@YAJW4TaskType@@PEAUDismUninstallState@@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(int, _DWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001fd50`
- `0x18002d050`

## callees

- `0x180012efc`
- `0x180013a54`
- `0x180013c80`
- `0x18001438c`
- `0x18001f1c4`
- `0x18002062c`
- `0x18002189c`
- `0x180022104`
- `0x1800248a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f2c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f2c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f267`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f29a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f387`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f431`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f473`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f267`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f29a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f387`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f431`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f473`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f2ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f2ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5aa`
- `DismApi!DismDisableFeature` at `0x18001f3eb`
- `DismApi!DismDisableFeature` at `0x18001f3eb`
- `DismApi!DismDelete` at `0x18001f571`
- `DismApi!DismDelete` at `0x18001f571`
- `DismApi!DismInitialize` at `0x18001f21a`
- `DismApi!DismInitialize` at `0x18001f21a`
- `DismApi!DismOpenSession` at `0x18001f33f`
- `DismApi!DismOpenSession` at `0x18001f33f`
- `DismApi!DismGetFeatureInfo` at `0x18001f535`
- `DismApi!DismGetFeatureInfo` at `0x18001f535`

## string_xrefs

- `0x18001f232`: `pcshell\shell\aix\shellconfigtask\lib\RecallTaskHandlerHelpers.h`
- `0x18001f352`: `pcshell\shell\aix\shellconfigtask\lib\RecallTaskHandlerHelpers.h`
- `0x18001f546`: `pcshell\shell\aix\shellconfigtask\lib\RecallTaskHandlerHelpers.h`

## pseudocode

```c
__int64 __fastcall UninstallRecall(int a1, _DWORD *a2)
{
  _QWORD *v3; // rax
  int v4; // eax
  unsigned int v5; // r14d
  __int64 v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  void *v8; // rbx
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rbx
  int FeatureInfo; // eax
  void *v19; // rbx
  int v20; // [rsp+20h] [rbp-50h]
  int v21[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v22[3]; // [rsp+48h] [rbp-28h] BYREF
  char v23; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v25; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v26; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v27; // [rsp+C0h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+C8h] [rbp+58h] BYREF

  v25 = a1;
  pv = 0;
  v3 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(&pv);
  tip2::details::shared_data<0,0,0>::start(*v3 + 8LL, v22);
  a2[1] = -1;
  *a2 = 1;
  v4 = DismInitialize(2, 0, 0);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( !v25 )
    {
      LODWORD(v27) = 2;
      wil::wnf_publish_nothrow<int>(retaddr, &v27);
    }
    v26 = 0;
    v22[0] = &v26;
    v22[1] = &v25;
    v22[2] = &pv;
    v10 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v26);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v13 = DismDisableFeature(v26, L"Recall", 0, 1, 0, 0, 0);
      v11 = v13;
      if ( v13 == -2147021886 || v13 == 3010 )
      {
        v16 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(&pv);
        v27 = v16;
        if ( v16 )
          _InterlockedAdd((volatile signed __int32 *)(v16 + 280), 1u);
        EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 200));
        ++*(_DWORD *)(v16 + 240);
        *(_DWORD *)(v16 + 272) = 6;
        tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(&v27);
        v11 = 0;
      }
      else
      {
        if ( v13 >= 0 )
        {
          v15 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(&pv);
          v27 = v15;
          if ( v15 )
            _InterlockedAdd((volatile signed __int32 *)(v15 + 280), 1u);
          EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 200));
          ++*(_DWORD *)(v15 + 240);
          *(_DWORD *)(v15 + 272) = 11;
        }
        else
        {
          v14 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(&pv);
          v27 = v14;
          if ( v14 )
            _InterlockedAdd((volatile signed __int32 *)(v14 + 280), 1u);
          EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 200));
          ++*(_DWORD *)(v14 + 240);
          *(_DWORD *)(v14 + 272) = 4;
        }
        tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(&v27);
      }
      v17 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(&pv);
      v27 = v17;
      if ( v17 )
        _InterlockedAdd((volatile signed __int32 *)(v17 + 280), 1u);
      EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 200));
      ++*(_DWORD *)(v17 + 240);
      *a2 = *(_DWORD *)(v17 + 272);
      tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(&v27);
      *(_QWORD *)v21 = 0;
      FeatureInfo = DismGetFeatureInfo(v26, L"Recall", 0, 0);
      if ( FeatureInfo < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD2,
          (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\RecallTaskHandlerHelpers.h",
          (const char *)(unsigned int)FeatureInfo,
          (int)v21);
        if ( *(_QWORD *)v21 )
          DismDelete();
      }
      v23 = 0;
      _lambda_230c3f3d33a0fee7742e817ac9e8368c_::operator()(v22);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\RecallTaskHandlerHelpers.h",
        (const char *)(unsigned int)v10,
        v20);
      v12 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(&pv);
      v27 = v12;
      if ( v12 )
        _InterlockedAdd((volatile signed __int32 *)(v12 + 280), 1u);
      EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 200));
      ++*(_DWORD *)(v12 + 240);
      *(_DWORD *)(v12 + 272) = 3;
      tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(&v27);
      *a2 = 3;
      v23 = 0;
      _lambda_230c3f3d33a0fee7742e817ac9e8368c_::operator()(v22);
    }
    v19 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>(v19);
      CoTaskMemFree(v19);
    }
    return v11;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\RecallTaskHandlerHelpers.h",
      (const char *)(unsigned int)v4,
      v20);
    v6 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(&pv);
    v27 = v6;
    if ( v6 )
      _InterlockedAdd((volatile signed __int32 *)(v6 + 280), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 200));
    ++*(_DWORD *)(v6 + 240);
    *(_DWORD *)(v6 + 272) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(&v27);
    *a2 = 2;
    v7 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      LODWORD(v7[1].SpinCount) |= 0x300u;
      if ( *(_QWORD *)&v7[6].LockCount )
        tip2::details::shared_data<0,0,0>::complete_helper(&v7->LockCount, 2);
      if ( v7 != (struct _RTL_CRITICAL_SECTION *)-200LL )
        LeaveCriticalSection(v7 + 5);
      v8 = pv;
      if ( pv )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>(v8);
          CoTaskMemFree(v8);
        }
      }
    }
    return v5;
  }
}

```

## disassembly

```asm
0x18001f1c4  mov     [rsp-38h+arg_0], ecx
0x18001f1c8  push    rbp
0x18001f1c9  push    rbx
0x18001f1ca  push    rsi
0x18001f1cb  push    rdi
0x18001f1cc  push    r12
0x18001f1ce  push    r13
0x18001f1d0  push    r14
0x18001f1d2  mov     rbp, rsp
0x18001f1d5  sub     rsp, 70h
0x18001f1d9  mov     rsi, rdx
0x18001f1dc  mov     [rbp+pv], 0
0x18001f1e4  lea     rcx, [rbp+pv]
0x18001f1e8  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(void)
0x18001f1ed  mov     rcx, [rax]
0x18001f1f0  add     rcx, 8
0x18001f1f4  lea     rdx, [rbp+var_28]
0x18001f1f8  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18001f1fd  mov     dword ptr [rsi+4], 0FFFFFFFFh
0x18001f204  mov     r12d, 1
0x18001f20a  mov     [rsi], r12d
0x18001f20d  xor     r8d, r8d
0x18001f210  xor     edx, edx
0x18001f212  lea     r13d, [r12+1]
0x18001f217  mov     ecx, r13d
0x18001f21a  call    cs:__imp_DismInitialize
0x18001f220  mov     r14d, eax
0x18001f223  mov     rcx, [rbp+38h]; this
0x18001f227  test    eax, eax
0x18001f229  jns     loc_18001F2FD
0x18001f22f  mov     r9d, eax; char *
0x18001f232  lea     r8, aPcshellShellAi_1; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18001f239  mov     edx, 83h; void *
0x18001f23e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f243  lea     rcx, [rbp+pv]
0x18001f247  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(void)
0x18001f24c  mov     rbx, [rax]
0x18001f24f  mov     [rbp+arg_10], rbx
0x18001f253  test    rbx, rbx
0x18001f256  jz      short loc_18001F260
0x18001f258  lock add [rbx+118h], r12d
0x18001f260  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001f267  call    cs:__imp_EnterCriticalSection
0x18001f26d  add     [rbx+0F0h], r12d
0x18001f274  mov     [rbx+110h], r13d
0x18001f27b  lea     rcx, [rbp+arg_10]
0x18001f27f  call    ??1?$test_data_control@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(void)
0x18001f284  mov     [rsi], r13d
0x18001f287  mov     rbx, [rbp+pv]
0x18001f28b  test    rbx, rbx
0x18001f28e  jz      short loc_18001F2F5
0x18001f290  lea     rdi, [rbx+0C8h]
0x18001f297  mov     rcx, rdi; lpCriticalSection
0x18001f29a  call    cs:__imp_EnterCriticalSection
0x18001f2a0  or      dword ptr [rbx+48h], 300h
0x18001f2a7  cmp     qword ptr [rbx+0F8h], 0
0x18001f2af  jz      short loc_18001F2BD
0x18001f2b1  mov     edx, r13d
0x18001f2b4  lea     rcx, [rbx+8]
0x18001f2b8  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001f2bd  test    rdi, rdi
0x18001f2c0  jz      short loc_18001F2CB
0x18001f2c2  mov     rcx, rdi; lpCriticalSection
0x18001f2c5  call    cs:__imp_LeaveCriticalSection
0x18001f2cb  mov     rbx, [rbp+pv]
0x18001f2cf  test    rbx, rbx
0x18001f2d2  jz      short loc_18001F2F5
0x18001f2d4  or      eax, 0FFFFFFFFh
0x18001f2d7  lock xadd [rbx+118h], eax
0x18001f2df  cmp     eax, r12d
0x18001f2e2  jnz     short loc_18001F2F5
0x18001f2e4  mov     rcx, rbx
0x18001f2e7  call    ??1?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>(void)
0x18001f2ec  mov     rcx, rbx; pv
0x18001f2ef  call    cs:__imp_CoTaskMemFree
0x18001f2f5  mov     eax, r14d
0x18001f2f8  jmp     loc_18001F5B2
0x18001f2fd  cmp     [rbp+arg_0], 0
0x18001f301  jnz     short loc_18001F310
0x18001f303  mov     dword ptr [rbp+arg_10], r13d
0x18001f307  lea     rdx, [rbp+arg_10]
0x18001f30b  call    ??$wnf_publish_nothrow@H@wil@@YAJAEBU_WNF_STATE_NAME@@AEBH@Z; wil::wnf_publish_nothrow<int>(_WNF_STATE_NAME const &,int const &)
0x18001f310  mov     [rbp+arg_8], 0
0x18001f317  lea     rax, [rbp+arg_8]
0x18001f31b  mov     [rbp+var_28], rax
0x18001f31f  lea     rax, [rbp+arg_0]
0x18001f323  mov     [rbp+var_20], rax
0x18001f327  lea     rax, [rbp+pv]
0x18001f32b  mov     [rbp+var_18], rax
0x18001f32f  lea     r9, [rbp+arg_8]
0x18001f333  xor     r8d, r8d
0x18001f336  xor     edx, edx
0x18001f338  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x18001f33f  call    cs:__imp_DismOpenSession
0x18001f345  mov     edi, eax
0x18001f347  mov     rcx, [rbp+38h]; this
0x18001f34b  test    eax, eax
0x18001f34d  jns     short loc_18001F3C0
0x18001f34f  mov     r9d, eax; char *
0x18001f352  lea     r8, aPcshellShellAi_1; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18001f359  mov     edx, 0ACh; void *
0x18001f35e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f363  lea     rcx, [rbp+pv]
0x18001f367  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(void)
0x18001f36c  mov     rbx, [rax]
0x18001f36f  mov     [rbp+arg_10], rbx
0x18001f373  test    rbx, rbx
0x18001f376  jz      short loc_18001F380
0x18001f378  lock add [rbx+118h], r12d
0x18001f380  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001f387  call    cs:__imp_EnterCriticalSection
0x18001f38d  add     [rbx+0F0h], r12d
0x18001f394  mov     r14d, 3
0x18001f39a  mov     [rbx+110h], r14d
0x18001f3a1  lea     rcx, [rbp+arg_10]
0x18001f3a5  call    ??1?$test_data_control@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(void)
0x18001f3aa  mov     [rsi], r14d
0x18001f3ad  mov     [rbp+var_10], 0
0x18001f3b1  lea     rcx, [rbp+var_28]
0x18001f3b5  call    ??R_lambda_230c3f3d33a0fee7742e817ac9e8368c_@@QEBA@XZ; _lambda_230c3f3d33a0fee7742e817ac9e8368c_::operator()(void)
0x18001f3ba  nop
0x18001f3bb  jmp     loc_18001F586
0x18001f3c0  mov     [rsp+70h+var_40], 0
0x18001f3c9  mov     [rsp+70h+var_48], 0
0x18001f3d2  mov     qword ptr [rsp+70h+var_50], 0
0x18001f3db  mov     r9d, r12d
0x18001f3de  xor     r8d, r8d
0x18001f3e1  lea     rdx, aRecall; "Recall"
0x18001f3e8  mov     ecx, [rbp+arg_8]
0x18001f3eb  call    cs:__imp_DismDisableFeature
0x18001f3f1  mov     edi, eax
0x18001f3f3  cmp     eax, 80070BC2h
0x18001f3f8  jz      loc_18001F48C
0x18001f3fe  cmp     eax, 0BC2h
0x18001f403  jz      loc_18001F48C
0x18001f409  lea     rcx, [rbp+pv]
0x18001f40d  test    eax, eax
0x18001f40f  jns     short loc_18001F453
0x18001f411  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(void)
0x18001f416  mov     rbx, [rax]
0x18001f419  mov     [rbp+arg_10], rbx
0x18001f41d  test    rbx, rbx
0x18001f420  jz      short loc_18001F42A
0x18001f422  lock add [rbx+118h], r12d
0x18001f42a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001f431  call    cs:__imp_EnterCriticalSection
0x18001f437  add     [rbx+0F0h], r12d
0x18001f43e  mov     dword ptr [rbx+110h], 4
0x18001f448  lea     rcx, [rbp+arg_10]
0x18001f44c  call    ??1?$test_data_control@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(void)
0x18001f451  jmp     short loc_18001F4D2
0x18001f453  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(void)
0x18001f458  mov     rbx, [rax]
0x18001f45b  mov     [rbp+arg_10], rbx
0x18001f45f  test    rbx, rbx
0x18001f462  jz      short loc_18001F46C
0x18001f464  lock add [rbx+118h], r12d
0x18001f46c  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001f473  call    cs:__imp_EnterCriticalSection
0x18001f479  add     [rbx+0F0h], r12d
0x18001f480  mov     dword ptr [rbx+110h], 0Bh
0x18001f48a  jmp     short loc_18001F448
0x18001f48c  lea     rcx, [rbp+pv]
0x18001f490  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(void)
0x18001f495  mov     rbx, [rax]
0x18001f498  mov     [rbp+arg_10], rbx
0x18001f49c  test    rbx, rbx
0x18001f49f  jz      short loc_18001F4A9
0x18001f4a1  lock add [rbx+118h], r12d
0x18001f4a9  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001f4b0  call    cs:__imp_EnterCriticalSection
0x18001f4b6  add     [rbx+0F0h], r12d
0x18001f4bd  mov     dword ptr [rbx+110h], 6
0x18001f4c7  lea     rcx, [rbp+arg_10]
0x18001f4cb  call    ??1?$test_data_control@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(void)
0x18001f4d0  xor     edi, edi
0x18001f4d2  lea     rcx, [rbp+pv]
0x18001f4d6  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::ensure_data(void)
0x18001f4db  mov     rbx, [rax]
0x18001f4de  mov     [rbp+arg_10], rbx
0x18001f4e2  test    rbx, rbx
0x18001f4e5  jz      short loc_18001F4EF
0x18001f4e7  lock add [rbx+118h], r12d
0x18001f4ef  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001f4f6  call    cs:__imp_EnterCriticalSection
0x18001f4fc  add     [rbx+0F0h], r12d
0x18001f503  mov     eax, [rbx+110h]
0x18001f509  mov     [rsi], eax
0x18001f50b  lea     rcx, [rbp+arg_10]
0x18001f50f  call    ??1?$test_data_control@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>>(void)
0x18001f514  mov     qword ptr [rbp+var_30], 0
0x18001f51c  lea     rax, [rbp+var_30]
0x18001f520  mov     qword ptr [rsp+70h+var_50], rax; int
0x18001f525  xor     r9d, r9d
0x18001f528  xor     r8d, r8d
0x18001f52b  lea     rdx, aRecall; "Recall"
0x18001f532  mov     ecx, [rbp+arg_8]
0x18001f535  call    cs:__imp_DismGetFeatureInfo
0x18001f53b  mov     rcx, [rbp+38h]; this
0x18001f53f  test    eax, eax
0x18001f541  jns     short loc_18001F55D
0x18001f543  mov     r9d, eax; char *
0x18001f546  lea     r8, aPcshellShellAi_1; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18001f54d  mov     edx, 0D2h; void *
0x18001f552  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f557  mov     rcx, qword ptr [rbp+var_30]
0x18001f55b  jmp     short loc_18001F56C
0x18001f55d  mov     rcx, qword ptr [rbp+var_30]
0x18001f561  test    rcx, rcx
0x18001f564  jz      short loc_18001F578
0x18001f566  mov     eax, [rcx+8]
0x18001f569  mov     [rsi+4], eax
0x18001f56c  test    rcx, rcx
0x18001f56f  jz      short loc_18001F578
0x18001f571  call    cs:__imp_DismDelete
0x18001f577  nop
0x18001f578  mov     [rbp+var_10], 0
0x18001f57c  lea     rcx, [rbp+var_28]
0x18001f580  call    ??R_lambda_230c3f3d33a0fee7742e817ac9e8368c_@@QEBA@XZ; _lambda_230c3f3d33a0fee7742e817ac9e8368c_::operator()(void)
0x18001f585  nop
0x18001f586  mov     rbx, [rbp+pv]
0x18001f58a  test    rbx, rbx
0x18001f58d  jz      short loc_18001F5B0
0x18001f58f  or      eax, 0FFFFFFFFh
0x18001f592  lock xadd [rbx+118h], eax
0x18001f59a  cmp     eax, 1
0x18001f59d  jnz     short loc_18001F5B0
0x18001f59f  mov     rcx, rbx
0x18001f5a2  call    ??1?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::~merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>(void)
0x18001f5a7  mov     rcx, rbx; pv
0x18001f5aa  call    cs:__imp_CoTaskMemFree
0x18001f5b0  mov     eax, edi
0x18001f5b2  add     rsp, 70h
0x18001f5b6  pop     r14
0x18001f5b8  pop     r13
0x18001f5ba  pop     r12
0x18001f5bc  pop     rdi
0x18001f5bd  pop     rsi
0x18001f5be  pop     rbx
0x18001f5bf  pop     rbp
0x18001f5c0  retn
```
