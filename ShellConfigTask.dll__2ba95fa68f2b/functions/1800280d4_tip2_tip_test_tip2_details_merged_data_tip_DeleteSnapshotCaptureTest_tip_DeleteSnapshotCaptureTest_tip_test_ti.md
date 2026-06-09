# tip2::tip_test<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>>::~tip_test<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>>(void)

- ea: `0x1800280d4`
- end: `0x180028109`
- name: `??1?$tip_test@V?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800314b3`

## callees

- `0x180027c80`
- `0x1800280d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280fd`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>>::~tip_test<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>>(
        __int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::~merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>((struct _RTL_CRITICAL_SECTION *)v1);
      CoTaskMemFree((LPVOID)v1);
    }
  }
}

```

## disassembly

```asm
0x1800280d4  push    rbx
0x1800280d6  sub     rsp, 20h
0x1800280da  mov     rbx, [rcx]
0x1800280dd  test    rbx, rbx
0x1800280e0  jz      short loc_180028103
0x1800280e2  or      eax, 0FFFFFFFFh
0x1800280e5  lock xadd [rbx+118h], eax
0x1800280ed  cmp     eax, 1
0x1800280f0  jnz     short loc_180028103
0x1800280f2  mov     rcx, rbx
0x1800280f5  call    ??1?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::~merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>(void)
0x1800280fa  mov     rcx, rbx; pv
0x1800280fd  call    cs:__imp_CoTaskMemFree
0x180028103  add     rsp, 20h
0x180028107  pop     rbx
0x180028108  retn
```
