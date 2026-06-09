# Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_dynamic_initializer_for___force_initialization__

- ea: `0x1400053c0`
- end: `0x140005453`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400053c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005405`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005405`

## string_xrefs

- `0x1400053ec`: `FirstOf = 0,LastOf,CommaList,PipeList,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 4; ++i )
    {
      v2 = off_140019560[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019560[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x1400053c0  mov     [rsp+arg_0], rbx
0x1400053c5  mov     [rsp+arg_8], rdi
0x1400053ca  push    r14
0x1400053cc  sub     rsp, 20h
0x1400053d0  cmp     cs:?value@?1??_initialized@_data_MultiSelector@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_initialized(void)'::`2'::value
0x1400053d7  jnz     short loc_140005442
0x1400053d9  xor     edi, edi
0x1400053db  lea     r14, cs:140000000h
0x1400053e2  xor     ebx, ebx
0x1400053e4  mov     rcx, ds:rva off_140019560[r14+rbx*8]; Str
0x1400053ec  lea     rax, rva ?storage@?1??_name_storage@_data_MultiSelector@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "FirstOf = 0,LastOf,CommaList,PipeList," ...
0x1400053f3  add     rax, rdi
0x1400053f6  lea     rdx, Control; "= \t\n"
0x1400053fd  mov     rva ?value@?1??_name_array@_data_MultiSelector@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_name_array(void)'::`2'::value ...
0x140005405  call    cs:__imp_strcspn
0x14000540b  mov     rcx, ds:rva off_140019560[r14+rbx*8]; "FirstOf = 0" ...
0x140005413  add     rax, rdi
0x140005416  mov     byte ptr [rax+r14+28020h], 0
0x14000541f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005423  inc     rax
0x140005426  cmp     byte ptr [rcx+rax], 0
0x14000542a  jnz     short loc_140005423
0x14000542c  inc     rdi
0x14000542f  inc     rbx
0x140005432  add     rdi, rax
0x140005435  cmp     rbx, 4
0x140005439  jb      short loc_1400053E4
0x14000543b  mov     cs:?value@?1??_initialized@_data_MultiSelector@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_MultiSelector::_initialized(void)'::`2'::value
0x140005442  mov     rbx, [rsp+28h+arg_0]
0x140005447  mov     rdi, [rsp+28h+arg_8]
0x14000544c  add     rsp, 20h
0x140005450  pop     r14
0x140005452  retn
```
