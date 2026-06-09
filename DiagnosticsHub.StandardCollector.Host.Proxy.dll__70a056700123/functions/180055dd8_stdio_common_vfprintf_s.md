# __stdio_common_vfprintf_s

- ea: `0x180055dd8`
- end: `0x180055efc`
- name: `__stdio_common_vfprintf_s`
- size: `292`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x180033298`
- `0x180055dd8`

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
0x180055dd8  push    rbp
0x180055dda  push    rbx
0x180055ddb  push    rdi
0x180055ddc  lea     rbp, [rsp-3Fh]
0x180055de1  sub     rsp, 0B0h
0x180055de8  and     [rbp+4Fh+var_90], 0
0x180055ded  mov     [rbp+4Fh+var_80], 0
0x180055df1  mov     [rbp+4Fh+var_68], 0
0x180055df5  mov     [rbp+4Fh+var_60], 0
0x180055df9  mov     [rbp+4Fh+var_58], 0
0x180055dfd  test    r9, r9
0x180055e00  jz      short loc_180055E08
0x180055e02  movups  xmm0, xmmword ptr [r9]
0x180055e06  jmp     short loc_180055E18
0x180055e08  cmp     cs:__acrt_locale_changed_data, 0
0x180055e0f  jnz     short loc_180055E21
0x180055e11  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180055e18  mov     [rbp+4Fh+var_68], 1
0x180055e1c  movdqu  [rbp+4Fh+var_78], xmm0
0x180055e21  mov     rax, [rbp+4Fh+ArgList]
0x180055e25  mov     [rbp+4Fh+arg_18], rax
0x180055e29  mov     [rbp+4Fh+arg_10], r8
0x180055e2d  mov     [rbp+4Fh+arg_0], rdx
0x180055e31  mov     [rbp+4Fh+arg_8], rcx
0x180055e35  test    rdx, rdx
0x180055e38  jnz     short loc_180055E68
0x180055e3a  lea     rax, [rbp+4Fh+var_90]
0x180055e3e  mov     [rbp+4Fh+var_60], 1
0x180055e42  mov     [rsp+0C0h+var_98], rax; __crt_cached_ptd_host *
0x180055e47  xor     r9d, r9d; LineNo
0x180055e4a  and     [rsp+0C0h+var_A0], 0
0x180055e50  xor     r8d, r8d; FileName
0x180055e53  xor     edx, edx; FunctionName
0x180055e55  mov     [rbp+4Fh+var_64], 16h
0x180055e5c  xor     ecx, ecx; Expression
0x180055e5e  call    _invalid_parameter_internal
0x180055e63  or      edi, 0FFFFFFFFh
0x180055e66  jmp     short loc_180055EB4
0x180055e68  test    r8, r8
0x180055e6b  jz      short loc_180055E3A
0x180055e6d  lea     rax, [rbp+4Fh+arg_0]
0x180055e71  mov     [rbp+4Fh+var_50], rdx
0x180055e75  mov     [rbp+4Fh+var_40], rax
0x180055e79  lea     r9, [rbp+4Fh+var_50]
0x180055e7d  lea     rax, [rbp+4Fh+var_90]
0x180055e81  mov     [rbp+4Fh+var_48], rdx
0x180055e85  mov     [rbp+4Fh+var_38], rax
0x180055e89  lea     r8, [rbp+4Fh+var_40]
0x180055e8d  lea     rax, [rbp+4Fh+arg_8]
0x180055e91  mov     [rbp+4Fh+var_30], rax
0x180055e95  lea     rdx, [rbp+4Fh+var_48]
0x180055e99  lea     rax, [rbp+4Fh+arg_10]
0x180055e9d  mov     [rbp+4Fh+var_28], rax
0x180055ea1  lea     rcx, [rbp+4Fh+ArgList]
0x180055ea5  lea     rax, [rbp+4Fh+arg_18]
0x180055ea9  mov     [rbp+4Fh+var_20], rax
0x180055ead  call    __crt_seh_guarded_call_int___operator____lambda_8e8668af99809de511100fe94da1a6bd___lambda_5ea5c948f63ef1db566fd27aadf3ca11_____lambda_ab2921ee12094a5a5396e2d3d37ffb58___
0x180055eb2  mov     edi, eax
0x180055eb4  cmp     [rbp+4Fh+var_68], 2
0x180055eb8  jnz     short loc_180055EC5
0x180055eba  mov     rcx, [rbp+4Fh+var_90]
0x180055ebe  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x180055ec5  cmp     [rbp+4Fh+var_60], 0
0x180055ec9  jz      short loc_180055EDA
0x180055ecb  mov     ebx, [rbp+4Fh+var_64]
0x180055ece  lea     rcx, [rbp+4Fh+var_90]; this
0x180055ed2  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180055ed7  mov     [rax+20h], ebx
0x180055eda  cmp     [rbp+4Fh+var_58], 0
0x180055ede  jz      short loc_180055EEF
0x180055ee0  mov     ebx, [rbp+4Fh+var_5C]
0x180055ee3  lea     rcx, [rbp+4Fh+var_90]; this
0x180055ee7  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180055eec  mov     [rax+24h], ebx
0x180055eef  mov     eax, edi
0x180055ef1  add     rsp, 0B0h
0x180055ef8  pop     rdi
0x180055ef9  pop     rbx
0x180055efa  pop     rbp
0x180055efb  retn
```
