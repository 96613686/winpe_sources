# Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_dynamic_initializer_for___force_initialization__

- ea: `0x140002310`
- end: `0x1400023a3`
- name: `Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002310`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002355`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002355`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      v2 = off_14001A0D0[i];
      `Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A0D0[i];
      `Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140002310  mov     [rsp+arg_0], rbx
0x140002315  mov     [rsp+arg_8], rdi
0x14000231a  push    r14
0x14000231c  sub     rsp, 20h
0x140002320  cmp     cs:?value@?1??_initialized@_data_AadDeviceTokenType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_initialized(void)'::`2'::value
0x140002327  jnz     short loc_140002392
0x140002329  xor     edi, edi
0x14000232b  lea     r14, cs:140000000h
0x140002332  xor     ebx, ebx
0x140002334  mov     rcx, ds:rva off_14001A0D0[r14+rbx*8]; Str
0x14000233c  lea     rax, rva ?storage@?1??_name_storage@_data_AadDeviceTokenType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "OneCollector,OneSettings," ...
0x140002343  add     rax, rdi
0x140002346  lea     rdx, Control; "= \t\n"
0x14000234d  mov     rva ?value@?1??_name_array@_data_AadDeviceTokenType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_name_array(void)'::`2'::value ...
0x140002355  call    cs:__imp_strcspn
0x14000235b  mov     rcx, ds:rva off_14001A0D0[r14+rbx*8]; "OneCollector" ...
0x140002363  add     rax, rdi
0x140002366  mov     byte ptr [rax+r14+27410h], 0
0x14000236f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002373  inc     rax
0x140002376  cmp     byte ptr [rcx+rax], 0
0x14000237a  jnz     short loc_140002373
0x14000237c  inc     rdi
0x14000237f  inc     rbx
0x140002382  add     rdi, rax
0x140002385  cmp     rbx, 2
0x140002389  jb      short loc_140002334
0x14000238b  mov     cs:?value@?1??_initialized@_data_AadDeviceTokenType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_AadDeviceTokenType::_initialized(void)'::`2'::value
0x140002392  mov     rbx, [rsp+28h+arg_0]
0x140002397  mov     rdi, [rsp+28h+arg_8]
0x14000239c  add     rsp, 20h
0x1400023a0  pop     r14
0x1400023a2  retn
```
