# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::validate_and_update_state_at_beginning_of_format_character(void)

- ea: `0x18005364c`
- end: `0x18005379c`
- name: `?validate_and_update_state_at_beginning_of_format_character@?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180045bbc`

## callees

- `0x180007b48`
- `0x180038cb0`
- `0x18005364c`
- `0x180060550`

## pseudocode

```c
char __fastcall __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::validate_and_update_state_at_beginning_of_format_character(
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
0x18005364c  mov     [rsp-8+arg_10], rbx
0x180053651  push    rbp
0x180053652  mov     rbp, rsp
0x180053655  sub     rsp, 40h
0x180053659  cmp     byte ptr [rcx+24h], 1
0x18005365d  mov     rbx, rcx
0x180053660  jnz     loc_1800536EC
0x180053666  mov     rcx, [rcx+10h]
0x18005366a  movzx   eax, word ptr [rcx]
0x18005366d  cmp     ax, 25h ; '%'
0x180053671  jz      short loc_1800536EC
0x180053673  mov     edx, [rbx+474h]
0x180053679  test    edx, edx
0x18005367b  jnz     short loc_1800536F9
0x18005367d  sub     ax, 30h ; '0'
0x180053681  cmp     ax, 9
0x180053685  ja      short loc_1800536E2
0x180053687  mov     [rbp+var_10], rcx
0x18005368b  lea     rax, [rbp+arg_0]
0x18005368f  mov     [rbp+arg_0], rcx
0x180053693  lea     r8d, [rdx+0Ah]
0x180053697  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x18005369b  lea     rdx, [rbp+var_10]
0x18005369f  mov     r9b, 1
0x1800536a2  mov     [rbp+var_8], rax
0x1800536a6  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x1800536ab  test    eax, eax
0x1800536ad  jle     short loc_1800536E2
0x1800536af  mov     rax, [rbp+arg_0]
0x1800536b3  cmp     word ptr [rax], 24h ; '$'
0x1800536b7  jnz     short loc_1800536E2
0x1800536b9  cmp     dword ptr [rbx+470h], 1
0x1800536c0  jnz     short loc_1800536D6
0x1800536c2  lea     rcx, [rbx+480h]; void *
0x1800536c9  xor     edx, edx; Val
0x1800536cb  mov     r8d, 960h; Size
0x1800536d1  call    memset
0x1800536d6  mov     dword ptr [rbx+474h], 2
0x1800536e0  jmp     short loc_1800536FE
0x1800536e2  mov     dword ptr [rbx+474h], 1
0x1800536ec  mov     al, 1
0x1800536ee  mov     rbx, [rsp+40h+arg_10]
0x1800536f3  add     rsp, 40h
0x1800536f7  pop     rbp
0x1800536f8  retn
0x1800536f9  cmp     edx, 2
0x1800536fc  jnz     short loc_1800536EC
0x1800536fe  mov     rax, [rbx+10h]
0x180053702  lea     rcx, [rbp+arg_8]
0x180053706  mov     [rbp+var_8], rcx
0x18005370a  lea     rdx, [rbp+var_10]
0x18005370e  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180053712  mov     r9b, 1
0x180053715  mov     r8d, 0Ah
0x18005371b  mov     [rbp+var_10], rax
0x18005371f  mov     [rbp+arg_8], rax
0x180053723  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x180053728  cmp     dword ptr [rbx+470h], 1
0x18005372f  mov     rcx, [rbp+arg_8]
0x180053733  lea     edx, [rax-1]
0x180053736  mov     [rbx+0DE4h], edx
0x18005373c  lea     rax, [rcx+2]
0x180053740  mov     [rbx+10h], rax
0x180053744  jnz     short loc_1800536EC
0x180053746  test    edx, edx
0x180053748  js      short loc_180053768
0x18005374a  cmp     word ptr [rcx], 24h ; '$'
0x18005374e  jnz     short loc_180053768
0x180053750  cmp     edx, 64h ; 'd'
0x180053753  jge     short loc_180053768
0x180053755  mov     ecx, [rbx+0DE0h]
0x18005375b  cmp     edx, ecx
0x18005375d  cmovle  edx, ecx
0x180053760  mov     [rbx+0DE0h], edx
0x180053766  jmp     short loc_1800536EC
0x180053768  mov     rax, [rbx+8]
0x18005376c  xor     r9d, r9d; LineNo
0x18005376f  xor     r8d, r8d; FileName
0x180053772  xor     edx, edx; FunctionName
0x180053774  xor     ecx, ecx; Expression
0x180053776  mov     byte ptr [rax+30h], 1
0x18005377a  mov     dword ptr [rax+2Ch], 16h
0x180053781  mov     rax, [rbx+8]
0x180053785  mov     [rsp+40h+var_18], rax; __crt_cached_ptd_host *
0x18005378a  and     [rsp+40h+var_20], 0
0x180053790  call    _invalid_parameter_internal
0x180053795  xor     al, al
0x180053797  jmp     loc_1800536EE
```
