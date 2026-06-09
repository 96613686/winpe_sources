# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>::validate_and_update_state_at_beginning_of_format_character(void)

- ea: `0x1800530d8`
- end: `0x18005321b`
- name: `?validate_and_update_state_at_beginning_of_format_character@?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800445d0`

## callees

- `0x1800073e8`
- `0x18003871c`
- `0x1800530d8`
- `0x180060270`

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
0x1800530d8  mov     [rsp-8+arg_10], rbx
0x1800530dd  push    rbp
0x1800530de  mov     rbp, rsp
0x1800530e1  sub     rsp, 40h
0x1800530e5  cmp     byte ptr [rcx+24h], 1
0x1800530e9  mov     rbx, rcx
0x1800530ec  jnz     short loc_18005316C
0x1800530ee  mov     rcx, [rcx+10h]
0x1800530f2  mov     al, [rcx]
0x1800530f4  cmp     al, 25h ; '%'
0x1800530f6  jz      short loc_18005316C
0x1800530f8  mov     edx, [rbx+474h]
0x1800530fe  test    edx, edx
0x180053100  jnz     short loc_180053179
0x180053102  sub     al, 30h ; '0'
0x180053104  cmp     al, 9
0x180053106  ja      short loc_180053162
0x180053108  mov     [rbp+var_10], rcx
0x18005310c  lea     rax, [rbp+arg_0]
0x180053110  mov     [rbp+arg_0], rcx
0x180053114  lea     r8d, [rdx+0Ah]
0x180053118  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x18005311c  lea     rdx, [rbp+var_10]
0x180053120  mov     r9b, 1
0x180053123  mov     [rbp+var_8], rax
0x180053127  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x18005312c  test    eax, eax
0x18005312e  jle     short loc_180053162
0x180053130  mov     rax, [rbp+arg_0]
0x180053134  cmp     byte ptr [rax], 24h ; '$'
0x180053137  jnz     short loc_180053162
0x180053139  cmp     dword ptr [rbx+470h], 1
0x180053140  jnz     short loc_180053156
0x180053142  lea     rcx, [rbx+480h]; void *
0x180053149  xor     edx, edx; Val
0x18005314b  mov     r8d, 960h; Size
0x180053151  call    memset
0x180053156  mov     dword ptr [rbx+474h], 2
0x180053160  jmp     short loc_18005317E
0x180053162  mov     dword ptr [rbx+474h], 1
0x18005316c  mov     al, 1
0x18005316e  mov     rbx, [rsp+40h+arg_10]
0x180053173  add     rsp, 40h
0x180053177  pop     rbp
0x180053178  retn
0x180053179  cmp     edx, 2
0x18005317c  jnz     short loc_18005316C
0x18005317e  mov     rax, [rbx+10h]
0x180053182  lea     rcx, [rbp+arg_8]
0x180053186  mov     [rbp+var_8], rcx
0x18005318a  lea     rdx, [rbp+var_10]
0x18005318e  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180053192  mov     r9b, 1
0x180053195  mov     r8d, 0Ah
0x18005319b  mov     [rbp+var_10], rax
0x18005319f  mov     [rbp+arg_8], rax
0x1800531a3  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x1800531a8  cmp     dword ptr [rbx+470h], 1
0x1800531af  mov     rcx, [rbp+arg_8]
0x1800531b3  lea     edx, [rax-1]
0x1800531b6  mov     [rbx+0DE4h], edx
0x1800531bc  lea     rax, [rcx+1]
0x1800531c0  mov     [rbx+10h], rax
0x1800531c4  jnz     short loc_18005316C
0x1800531c6  test    edx, edx
0x1800531c8  js      short loc_1800531E7
0x1800531ca  cmp     byte ptr [rcx], 24h ; '$'
0x1800531cd  jnz     short loc_1800531E7
0x1800531cf  cmp     edx, 64h ; 'd'
0x1800531d2  jge     short loc_1800531E7
0x1800531d4  mov     ecx, [rbx+0DE0h]
0x1800531da  cmp     edx, ecx
0x1800531dc  cmovle  edx, ecx
0x1800531df  mov     [rbx+0DE0h], edx
0x1800531e5  jmp     short loc_18005316C
0x1800531e7  mov     rax, [rbx+8]
0x1800531eb  xor     r9d, r9d; LineNo
0x1800531ee  xor     r8d, r8d; FileName
0x1800531f1  xor     edx, edx; FunctionName
0x1800531f3  xor     ecx, ecx; Expression
0x1800531f5  mov     byte ptr [rax+30h], 1
0x1800531f9  mov     dword ptr [rax+2Ch], 16h
0x180053200  mov     rax, [rbx+8]
0x180053204  mov     [rsp+40h+var_18], rax; __crt_cached_ptd_host *
0x180053209  and     [rsp+40h+var_20], 0
0x18005320f  call    _invalid_parameter_internal
0x180053214  xor     al, al
0x180053216  jmp     loc_18005316E
```
