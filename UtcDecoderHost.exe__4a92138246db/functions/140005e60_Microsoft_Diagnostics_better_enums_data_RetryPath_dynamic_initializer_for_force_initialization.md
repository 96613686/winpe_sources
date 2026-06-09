# Microsoft::Diagnostics::better_enums::_data_RetryPath::_dynamic_initializer_for___force_initialization__

- ea: `0x140005e60`
- end: `0x140005ef3`
- name: `Microsoft::Diagnostics::better_enums::_data_RetryPath::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005e60`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005ea5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005ea5`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_RetryPath::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_RetryPath::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v2 = off_14001A910[i];
      `Microsoft::Diagnostics::better_enums::_data_RetryPath::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_RetryPath::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A910[i];
      `Microsoft::Diagnostics::better_enums::_data_RetryPath::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_RetryPath::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140005e60  mov     [rsp+arg_0], rbx
0x140005e65  mov     [rsp+arg_8], rdi
0x140005e6a  push    r14
0x140005e6c  sub     rsp, 20h
0x140005e70  cmp     cs:?value@?1??_initialized@_data_RetryPath@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_RetryPath::_initialized(void)'::`2'::value
0x140005e77  jnz     short loc_140005EE2
0x140005e79  xor     edi, edi
0x140005e7b  lea     r14, cs:140000000h
0x140005e82  xor     ebx, ebx
0x140005e84  mov     rcx, ds:rva off_14001A910[r14+rbx*8]; Str
0x140005e8c  lea     rax, rva ?storage@?1??_name_storage@_data_RetryPath@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "NoExist,RetryPostWait,Timeout," ...
0x140005e93  add     rax, rdi
0x140005e96  lea     rdx, Control; "= \t\n"
0x140005e9d  mov     rva ?value@?1??_name_array@_data_RetryPath@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_RetryPath::_name_array(void)'::`2'::value ...
0x140005ea5  call    cs:__imp_strcspn
0x140005eab  mov     rcx, ds:rva off_14001A910[r14+rbx*8]; "NoExist" ...
0x140005eb3  add     rax, rdi
0x140005eb6  mov     byte ptr [rax+r14+263A0h], 0
0x140005ebf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005ec3  inc     rax
0x140005ec6  cmp     byte ptr [rcx+rax], 0
0x140005eca  jnz     short loc_140005EC3
0x140005ecc  inc     rdi
0x140005ecf  inc     rbx
0x140005ed2  add     rdi, rax
0x140005ed5  cmp     rbx, 3
0x140005ed9  jb      short loc_140005E84
0x140005edb  mov     cs:?value@?1??_initialized@_data_RetryPath@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_RetryPath::_initialized(void)'::`2'::value
0x140005ee2  mov     rbx, [rsp+28h+arg_0]
0x140005ee7  mov     rdi, [rsp+28h+arg_8]
0x140005eec  add     rsp, 20h
0x140005ef0  pop     r14
0x140005ef2  retn
```
