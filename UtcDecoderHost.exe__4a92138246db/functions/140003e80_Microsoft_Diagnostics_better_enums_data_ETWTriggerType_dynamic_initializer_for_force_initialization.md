# Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_dynamic_initializer_for___force_initialization__

- ea: `0x140003e80`
- end: `0x140003f13`
- name: `Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003e80`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003ec5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003ec5`

## string_xrefs

- `0x140003eac`: `Manifested,TraceLogging,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      v2 = off_14001A0E0[i];
      `Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A0E0[i];
      `Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140003e80  mov     [rsp+arg_0], rbx
0x140003e85  mov     [rsp+arg_8], rdi
0x140003e8a  push    r14
0x140003e8c  sub     rsp, 20h
0x140003e90  cmp     cs:?value@?1??_initialized@_data_ETWTriggerType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_initialized(void)'::`2'::value
0x140003e97  jnz     short loc_140003F02
0x140003e99  xor     edi, edi
0x140003e9b  lea     r14, cs:140000000h
0x140003ea2  xor     ebx, ebx
0x140003ea4  mov     rcx, ds:rva off_14001A0E0[r14+rbx*8]; Str
0x140003eac  lea     rax, rva ?storage@?1??_name_storage@_data_ETWTriggerType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Manifested,TraceLogging," ...
0x140003eb3  add     rax, rdi
0x140003eb6  lea     rdx, Control; "= \t\n"
0x140003ebd  mov     rva ?value@?1??_name_array@_data_ETWTriggerType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_name_array(void)'::`2'::value ...
0x140003ec5  call    cs:__imp_strcspn
0x140003ecb  mov     rcx, ds:rva off_14001A0E0[r14+rbx*8]; "Manifested" ...
0x140003ed3  add     rax, rdi
0x140003ed6  mov     byte ptr [rax+r14+257A0h], 0
0x140003edf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003ee3  inc     rax
0x140003ee6  cmp     byte ptr [rcx+rax], 0
0x140003eea  jnz     short loc_140003EE3
0x140003eec  inc     rdi
0x140003eef  inc     rbx
0x140003ef2  add     rdi, rax
0x140003ef5  cmp     rbx, 2
0x140003ef9  jb      short loc_140003EA4
0x140003efb  mov     cs:?value@?1??_initialized@_data_ETWTriggerType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_ETWTriggerType::_initialized(void)'::`2'::value
0x140003f02  mov     rbx, [rsp+28h+arg_0]
0x140003f07  mov     rdi, [rsp+28h+arg_8]
0x140003f0c  add     rsp, 20h
0x140003f10  pop     r14
0x140003f12  retn
```
