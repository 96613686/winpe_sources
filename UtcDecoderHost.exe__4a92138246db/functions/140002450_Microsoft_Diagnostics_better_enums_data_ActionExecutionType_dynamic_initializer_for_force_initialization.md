# Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_dynamic_initializer_for___force_initialization__

- ea: `0x140002450`
- end: `0x1400024e3`
- name: `Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002450`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002495`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002495`

## string_xrefs

- `0x14000247c`: `EscalationOnComplete,EscalationOnFail,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      v2 = off_14001A130[i];
      `Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A130[i];
      `Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140002450  mov     [rsp+arg_0], rbx
0x140002455  mov     [rsp+arg_8], rdi
0x14000245a  push    r14
0x14000245c  sub     rsp, 20h
0x140002460  cmp     cs:?value@?1??_initialized@_data_ActionExecutionType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_initialized(void)'::`2'::value
0x140002467  jnz     short loc_1400024D2
0x140002469  xor     edi, edi
0x14000246b  lea     r14, cs:140000000h
0x140002472  xor     ebx, ebx
0x140002474  mov     rcx, ds:rva off_14001A130[r14+rbx*8]; Str
0x14000247c  lea     rax, rva ?storage@?1??_name_storage@_data_ActionExecutionType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "EscalationOnComplete,EscalationOnFail," ...
0x140002483  add     rax, rdi
0x140002486  lea     rdx, Control; "= \t\n"
0x14000248d  mov     rva ?value@?1??_name_array@_data_ActionExecutionType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_name_array(void)'::`2'::value ...
0x140002495  call    cs:__imp_strcspn
0x14000249b  mov     rcx, ds:rva off_14001A130[r14+rbx*8]; "EscalationOnComplete" ...
0x1400024a3  add     rax, rdi
0x1400024a6  mov     byte ptr [rax+r14+264A0h], 0
0x1400024af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400024b3  inc     rax
0x1400024b6  cmp     byte ptr [rcx+rax], 0
0x1400024ba  jnz     short loc_1400024B3
0x1400024bc  inc     rdi
0x1400024bf  inc     rbx
0x1400024c2  add     rdi, rax
0x1400024c5  cmp     rbx, 2
0x1400024c9  jb      short loc_140002474
0x1400024cb  mov     cs:?value@?1??_initialized@_data_ActionExecutionType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_ActionExecutionType::_initialized(void)'::`2'::value
0x1400024d2  mov     rbx, [rsp+28h+arg_0]
0x1400024d7  mov     rdi, [rsp+28h+arg_8]
0x1400024dc  add     rsp, 20h
0x1400024e0  pop     r14
0x1400024e2  retn
```
