# Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_dynamic_initializer_for___force_initialization__

- ea: `0x140005960`
- end: `0x1400059f3`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140005960`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400059a5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400059a5`

## string_xrefs

- `0x14000598c`: `ProcessName,ProcessId,ServiceName,ServiceRegex,ModuleRegex,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 5; ++i )
    {
      v2 = off_140019650[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019650[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140005960  mov     [rsp+arg_0], rbx
0x140005965  mov     [rsp+arg_8], rdi
0x14000596a  push    r14
0x14000596c  sub     rsp, 20h
0x140005970  cmp     cs:?value@?1??_initialized@_data_ProcessDumpType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_initialized(void)'::`2'::value
0x140005977  jnz     short loc_1400059E2
0x140005979  xor     edi, edi
0x14000597b  lea     r14, cs:140000000h
0x140005982  xor     ebx, ebx
0x140005984  mov     rcx, ds:rva off_140019650[r14+rbx*8]; Str
0x14000598c  lea     rax, rva ?storage@?1??_name_storage@_data_ProcessDumpType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "ProcessName,ProcessId,ServiceName,Servi"... ...
0x140005993  add     rax, rdi
0x140005996  lea     rdx, Control; "= \t\n"
0x14000599d  mov     rva ?value@?1??_name_array@_data_ProcessDumpType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_name_array(void)'::`2'::value ...
0x1400059a5  call    cs:__imp_strcspn
0x1400059ab  mov     rcx, ds:rva off_140019650[r14+rbx*8]; "ProcessName" ...
0x1400059b3  add     rax, rdi
0x1400059b6  mov     byte ptr [rax+r14+25750h], 0
0x1400059bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400059c3  inc     rax
0x1400059c6  cmp     byte ptr [rcx+rax], 0
0x1400059ca  jnz     short loc_1400059C3
0x1400059cc  inc     rdi
0x1400059cf  inc     rbx
0x1400059d2  add     rdi, rax
0x1400059d5  cmp     rbx, 5
0x1400059d9  jb      short loc_140005984
0x1400059db  mov     cs:?value@?1??_initialized@_data_ProcessDumpType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ProcessDumpType::_initialized(void)'::`2'::value
0x1400059e2  mov     rbx, [rsp+28h+arg_0]
0x1400059e7  mov     rdi, [rsp+28h+arg_8]
0x1400059ec  add     rsp, 20h
0x1400059f0  pop     r14
0x1400059f2  retn
```
