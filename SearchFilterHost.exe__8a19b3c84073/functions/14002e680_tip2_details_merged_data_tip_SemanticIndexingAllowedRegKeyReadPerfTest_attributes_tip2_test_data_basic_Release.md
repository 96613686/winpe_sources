# tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::Release(void)

- ea: `0x14002e680`
- end: `0x14002e6b8`
- name: `?Release@?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002d5b0`
- `0x14002fd70`

## callees

- `0x14002d5f8`
- `0x14002e680`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e6a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e6a5`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 84);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::~merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>((__int64)pv);
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x14002e680  mov     [rsp+arg_0], rbx
0x14002e685  push    rdi
0x14002e686  sub     rsp, 20h
0x14002e68a  mov     rdi, rcx
0x14002e68d  or      ebx, 0FFFFFFFFh
0x14002e690  lock xadd [rcx+150h], ebx
0x14002e698  sub     ebx, 1
0x14002e69b  jnz     short loc_14002E6AB
0x14002e69d  call    ??1?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::~merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>(void)
0x14002e6a2  mov     rcx, rdi; pv
0x14002e6a5  call    cs:__imp_CoTaskMemFree
0x14002e6ab  mov     eax, ebx
0x14002e6ad  mov     rbx, [rsp+28h+arg_0]
0x14002e6b2  add     rsp, 20h
0x14002e6b6  pop     rdi
0x14002e6b7  retn
```
