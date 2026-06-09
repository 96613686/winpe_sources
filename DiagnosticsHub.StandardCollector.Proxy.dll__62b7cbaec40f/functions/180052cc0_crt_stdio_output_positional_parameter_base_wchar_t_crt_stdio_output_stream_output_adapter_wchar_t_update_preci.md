# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::update_precision(void)

- ea: `0x180052cc0`
- end: `0x180052e2e`
- name: `?update_precision@?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800452e0`
- `0x1800482a8`

## callees

- `0x180007b48`
- `0x180038cb0`
- `0x180042f04`
- `0x180052cc0`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::update_precision(
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
      if ( !(unsigned __int8)__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::is_positional_parameter_reappearance_consistent(
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
0x180052cc0  mov     [rsp+arg_8], rbx
0x180052cc5  push    rdi
0x180052cc6  sub     rsp, 40h
0x180052cca  cmp     dword ptr [rcx+474h], 1
0x180052cd1  mov     rbx, rcx
0x180052cd4  jnz     short loc_180052CED
0x180052cd6  mov     r8, [rcx+18h]
0x180052cda  lea     rdx, [r8+8]
0x180052cde  mov     [rcx+18h], rdx
0x180052ce2  mov     edx, [r8]
0x180052ce5  mov     [rcx+30h], edx
0x180052ce8  jmp     loc_180052E21
0x180052ced  mov     rax, [rcx+10h]
0x180052cf1  lea     rdx, [rsp+48h+var_18]
0x180052cf6  lea     rcx, [rsp+48h+arg_0]
0x180052cfb  mov     [rsp+48h+var_18], rax
0x180052d00  mov     [rsp+48h+var_10], rcx
0x180052d05  mov     r9b, 1
0x180052d08  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052d0c  mov     r8d, 0Ah
0x180052d12  mov     [rsp+48h+arg_0], rax
0x180052d17  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x180052d1c  cmp     dword ptr [rbx+470h], 1
0x180052d23  movsxd  r8, eax
0x180052d26  mov     rax, [rsp+48h+arg_0]
0x180052d2b  lea     edx, [r8-1]
0x180052d2f  lea     rcx, [rax+2]
0x180052d33  mov     [rbx+10h], rcx
0x180052d37  jnz     loc_180052E10
0x180052d3d  xor     edi, edi
0x180052d3f  test    edx, edx
0x180052d41  js      loc_180052DE0
0x180052d47  cmp     word ptr [rax], 24h ; '$'
0x180052d4b  jnz     loc_180052DE0
0x180052d51  cmp     edx, 64h ; 'd'
0x180052d54  jge     loc_180052DE0
0x180052d5a  mov     eax, [rbx+0DE0h]
0x180052d60  cmp     edx, eax
0x180052d62  mov     ecx, [rbx+34h]
0x180052d65  movzx   r9d, word ptr [rbx+3Ah]
0x180052d6a  cmovle  edx, eax
0x180052d6d  mov     [rbx+0DE0h], edx
0x180052d73  lea     rax, [r8+2Fh]
0x180052d77  lea     rax, [rax+rax*2]
0x180052d7b  lea     rdx, [rbx+rax*8]
0x180052d7f  cmp     [rdx], edi
0x180052d81  jnz     short loc_180052D9C
0x180052d83  mov     dword ptr [rdx], 1
0x180052d89  mov     [rdx+4], r9w
0x180052d8e  mov     [rdx+10h], ecx
0x180052d91  mov     dil, 1
0x180052d94  mov     al, dil
0x180052d97  jmp     loc_180052E23
0x180052d9c  mov     dword ptr [rsp+48h+var_28], ecx
0x180052da0  mov     r8d, 1
0x180052da6  mov     rcx, rbx
0x180052da9  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@_WW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::parameter_type,wchar_t,__crt_stdio_output::length_modifier)
0x180052dae  test    al, al
0x180052db0  jnz     short loc_180052D91
0x180052db2  mov     rax, [rbx+8]
0x180052db6  xor     r9d, r9d; LineNo
0x180052db9  xor     r8d, r8d; FileName
0x180052dbc  xor     edx, edx; FunctionName
0x180052dbe  xor     ecx, ecx; Expression
0x180052dc0  mov     byte ptr [rax+30h], 1
0x180052dc4  mov     dword ptr [rax+2Ch], 16h
0x180052dcb  mov     rax, [rbx+8]
0x180052dcf  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052dd4  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052dd9  call    _invalid_parameter_internal
0x180052dde  jmp     short loc_180052D94
0x180052de0  mov     rax, [rbx+8]
0x180052de4  xor     r9d, r9d; LineNo
0x180052de7  xor     r8d, r8d; FileName
0x180052dea  xor     edx, edx; FunctionName
0x180052dec  xor     ecx, ecx; Expression
0x180052dee  mov     byte ptr [rax+30h], 1
0x180052df2  mov     dword ptr [rax+2Ch], 16h
0x180052df9  mov     rax, [rbx+8]
0x180052dfd  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052e02  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052e07  call    _invalid_parameter_internal
0x180052e0c  xor     al, al
0x180052e0e  jmp     short loc_180052E23
0x180052e10  lea     rcx, [r8+r8*2]
0x180052e14  mov     rax, [rbx+rcx*8+470h]
0x180052e1c  mov     ecx, [rax]
0x180052e1e  mov     [rbx+30h], ecx
0x180052e21  mov     al, 1
0x180052e23  mov     rbx, [rsp+48h+arg_8]
0x180052e28  add     rsp, 40h
0x180052e2c  pop     rdi
0x180052e2d  retn
```
