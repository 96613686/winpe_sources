# Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_dynamic_initializer_for___force_initialization__

- ea: `0x140007e80`
- end: `0x140007f13`
- name: `Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007e80`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007ec5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007ec5`

## string_xrefs

- `0x140007eac`: `Healthy = 64,DrainageZone = 65,AchievementCacheWarning1 = 80,AchievementCacheWarning2 = 90,AchievementCacheFull = 95,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 5; ++i )
    {
      v2 = off_14001A1F0[i];
      `Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A1F0[i];
      `Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140007e80  mov     [rsp+arg_0], rbx
0x140007e85  mov     [rsp+arg_8], rdi
0x140007e8a  push    r14
0x140007e8c  sub     rsp, 20h
0x140007e90  cmp     cs:?value@?1??_initialized@_data_XboxCacheStorageThresholds@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_initialized(void)'::`2'::value
0x140007e97  jnz     short loc_140007F02
0x140007e99  xor     edi, edi
0x140007e9b  lea     r14, cs:140000000h
0x140007ea2  xor     ebx, ebx
0x140007ea4  mov     rcx, ds:rva off_14001A1F0[r14+rbx*8]; Str
0x140007eac  lea     rax, rva ?storage@?1??_name_storage@_data_XboxCacheStorageThresholds@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Healthy = 64,DrainageZone = 65,Achievem"... ...
0x140007eb3  add     rax, rdi
0x140007eb6  lea     rdx, Control; "= \t\n"
0x140007ebd  mov     rva ?value@?1??_name_array@_data_XboxCacheStorageThresholds@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_name_array(void)'::`2'::value ...
0x140007ec5  call    cs:__imp_strcspn
0x140007ecb  mov     rcx, ds:rva off_14001A1F0[r14+rbx*8]; "Healthy = 64" ...
0x140007ed3  add     rax, rdi
0x140007ed6  mov     byte ptr [rax+r14+268F0h], 0
0x140007edf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007ee3  inc     rax
0x140007ee6  cmp     byte ptr [rcx+rax], 0
0x140007eea  jnz     short loc_140007EE3
0x140007eec  inc     rdi
0x140007eef  inc     rbx
0x140007ef2  add     rdi, rax
0x140007ef5  cmp     rbx, 5
0x140007ef9  jb      short loc_140007EA4
0x140007efb  mov     cs:?value@?1??_initialized@_data_XboxCacheStorageThresholds@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_XboxCacheStorageThresholds::_initialized(void)'::`2'::value
0x140007f02  mov     rbx, [rsp+28h+arg_0]
0x140007f07  mov     rdi, [rsp+28h+arg_8]
0x140007f0c  add     rsp, 20h
0x140007f10  pop     r14
0x140007f12  retn
```
