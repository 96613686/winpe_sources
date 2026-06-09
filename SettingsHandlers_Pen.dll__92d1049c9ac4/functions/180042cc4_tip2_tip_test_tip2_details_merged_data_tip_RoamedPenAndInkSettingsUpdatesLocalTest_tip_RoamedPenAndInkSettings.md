# tip2::tip_test<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::start(void)

- ea: `0x180042cc4`
- end: `0x180042d58`
- name: `?start@?$tip_test@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ddb0`

## callees

- `0x18000bb40`
- `0x18003e364`
- `0x18003ec40`
- `0x1800407f4`
- `0x180042228`
- `0x180042b14`
- `0x180042cc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042cff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042cff`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::start(
        __int64 *a1,
        __int64 a2)
{
  _QWORD *v2; // rax
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rax
  void *v8; // rcx
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_QWORD *)*a1;
  if ( *a1 && (v2[31] || (v2[9] & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>,wil::err_returncode_policy>::reset();
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x148u);
    if ( !v5 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>(v5);
    v8 = (void *)*a1;
    v10 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<0,0,0>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x180042cc4  mov     [rsp+arg_8], rbx
0x180042cc9  push    rdi
0x180042cca  sub     rsp, 20h
0x180042cce  mov     rax, [rcx]
0x180042cd1  mov     rdi, rdx
0x180042cd4  mov     rbx, rcx
0x180042cd7  test    rax, rax
0x180042cda  jz      short loc_180042CF4
0x180042cdc  cmp     qword ptr [rax+0F8h], 0
0x180042ce4  jnz     short loc_180042CEF
0x180042ce6  test    dword ptr [rax+48h], 100h
0x180042ced  jz      short loc_180042CF4
0x180042cef  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>,wil::err_returncode_policy>::reset(void)
0x180042cf4  cmp     qword ptr [rbx], 0
0x180042cf8  jnz     short loc_180042D35
0x180042cfa  mov     ecx, 148h; cb
0x180042cff  call    cs:__imp_CoTaskMemAlloc
0x180042d05  test    rax, rax
0x180042d08  jz      short loc_180042D52
0x180042d0a  mov     rcx, rax
0x180042d0d  call    ??0?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>(void)
0x180042d12  mov     rcx, [rbx]; pv
0x180042d15  mov     [rsp+28h+arg_0], 0
0x180042d1e  mov     [rbx], rax
0x180042d21  test    rcx, rcx
0x180042d24  jz      short loc_180042D2B
0x180042d26  call    ?Release@?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>::Release(void)
0x180042d2b  lea     rcx, [rsp+28h+arg_0]
0x180042d30  call    ??1?$com_ptr_t@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>,wil::err_returncode_policy>(void)
0x180042d35  mov     rcx, [rbx]
0x180042d38  mov     rdx, rdi
0x180042d3b  add     rcx, 8
0x180042d3f  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180042d44  mov     rbx, [rsp+28h+arg_8]
0x180042d49  mov     rax, rdi
0x180042d4c  add     rsp, 20h
0x180042d50  pop     rdi
0x180042d51  retn
0x180042d52  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
