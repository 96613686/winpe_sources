# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x1400071bc`
- end: `0x140007208`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140003ee4`
- `0x14000404c`
- `0x14000437c`
- `0x1400070c8`

## callees

- `0x140001be0`
- `0x140001c64`
- `0x1400041b4`
- `0x1400071bc`

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
0x1400071bc  mov     [rsp+arg_8], rbx
0x1400071c1  mov     [rsp+arg_10], rsi
0x1400071c6  push    rdi
0x1400071c7  sub     rsp, 20h
0x1400071cb  mov     rdi, [rcx]
0x1400071ce  mov     rsi, rdx
0x1400071d1  mov     rbx, rcx
0x1400071d4  test    rdi, rdi
0x1400071d7  jz      short loc_1400071F5
0x1400071d9  lea     rcx, [rsp+28h+arg_0]; this
0x1400071de  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400071e3  mov     rcx, rdi; this
0x1400071e6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400071eb  lea     rcx, [rsp+28h+arg_0]; this
0x1400071f0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400071f5  mov     [rbx], rsi
0x1400071f8  mov     rbx, [rsp+28h+arg_8]
0x1400071fd  mov     rsi, [rsp+28h+arg_10]
0x140007202  add     rsp, 20h
0x140007206  pop     rdi
0x140007207  retn
```
