# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::validate_and_update_state_at_beginning_of_format_character(void)

- ea: `0x1800533b8`
- end: `0x1800534fb`
- name: `?validate_and_update_state_at_beginning_of_format_character@?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800448b0`

## callees

- `0x180007b48`
- `0x1800389fc`
- `0x1800533b8`
- `0x180060550`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::validate_and_update_state_at_beginning_of_format_character(
        __int64 a1)
{
  _BYTE *v2; // rcx
  int v3; // edx
  __crt_cached_ptd_host *v4; // rcx
  _BYTE *v6; // rax
  __crt_cached_ptd_host *v7; // rcx
  int v8; // eax
  bool v9; // zf
  _BYTE *v10; // rcx
  int v11; // edx
  __int64 v12; // rax
  _BYTE *v13; // [rsp+30h] [rbp-10h] BYREF
  _QWORD *v14; // [rsp+38h] [rbp-8h]
  _BYTE *v15; // [rsp+50h] [rbp+10h] BYREF
  _BYTE *v16; // [rsp+58h] [rbp+18h] BYREF

  if ( *(_BYTE *)(a1 + 36) != 1 )
    return 1;
  v2 = *(_BYTE **)(a1 + 16);
  if ( *v2 == 37 )
    return 1;
  v3 = *(_DWORD *)(a1 + 1140);
  if ( v3 )
  {
    if ( v3 == 2 )
      goto LABEL_13;
    return 1;
  }
  if ( (unsigned __int8)(*v2 - 48) > 9u
    || (v13 = v2,
        v15 = v2,
        v4 = *(__crt_cached_ptd_host **)(a1 + 8),
        v14 = &v15,
        (int)__crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<char>,0>(
               v4,
               (__int64)&v13,
               10,
               1u) <= 0)
    || *v15 != 36 )
  {
    *(_DWORD *)(a1 + 1140) = 1;
    return 1;
  }
  if ( *(_DWORD *)(a1 + 1136) == 1 )
    memset((void *)(a1 + 1152), 0, 0x960u);
  *(_DWORD *)(a1 + 1140) = 2;
LABEL_13:
  v6 = *(_BYTE **)(a1 + 16);
  v14 = &v16;
  v7 = *(__crt_cached_ptd_host **)(a1 + 8);
  v13 = v6;
  v16 = v6;
  v8 = __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<char>,0>(
         v7,
         (__int64)&v13,
         10,
         1u);
  v9 = *(_DWORD *)(a1 + 1136) == 1;
  v10 = v16;
  v11 = v8 - 1;
  *(_DWORD *)(a1 + 3556) = v8 - 1;
  *(_QWORD *)(a1 + 16) = v10 + 1;
  if ( !v9 )
    return 1;
  if ( v11 >= 0 && *v10 == 36 && v11 < 100 )
  {
    if ( v11 <= *(_DWORD *)(a1 + 3552) )
      v11 = *(_DWORD *)(a1 + 3552);
    *(_DWORD *)(a1 + 3552) = v11;
    return 1;
  }
  v12 = *(_QWORD *)(a1 + 8);
  *(_BYTE *)(v12 + 48) = 1;
  *(_DWORD *)(v12 + 44) = 22;
  invalid_parameter_internal(0, 0, 0, 0, 0, *(__crt_cached_ptd_host **)(a1 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800533b8  mov     [rsp-8+arg_10], rbx
0x1800533bd  push    rbp
0x1800533be  mov     rbp, rsp
0x1800533c1  sub     rsp, 40h
0x1800533c5  cmp     byte ptr [rcx+24h], 1
0x1800533c9  mov     rbx, rcx
0x1800533cc  jnz     short loc_18005344C
0x1800533ce  mov     rcx, [rcx+10h]
0x1800533d2  mov     al, [rcx]
0x1800533d4  cmp     al, 25h ; '%'
0x1800533d6  jz      short loc_18005344C
0x1800533d8  mov     edx, [rbx+474h]
0x1800533de  test    edx, edx
0x1800533e0  jnz     short loc_180053459
0x1800533e2  sub     al, 30h ; '0'
0x1800533e4  cmp     al, 9
0x1800533e6  ja      short loc_180053442
0x1800533e8  mov     [rbp+var_10], rcx
0x1800533ec  lea     rax, [rbp+arg_0]
0x1800533f0  mov     [rbp+arg_0], rcx
0x1800533f4  lea     r8d, [rdx+0Ah]
0x1800533f8  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x1800533fc  lea     rdx, [rbp+var_10]
0x180053400  mov     r9b, 1
0x180053403  mov     [rbp+var_8], rax
0x180053407  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x18005340c  test    eax, eax
0x18005340e  jle     short loc_180053442
0x180053410  mov     rax, [rbp+arg_0]
0x180053414  cmp     byte ptr [rax], 24h ; '$'
0x180053417  jnz     short loc_180053442
0x180053419  cmp     dword ptr [rbx+470h], 1
0x180053420  jnz     short loc_180053436
0x180053422  lea     rcx, [rbx+480h]; void *
0x180053429  xor     edx, edx; Val
0x18005342b  mov     r8d, 960h; Size
0x180053431  call    memset
0x180053436  mov     dword ptr [rbx+474h], 2
0x180053440  jmp     short loc_18005345E
0x180053442  mov     dword ptr [rbx+474h], 1
0x18005344c  mov     al, 1
0x18005344e  mov     rbx, [rsp+40h+arg_10]
0x180053453  add     rsp, 40h
0x180053457  pop     rbp
0x180053458  retn
0x180053459  cmp     edx, 2
0x18005345c  jnz     short loc_18005344C
0x18005345e  mov     rax, [rbx+10h]
0x180053462  lea     rcx, [rbp+arg_8]
0x180053466  mov     [rbp+var_8], rcx
0x18005346a  lea     rdx, [rbp+var_10]
0x18005346e  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180053472  mov     r9b, 1
0x180053475  mov     r8d, 0Ah
0x18005347b  mov     [rbp+var_10], rax
0x18005347f  mov     [rbp+arg_8], rax
0x180053483  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x180053488  cmp     dword ptr [rbx+470h], 1
0x18005348f  mov     rcx, [rbp+arg_8]
0x180053493  lea     edx, [rax-1]
0x180053496  mov     [rbx+0DE4h], edx
0x18005349c  lea     rax, [rcx+1]
0x1800534a0  mov     [rbx+10h], rax
0x1800534a4  jnz     short loc_18005344C
0x1800534a6  test    edx, edx
0x1800534a8  js      short loc_1800534C7
0x1800534aa  cmp     byte ptr [rcx], 24h ; '$'
0x1800534ad  jnz     short loc_1800534C7
0x1800534af  cmp     edx, 64h ; 'd'
0x1800534b2  jge     short loc_1800534C7
0x1800534b4  mov     ecx, [rbx+0DE0h]
0x1800534ba  cmp     edx, ecx
0x1800534bc  cmovle  edx, ecx
0x1800534bf  mov     [rbx+0DE0h], edx
0x1800534c5  jmp     short loc_18005344C
0x1800534c7  mov     rax, [rbx+8]
0x1800534cb  xor     r9d, r9d; LineNo
0x1800534ce  xor     r8d, r8d; FileName
0x1800534d1  xor     edx, edx; FunctionName
0x1800534d3  xor     ecx, ecx; Expression
0x1800534d5  mov     byte ptr [rax+30h], 1
0x1800534d9  mov     dword ptr [rax+2Ch], 16h
0x1800534e0  mov     rax, [rbx+8]
0x1800534e4  mov     [rsp+40h+var_18], rax; __crt_cached_ptd_host *
0x1800534e9  and     [rsp+40h+var_20], 0
0x1800534ef  call    _invalid_parameter_internal
0x1800534f4  xor     al, al
0x1800534f6  jmp     loc_18005344E
```
