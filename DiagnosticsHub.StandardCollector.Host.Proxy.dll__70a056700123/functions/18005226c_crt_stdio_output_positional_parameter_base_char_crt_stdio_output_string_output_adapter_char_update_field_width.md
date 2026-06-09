# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::update_field_width(void)

- ea: `0x18005226c`
- end: `0x1800523d7`
- name: `?update_field_width@?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `363`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800445d0`
- `0x18004d51c`

## callees

- `0x1800073e8`
- `0x18003871c`
- `0x1800429f0`
- `0x18005226c`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::update_field_width(
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
      if ( !(unsigned __int8)__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::is_positional_parameter_reappearance_consistent(
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
0x18005226c  mov     [rsp+arg_8], rbx
0x180052271  push    rdi
0x180052272  sub     rsp, 40h
0x180052276  cmp     dword ptr [rcx+474h], 1
0x18005227d  mov     rbx, rcx
0x180052280  jnz     short loc_180052299
0x180052282  mov     r8, [rcx+18h]
0x180052286  lea     rdx, [r8+8]
0x18005228a  mov     [rcx+18h], rdx
0x18005228e  mov     edx, [r8]
0x180052291  mov     [rcx+2Ch], edx
0x180052294  jmp     loc_1800523CA
0x180052299  mov     rax, [rcx+10h]
0x18005229d  lea     rdx, [rsp+48h+var_18]
0x1800522a2  lea     rcx, [rsp+48h+arg_0]
0x1800522a7  mov     [rsp+48h+var_18], rax
0x1800522ac  mov     [rsp+48h+var_10], rcx
0x1800522b1  mov     r9b, 1
0x1800522b4  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x1800522b8  mov     r8d, 0Ah
0x1800522be  mov     [rsp+48h+arg_0], rax
0x1800522c3  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x1800522c8  cmp     dword ptr [rbx+470h], 1
0x1800522cf  movsxd  r8, eax
0x1800522d2  mov     rax, [rsp+48h+arg_0]
0x1800522d7  lea     edx, [r8-1]
0x1800522db  lea     rcx, [rax+1]
0x1800522df  mov     [rbx+10h], rcx
0x1800522e3  jnz     loc_1800523B9
0x1800522e9  xor     edi, edi
0x1800522eb  test    edx, edx
0x1800522ed  js      loc_180052389
0x1800522f3  cmp     byte ptr [rax], 24h ; '$'
0x1800522f6  jnz     loc_180052389
0x1800522fc  cmp     edx, 64h ; 'd'
0x1800522ff  jge     loc_180052389
0x180052305  mov     eax, [rbx+0DE0h]
0x18005230b  cmp     edx, eax
0x18005230d  mov     ecx, [rbx+34h]
0x180052310  mov     r9b, [rbx+39h]
0x180052314  cmovle  edx, eax
0x180052317  mov     [rbx+0DE0h], edx
0x18005231d  lea     rax, [r8+2Fh]
0x180052321  lea     rax, [rax+rax*2]
0x180052325  lea     rdx, [rbx+rax*8]
0x180052329  cmp     [rdx], edi
0x18005232b  jnz     short loc_180052345
0x18005232d  mov     dword ptr [rdx], 1
0x180052333  mov     [rdx+4], r9b
0x180052337  mov     [rdx+10h], ecx
0x18005233a  mov     dil, 1
0x18005233d  mov     al, dil
0x180052340  jmp     loc_1800523CC
0x180052345  mov     dword ptr [rsp+48h+var_28], ecx
0x180052349  mov     r8d, 1
0x18005234f  mov     rcx, rbx
0x180052352  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@DW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::parameter_type,char,__crt_stdio_output::length_modifier)
0x180052357  test    al, al
0x180052359  jnz     short loc_18005233A
0x18005235b  mov     rax, [rbx+8]
0x18005235f  xor     r9d, r9d; LineNo
0x180052362  xor     r8d, r8d; FileName
0x180052365  xor     edx, edx; FunctionName
0x180052367  xor     ecx, ecx; Expression
0x180052369  mov     byte ptr [rax+30h], 1
0x18005236d  mov     dword ptr [rax+2Ch], 16h
0x180052374  mov     rax, [rbx+8]
0x180052378  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x18005237d  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052382  call    _invalid_parameter_internal
0x180052387  jmp     short loc_18005233D
0x180052389  mov     rax, [rbx+8]
0x18005238d  xor     r9d, r9d; LineNo
0x180052390  xor     r8d, r8d; FileName
0x180052393  xor     edx, edx; FunctionName
0x180052395  xor     ecx, ecx; Expression
0x180052397  mov     byte ptr [rax+30h], 1
0x18005239b  mov     dword ptr [rax+2Ch], 16h
0x1800523a2  mov     rax, [rbx+8]
0x1800523a6  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x1800523ab  mov     [rsp+48h+var_28], rdi; uintptr_t
0x1800523b0  call    _invalid_parameter_internal
0x1800523b5  xor     al, al
0x1800523b7  jmp     short loc_1800523CC
0x1800523b9  lea     rcx, [r8+r8*2]
0x1800523bd  mov     rax, [rbx+rcx*8+470h]
0x1800523c5  mov     ecx, [rax]
0x1800523c7  mov     [rbx+2Ch], ecx
0x1800523ca  mov     al, 1
0x1800523cc  mov     rbx, [rsp+48h+arg_8]
0x1800523d1  add     rsp, 40h
0x1800523d5  pop     rdi
0x1800523d6  retn
```
