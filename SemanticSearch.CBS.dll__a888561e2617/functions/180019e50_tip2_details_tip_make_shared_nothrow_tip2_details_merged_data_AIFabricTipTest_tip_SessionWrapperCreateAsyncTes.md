# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)

- ea: `0x180019e50`
- end: `0x180019f52`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `258`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`

## callees

- `0x180011960`
- `0x1800161b0`
- `0x180019e50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019e65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019e65`

## string_xrefs

- `0x180019e9e`: `SessionWrapperCreateAsyncTest`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  wil::details::in1diag3 *v3; // rcx
  _QWORD *v4; // rbx
  _QWORD *result; // rax
  __int128 v6; // [rsp+20h] [rbp-68h]
  __int128 v7; // [rsp+30h] [rbp-58h]
  _OWORD v8[3]; // [rsp+50h] [rbp-38h] BYREF

  v2 = CoTaskMemAlloc(0x130u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  *(_QWORD *)&v6 = 0xC10003A13586LL;
  *((_QWORD *)&v7 + 1) = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  *((_QWORD *)&v6 + 1) = "SessionWrapperCreateAsyncTest";
  LOWORD(v7) = 1;
  v8[0] = v6;
  v8[1] = v7;
  v8[2] = 0u;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v8);
  *(_OWORD *)(v4 + 33) = 0;
  v4[35] = 0;
  v4[36] = 7;
  *((_WORD *)v4 + 132) = 0;
  *v4 = &tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::`vftable';
  v4[32] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 74) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180019e50  mov     [rsp+arg_8], rbx
0x180019e55  push    rdi
0x180019e56  sub     rsp, 80h
0x180019e5d  mov     rdi, rcx
0x180019e60  mov     ecx, 130h; cb
0x180019e65  call    cs:__imp_CoTaskMemAlloc
0x180019e6b  mov     rbx, rax
0x180019e6e  test    rax, rax
0x180019e71  jz      loc_180019F4C
0x180019e77  xorps   xmm0, xmm0
0x180019e7a  mov     dword ptr [rsp+88h+var_68], 3A13586h
0x180019e82  movdqu  [rsp+88h+var_58+8], xmm0
0x180019e88  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180019e8f  mov     dword ptr [rsp+88h+var_68+4], 0C100h
0x180019e97  mov     [rbx], rax
0x180019e9a  lea     rcx, [rbx+8]
0x180019e9e  lea     rax, aSessionwrapper; "SessionWrapperCreateAsyncTest"
0x180019ea5  mov     [rsp+88h+arg_0], rsi
0x180019ead  mov     qword ptr [rsp+88h+var_68+8], rax
0x180019eb2  lea     r8, [rsp+88h+var_38]
0x180019eb7  movups  xmm0, [rsp+88h+var_68]
0x180019ebc  xor     esi, esi
0x180019ebe  mov     word ptr [rsp+88h+var_58], 1
0x180019ec5  movups  xmm1, [rsp+88h+var_58]
0x180019eca  mov     [rsp+88h+var_40], rsi
0x180019ecf  mov     rdx, rbx
0x180019ed2  movups  [rsp+88h+var_38], xmm0
0x180019ed7  movups  xmm0, xmmword ptr [rsp+40h]
0x180019edc  movups  [rsp+88h+var_28], xmm1
0x180019ee1  movups  [rsp+88h+var_18], xmm0
0x180019ee6  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180019eeb  lea     rax, ??_7?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::`vftable'
0x180019ef2  xorps   xmm0, xmm0
0x180019ef5  movups  xmmword ptr [rbx+108h], xmm0
0x180019efc  mov     [rbx+118h], rsi
0x180019f03  mov     qword ptr [rbx+120h], 7
0x180019f0e  mov     [rbx+108h], si
0x180019f15  mov     rsi, [rsp+88h+arg_0]
0x180019f1d  mov     [rbx], rax
0x180019f20  lea     rax, [rbx+10h]
0x180019f24  mov     [rbx+100h], rax
0x180019f2b  mov     rax, rdi
0x180019f2e  mov     dword ptr [rbx+128h], 1
0x180019f38  mov     [rdi], rbx
0x180019f3b  mov     rbx, [rsp+88h+arg_8]
0x180019f43  add     rsp, 80h
0x180019f4a  pop     rdi
0x180019f4b  retn
0x180019f4c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
