# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::validate_and_update_state_at_beginning_of_format_character(void)

- ea: `0x18005321c`
- end: `0x18005336c`
- name: `?validate_and_update_state_at_beginning_of_format_character@?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180045000`

## callees

- `0x1800073e8`
- `0x1800389d0`
- `0x18005321c`
- `0x180060270`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::validate_and_update_state_at_beginning_of_format_character(
        __int64 a1)
{
  __int16 *v2; // rcx
  int v3; // edx
  __crt_cached_ptd_host *v4; // rcx
  __int16 *v6; // rax
  __crt_cached_ptd_host *v7; // rcx
  int v8; // eax
  bool v9; // zf
  __int16 *v10; // rcx
  int v11; // edx
  __int64 v12; // rax
  __int16 *v13; // [rsp+30h] [rbp-10h] BYREF
  __int16 **v14; // [rsp+38h] [rbp-8h]
  __int16 *v15; // [rsp+50h] [rbp+10h] BYREF
  __int16 *v16; // [rsp+58h] [rbp+18h] BYREF

  if ( *(_BYTE *)(a1 + 36) != 1 )
    return 1;
  v2 = *(__int16 **)(a1 + 16);
  if ( *v2 == 37 )
    return 1;
  v3 = *(_DWORD *)(a1 + 1140);
  if ( v3 )
  {
    if ( v3 == 2 )
      goto LABEL_13;
    return 1;
  }
  if ( (unsigned __int16)(*v2 - 48) > 9u
    || (v13 = v2,
        v15 = v2,
        v4 = *(__crt_cached_ptd_host **)(a1 + 8),
        v14 = &v15,
        (int)__crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<wchar_t>,0>(
               v4,
               &v13,
               0xAu,
               1) <= 0)
    || *v15 != 36 )
  {
    *(_DWORD *)(a1 + 1140) = 1;
    return 1;
  }
  if ( *(_DWORD *)(a1 + 1136) == 1 )
    memset((void *)(a1 + 1152), 0, 0x960u);
  *(_DWORD *)(a1 + 1140) = 2;
LABEL_13:
  v6 = *(__int16 **)(a1 + 16);
  v14 = &v16;
  v7 = *(__crt_cached_ptd_host **)(a1 + 8);
  v13 = v6;
  v16 = v6;
  v8 = __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<wchar_t>,0>(v7, &v13, 0xAu, 1);
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
0x18005321c  mov     [rsp-8+arg_10], rbx
0x180053221  push    rbp
0x180053222  mov     rbp, rsp
0x180053225  sub     rsp, 40h
0x180053229  cmp     byte ptr [rcx+24h], 1
0x18005322d  mov     rbx, rcx
0x180053230  jnz     loc_1800532BC
0x180053236  mov     rcx, [rcx+10h]
0x18005323a  movzx   eax, word ptr [rcx]
0x18005323d  cmp     ax, 25h ; '%'
0x180053241  jz      short loc_1800532BC
0x180053243  mov     edx, [rbx+474h]
0x180053249  test    edx, edx
0x18005324b  jnz     short loc_1800532C9
0x18005324d  sub     ax, 30h ; '0'
0x180053251  cmp     ax, 9
0x180053255  ja      short loc_1800532B2
0x180053257  mov     [rbp+var_10], rcx
0x18005325b  lea     rax, [rbp+arg_0]
0x18005325f  mov     [rbp+arg_0], rcx
0x180053263  lea     r8d, [rdx+0Ah]
0x180053267  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x18005326b  lea     rdx, [rbp+var_10]
0x18005326f  mov     r9b, 1
0x180053272  mov     [rbp+var_8], rax
0x180053276  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x18005327b  test    eax, eax
0x18005327d  jle     short loc_1800532B2
0x18005327f  mov     rax, [rbp+arg_0]
0x180053283  cmp     word ptr [rax], 24h ; '$'
0x180053287  jnz     short loc_1800532B2
0x180053289  cmp     dword ptr [rbx+470h], 1
0x180053290  jnz     short loc_1800532A6
0x180053292  lea     rcx, [rbx+480h]; void *
0x180053299  xor     edx, edx; Val
0x18005329b  mov     r8d, 960h; Size
0x1800532a1  call    memset
0x1800532a6  mov     dword ptr [rbx+474h], 2
0x1800532b0  jmp     short loc_1800532CE
0x1800532b2  mov     dword ptr [rbx+474h], 1
0x1800532bc  mov     al, 1
0x1800532be  mov     rbx, [rsp+40h+arg_10]
0x1800532c3  add     rsp, 40h
0x1800532c7  pop     rbp
0x1800532c8  retn
0x1800532c9  cmp     edx, 2
0x1800532cc  jnz     short loc_1800532BC
0x1800532ce  mov     rax, [rbx+10h]
0x1800532d2  lea     rcx, [rbp+arg_8]
0x1800532d6  mov     [rbp+var_8], rcx
0x1800532da  lea     rdx, [rbp+var_10]
0x1800532de  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x1800532e2  mov     r9b, 1
0x1800532e5  mov     r8d, 0Ah
0x1800532eb  mov     [rbp+var_10], rax
0x1800532ef  mov     [rbp+arg_8], rax
0x1800532f3  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x1800532f8  cmp     dword ptr [rbx+470h], 1
0x1800532ff  mov     rcx, [rbp+arg_8]
0x180053303  lea     edx, [rax-1]
0x180053306  mov     [rbx+0DE4h], edx
0x18005330c  lea     rax, [rcx+2]
0x180053310  mov     [rbx+10h], rax
0x180053314  jnz     short loc_1800532BC
0x180053316  test    edx, edx
0x180053318  js      short loc_180053338
0x18005331a  cmp     word ptr [rcx], 24h ; '$'
0x18005331e  jnz     short loc_180053338
0x180053320  cmp     edx, 64h ; 'd'
0x180053323  jge     short loc_180053338
0x180053325  mov     ecx, [rbx+0DE0h]
0x18005332b  cmp     edx, ecx
0x18005332d  cmovle  edx, ecx
0x180053330  mov     [rbx+0DE0h], edx
0x180053336  jmp     short loc_1800532BC
0x180053338  mov     rax, [rbx+8]
0x18005333c  xor     r9d, r9d; LineNo
0x18005333f  xor     r8d, r8d; FileName
0x180053342  xor     edx, edx; FunctionName
0x180053344  xor     ecx, ecx; Expression
0x180053346  mov     byte ptr [rax+30h], 1
0x18005334a  mov     dword ptr [rax+2Ch], 16h
0x180053351  mov     rax, [rbx+8]
0x180053355  mov     [rsp+40h+var_18], rax; __crt_cached_ptd_host *
0x18005335a  and     [rsp+40h+var_20], 0
0x180053360  call    _invalid_parameter_internal
0x180053365  xor     al, al
0x180053367  jmp     loc_1800532BE
```
