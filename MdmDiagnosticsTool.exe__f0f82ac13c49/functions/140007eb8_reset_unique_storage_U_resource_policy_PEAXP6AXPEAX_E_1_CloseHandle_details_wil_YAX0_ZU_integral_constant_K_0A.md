# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x140007eb8`
- end: `0x140007f04`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400037d0`
- `0x140005a1c`
- `0x1400079bc`

## callees

- `0x140003174`
- `0x14000358c`
- `0x140003980`
- `0x140007eb8`

## pseudocode

```c
void __fastcall _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        wil::details **a1,
        wil::details *a2)
{
  wil::details *v2; // rdi
  void *v5; // rdx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v6);
    wil::details::CloseHandle(v2, v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v6);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x140007eb8  mov     [rsp+arg_8], rbx
0x140007ebd  mov     [rsp+arg_10], rsi
0x140007ec2  push    rdi
0x140007ec3  sub     rsp, 20h
0x140007ec7  mov     rdi, [rcx]
0x140007eca  mov     rsi, rdx
0x140007ecd  mov     rbx, rcx
0x140007ed0  test    rdi, rdi
0x140007ed3  jz      short loc_140007EF1
0x140007ed5  lea     rcx, [rsp+28h+arg_0]; this
0x140007eda  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140007edf  mov     rcx, rdi; this
0x140007ee2  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140007ee7  lea     rcx, [rsp+28h+arg_0]; this
0x140007eec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140007ef1  mov     [rbx], rsi
0x140007ef4  mov     rbx, [rsp+28h+arg_8]
0x140007ef9  mov     rsi, [rsp+28h+arg_10]
0x140007efe  add     rsp, 20h
0x140007f02  pop     rdi
0x140007f03  retn
```
