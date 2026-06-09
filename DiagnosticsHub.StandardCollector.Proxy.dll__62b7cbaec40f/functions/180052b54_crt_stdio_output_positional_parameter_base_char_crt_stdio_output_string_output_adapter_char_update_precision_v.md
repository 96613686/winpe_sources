# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::update_precision(void)

- ea: `0x180052b54`
- end: `0x180052cbf`
- name: `?update_precision@?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `363`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800448b0`
- `0x180048204`

## callees

- `0x180007b48`
- `0x1800389fc`
- `0x180042cd0`
- `0x180052b54`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::update_precision(
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
      *(_DWORD *)(a1 + 48) = **(_DWORD **)(a1 + 24 * v7 + 1136);
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
  *(_DWORD *)(a1 + 48) = *v2;
  return 1;
}

```

## disassembly

```asm
0x180052b54  mov     [rsp+arg_8], rbx
0x180052b59  push    rdi
0x180052b5a  sub     rsp, 40h
0x180052b5e  cmp     dword ptr [rcx+474h], 1
0x180052b65  mov     rbx, rcx
0x180052b68  jnz     short loc_180052B81
0x180052b6a  mov     r8, [rcx+18h]
0x180052b6e  lea     rdx, [r8+8]
0x180052b72  mov     [rcx+18h], rdx
0x180052b76  mov     edx, [r8]
0x180052b79  mov     [rcx+30h], edx
0x180052b7c  jmp     loc_180052CB2
0x180052b81  mov     rax, [rcx+10h]
0x180052b85  lea     rdx, [rsp+48h+var_18]
0x180052b8a  lea     rcx, [rsp+48h+arg_0]
0x180052b8f  mov     [rsp+48h+var_18], rax
0x180052b94  mov     [rsp+48h+var_10], rcx
0x180052b99  mov     r9b, 1
0x180052b9c  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052ba0  mov     r8d, 0Ah
0x180052ba6  mov     [rsp+48h+arg_0], rax
0x180052bab  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x180052bb0  cmp     dword ptr [rbx+470h], 1
0x180052bb7  movsxd  r8, eax
0x180052bba  mov     rax, [rsp+48h+arg_0]
0x180052bbf  lea     edx, [r8-1]
0x180052bc3  lea     rcx, [rax+1]
0x180052bc7  mov     [rbx+10h], rcx
0x180052bcb  jnz     loc_180052CA1
0x180052bd1  xor     edi, edi
0x180052bd3  test    edx, edx
0x180052bd5  js      loc_180052C71
0x180052bdb  cmp     byte ptr [rax], 24h ; '$'
0x180052bde  jnz     loc_180052C71
0x180052be4  cmp     edx, 64h ; 'd'
0x180052be7  jge     loc_180052C71
0x180052bed  mov     eax, [rbx+0DE0h]
0x180052bf3  cmp     edx, eax
0x180052bf5  mov     ecx, [rbx+34h]
0x180052bf8  mov     r9b, [rbx+39h]
0x180052bfc  cmovle  edx, eax
0x180052bff  mov     [rbx+0DE0h], edx
0x180052c05  lea     rax, [r8+2Fh]
0x180052c09  lea     rax, [rax+rax*2]
0x180052c0d  lea     rdx, [rbx+rax*8]
0x180052c11  cmp     [rdx], edi
0x180052c13  jnz     short loc_180052C2D
0x180052c15  mov     dword ptr [rdx], 1
0x180052c1b  mov     [rdx+4], r9b
0x180052c1f  mov     [rdx+10h], ecx
0x180052c22  mov     dil, 1
0x180052c25  mov     al, dil
0x180052c28  jmp     loc_180052CB4
0x180052c2d  mov     dword ptr [rsp+48h+var_28], ecx
0x180052c31  mov     r8d, 1
0x180052c37  mov     rcx, rbx
0x180052c3a  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@DW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::parameter_type,char,__crt_stdio_output::length_modifier)
0x180052c3f  test    al, al
0x180052c41  jnz     short loc_180052C22
0x180052c43  mov     rax, [rbx+8]
0x180052c47  xor     r9d, r9d; LineNo
0x180052c4a  xor     r8d, r8d; FileName
0x180052c4d  xor     edx, edx; FunctionName
0x180052c4f  xor     ecx, ecx; Expression
0x180052c51  mov     byte ptr [rax+30h], 1
0x180052c55  mov     dword ptr [rax+2Ch], 16h
0x180052c5c  mov     rax, [rbx+8]
0x180052c60  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052c65  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052c6a  call    _invalid_parameter_internal
0x180052c6f  jmp     short loc_180052C25
0x180052c71  mov     rax, [rbx+8]
0x180052c75  xor     r9d, r9d; LineNo
0x180052c78  xor     r8d, r8d; FileName
0x180052c7b  xor     edx, edx; FunctionName
0x180052c7d  xor     ecx, ecx; Expression
0x180052c7f  mov     byte ptr [rax+30h], 1
0x180052c83  mov     dword ptr [rax+2Ch], 16h
0x180052c8a  mov     rax, [rbx+8]
0x180052c8e  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052c93  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052c98  call    _invalid_parameter_internal
0x180052c9d  xor     al, al
0x180052c9f  jmp     short loc_180052CB4
0x180052ca1  lea     rcx, [r8+r8*2]
0x180052ca5  mov     rax, [rbx+rcx*8+470h]
0x180052cad  mov     ecx, [rax]
0x180052caf  mov     [rbx+30h], ecx
0x180052cb2  mov     al, 1
0x180052cb4  mov     rbx, [rsp+48h+arg_8]
0x180052cb9  add     rsp, 40h
0x180052cbd  pop     rdi
0x180052cbe  retn
```
