# _lambda_e5c96fcad99a0220c9fdc2dbfd8a2b73_::operator()

- ea: `0x18002252c`
- end: `0x18002265b`
- name: `_lambda_e5c96fcad99a0220c9fdc2dbfd8a2b73_::operator()`
- size: `303`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022d20`
- `0x1800a4914`

## callees

- `0x180020b8c`
- `0x180020d1c`
- `0x18002252c`
- `0x180025cb0`
- `0x1800261d8`
- `0x180027f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800225a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800225e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800225a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800225e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002260d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002260d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022642`

## pseudocode

```c
void __fastcall lambda_e5c96fcad99a0220c9fdc2dbfd8a2b73_::operator()(char **a1)
{
  char *v1; // rax
  char v2; // di
  char v3; // si
  char v4; // bp
  char v5; // r14
  __int64 *v6; // rax
  __int64 v7; // rbx
  char *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  __int128 v11; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF

  v1 = a1[3];
  pv = 0;
  v2 = *v1;
  v3 = *a1[2];
  v4 = *a1[1];
  v5 = **a1;
  v6 = tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>::ensure_data((__int64 *)&pv);
  tip2::details::shared_data<0,0,0>::start(*v6 + 8, &v11);
  v7 = *tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>::ensure_data((__int64 *)&pv);
  v12 = v7;
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 280));
  EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 200));
  ++*(_DWORD *)(v7 + 240);
  *(_BYTE *)(v7 + 272) = v5;
  *(_BYTE *)(v7 + 273) = v4;
  *(_BYTE *)(v7 + 274) = v3;
  *(_BYTE *)(v7 + 275) = v2;
  if ( pv )
  {
    v8 = (char *)pv + 8;
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    *((_DWORD *)v8 + 16) |= 0x300u;
    if ( *((_QWORD *)v8 + 30) )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)v8, 2u);
    if ( v9 )
      LeaveCriticalSection(v9);
  }
  tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>(&v12);
  v10 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>::~merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>(v10);
      CoTaskMemFree(v10);
    }
  }
}

```

## disassembly

```asm
0x18002252c  mov     r11, rsp
0x18002252f  mov     [r11+18h], rbx
0x180022533  mov     [r11+20h], rbp
0x180022537  push    rsi
0x180022538  push    rdi
0x180022539  push    r14
0x18002253b  sub     rsp, 30h
0x18002253f  mov     rax, [rcx+18h]
0x180022543  mov     qword ptr [r11+10h], 0
0x18002254b  mov     dil, [rax]
0x18002254e  mov     rax, [rcx+10h]
0x180022552  mov     sil, [rax]
0x180022555  mov     rax, [rcx+8]
0x180022559  mov     bpl, [rax]
0x18002255c  mov     rax, [rcx]
0x18002255f  lea     rcx, [r11+10h]
0x180022563  mov     r14b, [rax]
0x180022566  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>::ensure_data(void)
0x18002256b  lea     rdx, [rsp+48h+var_28]
0x180022570  mov     rcx, [rax]
0x180022573  add     rcx, 8
0x180022577  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18002257c  lea     rcx, [rsp+48h+pv]
0x180022581  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>::ensure_data(void)
0x180022586  mov     rbx, [rax]
0x180022589  mov     [rsp+48h+arg_0], rbx
0x18002258e  test    rbx, rbx
0x180022591  jz      short loc_18002259A
0x180022593  lock inc dword ptr [rbx+118h]
0x18002259a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800225a1  call    cs:__imp_EnterCriticalSection
0x1800225a7  inc     dword ptr [rbx+0F0h]
0x1800225ad  mov     [rbx+110h], r14b
0x1800225b4  mov     [rbx+111h], bpl
0x1800225bb  mov     [rbx+112h], sil
0x1800225c2  mov     [rbx+113h], dil
0x1800225c9  mov     rax, [rsp+48h+pv]
0x1800225ce  test    rax, rax
0x1800225d1  jz      short loc_180022613
0x1800225d3  lea     rbx, [rax+8]
0x1800225d7  lea     rdi, [rbx+0C0h]
0x1800225de  mov     rcx, rdi; lpCriticalSection
0x1800225e1  call    cs:__imp_EnterCriticalSection
0x1800225e7  or      dword ptr [rbx+40h], 300h
0x1800225ee  cmp     qword ptr [rbx+0F0h], 0
0x1800225f6  jz      short loc_180022605
0x1800225f8  mov     edx, 2
0x1800225fd  mov     rcx, rbx
0x180022600  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180022605  test    rdi, rdi
0x180022608  jz      short loc_180022613
0x18002260a  mov     rcx, rdi; lpCriticalSection
0x18002260d  call    cs:__imp_LeaveCriticalSection
0x180022613  lea     rcx, [rsp+48h+arg_0]
0x180022618  call    ??1?$test_data_control@V?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>(void)
0x18002261d  mov     rbx, [rsp+48h+pv]
0x180022622  test    rbx, rbx
0x180022625  jz      short loc_180022648
0x180022627  or      eax, 0FFFFFFFFh
0x18002262a  lock xadd [rbx+118h], eax
0x180022632  cmp     eax, 1
0x180022635  jnz     short loc_180022648
0x180022637  mov     rcx, rbx
0x18002263a  call    ??1?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>::~merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>(void)
0x18002263f  mov     rcx, rbx; pv
0x180022642  call    cs:__imp_CoTaskMemFree
0x180022648  mov     rbx, [rsp+48h+arg_10]
0x18002264d  mov     rbp, [rsp+48h+arg_18]
0x180022652  add     rsp, 30h
0x180022656  pop     r14
0x180022658  pop     rdi
0x180022659  pop     rsi
0x18002265a  retn
```
