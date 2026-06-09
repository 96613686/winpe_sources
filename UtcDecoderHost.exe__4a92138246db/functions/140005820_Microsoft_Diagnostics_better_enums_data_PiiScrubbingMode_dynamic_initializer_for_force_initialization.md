# Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_dynamic_initializer_for___force_initialization__

- ea: `0x140005820`
- end: `0x1400058b3`
- name: `Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005820`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005865`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005865`

## string_xrefs

- `0x14000584c`: `None,ReportOnly,ReplaceOnly,ReportAndReplace,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 4; ++i )
    {
      v2 = off_14001A0B0[i];
      `Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A0B0[i];
      `Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140005820  mov     [rsp+arg_0], rbx
0x140005825  mov     [rsp+arg_8], rdi
0x14000582a  push    r14
0x14000582c  sub     rsp, 20h
0x140005830  cmp     cs:?value@?1??_initialized@_data_PiiScrubbingMode@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_initialized(void)'::`2'::value
0x140005837  jnz     short loc_1400058A2
0x140005839  xor     edi, edi
0x14000583b  lea     r14, cs:140000000h
0x140005842  xor     ebx, ebx
0x140005844  mov     rcx, ds:rva off_14001A0B0[r14+rbx*8]; Str
0x14000584c  lea     rax, rva ?storage@?1??_name_storage@_data_PiiScrubbingMode@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "None,ReportOnly,ReplaceOnly,ReportAndRe"... ...
0x140005853  add     rax, rdi
0x140005856  lea     rdx, Control; "= \t\n"
0x14000585d  mov     rva ?value@?1??_name_array@_data_PiiScrubbingMode@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_name_array(void)'::`2'::value ...
0x140005865  call    cs:__imp_strcspn
0x14000586b  mov     rcx, ds:rva off_14001A0B0[r14+rbx*8]; "None" ...
0x140005873  add     rax, rdi
0x140005876  mov     byte ptr [rax+r14+274B0h], 0
0x14000587f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005883  inc     rax
0x140005886  cmp     byte ptr [rcx+rax], 0
0x14000588a  jnz     short loc_140005883
0x14000588c  inc     rdi
0x14000588f  inc     rbx
0x140005892  add     rdi, rax
0x140005895  cmp     rbx, 4
0x140005899  jb      short loc_140005844
0x14000589b  mov     cs:?value@?1??_initialized@_data_PiiScrubbingMode@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_PiiScrubbingMode::_initialized(void)'::`2'::value
0x1400058a2  mov     rbx, [rsp+28h+arg_0]
0x1400058a7  mov     rdi, [rsp+28h+arg_8]
0x1400058ac  add     rsp, 20h
0x1400058b0  pop     r14
0x1400058b2  retn
```
