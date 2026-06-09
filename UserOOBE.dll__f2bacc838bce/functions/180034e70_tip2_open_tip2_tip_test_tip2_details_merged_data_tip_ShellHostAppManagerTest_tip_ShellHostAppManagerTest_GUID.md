# tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>>(_GUID)

- ea: `0x180034e70`
- end: `0x180034ed1`
- name: `??$open@V?$tip_test@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@@0@U_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030fe4`
- `0x180037738`
- `0x180037be4`
- `0x180039840`
- `0x18003b130`
- `0x18003b320`
- `0x18003b6b0`

## callees

- `0x180007d14`
- `0x180034e70`
- `0x180035d5c`
- `0x180036e3c`
- `0x1800375b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034e8e`

## pseudocode

```c
_QWORD *__fastcall tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>>(
        _QWORD *a1,
        __int128 *a2)
{
  __int128 v2; // xmm0
  LPVOID v4; // rax
  wil::details::in1diag3 *v5; // rcx
  __int128 v7; // [rsp+20h] [rbp-18h] BYREF
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF

  v2 = *a2;
  *a1 = 0;
  v7 = v2;
  v4 = CoTaskMemAlloc(0x180u);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v5);
  v8 = tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>(
         v4,
         &v7);
  wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>::operator=(
    a1,
    &v8);
  wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>(&v8);
  return a1;
}

```

## disassembly

```asm
0x180034e70  push    rbx
0x180034e72  sub     rsp, 30h
0x180034e76  movaps  xmm0, xmmword ptr [rdx]
0x180034e79  mov     rbx, rcx
0x180034e7c  mov     qword ptr [rcx], 0
0x180034e83  mov     ecx, 180h; cb
0x180034e88  movdqa  [rsp+38h+var_18], xmm0
0x180034e8e  call    cs:__imp_CoTaskMemAlloc
0x180034e94  test    rax, rax
0x180034e97  jz      short loc_180034ECB
0x180034e99  lea     rdx, [rsp+38h+var_18]
0x180034e9e  mov     rcx, rax
0x180034ea1  call    ??0?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>(_GUID *)
0x180034ea6  lea     rdx, [rsp+38h+arg_0]
0x180034eab  mov     [rsp+38h+arg_0], rax
0x180034eb0  mov     rcx, rbx
0x180034eb3  call    ??4?$com_ptr_t@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy> &&)
0x180034eb8  lea     rcx, [rsp+38h+arg_0]
0x180034ebd  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>(void)
0x180034ec2  mov     rax, rbx
0x180034ec5  add     rsp, 30h
0x180034ec9  pop     rbx
0x180034eca  retn
0x180034ecb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
