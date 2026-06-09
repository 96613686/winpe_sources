# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x140007508`
- end: `0x140007554`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140003478`
- `0x1400035e4`
- `0x14000392c`
- `0x140007318`

## callees

- `0x140002d14`
- `0x1400032a8`
- `0x140003750`
- `0x140007508`

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
0x140007508  mov     [rsp+arg_8], rbx
0x14000750d  mov     [rsp+arg_10], rsi
0x140007512  push    rdi
0x140007513  sub     rsp, 20h
0x140007517  mov     rdi, [rcx]
0x14000751a  mov     rsi, rdx
0x14000751d  mov     rbx, rcx
0x140007520  test    rdi, rdi
0x140007523  jz      short loc_140007541
0x140007525  lea     rcx, [rsp+28h+arg_0]; this
0x14000752a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000752f  mov     rcx, rdi; this
0x140007532  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140007537  lea     rcx, [rsp+28h+arg_0]; this
0x14000753c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140007541  mov     [rbx], rsi
0x140007544  mov     rbx, [rsp+28h+arg_8]
0x140007549  mov     rsi, [rsp+28h+arg_10]
0x14000754e  add     rsp, 20h
0x140007552  pop     rdi
0x140007553  retn
```
