# Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_dynamic_initializer_for___force_initialization__

- ea: `0x140006590`
- end: `0x140006623`
- name: `Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140006590`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400065d5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400065d5`

## string_xrefs

- `0x1400065bc`: `Normal,ProcessId,ThreadId,ActivityId,Opcode,Timestamp,AppId,AppVer,ComposerId,EventName,ContainerId,ContainerType,SecurityId,BootId,AppSessionId,ShellId,RelatedActivityId,CorrelationVector,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0x12; ++i )
    {
      v2 = off_14001AE30[i];
      `Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001AE30[i];
      `Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140006590  mov     [rsp+arg_0], rbx
0x140006595  mov     [rsp+arg_8], rdi
0x14000659a  push    r14
0x14000659c  sub     rsp, 20h
0x1400065a0  cmp     cs:?value@?1??_initialized@_data_SelectorRoute@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_initialized(void)'::`2'::value
0x1400065a7  jnz     short loc_140006612
0x1400065a9  xor     edi, edi
0x1400065ab  lea     r14, cs:140000000h
0x1400065b2  xor     ebx, ebx
0x1400065b4  mov     rcx, ds:rva off_14001AE30[r14+rbx*8]; Str
0x1400065bc  lea     rax, rva ?storage@?1??_name_storage@_data_SelectorRoute@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Normal,ProcessId,ThreadId,ActivityId,Op"... ...
0x1400065c3  add     rax, rdi
0x1400065c6  lea     rdx, Control; "= \t\n"
0x1400065cd  mov     rva ?value@?1??_name_array@_data_SelectorRoute@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_name_array(void)'::`2'::value ...
0x1400065d5  call    cs:__imp_strcspn
0x1400065db  mov     rcx, ds:rva off_14001AE30[r14+rbx*8]; "Normal" ...
0x1400065e3  add     rax, rdi
0x1400065e6  mov     byte ptr [rax+r14+27CB0h], 0
0x1400065ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400065f3  inc     rax
0x1400065f6  cmp     byte ptr [rcx+rax], 0
0x1400065fa  jnz     short loc_1400065F3
0x1400065fc  inc     rdi
0x1400065ff  inc     rbx
0x140006602  add     rdi, rax
0x140006605  cmp     rbx, 12h
0x140006609  jb      short loc_1400065B4
0x14000660b  mov     cs:?value@?1??_initialized@_data_SelectorRoute@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_SelectorRoute::_initialized(void)'::`2'::value
0x140006612  mov     rbx, [rsp+28h+arg_0]
0x140006617  mov     rdi, [rsp+28h+arg_8]
0x14000661c  add     rsp, 20h
0x140006620  pop     r14
0x140006622  retn
```
