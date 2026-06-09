# _lambda_48f6cde26dd6ee3a0f9b87dcee5c9a85_::operator()

- ea: `0x1800221d4`
- end: `0x1800223a3`
- name: `_lambda_48f6cde26dd6ee3a0f9b87dcee5c9a85_::operator()`
- size: `463`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180023d6c`
- `0x1800a4bb9`

## callees

- `0x180020c18`
- `0x180020da4`
- `0x1800221d4`
- `0x180025cb0`
- `0x18002626c`
- `0x180027f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002229a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002232b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002229a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002232b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022357`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022357`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002238c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002238c`

## pseudocode

```c
void __fastcall lambda_48f6cde26dd6ee3a0f9b87dcee5c9a85_::operator()(char **a1)
{
  int *v1; // rax
  int v2; // edi
  int v3; // esi
  char v4; // bp
  char v5; // r14
  char v6; // r15
  char v7; // r12
  char v8; // r13
  __int64 *v9; // rax
  __int64 v10; // rbx
  char *v11; // rbx
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  char v14; // [rsp+20h] [rbp-68h]
  LPVOID pv; // [rsp+28h] [rbp-60h] BYREF
  _OWORD v16[5]; // [rsp+30h] [rbp-58h] BYREF
  char v17; // [rsp+90h] [rbp+8h]
  char v18; // [rsp+98h] [rbp+10h]
  char v19; // [rsp+A0h] [rbp+18h]
  char v20; // [rsp+A8h] [rbp+20h]

  v1 = (int *)a1[11];
  pv = 0;
  v2 = *v1;
  v3 = *(_DWORD *)a1[10];
  v4 = *a1[9];
  v5 = *a1[8];
  v6 = *a1[7];
  v7 = *a1[6];
  v8 = *a1[5];
  v14 = *a1[4];
  v20 = *a1[3];
  v19 = *a1[2];
  v18 = *a1[1];
  v17 = **a1;
  v9 = tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>::ensure_data((__int64 *)&pv);
  tip2::details::shared_data<0,0,0>::start(*v9 + 8, v16);
  v10 = *tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>::ensure_data((__int64 *)&pv);
  *(_QWORD *)&v16[0] = v10;
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 296));
  EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 200));
  ++*(_DWORD *)(v10 + 240);
  *(_BYTE *)(v10 + 272) = v17;
  *(_BYTE *)(v10 + 273) = v18;
  *(_BYTE *)(v10 + 274) = v19;
  *(_BYTE *)(v10 + 275) = v20;
  *(_BYTE *)(v10 + 276) = v14;
  *(_BYTE *)(v10 + 277) = v8;
  *(_BYTE *)(v10 + 278) = v7;
  *(_BYTE *)(v10 + 279) = v6;
  *(_BYTE *)(v10 + 280) = v5;
  *(_BYTE *)(v10 + 281) = v4;
  *(_DWORD *)(v10 + 284) = v3;
  *(_DWORD *)(v10 + 288) = v2;
  if ( pv )
  {
    v11 = (char *)pv + 8;
    v12 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    *((_DWORD *)v11 + 16) |= 0x300u;
    if ( *((_QWORD *)v11 + 30) )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)v11, 2u);
    if ( v12 )
      LeaveCriticalSection(v12);
  }
  tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>((__int64 *)v16);
  v13 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)pv + 74, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>::~merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>(v13);
      CoTaskMemFree(v13);
    }
  }
}

```

## disassembly

```asm
0x1800221d4  push    rbx
0x1800221d6  push    rbp
0x1800221d7  push    rsi
0x1800221d8  push    rdi
0x1800221d9  push    r12
0x1800221db  push    r13
0x1800221dd  push    r14
0x1800221df  push    r15
0x1800221e1  sub     rsp, 48h
0x1800221e5  mov     rax, [rcx+58h]
0x1800221e9  mov     [rsp+88h+pv], 0
0x1800221f2  mov     edi, [rax]
0x1800221f4  mov     rax, [rcx+50h]
0x1800221f8  mov     esi, [rax]
0x1800221fa  mov     rax, [rcx+48h]
0x1800221fe  mov     bpl, [rax]
0x180022201  mov     rax, [rcx+40h]
0x180022205  mov     r14b, [rax]
0x180022208  mov     rax, [rcx+38h]
0x18002220c  mov     r15b, [rax]
0x18002220f  mov     rax, [rcx+30h]
0x180022213  mov     r12b, [rax]
0x180022216  mov     rax, [rcx+28h]
0x18002221a  mov     r13b, [rax]
0x18002221d  mov     rax, [rcx+20h]
0x180022221  mov     al, [rax]
0x180022223  mov     [rsp+88h+var_68], al
0x180022227  mov     rax, [rcx+18h]
0x18002222b  mov     al, [rax]
0x18002222d  mov     [rsp+88h+arg_18], al
0x180022234  mov     rax, [rcx+10h]
0x180022238  mov     al, [rax]
0x18002223a  mov     [rsp+88h+arg_10], al
0x180022241  mov     rax, [rcx+8]
0x180022245  mov     al, [rax]
0x180022247  mov     [rsp+88h+arg_8], al
0x18002224e  mov     rax, [rcx]
0x180022251  lea     rcx, [rsp+88h+pv]
0x180022256  mov     al, [rax]
0x180022258  mov     [rsp+88h+arg_0], al
0x18002225f  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>::ensure_data(void)
0x180022264  lea     rdx, [rsp+88h+var_58]
0x180022269  mov     rcx, [rax]
0x18002226c  add     rcx, 8
0x180022270  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180022275  lea     rcx, [rsp+88h+pv]
0x18002227a  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>::ensure_data(void)
0x18002227f  mov     rbx, [rax]
0x180022282  mov     [rsp+88h+var_58], rbx
0x180022287  test    rbx, rbx
0x18002228a  jz      short loc_180022293
0x18002228c  lock inc dword ptr [rbx+128h]
0x180022293  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18002229a  call    cs:__imp_EnterCriticalSection
0x1800222a0  inc     dword ptr [rbx+0F0h]
0x1800222a6  mov     al, [rsp+88h+arg_0]
0x1800222ad  mov     [rbx+110h], al
0x1800222b3  mov     al, [rsp+88h+arg_8]
0x1800222ba  mov     [rbx+111h], al
0x1800222c0  mov     al, [rsp+88h+arg_10]
0x1800222c7  mov     [rbx+112h], al
0x1800222cd  mov     al, [rsp+88h+arg_18]
0x1800222d4  mov     [rbx+113h], al
0x1800222da  mov     al, [rsp+88h+var_68]
0x1800222de  mov     [rbx+114h], al
0x1800222e4  mov     [rbx+115h], r13b
0x1800222eb  mov     [rbx+116h], r12b
0x1800222f2  mov     [rbx+117h], r15b
0x1800222f9  mov     [rbx+118h], r14b
0x180022300  mov     [rbx+119h], bpl
0x180022307  mov     [rbx+11Ch], esi
0x18002230d  mov     [rbx+120h], edi
0x180022313  mov     rax, [rsp+88h+pv]
0x180022318  test    rax, rax
0x18002231b  jz      short loc_18002235D
0x18002231d  lea     rbx, [rax+8]
0x180022321  lea     rdi, [rbx+0C0h]
0x180022328  mov     rcx, rdi; lpCriticalSection
0x18002232b  call    cs:__imp_EnterCriticalSection
0x180022331  or      dword ptr [rbx+40h], 300h
0x180022338  cmp     qword ptr [rbx+0F0h], 0
0x180022340  jz      short loc_18002234F
0x180022342  mov     edx, 2
0x180022347  mov     rcx, rbx
0x18002234a  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18002234f  test    rdi, rdi
0x180022352  jz      short loc_18002235D
0x180022354  mov     rcx, rdi; lpCriticalSection
0x180022357  call    cs:__imp_LeaveCriticalSection
0x18002235d  lea     rcx, [rsp+88h+var_58]
0x180022362  call    ??1?$test_data_control@V?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>(void)
0x180022367  mov     rbx, [rsp+88h+pv]
0x18002236c  test    rbx, rbx
0x18002236f  jz      short loc_180022392
0x180022371  or      eax, 0FFFFFFFFh
0x180022374  lock xadd [rbx+128h], eax
0x18002237c  cmp     eax, 1
0x18002237f  jnz     short loc_180022392
0x180022381  mov     rcx, rbx
0x180022384  call    ??1?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>::~merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>(void)
0x180022389  mov     rcx, rbx; pv
0x18002238c  call    cs:__imp_CoTaskMemFree
0x180022392  add     rsp, 48h
0x180022396  pop     r15
0x180022398  pop     r14
0x18002239a  pop     r13
0x18002239c  pop     r12
0x18002239e  pop     rdi
0x18002239f  pop     rsi
0x1800223a0  pop     rbp
0x1800223a1  pop     rbx
0x1800223a2  retn
```
