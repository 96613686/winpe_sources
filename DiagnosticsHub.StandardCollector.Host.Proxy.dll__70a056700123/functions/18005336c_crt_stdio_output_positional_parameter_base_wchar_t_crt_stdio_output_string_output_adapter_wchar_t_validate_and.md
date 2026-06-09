# __crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>::validate_and_update_state_at_beginning_of_format_character(void)

- ea: `0x18005336c`
- end: `0x1800534bc`
- name: `?validate_and_update_state_at_beginning_of_format_character@?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEAA_NXZ`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800458dc`

## callees

- `0x1800073e8`
- `0x1800389d0`
- `0x18005336c`
- `0x180060270`

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
0x18005336c  mov     [rsp-8+arg_10], rbx
0x180053371  push    rbp
0x180053372  mov     rbp, rsp
0x180053375  sub     rsp, 40h
0x180053379  cmp     byte ptr [rcx+24h], 1
0x18005337d  mov     rbx, rcx
0x180053380  jnz     loc_18005340C
0x180053386  mov     rcx, [rcx+10h]
0x18005338a  movzx   eax, word ptr [rcx]
0x18005338d  cmp     ax, 25h ; '%'
0x180053391  jz      short loc_18005340C
0x180053393  mov     edx, [rbx+474h]
0x180053399  test    edx, edx
0x18005339b  jnz     short loc_180053419
0x18005339d  sub     ax, 30h ; '0'
0x1800533a1  cmp     ax, 9
0x1800533a5  ja      short loc_180053402
0x1800533a7  mov     [rbp+var_10], rcx
0x1800533ab  lea     rax, [rbp+arg_0]
0x1800533af  mov     [rbp+arg_0], rcx
0x1800533b3  lea     r8d, [rdx+0Ah]
0x1800533b7  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x1800533bb  lea     rdx, [rbp+var_10]
0x1800533bf  mov     r9b, 1
0x1800533c2  mov     [rbp+var_8], rax
0x1800533c6  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x1800533cb  test    eax, eax
0x1800533cd  jle     short loc_180053402
0x1800533cf  mov     rax, [rbp+arg_0]
0x1800533d3  cmp     word ptr [rax], 24h ; '$'
0x1800533d7  jnz     short loc_180053402
0x1800533d9  cmp     dword ptr [rbx+470h], 1
0x1800533e0  jnz     short loc_1800533F6
0x1800533e2  lea     rcx, [rbx+480h]; void *
0x1800533e9  xor     edx, edx; Val
0x1800533eb  mov     r8d, 960h; Size
0x1800533f1  call    memset
0x1800533f6  mov     dword ptr [rbx+474h], 2
0x180053400  jmp     short loc_18005341E
0x180053402  mov     dword ptr [rbx+474h], 1
0x18005340c  mov     al, 1
0x18005340e  mov     rbx, [rsp+40h+arg_10]
0x180053413  add     rsp, 40h
0x180053417  pop     rbp
0x180053418  retn
0x180053419  cmp     edx, 2
0x18005341c  jnz     short loc_18005340C
0x18005341e  mov     rax, [rbx+10h]
0x180053422  lea     rcx, [rbp+arg_8]
0x180053426  mov     [rbp+var_8], rcx
0x18005342a  lea     rdx, [rbp+var_10]
0x18005342e  mov     rcx, [rbx+8]; __crt_cached_ptd_host *
0x180053432  mov     r9b, 1
0x180053435  mov     r8d, 0Ah
0x18005343b  mov     [rbp+var_10], rax
0x18005343f  mov     [rbp+arg_8], rax
0x180053443  call    ??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z; __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)
0x180053448  cmp     dword ptr [rbx+470h], 1
0x18005344f  mov     rcx, [rbp+arg_8]
0x180053453  lea     edx, [rax-1]
0x180053456  mov     [rbx+0DE4h], edx
0x18005345c  lea     rax, [rcx+2]
0x180053460  mov     [rbx+10h], rax
0x180053464  jnz     short loc_18005340C
0x180053466  test    edx, edx
0x180053468  js      short loc_180053488
0x18005346a  cmp     word ptr [rcx], 24h ; '$'
0x18005346e  jnz     short loc_180053488
0x180053470  cmp     edx, 64h ; 'd'
0x180053473  jge     short loc_180053488
0x180053475  mov     ecx, [rbx+0DE0h]
0x18005347b  cmp     edx, ecx
0x18005347d  cmovle  edx, ecx
0x180053480  mov     [rbx+0DE0h], edx
0x180053486  jmp     short loc_18005340C
0x180053488  mov     rax, [rbx+8]
0x18005348c  xor     r9d, r9d; LineNo
0x18005348f  xor     r8d, r8d; FileName
0x180053492  xor     edx, edx; FunctionName
0x180053494  xor     ecx, ecx; Expression
0x180053496  mov     byte ptr [rax+30h], 1
0x18005349a  mov     dword ptr [rax+2Ch], 16h
0x1800534a1  mov     rax, [rbx+8]
0x1800534a5  mov     [rsp+40h+var_18], rax; __crt_cached_ptd_host *
0x1800534aa  and     [rsp+40h+var_20], 0
0x1800534b0  call    _invalid_parameter_internal
0x1800534b5  xor     al, al
0x1800534b7  jmp     loc_18005340E
```
