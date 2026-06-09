# Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_dynamic_initializer_for___force_initialization__

- ea: `0x140003960`
- end: `0x1400039f3`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003960`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400039a5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400039a5`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      v2 = off_1400197A0[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_1400197A0[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140003960  mov     [rsp+arg_0], rbx
0x140003965  mov     [rsp+arg_8], rdi
0x14000396a  push    r14
0x14000396c  sub     rsp, 20h
0x140003970  cmp     cs:?value@?1??_initialized@_data_DeserializeType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_initialized(void)'::`2'::value
0x140003977  jnz     short loc_1400039E2
0x140003979  xor     edi, edi
0x14000397b  lea     r14, cs:140000000h
0x140003982  xor     ebx, ebx
0x140003984  mov     rcx, ds:rva off_1400197A0[r14+rbx*8]; Str
0x14000398c  lea     rax, rva ?storage@?1??_name_storage@_data_DeserializeType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Required,Optional," ...
0x140003993  add     rax, rdi
0x140003996  lea     rdx, Control; "= \t\n"
0x14000399d  mov     rva ?value@?1??_name_array@_data_DeserializeType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_name_array(void)'::`2'::value ...
0x1400039a5  call    cs:__imp_strcspn
0x1400039ab  mov     rcx, ds:rva off_1400197A0[r14+rbx*8]; "Required" ...
0x1400039b3  add     rax, rdi
0x1400039b6  mov     byte ptr [rax+r14+27D80h], 0
0x1400039bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400039c3  inc     rax
0x1400039c6  cmp     byte ptr [rcx+rax], 0
0x1400039ca  jnz     short loc_1400039C3
0x1400039cc  inc     rdi
0x1400039cf  inc     rbx
0x1400039d2  add     rdi, rax
0x1400039d5  cmp     rbx, 2
0x1400039d9  jb      short loc_140003984
0x1400039db  mov     cs:?value@?1??_initialized@_data_DeserializeType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_DeserializeType::_initialized(void)'::`2'::value
0x1400039e2  mov     rbx, [rsp+28h+arg_0]
0x1400039e7  mov     rdi, [rsp+28h+arg_8]
0x1400039ec  add     rsp, 20h
0x1400039f0  pop     r14
0x1400039f2  retn
```
