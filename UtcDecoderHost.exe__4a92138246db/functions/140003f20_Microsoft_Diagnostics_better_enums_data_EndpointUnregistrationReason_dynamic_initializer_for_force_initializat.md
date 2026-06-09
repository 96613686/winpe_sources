# Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_dynamic_initializer_for___force_initialization__

- ea: `0x140003f20`
- end: `0x140003fb3`
- name: `Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003f20`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003f65`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140003f65`

## string_xrefs

- `0x140003f4c`: `BadSevilleConstructor = 0,DisableRpcCall = 1,LoadAllSettingsFile_EndpointInactive = 2,LoadSettingsFromFile_Expired = 3,DownloadSettingsForNamespace_Expired = 4,DownloadSettingsForNamespace_IncorrectSize = 5,PerformNamespaceDownload_NoContent = 6,ParseSettings_ChangedType = 7,OnDownloadLatestSettingsEvent_FailedDownload = 8,LoadScenariosFromXmlImpl_EndpointInactive = 9,OnEndScenarioParsing_MiniSlotNotEnabled = 10,DevHealthMonTenantDisabled = 11,AadStatusChanged = 12,Test = 99,Other = 100,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0xF; ++i )
    {
      v2 = off_14001A320[i];
      `Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A320[i];
      `Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140003f20  mov     [rsp+arg_0], rbx
0x140003f25  mov     [rsp+arg_8], rdi
0x140003f2a  push    r14
0x140003f2c  sub     rsp, 20h
0x140003f30  cmp     cs:?value@?1??_initialized@_data_EndpointUnregistrationReason@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_initialized(void)'::`2'::value
0x140003f37  jnz     short loc_140003FA2
0x140003f39  xor     edi, edi
0x140003f3b  lea     r14, cs:140000000h
0x140003f42  xor     ebx, ebx
0x140003f44  mov     rcx, ds:rva off_14001A320[r14+rbx*8]; Str
0x140003f4c  lea     rax, rva ?storage@?1??_name_storage@_data_EndpointUnregistrationReason@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "BadSevilleConstructor = 0,DisableRpcCal"... ...
0x140003f53  add     rax, rdi
0x140003f56  lea     rdx, Control; "= \t\n"
0x140003f5d  mov     rva ?value@?1??_name_array@_data_EndpointUnregistrationReason@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_name_array(void)'::`2'::value ...
0x140003f65  call    cs:__imp_strcspn
0x140003f6b  mov     rcx, ds:rva off_14001A320[r14+rbx*8]; "BadSevilleConstructor = 0" ...
0x140003f73  add     rax, rdi
0x140003f76  mov     byte ptr [rax+r14+27AC0h], 0
0x140003f7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003f83  inc     rax
0x140003f86  cmp     byte ptr [rcx+rax], 0
0x140003f8a  jnz     short loc_140003F83
0x140003f8c  inc     rdi
0x140003f8f  inc     rbx
0x140003f92  add     rdi, rax
0x140003f95  cmp     rbx, 0Fh
0x140003f99  jb      short loc_140003F44
0x140003f9b  mov     cs:?value@?1??_initialized@_data_EndpointUnregistrationReason@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_EndpointUnregistrationReason::_initialized(void)'::`2'::value
0x140003fa2  mov     rbx, [rsp+28h+arg_0]
0x140003fa7  mov     rdi, [rsp+28h+arg_8]
0x140003fac  add     rsp, 20h
0x140003fb0  pop     r14
0x140003fb2  retn
```
