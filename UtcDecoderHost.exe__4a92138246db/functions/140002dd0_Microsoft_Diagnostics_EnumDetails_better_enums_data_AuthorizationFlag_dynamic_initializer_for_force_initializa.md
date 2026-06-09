# Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_dynamic_initializer_for___force_initialization__

- ea: `0x140002dd0`
- end: `0x140002e63`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140002dd0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002e15`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002e15`

## string_xrefs

- `0x140002dfc`: `CanCollectAnyTelemetry = (1 << 0),CanCollectHeartbeats = (1 << 1),CanCollectCoreTelemetry = (1 << 2),CanCollectOsTelemetry = (1 << 3),CanReportScenarios = (1 << 4),CanAddMsaToMsTelemetry = (1 << 5),DEPRECATED_CanPerformTraceEscalations = (1 << 6),CanPerformDiagnosticEscalations = (1 << 7),CanUseAuthenticatedProxy = (1 << 8),CanReportUifEscalations = (1 << 9),CanCollectAnalyticsEvents = (1 << 10),CanPerformSiufEscalations = (1 << 11),IsControllerMode = (1 << 12),CanCollectClearUserIds = (1 << 13)`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0x11; ++i )
    {
      v2 = off_1400195C0[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_1400195C0[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140002dd0  mov     [rsp+arg_0], rbx
0x140002dd5  mov     [rsp+arg_8], rdi
0x140002dda  push    r14
0x140002ddc  sub     rsp, 20h
0x140002de0  cmp     cs:?value@?1??_initialized@_data_AuthorizationFlag@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_initialized(void)'::`2'::value
0x140002de7  jnz     short loc_140002E52
0x140002de9  xor     edi, edi
0x140002deb  lea     r14, cs:140000000h
0x140002df2  xor     ebx, ebx
0x140002df4  mov     rcx, ds:rva off_1400195C0[r14+rbx*8]; Str
0x140002dfc  lea     rax, rva ?storage@?1??_name_storage@_data_AuthorizationFlag@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "CanCollectAnyTelemetry = (1 << 0),CanCo"... ...
0x140002e03  add     rax, rdi
0x140002e06  lea     rdx, Control; "= \t\n"
0x140002e0d  mov     rva ?value@?1??_name_array@_data_AuthorizationFlag@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_name_array(void)'::`2'::value ...
0x140002e15  call    cs:__imp_strcspn
0x140002e1b  mov     rcx, ds:rva off_1400195C0[r14+rbx*8]; "CanCollectAnyTelemetry = (1 << 0)" ...
0x140002e23  add     rax, rdi
0x140002e26  mov     byte ptr [rax+r14+26E40h], 0
0x140002e2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002e33  inc     rax
0x140002e36  cmp     byte ptr [rcx+rax], 0
0x140002e3a  jnz     short loc_140002E33
0x140002e3c  inc     rdi
0x140002e3f  inc     rbx
0x140002e42  add     rdi, rax
0x140002e45  cmp     rbx, 11h
0x140002e49  jb      short loc_140002DF4
0x140002e4b  mov     cs:?value@?1??_initialized@_data_AuthorizationFlag@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_AuthorizationFlag::_initialized(void)'::`2'::value
0x140002e52  mov     rbx, [rsp+28h+arg_0]
0x140002e57  mov     rdi, [rsp+28h+arg_8]
0x140002e5c  add     rsp, 20h
0x140002e60  pop     r14
0x140002e62  retn
```
