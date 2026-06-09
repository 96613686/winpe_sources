# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>,>(void)

- ea: `0x1800da3f8`
- end: `0x1800da4a9`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_BrightnessOpenMonitorHandleTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_BrightnessOpenMonitorHandleTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800dc704`

## callees

- `0x18000f8a0`
- `0x18006c93c`
- `0x1800da3f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da40a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da40a`

## string_xrefs

- `0x1800da426`: `BrightnessOpenMonitorHandleTest`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  _DWORD *v3; // rbx
  _QWORD *result; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v6; // [rsp+28h] [rbp-30h]
  __int16 v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+32h] [rbp-26h]
  __int16 v9; // [rsp+36h] [rbp-22h]
  __int128 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  v3 = CoTaskMemAlloc(0x118u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  v5[0] = 39452890;
  v8 = 0;
  v6 = "BrightnessOpenMonitorHandleTest";
  v9 = 0;
  v11 = 0;
  *(_QWORD *)v3 = &tip2::details::test_data_interface::`vftable';
  v5[1] = 49408;
  v7 = 1;
  v10 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(v3 + 2, v3, v5);
  v3[68] = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 4;
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x1800da3f8  mov     [rsp+arg_0], rbx
0x1800da3fd  push    rdi
0x1800da3fe  sub     rsp, 50h
0x1800da402  mov     rdi, rcx
0x1800da405  mov     ecx, 118h; cb
0x1800da40a  call    cs:__imp_CoTaskMemAlloc
0x1800da410  mov     rbx, rax
0x1800da413  test    rax, rax
0x1800da416  jz      loc_1800DA4A3
0x1800da41c  xor     edx, edx
0x1800da41e  mov     [rsp+58h+var_38], 25A00DAh
0x1800da426  lea     rcx, aBrightnessopen; "BrightnessOpenMonitorHandleTest"
0x1800da42d  mov     [rsp+58h+var_26], edx
0x1800da431  mov     [rsp+58h+var_30], rcx
0x1800da436  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800da43d  mov     [rsp+58h+var_22], dx
0x1800da442  lea     rcx, [rbx+8]
0x1800da446  mov     [rsp+58h+var_10], rdx
0x1800da44b  lea     r8, [rsp+58h+var_38]
0x1800da450  xorps   xmm0, xmm0
0x1800da453  mov     [rbx], rax
0x1800da456  mov     rdx, rbx
0x1800da459  mov     [rsp+58h+var_34], 0C100h
0x1800da461  mov     [rsp+58h+var_28], 1
0x1800da468  movdqu  [rsp+58h+var_20], xmm0
0x1800da46e  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x1800da473  lea     rax, ??_7?$merged_data@U_tip_BrightnessOpenMonitorHandleTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@6B@; const tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>::`vftable'
0x1800da47a  mov     dword ptr [rbx+110h], 1
0x1800da484  mov     [rbx], rax
0x1800da487  lea     rax, [rbx+10h]
0x1800da48b  mov     [rbx+108h], rax
0x1800da492  mov     rax, rdi
0x1800da495  mov     [rdi], rbx
0x1800da498  mov     rbx, [rsp+58h+arg_0]
0x1800da49d  add     rsp, 50h
0x1800da4a1  pop     rdi
0x1800da4a2  retn
0x1800da4a3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
