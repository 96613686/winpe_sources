# tip2::tip_test<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>>::ensure_data(void)

- ea: `0x18002e674`
- end: `0x18002e700`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028844`

## callees

- `0x1800271d0`
- `0x180027c80`
- `0x18002e674`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e6c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e6ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e6c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e6ec`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>>::ensure_data(
        __int64 *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (__int64 *)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::~merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::~merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002e674  mov     [rsp+arg_10], rbx
0x18002e679  push    rdi
0x18002e67a  sub     rsp, 20h
0x18002e67e  cmp     qword ptr [rcx], 0
0x18002e682  mov     rdi, rcx
0x18002e685  jnz     short loc_18002E6F2
0x18002e687  lea     rcx, [rsp+28h+pv]
0x18002e68c  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>,>(void)
0x18002e691  mov     rdx, [rax]
0x18002e694  mov     qword ptr [rax], 0
0x18002e69b  mov     rbx, [rdi]
0x18002e69e  mov     [rdi], rdx
0x18002e6a1  test    rbx, rbx
0x18002e6a4  jz      short loc_18002E6C7
0x18002e6a6  or      eax, 0FFFFFFFFh
0x18002e6a9  lock xadd [rbx+118h], eax
0x18002e6b1  cmp     eax, 1
0x18002e6b4  jnz     short loc_18002E6C7
0x18002e6b6  mov     rcx, rbx
0x18002e6b9  call    ??1?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::~merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>(void)
0x18002e6be  mov     rcx, rbx; pv
0x18002e6c1  call    cs:__imp_CoTaskMemFree
0x18002e6c7  mov     rbx, [rsp+28h+pv]
0x18002e6cc  test    rbx, rbx
0x18002e6cf  jz      short loc_18002E6F2
0x18002e6d1  or      eax, 0FFFFFFFFh
0x18002e6d4  lock xadd [rbx+118h], eax
0x18002e6dc  cmp     eax, 1
0x18002e6df  jnz     short loc_18002E6F2
0x18002e6e1  mov     rcx, rbx
0x18002e6e4  call    ??1?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::~merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>(void)
0x18002e6e9  mov     rcx, rbx; pv
0x18002e6ec  call    cs:__imp_CoTaskMemFree
0x18002e6f2  mov     rbx, [rsp+28h+arg_10]
0x18002e6f7  mov     rax, rdi
0x18002e6fa  add     rsp, 20h
0x18002e6fe  pop     rdi
0x18002e6ff  retn
```
