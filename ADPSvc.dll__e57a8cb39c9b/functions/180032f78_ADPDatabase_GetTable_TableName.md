# ADPDatabase::GetTable(TableName)

- ea: `0x180032f78`
- end: `0x18003333d`
- name: `?GetTable@ADPDatabase@@IEAA?AV?$shared_ptr@VDatabaseTable@@@std@@W4TableName@@@Z`
- size: `965`
- prototype: `_QWORD *__fastcall(RTL_SRWLOCK *, _QWORD *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800261b8`
- `0x18002a010`

## callees

- `0x1800033bc`
- `0x180024d34`
- `0x18002d8ec`
- `0x180032f78`
- `0x180034724`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800332f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800332f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032fa3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032fa3`

## string_xrefs

- `0x180033325`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`

## pseudocode

```c
_QWORD *__fastcall ADPDatabase::GetTable(RTL_SRWLOCK *a1, _QWORD *a2, int a3)
{
  RTL_SRWLOCK *v5; // r12
  __int64 v6; // rdx
  unsigned __int64 i; // r8
  __int64 v8; // rdx
  _QWORD *Ptr; // r9
  __int64 v10; // rcx
  __int64 v11; // rax
  _DWORD *v12; // rdx
  signed __int32 v13; // eax
  signed __int32 v14; // ett
  PVOID v15; // r13
  volatile signed __int32 *v16; // r14
  char *v17; // rbx
  char *v18; // rsi
  volatile signed __int32 *v19; // rax
  volatile signed __int32 *v20; // rdi
  _DWORD *v21; // rdx
  signed __int32 v22; // eax
  signed __int32 v23; // ett
  PVOID v24; // r13
  volatile signed __int32 *v25; // r14
  _DWORD *v26; // rdx
  signed __int32 v27; // eax
  signed __int32 v28; // ett
  PVOID v29; // r13
  volatile signed __int32 *v30; // r14
  __int64 v31; // rcx
  volatile signed __int32 *v32; // rdi
  const char *v34; // [rsp+20h] [rbp-30h]
  __int128 v35; // [rsp+28h] [rbp-28h] BYREF
  __int128 v36; // [rsp+38h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  __int64 v38; // [rsp+90h] [rbp+40h]
  int v39; // [rsp+A0h] [rbp+50h] BYREF
  RTL_SRWLOCK *v40; // [rsp+A8h] [rbp+58h]

  v39 = a3;
  v5 = a1 + 3;
  AcquireSRWLockExclusive(a1 + 3);
  v40 = v5;
  v38 = (__int64)&a1[5];
  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v6 = 0x100000001B3LL * (*((unsigned __int8 *)&v39 + i) ^ (unsigned __int64)v6);
  v8 = (__int64)a1[11].Ptr & v6;
  Ptr = a1[8].Ptr;
  v10 = Ptr[2 * v8 + 1];
  if ( (PVOID)v10 == a1[6].Ptr )
  {
LABEL_7:
    v10 = 0;
  }
  else
  {
    while ( v39 != *(_DWORD *)(v10 + 16) )
    {
      if ( v10 == Ptr[2 * v8] )
        goto LABEL_7;
      v10 = *(_QWORD *)(v10 + 8);
    }
  }
  if ( v10 && (PVOID)v10 != a1[6].Ptr )
  {
    *a2 = 0;
    a2[1] = 0;
    v11 = *(_QWORD *)(v10 + 32);
    if ( v11 )
      _InterlockedAdd((volatile signed __int32 *)(v11 + 8), 1u);
    *a2 = *(_QWORD *)(v10 + 24);
    a2[1] = *(_QWORD *)(v10 + 32);
    goto LABEL_51;
  }
  v36 = 0;
  if ( !v39 )
  {
    v35 = 0;
    v26 = a1[2].Ptr;
    if ( v26 )
    {
      v27 = v26[2];
      do
      {
        if ( !v27 )
          goto LABEL_55;
        v28 = v27;
        v27 = _InterlockedCompareExchange(v26 + 2, v27 + 1, v27);
      }
      while ( v28 != v27 );
      v29 = a1[1].Ptr;
      *(_QWORD *)&v35 = v29;
      v30 = (volatile signed __int32 *)a1[2].Ptr;
      *((_QWORD *)&v35 + 1) = v30;
      v17 = (char *)operator new(0x28u);
      *(_QWORD *)&v35 = v17;
      *(_OWORD *)v17 = 0;
      *((_DWORD *)v17 + 2) = 1;
      *((_DWORD *)v17 + 3) = 1;
      *(_QWORD *)v17 = &std::_Ref_count_obj2<ActionsPolicyTable>::`vftable';
      v18 = v17 + 16;
      *((_QWORD *)v17 + 2) = &EntityHistoryTable::`vftable';
      *((_QWORD *)v17 + 3) = 0;
      *((_QWORD *)v17 + 4) = 0;
      v19 = v30;
      v20 = v30;
      if ( v30 )
        _InterlockedIncrement(v30 + 2);
      *((_QWORD *)v17 + 3) = v29;
      *((_QWORD *)v17 + 4) = v30;
      *(_QWORD *)&v36 = v17 + 16;
      *((_QWORD *)&v36 + 1) = v17;
      goto LABEL_40;
    }
    goto LABEL_55;
  }
  if ( v39 == 1 )
  {
    v35 = 0;
    v21 = a1[2].Ptr;
    if ( v21 )
    {
      v22 = v21[2];
      do
      {
        if ( !v22 )
          goto LABEL_55;
        v23 = v22;
        v22 = _InterlockedCompareExchange(v21 + 2, v22 + 1, v22);
      }
      while ( v23 != v22 );
      v24 = a1[1].Ptr;
      *(_QWORD *)&v35 = v24;
      v25 = (volatile signed __int32 *)a1[2].Ptr;
      *((_QWORD *)&v35 + 1) = v25;
      v17 = (char *)operator new(0x28u);
      *(_QWORD *)&v35 = v17;
      *(_OWORD *)v17 = 0;
      *((_DWORD *)v17 + 2) = 1;
      *((_DWORD *)v17 + 3) = 1;
      *(_QWORD *)v17 = &std::_Ref_count_obj2<ActionsPolicyTable>::`vftable';
      v18 = v17 + 16;
      *((_QWORD *)v17 + 2) = &EntityHistoryTable::`vftable';
      *((_QWORD *)v17 + 3) = 0;
      *((_QWORD *)v17 + 4) = 0;
      v19 = v25;
      v20 = v25;
      if ( v25 )
        _InterlockedIncrement(v25 + 2);
      *((_QWORD *)v17 + 3) = v24;
      *((_QWORD *)v17 + 4) = v25;
      *(_QWORD *)&v36 = v17 + 16;
      *((_QWORD *)&v36 + 1) = v17;
      goto LABEL_40;
    }
LABEL_55:
    std::_Throw_bad_weak_ptr();
  }
  if ( v39 != 2 )
    wil::details::in1diag3::FailFast_UnexpectedMsg(
      retaddr,
      (void *)0x24E,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
      "Invalid table name",
      v34);
  v35 = 0;
  v12 = a1[2].Ptr;
  if ( !v12 )
    goto LABEL_55;
  v13 = v12[2];
  do
  {
    if ( !v13 )
      goto LABEL_55;
    v14 = v13;
    v13 = _InterlockedCompareExchange(v12 + 2, v13 + 1, v13);
  }
  while ( v14 != v13 );
  v15 = a1[1].Ptr;
  *(_QWORD *)&v35 = v15;
  v16 = (volatile signed __int32 *)a1[2].Ptr;
  *((_QWORD *)&v35 + 1) = v16;
  v17 = (char *)operator new(0x28u);
  *(_QWORD *)&v35 = v17;
  *(_OWORD *)v17 = 0;
  *((_DWORD *)v17 + 2) = 1;
  *((_DWORD *)v17 + 3) = 1;
  *(_QWORD *)v17 = &std::_Ref_count_obj2<ActionsPolicyTable>::`vftable';
  v18 = v17 + 16;
  *((_QWORD *)v17 + 2) = &EntityHistoryTable::`vftable';
  *((_QWORD *)v17 + 3) = 0;
  *((_QWORD *)v17 + 4) = 0;
  v19 = v16;
  v20 = v16;
  if ( v16 )
    _InterlockedIncrement(v16 + 2);
  *((_QWORD *)v17 + 3) = v15;
  *((_QWORD *)v17 + 4) = v16;
  *(_QWORD *)&v36 = v17 + 16;
  *((_QWORD *)&v36 + 1) = v17;
LABEL_40:
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  v31 = *(_QWORD *)std::_Hash<std::_Umap_traits<enum TableName,std::shared_ptr<DatabaseTable>,std::_Uhash_compare<enum TableName,std::hash<enum TableName>,std::equal_to<enum TableName>>,std::allocator<std::pair<enum TableName const,std::shared_ptr<DatabaseTable>>>,0>>::_Try_emplace<enum TableName const &,>(
                     v38,
                     (__int64)&v35,
                     &v39);
  if ( v17 )
    _InterlockedIncrement((volatile signed __int32 *)v17 + 2);
  *(_QWORD *)(v31 + 24) = v18;
  v32 = *(volatile signed __int32 **)(v31 + 32);
  *(_QWORD *)(v31 + 32) = v17;
  if ( v32 )
  {
    if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
      if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
    }
  }
  *a2 = v18;
  a2[1] = v17;
LABEL_51:
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  return a2;
}

```

## disassembly

```asm
0x180032f78  mov     [rsp-38h+arg_8], rbx
0x180032f7d  mov     [rsp-38h+arg_10], r8d
0x180032f82  push    rbp
0x180032f83  push    rsi
0x180032f84  push    rdi
0x180032f85  push    r12
0x180032f87  push    r13
0x180032f89  push    r14
0x180032f8b  push    r15
0x180032f8d  mov     rbp, rsp
0x180032f90  sub     rsp, 50h
0x180032f94  mov     r15, rdx
0x180032f97  mov     r14, rcx
0x180032f9a  xor     edi, edi
0x180032f9c  lea     r12, [rcx+18h]
0x180032fa0  mov     rcx, r12; SRWLock
0x180032fa3  call    cs:__imp_AcquireSRWLockExclusive
0x180032fa9  mov     [rbp+arg_18], r12
0x180032fad  lea     r10, [r14+28h]
0x180032fb1  mov     [rbp+arg_0], r10
0x180032fb5  mov     rdx, 0CBF29CE484222325h
0x180032fbf  mov     r8d, edi
0x180032fc2  lea     esi, [rdi+1]
0x180032fc5  movzx   eax, byte ptr [rbp+r8+arg_10]
0x180032fcb  xor     rdx, rax
0x180032fce  mov     rcx, 100000001B3h
0x180032fd8  imul    rdx, rcx
0x180032fdc  add     r8, rsi
0x180032fdf  cmp     r8, 4
0x180032fe3  jb      short loc_180032FC5
0x180032fe5  and     rdx, [r10+30h]
0x180032fe9  mov     r9, [r10+18h]
0x180032fed  mov     rax, rdx
0x180032ff0  add     rax, rax
0x180032ff3  mov     rcx, [r9+rax*8+8]
0x180032ff8  mov     r8d, [rbp+arg_10]
0x180032ffc  cmp     rcx, [r10+8]
0x180033000  jz      short loc_18003301A
0x180033002  add     rdx, rdx
0x180033005  mov     rax, [r9+rdx*8]
0x180033009  cmp     r8d, [rcx+10h]
0x18003300d  jz      short loc_18003301D
0x18003300f  cmp     rcx, rax
0x180033012  jz      short loc_18003301A
0x180033014  mov     rcx, [rcx+8]
0x180033018  jmp     short loc_180033009
0x18003301a  mov     rcx, rdi
0x18003301d  test    rcx, rcx
0x180033020  jz      short loc_180033050
0x180033022  cmp     rcx, [r10+8]
0x180033026  jz      short loc_180033050
0x180033028  mov     [r15], rdi
0x18003302b  mov     [r15+8], rdi
0x18003302f  mov     rax, [rcx+20h]
0x180033033  test    rax, rax
0x180033036  jz      short loc_18003303C
0x180033038  lock add [rax+8], esi
0x18003303c  mov     rax, [rcx+18h]
0x180033040  mov     [r15], rax
0x180033043  mov     rax, [rcx+20h]
0x180033047  mov     [r15+8], rax
0x18003304b  jmp     loc_1800332F1
0x180033050  xorps   xmm0, xmm0
0x180033053  movdqu  [rbp+var_18], xmm0
0x180033058  test    r8d, r8d
0x18003305b  jz      loc_1800331AE
0x180033061  sub     r8d, 1
0x180033065  jz      loc_180033112
0x18003306b  cmp     r8d, 1
0x18003306f  jnz     loc_18003331A
0x180033075  movdqu  [rbp+var_28], xmm0
0x18003307a  mov     rdx, [r14+10h]
0x18003307e  test    rdx, rdx
0x180033081  jz      loc_180033337
0x180033087  mov     eax, [rdx+8]
0x18003308a  jmp     short loc_180033096
0x18003308c  lea     ecx, [rax+1]
0x18003308f  lock cmpxchg [rdx+8], ecx
0x180033094  jz      short loc_1800330A0
0x180033096  test    eax, eax
0x180033098  jz      loc_180033337
0x18003309e  jmp     short loc_18003308C
0x1800330a0  mov     r13, [r14+8]
0x1800330a4  mov     qword ptr [rbp+var_28], r13
0x1800330a8  mov     r14, [r14+10h]
0x1800330ac  mov     qword ptr [rbp+var_28+8], r14
0x1800330b0  mov     ecx, 28h ; '('; Size
0x1800330b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800330ba  mov     rbx, rax
0x1800330bd  mov     qword ptr [rbp+var_28], rax
0x1800330c1  xorps   xmm0, xmm0
0x1800330c4  movups  xmmword ptr [rax], xmm0
0x1800330c7  mov     [rax+8], esi
0x1800330ca  mov     [rax+0Ch], esi
0x1800330cd  lea     rax, ??_7?$_Ref_count_obj2@UActionsPolicyTable@@@std@@6B@; const std::_Ref_count_obj2<ActionsPolicyTable>::`vftable'
0x1800330d4  mov     [rbx], rax
0x1800330d7  lea     rsi, [rbx+10h]
0x1800330db  lea     rax, ??_7EntityHistoryTable@@6B@; const EntityHistoryTable::`vftable'
0x1800330e2  mov     [rsi], rax
0x1800330e5  mov     [rsi+8], rdi
0x1800330e9  mov     [rsi+10h], rdi
0x1800330ed  mov     rax, r14
0x1800330f0  mov     rdi, r14
0x1800330f3  test    r14, r14
0x1800330f6  jz      short loc_1800330FD
0x1800330f8  lock inc dword ptr [r14+8]
0x1800330fd  mov     [rsi+8], r13
0x180033101  mov     [rsi+10h], r14
0x180033105  mov     qword ptr [rbp+var_18], rsi
0x180033109  mov     qword ptr [rbp+var_18+8], rbx
0x18003310d  jmp     loc_180033245
0x180033112  movdqu  [rbp+var_28], xmm0
0x180033117  mov     rdx, [r14+10h]
0x18003311b  test    rdx, rdx
0x18003311e  jz      loc_180033337
0x180033124  mov     eax, [rdx+8]
0x180033127  jmp     short loc_180033133
0x180033129  lea     ecx, [rax+1]
0x18003312c  lock cmpxchg [rdx+8], ecx
0x180033131  jz      short loc_18003313C
0x180033133  test    eax, eax
0x180033135  jnz     short loc_180033129
0x180033137  jmp     loc_180033337
0x18003313c  mov     r13, [r14+8]
0x180033140  mov     qword ptr [rbp+var_28], r13
0x180033144  mov     r14, [r14+10h]
0x180033148  mov     qword ptr [rbp+var_28+8], r14
0x18003314c  mov     ecx, 28h ; '('; Size
0x180033151  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033156  mov     rbx, rax
0x180033159  mov     qword ptr [rbp+var_28], rax
0x18003315d  xorps   xmm0, xmm0
0x180033160  movups  xmmword ptr [rax], xmm0
0x180033163  mov     [rax+8], esi
0x180033166  mov     [rax+0Ch], esi
0x180033169  lea     rax, ??_7?$_Ref_count_obj2@UActionsPolicyTable@@@std@@6B@; const std::_Ref_count_obj2<ActionsPolicyTable>::`vftable'
0x180033170  mov     [rbx], rax
0x180033173  lea     rsi, [rbx+10h]
0x180033177  lea     rax, ??_7EntityHistoryTable@@6B@; const EntityHistoryTable::`vftable'
0x18003317e  mov     [rsi], rax
0x180033181  mov     [rsi+8], rdi
0x180033185  mov     [rsi+10h], rdi
0x180033189  mov     rax, r14
0x18003318c  mov     rdi, r14
0x18003318f  test    r14, r14
0x180033192  jz      short loc_180033199
0x180033194  lock inc dword ptr [r14+8]
0x180033199  mov     [rsi+8], r13
0x18003319d  mov     [rsi+10h], r14
0x1800331a1  mov     qword ptr [rbp+var_18], rsi
0x1800331a5  mov     qword ptr [rbp+var_18+8], rbx
0x1800331a9  jmp     loc_180033245
0x1800331ae  movdqu  [rbp+var_28], xmm0
0x1800331b3  mov     rdx, [r14+10h]
0x1800331b7  test    rdx, rdx
0x1800331ba  jz      loc_180033337
0x1800331c0  mov     eax, [rdx+8]
0x1800331c3  jmp     short loc_1800331CF
0x1800331c5  lea     ecx, [rax+1]
0x1800331c8  lock cmpxchg [rdx+8], ecx
0x1800331cd  jz      short loc_1800331D8
0x1800331cf  test    eax, eax
0x1800331d1  jnz     short loc_1800331C5
0x1800331d3  jmp     loc_180033337
0x1800331d8  mov     r13, [r14+8]
0x1800331dc  mov     qword ptr [rbp+var_28], r13
0x1800331e0  mov     r14, [r14+10h]
0x1800331e4  mov     qword ptr [rbp+var_28+8], r14
0x1800331e8  mov     ecx, 28h ; '('; Size
0x1800331ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800331f2  mov     rbx, rax
0x1800331f5  mov     qword ptr [rbp+var_28], rax
0x1800331f9  xorps   xmm0, xmm0
0x1800331fc  movups  xmmword ptr [rax], xmm0
0x1800331ff  mov     [rax+8], esi
0x180033202  mov     [rax+0Ch], esi
0x180033205  lea     rax, ??_7?$_Ref_count_obj2@UActionsPolicyTable@@@std@@6B@; const std::_Ref_count_obj2<ActionsPolicyTable>::`vftable'
0x18003320c  mov     [rbx], rax
0x18003320f  lea     rsi, [rbx+10h]
0x180033213  lea     rax, ??_7EntityHistoryTable@@6B@; const EntityHistoryTable::`vftable'
0x18003321a  mov     [rsi], rax
0x18003321d  mov     [rsi+8], rdi
0x180033221  mov     [rsi+10h], rdi
0x180033225  mov     rax, r14
0x180033228  mov     rdi, r14
0x18003322b  test    r14, r14
0x18003322e  jz      short loc_180033235
0x180033230  lock inc dword ptr [r14+8]
0x180033235  mov     [rsi+8], r13
0x180033239  mov     [rsi+10h], r14
0x18003323d  mov     qword ptr [rbp+var_18], rsi
0x180033241  mov     qword ptr [rbp+var_18+8], rbx
0x180033245  or      r14d, 0FFFFFFFFh
0x180033249  test    rax, rax
0x18003324c  jz      short loc_180033285
0x18003324e  mov     eax, r14d
0x180033251  lock xadd [rdi+8], eax
0x180033256  add     eax, r14d
0x180033259  jnz     short loc_180033285
0x18003325b  mov     rax, [rdi]
0x18003325e  mov     rcx, rdi
0x180033261  mov     rax, [rax]
0x180033264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033269  mov     eax, r14d
0x18003326c  lock xadd [rdi+0Ch], eax
0x180033271  add     eax, r14d
0x180033274  jnz     short loc_180033285
0x180033276  mov     rax, [rdi]
0x180033279  mov     rcx, rdi
0x18003327c  mov     rax, [rax+8]
0x180033280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033285  lea     r8, [rbp+arg_10]
0x180033289  lea     rdx, [rbp+var_28]
0x18003328d  mov     rcx, [rbp+arg_0]
0x180033291  call    ??$_Try_emplace@AEBW4TableName@@$$V@?$_Hash@V?$_Umap_traits@W4TableName@@V?$shared_ptr@VDatabaseTable@@@std@@V?$_Uhash_compare@W4TableName@@U?$hash@W4TableName@@@std@@U?$equal_to@W4TableName@@@3@@3@V?$allocator@U?$pair@$$CBW4TableName@@V?$shared_ptr@VDatabaseTable@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4TableName@@V?$shared_ptr@VDatabaseTable@@@std@@@std@@PEAX@std@@_N@1@AEBW4TableName@@@Z; std::_Hash<std::_Umap_traits<TableName,std::shared_ptr<DatabaseTable>,std::_Uhash_compare<TableName,std::hash<TableName>,std::equal_to<TableName>>,std::allocator<std::pair<TableName const,std::shared_ptr<DatabaseTable>>>,0>>::_Try_emplace<TableName const &,>(TableName const &)
0x180033296  mov     rcx, [rax]
0x180033299  test    rbx, rbx
0x18003329c  jz      short loc_1800332A2
0x18003329e  lock inc dword ptr [rbx+8]
0x1800332a2  mov     [rcx+18h], rsi
0x1800332a6  mov     rdi, [rcx+20h]
0x1800332aa  mov     [rcx+20h], rbx
0x1800332ae  test    rdi, rdi
0x1800332b1  jz      short loc_1800332EA
0x1800332b3  mov     eax, r14d
0x1800332b6  lock xadd [rdi+8], eax
0x1800332bb  add     eax, r14d
0x1800332be  jnz     short loc_1800332EA
0x1800332c0  mov     rax, [rdi]
0x1800332c3  mov     rcx, rdi
0x1800332c6  mov     rax, [rax]
0x1800332c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332ce  mov     eax, r14d
0x1800332d1  lock xadd [rdi+0Ch], eax
0x1800332d6  add     eax, r14d
0x1800332d9  jnz     short loc_1800332EA
0x1800332db  mov     rax, [rdi]
0x1800332de  mov     rcx, rdi
0x1800332e1  mov     rax, [rax+8]
0x1800332e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332ea  mov     [r15], rsi
0x1800332ed  mov     [r15+8], rbx
0x1800332f1  test    r12, r12
0x1800332f4  jz      short loc_1800332FF
0x1800332f6  mov     rcx, r12; SRWLock
0x1800332f9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800332ff  mov     rax, r15
0x180033302  mov     rbx, [rsp+50h+arg_8]
0x18003330a  add     rsp, 50h
0x18003330e  pop     r15
0x180033310  pop     r14
0x180033312  pop     r13
0x180033314  pop     r12
0x180033316  pop     rdi
0x180033317  pop     rsi
0x180033318  pop     rbp
0x180033319  retn
0x18003331a  mov     rcx, [rbp+38h]; this
0x18003331e  lea     r9, aInvalidTableNa; "Invalid table name"
0x180033325  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18003332c  mov     edx, 24Eh; void *
0x180033331  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x180033337  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
```
