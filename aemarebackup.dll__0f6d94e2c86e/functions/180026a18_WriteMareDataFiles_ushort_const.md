# WriteMareDataFiles(ushort const *)

- ea: `0x180026a18`
- end: `0x180026ae2`
- name: `?WriteMareDataFiles@@YAJPEBG@Z`
- size: `202`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000eaf0`

## callees

- `0x18001359c`
- `0x1800172a0`
- `0x180026a18`
- `0x180027e30`
- `0x1800283e0`
- `0x18002a77c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026a79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026a79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026aa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026aa6`
- `ole32!CoTaskMemFree` at `0x180026ad1`
- `ole32!CoTaskMemFree` at `0x180026ad1`

## pseudocode

```c
__int64 __fastcall WriteMareDataFiles(const unsigned __int16 *a1)
{
  _QWORD *v1; // rax
  unsigned int v2; // edi
  char *v3; // rbx
  const char *v5; // rax
  wil *v6; // rcx
  std::exception *v7; // [rsp+30h] [rbp-38h] BYREF
  char v8[48]; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v10; // [rsp+70h] [rbp+8h]
  int v11; // [rsp+70h] [rbp+8h]
  LPVOID pv; // [rsp+78h] [rbp+10h] BYREF
  __int64 v13; // [rsp+80h] [rbp+18h]

  v13 = 0;
  pv = 0;
  v1 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::ensure_data(&pv);
  tip2::details::shared_data<1,0,1>::start(*v1 + 8LL, v8);
  try
  {
    v2 = Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData(&dword_1800F6C3C);
  }
  catch ( std::exception *v7 )
  {
    v5 = (const char *)(*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v7 + 8LL))(v7);
    AslLogCallPrintf(1, "WriteMareDataFiles", 28, v5);
    v10 = wil::ResultFromCaughtException(v6);
    v2 = v10;
  }
  catch ( ... )
  {
    v11 = -2147467259;
    AslLogCallPrintf(1, "WriteMareDataFiles", 34, "Unknown exception [%#x]", -2147467259);
    v2 = v11;
  }
  v3 = (char *)pv;
  if ( pv )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    *((_DWORD *)v3 + 18) |= 0x300u;
    if ( *((_QWORD *)v3 + 31) )
      tip2::details::shared_data<1,0,1>::complete_helper(v3 + 8, 2);
    if ( v3 != (char *)-200LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)v3 + 5);
    v3 = (char *)pv;
  }
  if ( v3 && _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(v3);
    CoTaskMemFree(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x180026a18  mov     rax, rsp
0x180026a1b  mov     [rax+8], rcx
0x180026a1f  push    rbx
0x180026a20  push    rsi
0x180026a21  push    rdi
0x180026a22  sub     rsp, 50h
0x180026a26  mov     qword ptr [rax+18h], 0
0x180026a2e  mov     qword ptr [rax+10h], 0
0x180026a36  lea     rcx, [rax+10h]
0x180026a3a  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>>::ensure_data(void)
0x180026a3f  mov     rcx, [rax]
0x180026a42  add     rcx, 8
0x180026a46  lea     rdx, [rsp+68h+var_30]
0x180026a4b  call    ?start@?$shared_data@$00$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,1>::start(void)
0x180026a50  nop
0x180026a51  lea     rcx, dword_1800F6C3C; unsigned __int16 *
0x180026a58  call    ?CollectAndWriteMareData@MareDataWriter@Inventory@Compat@Windows@@SAJPEBG@Z; Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData(ushort const *)
0x180026a5d  mov     edi, eax
0x180026a5f  jmp     short loc_180026A65
0x180026a61  mov     edi, [rsp+68h+arg_0]
0x180026a65  mov     rbx, [rsp+68h+pv]
0x180026a6a  test    rbx, rbx
0x180026a6d  jz      short loc_180026AB1
0x180026a6f  lea     rsi, [rbx+0C8h]
0x180026a76  mov     rcx, rsi; lpCriticalSection
0x180026a79  call    cs:__imp_EnterCriticalSection
0x180026a7f  or      dword ptr [rbx+48h], 300h
0x180026a86  cmp     qword ptr [rbx+0F8h], 0
0x180026a8e  jz      short loc_180026A9E
0x180026a90  mov     edx, 2
0x180026a95  lea     rcx, [rbx+8]
0x180026a99  call    ?complete_helper@?$shared_data@$00$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,1>::complete_helper(TestQueryOptions)
0x180026a9e  test    rsi, rsi
0x180026aa1  jz      short loc_180026AAC
0x180026aa3  mov     rcx, rsi; lpCriticalSection
0x180026aa6  call    cs:__imp_LeaveCriticalSection
0x180026aac  mov     rbx, [rsp+68h+pv]
0x180026ab1  test    rbx, rbx
0x180026ab4  jz      short loc_180026AD8
0x180026ab6  or      ecx, 0FFFFFFFFh
0x180026ab9  lock xadd [rbx+150h], ecx
0x180026ac1  cmp     ecx, 1
0x180026ac4  jnz     short loc_180026AD8
0x180026ac6  mov     rcx, rbx
0x180026ac9  call    ??1?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>(void)
0x180026ace  mov     rcx, rbx; pv
0x180026ad1  call    cs:__imp_CoTaskMemFree
0x180026ad7  nop
0x180026ad8  mov     eax, edi
0x180026ada  add     rsp, 50h
0x180026ade  pop     rdi
0x180026adf  pop     rsi
0x180026ae0  pop     rbx
0x180026ae1  retn
```
