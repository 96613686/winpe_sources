# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::update_field_width(void)

- ea: `0x180052548`
- end: `0x1800526b6`
- name: `?update_field_width@?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800458dc`
- `0x18004d690`

## callees

- `0x1800073e8`
- `0x1800389d0`
- `0x180042e28`
- `0x180052548`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::update_field_width(
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
  *(_DWORD *)(a1 + 44) = *v2;
  return 1;
}

```

## disassembly

```asm
0x180052548  mov     [rsp+arg_8], rbx
0x18005254d  push    rdi
0x18005254e  sub     rsp, 40h
0x180052552  cmp     dword ptr [rcx+474h], 1
0x180052559  mov     rbx, rcx
0x18005255c  jnz     short loc_180052575
0x18005255e  mov     r8, [rcx+18h]
0x180052562  lea     rdx, [r8+8]
0x180052566  mov     [rcx+18h], rdx
0x18005256a  mov     edx, [r8]
0x18005256d  mov     [rcx+2Ch], edx
0x180052570  jmp     loc_1800526A9
0x180052575  mov     rax, [rcx+10h]
0x180052579  lea     rdx, [rsp+48h+var_18]
0x18005257e  lea     rcx, [rsp+48h+arg_0]
0x180052583  mov     [rsp+48h+var_18], rax
0x180052588  mov     [rsp+48h+var_10], rcx
0x18005258d  mov     r9b, 1
0x180052590  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052594  mov     r8d, 0Ah
0x18005259a  mov     [rsp+48h+arg_0], rax
0x18005259f  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x1800525a4  cmp     dword ptr [rbx+470h], 1
0x1800525ab  movsxd  r8, eax
0x1800525ae  mov     rax, [rsp+48h+arg_0]
0x1800525b3  lea     edx, [r8-1]
0x1800525b7  lea     rcx, [rax+2]
0x1800525bb  mov     [rbx+10h], rcx
0x1800525bf  jnz     loc_180052698
0x1800525c5  xor     edi, edi
0x1800525c7  test    edx, edx
0x1800525c9  js      loc_180052668
0x1800525cf  cmp     word ptr [rax], 24h ; '$'
0x1800525d3  jnz     loc_180052668
0x1800525d9  cmp     edx, 64h ; 'd'
0x1800525dc  jge     loc_180052668
0x1800525e2  mov     eax, [rbx+0DE0h]
0x1800525e8  cmp     edx, eax
0x1800525ea  mov     ecx, [rbx+34h]
0x1800525ed  movzx   r9d, word ptr [rbx+3Ah]
0x1800525f2  cmovle  edx, eax
0x1800525f5  mov     [rbx+0DE0h], edx
0x1800525fb  lea     rax, [r8+2Fh]
0x1800525ff  lea     rax, [rax+rax*2]
0x180052603  lea     rdx, [rbx+rax*8]
0x180052607  cmp     [rdx], edi
0x180052609  jnz     short loc_180052624
0x18005260b  mov     dword ptr [rdx], 1
0x180052611  mov     [rdx+4], r9w
0x180052616  mov     [rdx+10h], ecx
0x180052619  mov     dil, 1
0x18005261c  mov     al, dil
0x18005261f  jmp     loc_1800526AB
0x180052624  mov     dword ptr [rsp+48h+var_28], ecx
0x180052628  mov     r8d, 1
0x18005262e  mov     rcx, rbx
0x180052631  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@_WW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::parameter_type,wchar_t,__crt_stdio_output::length_modifier)
0x180052636  test    al, al
0x180052638  jnz     short loc_180052619
0x18005263a  mov     rax, [rbx+8]
0x18005263e  xor     r9d, r9d; LineNo
0x180052641  xor     r8d, r8d; FileName
0x180052644  xor     edx, edx; FunctionName
0x180052646  xor     ecx, ecx; Expression
0x180052648  mov     byte ptr [rax+30h], 1
0x18005264c  mov     dword ptr [rax+2Ch], 16h
0x180052653  mov     rax, [rbx+8]
0x180052657  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x18005265c  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052661  call    _invalid_parameter_internal
0x180052666  jmp     short loc_18005261C
0x180052668  mov     rax, [rbx+8]
0x18005266c  xor     r9d, r9d; LineNo
0x18005266f  xor     r8d, r8d; FileName
0x180052672  xor     edx, edx; FunctionName
0x180052674  xor     ecx, ecx; Expression
0x180052676  mov     byte ptr [rax+30h], 1
0x18005267a  mov     dword ptr [rax+2Ch], 16h
0x180052681  mov     rax, [rbx+8]
0x180052685  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x18005268a  mov     [rsp+48h+var_28], rdi; uintptr_t
0x18005268f  call    _invalid_parameter_internal
0x180052694  xor     al, al
0x180052696  jmp     short loc_1800526AB
0x180052698  lea     rcx, [r8+r8*2]
0x18005269c  mov     rax, [rbx+rcx*8+470h]
0x1800526a4  mov     ecx, [rax]
0x1800526a6  mov     [rbx+2Ch], ecx
0x1800526a9  mov     al, 1
0x1800526ab  mov     rbx, [rsp+48h+arg_8]
0x1800526b0  add     rsp, 40h
0x1800526b4  pop     rdi
0x1800526b5  retn
```
