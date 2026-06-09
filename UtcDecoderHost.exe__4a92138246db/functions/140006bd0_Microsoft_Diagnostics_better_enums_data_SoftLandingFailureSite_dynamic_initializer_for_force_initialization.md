# Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_dynamic_initializer_for___force_initialization__

- ea: `0x140006bd0`
- end: `0x140006c63`
- name: `Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140006bd0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006c15`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006c15`

## string_xrefs

- `0x140006bfc`: `DisabledViaTestHook,NoSessionId,FailedToGetSlFolderForUser,SlFolderForUserEmpty,FailedToCopyFilesFromSlFolder,FailedToVerifyTrust,FailedToCopyToUtcFolder,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 7; ++i )
    {
      v2 = off_140019E30[i];
      `Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019E30[i];
      `Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140006bd0  mov     [rsp+arg_0], rbx
0x140006bd5  mov     [rsp+arg_8], rdi
0x140006bda  push    r14
0x140006bdc  sub     rsp, 20h
0x140006be0  cmp     cs:?value@?1??_initialized@_data_SoftLandingFailureSite@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_initialized(void)'::`2'::value
0x140006be7  jnz     short loc_140006C52
0x140006be9  xor     edi, edi
0x140006beb  lea     r14, cs:140000000h
0x140006bf2  xor     ebx, ebx
0x140006bf4  mov     rcx, ds:rva off_140019E30[r14+rbx*8]; Str
0x140006bfc  lea     rax, rva ?storage@?1??_name_storage@_data_SoftLandingFailureSite@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "DisabledViaTestHook,NoSessionId,FailedT"... ...
0x140006c03  add     rax, rdi
0x140006c06  lea     rdx, Control; "= \t\n"
0x140006c0d  mov     rva ?value@?1??_name_array@_data_SoftLandingFailureSite@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_name_array(void)'::`2'::value ...
0x140006c15  call    cs:__imp_strcspn
0x140006c1b  mov     rcx, ds:rva off_140019E30[r14+rbx*8]; "DisabledViaTestHook" ...
0x140006c23  add     rax, rdi
0x140006c26  mov     byte ptr [rax+r14+25820h], 0
0x140006c2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006c33  inc     rax
0x140006c36  cmp     byte ptr [rcx+rax], 0
0x140006c3a  jnz     short loc_140006C33
0x140006c3c  inc     rdi
0x140006c3f  inc     rbx
0x140006c42  add     rdi, rax
0x140006c45  cmp     rbx, 7
0x140006c49  jb      short loc_140006BF4
0x140006c4b  mov     cs:?value@?1??_initialized@_data_SoftLandingFailureSite@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_SoftLandingFailureSite::_initialized(void)'::`2'::value
0x140006c52  mov     rbx, [rsp+28h+arg_0]
0x140006c57  mov     rdi, [rsp+28h+arg_8]
0x140006c5c  add     rsp, 20h
0x140006c60  pop     r14
0x140006c62  retn
```
