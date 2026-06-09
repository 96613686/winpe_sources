# Microsoft::Diagnostics::better_enums::_data_ActionDestination::_dynamic_initializer_for___force_initialization__

- ea: `0x1400023b0`
- end: `0x140002443`
- name: `Microsoft::Diagnostics::better_enums::_data_ActionDestination::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400023b0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400023f5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400023f5`

## string_xrefs

- `0x1400023dc`: `Host,Agent,All,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_ActionDestination::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_ActionDestination::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v2 = off_140019C80[i];
      `Microsoft::Diagnostics::better_enums::_data_ActionDestination::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_ActionDestination::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019C80[i];
      `Microsoft::Diagnostics::better_enums::_data_ActionDestination::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_ActionDestination::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x1400023b0  mov     [rsp+arg_0], rbx
0x1400023b5  mov     [rsp+arg_8], rdi
0x1400023ba  push    r14
0x1400023bc  sub     rsp, 20h
0x1400023c0  cmp     cs:?value@?1??_initialized@_data_ActionDestination@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_ActionDestination::_initialized(void)'::`2'::value
0x1400023c7  jnz     short loc_140002432
0x1400023c9  xor     edi, edi
0x1400023cb  lea     r14, cs:140000000h
0x1400023d2  xor     ebx, ebx
0x1400023d4  mov     rcx, ds:rva off_140019C80[r14+rbx*8]; Str
0x1400023dc  lea     rax, rva ?storage@?1??_name_storage@_data_ActionDestination@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Host,Agent,All," ...
0x1400023e3  add     rax, rdi
0x1400023e6  lea     rdx, Control; "= \t\n"
0x1400023ed  mov     rva ?value@?1??_name_array@_data_ActionDestination@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_ActionDestination::_name_array(void)'::`2'::value ...
0x1400023f5  call    cs:__imp_strcspn
0x1400023fb  mov     rcx, ds:rva off_140019C80[r14+rbx*8]; "Host" ...
0x140002403  add     rax, rdi
0x140002406  mov     byte ptr [rax+r14+272E0h], 0
0x14000240f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002413  inc     rax
0x140002416  cmp     byte ptr [rcx+rax], 0
0x14000241a  jnz     short loc_140002413
0x14000241c  inc     rdi
0x14000241f  inc     rbx
0x140002422  add     rdi, rax
0x140002425  cmp     rbx, 3
0x140002429  jb      short loc_1400023D4
0x14000242b  mov     cs:?value@?1??_initialized@_data_ActionDestination@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_ActionDestination::_initialized(void)'::`2'::value
0x140002432  mov     rbx, [rsp+28h+arg_0]
0x140002437  mov     rdi, [rsp+28h+arg_8]
0x14000243c  add     rsp, 20h
0x140002440  pop     r14
0x140002442  retn
```
