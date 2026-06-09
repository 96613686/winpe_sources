# Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_dynamic_initializer_for___force_initialization__

- ea: `0x1400026d0`
- end: `0x140002763`
- name: `Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400026d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002715`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002715`

## string_xrefs

- `0x1400026fc`: `TransmitJsonString = 1,RelogEventToEtw = 2,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      v2 = off_14001A0F0[i];
      `Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A0F0[i];
      `Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x1400026d0  mov     [rsp+arg_0], rbx
0x1400026d5  mov     [rsp+arg_8], rdi
0x1400026da  push    r14
0x1400026dc  sub     rsp, 20h
0x1400026e0  cmp     cs:?value@?1??_initialized@_data_AgentMessageFlags@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_initialized(void)'::`2'::value
0x1400026e7  jnz     short loc_140002752
0x1400026e9  xor     edi, edi
0x1400026eb  lea     r14, cs:140000000h
0x1400026f2  xor     ebx, ebx
0x1400026f4  mov     rcx, ds:rva off_14001A0F0[r14+rbx*8]; Str
0x1400026fc  lea     rax, rva ?storage@?1??_name_storage@_data_AgentMessageFlags@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "TransmitJsonString = 1,RelogEventToEtw "... ...
0x140002703  add     rax, rdi
0x140002706  lea     rdx, Control; "= \t\n"
0x14000270d  mov     rva ?value@?1??_name_array@_data_AgentMessageFlags@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_name_array(void)'::`2'::value ...
0x140002715  call    cs:__imp_strcspn
0x14000271b  mov     rcx, ds:rva off_14001A0F0[r14+rbx*8]; "TransmitJsonString = 1" ...
0x140002723  add     rax, rdi
0x140002726  mov     byte ptr [rax+r14+273E0h], 0
0x14000272f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002733  inc     rax
0x140002736  cmp     byte ptr [rcx+rax], 0
0x14000273a  jnz     short loc_140002733
0x14000273c  inc     rdi
0x14000273f  inc     rbx
0x140002742  add     rdi, rax
0x140002745  cmp     rbx, 2
0x140002749  jb      short loc_1400026F4
0x14000274b  mov     cs:?value@?1??_initialized@_data_AgentMessageFlags@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_AgentMessageFlags::_initialized(void)'::`2'::value
0x140002752  mov     rbx, [rsp+28h+arg_0]
0x140002757  mov     rdi, [rsp+28h+arg_8]
0x14000275c  add     rsp, 20h
0x140002760  pop     r14
0x140002762  retn
```
