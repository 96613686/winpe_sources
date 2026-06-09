# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x140005f54`
- end: `0x140005fa0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140003440`
- `0x140004aac`
- `0x140005c30`
- `0x14000759c`
- `0x14000925c`

## callees

- `0x140003138`
- `0x1400033a4`
- `0x1400035f0`
- `0x140005f54`

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
0x140005f54  mov     [rsp+arg_8], rbx
0x140005f59  mov     [rsp+arg_10], rsi
0x140005f5e  push    rdi
0x140005f5f  sub     rsp, 20h
0x140005f63  mov     rdi, [rcx]
0x140005f66  mov     rsi, rdx
0x140005f69  mov     rbx, rcx
0x140005f6c  test    rdi, rdi
0x140005f6f  jz      short loc_140005F8D
0x140005f71  lea     rcx, [rsp+28h+arg_0]; this
0x140005f76  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140005f7b  mov     rcx, rdi; this
0x140005f7e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140005f83  lea     rcx, [rsp+28h+arg_0]; this
0x140005f88  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140005f8d  mov     [rbx], rsi
0x140005f90  mov     rbx, [rsp+28h+arg_8]
0x140005f95  mov     rsi, [rsp+28h+arg_10]
0x140005f9a  add     rsp, 20h
0x140005f9e  pop     rdi
0x140005f9f  retn
```
