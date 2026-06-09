# __stdio_common_vfwprintf_s

- ea: `0x180056144`
- end: `0x180056268`
- name: `__stdio_common_vfwprintf_s`
- size: `292`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x180033258`
- `0x180056144`

## pseudocode

```c
int __cdecl _stdio_common_vfwprintf_s(
        unsigned __int64 Options,
        FILE *Stream,
        const wchar_t *Format,
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
  const wchar_t *v23; // [rsp+E0h] [rbp+6Fh] BYREF
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
    v6 = _crt_seh_guarded_call_int_::operator()__lambda_740b16f11d3f1d0e3539b6f82067f039___lambda_12129ca491078c9e25e3e1c40c47083e_____lambda_726acf3f6ef76bdfe9ce222780860567___(
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
0x180056144  push    rbp
0x180056146  push    rbx
0x180056147  push    rdi
0x180056148  lea     rbp, [rsp-3Fh]
0x18005614d  sub     rsp, 0B0h
0x180056154  and     [rbp+4Fh+var_90], 0
0x180056159  mov     [rbp+4Fh+var_80], 0
0x18005615d  mov     [rbp+4Fh+var_68], 0
0x180056161  mov     [rbp+4Fh+var_60], 0
0x180056165  mov     [rbp+4Fh+var_58], 0
0x180056169  test    r9, r9
0x18005616c  jz      short loc_180056174
0x18005616e  movups  xmm0, xmmword ptr [r9]
0x180056172  jmp     short loc_180056184
0x180056174  cmp     cs:__acrt_locale_changed_data, 0
0x18005617b  jnz     short loc_18005618D
0x18005617d  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180056184  mov     [rbp+4Fh+var_68], 1
0x180056188  movdqu  [rbp+4Fh+var_78], xmm0
0x18005618d  mov     rax, [rbp+4Fh+ArgList]
0x180056191  mov     [rbp+4Fh+arg_18], rax
0x180056195  mov     [rbp+4Fh+arg_10], r8
0x180056199  mov     [rbp+4Fh+arg_0], rdx
0x18005619d  mov     [rbp+4Fh+arg_8], rcx
0x1800561a1  test    rdx, rdx
0x1800561a4  jnz     short loc_1800561D4
0x1800561a6  lea     rax, [rbp+4Fh+var_90]
0x1800561aa  mov     [rbp+4Fh+var_60], 1
0x1800561ae  mov     [rsp+0C0h+var_98], rax; __crt_cached_ptd_host *
0x1800561b3  xor     r9d, r9d; LineNo
0x1800561b6  and     [rsp+0C0h+var_A0], 0
0x1800561bc  xor     r8d, r8d; FileName
0x1800561bf  xor     edx, edx; FunctionName
0x1800561c1  mov     [rbp+4Fh+var_64], 16h
0x1800561c8  xor     ecx, ecx; Expression
0x1800561ca  call    _invalid_parameter_internal
0x1800561cf  or      edi, 0FFFFFFFFh
0x1800561d2  jmp     short loc_180056220
0x1800561d4  test    r8, r8
0x1800561d7  jz      short loc_1800561A6
0x1800561d9  lea     rax, [rbp+4Fh+arg_0]
0x1800561dd  mov     [rbp+4Fh+var_50], rdx
0x1800561e1  mov     [rbp+4Fh+var_40], rax
0x1800561e5  lea     r9, [rbp+4Fh+var_50]
0x1800561e9  lea     rax, [rbp+4Fh+var_90]
0x1800561ed  mov     [rbp+4Fh+var_48], rdx
0x1800561f1  mov     [rbp+4Fh+var_38], rax
0x1800561f5  lea     r8, [rbp+4Fh+var_40]
0x1800561f9  lea     rax, [rbp+4Fh+arg_8]
0x1800561fd  mov     [rbp+4Fh+var_30], rax
0x180056201  lea     rdx, [rbp+4Fh+var_48]
0x180056205  lea     rax, [rbp+4Fh+arg_10]
0x180056209  mov     [rbp+4Fh+var_28], rax
0x18005620d  lea     rcx, [rbp+4Fh+ArgList]
0x180056211  lea     rax, [rbp+4Fh+arg_18]
0x180056215  mov     [rbp+4Fh+var_20], rax
0x180056219  call    __crt_seh_guarded_call_int___operator____lambda_740b16f11d3f1d0e3539b6f82067f039___lambda_12129ca491078c9e25e3e1c40c47083e_____lambda_726acf3f6ef76bdfe9ce222780860567___
0x18005621e  mov     edi, eax
0x180056220  cmp     [rbp+4Fh+var_68], 2
0x180056224  jnz     short loc_180056231
0x180056226  mov     rcx, [rbp+4Fh+var_90]
0x18005622a  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x180056231  cmp     [rbp+4Fh+var_60], 0
0x180056235  jz      short loc_180056246
0x180056237  mov     ebx, [rbp+4Fh+var_64]
0x18005623a  lea     rcx, [rbp+4Fh+var_90]; this
0x18005623e  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056243  mov     [rax+20h], ebx
0x180056246  cmp     [rbp+4Fh+var_58], 0
0x18005624a  jz      short loc_18005625B
0x18005624c  mov     ebx, [rbp+4Fh+var_5C]
0x18005624f  lea     rcx, [rbp+4Fh+var_90]; this
0x180056253  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056258  mov     [rax+24h], ebx
0x18005625b  mov     eax, edi
0x18005625d  add     rsp, 0B0h
0x180056264  pop     rdi
0x180056265  pop     rbx
0x180056266  pop     rbp
0x180056267  retn
```
