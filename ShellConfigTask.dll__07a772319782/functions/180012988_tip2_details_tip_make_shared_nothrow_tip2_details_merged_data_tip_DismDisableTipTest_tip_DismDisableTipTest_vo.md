# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>,>(void)

- ea: `0x180012988`
- end: `0x180012a43`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `187`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022104`

## callees

- `0x18000c5c4`
- `0x180012988`
- `0x180012f30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001299a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001299a`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>,>(
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
  v6[0] = 54221463;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "DismDisableTipTest";
  v6[1] = 49408;
  v8 = 257;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  *((_DWORD *)v4 + 68) = 1;
  *v4 = &tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 70) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180012988  mov     [rsp+arg_0], rbx
0x18001298d  push    rdi
0x18001298e  sub     rsp, 50h
0x180012992  mov     rdi, rcx
0x180012995  mov     ecx, 120h; cb
0x18001299a  call    cs:__imp_CoTaskMemAlloc
0x1800129a0  mov     rbx, rax
0x1800129a3  test    rax, rax
0x1800129a6  jz      loc_180012A3D
0x1800129ac  xor     ecx, ecx
0x1800129ae  mov     [rsp+58h+var_38], 33B5A97h
0x1800129b6  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800129bd  mov     [rsp+58h+var_26], ecx
0x1800129c1  mov     [rbx], rax
0x1800129c4  lea     r8, [rsp+58h+var_38]
0x1800129c9  lea     rax, aDismdisabletip; "DismDisableTipTest"
0x1800129d0  mov     [rsp+58h+var_22], cx
0x1800129d5  xorps   xmm0, xmm0
0x1800129d8  mov     [rsp+58h+var_10], rcx
0x1800129dd  lea     rcx, [rbx+8]
0x1800129e1  mov     [rsp+58h+var_30], rax
0x1800129e6  mov     rdx, rbx
0x1800129e9  mov     [rsp+58h+var_34], 0C100h
0x1800129f1  mov     [rsp+58h+var_28], 101h
0x1800129f8  movdqu  [rsp+58h+var_20], xmm0
0x1800129fe  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180012a03  lea     rax, ??_7?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::`vftable'
0x180012a0a  mov     dword ptr [rbx+110h], 1
0x180012a14  mov     [rbx], rax
0x180012a17  lea     rax, [rbx+10h]
0x180012a1b  mov     [rbx+108h], rax
0x180012a22  mov     rax, rdi
0x180012a25  mov     dword ptr [rbx+118h], 1
0x180012a2f  mov     [rdi], rbx
0x180012a32  mov     rbx, [rsp+58h+arg_0]
0x180012a37  add     rsp, 50h
0x180012a3b  pop     rdi
0x180012a3c  retn
0x180012a3d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
