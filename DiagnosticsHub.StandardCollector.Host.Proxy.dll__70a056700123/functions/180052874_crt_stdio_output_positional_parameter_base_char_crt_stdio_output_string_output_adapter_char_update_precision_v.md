# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::update_precision(void)

- ea: `0x180052874`
- end: `0x1800529df`
- name: `?update_precision@?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `363`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800445d0`
- `0x180047f24`

## callees

- `0x1800073e8`
- `0x18003871c`
- `0x1800429f0`
- `0x180052874`

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
0x180052874  mov     [rsp+arg_8], rbx
0x180052879  push    rdi
0x18005287a  sub     rsp, 40h
0x18005287e  cmp     dword ptr [rcx+474h], 1
0x180052885  mov     rbx, rcx
0x180052888  jnz     short loc_1800528A1
0x18005288a  mov     r8, [rcx+18h]
0x18005288e  lea     rdx, [r8+8]
0x180052892  mov     [rcx+18h], rdx
0x180052896  mov     edx, [r8]
0x180052899  mov     [rcx+30h], edx
0x18005289c  jmp     loc_1800529D2
0x1800528a1  mov     rax, [rcx+10h]
0x1800528a5  lea     rdx, [rsp+48h+var_18]
0x1800528aa  lea     rcx, [rsp+48h+arg_0]
0x1800528af  mov     [rsp+48h+var_18], rax
0x1800528b4  mov     [rsp+48h+var_10], rcx
0x1800528b9  mov     r9b, 1
0x1800528bc  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x1800528c0  mov     r8d, 0Ah
0x1800528c6  mov     [rsp+48h+arg_0], rax
0x1800528cb  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x1800528d0  cmp     dword ptr [rbx+470h], 1
0x1800528d7  movsxd  r8, eax
0x1800528da  mov     rax, [rsp+48h+arg_0]
0x1800528df  lea     edx, [r8-1]
0x1800528e3  lea     rcx, [rax+1]
0x1800528e7  mov     [rbx+10h], rcx
0x1800528eb  jnz     loc_1800529C1
0x1800528f1  xor     edi, edi
0x1800528f3  test    edx, edx
0x1800528f5  js      loc_180052991
0x1800528fb  cmp     byte ptr [rax], 24h ; '$'
0x1800528fe  jnz     loc_180052991
0x180052904  cmp     edx, 64h ; 'd'
0x180052907  jge     loc_180052991
0x18005290d  mov     eax, [rbx+0DE0h]
0x180052913  cmp     edx, eax
0x180052915  mov     ecx, [rbx+34h]
0x180052918  mov     r9b, [rbx+39h]
0x18005291c  cmovle  edx, eax
0x18005291f  mov     [rbx+0DE0h], edx
0x180052925  lea     rax, [r8+2Fh]
0x180052929  lea     rax, [rax+rax*2]
0x18005292d  lea     rdx, [rbx+rax*8]
0x180052931  cmp     [rdx], edi
0x180052933  jnz     short loc_18005294D
0x180052935  mov     dword ptr [rdx], 1
0x18005293b  mov     [rdx+4], r9b
0x18005293f  mov     [rdx+10h], ecx
0x180052942  mov     dil, 1
0x180052945  mov     al, dil
0x180052948  jmp     loc_1800529D4
0x18005294d  mov     dword ptr [rsp+48h+var_28], ecx
0x180052951  mov     r8d, 1
0x180052957  mov     rcx, rbx
0x18005295a  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@DW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::parameter_type,char,__crt_stdio_output::length_modifier)
0x18005295f  test    al, al
0x180052961  jnz     short loc_180052942
0x180052963  mov     rax, [rbx+8]
0x180052967  xor     r9d, r9d; LineNo
0x18005296a  xor     r8d, r8d; FileName
0x18005296d  xor     edx, edx; FunctionName
0x18005296f  xor     ecx, ecx; Expression
0x180052971  mov     byte ptr [rax+30h], 1
0x180052975  mov     dword ptr [rax+2Ch], 16h
0x18005297c  mov     rax, [rbx+8]
0x180052980  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052985  mov     [rsp+48h+var_28], rdi; uintptr_t
0x18005298a  call    _invalid_parameter_internal
0x18005298f  jmp     short loc_180052945
0x180052991  mov     rax, [rbx+8]
0x180052995  xor     r9d, r9d; LineNo
0x180052998  xor     r8d, r8d; FileName
0x18005299b  xor     edx, edx; FunctionName
0x18005299d  xor     ecx, ecx; Expression
0x18005299f  mov     byte ptr [rax+30h], 1
0x1800529a3  mov     dword ptr [rax+2Ch], 16h
0x1800529aa  mov     rax, [rbx+8]
0x1800529ae  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x1800529b3  mov     [rsp+48h+var_28], rdi; uintptr_t
0x1800529b8  call    _invalid_parameter_internal
0x1800529bd  xor     al, al
0x1800529bf  jmp     short loc_1800529D4
0x1800529c1  lea     rcx, [r8+r8*2]
0x1800529c5  mov     rax, [rbx+rcx*8+470h]
0x1800529cd  mov     ecx, [rax]
0x1800529cf  mov     [rbx+30h], ecx
0x1800529d2  mov     al, 1
0x1800529d4  mov     rbx, [rsp+48h+arg_8]
0x1800529d9  add     rsp, 40h
0x1800529dd  pop     rdi
0x1800529de  retn
```
