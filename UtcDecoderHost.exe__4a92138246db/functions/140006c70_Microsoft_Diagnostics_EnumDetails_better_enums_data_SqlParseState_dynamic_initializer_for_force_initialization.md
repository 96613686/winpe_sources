# Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_dynamic_initializer_for___force_initialization__

- ea: `0x140006c70`
- end: `0x140006d03`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140006c70`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006cb5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006cb5`

## string_xrefs

- `0x140006c9c`: `New,Exists,Delete,Ignore,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 4; ++i )
    {
      v2 = off_140019A80[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019A80[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140006c70  mov     [rsp+arg_0], rbx
0x140006c75  mov     [rsp+arg_8], rdi
0x140006c7a  push    r14
0x140006c7c  sub     rsp, 20h
0x140006c80  cmp     cs:?value@?1??_initialized@_data_SqlParseState@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_initialized(void)'::`2'::value
0x140006c87  jnz     short loc_140006CF2
0x140006c89  xor     edi, edi
0x140006c8b  lea     r14, cs:140000000h
0x140006c92  xor     ebx, ebx
0x140006c94  mov     rcx, ds:rva off_140019A80[r14+rbx*8]; Str
0x140006c9c  lea     rax, rva ?storage@?1??_name_storage@_data_SqlParseState@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "New,Exists,Delete,Ignore," ...
0x140006ca3  add     rax, rdi
0x140006ca6  lea     rdx, Control; "= \t\n"
0x140006cad  mov     rva ?value@?1??_name_array@_data_SqlParseState@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_name_array(void)'::`2'::value ...
0x140006cb5  call    cs:__imp_strcspn
0x140006cbb  mov     rcx, ds:rva off_140019A80[r14+rbx*8]; "New" ...
0x140006cc3  add     rax, rdi
0x140006cc6  mov     byte ptr [rax+r14+28990h], 0
0x140006ccf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006cd3  inc     rax
0x140006cd6  cmp     byte ptr [rcx+rax], 0
0x140006cda  jnz     short loc_140006CD3
0x140006cdc  inc     rdi
0x140006cdf  inc     rbx
0x140006ce2  add     rdi, rax
0x140006ce5  cmp     rbx, 4
0x140006ce9  jb      short loc_140006C94
0x140006ceb  mov     cs:?value@?1??_initialized@_data_SqlParseState@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_SqlParseState::_initialized(void)'::`2'::value
0x140006cf2  mov     rbx, [rsp+28h+arg_0]
0x140006cf7  mov     rdi, [rsp+28h+arg_8]
0x140006cfc  add     rsp, 20h
0x140006d00  pop     r14
0x140006d02  retn
```
