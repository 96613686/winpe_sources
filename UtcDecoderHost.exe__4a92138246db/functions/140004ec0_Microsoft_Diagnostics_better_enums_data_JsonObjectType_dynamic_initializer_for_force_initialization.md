# Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_dynamic_initializer_for___force_initialization__

- ea: `0x140004ec0`
- end: `0x140004f53`
- name: `Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004ec0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004f05`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004f05`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v2 = off_14001A500[i];
      `Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A500[i];
      `Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140004ec0  mov     [rsp+arg_0], rbx
0x140004ec5  mov     [rsp+arg_8], rdi
0x140004eca  push    r14
0x140004ecc  sub     rsp, 20h
0x140004ed0  cmp     cs:?value@?1??_initialized@_data_JsonObjectType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_initialized(void)'::`2'::value
0x140004ed7  jnz     short loc_140004F42
0x140004ed9  xor     edi, edi
0x140004edb  lea     r14, cs:140000000h
0x140004ee2  xor     ebx, ebx
0x140004ee4  mov     rcx, ds:rva off_14001A500[r14+rbx*8]; Str
0x140004eec  lea     rax, rva ?storage@?1??_name_storage@_data_JsonObjectType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Struct,Array,Map," ...
0x140004ef3  add     rax, rdi
0x140004ef6  lea     rdx, Control; "= \t\n"
0x140004efd  mov     rva ?value@?1??_name_array@_data_JsonObjectType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_name_array(void)'::`2'::value ...
0x140004f05  call    cs:__imp_strcspn
0x140004f0b  mov     rcx, ds:rva off_14001A500[r14+rbx*8]; "Struct" ...
0x140004f13  add     rax, rdi
0x140004f16  mov     byte ptr [rax+r14+28560h], 0
0x140004f1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004f23  inc     rax
0x140004f26  cmp     byte ptr [rcx+rax], 0
0x140004f2a  jnz     short loc_140004F23
0x140004f2c  inc     rdi
0x140004f2f  inc     rbx
0x140004f32  add     rdi, rax
0x140004f35  cmp     rbx, 3
0x140004f39  jb      short loc_140004EE4
0x140004f3b  mov     cs:?value@?1??_initialized@_data_JsonObjectType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_JsonObjectType::_initialized(void)'::`2'::value
0x140004f42  mov     rbx, [rsp+28h+arg_0]
0x140004f47  mov     rdi, [rsp+28h+arg_8]
0x140004f4c  add     rsp, 20h
0x140004f50  pop     r14
0x140004f52  retn
```
