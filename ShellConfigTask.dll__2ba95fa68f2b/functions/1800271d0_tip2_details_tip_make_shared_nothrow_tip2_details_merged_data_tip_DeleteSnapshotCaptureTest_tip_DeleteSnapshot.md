# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>,>(void)

- ea: `0x1800271d0`
- end: `0x18002728b`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e674`

## callees

- `0x18000c5c4`
- `0x180012f30`
- `0x1800271d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800271e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800271e2`

## string_xrefs

- `0x180027211`: `DeleteSnapshotCaptureTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  wil::details::in1diag3 *v3; // rcx
  _QWORD *v4; // rbx
  _QWORD *result; // rax
  _DWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v7; // [rsp+28h] [rbp-30h]
  __int16 v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+32h] [rbp-26h]
  __int16 v10; // [rsp+36h] [rbp-22h]
  __int128 v11; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+48h] [rbp-10h]

  v2 = CoTaskMemAlloc(0x120u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 57155508;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "DeleteSnapshotCaptureTest";
  v6[1] = 49408;
  v8 = 257;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  *((_DWORD *)v4 + 68) = 0;
  *v4 = &tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 70) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x1800271d0  mov     [rsp+arg_0], rbx
0x1800271d5  push    rdi
0x1800271d6  sub     rsp, 50h
0x1800271da  mov     rdi, rcx
0x1800271dd  mov     ecx, 120h; cb
0x1800271e2  call    cs:__imp_CoTaskMemAlloc
0x1800271e8  mov     rbx, rax
0x1800271eb  test    rax, rax
0x1800271ee  jz      loc_180027285
0x1800271f4  xor     ecx, ecx
0x1800271f6  mov     [rsp+58h+var_38], 3681FB4h
0x1800271fe  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180027205  mov     [rsp+58h+var_26], ecx
0x180027209  mov     [rbx], rax
0x18002720c  lea     r8, [rsp+58h+var_38]
0x180027211  lea     rax, aDeletesnapshot; "DeleteSnapshotCaptureTest"
0x180027218  mov     [rsp+58h+var_22], cx
0x18002721d  xorps   xmm0, xmm0
0x180027220  mov     [rsp+58h+var_10], rcx
0x180027225  lea     rcx, [rbx+8]
0x180027229  mov     [rsp+58h+var_30], rax
0x18002722e  mov     rdx, rbx
0x180027231  mov     [rsp+58h+var_34], 0C100h
0x180027239  mov     [rsp+58h+var_28], 101h
0x180027240  movdqu  [rsp+58h+var_20], xmm0
0x180027246  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18002724b  lea     rax, ??_7?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::`vftable'
0x180027252  mov     dword ptr [rbx+110h], 0
0x18002725c  mov     [rbx], rax
0x18002725f  lea     rax, [rbx+10h]
0x180027263  mov     [rbx+108h], rax
0x18002726a  mov     rax, rdi
0x18002726d  mov     dword ptr [rbx+118h], 1
0x180027277  mov     [rdi], rbx
0x18002727a  mov     rbx, [rsp+58h+arg_0]
0x18002727f  add     rsp, 50h
0x180027283  pop     rdi
0x180027284  retn
0x180027285  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
