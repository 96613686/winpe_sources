# _anonymous_namespace_::CleanupMmpcEnrollments

- ea: `0x140052fc0`
- end: `0x1400532f2`
- name: `_anonymous_namespace_::CleanupMmpcEnrollments`
- size: `818`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x140053430`
- `0x140054320`

## callees

- `0x1400095b4`
- `0x1400347e8`
- `0x140034950`
- `0x140052c80`
- `0x140052d0c`
- `0x140052fc0`
- `0x140056210`
- `0x140056498`
- `0x140056784`
- `0x140057ef4`
- `0x14005d010`

## import_xrefs

- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x140052fdd`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x140052fdd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400530a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140053164`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400531b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400531f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14005323b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400530a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140053164`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400531b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400531f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14005323b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140053266`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140053266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140053111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140053111`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140053124`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140053124`
- `OLEAUT32!__imp_SysFreeString` at `0x14005311c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400532bb`
- `OLEAUT32!__imp_SysFreeString` at `0x14005311c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400532bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400532ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400532ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall anonymous_namespace_::CleanupMmpcEnrollments(__int64 a1)
{
  __int64 DatabaseManagerInstance; // rbx
  __int64 (__fastcall *v3)(__int64, __int64, __int64 *, _QWORD); // rsi
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  struct _RTL_CRITICAL_SECTION **v9; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  __int64 v11; // rbx
  unsigned int (__fastcall *v12)(__int64, __int64 *); // rdi
  __int64 v13; // rcx
  __int64 v14; // rsi
  int (__fastcall *v15)(__int64, BSTR *); // r14
  OLECHAR *v16; // rdi
  DWORD LastError; // ebx
  struct _RTL_CRITICAL_SECTION *v18; // rbx
  int v19; // edi
  struct _RTL_CRITICAL_SECTION *v20; // rbx
  struct _RTL_CRITICAL_SECTION *v21; // rbx
  CEnrollmentLogger *Logger; // rax
  char *v23; // rbx
  struct _RTL_CRITICAL_SECTION *v24; // rdi
  __int64 v25; // rcx
  struct _RTL_CRITICAL_SECTION *v26; // rbx
  __int64 v27; // rcx
  int v28; // [rsp+20h] [rbp-30h]
  __int64 v29; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  __int128 v31; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct _RTL_CRITICAL_SECTION *v33; // [rsp+88h] [rbp+38h] BYREF
  __int64 v34; // [rsp+90h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+48h] BYREF

  v34 = 0;
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v3 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)DatabaseManagerInstance + 24LL);
  v4 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = v3(DatabaseManagerInstance, a1, &v34, 0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    bstrString = 0;
    pv = 0;
    v9 = tip2::tip_test<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)&pv);
    tip2::details::shared_data<0,0,0>::start((__int64)&(*v9)->LockCount, &v31);
    v10 = *tip2::tip_test<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)&pv);
    v33 = v10;
    if ( v10 )
      _InterlockedIncrement(&v10[7].LockCount);
    EnterCriticalSection(v10 + 5);
    ++LODWORD(v10[6].DebugInfo);
    HIDWORD(v10[6].SpinCount) = 0;
    tip2::test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>(&v33);
    v29 = 0;
    while ( 1 )
    {
      v11 = v34;
      v12 = *(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 24LL);
      v13 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      if ( v12(v11, &v29) )
        break;
      v14 = v29;
      v15 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v29 + 32LL);
      v16 = bstrString;
      if ( bstrString )
      {
        LastError = GetLastError();
        SysFreeString(v16);
        SetLastError(LastError);
      }
      bstrString = 0;
      if ( v15(v14, &bstrString) >= 0 )
      {
        v18 = *tip2::tip_test<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)&pv);
        v33 = v18;
        if ( v18 )
          _InterlockedIncrement(&v18[7].LockCount);
        EnterCriticalSection(v18 + 5);
        ++LODWORD(v18[6].DebugInfo);
        ++HIDWORD(v18[6].SpinCount);
        tip2::test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>(&v33);
        v19 = UnEnrollMmpcFromDualEnrollment(bstrString);
        if ( v19 < 0 )
        {
          v20 = *tip2::tip_test<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)&pv);
          v33 = v20;
          if ( v20 )
            _InterlockedIncrement(&v20[7].LockCount);
          EnterCriticalSection(v20 + 5);
          ++LODWORD(v20[6].DebugInfo);
          LOBYTE(v20[7].DebugInfo) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>(&v33);
        }
        v21 = *tip2::tip_test<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::ensure_data((struct _RTL_CRITICAL_SECTION **)&pv);
        v33 = v21;
        if ( v21 )
          _InterlockedIncrement(&v21[7].LockCount);
        EnterCriticalSection(v21 + 5);
        ++LODWORD(v21[6].DebugInfo);
        LODWORD(v21[6].SpinCount) = v19;
        tip2::test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>(&v33);
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogCleanupStaleEnrollments(Logger, bstrString, v19);
      }
    }
    if ( pv )
    {
      v23 = (char *)pv + 8;
      v24 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      *((_DWORD *)v23 + 16) |= 0x300u;
      if ( *((_QWORD *)v23 + 30) )
        tip2::details::shared_data<0,0,0>::complete_helper((__int64)v23, 2u);
      if ( v24 )
        LeaveCriticalSection(v24);
    }
    v25 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>::~merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>(v26);
      CoTaskMemFree(v26);
    }
    if ( bstrString )
      SysFreeString(bstrString);
    v27 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
      (const char *)(unsigned int)v5,
      v28);
    v7 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v6;
  }
}

```

## disassembly

```asm
0x140052fc0  mov     [rsp-28h+arg_0], rbx
0x140052fc5  push    rbp
0x140052fc6  push    rsi
0x140052fc7  push    rdi
0x140052fc8  push    r14
0x140052fca  push    r15
0x140052fcc  mov     rbp, rsp
0x140052fcf  sub     rsp, 50h
0x140052fd3  mov     rdi, rcx
0x140052fd6  xor     r15d, r15d
0x140052fd9  mov     [rbp+arg_10], r15
0x140052fdd  call    cs:__imp_GetDatabaseManagerInstance
0x140052fe3  mov     rbx, rax
0x140052fe6  mov     rdx, [rax]
0x140052fe9  mov     rsi, [rdx+18h]
0x140052fed  mov     rcx, [rbp+arg_10]
0x140052ff1  test    rcx, rcx
0x140052ff4  jz      short loc_140053007
0x140052ff6  mov     [rbp+arg_10], r15
0x140052ffa  mov     rdx, [rcx]
0x140052ffd  mov     rax, [rdx+10h]
0x140053001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053006  nop
0x140053007  xor     r9d, r9d
0x14005300a  lea     r8, [rbp+arg_10]
0x14005300e  mov     rdx, rdi
0x140053011  mov     rcx, rbx
0x140053014  mov     rax, rsi
0x140053017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005301c  mov     ebx, eax
0x14005301e  test    eax, eax
0x140053020  jns     short loc_14005305C
0x140053022  mov     rcx, [rbp+28h]; this
0x140053026  mov     r9d, eax; char *
0x140053029  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140053030  mov     edx, 65h ; 'e'; void *
0x140053035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005303a  nop
0x14005303b  mov     rcx, [rbp+arg_10]
0x14005303f  test    rcx, rcx
0x140053042  jz      short loc_140053055
0x140053044  mov     [rbp+arg_10], r15
0x140053048  mov     rax, [rcx]
0x14005304b  mov     rax, [rax+10h]
0x14005304f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053054  nop
0x140053055  mov     eax, ebx
0x140053057  jmp     loc_1400532DE
0x14005305c  mov     [rbp+bstrString], r15
0x140053060  mov     [rbp+pv], r15
0x140053064  lea     rcx, [rbp+pv]
0x140053068  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::ensure_data(void)
0x14005306d  mov     rcx, [rax]
0x140053070  add     rcx, 8
0x140053074  lea     rdx, [rbp+var_10]
0x140053078  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x14005307d  nop
0x14005307e  lea     rcx, [rbp+pv]
0x140053082  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::ensure_data(void)
0x140053087  mov     rbx, [rax]
0x14005308a  mov     [rbp+arg_8], rbx
0x14005308e  test    rbx, rbx
0x140053091  jz      short loc_14005309A
0x140053093  lock inc dword ptr [rbx+120h]
0x14005309a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1400530a1  call    cs:__imp_EnterCriticalSection
0x1400530a7  inc     dword ptr [rbx+0F0h]
0x1400530ad  mov     [rbx+114h], r15d
0x1400530b4  lea     rcx, [rbp+arg_8]
0x1400530b8  call    ??1?$test_data_control@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>(void)
0x1400530bd  mov     [rbp+var_20], r15
0x1400530c1  mov     rbx, [rbp+arg_10]
0x1400530c5  mov     rax, [rbx]
0x1400530c8  mov     rdi, [rax+18h]
0x1400530cc  mov     rcx, [rbp+var_20]
0x1400530d0  test    rcx, rcx
0x1400530d3  jz      short loc_1400530E6
0x1400530d5  mov     [rbp+var_20], r15
0x1400530d9  mov     rdx, [rcx]
0x1400530dc  mov     rax, [rdx+10h]
0x1400530e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400530e5  nop
0x1400530e6  lea     rdx, [rbp+var_20]
0x1400530ea  mov     rcx, rbx
0x1400530ed  mov     rax, rdi
0x1400530f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400530f5  test    eax, eax
0x1400530f7  jnz     loc_140053224
0x1400530fd  mov     rsi, [rbp+var_20]
0x140053101  mov     rax, [rsi]
0x140053104  mov     r14, [rax+20h]
0x140053108  mov     rdi, [rbp+bstrString]
0x14005310c  test    rdi, rdi
0x14005310f  jz      short loc_14005312A
0x140053111  call    cs:__imp_GetLastError
0x140053117  mov     ebx, eax
0x140053119  mov     rcx, rdi; bstrString
0x14005311c  call    cs:__imp_SysFreeString
0x140053122  mov     ecx, ebx; dwErrCode
0x140053124  call    cs:__imp_SetLastError
0x14005312a  mov     [rbp+bstrString], r15
0x14005312e  lea     rdx, [rbp+bstrString]
0x140053132  mov     rcx, rsi
0x140053135  mov     rax, r14
0x140053138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005313d  test    eax, eax
0x14005313f  js      short loc_1400530C1
0x140053141  lea     rcx, [rbp+pv]
0x140053145  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::ensure_data(void)
0x14005314a  mov     rbx, [rax]
0x14005314d  mov     [rbp+arg_8], rbx
0x140053151  test    rbx, rbx
0x140053154  jz      short loc_14005315D
0x140053156  lock inc dword ptr [rbx+120h]
0x14005315d  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140053164  call    cs:__imp_EnterCriticalSection
0x14005316a  inc     dword ptr [rbx+0F0h]
0x140053170  inc     dword ptr [rbx+114h]
0x140053176  lea     rcx, [rbp+arg_8]
0x14005317a  call    ??1?$test_data_control@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>(void)
0x14005317f  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x140053183  call    ?UnEnrollMmpcFromDualEnrollment@@YAJPEBG@Z; UnEnrollMmpcFromDualEnrollment(ushort const *)
0x140053188  mov     edi, eax
0x14005318a  test    eax, eax
0x14005318c  jns     short loc_1400531CD
0x14005318e  lea     rcx, [rbp+pv]
0x140053192  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::ensure_data(void)
0x140053197  mov     rbx, [rax]
0x14005319a  mov     [rbp+arg_8], rbx
0x14005319e  test    rbx, rbx
0x1400531a1  jz      short loc_1400531AA
0x1400531a3  lock inc dword ptr [rbx+120h]
0x1400531aa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1400531b1  call    cs:__imp_EnterCriticalSection
0x1400531b7  inc     dword ptr [rbx+0F0h]
0x1400531bd  mov     byte ptr [rbx+118h], 1
0x1400531c4  lea     rcx, [rbp+arg_8]
0x1400531c8  call    ??1?$test_data_control@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>(void)
0x1400531cd  lea     rcx, [rbp+pv]
0x1400531d1  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::ensure_data(void)
0x1400531d6  mov     rbx, [rax]
0x1400531d9  mov     [rbp+arg_8], rbx
0x1400531dd  test    rbx, rbx
0x1400531e0  jz      short loc_1400531E9
0x1400531e2  lock inc dword ptr [rbx+120h]
0x1400531e9  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1400531f0  call    cs:__imp_EnterCriticalSection
0x1400531f6  inc     dword ptr [rbx+0F0h]
0x1400531fc  mov     [rbx+110h], edi
0x140053202  lea     rcx, [rbp+arg_8]
0x140053206  call    ??1?$test_data_control@V?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>::~test_data_control<tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>>(void)
0x14005320b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140053210  mov     r8d, edi; int
0x140053213  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x140053217  mov     rcx, rax; this
0x14005321a  call    ?LogCleanupStaleEnrollments@CEnrollmentLogger@@QEAAXPEBGJ@Z; CEnrollmentLogger::LogCleanupStaleEnrollments(ushort const *,long)
0x14005321f  jmp     loc_1400530C1
0x140053224  mov     rax, [rbp+pv]
0x140053228  test    rax, rax
0x14005322b  jz      short loc_14005326D
0x14005322d  lea     rbx, [rax+8]
0x140053231  lea     rdi, [rbx+0C0h]
0x140053238  mov     rcx, rdi; lpCriticalSection
0x14005323b  call    cs:__imp_EnterCriticalSection
0x140053241  or      dword ptr [rbx+40h], 300h
0x140053248  cmp     [rbx+0F0h], r15
0x14005324f  jz      short loc_14005325E
0x140053251  mov     edx, 2
0x140053256  mov     rcx, rbx
0x140053259  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x14005325e  test    rdi, rdi
0x140053261  jz      short loc_14005326D
0x140053263  mov     rcx, rdi; lpCriticalSection
0x140053266  call    cs:__imp_LeaveCriticalSection
0x14005326c  nop
0x14005326d  mov     rcx, [rbp+var_20]
0x140053271  test    rcx, rcx
0x140053274  jz      short loc_140053287
0x140053276  mov     [rbp+var_20], r15
0x14005327a  mov     rax, [rcx]
0x14005327d  mov     rax, [rax+10h]
0x140053281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053286  nop
0x140053287  mov     rbx, [rbp+pv]
0x14005328b  test    rbx, rbx
0x14005328e  jz      short loc_1400532B2
0x140053290  or      eax, 0FFFFFFFFh
0x140053293  lock xadd [rbx+120h], eax
0x14005329b  cmp     eax, 1
0x14005329e  jnz     short loc_1400532B2
0x1400532a0  mov     rcx, rbx
0x1400532a3  call    ??1?$merged_data@U_tip_MmpcDualEnrollmentTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>::~merged_data<_tip_MmpcDualEnrollmentTipTest,_tip_MmpcDualEnrollmentTipTest>(void)
0x1400532a8  mov     rcx, rbx; pv
0x1400532ab  call    cs:__imp_CoTaskMemFree
0x1400532b1  nop
0x1400532b2  mov     rcx, [rbp+bstrString]; bstrString
0x1400532b6  test    rcx, rcx
0x1400532b9  jz      short loc_1400532C2
0x1400532bb  call    cs:__imp_SysFreeString
0x1400532c1  nop
0x1400532c2  mov     rcx, [rbp+arg_10]
0x1400532c6  test    rcx, rcx
0x1400532c9  jz      short loc_1400532DC
0x1400532cb  mov     [rbp+arg_10], r15
0x1400532cf  mov     rax, [rcx]
0x1400532d2  mov     rax, [rax+10h]
0x1400532d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400532db  nop
0x1400532dc  xor     eax, eax
0x1400532de  mov     rbx, [rsp+50h+arg_0]
0x1400532e6  add     rsp, 50h
0x1400532ea  pop     r15
0x1400532ec  pop     r14
0x1400532ee  pop     rdi
0x1400532ef  pop     rsi
0x1400532f0  pop     rbp
0x1400532f1  retn
```
