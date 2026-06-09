# __stdio_common_vfprintf

- ea: `0x180055b90`
- end: `0x180055cb4`
- name: `__stdio_common_vfprintf`
- size: `292`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x1800332d8`
- `0x180055b90`

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
0x180055b90  push    rbp
0x180055b92  push    rbx
0x180055b93  push    rdi
0x180055b94  lea     rbp, [rsp-3Fh]
0x180055b99  sub     rsp, 0B0h
0x180055ba0  and     [rbp+4Fh+var_90], 0
0x180055ba5  mov     [rbp+4Fh+var_80], 0
0x180055ba9  mov     [rbp+4Fh+var_68], 0
0x180055bad  mov     [rbp+4Fh+var_60], 0
0x180055bb1  mov     [rbp+4Fh+var_58], 0
0x180055bb5  test    r9, r9
0x180055bb8  jz      short loc_180055BC0
0x180055bba  movups  xmm0, xmmword ptr [r9]
0x180055bbe  jmp     short loc_180055BD0
0x180055bc0  cmp     cs:__acrt_locale_changed_data, 0
0x180055bc7  jnz     short loc_180055BD9
0x180055bc9  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180055bd0  mov     [rbp+4Fh+var_68], 1
0x180055bd4  movdqu  [rbp+4Fh+var_78], xmm0
0x180055bd9  mov     rax, [rbp+4Fh+ArgList]
0x180055bdd  mov     [rbp+4Fh+arg_18], rax
0x180055be1  mov     [rbp+4Fh+arg_10], r8
0x180055be5  mov     [rbp+4Fh+arg_0], rdx
0x180055be9  mov     [rbp+4Fh+arg_8], rcx
0x180055bed  test    rdx, rdx
0x180055bf0  jnz     short loc_180055C20
0x180055bf2  lea     rax, [rbp+4Fh+var_90]
0x180055bf6  mov     [rbp+4Fh+var_60], 1
0x180055bfa  mov     [rsp+0C0h+var_98], rax; __crt_cached_ptd_host *
0x180055bff  xor     r9d, r9d; LineNo
0x180055c02  and     [rsp+0C0h+var_A0], 0
0x180055c08  xor     r8d, r8d; FileName
0x180055c0b  xor     edx, edx; FunctionName
0x180055c0d  mov     [rbp+4Fh+var_64], 16h
0x180055c14  xor     ecx, ecx; Expression
0x180055c16  call    _invalid_parameter_internal
0x180055c1b  or      edi, 0FFFFFFFFh
0x180055c1e  jmp     short loc_180055C6C
0x180055c20  test    r8, r8
0x180055c23  jz      short loc_180055BF2
0x180055c25  lea     rax, [rbp+4Fh+arg_0]
0x180055c29  mov     [rbp+4Fh+var_50], rdx
0x180055c2d  mov     [rbp+4Fh+var_40], rax
0x180055c31  lea     r9, [rbp+4Fh+var_50]
0x180055c35  lea     rax, [rbp+4Fh+var_90]
0x180055c39  mov     [rbp+4Fh+var_48], rdx
0x180055c3d  mov     [rbp+4Fh+var_38], rax
0x180055c41  lea     r8, [rbp+4Fh+var_40]
0x180055c45  lea     rax, [rbp+4Fh+arg_8]
0x180055c49  mov     [rbp+4Fh+var_30], rax
0x180055c4d  lea     rdx, [rbp+4Fh+var_48]
0x180055c51  lea     rax, [rbp+4Fh+arg_10]
0x180055c55  mov     [rbp+4Fh+var_28], rax
0x180055c59  lea     rcx, [rbp+4Fh+ArgList]
0x180055c5d  lea     rax, [rbp+4Fh+arg_18]
0x180055c61  mov     [rbp+4Fh+var_20], rax
0x180055c65  call    __crt_seh_guarded_call_int___operator____lambda_d854c62834386a3b23916ad6dae2782d___lambda_303760bc4008a2b3ec4768a30b06a80c_____lambda_4780a7ea4f8cbd2590aec34bd14e2bbf___
0x180055c6a  mov     edi, eax
0x180055c6c  cmp     [rbp+4Fh+var_68], 2
0x180055c70  jnz     short loc_180055C7D
0x180055c72  mov     rcx, [rbp+4Fh+var_90]
0x180055c76  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x180055c7d  cmp     [rbp+4Fh+var_60], 0
0x180055c81  jz      short loc_180055C92
0x180055c83  mov     ebx, [rbp+4Fh+var_64]
0x180055c86  lea     rcx, [rbp+4Fh+var_90]; this
0x180055c8a  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180055c8f  mov     [rax+20h], ebx
0x180055c92  cmp     [rbp+4Fh+var_58], 0
0x180055c96  jz      short loc_180055CA7
0x180055c98  mov     ebx, [rbp+4Fh+var_5C]
0x180055c9b  lea     rcx, [rbp+4Fh+var_90]; this
0x180055c9f  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180055ca4  mov     [rax+24h], ebx
0x180055ca7  mov     eax, edi
0x180055ca9  add     rsp, 0B0h
0x180055cb0  pop     rdi
0x180055cb1  pop     rbx
0x180055cb2  pop     rbp
0x180055cb3  retn
```
