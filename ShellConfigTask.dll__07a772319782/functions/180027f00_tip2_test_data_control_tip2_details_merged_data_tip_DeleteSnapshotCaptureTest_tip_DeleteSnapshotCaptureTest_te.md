# tip2::test_data_control<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>>::~test_data_control<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>>(void)

- ea: `0x180027f00`
- end: `0x180027f82`
- name: `??1?$test_data_control@V?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180028844`

## callees

- `0x180021ecc`
- `0x180027c80`
- `0x180027f00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027f48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027f71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027f48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027f71`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>>::~test_data_control<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::~merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::~merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180027f00  mov     [rsp+arg_8], rbx
0x180027f05  push    rdi
0x180027f06  sub     rsp, 20h
0x180027f0a  mov     rdi, rcx
0x180027f0d  mov     rcx, [rcx]
0x180027f10  test    rcx, rcx
0x180027f13  jz      short loc_180027F4E
0x180027f15  add     rcx, 8
0x180027f19  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180027f1e  mov     rbx, [rdi]
0x180027f21  mov     qword ptr [rdi], 0
0x180027f28  test    rbx, rbx
0x180027f2b  jz      short loc_180027F4E
0x180027f2d  or      eax, 0FFFFFFFFh
0x180027f30  lock xadd [rbx+118h], eax
0x180027f38  cmp     eax, 1
0x180027f3b  jnz     short loc_180027F4E
0x180027f3d  mov     rcx, rbx
0x180027f40  call    ??1?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::~merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>(void)
0x180027f45  mov     rcx, rbx; pv
0x180027f48  call    cs:__imp_CoTaskMemFree
0x180027f4e  mov     rbx, [rdi]
0x180027f51  test    rbx, rbx
0x180027f54  jz      short loc_180027F77
0x180027f56  or      eax, 0FFFFFFFFh
0x180027f59  lock xadd [rbx+118h], eax
0x180027f61  cmp     eax, 1
0x180027f64  jnz     short loc_180027F77
0x180027f66  mov     rcx, rbx
0x180027f69  call    ??1?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::~merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>(void)
0x180027f6e  mov     rcx, rbx; pv
0x180027f71  call    cs:__imp_CoTaskMemFree
0x180027f77  mov     rbx, [rsp+28h+arg_8]
0x180027f7c  add     rsp, 20h
0x180027f80  pop     rdi
0x180027f81  retn
```
