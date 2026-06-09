# Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_dynamic_initializer_for___force_initialization__

- ea: `0x140004ba0`
- end: `0x140004c33`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004ba0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004be5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004be5`

## string_xrefs

- `0x140004bcc`: `Ingestion,Uploader,Scenario,Storage,Census,ContainerHost,ContainerAgent,InProc,DevHealthMon,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 9; ++i )
    {
      v2 = off_1400197B0[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_1400197B0[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140004ba0  mov     [rsp+arg_0], rbx
0x140004ba5  mov     [rsp+arg_8], rdi
0x140004baa  push    r14
0x140004bac  sub     rsp, 20h
0x140004bb0  cmp     cs:?value@?1??_initialized@_data_HeartBeatSectionFlags@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_initialized(void)'::`2'::value
0x140004bb7  jnz     short loc_140004C22
0x140004bb9  xor     edi, edi
0x140004bbb  lea     r14, cs:140000000h
0x140004bc2  xor     ebx, ebx
0x140004bc4  mov     rcx, ds:rva off_1400197B0[r14+rbx*8]; Str
0x140004bcc  lea     rax, rva ?storage@?1??_name_storage@_data_HeartBeatSectionFlags@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Ingestion,Uploader,Scenario,Storage,Cen"... ...
0x140004bd3  add     rax, rdi
0x140004bd6  lea     rdx, Control; "= \t\n"
0x140004bdd  mov     rva ?value@?1??_name_array@_data_HeartBeatSectionFlags@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_name_array(void)'::`2'::value ...
0x140004be5  call    cs:__imp_strcspn
0x140004beb  mov     rcx, ds:rva off_1400197B0[r14+rbx*8]; "Ingestion" ...
0x140004bf3  add     rax, rdi
0x140004bf6  mov     byte ptr [rax+r14+25AE0h], 0
0x140004bff  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004c03  inc     rax
0x140004c06  cmp     byte ptr [rcx+rax], 0
0x140004c0a  jnz     short loc_140004C03
0x140004c0c  inc     rdi
0x140004c0f  inc     rbx
0x140004c12  add     rdi, rax
0x140004c15  cmp     rbx, 9
0x140004c19  jb      short loc_140004BC4
0x140004c1b  mov     cs:?value@?1??_initialized@_data_HeartBeatSectionFlags@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_HeartBeatSectionFlags::_initialized(void)'::`2'::value
0x140004c22  mov     rbx, [rsp+28h+arg_0]
0x140004c27  mov     rdi, [rsp+28h+arg_8]
0x140004c2c  add     rsp, 20h
0x140004c30  pop     r14
0x140004c32  retn
```
