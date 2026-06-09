# Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_dynamic_initializer_for___force_initialization__

- ea: `0x1400042e0`
- end: `0x140004373`
- name: `Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400042e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004325`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004325`

## string_xrefs

- `0x14000430c`: `Unknown,KernelWmiEvent,TeiFromPayload,FromTraceEventInfoTlg,TdhGetEventInformationFuncPtr_unused,TdhGetEventInformation,FromTraceEventInfoMan,GetProvider,ProviderGetEventInformation,TdhFacadeOutOfMemory,JsonBuilderOutOfMemory,JsonBuilderOther,GeneralOutOfMemory,UnknownUtcException,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0xE; ++i )
    {
      v2 = off_14001A3A0[i];
      `Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A3A0[i];
      `Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x1400042e0  mov     [rsp+arg_0], rbx
0x1400042e5  mov     [rsp+arg_8], rdi
0x1400042ea  push    r14
0x1400042ec  sub     rsp, 20h
0x1400042f0  cmp     cs:?value@?1??_initialized@_data_EtwDecodingFailureSite@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_initialized(void)'::`2'::value
0x1400042f7  jnz     short loc_140004362
0x1400042f9  xor     edi, edi
0x1400042fb  lea     r14, cs:140000000h
0x140004302  xor     ebx, ebx
0x140004304  mov     rcx, ds:rva off_14001A3A0[r14+rbx*8]; Str
0x14000430c  lea     rax, rva ?storage@?1??_name_storage@_data_EtwDecodingFailureSite@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Unknown,KernelWmiEvent,TeiFromPayload,F"... ...
0x140004313  add     rax, rdi
0x140004316  lea     rdx, Control; "= \t\n"
0x14000431d  mov     rva ?value@?1??_name_array@_data_EtwDecodingFailureSite@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_name_array(void)'::`2'::value ...
0x140004325  call    cs:__imp_strcspn
0x14000432b  mov     rcx, ds:rva off_14001A3A0[r14+rbx*8]; "Unknown" ...
0x140004333  add     rax, rdi
0x140004336  mov     byte ptr [rax+r14+259A0h], 0
0x14000433f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004343  inc     rax
0x140004346  cmp     byte ptr [rcx+rax], 0
0x14000434a  jnz     short loc_140004343
0x14000434c  inc     rdi
0x14000434f  inc     rbx
0x140004352  add     rdi, rax
0x140004355  cmp     rbx, 0Eh
0x140004359  jb      short loc_140004304
0x14000435b  mov     cs:?value@?1??_initialized@_data_EtwDecodingFailureSite@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_EtwDecodingFailureSite::_initialized(void)'::`2'::value
0x140004362  mov     rbx, [rsp+28h+arg_0]
0x140004367  mov     rdi, [rsp+28h+arg_8]
0x14000436c  add     rsp, 20h
0x140004370  pop     r14
0x140004372  retn
```
