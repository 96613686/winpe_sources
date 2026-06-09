# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x1800116a0`
- end: `0x1800116ec`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000fc40`
- `0x180010d80`
- `0x180011634`

## callees

- `0x18000dea4`
- `0x18000df24`
- `0x18000fe0c`
- `0x1800116a0`

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
0x1800116a0  mov     [rsp+arg_8], rbx
0x1800116a5  mov     [rsp+arg_10], rsi
0x1800116aa  push    rdi
0x1800116ab  sub     rsp, 20h
0x1800116af  mov     rdi, [rcx]
0x1800116b2  mov     rsi, rdx
0x1800116b5  mov     rbx, rcx
0x1800116b8  test    rdi, rdi
0x1800116bb  jz      short loc_1800116D9
0x1800116bd  lea     rcx, [rsp+28h+arg_0]; this
0x1800116c2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800116c7  mov     rcx, rdi; this
0x1800116ca  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800116cf  lea     rcx, [rsp+28h+arg_0]; this
0x1800116d4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800116d9  mov     [rbx], rsi
0x1800116dc  mov     rbx, [rsp+28h+arg_8]
0x1800116e1  mov     rsi, [rsp+28h+arg_10]
0x1800116e6  add     rsp, 20h
0x1800116ea  pop     rdi
0x1800116eb  retn
```
