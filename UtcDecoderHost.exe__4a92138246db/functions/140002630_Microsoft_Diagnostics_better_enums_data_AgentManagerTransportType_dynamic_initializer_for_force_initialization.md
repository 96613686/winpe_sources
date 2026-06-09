# Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_dynamic_initializer_for___force_initialization__

- ea: `0x140002630`
- end: `0x1400026c3`
- name: `Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002630`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002675`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002675`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      v2 = off_14001A080[i];
      `Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A080[i];
      `Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140002630  mov     [rsp+arg_0], rbx
0x140002635  mov     [rsp+arg_8], rdi
0x14000263a  push    r14
0x14000263c  sub     rsp, 20h
0x140002640  cmp     cs:?value@?1??_initialized@_data_AgentManagerTransportType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_initialized(void)'::`2'::value
0x140002647  jnz     short loc_1400026B2
0x140002649  xor     edi, edi
0x14000264b  lea     r14, cs:140000000h
0x140002652  xor     ebx, ebx
0x140002654  mov     rcx, ds:rva off_14001A080[r14+rbx*8]; Str
0x14000265c  lea     rax, rva ?storage@?1??_name_storage@_data_AgentManagerTransportType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Windows,Linux," ...
0x140002663  add     rax, rdi
0x140002666  lea     rdx, Control; "= \t\n"
0x14000266d  mov     rva ?value@?1??_name_array@_data_AgentManagerTransportType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_name_array(void)'::`2'::value ...
0x140002675  call    cs:__imp_strcspn
0x14000267b  mov     rcx, ds:rva off_14001A080[r14+rbx*8]; "Windows" ...
0x140002683  add     rax, rdi
0x140002686  mov     byte ptr [rax+r14+25810h], 0
0x14000268f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002693  inc     rax
0x140002696  cmp     byte ptr [rcx+rax], 0
0x14000269a  jnz     short loc_140002693
0x14000269c  inc     rdi
0x14000269f  inc     rbx
0x1400026a2  add     rdi, rax
0x1400026a5  cmp     rbx, 2
0x1400026a9  jb      short loc_140002654
0x1400026ab  mov     cs:?value@?1??_initialized@_data_AgentManagerTransportType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_AgentManagerTransportType::_initialized(void)'::`2'::value
0x1400026b2  mov     rbx, [rsp+28h+arg_0]
0x1400026b7  mov     rdi, [rsp+28h+arg_8]
0x1400026bc  add     rsp, 20h
0x1400026c0  pop     r14
0x1400026c2  retn
```
