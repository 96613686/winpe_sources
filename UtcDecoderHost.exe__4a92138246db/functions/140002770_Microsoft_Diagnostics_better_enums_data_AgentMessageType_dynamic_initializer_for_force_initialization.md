# Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_dynamic_initializer_for___force_initialization__

- ea: `0x140002770`
- end: `0x140002803`
- name: `Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140002770`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400027b5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400027b5`

## string_xrefs

- `0x14000279c`: `AgentInfo = 0,HostInfo,AuthorizationInfo,SamplingRules,TelemetryEvent,Disconnect,__DEPRECATED__SchemaRequests,EscalationRequest,EscalationData,StartTraceW,StopTraceW,ScenarioObjectRequest,__DEPRECATED__AgentOwnerInfo,SnapTrace,DTraceRequest,RegisterTenant,UnregisterTenant,ApiCompletion,AgentOptions,RegisterWatsonCrash,WatsonCrash,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0x15; ++i )
    {
      v2 = off_14001A9F0[i];
      `Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A9F0[i];
      `Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140002770  mov     [rsp+arg_0], rbx
0x140002775  mov     [rsp+arg_8], rdi
0x14000277a  push    r14
0x14000277c  sub     rsp, 20h
0x140002780  cmp     cs:?value@?1??_initialized@_data_AgentMessageType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_initialized(void)'::`2'::value
0x140002787  jnz     short loc_1400027F2
0x140002789  xor     edi, edi
0x14000278b  lea     r14, cs:140000000h
0x140002792  xor     ebx, ebx
0x140002794  mov     rcx, ds:rva off_14001A9F0[r14+rbx*8]; Str
0x14000279c  lea     rax, rva ?storage@?1??_name_storage@_data_AgentMessageType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "AgentInfo = 0,HostInfo,AuthorizationInf"... ...
0x1400027a3  add     rax, rdi
0x1400027a6  lea     rdx, Control; "= \t\n"
0x1400027ad  mov     rva ?value@?1??_name_array@_data_AgentMessageType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_name_array(void)'::`2'::value ...
0x1400027b5  call    cs:__imp_strcspn
0x1400027bb  mov     rcx, ds:rva off_14001A9F0[r14+rbx*8]; "AgentInfo = 0" ...
0x1400027c3  add     rax, rdi
0x1400027c6  mov     byte ptr [rax+r14+27EA0h], 0
0x1400027cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400027d3  inc     rax
0x1400027d6  cmp     byte ptr [rcx+rax], 0
0x1400027da  jnz     short loc_1400027D3
0x1400027dc  inc     rdi
0x1400027df  inc     rbx
0x1400027e2  add     rdi, rax
0x1400027e5  cmp     rbx, 15h
0x1400027e9  jb      short loc_140002794
0x1400027eb  mov     cs:?value@?1??_initialized@_data_AgentMessageType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_AgentMessageType::_initialized(void)'::`2'::value
0x1400027f2  mov     rbx, [rsp+28h+arg_0]
0x1400027f7  mov     rdi, [rsp+28h+arg_8]
0x1400027fc  add     rsp, 20h
0x140002800  pop     r14
0x140002802  retn
```
