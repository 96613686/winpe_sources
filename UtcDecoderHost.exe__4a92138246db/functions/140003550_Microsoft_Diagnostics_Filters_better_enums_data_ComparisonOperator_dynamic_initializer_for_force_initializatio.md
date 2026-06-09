# Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_dynamic_initializer_for___force_initialization__

- ea: `0x140003550`
- end: `0x1400035e3`
- name: `Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003550`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003595`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003595`

## pseudocode

```c
void Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0xD; ++i )
    {
      v2 = off_140019C00[i];
      `Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019C00[i];
      `Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140003550  mov     [rsp+arg_0], rbx
0x140003555  mov     [rsp+arg_8], rdi
0x14000355a  push    r14
0x14000355c  sub     rsp, 20h
0x140003560  cmp     cs:?value@?1??_initialized@_data_ComparisonOperator@better_enums@Filters@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_initialized(void)'::`2'::value
0x140003567  jnz     short loc_1400035D2
0x140003569  xor     edi, edi
0x14000356b  lea     r14, cs:140000000h
0x140003572  xor     ebx, ebx
0x140003574  mov     rcx, ds:rva off_140019C00[r14+rbx*8]; Str
0x14000357c  lea     rax, rva ?storage@?1??_name_storage@_data_ComparisonOperator@better_enums@Filters@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Equal,NotEqual,GreaterThan,LessThan,Gre"... ...
0x140003583  add     rax, rdi
0x140003586  lea     rdx, Control; "= \t\n"
0x14000358d  mov     rva ?value@?1??_name_array@_data_ComparisonOperator@better_enums@Filters@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_name_array(void)'::`2'::value ...
0x140003595  call    cs:__imp_strcspn
0x14000359b  mov     rcx, ds:rva off_140019C00[r14+rbx*8]; "Equal" ...
0x1400035a3  add     rax, rdi
0x1400035a6  mov     byte ptr [rax+r14+25C50h], 0
0x1400035af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400035b3  inc     rax
0x1400035b6  cmp     byte ptr [rcx+rax], 0
0x1400035ba  jnz     short loc_1400035B3
0x1400035bc  inc     rdi
0x1400035bf  inc     rbx
0x1400035c2  add     rdi, rax
0x1400035c5  cmp     rbx, 0Dh
0x1400035c9  jb      short loc_140003574
0x1400035cb  mov     cs:?value@?1??_initialized@_data_ComparisonOperator@better_enums@Filters@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::Filters::better_enums::_data_ComparisonOperator::_initialized(void)'::`2'::value
0x1400035d2  mov     rbx, [rsp+28h+arg_0]
0x1400035d7  mov     rdi, [rsp+28h+arg_8]
0x1400035dc  add     rsp, 20h
0x1400035e0  pop     r14
0x1400035e2  retn
```
