# Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_dynamic_initializer_for___force_initialization__

- ea: `0x140006950`
- end: `0x1400069e3`
- name: `Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140006950`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006995`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006995`

## string_xrefs

- `0x14000697c`: `Complete,DiffCompressed,MergePatch,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v2 = off_14001A5E0[i];
      `Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A5E0[i];
      `Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140006950  mov     [rsp+arg_0], rbx
0x140006955  mov     [rsp+arg_8], rdi
0x14000695a  push    r14
0x14000695c  sub     rsp, 20h
0x140006960  cmp     cs:?value@?1??_initialized@_data_SettingsPayloadType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_initialized(void)'::`2'::value
0x140006967  jnz     short loc_1400069D2
0x140006969  xor     edi, edi
0x14000696b  lea     r14, cs:140000000h
0x140006972  xor     ebx, ebx
0x140006974  mov     rcx, ds:rva off_14001A5E0[r14+rbx*8]; Str
0x14000697c  lea     rax, rva ?storage@?1??_name_storage@_data_SettingsPayloadType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Complete,DiffCompressed,MergePatch," ...
0x140006983  add     rax, rdi
0x140006986  lea     rdx, Control; "= \t\n"
0x14000698d  mov     rva ?value@?1??_name_array@_data_SettingsPayloadType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_name_array(void)'::`2'::value ...
0x140006995  call    cs:__imp_strcspn
0x14000699b  mov     rcx, ds:rva off_14001A5E0[r14+rbx*8]; "Complete" ...
0x1400069a3  add     rax, rdi
0x1400069a6  mov     byte ptr [rax+r14+26370h], 0
0x1400069af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400069b3  inc     rax
0x1400069b6  cmp     byte ptr [rcx+rax], 0
0x1400069ba  jnz     short loc_1400069B3
0x1400069bc  inc     rdi
0x1400069bf  inc     rbx
0x1400069c2  add     rdi, rax
0x1400069c5  cmp     rbx, 3
0x1400069c9  jb      short loc_140006974
0x1400069cb  mov     cs:?value@?1??_initialized@_data_SettingsPayloadType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_SettingsPayloadType::_initialized(void)'::`2'::value
0x1400069d2  mov     rbx, [rsp+28h+arg_0]
0x1400069d7  mov     rdi, [rsp+28h+arg_8]
0x1400069dc  add     rsp, 20h
0x1400069e0  pop     r14
0x1400069e2  retn
```
