# Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_dynamic_initializer_for___force_initialization__

- ea: `0x140006770`
- end: `0x140006803`
- name: `Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006770`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400067b5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400067b5`

## string_xrefs

- `0x14000679c`: `Initial = 0,OobeComplete = 1,PermissionKey = 2,Flighting = 3,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 4; ++i )
    {
      v2 = off_140019E00[i];
      `Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019E00[i];
      `Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140006770  mov     [rsp+arg_0], rbx
0x140006775  mov     [rsp+arg_8], rdi
0x14000677a  push    r14
0x14000677c  sub     rsp, 20h
0x140006780  cmp     cs:?value@?1??_initialized@_data_SetAllowedToProcessDataReason@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_initialized(void)'::`2'::value
0x140006787  jnz     short loc_1400067F2
0x140006789  xor     edi, edi
0x14000678b  lea     r14, cs:140000000h
0x140006792  xor     ebx, ebx
0x140006794  mov     rcx, ds:rva off_140019E00[r14+rbx*8]; Str
0x14000679c  lea     rax, rva ?storage@?1??_name_storage@_data_SetAllowedToProcessDataReason@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Initial = 0,OobeComplete = 1,Permission"... ...
0x1400067a3  add     rax, rdi
0x1400067a6  lea     rdx, Control; "= \t\n"
0x1400067ad  mov     rva ?value@?1??_name_array@_data_SetAllowedToProcessDataReason@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_name_array(void)'::`2'::value ...
0x1400067b5  call    cs:__imp_strcspn
0x1400067bb  mov     rcx, ds:rva off_140019E00[r14+rbx*8]; "Initial = 0" ...
0x1400067c3  add     rax, rdi
0x1400067c6  mov     byte ptr [rax+r14+26600h], 0
0x1400067cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400067d3  inc     rax
0x1400067d6  cmp     byte ptr [rcx+rax], 0
0x1400067da  jnz     short loc_1400067D3
0x1400067dc  inc     rdi
0x1400067df  inc     rbx
0x1400067e2  add     rdi, rax
0x1400067e5  cmp     rbx, 4
0x1400067e9  jb      short loc_140006794
0x1400067eb  mov     cs:?value@?1??_initialized@_data_SetAllowedToProcessDataReason@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_SetAllowedToProcessDataReason::_initialized(void)'::`2'::value
0x1400067f2  mov     rbx, [rsp+28h+arg_0]
0x1400067f7  mov     rdi, [rsp+28h+arg_8]
0x1400067fc  add     rsp, 20h
0x140006800  pop     r14
0x140006802  retn
```
