# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::update_field_width(void)

- ea: `0x1800523d8`
- end: `0x180052546`
- name: `?update_field_width@?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180045000`
- `0x18004d5d4`

## callees

- `0x1800073e8`
- `0x1800389d0`
- `0x180042c24`
- `0x1800523d8`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::update_field_width(
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
      *(_DWORD *)(a1 + 44) = **(_DWORD **)(a1 + 24 * v6 + 1136);
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
  *(_DWORD *)(a1 + 44) = *v2;
  return 1;
}

```

## disassembly

```asm
0x1800523d8  mov     [rsp+arg_8], rbx
0x1800523dd  push    rdi
0x1800523de  sub     rsp, 40h
0x1800523e2  cmp     dword ptr [rcx+474h], 1
0x1800523e9  mov     rbx, rcx
0x1800523ec  jnz     short loc_180052405
0x1800523ee  mov     r8, [rcx+18h]
0x1800523f2  lea     rdx, [r8+8]
0x1800523f6  mov     [rcx+18h], rdx
0x1800523fa  mov     edx, [r8]
0x1800523fd  mov     [rcx+2Ch], edx
0x180052400  jmp     loc_180052539
0x180052405  mov     rax, [rcx+10h]
0x180052409  lea     rdx, [rsp+48h+var_18]
0x18005240e  lea     rcx, [rsp+48h+arg_0]
0x180052413  mov     [rsp+48h+var_18], rax
0x180052418  mov     [rsp+48h+var_10], rcx
0x18005241d  mov     r9b, 1
0x180052420  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052424  mov     r8d, 0Ah
0x18005242a  mov     [rsp+48h+arg_0], rax
0x18005242f  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x180052434  cmp     dword ptr [rbx+470h], 1
0x18005243b  movsxd  r8, eax
0x18005243e  mov     rax, [rsp+48h+arg_0]
0x180052443  lea     edx, [r8-1]
0x180052447  lea     rcx, [rax+2]
0x18005244b  mov     [rbx+10h], rcx
0x18005244f  jnz     loc_180052528
0x180052455  xor     edi, edi
0x180052457  test    edx, edx
0x180052459  js      loc_1800524F8
0x18005245f  cmp     word ptr [rax], 24h ; '$'
0x180052463  jnz     loc_1800524F8
0x180052469  cmp     edx, 64h ; 'd'
0x18005246c  jge     loc_1800524F8
0x180052472  mov     eax, [rbx+0DE0h]
0x180052478  cmp     edx, eax
0x18005247a  mov     ecx, [rbx+34h]
0x18005247d  movzx   r9d, word ptr [rbx+3Ah]
0x180052482  cmovle  edx, eax
0x180052485  mov     [rbx+0DE0h], edx
0x18005248b  lea     rax, [r8+2Fh]
0x18005248f  lea     rax, [rax+rax*2]
0x180052493  lea     rdx, [rbx+rax*8]
0x180052497  cmp     [rdx], edi
0x180052499  jnz     short loc_1800524B4
0x18005249b  mov     dword ptr [rdx], 1
0x1800524a1  mov     [rdx+4], r9w
0x1800524a6  mov     [rdx+10h], ecx
0x1800524a9  mov     dil, 1
0x1800524ac  mov     al, dil
0x1800524af  jmp     loc_18005253B
0x1800524b4  mov     dword ptr [rsp+48h+var_28], ecx
0x1800524b8  mov     r8d, 1
0x1800524be  mov     rcx, rbx
0x1800524c1  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@_WW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::parameter_type,wchar_t,__crt_stdio_output::length_modifier)
0x1800524c6  test    al, al
0x1800524c8  jnz     short loc_1800524A9
0x1800524ca  mov     rax, [rbx+8]
0x1800524ce  xor     r9d, r9d; LineNo
0x1800524d1  xor     r8d, r8d; FileName
0x1800524d4  xor     edx, edx; FunctionName
0x1800524d6  xor     ecx, ecx; Expression
0x1800524d8  mov     byte ptr [rax+30h], 1
0x1800524dc  mov     dword ptr [rax+2Ch], 16h
0x1800524e3  mov     rax, [rbx+8]
0x1800524e7  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x1800524ec  mov     [rsp+48h+var_28], rdi; uintptr_t
0x1800524f1  call    _invalid_parameter_internal
0x1800524f6  jmp     short loc_1800524AC
0x1800524f8  mov     rax, [rbx+8]
0x1800524fc  xor     r9d, r9d; LineNo
0x1800524ff  xor     r8d, r8d; FileName
0x180052502  xor     edx, edx; FunctionName
0x180052504  xor     ecx, ecx; Expression
0x180052506  mov     byte ptr [rax+30h], 1
0x18005250a  mov     dword ptr [rax+2Ch], 16h
0x180052511  mov     rax, [rbx+8]
0x180052515  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x18005251a  mov     [rsp+48h+var_28], rdi; uintptr_t
0x18005251f  call    _invalid_parameter_internal
0x180052524  xor     al, al
0x180052526  jmp     short loc_18005253B
0x180052528  lea     rcx, [r8+r8*2]
0x18005252c  mov     rax, [rbx+rcx*8+470h]
0x180052534  mov     ecx, [rax]
0x180052536  mov     [rbx+2Ch], ecx
0x180052539  mov     al, 1
0x18005253b  mov     rbx, [rsp+48h+arg_8]
0x180052540  add     rsp, 40h
0x180052544  pop     rdi
0x180052545  retn
```
