# tip2::tip_test<tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>>::start(void)

- ea: `0x180045124`
- end: `0x1800451b8`
- name: `?start@?$tip_test@V?$merged_data@U_tip_EnergySaverToggleTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003fcf4`

## callees

- `0x180010010`
- `0x18003a350`
- `0x18003fe30`
- `0x1800403c4`
- `0x1800433ac`
- `0x1800450fc`
- `0x180045124`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004515f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004515f`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>>::start(
        __int64 *a1,
        __int64 a2)
{
  _QWORD *v2; // rax
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rax
  void *v8; // rcx
  void *v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_QWORD *)*a1;
  if ( *a1 && (v2[31] || (v2[9] & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>,wil::err_returncode_policy>::reset();
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x120u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>(v5);
    v8 = (void *)*a1;
    v10 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<1,0,0>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x180045124  mov     [rsp+arg_8], rbx
0x180045129  push    rdi
0x18004512a  sub     rsp, 20h
0x18004512e  mov     rax, [rcx]
0x180045131  mov     rdi, rdx
0x180045134  mov     rbx, rcx
0x180045137  test    rax, rax
0x18004513a  jz      short loc_180045154
0x18004513c  cmp     qword ptr [rax+0F8h], 0
0x180045144  jnz     short loc_18004514F
0x180045146  test    dword ptr [rax+48h], 100h
0x18004514d  jz      short loc_180045154
0x18004514f  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_EnergySaverToggleTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>,wil::err_returncode_policy>::reset(void)
0x180045154  cmp     qword ptr [rbx], 0
0x180045158  jnz     short loc_180045195
0x18004515a  mov     ecx, 120h; cb
0x18004515f  call    cs:__imp_CoTaskMemAlloc
0x180045165  test    rax, rax
0x180045168  jz      short loc_1800451B2
0x18004516a  mov     rcx, rax
0x18004516d  call    ??0?$merged_data@U_tip_EnergySaverToggleTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>(void)
0x180045172  mov     rcx, [rbx]; pv
0x180045175  mov     [rsp+28h+arg_0], 0
0x18004517e  mov     [rbx], rax
0x180045181  test    rcx, rcx
0x180045184  jz      short loc_18004518B
0x180045186  call    ?Release@?$merged_data@U_tip_EnergySaverToggleTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>::Release(void)
0x18004518b  lea     rcx, [rsp+28h+arg_0]
0x180045190  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EnergySaverToggleTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>,wil::err_returncode_policy>(void)
0x180045195  mov     rcx, [rbx]
0x180045198  mov     rdx, rdi
0x18004519b  add     rcx, 8
0x18004519f  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x1800451a4  mov     rbx, [rsp+28h+arg_8]
0x1800451a9  mov     rax, rdi
0x1800451ac  add     rsp, 20h
0x1800451b0  pop     rdi
0x1800451b1  retn
0x1800451b2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
