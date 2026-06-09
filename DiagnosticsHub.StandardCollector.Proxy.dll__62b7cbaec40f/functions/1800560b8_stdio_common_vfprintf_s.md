# __stdio_common_vfprintf_s

- ea: `0x1800560b8`
- end: `0x1800561dc`
- name: `__stdio_common_vfprintf_s`
- size: `292`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000774c`
- `0x180007b48`
- `0x180033578`
- `0x1800560b8`

## pseudocode

```c
int __cdecl _stdio_common_vfprintf_s(
        unsigned __int64 Options,
        FILE *Stream,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  __crt_locale_pointers v5; // xmm0
  int v6; // edi
  int v7; // ebx
  int v8; // ebx
  _QWORD v10[2]; // [rsp+30h] [rbp-41h] BYREF
  char v11; // [rsp+40h] [rbp-31h]
  __crt_locale_pointers v12; // [rsp+48h] [rbp-29h]
  char v13; // [rsp+58h] [rbp-19h]
  int v14; // [rsp+5Ch] [rbp-15h]
  char v15; // [rsp+60h] [rbp-11h]
  int v16; // [rsp+64h] [rbp-Dh]
  char v17; // [rsp+68h] [rbp-9h]
  FILE *v18; // [rsp+70h] [rbp-1h] BYREF
  FILE *v19; // [rsp+78h] [rbp+7h] BYREF
  _QWORD v20[8]; // [rsp+80h] [rbp+Fh] BYREF
  FILE *v21; // [rsp+D0h] [rbp+5Fh] BYREF
  unsigned __int64 v22; // [rsp+D8h] [rbp+67h] BYREF
  const char *v23; // [rsp+E0h] [rbp+6Fh] BYREF
  va_list v24; // [rsp+E8h] [rbp+77h] BYREF

  v10[0] = 0;
  v11 = 0;
  v13 = 0;
  v15 = 0;
  v17 = 0;
  if ( Locale )
  {
    v5 = *Locale;
LABEL_5:
    v13 = 1;
    v12 = v5;
    goto LABEL_6;
  }
  if ( !_acrt_locale_changed_data )
  {
    v5 = *(__crt_locale_pointers *)&_acrt_initial_locale_pointers;
    goto LABEL_5;
  }
LABEL_6:
  v24 = ArgList;
  v23 = Format;
  v21 = Stream;
  v22 = Options;
  if ( Stream && Format )
  {
    v18 = Stream;
    v20[0] = &v21;
    v19 = Stream;
    v20[1] = v10;
    v20[2] = &v22;
    v20[3] = &v23;
    v20[4] = &v24;
    v6 = _crt_seh_guarded_call_int_::operator()__lambda_8e8668af99809de511100fe94da1a6bd___lambda_5ea5c948f63ef1db566fd27aadf3ca11_____lambda_ab2921ee12094a5a5396e2d3d37ffb58___(
           &ArgList,
           &v19,
           v20,
           &v18);
  }
  else
  {
    v15 = 1;
    v14 = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v10);
    v6 = -1;
  }
  if ( v13 == 2 )
    *(_DWORD *)(v10[0] + 936LL) &= ~2u;
  if ( v15 )
  {
    v7 = v14;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v10) + 8) = v7;
  }
  if ( v17 )
  {
    v8 = v16;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v10) + 9) = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x1800560b8  push    rbp
0x1800560ba  push    rbx
0x1800560bb  push    rdi
0x1800560bc  lea     rbp, [rsp-3Fh]
0x1800560c1  sub     rsp, 0B0h
0x1800560c8  and     [rbp+4Fh+var_90], 0
0x1800560cd  mov     [rbp+4Fh+var_80], 0
0x1800560d1  mov     [rbp+4Fh+var_68], 0
0x1800560d5  mov     [rbp+4Fh+var_60], 0
0x1800560d9  mov     [rbp+4Fh+var_58], 0
0x1800560dd  test    r9, r9
0x1800560e0  jz      short loc_1800560E8
0x1800560e2  movups  xmm0, xmmword ptr [r9]
0x1800560e6  jmp     short loc_1800560F8
0x1800560e8  cmp     cs:__acrt_locale_changed_data, 0
0x1800560ef  jnz     short loc_180056101
0x1800560f1  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x1800560f8  mov     [rbp+4Fh+var_68], 1
0x1800560fc  movdqu  [rbp+4Fh+var_78], xmm0
0x180056101  mov     rax, [rbp+4Fh+ArgList]
0x180056105  mov     [rbp+4Fh+arg_18], rax
0x180056109  mov     [rbp+4Fh+arg_10], r8
0x18005610d  mov     [rbp+4Fh+arg_0], rdx
0x180056111  mov     [rbp+4Fh+arg_8], rcx
0x180056115  test    rdx, rdx
0x180056118  jnz     short loc_180056148
0x18005611a  lea     rax, [rbp+4Fh+var_90]
0x18005611e  mov     [rbp+4Fh+var_60], 1
0x180056122  mov     [rsp+0C0h+var_98], rax; __crt_cached_ptd_host *
0x180056127  xor     r9d, r9d; LineNo
0x18005612a  and     [rsp+0C0h+var_A0], 0
0x180056130  xor     r8d, r8d; FileName
0x180056133  xor     edx, edx; FunctionName
0x180056135  mov     [rbp+4Fh+var_64], 16h
0x18005613c  xor     ecx, ecx; Expression
0x18005613e  call    _invalid_parameter_internal
0x180056143  or      edi, 0FFFFFFFFh
0x180056146  jmp     short loc_180056194
0x180056148  test    r8, r8
0x18005614b  jz      short loc_18005611A
0x18005614d  lea     rax, [rbp+4Fh+arg_0]
0x180056151  mov     [rbp+4Fh+var_50], rdx
0x180056155  mov     [rbp+4Fh+var_40], rax
0x180056159  lea     r9, [rbp+4Fh+var_50]
0x18005615d  lea     rax, [rbp+4Fh+var_90]
0x180056161  mov     [rbp+4Fh+var_48], rdx
0x180056165  mov     [rbp+4Fh+var_38], rax
0x180056169  lea     r8, [rbp+4Fh+var_40]
0x18005616d  lea     rax, [rbp+4Fh+arg_8]
0x180056171  mov     [rbp+4Fh+var_30], rax
0x180056175  lea     rdx, [rbp+4Fh+var_48]
0x180056179  lea     rax, [rbp+4Fh+arg_10]
0x18005617d  mov     [rbp+4Fh+var_28], rax
0x180056181  lea     rcx, [rbp+4Fh+ArgList]
0x180056185  lea     rax, [rbp+4Fh+arg_18]
0x180056189  mov     [rbp+4Fh+var_20], rax
0x18005618d  call    __crt_seh_guarded_call_int___operator____lambda_8e8668af99809de511100fe94da1a6bd___lambda_5ea5c948f63ef1db566fd27aadf3ca11_____lambda_ab2921ee12094a5a5396e2d3d37ffb58___
0x180056192  mov     edi, eax
0x180056194  cmp     [rbp+4Fh+var_68], 2
0x180056198  jnz     short loc_1800561A5
0x18005619a  mov     rcx, [rbp+4Fh+var_90]
0x18005619e  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x1800561a5  cmp     [rbp+4Fh+var_60], 0
0x1800561a9  jz      short loc_1800561BA
0x1800561ab  mov     ebx, [rbp+4Fh+var_64]
0x1800561ae  lea     rcx, [rbp+4Fh+var_90]; this
0x1800561b2  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800561b7  mov     [rax+20h], ebx
0x1800561ba  cmp     [rbp+4Fh+var_58], 0
0x1800561be  jz      short loc_1800561CF
0x1800561c0  mov     ebx, [rbp+4Fh+var_5C]
0x1800561c3  lea     rcx, [rbp+4Fh+var_90]; this
0x1800561c7  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800561cc  mov     [rax+24h], ebx
0x1800561cf  mov     eax, edi
0x1800561d1  add     rsp, 0B0h
0x1800561d8  pop     rdi
0x1800561d9  pop     rbx
0x1800561da  pop     rbp
0x1800561db  retn
```
