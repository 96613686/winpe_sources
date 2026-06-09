# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::update_field_width(void)

- ea: `0x1800523e0`
- end: `0x18005254b`
- name: `?update_field_width@?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `363`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180043dac`
- `0x18004d744`

## callees

- `0x180007b48`
- `0x1800389fc`
- `0x180042a9c`
- `0x1800523e0`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::update_field_width(
        __int64 a1)
{
  _DWORD *v2; // r8
  __crt_cached_ptd_host *v3; // rcx
  int v4; // eax
  int v5; // r9d
  bool v6; // zf
  __int64 v7; // r8
  _BYTE *v8; // rax
  int v9; // edx
  char v10; // di
  int v11; // ecx
  __int64 v12; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  _QWORD v16[3]; // [rsp+30h] [rbp-18h] BYREF
  _BYTE *v17; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 1140) != 1 )
  {
    v16[0] = *(_QWORD *)(a1 + 16);
    v16[1] = &v17;
    v3 = *(__crt_cached_ptd_host **)(a1 + 8);
    v17 = (_BYTE *)v16[0];
    v4 = __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<char>,0>(
           v3,
           (__int64)v16,
           10,
           1u);
    v6 = *(_DWORD *)(a1 + 1136) == 1;
    v7 = v4;
    v8 = v17;
    v9 = v7 - 1;
    *(_QWORD *)(a1 + 16) = v17 + 1;
    if ( !v6 )
    {
      *(_DWORD *)(a1 + 44) = **(_DWORD **)(a1 + 24 * v7 + 1136);
      return 1;
    }
    v10 = 0;
    if ( v9 < 0 || *v8 != 36 || v9 >= 100 )
    {
      v15 = *(_QWORD *)(a1 + 8);
      *(_BYTE *)(v15 + 48) = 1;
      *(_DWORD *)(v15 + 44) = 22;
      invalid_parameter_internal(0, 0, 0, 0, 0, *(__crt_cached_ptd_host **)(a1 + 8));
      return 0;
    }
    v11 = *(_DWORD *)(a1 + 52);
    LOBYTE(v5) = *(_BYTE *)(a1 + 57);
    if ( v9 <= *(_DWORD *)(a1 + 3552) )
      v9 = *(_DWORD *)(a1 + 3552);
    *(_DWORD *)(a1 + 3552) = v9;
    v12 = a1 + 24 * (v7 + 47);
    if ( *(_DWORD *)v12 )
    {
      if ( !(unsigned __int8)__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::is_positional_parameter_reappearance_consistent(
                               a1,
                               v12,
                               1,
                               v5,
                               v11) )
      {
        v14 = *(_QWORD *)(a1 + 8);
        *(_BYTE *)(v14 + 48) = 1;
        *(_DWORD *)(v14 + 44) = 22;
        invalid_parameter_internal(0, 0, 0, 0, 0, *(__crt_cached_ptd_host **)(a1 + 8));
        return v10;
      }
    }
    else
    {
      *(_DWORD *)v12 = 1;
      *(_BYTE *)(v12 + 4) = v5;
      *(_DWORD *)(v12 + 16) = v11;
    }
    return 1;
  }
  v2 = *(_DWORD **)(a1 + 24);
  *(_QWORD *)(a1 + 24) = v2 + 2;
  *(_DWORD *)(a1 + 44) = *v2;
  return 1;
}

```

## disassembly

```asm
0x1800523e0  mov     [rsp+arg_8], rbx
0x1800523e5  push    rdi
0x1800523e6  sub     rsp, 40h
0x1800523ea  cmp     dword ptr [rcx+474h], 1
0x1800523f1  mov     rbx, rcx
0x1800523f4  jnz     short loc_18005240D
0x1800523f6  mov     r8, [rcx+18h]
0x1800523fa  lea     rdx, [r8+8]
0x1800523fe  mov     [rcx+18h], rdx
0x180052402  mov     edx, [r8]
0x180052405  mov     [rcx+2Ch], edx
0x180052408  jmp     loc_18005253E
0x18005240d  mov     rax, [rcx+10h]
0x180052411  lea     rdx, [rsp+48h+var_18]
0x180052416  lea     rcx, [rsp+48h+arg_0]
0x18005241b  mov     [rsp+48h+var_18], rax
0x180052420  mov     [rsp+48h+var_10], rcx
0x180052425  mov     r9b, 1
0x180052428  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x18005242c  mov     r8d, 0Ah
0x180052432  mov     [rsp+48h+arg_0], rax
0x180052437  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x18005243c  cmp     dword ptr [rbx+470h], 1
0x180052443  movsxd  r8, eax
0x180052446  mov     rax, [rsp+48h+arg_0]
0x18005244b  lea     edx, [r8-1]
0x18005244f  lea     rcx, [rax+1]
0x180052453  mov     [rbx+10h], rcx
0x180052457  jnz     loc_18005252D
0x18005245d  xor     edi, edi
0x18005245f  test    edx, edx
0x180052461  js      loc_1800524FD
0x180052467  cmp     byte ptr [rax], 24h ; '$'
0x18005246a  jnz     loc_1800524FD
0x180052470  cmp     edx, 64h ; 'd'
0x180052473  jge     loc_1800524FD
0x180052479  mov     eax, [rbx+0DE0h]
0x18005247f  cmp     edx, eax
0x180052481  mov     ecx, [rbx+34h]
0x180052484  mov     r9b, [rbx+39h]
0x180052488  cmovle  edx, eax
0x18005248b  mov     [rbx+0DE0h], edx
0x180052491  lea     rax, [r8+2Fh]
0x180052495  lea     rax, [rax+rax*2]
0x180052499  lea     rdx, [rbx+rax*8]
0x18005249d  cmp     [rdx], edi
0x18005249f  jnz     short loc_1800524B9
0x1800524a1  mov     dword ptr [rdx], 1
0x1800524a7  mov     [rdx+4], r9b
0x1800524ab  mov     [rdx+10h], ecx
0x1800524ae  mov     dil, 1
0x1800524b1  mov     al, dil
0x1800524b4  jmp     loc_180052540
0x1800524b9  mov     dword ptr [rsp+48h+var_28], ecx
0x1800524bd  mov     r8d, 1
0x1800524c3  mov     rcx, rbx
0x1800524c6  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@DW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::parameter_type,char,__crt_stdio_output::length_modifier)
0x1800524cb  test    al, al
0x1800524cd  jnz     short loc_1800524AE
0x1800524cf  mov     rax, [rbx+8]
0x1800524d3  xor     r9d, r9d; LineNo
0x1800524d6  xor     r8d, r8d; FileName
0x1800524d9  xor     edx, edx; FunctionName
0x1800524db  xor     ecx, ecx; Expression
0x1800524dd  mov     byte ptr [rax+30h], 1
0x1800524e1  mov     dword ptr [rax+2Ch], 16h
0x1800524e8  mov     rax, [rbx+8]
0x1800524ec  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x1800524f1  mov     [rsp+48h+var_28], rdi; uintptr_t
0x1800524f6  call    _invalid_parameter_internal
0x1800524fb  jmp     short loc_1800524B1
0x1800524fd  mov     rax, [rbx+8]
0x180052501  xor     r9d, r9d; LineNo
0x180052504  xor     r8d, r8d; FileName
0x180052507  xor     edx, edx; FunctionName
0x180052509  xor     ecx, ecx; Expression
0x18005250b  mov     byte ptr [rax+30h], 1
0x18005250f  mov     dword ptr [rax+2Ch], 16h
0x180052516  mov     rax, [rbx+8]
0x18005251a  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x18005251f  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052524  call    _invalid_parameter_internal
0x180052529  xor     al, al
0x18005252b  jmp     short loc_180052540
0x18005252d  lea     rcx, [r8+r8*2]
0x180052531  mov     rax, [rbx+rcx*8+470h]
0x180052539  mov     ecx, [rax]
0x18005253b  mov     [rbx+2Ch], ecx
0x18005253e  mov     al, 1
0x180052540  mov     rbx, [rsp+48h+arg_8]
0x180052545  add     rsp, 40h
0x180052549  pop     rdi
0x18005254a  retn
```
