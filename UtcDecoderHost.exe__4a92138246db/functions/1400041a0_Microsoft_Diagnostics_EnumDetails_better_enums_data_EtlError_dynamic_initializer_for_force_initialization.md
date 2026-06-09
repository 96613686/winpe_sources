# Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_dynamic_initializer_for___force_initialization__

- ea: `0x1400041a0`
- end: `0x140004233`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400041a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400041e5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400041e5`

## string_xrefs

- `0x1400041cc`: `NoError = 0,NoSettingsAvailable = 1,NotAuthorizedToProcessShutdownLoggerETL = 2,NotAuthorizedToProcessETLLogs = 3,NotAuthorizedToProcessAutoLoggerLoggerETL = 4,FailingOpenETWTraceWhenProcessingEtlFile = 5,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 6; ++i )
    {
      v2 = off_140019800[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019800[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x1400041a0  mov     [rsp+arg_0], rbx
0x1400041a5  mov     [rsp+arg_8], rdi
0x1400041aa  push    r14
0x1400041ac  sub     rsp, 20h
0x1400041b0  cmp     cs:?value@?1??_initialized@_data_EtlError@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_initialized(void)'::`2'::value
0x1400041b7  jnz     short loc_140004222
0x1400041b9  xor     edi, edi
0x1400041bb  lea     r14, cs:140000000h
0x1400041c2  xor     ebx, ebx
0x1400041c4  mov     rcx, ds:rva off_140019800[r14+rbx*8]; Str
0x1400041cc  lea     rax, rva ?storage@?1??_name_storage@_data_EtlError@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "NoError = 0,NoSettingsAvailable = 1,Not"... ...
0x1400041d3  add     rax, rdi
0x1400041d6  lea     rdx, Control; "= \t\n"
0x1400041dd  mov     rva ?value@?1??_name_array@_data_EtlError@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_name_array(void)'::`2'::value ...
0x1400041e5  call    cs:__imp_strcspn
0x1400041eb  mov     rcx, ds:rva off_140019800[r14+rbx*8]; "NoError = 0" ...
0x1400041f3  add     rax, rdi
0x1400041f6  mov     byte ptr [rax+r14+262A0h], 0
0x1400041ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004203  inc     rax
0x140004206  cmp     byte ptr [rcx+rax], 0
0x14000420a  jnz     short loc_140004203
0x14000420c  inc     rdi
0x14000420f  inc     rbx
0x140004212  add     rdi, rax
0x140004215  cmp     rbx, 6
0x140004219  jb      short loc_1400041C4
0x14000421b  mov     cs:?value@?1??_initialized@_data_EtlError@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_EtlError::_initialized(void)'::`2'::value
0x140004222  mov     rbx, [rsp+28h+arg_0]
0x140004227  mov     rdi, [rsp+28h+arg_8]
0x14000422c  add     rsp, 20h
0x140004230  pop     r14
0x140004232  retn
```
