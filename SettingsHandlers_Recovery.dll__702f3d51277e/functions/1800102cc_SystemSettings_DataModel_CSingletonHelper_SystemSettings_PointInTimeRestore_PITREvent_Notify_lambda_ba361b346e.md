# SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::_Notify<_lambda_ba361b346e648473d0e0f5ec774d7d2a_>(_lambda_ba361b346e648473d0e0f5ec774d7d2a_ const &)

- ea: `0x1800102cc`
- end: `0x180010559`
- name: `??$_Notify@V_lambda_ba361b346e648473d0e0f5ec774d7d2a_@@@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_ba361b346e648473d0e0f5ec774d7d2a_@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014820`
- `0x180014bd0`
- `0x18001faf0`
- `0x18001fe30`
- `0x180020370`
- `0x180020900`
- `0x180022b20`
- `0x180022bf0`
- `0x180022cc0`
- `0x180022d90`
- `0x180024974`

## callees

- `0x18000282c`
- `0x180002890`
- `0x1800102cc`
- `0x180011d7c`
- `0x18001e840`
- `0x180021870`
- `0x180023260`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001043b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001043b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800104d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800104eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800104d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800104eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001044e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800104fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001044e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800104fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010393`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010393`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010478`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010478`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::_Notify<_lambda_ba361b346e648473d0e0f5ec774d7d2a_>(
        struct _RTL_CRITICAL_SECTION *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r14
  struct _RTL_CRITICAL_SECTION *v4; // r15
  struct _RTL_CRITICAL_SECTION *v5; // r13
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  _QWORD *i; // rax
  RTL_SRWLOCK *v9; // rdi
  __int64 v10; // r10
  unsigned __int64 j; // r8
  _QWORD *v12; // r8
  const WCHAR *v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  unsigned int v16; // r8d
  const char *v17; // r9
  _QWORD **v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rbx
  RTL_SRWLOCK *v21; // [rsp+30h] [rbp-98h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-90h]
  char v23[16]; // [rsp+40h] [rbp-88h] BYREF
  int v24; // [rsp+50h] [rbp-78h] BYREF
  void *Block; // [rsp+58h] [rbp-70h]
  __int64 v26; // [rsp+60h] [rbp-68h]
  __int64 v27; // [rsp+68h] [rbp-60h] BYREF
  __int128 v28; // [rsp+70h] [rbp-58h]
  __int64 v29; // [rsp+80h] [rbp-48h]
  __int64 v30; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  __int64 v34; // [rsp+D8h] [rbp+10h]
  RTL_SRWLOCK *v36; // [rsp+E0h] [rbp+18h]
  struct _RTL_CRITICAL_SECTION *v37; // [rsp+E8h] [rbp+20h]

  v34 = a2;
  v3 = a2;
  v4 = a1;
  v5 = a1;
  v37 = a1;
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  v26 = 0;
  v6 = operator new(0x18u);
  *v6 = v6;
  v6[1] = v6;
  Block = v6;
  v27 = 0;
  v28 = 0;
  v29 = 7;
  v30 = 8;
  v24 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>::_Assign_grow(
    &v27,
    16,
    v6);
LABEL_2:
  v21 = 0;
  SRWLock = 0;
  EnterCriticalSection(v4 + 4);
  v7 = *(_QWORD **)&v5[1].LockCount;
  for ( i = (_QWORD *)*v7; i != v7; i = (_QWORD *)*i )
  {
    v9 = (RTL_SRWLOCK *)i[2];
    v36 = v9;
    v10 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 8; ++j )
      v10 = 0x100000001B3LL * (*((unsigned __int8 *)&v36 + j) ^ (unsigned __int64)v10);
    v12 = *(_QWORD **)(v27 + 16 * (v10 & v29) + 8);
    if ( v12 == Block )
    {
LABEL_10:
      v12 = 0;
    }
    else
    {
      while ( v9 != (RTL_SRWLOCK *)v12[2] )
      {
        if ( v12 == *(_QWORD **)(v27 + 16 * (v10 & v29)) )
          goto LABEL_10;
        v12 = (_QWORD *)v12[1];
      }
    }
    if ( !v12 )
    {
      v21 = v9;
      AcquireSRWLockShared(v9 + 3);
      SRWLock = v9 + 3;
      if ( v4 != (struct _RTL_CRITICAL_SECTION *)-160LL )
        LeaveCriticalSection(v4 + 4);
      try
      {
        v13 = (const WCHAR *)(*(__int64 (__fastcall **)(RTL_SRWLOCK *))v9->Ptr)(v9);
        if ( CompareStringOrdinal(*(LPCWCH *)v3, -1, v13, -1, 0) == 2 )
          (*((void (__fastcall **)(RTL_SRWLOCK *, _QWORD))v9->Ptr + 1))(v9, **(unsigned int **)(v3 + 8));
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x652, v14, v15);
        v4 = a1;
        v3 = v34;
        v5 = v37;
      }
      try
      {
        std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::insert(
          &v24,
          v23,
          &v21);
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x65A, v16, v17);
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
        goto LABEL_23;
      }
      goto LABEL_2;
    }
  }
  if ( v4 != (struct _RTL_CRITICAL_SECTION *)-160LL )
    LeaveCriticalSection(v4 + 4);
LABEL_23:
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>(&v27);
  v18 = (_QWORD **)Block;
  **((_QWORD **)Block + 1) = 0;
  v19 = *v18;
  if ( v19 )
  {
    do
    {
      v20 = (_QWORD *)*v19;
      operator delete(v19);
      v19 = v20;
    }
    while ( v20 );
  }
  operator delete(Block);
}

```

## disassembly

```asm
0x1800102cc  mov     [rsp+arg_8], rdx
0x1800102d1  mov     [rsp+arg_0], rcx
0x1800102d6  push    rbx
0x1800102d7  push    rsi
0x1800102d8  push    rdi
0x1800102d9  push    r13
0x1800102db  push    r14
0x1800102dd  push    r15
0x1800102df  sub     rsp, 98h
0x1800102e6  mov     r14, rdx
0x1800102e9  mov     r15, rcx
0x1800102ec  mov     r13, rcx
0x1800102ef  mov     [rsp+0C8h+arg_18], rcx
0x1800102f7  mov     r8b, 3
0x1800102fa  mov     dl, 1
0x1800102fc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180010303  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180010308  mov     [rsp+0C8h+var_78], 0
0x180010310  mov     [rsp+0C8h+Block], 0
0x180010319  mov     [rsp+0C8h+var_68], 0
0x180010322  mov     ecx, 18h; Size
0x180010327  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001032c  mov     [rax], rax
0x18001032f  mov     [rax+8], rax
0x180010333  mov     [rsp+0C8h+Block], rax
0x180010338  mov     [rsp+0C8h+var_60], 0
0x180010341  xorps   xmm0, xmm0
0x180010344  movdqa  [rsp+0C8h+var_58], xmm0
0x18001034a  mov     [rsp+0C8h+var_48], 7
0x180010356  mov     [rsp+0C8h+var_40], 8
0x180010362  mov     [rsp+0C8h+var_78], 3F800000h
0x18001036a  mov     r8, rax
0x18001036d  mov     edx, 10h
0x180010372  lea     rcx, [rsp+0C8h+var_60]
0x180010377  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>)
0x18001037c  nop
0x18001037d  xor     eax, eax
0x18001037f  mov     [rsp+0C8h+var_98], rax
0x180010384  mov     [rsp+0C8h+SRWLock], rax
0x180010389  lea     rsi, [r15+0A0h]
0x180010390  mov     rcx, rsi; lpCriticalSection
0x180010393  call    cs:__imp_EnterCriticalSection
0x180010399  mov     rcx, [r13+30h]
0x18001039d  mov     rax, [rcx]
0x1800103a0  mov     r11, [rsp+0C8h+var_60]
0x1800103a5  cmp     rax, rcx
0x1800103a8  jz      loc_1800104F3
0x1800103ae  mov     rdi, [rax+10h]
0x1800103b2  mov     [rsp+0C8h+arg_10], rdi
0x1800103ba  mov     r10, 0CBF29CE484222325h
0x1800103c4  xor     r8d, r8d
0x1800103c7  movzx   edx, byte ptr [rsp+r8+0C8h+arg_10]
0x1800103d0  xor     r10, rdx
0x1800103d3  mov     r9, 100000001B3h
0x1800103dd  imul    r10, r9
0x1800103e1  inc     r8
0x1800103e4  cmp     r8, 8
0x1800103e8  jb      short loc_1800103C7
0x1800103ea  mov     r9, [rsp+0C8h+var_48]
0x1800103f2  and     r9, r10
0x1800103f5  mov     rdx, r9
0x1800103f8  add     rdx, rdx
0x1800103fb  mov     r8, [r11+rdx*8+8]
0x180010400  cmp     r8, [rsp+0C8h+Block]
0x180010405  jz      short loc_18001041F
0x180010407  add     r9, r9
0x18001040a  mov     rdx, [r11+r9*8]
0x18001040e  cmp     rdi, [r8+10h]
0x180010412  jz      short loc_180010422
0x180010414  cmp     r8, rdx
0x180010417  jz      short loc_18001041F
0x180010419  mov     r8, [r8+8]
0x18001041d  jmp     short loc_18001040E
0x18001041f  xor     r8d, r8d
0x180010422  test    r8, r8
0x180010425  jz      short loc_18001042F
0x180010427  mov     rax, [rax]
0x18001042a  jmp     loc_1800103A5
0x18001042f  mov     [rsp+0C8h+var_98], rdi
0x180010434  lea     rbx, [rdi+18h]
0x180010438  mov     rcx, rbx; SRWLock
0x18001043b  call    cs:__imp_AcquireSRWLockShared
0x180010441  mov     [rsp+0C8h+SRWLock], rbx
0x180010446  test    rsi, rsi
0x180010449  jz      short loc_180010455
0x18001044b  mov     rcx, rsi; lpCriticalSection
0x18001044e  call    cs:__imp_LeaveCriticalSection
0x180010454  nop
0x180010455  mov     rax, [rdi]
0x180010458  mov     rcx, rdi
0x18001045b  mov     rax, [rax]
0x18001045e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010463  mov     [rsp+0C8h+bIgnoreCase], 0; bIgnoreCase
0x18001046b  or      r9d, 0FFFFFFFFh; cchCount2
0x18001046f  mov     r8, rax; lpString2
0x180010472  or      edx, r9d; cchCount1
0x180010475  mov     rcx, [r14]; lpString1
0x180010478  call    cs:__imp_CompareStringOrdinal
0x18001047e  cmp     eax, 2
0x180010481  jnz     short loc_180010499
0x180010483  mov     rax, [rdi]
0x180010486  mov     rdx, [r14+8]
0x18001048a  mov     edx, [rdx]
0x18001048c  mov     rcx, rdi
0x18001048f  mov     rax, [rax+8]
0x180010493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010498  nop
0x180010499  jmp     short loc_1800104B3
0x18001049b  mov     r15, [rsp+0C8h+arg_0]
0x1800104a3  mov     r14, [rsp+0C8h+arg_8]
0x1800104ab  mov     r13, [rsp+0C8h+arg_18]
0x1800104b3  lea     r8, [rsp+0C8h+var_98]
0x1800104b8  lea     rdx, [rsp+0C8h+var_88]
0x1800104bd  lea     rcx, [rsp+0C8h+var_78]
0x1800104c2  call    ?insert@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@2@AEBQEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::insert(SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback * const &)
0x1800104c7  nop
0x1800104c8  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x1800104cd  test    rcx, rcx
0x1800104d0  jz      loc_18001037D
0x1800104d6  call    cs:__imp_ReleaseSRWLockShared
0x1800104dc  jmp     loc_18001037D
0x1800104e1  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x1800104e6  test    rcx, rcx
0x1800104e9  jz      short loc_180010502
0x1800104eb  call    cs:__imp_ReleaseSRWLockShared
0x1800104f1  jmp     short loc_180010502
0x1800104f3  test    rsi, rsi
0x1800104f6  jz      short loc_180010502
0x1800104f8  mov     rcx, rsi; lpCriticalSection
0x1800104fb  call    cs:__imp_LeaveCriticalSection
0x180010501  nop
0x180010502  lea     rcx, [rsp+0C8h+var_60]
0x180010507  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>(void)
0x18001050c  mov     rcx, [rsp+0C8h+Block]
0x180010511  mov     rax, [rcx+8]
0x180010515  mov     qword ptr [rax], 0
0x18001051c  mov     rcx, [rcx]; Block
0x18001051f  test    rcx, rcx
0x180010522  jz      short loc_180010539
0x180010524  mov     rbx, [rcx]
0x180010527  mov     edx, 18h
0x18001052c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010531  mov     rcx, rbx
0x180010534  test    rbx, rbx
0x180010537  jnz     short loc_180010524
0x180010539  mov     edx, 18h
0x18001053e  mov     rcx, [rsp+0C8h+Block]; Block
0x180010543  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010548  add     rsp, 98h
0x18001054f  pop     r15
0x180010551  pop     r14
0x180010553  pop     r13
0x180010555  pop     rdi
0x180010556  pop     rsi
0x180010557  pop     rbx
0x180010558  retn
```
