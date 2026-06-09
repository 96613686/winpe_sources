# Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_dynamic_initializer_for___force_initialization__

- ea: `0x140004920`
- end: `0x1400049b3`
- name: `Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004920`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004965`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140004965`

## string_xrefs

- `0x14000494c`: `CallbackOnFile,CallbackOnDirectory,Recurse,`

## pseudocode

```c
void Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v2 = off_14001AF80[i];
      `Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001AF80[i];
      `Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140004920  mov     [rsp+arg_0], rbx
0x140004925  mov     [rsp+arg_8], rdi
0x14000492a  push    r14
0x14000492c  sub     rsp, 20h
0x140004930  cmp     cs:?value@?1??_initialized@_data_FileSystemItemFlags@better_enums@EnumDetails@Utils@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_initialized(void)'::`2'::value
0x140004937  jnz     short loc_1400049A2
0x140004939  xor     edi, edi
0x14000493b  lea     r14, cs:140000000h
0x140004942  xor     ebx, ebx
0x140004944  mov     rcx, ds:rva off_14001AF80[r14+rbx*8]; Str
0x14000494c  lea     rax, rva ?storage@?1??_name_storage@_data_FileSystemItemFlags@better_enums@EnumDetails@Utils@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "CallbackOnFile,CallbackOnDirectory,Recu"... ...
0x140004953  add     rax, rdi
0x140004956  lea     rdx, Control; "= \t\n"
0x14000495d  mov     rva ?value@?1??_name_array@_data_FileSystemItemFlags@better_enums@EnumDetails@Utils@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_name_array(void)'::`2'::value ...
0x140004965  call    cs:__imp_strcspn
0x14000496b  mov     rcx, ds:rva off_14001AF80[r14+rbx*8]; "CallbackOnFile" ...
0x140004973  add     rax, rdi
0x140004976  mov     byte ptr [rax+r14+258C0h], 0
0x14000497f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004983  inc     rax
0x140004986  cmp     byte ptr [rcx+rax], 0
0x14000498a  jnz     short loc_140004983
0x14000498c  inc     rdi
0x14000498f  inc     rbx
0x140004992  add     rdi, rax
0x140004995  cmp     rbx, 3
0x140004999  jb      short loc_140004944
0x14000499b  mov     cs:?value@?1??_initialized@_data_FileSystemItemFlags@better_enums@EnumDetails@Utils@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::Utils::EnumDetails::better_enums::_data_FileSystemItemFlags::_initialized(void)'::`2'::value
0x1400049a2  mov     rbx, [rsp+28h+arg_0]
0x1400049a7  mov     rdi, [rsp+28h+arg_8]
0x1400049ac  add     rsp, 20h
0x1400049b0  pop     r14
0x1400049b2  retn
```
