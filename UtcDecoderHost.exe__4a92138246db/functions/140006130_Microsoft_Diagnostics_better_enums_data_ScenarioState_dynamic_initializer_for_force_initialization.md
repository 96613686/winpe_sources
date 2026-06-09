# Microsoft::Diagnostics::better_enums::_data_ScenarioState::_dynamic_initializer_for___force_initialization__

- ea: `0x140006130`
- end: `0x1400061c3`
- name: `Microsoft::Diagnostics::better_enums::_data_ScenarioState::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006130`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006175`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006175`

## string_xrefs

- `0x14000615c`: `Created,TriggerMatched,TriggerlessMatched,Completed,CompletionReported,CancellationReported,FailureReported,CompletionEscalated,FailureEscalated,TelemetryCreated,TelemetryTriggerMatched,TelemetryCompletionReported,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_ScenarioState::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_ScenarioState::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0xC; ++i )
    {
      v2 = off_14001A020[i];
      `Microsoft::Diagnostics::better_enums::_data_ScenarioState::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_ScenarioState::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A020[i];
      `Microsoft::Diagnostics::better_enums::_data_ScenarioState::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_ScenarioState::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140006130  mov     [rsp+arg_0], rbx
0x140006135  mov     [rsp+arg_8], rdi
0x14000613a  push    r14
0x14000613c  sub     rsp, 20h
0x140006140  cmp     cs:?value@?1??_initialized@_data_ScenarioState@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_ScenarioState::_initialized(void)'::`2'::value
0x140006147  jnz     short loc_1400061B2
0x140006149  xor     edi, edi
0x14000614b  lea     r14, cs:140000000h
0x140006152  xor     ebx, ebx
0x140006154  mov     rcx, ds:rva off_14001A020[r14+rbx*8]; Str
0x14000615c  lea     rax, rva ?storage@?1??_name_storage@_data_ScenarioState@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Created,TriggerMatched,TriggerlessMatch"... ...
0x140006163  add     rax, rdi
0x140006166  lea     rdx, Control; "= \t\n"
0x14000616d  mov     rva ?value@?1??_name_array@_data_ScenarioState@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_ScenarioState::_name_array(void)'::`2'::value ...
0x140006175  call    cs:__imp_strcspn
0x14000617b  mov     rcx, ds:rva off_14001A020[r14+rbx*8]; "Created" ...
0x140006183  add     rax, rdi
0x140006186  mov     byte ptr [rax+r14+26A30h], 0
0x14000618f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006193  inc     rax
0x140006196  cmp     byte ptr [rcx+rax], 0
0x14000619a  jnz     short loc_140006193
0x14000619c  inc     rdi
0x14000619f  inc     rbx
0x1400061a2  add     rdi, rax
0x1400061a5  cmp     rbx, 0Ch
0x1400061a9  jb      short loc_140006154
0x1400061ab  mov     cs:?value@?1??_initialized@_data_ScenarioState@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_ScenarioState::_initialized(void)'::`2'::value
0x1400061b2  mov     rbx, [rsp+28h+arg_0]
0x1400061b7  mov     rdi, [rsp+28h+arg_8]
0x1400061bc  add     rsp, 20h
0x1400061c0  pop     r14
0x1400061c2  retn
```
