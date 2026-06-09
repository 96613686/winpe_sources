# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::validate_and_update_state_at_beginning_of_format_character(void)

- ea: `0x180052f94`
- end: `0x1800530d7`
- name: `?validate_and_update_state_at_beginning_of_format_character@?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180043acc`

## callees

- `0x1800073e8`
- `0x18003871c`
- `0x180052f94`
- `0x180060270`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::validate_and_update_state_at_beginning_of_format_character(
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
0x180052f94  mov     [rsp-8+arg_10], rbx
0x180052f99  push    rbp
0x180052f9a  mov     rbp, rsp
0x180052f9d  sub     rsp, 40h
0x180052fa1  cmp     byte ptr [rcx+24h], 1
0x180052fa5  mov     rbx, rcx
0x180052fa8  jnz     short loc_180053028
0x180052faa  mov     rcx, [rcx+10h]
0x180052fae  mov     al, [rcx]
0x180052fb0  cmp     al, 25h ; '%'
0x180052fb2  jz      short loc_180053028
0x180052fb4  mov     edx, [rbx+474h]
0x180052fba  test    edx, edx
0x180052fbc  jnz     short loc_180053035
0x180052fbe  sub     al, 30h ; '0'
0x180052fc0  cmp     al, 9
0x180052fc2  ja      short loc_18005301E
0x180052fc4  mov     [rbp+var_10], rcx
0x180052fc8  lea     rax, [rbp+arg_0]
0x180052fcc  mov     [rbp+arg_0], rcx
0x180052fd0  lea     r8d, [rdx+0Ah]
0x180052fd4  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180052fd8  lea     rdx, [rbp+var_10]
0x180052fdc  mov     r9b, 1
0x180052fdf  mov     [rbp+var_8], rax
0x180052fe3  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x180052fe8  test    eax, eax
0x180052fea  jle     short loc_18005301E
0x180052fec  mov     rax, [rbp+arg_0]
0x180052ff0  cmp     byte ptr [rax], 24h ; '$'
0x180052ff3  jnz     short loc_18005301E
0x180052ff5  cmp     dword ptr [rbx+470h], 1
0x180052ffc  jnz     short loc_180053012
0x180052ffe  lea     rcx, [rbx+480h]; void *
0x180053005  xor     edx, edx; Val
0x180053007  mov     r8d, 960h; Size
0x18005300d  call    memset
0x180053012  mov     dword ptr [rbx+474h], 2
0x18005301c  jmp     short loc_18005303A
0x18005301e  mov     dword ptr [rbx+474h], 1
0x180053028  mov     al, 1
0x18005302a  mov     rbx, [rsp+40h+arg_10]
0x18005302f  add     rsp, 40h
0x180053033  pop     rbp
0x180053034  retn
0x180053035  cmp     edx, 2
0x180053038  jnz     short loc_180053028
0x18005303a  mov     rax, [rbx+10h]
0x18005303e  lea     rcx, [rbp+arg_8]
0x180053042  mov     [rbp+var_8], rcx
0x180053046  lea     rdx, [rbp+var_10]
0x18005304a  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x18005304e  mov     r9b, 1
0x180053051  mov     r8d, 0Ah
0x180053057  mov     [rbp+var_10], rax
0x18005305b  mov     [rbp+arg_8], rax
0x18005305f  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x180053064  cmp     dword ptr [rbx+470h], 1
0x18005306b  mov     rcx, [rbp+arg_8]
0x18005306f  lea     edx, [rax-1]
0x180053072  mov     [rbx+0DE4h], edx
0x180053078  lea     rax, [rcx+1]
0x18005307c  mov     [rbx+10h], rax
0x180053080  jnz     short loc_180053028
0x180053082  test    edx, edx
0x180053084  js      short loc_1800530A3
0x180053086  cmp     byte ptr [rcx], 24h ; '$'
0x180053089  jnz     short loc_1800530A3
0x18005308b  cmp     edx, 64h ; 'd'
0x18005308e  jge     short loc_1800530A3
0x180053090  mov     ecx, [rbx+0DE0h]
0x180053096  cmp     edx, ecx
0x180053098  cmovle  edx, ecx
0x18005309b  mov     [rbx+0DE0h], edx
0x1800530a1  jmp     short loc_180053028
0x1800530a3  mov     rax, [rbx+8]
0x1800530a7  xor     r9d, r9d; LineNo
0x1800530aa  xor     r8d, r8d; FileName
0x1800530ad  xor     edx, edx; FunctionName
0x1800530af  xor     ecx, ecx; Expression
0x1800530b1  mov     byte ptr [rax+30h], 1
0x1800530b5  mov     dword ptr [rax+2Ch], 16h
0x1800530bc  mov     rax, [rbx+8]
0x1800530c0  mov     [rsp+40h+var_18], rax; __crt_cached_ptd_host *
0x1800530c5  and     [rsp+40h+var_20], 0
0x1800530cb  call    _invalid_parameter_internal
0x1800530d0  xor     al, al
0x1800530d2  jmp     loc_18005302A
```
