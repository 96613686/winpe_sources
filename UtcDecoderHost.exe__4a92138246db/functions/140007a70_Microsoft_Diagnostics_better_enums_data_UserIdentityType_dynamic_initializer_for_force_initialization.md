# Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_dynamic_initializer_for___force_initialization__

- ea: `0x140007a70`
- end: `0x140007b03`
- name: `Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007a70`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007ab5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007ab5`

## string_xrefs

- `0x140007a9c`: `MsaSafeCustomerId = 0,MsaUserTicket = 1,UserSpecificMsaDeviceTicket = 2,AadObjectId = 3,XToken = 4,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 5; ++i )
    {
      v2 = off_14001A1C0[i];
      `Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A1C0[i];
      `Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140007a70  mov     [rsp+arg_0], rbx
0x140007a75  mov     [rsp+arg_8], rdi
0x140007a7a  push    r14
0x140007a7c  sub     rsp, 20h
0x140007a80  cmp     cs:?value@?1??_initialized@_data_UserIdentityType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_initialized(void)'::`2'::value
0x140007a87  jnz     short loc_140007AF2
0x140007a89  xor     edi, edi
0x140007a8b  lea     r14, cs:140000000h
0x140007a92  xor     ebx, ebx
0x140007a94  mov     rcx, ds:rva off_14001A1C0[r14+rbx*8]; Str
0x140007a9c  lea     rax, rva ?storage@?1??_name_storage@_data_UserIdentityType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "MsaSafeCustomerId = 0,MsaUserTicket = 1"... ...
0x140007aa3  add     rax, rdi
0x140007aa6  lea     rdx, Control; "= \t\n"
0x140007aad  mov     rva ?value@?1??_name_array@_data_UserIdentityType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_name_array(void)'::`2'::value ...
0x140007ab5  call    cs:__imp_strcspn
0x140007abb  mov     rcx, ds:rva off_14001A1C0[r14+rbx*8]; "MsaSafeCustomerId = 0" ...
0x140007ac3  add     rax, rdi
0x140007ac6  mov     byte ptr [rax+r14+27DD0h], 0
0x140007acf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007ad3  inc     rax
0x140007ad6  cmp     byte ptr [rcx+rax], 0
0x140007ada  jnz     short loc_140007AD3
0x140007adc  inc     rdi
0x140007adf  inc     rbx
0x140007ae2  add     rdi, rax
0x140007ae5  cmp     rbx, 5
0x140007ae9  jb      short loc_140007A94
0x140007aeb  mov     cs:?value@?1??_initialized@_data_UserIdentityType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_UserIdentityType::_initialized(void)'::`2'::value
0x140007af2  mov     rbx, [rsp+28h+arg_0]
0x140007af7  mov     rdi, [rsp+28h+arg_8]
0x140007afc  add     rsp, 20h
0x140007b00  pop     r14
0x140007b02  retn
```
