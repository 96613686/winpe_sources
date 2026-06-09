# Microsoft::Diagnostics::better_enums::_data_LoadSettings::_dynamic_initializer_for___force_initialization__

- ea: `0x140005000`
- end: `0x140005093`
- name: `Microsoft::Diagnostics::better_enums::_data_LoadSettings::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140005000`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005045`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005045`

## string_xrefs

- `0x14000502c`: `UtcAppJsonAndSideload,All,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_LoadSettings::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_LoadSettings::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      v2 = off_14001A760[i];
      `Microsoft::Diagnostics::better_enums::_data_LoadSettings::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_LoadSettings::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A760[i];
      `Microsoft::Diagnostics::better_enums::_data_LoadSettings::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_LoadSettings::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140005000  mov     [rsp+arg_0], rbx
0x140005005  mov     [rsp+arg_8], rdi
0x14000500a  push    r14
0x14000500c  sub     rsp, 20h
0x140005010  cmp     cs:?value@?1??_initialized@_data_LoadSettings@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_LoadSettings::_initialized(void)'::`2'::value
0x140005017  jnz     short loc_140005082
0x140005019  xor     edi, edi
0x14000501b  lea     r14, cs:140000000h
0x140005022  xor     ebx, ebx
0x140005024  mov     rcx, ds:rva off_14001A760[r14+rbx*8]; Str
0x14000502c  lea     rax, rva ?storage@?1??_name_storage@_data_LoadSettings@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "UtcAppJsonAndSideload,All," ...
0x140005033  add     rax, rdi
0x140005036  lea     rdx, Control; "= \t\n"
0x14000503d  mov     rva ?value@?1??_name_array@_data_LoadSettings@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_LoadSettings::_name_array(void)'::`2'::value ...
0x140005045  call    cs:__imp_strcspn
0x14000504b  mov     rcx, ds:rva off_14001A760[r14+rbx*8]; "UtcAppJsonAndSideload" ...
0x140005053  add     rax, rdi
0x140005056  mov     byte ptr [rax+r14+268C0h], 0
0x14000505f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005063  inc     rax
0x140005066  cmp     byte ptr [rcx+rax], 0
0x14000506a  jnz     short loc_140005063
0x14000506c  inc     rdi
0x14000506f  inc     rbx
0x140005072  add     rdi, rax
0x140005075  cmp     rbx, 2
0x140005079  jb      short loc_140005024
0x14000507b  mov     cs:?value@?1??_initialized@_data_LoadSettings@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_LoadSettings::_initialized(void)'::`2'::value
0x140005082  mov     rbx, [rsp+28h+arg_0]
0x140005087  mov     rdi, [rsp+28h+arg_8]
0x14000508c  add     rsp, 20h
0x140005090  pop     r14
0x140005092  retn
```
