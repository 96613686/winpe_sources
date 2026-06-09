# Microsoft::Diagnostics::better_enums::_data_TriggerSource::_dynamic_initializer_for___force_initialization__

- ea: `0x140007750`
- end: `0x1400077e3`
- name: `Microsoft::Diagnostics::better_enums::_data_TriggerSource::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007750`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007795`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007795`

## string_xrefs

- `0x14000777c`: `Host,Agent,Any,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_TriggerSource::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_TriggerSource::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v2 = off_14001A930[i];
      `Microsoft::Diagnostics::better_enums::_data_TriggerSource::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_TriggerSource::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A930[i];
      `Microsoft::Diagnostics::better_enums::_data_TriggerSource::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_TriggerSource::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140007750  mov     [rsp+arg_0], rbx
0x140007755  mov     [rsp+arg_8], rdi
0x14000775a  push    r14
0x14000775c  sub     rsp, 20h
0x140007760  cmp     cs:?value@?1??_initialized@_data_TriggerSource@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_TriggerSource::_initialized(void)'::`2'::value
0x140007767  jnz     short loc_1400077D2
0x140007769  xor     edi, edi
0x14000776b  lea     r14, cs:140000000h
0x140007772  xor     ebx, ebx
0x140007774  mov     rcx, ds:rva off_14001A930[r14+rbx*8]; Str
0x14000777c  lea     rax, rva ?storage@?1??_name_storage@_data_TriggerSource@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Host,Agent,Any," ...
0x140007783  add     rax, rdi
0x140007786  lea     rdx, Control; "= \t\n"
0x14000778d  mov     rva ?value@?1??_name_array@_data_TriggerSource@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_TriggerSource::_name_array(void)'::`2'::value ...
0x140007795  call    cs:__imp_strcspn
0x14000779b  mov     rcx, ds:rva off_14001A930[r14+rbx*8]; "Host" ...
0x1400077a3  add     rax, rdi
0x1400077a6  mov     byte ptr [rax+r14+26CA0h], 0
0x1400077af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400077b3  inc     rax
0x1400077b6  cmp     byte ptr [rcx+rax], 0
0x1400077ba  jnz     short loc_1400077B3
0x1400077bc  inc     rdi
0x1400077bf  inc     rbx
0x1400077c2  add     rdi, rax
0x1400077c5  cmp     rbx, 3
0x1400077c9  jb      short loc_140007774
0x1400077cb  mov     cs:?value@?1??_initialized@_data_TriggerSource@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_TriggerSource::_initialized(void)'::`2'::value
0x1400077d2  mov     rbx, [rsp+28h+arg_0]
0x1400077d7  mov     rdi, [rsp+28h+arg_8]
0x1400077dc  add     rsp, 20h
0x1400077e0  pop     r14
0x1400077e2  retn
```
