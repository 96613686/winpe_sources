# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x1400098b8`
- end: `0x140009904`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400052f8`
- `0x140005464`
- `0x1400057ac`
- `0x14000966c`

## callees

- `0x140004d20`
- `0x1400050ac`
- `0x1400055d0`
- `0x1400098b8`

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
0x1400098b8  mov     [rsp+arg_8], rbx
0x1400098bd  mov     [rsp+arg_10], rsi
0x1400098c2  push    rdi
0x1400098c3  sub     rsp, 20h
0x1400098c7  mov     rdi, [rcx]
0x1400098ca  mov     rsi, rdx
0x1400098cd  mov     rbx, rcx
0x1400098d0  test    rdi, rdi
0x1400098d3  jz      short loc_1400098F1
0x1400098d5  lea     rcx, [rsp+28h+arg_0]; this
0x1400098da  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400098df  mov     rcx, rdi; this
0x1400098e2  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400098e7  lea     rcx, [rsp+28h+arg_0]; this
0x1400098ec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400098f1  mov     [rbx], rsi
0x1400098f4  mov     rbx, [rsp+28h+arg_8]
0x1400098f9  mov     rsi, [rsp+28h+arg_10]
0x1400098fe  add     rsp, 20h
0x140009902  pop     rdi
0x140009903  retn
```
