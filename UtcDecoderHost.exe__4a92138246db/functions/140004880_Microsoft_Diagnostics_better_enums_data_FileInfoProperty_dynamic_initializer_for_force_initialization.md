# Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_dynamic_initializer_for___force_initialization__

- ea: `0x140004880`
- end: `0x140004913`
- name: `Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004880`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400048c5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400048c5`

## string_xrefs

- `0x1400048ac`: `None,FileId,ProgId,Description,FileVer,BinFileVerMajor,BinFileVerMinor,BinFileVerBuild,BinFileVerRev,VerLang,ProductName,Company,ProductVer,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0xD; ++i )
    {
      v2 = off_14001AAF0[i];
      `Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001AAF0[i];
      `Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140004880  mov     [rsp+arg_0], rbx
0x140004885  mov     [rsp+arg_8], rdi
0x14000488a  push    r14
0x14000488c  sub     rsp, 20h
0x140004890  cmp     cs:?value@?1??_initialized@_data_FileInfoProperty@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_initialized(void)'::`2'::value
0x140004897  jnz     short loc_140004902
0x140004899  xor     edi, edi
0x14000489b  lea     r14, cs:140000000h
0x1400048a2  xor     ebx, ebx
0x1400048a4  mov     rcx, ds:rva off_14001AAF0[r14+rbx*8]; Str
0x1400048ac  lea     rax, rva ?storage@?1??_name_storage@_data_FileInfoProperty@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "None,FileId,ProgId,Description,FileVer,"... ...
0x1400048b3  add     rax, rdi
0x1400048b6  lea     rdx, Control; "= \t\n"
0x1400048bd  mov     rva ?value@?1??_name_array@_data_FileInfoProperty@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_name_array(void)'::`2'::value ...
0x1400048c5  call    cs:__imp_strcspn
0x1400048cb  mov     rcx, ds:rva off_14001AAF0[r14+rbx*8]; "None" ...
0x1400048d3  add     rax, rdi
0x1400048d6  mov     byte ptr [rax+r14+26C10h], 0
0x1400048df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400048e3  inc     rax
0x1400048e6  cmp     byte ptr [rcx+rax], 0
0x1400048ea  jnz     short loc_1400048E3
0x1400048ec  inc     rdi
0x1400048ef  inc     rbx
0x1400048f2  add     rdi, rax
0x1400048f5  cmp     rbx, 0Dh
0x1400048f9  jb      short loc_1400048A4
0x1400048fb  mov     cs:?value@?1??_initialized@_data_FileInfoProperty@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_FileInfoProperty::_initialized(void)'::`2'::value
0x140004902  mov     rbx, [rsp+28h+arg_0]
0x140004907  mov     rdi, [rsp+28h+arg_8]
0x14000490c  add     rsp, 20h
0x140004910  pop     r14
0x140004912  retn
```
