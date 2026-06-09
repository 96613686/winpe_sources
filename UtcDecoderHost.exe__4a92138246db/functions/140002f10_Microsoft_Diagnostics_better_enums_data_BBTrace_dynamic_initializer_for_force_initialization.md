# Microsoft::Diagnostics::better_enums::_data_BBTrace::_dynamic_initializer_for___force_initialization__

- ea: `0x140002f10`
- end: `0x140002fa3`
- name: `Microsoft::Diagnostics::better_enums::_data_BBTrace::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002f10`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002f55`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002f55`

## string_xrefs

- `0x140002f3c`: `EventStoreGetDataByLatency,EventStoreDeleteData,EventStoreFlushPreCompress,EventStoreClear,EventStoreFlushToFile,ETWProcessETLStart,ETWProcessETLEnd,AsimovSerializeCustomData,ThreadExitCode,TraceStartFailed,Watchdog2ndChance,EventStoreDeleteFailed,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_BBTrace::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_BBTrace::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0xC; ++i )
    {
      v2 = off_14001A780[i];
      `Microsoft::Diagnostics::better_enums::_data_BBTrace::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_BBTrace::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A780[i];
      `Microsoft::Diagnostics::better_enums::_data_BBTrace::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_BBTrace::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140002f10  mov     [rsp+arg_0], rbx
0x140002f15  mov     [rsp+arg_8], rdi
0x140002f1a  push    r14
0x140002f1c  sub     rsp, 20h
0x140002f20  cmp     cs:?value@?1??_initialized@_data_BBTrace@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_BBTrace::_initialized(void)'::`2'::value
0x140002f27  jnz     short loc_140002F92
0x140002f29  xor     edi, edi
0x140002f2b  lea     r14, cs:140000000h
0x140002f32  xor     ebx, ebx
0x140002f34  mov     rcx, ds:rva off_14001A780[r14+rbx*8]; Str
0x140002f3c  lea     rax, rva ?storage@?1??_name_storage@_data_BBTrace@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "EventStoreGetDataByLatency,EventStoreDe"... ...
0x140002f43  add     rax, rdi
0x140002f46  lea     rdx, Control; "= \t\n"
0x140002f4d  mov     rva ?value@?1??_name_array@_data_BBTrace@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_BBTrace::_name_array(void)'::`2'::value ...
0x140002f55  call    cs:__imp_strcspn
0x140002f5b  mov     rcx, ds:rva off_14001A780[r14+rbx*8]; "EventStoreGetDataByLatency" ...
0x140002f63  add     rax, rdi
0x140002f66  mov     byte ptr [rax+r14+28380h], 0
0x140002f6f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002f73  inc     rax
0x140002f76  cmp     byte ptr [rcx+rax], 0
0x140002f7a  jnz     short loc_140002F73
0x140002f7c  inc     rdi
0x140002f7f  inc     rbx
0x140002f82  add     rdi, rax
0x140002f85  cmp     rbx, 0Ch
0x140002f89  jb      short loc_140002F34
0x140002f8b  mov     cs:?value@?1??_initialized@_data_BBTrace@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_BBTrace::_initialized(void)'::`2'::value
0x140002f92  mov     rbx, [rsp+28h+arg_0]
0x140002f97  mov     rdi, [rsp+28h+arg_8]
0x140002f9c  add     rsp, 20h
0x140002fa0  pop     r14
0x140002fa2  retn
```
