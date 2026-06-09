# Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_dynamic_initializer_for___force_initialization__

- ea: `0x140006fd0`
- end: `0x140007063`
- name: `Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006fd0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007015`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007015`

## string_xrefs

- `0x140006ffc`: `Security,Basic,Enhanced,Full,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 4; ++i )
    {
      v2 = off_14001A650[i];
      `Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A650[i];
      `Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140006fd0  mov     [rsp+arg_0], rbx
0x140006fd5  mov     [rsp+arg_8], rdi
0x140006fda  push    r14
0x140006fdc  sub     rsp, 20h
0x140006fe0  cmp     cs:?value@?1??_initialized@_data_TelemetryPermissionLevel@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_initialized(void)'::`2'::value
0x140006fe7  jnz     short loc_140007052
0x140006fe9  xor     edi, edi
0x140006feb  lea     r14, cs:140000000h
0x140006ff2  xor     ebx, ebx
0x140006ff4  mov     rcx, ds:rva off_14001A650[r14+rbx*8]; Str
0x140006ffc  lea     rax, rva ?storage@?1??_name_storage@_data_TelemetryPermissionLevel@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Security,Basic,Enhanced,Full," ...
0x140007003  add     rax, rdi
0x140007006  lea     rdx, Control; "= \t\n"
0x14000700d  mov     rva ?value@?1??_name_array@_data_TelemetryPermissionLevel@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_name_array(void)'::`2'::value ...
0x140007015  call    cs:__imp_strcspn
0x14000701b  mov     rcx, ds:rva off_14001A650[r14+rbx*8]; "Security" ...
0x140007023  add     rax, rdi
0x140007026  mov     byte ptr [rax+r14+287A0h], 0
0x14000702f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007033  inc     rax
0x140007036  cmp     byte ptr [rcx+rax], 0
0x14000703a  jnz     short loc_140007033
0x14000703c  inc     rdi
0x14000703f  inc     rbx
0x140007042  add     rdi, rax
0x140007045  cmp     rbx, 4
0x140007049  jb      short loc_140006FF4
0x14000704b  mov     cs:?value@?1??_initialized@_data_TelemetryPermissionLevel@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_TelemetryPermissionLevel::_initialized(void)'::`2'::value
0x140007052  mov     rbx, [rsp+28h+arg_0]
0x140007057  mov     rdi, [rsp+28h+arg_8]
0x14000705c  add     rsp, 20h
0x140007060  pop     r14
0x140007062  retn
```
