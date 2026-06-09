# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::update_precision(void)

- ea: `0x1800529e8`
- end: `0x180052b53`
- name: `?update_precision@?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `363`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180043dac`
- `0x180048160`

## callees

- `0x180007b48`
- `0x1800389fc`
- `0x180042a9c`
- `0x1800529e8`

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
0x1800529e8  mov     [rsp+arg_8], rbx
0x1800529ed  push    rdi
0x1800529ee  sub     rsp, 40h
0x1800529f2  cmp     dword ptr [rcx+474h], 1
0x1800529f9  mov     rbx, rcx
0x1800529fc  jnz     short loc_180052A15
0x1800529fe  mov     r8, [rcx+18h]
0x180052a02  lea     rdx, [r8+8]
0x180052a06  mov     [rcx+18h], rdx
0x180052a0a  mov     edx, [r8]
0x180052a0d  mov     [rcx+30h], edx
0x180052a10  jmp     loc_180052B46
0x180052a15  mov     rax, [rcx+10h]
0x180052a19  lea     rdx, [rsp+48h+var_18]
0x180052a1e  lea     rcx, [rsp+48h+arg_0]
0x180052a23  mov     [rsp+48h+var_18], rax
0x180052a28  mov     [rsp+48h+var_10], rcx
0x180052a2d  mov     r9b, 1
0x180052a30  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052a34  mov     r8d, 0Ah
0x180052a3a  mov     [rsp+48h+arg_0], rax
0x180052a3f  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x180052a44  cmp     dword ptr [rbx+470h], 1
0x180052a4b  movsxd  r8, eax
0x180052a4e  mov     rax, [rsp+48h+arg_0]
0x180052a53  lea     edx, [r8-1]
0x180052a57  lea     rcx, [rax+1]
0x180052a5b  mov     [rbx+10h], rcx
0x180052a5f  jnz     loc_180052B35
0x180052a65  xor     edi, edi
0x180052a67  test    edx, edx
0x180052a69  js      loc_180052B05
0x180052a6f  cmp     byte ptr [rax], 24h ; '$'
0x180052a72  jnz     loc_180052B05
0x180052a78  cmp     edx, 64h ; 'd'
0x180052a7b  jge     loc_180052B05
0x180052a81  mov     eax, [rbx+0DE0h]
0x180052a87  cmp     edx, eax
0x180052a89  mov     ecx, [rbx+34h]
0x180052a8c  mov     r9b, [rbx+39h]
0x180052a90  cmovle  edx, eax
0x180052a93  mov     [rbx+0DE0h], edx
0x180052a99  lea     rax, [r8+2Fh]
0x180052a9d  lea     rax, [rax+rax*2]
0x180052aa1  lea     rdx, [rbx+rax*8]
0x180052aa5  cmp     [rdx], edi
0x180052aa7  jnz     short loc_180052AC1
0x180052aa9  mov     dword ptr [rdx], 1
0x180052aaf  mov     [rdx+4], r9b
0x180052ab3  mov     [rdx+10h], ecx
0x180052ab6  mov     dil, 1
0x180052ab9  mov     al, dil
0x180052abc  jmp     loc_180052B48
0x180052ac1  mov     dword ptr [rsp+48h+var_28], ecx
0x180052ac5  mov     r8d, 1
0x180052acb  mov     rcx, rbx
0x180052ace  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@DW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::parameter_type,char,__crt_stdio_output::length_modifier)
0x180052ad3  test    al, al
0x180052ad5  jnz     short loc_180052AB6
0x180052ad7  mov     rax, [rbx+8]
0x180052adb  xor     r9d, r9d; LineNo
0x180052ade  xor     r8d, r8d; FileName
0x180052ae1  xor     edx, edx; FunctionName
0x180052ae3  xor     ecx, ecx; Expression
0x180052ae5  mov     byte ptr [rax+30h], 1
0x180052ae9  mov     dword ptr [rax+2Ch], 16h
0x180052af0  mov     rax, [rbx+8]
0x180052af4  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052af9  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052afe  call    _invalid_parameter_internal
0x180052b03  jmp     short loc_180052AB9
0x180052b05  mov     rax, [rbx+8]
0x180052b09  xor     r9d, r9d; LineNo
0x180052b0c  xor     r8d, r8d; FileName
0x180052b0f  xor     edx, edx; FunctionName
0x180052b11  xor     ecx, ecx; Expression
0x180052b13  mov     byte ptr [rax+30h], 1
0x180052b17  mov     dword ptr [rax+2Ch], 16h
0x180052b1e  mov     rax, [rbx+8]
0x180052b22  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052b27  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052b2c  call    _invalid_parameter_internal
0x180052b31  xor     al, al
0x180052b33  jmp     short loc_180052B48
0x180052b35  lea     rcx, [r8+r8*2]
0x180052b39  mov     rax, [rbx+rcx*8+470h]
0x180052b41  mov     ecx, [rax]
0x180052b43  mov     [rbx+30h], ecx
0x180052b46  mov     al, 1
0x180052b48  mov     rbx, [rsp+48h+arg_8]
0x180052b4d  add     rsp, 40h
0x180052b51  pop     rdi
0x180052b52  retn
```
