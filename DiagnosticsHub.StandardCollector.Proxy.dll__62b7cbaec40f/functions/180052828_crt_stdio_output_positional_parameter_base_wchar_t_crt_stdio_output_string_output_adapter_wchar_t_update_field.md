# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::update_field_width(void)

- ea: `0x180052828`
- end: `0x180052996`
- name: `?update_field_width@?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180045bbc`
- `0x18004d970`

## callees

- `0x180007b48`
- `0x180038cb0`
- `0x180043108`
- `0x180052828`

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
0x180052828  mov     [rsp+arg_8], rbx
0x18005282d  push    rdi
0x18005282e  sub     rsp, 40h
0x180052832  cmp     dword ptr [rcx+474h], 1
0x180052839  mov     rbx, rcx
0x18005283c  jnz     short loc_180052855
0x18005283e  mov     r8, [rcx+18h]
0x180052842  lea     rdx, [r8+8]
0x180052846  mov     [rcx+18h], rdx
0x18005284a  mov     edx, [r8]
0x18005284d  mov     [rcx+2Ch], edx
0x180052850  jmp     loc_180052989
0x180052855  mov     rax, [rcx+10h]
0x180052859  lea     rdx, [rsp+48h+var_18]
0x18005285e  lea     rcx, [rsp+48h+arg_0]
0x180052863  mov     [rsp+48h+var_18], rax
0x180052868  mov     [rsp+48h+var_10], rcx
0x18005286d  mov     r9b, 1
0x180052870  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052874  mov     r8d, 0Ah
0x18005287a  mov     [rsp+48h+arg_0], rax
0x18005287f  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x180052884  cmp     dword ptr [rbx+470h], 1
0x18005288b  movsxd  r8, eax
0x18005288e  mov     rax, [rsp+48h+arg_0]
0x180052893  lea     edx, [r8-1]
0x180052897  lea     rcx, [rax+2]
0x18005289b  mov     [rbx+10h], rcx
0x18005289f  jnz     loc_180052978
0x1800528a5  xor     edi, edi
0x1800528a7  test    edx, edx
0x1800528a9  js      loc_180052948
0x1800528af  cmp     word ptr [rax], 24h ; '$'
0x1800528b3  jnz     loc_180052948
0x1800528b9  cmp     edx, 64h ; 'd'
0x1800528bc  jge     loc_180052948
0x1800528c2  mov     eax, [rbx+0DE0h]
0x1800528c8  cmp     edx, eax
0x1800528ca  mov     ecx, [rbx+34h]
0x1800528cd  movzx   r9d, word ptr [rbx+3Ah]
0x1800528d2  cmovle  edx, eax
0x1800528d5  mov     [rbx+0DE0h], edx
0x1800528db  lea     rax, [r8+2Fh]
0x1800528df  lea     rax, [rax+rax*2]
0x1800528e3  lea     rdx, [rbx+rax*8]
0x1800528e7  cmp     [rdx], edi
0x1800528e9  jnz     short loc_180052904
0x1800528eb  mov     dword ptr [rdx], 1
0x1800528f1  mov     [rdx+4], r9w
0x1800528f6  mov     [rdx+10h], ecx
0x1800528f9  mov     dil, 1
0x1800528fc  mov     al, dil
0x1800528ff  jmp     loc_18005298B
0x180052904  mov     dword ptr [rsp+48h+var_28], ecx
0x180052908  mov     r8d, 1
0x18005290e  mov     rcx, rbx
0x180052911  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@_WW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::parameter_type,wchar_t,__crt_stdio_output::length_modifier)
0x180052916  test    al, al
0x180052918  jnz     short loc_1800528F9
0x18005291a  mov     rax, [rbx+8]
0x18005291e  xor     r9d, r9d; LineNo
0x180052921  xor     r8d, r8d; FileName
0x180052924  xor     edx, edx; FunctionName
0x180052926  xor     ecx, ecx; Expression
0x180052928  mov     byte ptr [rax+30h], 1
0x18005292c  mov     dword ptr [rax+2Ch], 16h
0x180052933  mov     rax, [rbx+8]
0x180052937  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x18005293c  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052941  call    _invalid_parameter_internal
0x180052946  jmp     short loc_1800528FC
0x180052948  mov     rax, [rbx+8]
0x18005294c  xor     r9d, r9d; LineNo
0x18005294f  xor     r8d, r8d; FileName
0x180052952  xor     edx, edx; FunctionName
0x180052954  xor     ecx, ecx; Expression
0x180052956  mov     byte ptr [rax+30h], 1
0x18005295a  mov     dword ptr [rax+2Ch], 16h
0x180052961  mov     rax, [rbx+8]
0x180052965  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x18005296a  mov     [rsp+48h+var_28], rdi; uintptr_t
0x18005296f  call    _invalid_parameter_internal
0x180052974  xor     al, al
0x180052976  jmp     short loc_18005298B
0x180052978  lea     rcx, [r8+r8*2]
0x18005297c  mov     rax, [rbx+rcx*8+470h]
0x180052984  mov     ecx, [rax]
0x180052986  mov     [rbx+2Ch], ecx
0x180052989  mov     al, 1
0x18005298b  mov     rbx, [rsp+48h+arg_8]
0x180052990  add     rsp, 40h
0x180052994  pop     rdi
0x180052995  retn
```
