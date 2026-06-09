# Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_dynamic_initializer_for___force_initialization__

- ea: `0x140003230`
- end: `0x1400032c3`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003230`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003275`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003275`

## string_xrefs

- `0x14000325c`: `AllowUpdate,DenyUpdate,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      v2 = off_140019AA0[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019AA0[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140003230  mov     [rsp+arg_0], rbx
0x140003235  mov     [rsp+arg_8], rdi
0x14000323a  push    r14
0x14000323c  sub     rsp, 20h
0x140003240  cmp     cs:?value@?1??_initialized@_data_BufferUpdateOptions@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_initialized(void)'::`2'::value
0x140003247  jnz     short loc_1400032B2
0x140003249  xor     edi, edi
0x14000324b  lea     r14, cs:140000000h
0x140003252  xor     ebx, ebx
0x140003254  mov     rcx, ds:rva off_140019AA0[r14+rbx*8]; Str
0x14000325c  lea     rax, rva ?storage@?1??_name_storage@_data_BufferUpdateOptions@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "AllowUpdate,DenyUpdate," ...
0x140003263  add     rax, rdi
0x140003266  lea     rdx, Control; "= \t\n"
0x14000326d  mov     rva ?value@?1??_name_array@_data_BufferUpdateOptions@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_name_array(void)'::`2'::value ...
0x140003275  call    cs:__imp_strcspn
0x14000327b  mov     rcx, ds:rva off_140019AA0[r14+rbx*8]; "AllowUpdate" ...
0x140003283  add     rax, rdi
0x140003286  mov     byte ptr [rax+r14+284C0h], 0
0x14000328f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003293  inc     rax
0x140003296  cmp     byte ptr [rcx+rax], 0
0x14000329a  jnz     short loc_140003293
0x14000329c  inc     rdi
0x14000329f  inc     rbx
0x1400032a2  add     rdi, rax
0x1400032a5  cmp     rbx, 2
0x1400032a9  jb      short loc_140003254
0x1400032ab  mov     cs:?value@?1??_initialized@_data_BufferUpdateOptions@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_BufferUpdateOptions::_initialized(void)'::`2'::value
0x1400032b2  mov     rbx, [rsp+28h+arg_0]
0x1400032b7  mov     rdi, [rsp+28h+arg_8]
0x1400032bc  add     rsp, 20h
0x1400032c0  pop     r14
0x1400032c2  retn
```
