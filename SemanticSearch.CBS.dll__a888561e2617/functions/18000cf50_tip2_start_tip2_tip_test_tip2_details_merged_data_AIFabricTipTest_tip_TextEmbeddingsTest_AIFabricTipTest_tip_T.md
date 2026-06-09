# tip2::start<tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>>>(void)

- ea: `0x18000cf50`
- end: `0x18000d049`
- name: `??$start@V?$tip_test@V?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@@0@XZ`
- size: `249`
- prototype: `void **__fastcall(void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000afa0`
- `0x18000b2a0`

## callees

- `0x18000cf50`
- `0x18000fc60`
- `0x180010050`
- `0x180011960`
- `0x1800161b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cf6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cf6c`

## pseudocode

```c
void **__fastcall tip2::start<tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>>>(
        void **a1)
{
  _QWORD *v2; // rax
  wil::details::in1diag3 *v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rcx
  __int128 v7; // [rsp+20h] [rbp-78h]
  __int128 v8; // [rsp+30h] [rbp-68h]
  _OWORD v9[3]; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v10[24]; // [rsp+80h] [rbp-18h] BYREF

  *a1 = 0;
  v2 = CoTaskMemAlloc(0x110u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  *(_QWORD *)&v7 = 0xC10002A85433LL;
  *((_QWORD *)&v8 + 1) = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  LOWORD(v8) = 1;
  *((_QWORD *)&v7 + 1) = "TextEmbeddingsTest";
  v9[1] = v8;
  v9[0] = v7;
  v9[2] = 0u;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v9);
  *((_DWORD *)v4 + 66) = 1;
  *v4 = &tip2::details::merged_data<AIFabricTipTest::_tip_ImageEmbeddingsTest,AIFabricTipTest::_tip_ImageEmbeddingsTest>::`vftable';
  v4[32] = v4 + 2;
  v5 = *a1;
  *a1 = v4;
  if ( v5 )
    tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(v5);
  tip2::details::shared_data<0,0,0>::start((char *)*a1 + 8, v10);
  return a1;
}

```

## disassembly

```asm
0x18000cf50  mov     [rsp+arg_8], rbx
0x18000cf55  push    rdi
0x18000cf56  sub     rsp, 90h
0x18000cf5d  mov     rbx, rcx
0x18000cf60  mov     qword ptr [rcx], 0
0x18000cf67  mov     ecx, 110h; cb
0x18000cf6c  call    cs:__imp_CoTaskMemAlloc
0x18000cf72  mov     rdi, rax
0x18000cf75  test    rax, rax
0x18000cf78  jz      loc_18000D043
0x18000cf7e  xorps   xmm0, xmm0
0x18000cf81  mov     dword ptr [rsp+98h+var_78], 2A85433h
0x18000cf89  movdqu  [rsp+98h+var_68+8], xmm0
0x18000cf8f  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18000cf96  mov     dword ptr [rsp+98h+var_78+4], 0C100h
0x18000cf9e  mov     [rdi], rax
0x18000cfa1  lea     rcx, [rdi+8]
0x18000cfa5  lea     rax, aTextembeddings; "TextEmbeddingsTest"
0x18000cfac  mov     word ptr [rsp+98h+var_68], 1
0x18000cfb3  movups  xmm1, [rsp+98h+var_68]
0x18000cfb8  mov     qword ptr [rsp+98h+var_78+8], rax
0x18000cfbd  lea     r8, [rsp+98h+var_48]
0x18000cfc2  movups  xmm0, [rsp+98h+var_78]
0x18000cfc7  mov     [rsp+98h+var_50], 0
0x18000cfd0  mov     rdx, rdi
0x18000cfd3  movups  [rsp+98h+var_38], xmm1
0x18000cfd8  movups  [rsp+98h+var_48], xmm0
0x18000cfdd  movups  xmm0, xmmword ptr [rsp+40h]
0x18000cfe2  movups  [rsp+98h+var_28], xmm0
0x18000cfe7  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18000cfec  lea     rax, ??_7?$merged_data@U_tip_ImageEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AIFabricTipTest::_tip_ImageEmbeddingsTest,AIFabricTipTest::_tip_ImageEmbeddingsTest>::`vftable'
0x18000cff3  mov     dword ptr [rdi+108h], 1
0x18000cffd  mov     [rdi], rax
0x18000d000  lea     rax, [rdi+10h]
0x18000d004  mov     [rdi+100h], rax
0x18000d00b  mov     rcx, [rbx]; pv
0x18000d00e  mov     [rbx], rdi
0x18000d011  test    rcx, rcx
0x18000d014  jz      short loc_18000D01B
0x18000d016  call    ?Release@?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(void)
0x18000d01b  mov     rcx, [rbx]
0x18000d01e  lea     rdx, [rsp+98h+var_18]
0x18000d026  add     rcx, 8
0x18000d02a  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18000d02f  mov     rax, rbx
0x18000d032  mov     rbx, [rsp+98h+arg_8]
0x18000d03a  add     rsp, 90h
0x18000d041  pop     rdi
0x18000d042  retn
0x18000d043  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
