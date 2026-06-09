# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::update_precision(void)

- ea: `0x180052e30`
- end: `0x180052f9e`
- name: `?update_precision@?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180045bbc`
- `0x18004834c`

## callees

- `0x180007b48`
- `0x180038cb0`
- `0x180043108`
- `0x180052e30`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::update_precision(
        __int64 a1)
{
  _DWORD *v2; // r8
  __crt_cached_ptd_host *v3; // rcx
  int v4; // eax
  bool v5; // zf
  __int64 v6; // r8
  __int16 *v7; // rax
  int v8; // edx
  char v9; // di
  int v10; // ecx
  int v11; // r9d
  __int64 v12; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int16 *v16[3]; // [rsp+30h] [rbp-18h] BYREF
  __int16 *v17; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 1140) != 1 )
  {
    v16[0] = *(__int16 **)(a1 + 16);
    v16[1] = (__int16 *)&v17;
    v3 = *(__crt_cached_ptd_host **)(a1 + 8);
    v17 = v16[0];
    v4 = __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<wchar_t>,0>(v3, v16, 0xAu, 1);
    v5 = *(_DWORD *)(a1 + 1136) == 1;
    v6 = v4;
    v7 = v17;
    v8 = v6 - 1;
    *(_QWORD *)(a1 + 16) = v17 + 1;
    if ( !v5 )
    {
      *(_DWORD *)(a1 + 48) = **(_DWORD **)(a1 + 24 * v6 + 1136);
      return 1;
    }
    v9 = 0;
    if ( v8 < 0 || *v7 != 36 || v8 >= 100 )
    {
      v15 = *(_QWORD *)(a1 + 8);
      *(_BYTE *)(v15 + 48) = 1;
      *(_DWORD *)(v15 + 44) = 22;
      invalid_parameter_internal(0, 0, 0, 0, 0, *(__crt_cached_ptd_host **)(a1 + 8));
      return 0;
    }
    v10 = *(_DWORD *)(a1 + 52);
    v11 = *(unsigned __int16 *)(a1 + 58);
    if ( v8 <= *(_DWORD *)(a1 + 3552) )
      v8 = *(_DWORD *)(a1 + 3552);
    *(_DWORD *)(a1 + 3552) = v8;
    v12 = a1 + 24 * (v6 + 47);
    if ( *(_DWORD *)v12 )
    {
      if ( !(unsigned __int8)__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::is_positional_parameter_reappearance_consistent(
                               a1,
                               v12,
                               1,
                               v11,
                               v10) )
      {
        v14 = *(_QWORD *)(a1 + 8);
        *(_BYTE *)(v14 + 48) = 1;
        *(_DWORD *)(v14 + 44) = 22;
        invalid_parameter_internal(0, 0, 0, 0, 0, *(__crt_cached_ptd_host **)(a1 + 8));
        return v9;
      }
    }
    else
    {
      *(_DWORD *)v12 = 1;
      *(_WORD *)(v12 + 4) = v11;
      *(_DWORD *)(v12 + 16) = v10;
    }
    return 1;
  }
  v2 = *(_DWORD **)(a1 + 24);
  *(_QWORD *)(a1 + 24) = v2 + 2;
  *(_DWORD *)(a1 + 48) = *v2;
  return 1;
}

```

## disassembly

```asm
0x180052e30  mov     [rsp+arg_8], rbx
0x180052e35  push    rdi
0x180052e36  sub     rsp, 40h
0x180052e3a  cmp     dword ptr [rcx+474h], 1
0x180052e41  mov     rbx, rcx
0x180052e44  jnz     short loc_180052E5D
0x180052e46  mov     r8, [rcx+18h]
0x180052e4a  lea     rdx, [r8+8]
0x180052e4e  mov     [rcx+18h], rdx
0x180052e52  mov     edx, [r8]
0x180052e55  mov     [rcx+30h], edx
0x180052e58  jmp     loc_180052F91
0x180052e5d  mov     rax, [rcx+10h]
0x180052e61  lea     rdx, [rsp+48h+var_18]
0x180052e66  lea     rcx, [rsp+48h+arg_0]
0x180052e6b  mov     [rsp+48h+var_18], rax
0x180052e70  mov     [rsp+48h+var_10], rcx
0x180052e75  mov     r9b, 1
0x180052e78  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052e7c  mov     r8d, 0Ah
0x180052e82  mov     [rsp+48h+arg_0], rax
0x180052e87  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x180052e8c  cmp     dword ptr [rbx+470h], 1
0x180052e93  movsxd  r8, eax
0x180052e96  mov     rax, [rsp+48h+arg_0]
0x180052e9b  lea     edx, [r8-1]
0x180052e9f  lea     rcx, [rax+2]
0x180052ea3  mov     [rbx+10h], rcx
0x180052ea7  jnz     loc_180052F80
0x180052ead  xor     edi, edi
0x180052eaf  test    edx, edx
0x180052eb1  js      loc_180052F50
0x180052eb7  cmp     word ptr [rax], 24h ; '$'
0x180052ebb  jnz     loc_180052F50
0x180052ec1  cmp     edx, 64h ; 'd'
0x180052ec4  jge     loc_180052F50
0x180052eca  mov     eax, [rbx+0DE0h]
0x180052ed0  cmp     edx, eax
0x180052ed2  mov     ecx, [rbx+34h]
0x180052ed5  movzx   r9d, word ptr [rbx+3Ah]
0x180052eda  cmovle  edx, eax
0x180052edd  mov     [rbx+0DE0h], edx
0x180052ee3  lea     rax, [r8+2Fh]
0x180052ee7  lea     rax, [rax+rax*2]
0x180052eeb  lea     rdx, [rbx+rax*8]
0x180052eef  cmp     [rdx], edi
0x180052ef1  jnz     short loc_180052F0C
0x180052ef3  mov     dword ptr [rdx], 1
0x180052ef9  mov     [rdx+4], r9w
0x180052efe  mov     [rdx+10h], ecx
0x180052f01  mov     dil, 1
0x180052f04  mov     al, dil
0x180052f07  jmp     loc_180052F93
0x180052f0c  mov     dword ptr [rsp+48h+var_28], ecx
0x180052f10  mov     r8d, 1
0x180052f16  mov     rcx, rbx
0x180052f19  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@_WW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::parameter_type,wchar_t,__crt_stdio_output::length_modifier)
0x180052f1e  test    al, al
0x180052f20  jnz     short loc_180052F01
0x180052f22  mov     rax, [rbx+8]
0x180052f26  xor     r9d, r9d; LineNo
0x180052f29  xor     r8d, r8d; FileName
0x180052f2c  xor     edx, edx; FunctionName
0x180052f2e  xor     ecx, ecx; Expression
0x180052f30  mov     byte ptr [rax+30h], 1
0x180052f34  mov     dword ptr [rax+2Ch], 16h
0x180052f3b  mov     rax, [rbx+8]
0x180052f3f  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052f44  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052f49  call    _invalid_parameter_internal
0x180052f4e  jmp     short loc_180052F04
0x180052f50  mov     rax, [rbx+8]
0x180052f54  xor     r9d, r9d; LineNo
0x180052f57  xor     r8d, r8d; FileName
0x180052f5a  xor     edx, edx; FunctionName
0x180052f5c  xor     ecx, ecx; Expression
0x180052f5e  mov     byte ptr [rax+30h], 1
0x180052f62  mov     dword ptr [rax+2Ch], 16h
0x180052f69  mov     rax, [rbx+8]
0x180052f6d  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052f72  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052f77  call    _invalid_parameter_internal
0x180052f7c  xor     al, al
0x180052f7e  jmp     short loc_180052F93
0x180052f80  lea     rcx, [r8+r8*2]
0x180052f84  mov     rax, [rbx+rcx*8+470h]
0x180052f8c  mov     ecx, [rax]
0x180052f8e  mov     [rbx+30h], ecx
0x180052f91  mov     al, 1
0x180052f93  mov     rbx, [rsp+48h+arg_8]
0x180052f98  add     rsp, 40h
0x180052f9c  pop     rdi
0x180052f9d  retn
```
