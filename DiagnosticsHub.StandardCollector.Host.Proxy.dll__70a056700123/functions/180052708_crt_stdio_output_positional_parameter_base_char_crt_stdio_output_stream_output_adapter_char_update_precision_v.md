# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::update_precision(void)

- ea: `0x180052708`
- end: `0x180052873`
- name: `?update_precision@?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `363`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180043acc`
- `0x180047e80`

## callees

- `0x1800073e8`
- `0x18003871c`
- `0x1800427bc`
- `0x180052708`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::update_precision(
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
  *(_DWORD *)(a1 + 48) = *v2;
  return 1;
}

```

## disassembly

```asm
0x180052708  mov     [rsp+arg_8], rbx
0x18005270d  push    rdi
0x18005270e  sub     rsp, 40h
0x180052712  cmp     dword ptr [rcx+474h], 1
0x180052719  mov     rbx, rcx
0x18005271c  jnz     short loc_180052735
0x18005271e  mov     r8, [rcx+18h]
0x180052722  lea     rdx, [r8+8]
0x180052726  mov     [rcx+18h], rdx
0x18005272a  mov     edx, [r8]
0x18005272d  mov     [rcx+30h], edx
0x180052730  jmp     loc_180052866
0x180052735  mov     rax, [rcx+10h]
0x180052739  lea     rdx, [rsp+48h+var_18]
0x18005273e  lea     rcx, [rsp+48h+arg_0]
0x180052743  mov     [rsp+48h+var_18], rax
0x180052748  mov     [rsp+48h+var_10], rcx
0x18005274d  mov     r9b, 1
0x180052750  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052754  mov     r8d, 0Ah
0x18005275a  mov     [rsp+48h+arg_0], rax
0x18005275f  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x180052764  cmp     dword ptr [rbx+470h], 1
0x18005276b  movsxd  r8, eax
0x18005276e  mov     rax, [rsp+48h+arg_0]
0x180052773  lea     edx, [r8-1]
0x180052777  lea     rcx, [rax+1]
0x18005277b  mov     [rbx+10h], rcx
0x18005277f  jnz     loc_180052855
0x180052785  xor     edi, edi
0x180052787  test    edx, edx
0x180052789  js      loc_180052825
0x18005278f  cmp     byte ptr [rax], 24h ; '$'
0x180052792  jnz     loc_180052825
0x180052798  cmp     edx, 64h ; 'd'
0x18005279b  jge     loc_180052825
0x1800527a1  mov     eax, [rbx+0DE0h]
0x1800527a7  cmp     edx, eax
0x1800527a9  mov     ecx, [rbx+34h]
0x1800527ac  mov     r9b, [rbx+39h]
0x1800527b0  cmovle  edx, eax
0x1800527b3  mov     [rbx+0DE0h], edx
0x1800527b9  lea     rax, [r8+2Fh]
0x1800527bd  lea     rax, [rax+rax*2]
0x1800527c1  lea     rdx, [rbx+rax*8]
0x1800527c5  cmp     [rdx], edi
0x1800527c7  jnz     short loc_1800527E1
0x1800527c9  mov     dword ptr [rdx], 1
0x1800527cf  mov     [rdx+4], r9b
0x1800527d3  mov     [rdx+10h], ecx
0x1800527d6  mov     dil, 1
0x1800527d9  mov     al, dil
0x1800527dc  jmp     loc_180052868
0x1800527e1  mov     dword ptr [rsp+48h+var_28], ecx
0x1800527e5  mov     r8d, 1
0x1800527eb  mov     rcx, rbx
0x1800527ee  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@DW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::parameter_type,char,__crt_stdio_output::length_modifier)
0x1800527f3  test    al, al
0x1800527f5  jnz     short loc_1800527D6
0x1800527f7  mov     rax, [rbx+8]
0x1800527fb  xor     r9d, r9d; LineNo
0x1800527fe  xor     r8d, r8d; FileName
0x180052801  xor     edx, edx; FunctionName
0x180052803  xor     ecx, ecx; Expression
0x180052805  mov     byte ptr [rax+30h], 1
0x180052809  mov     dword ptr [rax+2Ch], 16h
0x180052810  mov     rax, [rbx+8]
0x180052814  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052819  mov     [rsp+48h+var_28], rdi; uintptr_t
0x18005281e  call    _invalid_parameter_internal
0x180052823  jmp     short loc_1800527D9
0x180052825  mov     rax, [rbx+8]
0x180052829  xor     r9d, r9d; LineNo
0x18005282c  xor     r8d, r8d; FileName
0x18005282f  xor     edx, edx; FunctionName
0x180052831  xor     ecx, ecx; Expression
0x180052833  mov     byte ptr [rax+30h], 1
0x180052837  mov     dword ptr [rax+2Ch], 16h
0x18005283e  mov     rax, [rbx+8]
0x180052842  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052847  mov     [rsp+48h+var_28], rdi; uintptr_t
0x18005284c  call    _invalid_parameter_internal
0x180052851  xor     al, al
0x180052853  jmp     short loc_180052868
0x180052855  lea     rcx, [r8+r8*2]
0x180052859  mov     rax, [rbx+rcx*8+470h]
0x180052861  mov     ecx, [rax]
0x180052863  mov     [rbx+30h], ecx
0x180052866  mov     al, 1
0x180052868  mov     rbx, [rsp+48h+arg_8]
0x18005286d  add     rsp, 40h
0x180052871  pop     rdi
0x180052872  retn
```
