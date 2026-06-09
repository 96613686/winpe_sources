# __crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>::validate_and_update_state_at_beginning_of_format_character(void)

- ea: `0x180053274`
- end: `0x1800533b7`
- name: `?validate_and_update_state_at_beginning_of_format_character@?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180043dac`

## callees

- `0x180007b48`
- `0x1800389fc`
- `0x180053274`
- `0x180060550`

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
0x180053274  mov     [rsp-8+arg_10], rbx
0x180053279  push    rbp
0x18005327a  mov     rbp, rsp
0x18005327d  sub     rsp, 40h
0x180053281  cmp     byte ptr [rcx+24h], 1
0x180053285  mov     rbx, rcx
0x180053288  jnz     short loc_180053308
0x18005328a  mov     rcx, [rcx+10h]
0x18005328e  mov     al, [rcx]
0x180053290  cmp     al, 25h ; '%'
0x180053292  jz      short loc_180053308
0x180053294  mov     edx, [rbx+474h]
0x18005329a  test    edx, edx
0x18005329c  jnz     short loc_180053315
0x18005329e  sub     al, 30h ; '0'
0x1800532a0  cmp     al, 9
0x1800532a2  ja      short loc_1800532FE
0x1800532a4  mov     [rbp+var_10], rcx
0x1800532a8  lea     rax, [rbp+arg_0]
0x1800532ac  mov     [rbp+arg_0], rcx
0x1800532b0  lea     r8d, [rdx+0Ah]
0x1800532b4  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x1800532b8  lea     rdx, [rbp+var_10]
0x1800532bc  mov     r9b, 1
0x1800532bf  mov     [rbp+var_8], rax
0x1800532c3  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x1800532c8  test    eax, eax
0x1800532ca  jle     short loc_1800532FE
0x1800532cc  mov     rax, [rbp+arg_0]
0x1800532d0  cmp     byte ptr [rax], 24h ; '$'
0x1800532d3  jnz     short loc_1800532FE
0x1800532d5  cmp     dword ptr [rbx+470h], 1
0x1800532dc  jnz     short loc_1800532F2
0x1800532de  lea     rcx, [rbx+480h]; void *
0x1800532e5  xor     edx, edx; Val
0x1800532e7  mov     r8d, 960h; Size
0x1800532ed  call    memset
0x1800532f2  mov     dword ptr [rbx+474h], 2
0x1800532fc  jmp     short loc_18005331A
0x1800532fe  mov     dword ptr [rbx+474h], 1
0x180053308  mov     al, 1
0x18005330a  mov     rbx, [rsp+40h+arg_10]
0x18005330f  add     rsp, 40h
0x180053313  pop     rbp
0x180053314  retn
0x180053315  cmp     edx, 2
0x180053318  jnz     short loc_180053308
0x18005331a  mov     rax, [rbx+10h]
0x18005331e  lea     rcx, [rbp+arg_8]
0x180053322  mov     [rbp+var_8], rcx
0x180053326  lea     rdx, [rbp+var_10]
0x18005332a  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x18005332e  mov     r9b, 1
0x180053331  mov     r8d, 0Ah
0x180053337  mov     [rbp+var_10], rax
0x18005333b  mov     [rbp+arg_8], rax
0x18005333f  call    ??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)
0x180053344  cmp     dword ptr [rbx+470h], 1
0x18005334b  mov     rcx, [rbp+arg_8]
0x18005334f  lea     edx, [rax-1]
0x180053352  mov     [rbx+0DE4h], edx
0x180053358  lea     rax, [rcx+1]
0x18005335c  mov     [rbx+10h], rax
0x180053360  jnz     short loc_180053308
0x180053362  test    edx, edx
0x180053364  js      short loc_180053383
0x180053366  cmp     byte ptr [rcx], 24h ; '$'
0x180053369  jnz     short loc_180053383
0x18005336b  cmp     edx, 64h ; 'd'
0x18005336e  jge     short loc_180053383
0x180053370  mov     ecx, [rbx+0DE0h]
0x180053376  cmp     edx, ecx
0x180053378  cmovle  edx, ecx
0x18005337b  mov     [rbx+0DE0h], edx
0x180053381  jmp     short loc_180053308
0x180053383  mov     rax, [rbx+8]
0x180053387  xor     r9d, r9d; LineNo
0x18005338a  xor     r8d, r8d; FileName
0x18005338d  xor     edx, edx; FunctionName
0x18005338f  xor     ecx, ecx; Expression
0x180053391  mov     byte ptr [rax+30h], 1
0x180053395  mov     dword ptr [rax+2Ch], 16h
0x18005339c  mov     rax, [rbx+8]
0x1800533a0  mov     [rsp+40h+var_18], rax; __crt_cached_ptd_host *
0x1800533a5  and     [rsp+40h+var_20], 0
0x1800533ab  call    _invalid_parameter_internal
0x1800533b0  xor     al, al
0x1800533b2  jmp     loc_18005330A
```
