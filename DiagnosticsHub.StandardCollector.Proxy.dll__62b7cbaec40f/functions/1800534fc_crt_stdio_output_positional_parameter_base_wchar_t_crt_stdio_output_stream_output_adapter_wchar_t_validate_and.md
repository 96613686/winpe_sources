# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::validate_and_update_state_at_beginning_of_format_character(void)

- ea: `0x1800534fc`
- end: `0x18005364c`
- name: `?validate_and_update_state_at_beginning_of_format_character@?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800452e0`

## callees

- `0x180007b48`
- `0x180038cb0`
- `0x1800534fc`
- `0x180060550`

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
0x1800534fc  mov     [rsp-8+arg_10], rbx
0x180053501  push    rbp
0x180053502  mov     rbp, rsp
0x180053505  sub     rsp, 40h
0x180053509  cmp     byte ptr [rcx+24h], 1
0x18005350d  mov     rbx, rcx
0x180053510  jnz     loc_18005359C
0x180053516  mov     rcx, [rcx+10h]
0x18005351a  movzx   eax, word ptr [rcx]
0x18005351d  cmp     ax, 25h ; '%'
0x180053521  jz      short loc_18005359C
0x180053523  mov     edx, [rbx+474h]
0x180053529  test    edx, edx
0x18005352b  jnz     short loc_1800535A9
0x18005352d  sub     ax, 30h ; '0'
0x180053531  cmp     ax, 9
0x180053535  ja      short loc_180053592
0x180053537  mov     [rbp+var_10], rcx
0x18005353b  lea     rax, [rbp+arg_0]
0x18005353f  mov     [rbp+arg_0], rcx
0x180053543  lea     r8d, [rdx+0Ah]
0x180053547  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x18005354b  lea     rdx, [rbp+var_10]
0x18005354f  mov     r9b, 1
0x180053552  mov     [rbp+var_8], rax
0x180053556  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x18005355b  test    eax, eax
0x18005355d  jle     short loc_180053592
0x18005355f  mov     rax, [rbp+arg_0]
0x180053563  cmp     word ptr [rax], 24h ; '$'
0x180053567  jnz     short loc_180053592
0x180053569  cmp     dword ptr [rbx+470h], 1
0x180053570  jnz     short loc_180053586
0x180053572  lea     rcx, [rbx+480h]; void *
0x180053579  xor     edx, edx; Val
0x18005357b  mov     r8d, 960h; Size
0x180053581  call    memset
0x180053586  mov     dword ptr [rbx+474h], 2
0x180053590  jmp     short loc_1800535AE
0x180053592  mov     dword ptr [rbx+474h], 1
0x18005359c  mov     al, 1
0x18005359e  mov     rbx, [rsp+40h+arg_10]
0x1800535a3  add     rsp, 40h
0x1800535a7  pop     rbp
0x1800535a8  retn
0x1800535a9  cmp     edx, 2
0x1800535ac  jnz     short loc_18005359C
0x1800535ae  mov     rax, [rbx+10h]
0x1800535b2  lea     rcx, [rbp+arg_8]
0x1800535b6  mov     [rbp+var_8], rcx
0x1800535ba  lea     rdx, [rbp+var_10]
0x1800535be  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x1800535c2  mov     r9b, 1
0x1800535c5  mov     r8d, 0Ah
0x1800535cb  mov     [rbp+var_10], rax
0x1800535cf  mov     [rbp+arg_8], rax
0x1800535d3  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x1800535d8  cmp     dword ptr [rbx+470h], 1
0x1800535df  mov     rcx, [rbp+arg_8]
0x1800535e3  lea     edx, [rax-1]
0x1800535e6  mov     [rbx+0DE4h], edx
0x1800535ec  lea     rax, [rcx+2]
0x1800535f0  mov     [rbx+10h], rax
0x1800535f4  jnz     short loc_18005359C
0x1800535f6  test    edx, edx
0x1800535f8  js      short loc_180053618
0x1800535fa  cmp     word ptr [rcx], 24h ; '$'
0x1800535fe  jnz     short loc_180053618
0x180053600  cmp     edx, 64h ; 'd'
0x180053603  jge     short loc_180053618
0x180053605  mov     ecx, [rbx+0DE0h]
0x18005360b  cmp     edx, ecx
0x18005360d  cmovle  edx, ecx
0x180053610  mov     [rbx+0DE0h], edx
0x180053616  jmp     short loc_18005359C
0x180053618  mov     rax, [rbx+8]
0x18005361c  xor     r9d, r9d; LineNo
0x18005361f  xor     r8d, r8d; FileName
0x180053622  xor     edx, edx; FunctionName
0x180053624  xor     ecx, ecx; Expression
0x180053626  mov     byte ptr [rax+30h], 1
0x18005362a  mov     dword ptr [rax+2Ch], 16h
0x180053631  mov     rax, [rbx+8]
0x180053635  mov     [rsp+40h+var_18], rax; __crt_cached_ptd_host *
0x18005363a  and     [rsp+40h+var_20], 0
0x180053640  call    _invalid_parameter_internal
0x180053645  xor     al, al
0x180053647  jmp     loc_18005359E
```
