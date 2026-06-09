# Microsoft::Diagnostics::better_enums::_data_IoRequestType::_dynamic_initializer_for___force_initialization__

- ea: `0x140004e20`
- end: `0x140004eb3`
- name: `Microsoft::Diagnostics::better_enums::_data_IoRequestType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004e20`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004e65`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004e65`

## string_xrefs

- `0x140004e4c`: `Connect = 0,Read,Write,ConnectLinux,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_IoRequestType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_IoRequestType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 4; ++i )
    {
      v2 = off_140019D90[i];
      `Microsoft::Diagnostics::better_enums::_data_IoRequestType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_IoRequestType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019D90[i];
      `Microsoft::Diagnostics::better_enums::_data_IoRequestType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_IoRequestType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140004e20  mov     [rsp+arg_0], rbx
0x140004e25  mov     [rsp+arg_8], rdi
0x140004e2a  push    r14
0x140004e2c  sub     rsp, 20h
0x140004e30  cmp     cs:?value@?1??_initialized@_data_IoRequestType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_IoRequestType::_initialized(void)'::`2'::value
0x140004e37  jnz     short loc_140004EA2
0x140004e39  xor     edi, edi
0x140004e3b  lea     r14, cs:140000000h
0x140004e42  xor     ebx, ebx
0x140004e44  mov     rcx, ds:rva off_140019D90[r14+rbx*8]; Str
0x140004e4c  lea     rax, rva ?storage@?1??_name_storage@_data_IoRequestType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Connect = 0,Read,Write,ConnectLinux," ...
0x140004e53  add     rax, rdi
0x140004e56  lea     rdx, Control; "= \t\n"
0x140004e5d  mov     rva ?value@?1??_name_array@_data_IoRequestType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_IoRequestType::_name_array(void)'::`2'::value ...
0x140004e65  call    cs:__imp_strcspn
0x140004e6b  mov     rcx, ds:rva off_140019D90[r14+rbx*8]; "Connect = 0" ...
0x140004e73  add     rax, rdi
0x140004e76  mov     byte ptr [rax+r14+28890h], 0
0x140004e7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004e83  inc     rax
0x140004e86  cmp     byte ptr [rcx+rax], 0
0x140004e8a  jnz     short loc_140004E83
0x140004e8c  inc     rdi
0x140004e8f  inc     rbx
0x140004e92  add     rdi, rax
0x140004e95  cmp     rbx, 4
0x140004e99  jb      short loc_140004E44
0x140004e9b  mov     cs:?value@?1??_initialized@_data_IoRequestType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_IoRequestType::_initialized(void)'::`2'::value
0x140004ea2  mov     rbx, [rsp+28h+arg_0]
0x140004ea7  mov     rdi, [rsp+28h+arg_8]
0x140004eac  add     rsp, 20h
0x140004eb0  pop     r14
0x140004eb2  retn
```
