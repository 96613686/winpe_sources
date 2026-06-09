# Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_dynamic_initializer_for___force_initialization__

- ea: `0x140006270`
- end: `0x140006303`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006270`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400062b5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400062b5`

## string_xrefs

- `0x14000629c`: `ExcessiveCompletion,ExcessiveExpiration,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 2; ++i )
    {
      v2 = off_140019590[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019590[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140006270  mov     [rsp+arg_0], rbx
0x140006275  mov     [rsp+arg_8], rdi
0x14000627a  push    r14
0x14000627c  sub     rsp, 20h
0x140006280  cmp     cs:?value@?1??_initialized@_data_ScenarioThrottledReason@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_initialized(void)'::`2'::value
0x140006287  jnz     short loc_1400062F2
0x140006289  xor     edi, edi
0x14000628b  lea     r14, cs:140000000h
0x140006292  xor     ebx, ebx
0x140006294  mov     rcx, ds:rva off_140019590[r14+rbx*8]; Str
0x14000629c  lea     rax, rva ?storage@?1??_name_storage@_data_ScenarioThrottledReason@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "ExcessiveCompletion,ExcessiveExpiration"... ...
0x1400062a3  add     rax, rdi
0x1400062a6  lea     rdx, Control; "= \t\n"
0x1400062ad  mov     rva ?value@?1??_name_array@_data_ScenarioThrottledReason@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_name_array(void)'::`2'::value ...
0x1400062b5  call    cs:__imp_strcspn
0x1400062bb  mov     rcx, ds:rva off_140019590[r14+rbx*8]; "ExcessiveCompletion" ...
0x1400062c3  add     rax, rdi
0x1400062c6  mov     byte ptr [rax+r14+28530h], 0
0x1400062cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400062d3  inc     rax
0x1400062d6  cmp     byte ptr [rcx+rax], 0
0x1400062da  jnz     short loc_1400062D3
0x1400062dc  inc     rdi
0x1400062df  inc     rbx
0x1400062e2  add     rdi, rax
0x1400062e5  cmp     rbx, 2
0x1400062e9  jb      short loc_140006294
0x1400062eb  mov     cs:?value@?1??_initialized@_data_ScenarioThrottledReason@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioThrottledReason::_initialized(void)'::`2'::value
0x1400062f2  mov     rbx, [rsp+28h+arg_0]
0x1400062f7  mov     rdi, [rsp+28h+arg_8]
0x1400062fc  add     rsp, 20h
0x140006300  pop     r14
0x140006302  retn
```
