# Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_dynamic_initializer_for___force_initialization__

- ea: `0x140003690`
- end: `0x1400036d2`
- name: `Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_dynamic_initializer_for___force_initialization__`
- size: `66`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003690`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400036bb`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400036bb`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_dynamic_initializer_for___force_initialization__()
{
  size_t v0; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_initialized'::`2'::value )
  {
    `Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_name_array'::`2'::value = (__int64)`Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_name_storage'::`2'::storage;
    v0 = strcspn("DScript", "= \t\n");
    `Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_initialized'::`2'::value = 1;
    `Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_name_storage'::`2'::storage[v0] = 0;
  }
}

```

## disassembly

```asm
0x140003690  push    rbx
0x140003692  sub     rsp, 20h
0x140003696  cmp     cs:?value@?1??_initialized@_data_ConfigurationType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_initialized(void)'::`2'::value
0x14000369d  jnz     short loc_1400036CC
0x14000369f  mov     rcx, cs:off_14001A288; Str
0x1400036a6  lea     rbx, ?storage@?1??_name_storage@_data_ConfigurationType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA; "DScript,"
0x1400036ad  lea     rdx, Control; "= \t\n"
0x1400036b4  mov     cs:?value@?1??_name_array@_data_ConfigurationType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA, rbx; char const * near * `Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_name_array(void)'::`2'::value
0x1400036bb  call    cs:__imp_strcspn
0x1400036c1  mov     cs:?value@?1??_initialized@_data_ConfigurationType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_initialized(void)'::`2'::value
0x1400036c8  mov     byte ptr [rax+rbx], 0
0x1400036cc  add     rsp, 20h
0x1400036d0  pop     rbx
0x1400036d1  retn
```
