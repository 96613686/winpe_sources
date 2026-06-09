# Microsoft::Diagnostics::better_enums::_data_FilterType::_dynamic_initializer_for___force_initialization__

- ea: `0x1400049c0`
- end: `0x140004a53`
- name: `Microsoft::Diagnostics::better_enums::_data_FilterType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400049c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004a05`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004a05`

## string_xrefs

- `0x1400049ec`: `RegistryKeyFilter,FileInfoFilter,ServiceStatusFilter,TelemetryProtocolFilter,SinglePropertyFilter,DualPropertyFilter,ScriptFilter,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_FilterType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_FilterType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 7; ++i )
    {
      v2 = off_14001A8D0[i];
      `Microsoft::Diagnostics::better_enums::_data_FilterType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_FilterType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A8D0[i];
      `Microsoft::Diagnostics::better_enums::_data_FilterType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_FilterType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x1400049c0  mov     [rsp+arg_0], rbx
0x1400049c5  mov     [rsp+arg_8], rdi
0x1400049ca  push    r14
0x1400049cc  sub     rsp, 20h
0x1400049d0  cmp     cs:?value@?1??_initialized@_data_FilterType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_FilterType::_initialized(void)'::`2'::value
0x1400049d7  jnz     short loc_140004A42
0x1400049d9  xor     edi, edi
0x1400049db  lea     r14, cs:140000000h
0x1400049e2  xor     ebx, ebx
0x1400049e4  mov     rcx, ds:rva off_14001A8D0[r14+rbx*8]; Str
0x1400049ec  lea     rax, rva ?storage@?1??_name_storage@_data_FilterType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "RegistryKeyFilter,FileInfoFilter,Servic"... ...
0x1400049f3  add     rax, rdi
0x1400049f6  lea     rdx, Control; "= \t\n"
0x1400049fd  mov     rva ?value@?1??_name_array@_data_FilterType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_FilterType::_name_array(void)'::`2'::value ...
0x140004a05  call    cs:__imp_strcspn
0x140004a0b  mov     rcx, ds:rva off_14001A8D0[r14+rbx*8]; "RegistryKeyFilter" ...
0x140004a13  add     rax, rdi
0x140004a16  mov     byte ptr [rax+r14+25910h], 0
0x140004a1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004a23  inc     rax
0x140004a26  cmp     byte ptr [rcx+rax], 0
0x140004a2a  jnz     short loc_140004A23
0x140004a2c  inc     rdi
0x140004a2f  inc     rbx
0x140004a32  add     rdi, rax
0x140004a35  cmp     rbx, 7
0x140004a39  jb      short loc_1400049E4
0x140004a3b  mov     cs:?value@?1??_initialized@_data_FilterType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_FilterType::_initialized(void)'::`2'::value
0x140004a42  mov     rbx, [rsp+28h+arg_0]
0x140004a47  mov     rdi, [rsp+28h+arg_8]
0x140004a4c  add     rsp, 20h
0x140004a50  pop     r14
0x140004a52  retn
```
