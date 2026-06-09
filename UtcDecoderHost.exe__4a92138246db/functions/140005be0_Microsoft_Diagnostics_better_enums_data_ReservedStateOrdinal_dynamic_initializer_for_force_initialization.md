# Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_dynamic_initializer_for___force_initialization__

- ea: `0x140005be0`
- end: `0x140005c73`
- name: `Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005be0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005c25`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005c25`

## string_xrefs

- `0x140005c0c`: `Start = 250,Cancel = 251,Fail = 252,Complete = 253,Timeout = 254,MaxValue = 255,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 6; ++i )
    {
      v2 = off_14001A490[i];
      `Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A490[i];
      `Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140005be0  mov     [rsp+arg_0], rbx
0x140005be5  mov     [rsp+arg_8], rdi
0x140005bea  push    r14
0x140005bec  sub     rsp, 20h
0x140005bf0  cmp     cs:?value@?1??_initialized@_data_ReservedStateOrdinal@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_initialized(void)'::`2'::value
0x140005bf7  jnz     short loc_140005C62
0x140005bf9  xor     edi, edi
0x140005bfb  lea     r14, cs:140000000h
0x140005c02  xor     ebx, ebx
0x140005c04  mov     rcx, ds:rva off_14001A490[r14+rbx*8]; Str
0x140005c0c  lea     rax, rva ?storage@?1??_name_storage@_data_ReservedStateOrdinal@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Start = 250,Cancel = 251,Fail = 252,Com"... ...
0x140005c13  add     rax, rdi
0x140005c16  lea     rdx, Control; "= \t\n"
0x140005c1d  mov     rva ?value@?1??_name_array@_data_ReservedStateOrdinal@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_name_array(void)'::`2'::value ...
0x140005c25  call    cs:__imp_strcspn
0x140005c2b  mov     rcx, ds:rva off_14001A490[r14+rbx*8]; "Start = 250" ...
0x140005c33  add     rax, rdi
0x140005c36  mov     byte ptr [rax+r14+27310h], 0
0x140005c3f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005c43  inc     rax
0x140005c46  cmp     byte ptr [rcx+rax], 0
0x140005c4a  jnz     short loc_140005C43
0x140005c4c  inc     rdi
0x140005c4f  inc     rbx
0x140005c52  add     rdi, rax
0x140005c55  cmp     rbx, 6
0x140005c59  jb      short loc_140005C04
0x140005c5b  mov     cs:?value@?1??_initialized@_data_ReservedStateOrdinal@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_ReservedStateOrdinal::_initialized(void)'::`2'::value
0x140005c62  mov     rbx, [rsp+28h+arg_0]
0x140005c67  mov     rdi, [rsp+28h+arg_8]
0x140005c6c  add     rsp, 20h
0x140005c70  pop     r14
0x140005c72  retn
```
