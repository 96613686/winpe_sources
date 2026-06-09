# Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_dynamic_initializer_for___force_initialization__

- ea: `0x1400035f0`
- end: `0x140003683`
- name: `Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400035f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003635`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003635`

## string_xrefs

- `0x14000361c`: `DetermineFromRegistry,RunAsHost,RunAsAgent,RunAsInProcHost,RunAsInProcAgent,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 5; ++i )
    {
      v2 = off_14001A430[i];
      `Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A430[i];
      `Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x1400035f0  mov     [rsp+arg_0], rbx
0x1400035f5  mov     [rsp+arg_8], rdi
0x1400035fa  push    r14
0x1400035fc  sub     rsp, 20h
0x140003600  cmp     cs:?value@?1??_initialized@_data_ComponentInitializationMode@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_initialized(void)'::`2'::value
0x140003607  jnz     short loc_140003672
0x140003609  xor     edi, edi
0x14000360b  lea     r14, cs:140000000h
0x140003612  xor     ebx, ebx
0x140003614  mov     rcx, ds:rva off_14001A430[r14+rbx*8]; Str
0x14000361c  lea     rax, rva ?storage@?1??_name_storage@_data_ComponentInitializationMode@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "DetermineFromRegistry,RunAsHost,RunAsAg"... ...
0x140003623  add     rax, rdi
0x140003626  lea     rdx, Control; "= \t\n"
0x14000362d  mov     rva ?value@?1??_name_array@_data_ComponentInitializationMode@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_name_array(void)'::`2'::value ...
0x140003635  call    cs:__imp_strcspn
0x14000363b  mov     rcx, ds:rva off_14001A430[r14+rbx*8]; "DetermineFromRegistry" ...
0x140003643  add     rax, rdi
0x140003646  mov     byte ptr [rax+r14+28A00h], 0
0x14000364f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003653  inc     rax
0x140003656  cmp     byte ptr [rcx+rax], 0
0x14000365a  jnz     short loc_140003653
0x14000365c  inc     rdi
0x14000365f  inc     rbx
0x140003662  add     rdi, rax
0x140003665  cmp     rbx, 5
0x140003669  jb      short loc_140003614
0x14000366b  mov     cs:?value@?1??_initialized@_data_ComponentInitializationMode@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_ComponentInitializationMode::_initialized(void)'::`2'::value
0x140003672  mov     rbx, [rsp+28h+arg_0]
0x140003677  mov     rdi, [rsp+28h+arg_8]
0x14000367c  add     rsp, 20h
0x140003680  pop     r14
0x140003682  retn
```
