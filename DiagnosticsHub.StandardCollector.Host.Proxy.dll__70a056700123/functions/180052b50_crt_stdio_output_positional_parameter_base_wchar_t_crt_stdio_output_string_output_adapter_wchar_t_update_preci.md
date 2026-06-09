# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::update_precision(void)

- ea: `0x180052b50`
- end: `0x180052cbe`
- name: `?update_precision@?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800458dc`
- `0x18004806c`

## callees

- `0x1800073e8`
- `0x1800389d0`
- `0x180042e28`
- `0x180052b50`

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
0x180052b50  mov     [rsp+arg_8], rbx
0x180052b55  push    rdi
0x180052b56  sub     rsp, 40h
0x180052b5a  cmp     dword ptr [rcx+474h], 1
0x180052b61  mov     rbx, rcx
0x180052b64  jnz     short loc_180052B7D
0x180052b66  mov     r8, [rcx+18h]
0x180052b6a  lea     rdx, [r8+8]
0x180052b6e  mov     [rcx+18h], rdx
0x180052b72  mov     edx, [r8]
0x180052b75  mov     [rcx+30h], edx
0x180052b78  jmp     loc_180052CB1
0x180052b7d  mov     rax, [rcx+10h]
0x180052b81  lea     rdx, [rsp+48h+var_18]
0x180052b86  lea     rcx, [rsp+48h+arg_0]
0x180052b8b  mov     [rsp+48h+var_18], rax
0x180052b90  mov     [rsp+48h+var_10], rcx
0x180052b95  mov     r9b, 1
0x180052b98  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052b9c  mov     r8d, 0Ah
0x180052ba2  mov     [rsp+48h+arg_0], rax
0x180052ba7  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x180052bac  cmp     dword ptr [rbx+470h], 1
0x180052bb3  movsxd  r8, eax
0x180052bb6  mov     rax, [rsp+48h+arg_0]
0x180052bbb  lea     edx, [r8-1]
0x180052bbf  lea     rcx, [rax+2]
0x180052bc3  mov     [rbx+10h], rcx
0x180052bc7  jnz     loc_180052CA0
0x180052bcd  xor     edi, edi
0x180052bcf  test    edx, edx
0x180052bd1  js      loc_180052C70
0x180052bd7  cmp     word ptr [rax], 24h ; '$'
0x180052bdb  jnz     loc_180052C70
0x180052be1  cmp     edx, 64h ; 'd'
0x180052be4  jge     loc_180052C70
0x180052bea  mov     eax, [rbx+0DE0h]
0x180052bf0  cmp     edx, eax
0x180052bf2  mov     ecx, [rbx+34h]
0x180052bf5  movzx   r9d, word ptr [rbx+3Ah]
0x180052bfa  cmovle  edx, eax
0x180052bfd  mov     [rbx+0DE0h], edx
0x180052c03  lea     rax, [r8+2Fh]
0x180052c07  lea     rax, [rax+rax*2]
0x180052c0b  lea     rdx, [rbx+rax*8]
0x180052c0f  cmp     [rdx], edi
0x180052c11  jnz     short loc_180052C2C
0x180052c13  mov     dword ptr [rdx], 1
0x180052c19  mov     [rdx+4], r9w
0x180052c1e  mov     [rdx+10h], ecx
0x180052c21  mov     dil, 1
0x180052c24  mov     al, dil
0x180052c27  jmp     loc_180052CB3
0x180052c2c  mov     dword ptr [rsp+48h+var_28], ecx
0x180052c30  mov     r8d, 1
0x180052c36  mov     rcx, rbx
0x180052c39  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@_WW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::parameter_type,wchar_t,__crt_stdio_output::length_modifier)
0x180052c3e  test    al, al
0x180052c40  jnz     short loc_180052C21
0x180052c42  mov     rax, [rbx+8]
0x180052c46  xor     r9d, r9d; LineNo
0x180052c49  xor     r8d, r8d; FileName
0x180052c4c  xor     edx, edx; FunctionName
0x180052c4e  xor     ecx, ecx; Expression
0x180052c50  mov     byte ptr [rax+30h], 1
0x180052c54  mov     dword ptr [rax+2Ch], 16h
0x180052c5b  mov     rax, [rbx+8]
0x180052c5f  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052c64  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052c69  call    _invalid_parameter_internal
0x180052c6e  jmp     short loc_180052C24
0x180052c70  mov     rax, [rbx+8]
0x180052c74  xor     r9d, r9d; LineNo
0x180052c77  xor     r8d, r8d; FileName
0x180052c7a  xor     edx, edx; FunctionName
0x180052c7c  xor     ecx, ecx; Expression
0x180052c7e  mov     byte ptr [rax+30h], 1
0x180052c82  mov     dword ptr [rax+2Ch], 16h
0x180052c89  mov     rax, [rbx+8]
0x180052c8d  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052c92  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052c97  call    _invalid_parameter_internal
0x180052c9c  xor     al, al
0x180052c9e  jmp     short loc_180052CB3
0x180052ca0  lea     rcx, [r8+r8*2]
0x180052ca4  mov     rax, [rbx+rcx*8+470h]
0x180052cac  mov     ecx, [rax]
0x180052cae  mov     [rbx+30h], ecx
0x180052cb1  mov     al, 1
0x180052cb3  mov     rbx, [rsp+48h+arg_8]
0x180052cb8  add     rsp, 40h
0x180052cbc  pop     rdi
0x180052cbd  retn
```
