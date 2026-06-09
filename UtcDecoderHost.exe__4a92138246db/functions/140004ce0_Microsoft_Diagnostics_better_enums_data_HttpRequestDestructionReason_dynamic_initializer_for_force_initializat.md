# Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_dynamic_initializer_for___force_initialization__

- ea: `0x140004ce0`
- end: `0x140004d73`
- name: `Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004ce0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004d25`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004d25`

## string_xrefs

- `0x140004d0c`: `HandleClosing,Error,Completion,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v2 = off_14001A110[i];
      `Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A110[i];
      `Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140004ce0  mov     [rsp+arg_0], rbx
0x140004ce5  mov     [rsp+arg_8], rdi
0x140004cea  push    r14
0x140004cec  sub     rsp, 20h
0x140004cf0  cmp     cs:?value@?1??_initialized@_data_HttpRequestDestructionReason@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_initialized(void)'::`2'::value
0x140004cf7  jnz     short loc_140004D62
0x140004cf9  xor     edi, edi
0x140004cfb  lea     r14, cs:140000000h
0x140004d02  xor     ebx, ebx
0x140004d04  mov     rcx, ds:rva off_14001A110[r14+rbx*8]; Str
0x140004d0c  lea     rax, rva ?storage@?1??_name_storage@_data_HttpRequestDestructionReason@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "HandleClosing,Error,Completion," ...
0x140004d13  add     rax, rdi
0x140004d16  lea     rdx, Control; "= \t\n"
0x140004d1d  mov     rva ?value@?1??_name_array@_data_HttpRequestDestructionReason@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_name_array(void)'::`2'::value ...
0x140004d25  call    cs:__imp_strcspn
0x140004d2b  mov     rcx, ds:rva off_14001A110[r14+rbx*8]; "HandleClosing" ...
0x140004d33  add     rax, rdi
0x140004d36  mov     byte ptr [rax+r14+26D70h], 0
0x140004d3f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004d43  inc     rax
0x140004d46  cmp     byte ptr [rcx+rax], 0
0x140004d4a  jnz     short loc_140004D43
0x140004d4c  inc     rdi
0x140004d4f  inc     rbx
0x140004d52  add     rdi, rax
0x140004d55  cmp     rbx, 3
0x140004d59  jb      short loc_140004D04
0x140004d5b  mov     cs:?value@?1??_initialized@_data_HttpRequestDestructionReason@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_HttpRequestDestructionReason::_initialized(void)'::`2'::value
0x140004d62  mov     rbx, [rsp+28h+arg_0]
0x140004d67  mov     rdi, [rsp+28h+arg_8]
0x140004d6c  add     rsp, 20h
0x140004d70  pop     r14
0x140004d72  retn
```
