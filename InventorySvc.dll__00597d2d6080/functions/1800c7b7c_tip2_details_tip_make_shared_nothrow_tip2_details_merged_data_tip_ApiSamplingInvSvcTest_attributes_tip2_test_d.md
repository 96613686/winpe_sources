# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>,>(void)

- ea: `0x1800c7b7c`
- end: `0x1800c7ce3`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c7cec`

## callees

- `0x1800108c4`
- `0x1800c7b7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800c7c62`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800c7c62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c7b93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c7b93`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx

  v3 = (char *)CoTaskMemAlloc(0x158u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  *(_QWORD *)v3 = &tip2::details::test_data_interface::`vftable';
  *((_QWORD *)v3 + 1) = v3;
  *((_QWORD *)v3 + 2) = 0;
  *((_DWORD *)v3 + 18) = 0;
  *((_QWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 11) = 0;
  *((_QWORD *)v3 + 12) = 0;
  *((_QWORD *)v3 + 13) = 0;
  *((_QWORD *)v3 + 14) = 0;
  *((_QWORD *)v3 + 15) = 0;
  *((_QWORD *)v3 + 16) = 0;
  *((_QWORD *)v3 + 17) = 0;
  *((_QWORD *)v3 + 18) = 0;
  *(_OWORD *)(v3 + 152) = 0;
  v3[168] = 0;
  *((_WORD *)v3 + 85) = -1;
  *((_QWORD *)v3 + 22) = 0;
  *((_QWORD *)v3 + 23) = 0;
  *((_DWORD *)v3 + 48) = 0;
  *((_DWORD *)v3 + 60) = 0;
  *((_QWORD *)v3 + 31) = 0;
  *((_DWORD *)v3 + 6) = 53713941;
  *((_DWORD *)v3 + 7) = 180544;
  *((_QWORD *)v3 + 4) = "ApiSamplingInvSvcTest";
  *((_WORD *)v3 + 20) = 1;
  *(_DWORD *)(v3 + 42) = 0;
  *((_WORD *)v3 + 23) = 0;
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  *((_QWORD *)v3 + 33) = 0;
  *((_QWORD *)v3 + 34) = 0;
  *((_QWORD *)v3 + 35) = 0;
  *((_QWORD *)v3 + 36) = 0;
  *((_QWORD *)v3 + 37) = 0;
  *((_QWORD *)v3 + 38) = 0;
  *((_QWORD *)v3 + 39) = 0;
  *((_QWORD *)v3 + 40) = 0;
  *((_QWORD *)v3 + 41) = 0;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::`vftable';
  *((_DWORD *)v3 + 84) = 1;
  *((_QWORD *)v3 + 32) = v3 + 16;
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x1800c7b7c  mov     [rsp+arg_0], rbx
0x1800c7b81  mov     [rsp+arg_8], rsi
0x1800c7b86  push    rdi
0x1800c7b87  sub     rsp, 20h
0x1800c7b8b  mov     rdi, rcx
0x1800c7b8e  mov     ecx, 158h; cb
0x1800c7b93  call    cs:__imp_CoTaskMemAlloc
0x1800c7b99  mov     rbx, rax
0x1800c7b9c  xor     esi, esi
0x1800c7b9e  test    rax, rax
0x1800c7ba1  jz      loc_1800C7CDD
0x1800c7ba7  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800c7bae  mov     [rbx], rax
0x1800c7bb1  lea     rdx, aApisamplinginv; "ApiSamplingInvSvcTest"
0x1800c7bb8  xor     r8d, r8d
0x1800c7bbb  mov     [rbx+8], rbx
0x1800c7bbf  mov     [rbx+10h], rsi
0x1800c7bc3  mov     [rbx+48h], esi
0x1800c7bc6  mov     [rbx+50h], rsi
0x1800c7bca  mov     [rbx+58h], rsi
0x1800c7bce  mov     [rbx+60h], rsi
0x1800c7bd2  mov     [rbx+68h], rsi
0x1800c7bd6  mov     [rbx+70h], rsi
0x1800c7bda  mov     [rbx+78h], rsi
0x1800c7bde  mov     [rbx+80h], rsi
0x1800c7be5  mov     [rbx+88h], rsi
0x1800c7bec  mov     [rbx+90h], rsi
0x1800c7bf3  xorps   xmm0, xmm0
0x1800c7bf6  movups  xmmword ptr [rbx+98h], xmm0
0x1800c7bfd  mov     [rbx+0A8h], sil
0x1800c7c04  mov     word ptr [rbx+0AAh], 0FFFFh
0x1800c7c0d  mov     [rbx+0B0h], rsi
0x1800c7c14  mov     [rbx+0B8h], rsi
0x1800c7c1b  mov     [rbx+0C0h], esi
0x1800c7c21  mov     [rbx+0F0h], esi
0x1800c7c27  mov     [rbx+0F8h], rsi
0x1800c7c2e  mov     dword ptr [rbx+18h], 3339C15h
0x1800c7c35  mov     dword ptr [rbx+1Ch], 2C140h
0x1800c7c3c  mov     [rbx+20h], rdx
0x1800c7c40  mov     word ptr [rbx+28h], 1
0x1800c7c46  mov     [rbx+2Ah], r8d
0x1800c7c4a  mov     [rbx+2Eh], r8w
0x1800c7c4f  mov     [rbx+30h], rsi
0x1800c7c53  mov     [rbx+38h], rsi
0x1800c7c57  mov     [rbx+40h], rsi
0x1800c7c5b  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800c7c62  call    cs:__imp_InitializeCriticalSection
0x1800c7c68  nop
0x1800c7c69  mov     [rbx+108h], rsi
0x1800c7c70  mov     [rbx+110h], rsi
0x1800c7c77  mov     [rbx+118h], rsi
0x1800c7c7e  mov     [rbx+120h], rsi
0x1800c7c85  mov     [rbx+128h], rsi
0x1800c7c8c  mov     [rbx+130h], rsi
0x1800c7c93  mov     [rbx+138h], rsi
0x1800c7c9a  mov     [rbx+140h], rsi
0x1800c7ca1  mov     [rbx+148h], rsi
0x1800c7ca8  lea     rax, ??_7?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@6B@; const tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::`vftable'
0x1800c7caf  mov     [rbx], rax
0x1800c7cb2  mov     dword ptr [rbx+150h], 1
0x1800c7cbc  lea     rax, [rbx+10h]
0x1800c7cc0  mov     [rbx+100h], rax
0x1800c7cc7  mov     [rdi], rbx
0x1800c7cca  mov     rax, rdi
0x1800c7ccd  mov     rbx, [rsp+28h+arg_0]
0x1800c7cd2  mov     rsi, [rsp+28h+arg_8]
0x1800c7cd7  add     rsp, 20h
0x1800c7cdb  pop     rdi
0x1800c7cdc  retn
0x1800c7cdd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
