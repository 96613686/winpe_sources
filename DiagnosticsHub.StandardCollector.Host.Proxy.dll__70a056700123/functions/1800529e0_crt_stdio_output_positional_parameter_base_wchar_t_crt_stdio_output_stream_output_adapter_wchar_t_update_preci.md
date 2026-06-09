# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::update_precision(void)

- ea: `0x1800529e0`
- end: `0x180052b4e`
- name: `?update_precision@?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180045000`
- `0x180047fc8`

## callees

- `0x1800073e8`
- `0x1800389d0`
- `0x180042c24`
- `0x1800529e0`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::update_precision(
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
  *(_DWORD *)(a1 + 48) = *v2;
  return 1;
}

```

## disassembly

```asm
0x1800529e0  mov     [rsp+arg_8], rbx
0x1800529e5  push    rdi
0x1800529e6  sub     rsp, 40h
0x1800529ea  cmp     dword ptr [rcx+474h], 1
0x1800529f1  mov     rbx, rcx
0x1800529f4  jnz     short loc_180052A0D
0x1800529f6  mov     r8, [rcx+18h]
0x1800529fa  lea     rdx, [r8+8]
0x1800529fe  mov     [rcx+18h], rdx
0x180052a02  mov     edx, [r8]
0x180052a05  mov     [rcx+30h], edx
0x180052a08  jmp     loc_180052B41
0x180052a0d  mov     rax, [rcx+10h]
0x180052a11  lea     rdx, [rsp+48h+var_18]
0x180052a16  lea     rcx, [rsp+48h+arg_0]
0x180052a1b  mov     [rsp+48h+var_18], rax
0x180052a20  mov     [rsp+48h+var_10], rcx
0x180052a25  mov     r9b, 1
0x180052a28  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052a2c  mov     r8d, 0Ah
0x180052a32  mov     [rsp+48h+arg_0], rax
0x180052a37  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x180052a3c  cmp     dword ptr [rbx+470h], 1
0x180052a43  movsxd  r8, eax
0x180052a46  mov     rax, [rsp+48h+arg_0]
0x180052a4b  lea     edx, [r8-1]
0x180052a4f  lea     rcx, [rax+2]
0x180052a53  mov     [rbx+10h], rcx
0x180052a57  jnz     loc_180052B30
0x180052a5d  xor     edi, edi
0x180052a5f  test    edx, edx
0x180052a61  js      loc_180052B00
0x180052a67  cmp     word ptr [rax], 24h ; '$'
0x180052a6b  jnz     loc_180052B00
0x180052a71  cmp     edx, 64h ; 'd'
0x180052a74  jge     loc_180052B00
0x180052a7a  mov     eax, [rbx+0DE0h]
0x180052a80  cmp     edx, eax
0x180052a82  mov     ecx, [rbx+34h]
0x180052a85  movzx   r9d, word ptr [rbx+3Ah]
0x180052a8a  cmovle  edx, eax
0x180052a8d  mov     [rbx+0DE0h], edx
0x180052a93  lea     rax, [r8+2Fh]
0x180052a97  lea     rax, [rax+rax*2]
0x180052a9b  lea     rdx, [rbx+rax*8]
0x180052a9f  cmp     [rdx], edi
0x180052aa1  jnz     short loc_180052ABC
0x180052aa3  mov     dword ptr [rdx], 1
0x180052aa9  mov     [rdx+4], r9w
0x180052aae  mov     [rdx+10h], ecx
0x180052ab1  mov     dil, 1
0x180052ab4  mov     al, dil
0x180052ab7  jmp     loc_180052B43
0x180052abc  mov     dword ptr [rsp+48h+var_28], ecx
0x180052ac0  mov     r8d, 1
0x180052ac6  mov     rcx, rbx
0x180052ac9  call    ?is_positional_parameter_reappearance_consistent@?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@AEAA_NAEBUparameter_data@12@W4parameter_type@12@_WW4length_modifier@2@@Z; __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::is_positional_parameter_reappearance_consistent(__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::parameter_data const &,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::parameter_type,wchar_t,__crt_stdio_output::length_modifier)
0x180052ace  test    al, al
0x180052ad0  jnz     short loc_180052AB1
0x180052ad2  mov     rax, [rbx+8]
0x180052ad6  xor     r9d, r9d; LineNo
0x180052ad9  xor     r8d, r8d; FileName
0x180052adc  xor     edx, edx; FunctionName
0x180052ade  xor     ecx, ecx; Expression
0x180052ae0  mov     byte ptr [rax+30h], 1
0x180052ae4  mov     dword ptr [rax+2Ch], 16h
0x180052aeb  mov     rax, [rbx+8]
0x180052aef  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052af4  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052af9  call    _invalid_parameter_internal
0x180052afe  jmp     short loc_180052AB4
0x180052b00  mov     rax, [rbx+8]
0x180052b04  xor     r9d, r9d; LineNo
0x180052b07  xor     r8d, r8d; FileName
0x180052b0a  xor     edx, edx; FunctionName
0x180052b0c  xor     ecx, ecx; Expression
0x180052b0e  mov     byte ptr [rax+30h], 1
0x180052b12  mov     dword ptr [rax+2Ch], 16h
0x180052b19  mov     rax, [rbx+8]
0x180052b1d  mov     [rsp+48h+var_20], rax; __crt_cached_ptd_host *
0x180052b22  mov     [rsp+48h+var_28], rdi; uintptr_t
0x180052b27  call    _invalid_parameter_internal
0x180052b2c  xor     al, al
0x180052b2e  jmp     short loc_180052B43
0x180052b30  lea     rcx, [r8+r8*2]
0x180052b34  mov     rax, [rbx+rcx*8+470h]
0x180052b3c  mov     ecx, [rax]
0x180052b3e  mov     [rbx+30h], ecx
0x180052b41  mov     al, 1
0x180052b43  mov     rbx, [rsp+48h+arg_8]
0x180052b48  add     rsp, 40h
0x180052b4c  pop     rdi
0x180052b4d  retn
```
