# Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_dynamic_initializer_for___force_initialization__

- ea: `0x140003410`
- end: `0x1400034a3`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140003410`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003455`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003455`

## string_xrefs

- `0x14000343c`: `RegistryDump,FileInfo,Etl,UserDump,KernelDump,WnfDump,AgentDiagnosticsZip,Other = std::numeric_limits<uint16>::max(),`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 8; ++i )
    {
      v2 = off_140019680[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019680[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140003410  mov     [rsp+arg_0], rbx
0x140003415  mov     [rsp+arg_8], rdi
0x14000341a  push    r14
0x14000341c  sub     rsp, 20h
0x140003420  cmp     cs:?value@?1??_initialized@_data_CollectedFileType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_initialized(void)'::`2'::value
0x140003427  jnz     short loc_140003492
0x140003429  xor     edi, edi
0x14000342b  lea     r14, cs:140000000h
0x140003432  xor     ebx, ebx
0x140003434  mov     rcx, ds:rva off_140019680[r14+rbx*8]; Str
0x14000343c  lea     rax, rva ?storage@?1??_name_storage@_data_CollectedFileType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "RegistryDump,FileInfo,Etl,UserDump,Kern"... ...
0x140003443  add     rax, rdi
0x140003446  lea     rdx, Control; "= \t\n"
0x14000344d  mov     rva ?value@?1??_name_array@_data_CollectedFileType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_name_array(void)'::`2'::value ...
0x140003455  call    cs:__imp_strcspn
0x14000345b  mov     rcx, ds:rva off_140019680[r14+rbx*8]; "RegistryDump" ...
0x140003463  add     rax, rdi
0x140003466  mov     byte ptr [rax+r14+26DC0h], 0
0x14000346f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003473  inc     rax
0x140003476  cmp     byte ptr [rcx+rax], 0
0x14000347a  jnz     short loc_140003473
0x14000347c  inc     rdi
0x14000347f  inc     rbx
0x140003482  add     rdi, rax
0x140003485  cmp     rbx, 8
0x140003489  jb      short loc_140003434
0x14000348b  mov     cs:?value@?1??_initialized@_data_CollectedFileType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_CollectedFileType::_initialized(void)'::`2'::value
0x140003492  mov     rbx, [rsp+28h+arg_0]
0x140003497  mov     rdi, [rsp+28h+arg_8]
0x14000349c  add     rsp, 20h
0x1400034a0  pop     r14
0x1400034a2  retn
```
