# Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_dynamic_initializer_for___force_initialization__

- ea: `0x140003d40`
- end: `0x140003dd3`
- name: `Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003d40`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003d85`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003d85`

## string_xrefs

- `0x140003d6c`: `InCode,Registry,OneSettings,None,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 4; ++i )
    {
      v2 = off_14001A850[i];
      `Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A850[i];
      `Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140003d40  mov     [rsp+arg_0], rbx
0x140003d45  mov     [rsp+arg_8], rdi
0x140003d4a  push    r14
0x140003d4c  sub     rsp, 20h
0x140003d50  cmp     cs:?value@?1??_initialized@_data_DynamicConfigInitOrder@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_initialized(void)'::`2'::value
0x140003d57  jnz     short loc_140003DC2
0x140003d59  xor     edi, edi
0x140003d5b  lea     r14, cs:140000000h
0x140003d62  xor     ebx, ebx
0x140003d64  mov     rcx, ds:rva off_14001A850[r14+rbx*8]; Str
0x140003d6c  lea     rax, rva ?storage@?1??_name_storage@_data_DynamicConfigInitOrder@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "InCode,Registry,OneSettings,None," ...
0x140003d73  add     rax, rdi
0x140003d76  lea     rdx, Control; "= \t\n"
0x140003d7d  mov     rva ?value@?1??_name_array@_data_DynamicConfigInitOrder@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_name_array(void)'::`2'::value ...
0x140003d85  call    cs:__imp_strcspn
0x140003d8b  mov     rcx, ds:rva off_14001A850[r14+rbx*8]; "InCode" ...
0x140003d93  add     rax, rdi
0x140003d96  mov     byte ptr [rax+r14+25B60h], 0
0x140003d9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003da3  inc     rax
0x140003da6  cmp     byte ptr [rcx+rax], 0
0x140003daa  jnz     short loc_140003DA3
0x140003dac  inc     rdi
0x140003daf  inc     rbx
0x140003db2  add     rdi, rax
0x140003db5  cmp     rbx, 4
0x140003db9  jb      short loc_140003D64
0x140003dbb  mov     cs:?value@?1??_initialized@_data_DynamicConfigInitOrder@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_DynamicConfigInitOrder::_initialized(void)'::`2'::value
0x140003dc2  mov     rbx, [rsp+28h+arg_0]
0x140003dc7  mov     rdi, [rsp+28h+arg_8]
0x140003dcc  add     rsp, 20h
0x140003dd0  pop     r14
0x140003dd2  retn
```
