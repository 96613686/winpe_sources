# Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_dynamic_initializer_for___force_initialization__

- ea: `0x140007b10`
- end: `0x140007ba3`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007b10`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007b55`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007b55`

## string_xrefs

- `0x140007b3c`: `CommercialDataPipeline = (1 << 0),DesktopAnalytics = (1 << 1),`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      v2 = off_140019B60[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019B60[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140007b10  mov     [rsp+arg_0], rbx
0x140007b15  mov     [rsp+arg_8], rdi
0x140007b1a  push    r14
0x140007b1c  sub     rsp, 20h
0x140007b20  cmp     cs:?value@?1??_initialized@_data_UtcPartnerProgramsFlags@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_initialized(void)'::`2'::value
0x140007b27  jnz     short loc_140007B92
0x140007b29  xor     edi, edi
0x140007b2b  lea     r14, cs:140000000h
0x140007b32  xor     ebx, ebx
0x140007b34  mov     rcx, ds:rva off_140019B60[r14+rbx*8]; Str
0x140007b3c  lea     rax, rva ?storage@?1??_name_storage@_data_UtcPartnerProgramsFlags@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "CommercialDataPipeline = (1 << 0),Deskt"... ...
0x140007b43  add     rax, rdi
0x140007b46  lea     rdx, Control; "= \t\n"
0x140007b4d  mov     rva ?value@?1??_name_array@_data_UtcPartnerProgramsFlags@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_name_array(void)'::`2'::value ...
0x140007b55  call    cs:__imp_strcspn
0x140007b5b  mov     rcx, ds:rva off_140019B60[r14+rbx*8]; "CommercialDataPipeline = (1 << 0)" ...
0x140007b63  add     rax, rdi
0x140007b66  mov     byte ptr [rax+r14+26640h], 0
0x140007b6f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007b73  inc     rax
0x140007b76  cmp     byte ptr [rcx+rax], 0
0x140007b7a  jnz     short loc_140007B73
0x140007b7c  inc     rdi
0x140007b7f  inc     rbx
0x140007b82  add     rdi, rax
0x140007b85  cmp     rbx, 2
0x140007b89  jb      short loc_140007B34
0x140007b8b  mov     cs:?value@?1??_initialized@_data_UtcPartnerProgramsFlags@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_UtcPartnerProgramsFlags::_initialized(void)'::`2'::value
0x140007b92  mov     rbx, [rsp+28h+arg_0]
0x140007b97  mov     rdi, [rsp+28h+arg_8]
0x140007b9c  add     rsp, 20h
0x140007ba0  pop     r14
0x140007ba2  retn
```
