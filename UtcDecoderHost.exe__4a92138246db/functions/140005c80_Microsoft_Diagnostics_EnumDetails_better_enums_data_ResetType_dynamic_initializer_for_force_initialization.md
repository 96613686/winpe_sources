# Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_dynamic_initializer_for___force_initialization__

- ea: `0x140005c80`
- end: `0x140005d13`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140005c80`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005cc5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005cc5`

## string_xrefs

- `0x140005cac`: `DeferredGenericAndReinitialize,PrepareForFailFast,DeleteFilesOnly,ReconstructScenarioDatabase,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 4; ++i )
    {
      v2 = off_140019840[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019840[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140005c80  mov     [rsp+arg_0], rbx
0x140005c85  mov     [rsp+arg_8], rdi
0x140005c8a  push    r14
0x140005c8c  sub     rsp, 20h
0x140005c90  cmp     cs:?value@?1??_initialized@_data_ResetType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_initialized(void)'::`2'::value
0x140005c97  jnz     short loc_140005D02
0x140005c99  xor     edi, edi
0x140005c9b  lea     r14, cs:140000000h
0x140005ca2  xor     ebx, ebx
0x140005ca4  mov     rcx, ds:rva off_140019840[r14+rbx*8]; Str
0x140005cac  lea     rax, rva ?storage@?1??_name_storage@_data_ResetType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "DeferredGenericAndReinitialize,PrepareF"... ...
0x140005cb3  add     rax, rdi
0x140005cb6  lea     rdx, Control; "= \t\n"
0x140005cbd  mov     rva ?value@?1??_name_array@_data_ResetType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_name_array(void)'::`2'::value ...
0x140005cc5  call    cs:__imp_strcspn
0x140005ccb  mov     rcx, ds:rva off_140019840[r14+rbx*8]; "DeferredGenericAndReinitialize" ...
0x140005cd3  add     rax, rdi
0x140005cd6  mov     byte ptr [rax+r14+28810h], 0
0x140005cdf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005ce3  inc     rax
0x140005ce6  cmp     byte ptr [rcx+rax], 0
0x140005cea  jnz     short loc_140005CE3
0x140005cec  inc     rdi
0x140005cef  inc     rbx
0x140005cf2  add     rdi, rax
0x140005cf5  cmp     rbx, 4
0x140005cf9  jb      short loc_140005CA4
0x140005cfb  mov     cs:?value@?1??_initialized@_data_ResetType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_initialized(void)'::`2'::value
0x140005d02  mov     rbx, [rsp+28h+arg_0]
0x140005d07  mov     rdi, [rsp+28h+arg_8]
0x140005d0c  add     rsp, 20h
0x140005d10  pop     r14
0x140005d12  retn
```
