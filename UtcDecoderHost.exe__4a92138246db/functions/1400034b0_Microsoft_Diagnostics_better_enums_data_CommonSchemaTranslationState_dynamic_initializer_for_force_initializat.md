# Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_dynamic_initializer_for___force_initialization__

- ea: `0x1400034b0`
- end: `0x140003543`
- name: `Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400034b0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400034f5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400034f5`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v2 = off_14001A9A0[i];
      `Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A9A0[i];
      `Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x1400034b0  mov     [rsp+arg_0], rbx
0x1400034b5  mov     [rsp+arg_8], rdi
0x1400034ba  push    r14
0x1400034bc  sub     rsp, 20h
0x1400034c0  cmp     cs:?value@?1??_initialized@_data_CommonSchemaTranslationState@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_initialized(void)'::`2'::value
0x1400034c7  jnz     short loc_140003532
0x1400034c9  xor     edi, edi
0x1400034cb  lea     r14, cs:140000000h
0x1400034d2  xor     ebx, ebx
0x1400034d4  mov     rcx, ds:rva off_14001A9A0[r14+rbx*8]; Str
0x1400034dc  lea     rax, rva ?storage@?1??_name_storage@_data_CommonSchemaTranslationState@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Uninitialized = 0,TranslationNeeded,Tra"... ...
0x1400034e3  add     rax, rdi
0x1400034e6  lea     rdx, Control; "= \t\n"
0x1400034ed  mov     rva ?value@?1??_name_array@_data_CommonSchemaTranslationState@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_name_array(void)'::`2'::value ...
0x1400034f5  call    cs:__imp_strcspn
0x1400034fb  mov     rcx, ds:rva off_14001A9A0[r14+rbx*8]; "Uninitialized = 0" ...
0x140003503  add     rax, rdi
0x140003506  mov     byte ptr [rax+r14+27280h], 0
0x14000350f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003513  inc     rax
0x140003516  cmp     byte ptr [rcx+rax], 0
0x14000351a  jnz     short loc_140003513
0x14000351c  inc     rdi
0x14000351f  inc     rbx
0x140003522  add     rdi, rax
0x140003525  cmp     rbx, 3
0x140003529  jb      short loc_1400034D4
0x14000352b  mov     cs:?value@?1??_initialized@_data_CommonSchemaTranslationState@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_CommonSchemaTranslationState::_initialized(void)'::`2'::value
0x140003532  mov     rbx, [rsp+28h+arg_0]
0x140003537  mov     rdi, [rsp+28h+arg_8]
0x14000353c  add     rsp, 20h
0x140003540  pop     r14
0x140003542  retn
```
