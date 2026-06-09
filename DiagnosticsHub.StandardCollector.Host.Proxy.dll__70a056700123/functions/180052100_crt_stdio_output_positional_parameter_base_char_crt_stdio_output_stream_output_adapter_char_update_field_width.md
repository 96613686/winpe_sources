# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::update_field_width(void)

- ea: `0x180052100`
- end: `0x18005226b`
- name: `?update_field_width@?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `363`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180043acc`
- `0x18004d464`

## callees

- `0x1800073e8`
- `0x18003871c`
- `0x1800427bc`
- `0x180052100`

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
0x180052100  mov     [rsp+arg_8], rbx
0x180052105  push    rdi
0x180052106  sub     rsp, 40h
0x18005210a  cmp     dword ptr [rcx+474h], 1
0x180052111  mov     rbx, rcx
0x180052114  jnz     short loc_18005212D
0x180052116  mov     r8, [rcx+18h]
0x18005211a  lea     rdx, [r8+8]
0x18005211e  mov     [rcx+18h], rdx
0x180052122  mov     edx, [r8]
0x180052125  mov     [rcx+2Ch], edx
0x180052128  jmp     loc_18005225E
0x18005212d  mov     rax, [rcx+10h]
0x180052131  lea     rdx, [rsp+48h+var_18]
0x180052136  lea     rcx, [rsp+48h+arg_0]
0x18005213b  mov     [rsp+48h+var_18], rax
0x180052140  mov     [rsp+48h+var_10], rcx
0x180052145  mov     r9b, 1
0x180052148  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x18005214c  mov     r8d, 0Ah
0x180052152  mov     [rsp+48h+arg_0], rax
0x180052157  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x18005215c  cmp     dword ptr [rbx+470h], 1
0x180052163  movsxd  r8, eax
0x180052166  mov     rax, [rsp+48h+arg_0]
0x18005216b  lea     edx, [r8-1]
0x18005216f  lea     rcx, [rax+1]
0x180052173  mov     [rbx+10h], rcx
0x180052177  jnz     loc_18005224D
0x18005217d  xor     edi, edi
0x18005217f  test    edx, edx
0x180052181  js      loc_18005221D
0x180052187  cmp     byte ptr [rax], 24h ; '$'
0x18005218a  jnz     loc_18005221D
0x180052190  cmp     edx, 64h ; 'd'
0x180052193  jge     loc_18005221D
0x180052199  mov     eax, [rbx+0DE0h]
0x18005219f  cmp     edx, eax
0x1800521a1  mov     ecx, [rbx+34h]
0x1800521a4  mov     r9b, [rbx+39h]
0x1800521a8  cmovle  edx, eax
0x1800521ab  mov     [rbx+0DE0h], edx
0x1800521b1  lea     rax, [r8+2Fh]
0x1800521b5  lea     rax, [rax+rax*2]
0x1800521b9  lea     rdx, [rbx+rax*8]
0x1800521bd  cmp     [rdx], edi
0x1800521bf  jnz     short loc_1800521D9
0x1800521c1  mov     dword ptr [rdx], 1
0x1800521c7  mov     [rdx+4], r9b
0x1800521cb  mov     [rdx+10h], ecx
0x1800521ce  mov     dil, 1
0x1800521d1  mov     al, dil
0x1800521d4  jmp     loc_180052260
0x1800521d9  mov     dword ptr [rsp+48h+var_28], ecx
0x1800521dd  mov     r8d, 1
0x1800521e3  mov     rcx, rbx
0x1800521e6  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@DW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::parameter_type,char,__crt_stdio_output::length_modifier)
0x1800521eb  test    al, al
0x1800521ed  jnz     short loc_1800521CE
0x1800521ef  mov     rax, [rbx+8]
0x1800521f3  xor     r9d, r9d; LineNo
0x1800521f6  xor     r8d, r8d; FileName
0x1800521f9  xor     edx, edx; FunctionName
0x1800521fb  xor     ecx, ecx; Expression
0x1800521fd  mov     byte ptr [rax+30h], 1
0x180052201  mov     dword ptr [rax+2Ch], 16h
0x180052208  mov     rax, [rbx+8]
0x18005220c  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052211  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052216  call    _invalid_parameter_internal
0x18005221b  jmp     short loc_1800521D1
0x18005221d  mov     rax, [rbx+8]
0x180052221  xor     r9d, r9d; LineNo
0x180052224  xor     r8d, r8d; FileName
0x180052227  xor     edx, edx; FunctionName
0x180052229  xor     ecx, ecx; Expression
0x18005222b  mov     byte ptr [rax+30h], 1
0x18005222f  mov     dword ptr [rax+2Ch], 16h
0x180052236  mov     rax, [rbx+8]
0x18005223a  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x18005223f  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052244  call    _invalid_parameter_internal
0x180052249  xor     al, al
0x18005224b  jmp     short loc_180052260
0x18005224d  lea     rcx, [r8+r8*2]
0x180052251  mov     rax, [rbx+rcx*8+470h]
0x180052259  mov     ecx, [rax]
0x18005225b  mov     [rbx+2Ch], ecx
0x18005225e  mov     al, 1
0x180052260  mov     rbx, [rsp+48h+arg_8]
0x180052265  add     rsp, 40h
0x180052269  pop     rdi
0x18005226a  retn
```
