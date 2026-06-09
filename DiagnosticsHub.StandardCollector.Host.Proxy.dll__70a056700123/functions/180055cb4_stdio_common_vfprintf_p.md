# __stdio_common_vfprintf_p

- ea: `0x180055cb4`
- end: `0x180055dd8`
- name: `__stdio_common_vfprintf_p`
- size: `292`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x1800331d8`
- `0x180055cb4`

## pseudocode

```c
int __cdecl _stdio_common_vfprintf_p(
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
    v6 = _crt_seh_guarded_call_int_::operator()__lambda_327624876a1fadbdc74949c2cdec3325___lambda_84e9765dc95e3bd10daf0706c0bd69e1_____lambda_aeafa6d5a7ea74141bf18d6a17697d45___(
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
0x180055cb4  push    rbp
0x180055cb6  push    rbx
0x180055cb7  push    rdi
0x180055cb8  lea     rbp, [rsp-3Fh]
0x180055cbd  sub     rsp, 0B0h
0x180055cc4  and     [rbp+4Fh+var_90], 0
0x180055cc9  mov     [rbp+4Fh+var_80], 0
0x180055ccd  mov     [rbp+4Fh+var_68], 0
0x180055cd1  mov     [rbp+4Fh+var_60], 0
0x180055cd5  mov     [rbp+4Fh+var_58], 0
0x180055cd9  test    r9, r9
0x180055cdc  jz      short loc_180055CE4
0x180055cde  movups  xmm0, xmmword ptr [r9]
0x180055ce2  jmp     short loc_180055CF4
0x180055ce4  cmp     cs:__acrt_locale_changed_data, 0
0x180055ceb  jnz     short loc_180055CFD
0x180055ced  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180055cf4  mov     [rbp+4Fh+var_68], 1
0x180055cf8  movdqu  [rbp+4Fh+var_78], xmm0
0x180055cfd  mov     rax, [rbp+4Fh+ArgList]
0x180055d01  mov     [rbp+4Fh+arg_18], rax
0x180055d05  mov     [rbp+4Fh+arg_10], r8
0x180055d09  mov     [rbp+4Fh+arg_0], rdx
0x180055d0d  mov     [rbp+4Fh+arg_8], rcx
0x180055d11  test    rdx, rdx
0x180055d14  jnz     short loc_180055D44
0x180055d16  lea     rax, [rbp+4Fh+var_90]
0x180055d1a  mov     [rbp+4Fh+var_60], 1
0x180055d1e  mov     [rsp+0C0h+var_98], rax; __crt_cached_ptd_host *
0x180055d23  xor     r9d, r9d; LineNo
0x180055d26  and     [rsp+0C0h+var_A0], 0
0x180055d2c  xor     r8d, r8d; FileName
0x180055d2f  xor     edx, edx; FunctionName
0x180055d31  mov     [rbp+4Fh+var_64], 16h
0x180055d38  xor     ecx, ecx; Expression
0x180055d3a  call    _invalid_parameter_internal
0x180055d3f  or      edi, 0FFFFFFFFh
0x180055d42  jmp     short loc_180055D90
0x180055d44  test    r8, r8
0x180055d47  jz      short loc_180055D16
0x180055d49  lea     rax, [rbp+4Fh+arg_0]
0x180055d4d  mov     [rbp+4Fh+var_50], rdx
0x180055d51  mov     [rbp+4Fh+var_40], rax
0x180055d55  lea     r9, [rbp+4Fh+var_50]
0x180055d59  lea     rax, [rbp+4Fh+var_90]
0x180055d5d  mov     [rbp+4Fh+var_48], rdx
0x180055d61  mov     [rbp+4Fh+var_38], rax
0x180055d65  lea     r8, [rbp+4Fh+var_40]
0x180055d69  lea     rax, [rbp+4Fh+arg_8]
0x180055d6d  mov     [rbp+4Fh+var_30], rax
0x180055d71  lea     rdx, [rbp+4Fh+var_48]
0x180055d75  lea     rax, [rbp+4Fh+arg_10]
0x180055d79  mov     [rbp+4Fh+var_28], rax
0x180055d7d  lea     rcx, [rbp+4Fh+ArgList]
0x180055d81  lea     rax, [rbp+4Fh+arg_18]
0x180055d85  mov     [rbp+4Fh+var_20], rax
0x180055d89  call    __crt_seh_guarded_call_int___operator____lambda_327624876a1fadbdc74949c2cdec3325___lambda_84e9765dc95e3bd10daf0706c0bd69e1_____lambda_aeafa6d5a7ea74141bf18d6a17697d45___
0x180055d8e  mov     edi, eax
0x180055d90  cmp     [rbp+4Fh+var_68], 2
0x180055d94  jnz     short loc_180055DA1
0x180055d96  mov     rcx, [rbp+4Fh+var_90]
0x180055d9a  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x180055da1  cmp     [rbp+4Fh+var_60], 0
0x180055da5  jz      short loc_180055DB6
0x180055da7  mov     ebx, [rbp+4Fh+var_64]
0x180055daa  lea     rcx, [rbp+4Fh+var_90]; this
0x180055dae  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180055db3  mov     [rax+20h], ebx
0x180055db6  cmp     [rbp+4Fh+var_58], 0
0x180055dba  jz      short loc_180055DCB
0x180055dbc  mov     ebx, [rbp+4Fh+var_5C]
0x180055dbf  lea     rcx, [rbp+4Fh+var_90]; this
0x180055dc3  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180055dc8  mov     [rax+24h], ebx
0x180055dcb  mov     eax, edi
0x180055dcd  add     rsp, 0B0h
0x180055dd4  pop     rdi
0x180055dd5  pop     rbx
0x180055dd6  pop     rbp
0x180055dd7  retn
```
