# __stdio_common_vfprintf

- ea: `0x180055e70`
- end: `0x180055f94`
- name: `__stdio_common_vfprintf`
- size: `292`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000774c`
- `0x180007b48`
- `0x1800335b8`
- `0x180055e70`

## pseudocode

```c
int __cdecl _stdio_common_vfprintf(
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
    v6 = _crt_seh_guarded_call_int_::operator()__lambda_d854c62834386a3b23916ad6dae2782d___lambda_303760bc4008a2b3ec4768a30b06a80c_____lambda_4780a7ea4f8cbd2590aec34bd14e2bbf___(
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
0x180055e70  push    rbp
0x180055e72  push    rbx
0x180055e73  push    rdi
0x180055e74  lea     rbp, [rsp-3Fh]
0x180055e79  sub     rsp, 0B0h
0x180055e80  and     [rbp+4Fh+var_90], 0
0x180055e85  mov     [rbp+4Fh+var_80], 0
0x180055e89  mov     [rbp+4Fh+var_68], 0
0x180055e8d  mov     [rbp+4Fh+var_60], 0
0x180055e91  mov     [rbp+4Fh+var_58], 0
0x180055e95  test    r9, r9
0x180055e98  jz      short loc_180055EA0
0x180055e9a  movups  xmm0, xmmword ptr [r9]
0x180055e9e  jmp     short loc_180055EB0
0x180055ea0  cmp     cs:__acrt_locale_changed_data, 0
0x180055ea7  jnz     short loc_180055EB9
0x180055ea9  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180055eb0  mov     [rbp+4Fh+var_68], 1
0x180055eb4  movdqu  [rbp+4Fh+var_78], xmm0
0x180055eb9  mov     rax, [rbp+4Fh+ArgList]
0x180055ebd  mov     [rbp+4Fh+arg_18], rax
0x180055ec1  mov     [rbp+4Fh+arg_10], r8
0x180055ec5  mov     [rbp+4Fh+arg_0], rdx
0x180055ec9  mov     [rbp+4Fh+arg_8], rcx
0x180055ecd  test    rdx, rdx
0x180055ed0  jnz     short loc_180055F00
0x180055ed2  lea     rax, [rbp+4Fh+var_90]
0x180055ed6  mov     [rbp+4Fh+var_60], 1
0x180055eda  mov     [rsp+0C0h+var_98], rax; __crt_cached_ptd_host *
0x180055edf  xor     r9d, r9d; LineNo
0x180055ee2  and     [rsp+0C0h+var_A0], 0
0x180055ee8  xor     r8d, r8d; FileName
0x180055eeb  xor     edx, edx; FunctionName
0x180055eed  mov     [rbp+4Fh+var_64], 16h
0x180055ef4  xor     ecx, ecx; Expression
0x180055ef6  call    _invalid_parameter_internal
0x180055efb  or      edi, 0FFFFFFFFh
0x180055efe  jmp     short loc_180055F4C
0x180055f00  test    r8, r8
0x180055f03  jz      short loc_180055ED2
0x180055f05  lea     rax, [rbp+4Fh+arg_0]
0x180055f09  mov     [rbp+4Fh+var_50], rdx
0x180055f0d  mov     [rbp+4Fh+var_40], rax
0x180055f11  lea     r9, [rbp+4Fh+var_50]
0x180055f15  lea     rax, [rbp+4Fh+var_90]
0x180055f19  mov     [rbp+4Fh+var_48], rdx
0x180055f1d  mov     [rbp+4Fh+var_38], rax
0x180055f21  lea     r8, [rbp+4Fh+var_40]
0x180055f25  lea     rax, [rbp+4Fh+arg_8]
0x180055f29  mov     [rbp+4Fh+var_30], rax
0x180055f2d  lea     rdx, [rbp+4Fh+var_48]
0x180055f31  lea     rax, [rbp+4Fh+arg_10]
0x180055f35  mov     [rbp+4Fh+var_28], rax
0x180055f39  lea     rcx, [rbp+4Fh+ArgList]
0x180055f3d  lea     rax, [rbp+4Fh+arg_18]
0x180055f41  mov     [rbp+4Fh+var_20], rax
0x180055f45  call    __crt_seh_guarded_call_int___operator____lambda_d854c62834386a3b23916ad6dae2782d___lambda_303760bc4008a2b3ec4768a30b06a80c_____lambda_4780a7ea4f8cbd2590aec34bd14e2bbf___
0x180055f4a  mov     edi, eax
0x180055f4c  cmp     [rbp+4Fh+var_68], 2
0x180055f50  jnz     short loc_180055F5D
0x180055f52  mov     rcx, [rbp+4Fh+var_90]
0x180055f56  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x180055f5d  cmp     [rbp+4Fh+var_60], 0
0x180055f61  jz      short loc_180055F72
0x180055f63  mov     ebx, [rbp+4Fh+var_64]
0x180055f66  lea     rcx, [rbp+4Fh+var_90]; this
0x180055f6a  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180055f6f  mov     [rax+20h], ebx
0x180055f72  cmp     [rbp+4Fh+var_58], 0
0x180055f76  jz      short loc_180055F87
0x180055f78  mov     ebx, [rbp+4Fh+var_5C]
0x180055f7b  lea     rcx, [rbp+4Fh+var_90]; this
0x180055f7f  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180055f84  mov     [rax+24h], ebx
0x180055f87  mov     eax, edi
0x180055f89  add     rsp, 0B0h
0x180055f90  pop     rdi
0x180055f91  pop     rbx
0x180055f92  pop     rbp
0x180055f93  retn
```
