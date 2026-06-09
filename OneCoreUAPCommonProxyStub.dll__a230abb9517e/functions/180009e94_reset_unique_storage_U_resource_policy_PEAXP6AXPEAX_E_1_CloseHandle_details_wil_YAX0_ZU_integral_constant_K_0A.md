# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180009e94`
- end: `0x180009ee0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007778`
- `0x180008c1c`
- `0x180009d50`

## callees

- `0x180007258`
- `0x18000764c`
- `0x180007914`
- `0x180009e94`

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
0x180009e94  mov     [rsp+arg_8], rbx
0x180009e99  mov     [rsp+arg_10], rsi
0x180009e9e  push    rdi
0x180009e9f  sub     rsp, 20h
0x180009ea3  mov     rdi, [rcx]
0x180009ea6  mov     rsi, rdx
0x180009ea9  mov     rbx, rcx
0x180009eac  test    rdi, rdi
0x180009eaf  jz      short loc_180009ECD
0x180009eb1  lea     rcx, [rsp+28h+arg_0]; this
0x180009eb6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009ebb  mov     rcx, rdi; this
0x180009ebe  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180009ec3  lea     rcx, [rsp+28h+arg_0]; this
0x180009ec8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009ecd  mov     [rbx], rsi
0x180009ed0  mov     rbx, [rsp+28h+arg_8]
0x180009ed5  mov     rsi, [rsp+28h+arg_10]
0x180009eda  add     rsp, 20h
0x180009ede  pop     rdi
0x180009edf  retn
```
