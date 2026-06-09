# Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_dynamic_initializer_for___force_initialization__

- ea: `0x140003780`
- end: `0x140003813`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003780`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400037c5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400037c5`

## string_xrefs

- `0x1400037ac`: `Scenario,Registry,Api,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v2 = off_140019AE0[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019AE0[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140003780  mov     [rsp+arg_0], rbx
0x140003785  mov     [rsp+arg_8], rdi
0x14000378a  push    r14
0x14000378c  sub     rsp, 20h
0x140003790  cmp     cs:?value@?1??_initialized@_data_CopyOutputDirectorySource@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_initialized(void)'::`2'::value
0x140003797  jnz     short loc_140003802
0x140003799  xor     edi, edi
0x14000379b  lea     r14, cs:140000000h
0x1400037a2  xor     ebx, ebx
0x1400037a4  mov     rcx, ds:rva off_140019AE0[r14+rbx*8]; Str
0x1400037ac  lea     rax, rva ?storage@?1??_name_storage@_data_CopyOutputDirectorySource@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Scenario,Registry,Api," ...
0x1400037b3  add     rax, rdi
0x1400037b6  lea     rdx, Control; "= \t\n"
0x1400037bd  mov     rva ?value@?1??_name_array@_data_CopyOutputDirectorySource@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_name_array(void)'::`2'::value ...
0x1400037c5  call    cs:__imp_strcspn
0x1400037cb  mov     rcx, ds:rva off_140019AE0[r14+rbx*8]; "Scenario" ...
0x1400037d3  add     rax, rdi
0x1400037d6  mov     byte ptr [rax+r14+28480h], 0
0x1400037df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400037e3  inc     rax
0x1400037e6  cmp     byte ptr [rcx+rax], 0
0x1400037ea  jnz     short loc_1400037E3
0x1400037ec  inc     rdi
0x1400037ef  inc     rbx
0x1400037f2  add     rdi, rax
0x1400037f5  cmp     rbx, 3
0x1400037f9  jb      short loc_1400037A4
0x1400037fb  mov     cs:?value@?1??_initialized@_data_CopyOutputDirectorySource@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CopyOutputDirectorySource::_initialized(void)'::`2'::value
0x140003802  mov     rbx, [rsp+28h+arg_0]
0x140003807  mov     rdi, [rsp+28h+arg_8]
0x14000380c  add     rsp, 20h
0x140003810  pop     r14
0x140003812  retn
```
