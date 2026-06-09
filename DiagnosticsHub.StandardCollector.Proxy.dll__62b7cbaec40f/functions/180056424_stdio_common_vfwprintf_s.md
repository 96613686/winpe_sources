# __stdio_common_vfwprintf_s

- ea: `0x180056424`
- end: `0x180056548`
- name: `__stdio_common_vfwprintf_s`
- size: `292`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000774c`
- `0x180007b48`
- `0x180033538`
- `0x180056424`

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
0x180056424  push    rbp
0x180056426  push    rbx
0x180056427  push    rdi
0x180056428  lea     rbp, [rsp-3Fh]
0x18005642d  sub     rsp, 0B0h
0x180056434  and     [rbp+4Fh+var_90], 0
0x180056439  mov     [rbp+4Fh+var_80], 0
0x18005643d  mov     [rbp+4Fh+var_68], 0
0x180056441  mov     [rbp+4Fh+var_60], 0
0x180056445  mov     [rbp+4Fh+var_58], 0
0x180056449  test    r9, r9
0x18005644c  jz      short loc_180056454
0x18005644e  movups  xmm0, xmmword ptr [r9]
0x180056452  jmp     short loc_180056464
0x180056454  cmp     cs:__acrt_locale_changed_data, 0
0x18005645b  jnz     short loc_18005646D
0x18005645d  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180056464  mov     [rbp+4Fh+var_68], 1
0x180056468  movdqu  [rbp+4Fh+var_78], xmm0
0x18005646d  mov     rax, [rbp+4Fh+ArgList]
0x180056471  mov     [rbp+4Fh+arg_18], rax
0x180056475  mov     [rbp+4Fh+arg_10], r8
0x180056479  mov     [rbp+4Fh+arg_0], rdx
0x18005647d  mov     [rbp+4Fh+arg_8], rcx
0x180056481  test    rdx, rdx
0x180056484  jnz     short loc_1800564B4
0x180056486  lea     rax, [rbp+4Fh+var_90]
0x18005648a  mov     [rbp+4Fh+var_60], 1
0x18005648e  mov     [rsp+0C0h+var_98], rax; __crt_cached_ptd_host *
0x180056493  xor     r9d, r9d; LineNo
0x180056496  and     [rsp+0C0h+var_A0], 0
0x18005649c  xor     r8d, r8d; FileName
0x18005649f  xor     edx, edx; FunctionName
0x1800564a1  mov     [rbp+4Fh+var_64], 16h
0x1800564a8  xor     ecx, ecx; Expression
0x1800564aa  call    _invalid_parameter_internal
0x1800564af  or      edi, 0FFFFFFFFh
0x1800564b2  jmp     short loc_180056500
0x1800564b4  test    r8, r8
0x1800564b7  jz      short loc_180056486
0x1800564b9  lea     rax, [rbp+4Fh+arg_0]
0x1800564bd  mov     [rbp+4Fh+var_50], rdx
0x1800564c1  mov     [rbp+4Fh+var_40], rax
0x1800564c5  lea     r9, [rbp+4Fh+var_50]
0x1800564c9  lea     rax, [rbp+4Fh+var_90]
0x1800564cd  mov     [rbp+4Fh+var_48], rdx
0x1800564d1  mov     [rbp+4Fh+var_38], rax
0x1800564d5  lea     r8, [rbp+4Fh+var_40]
0x1800564d9  lea     rax, [rbp+4Fh+arg_8]
0x1800564dd  mov     [rbp+4Fh+var_30], rax
0x1800564e1  lea     rdx, [rbp+4Fh+var_48]
0x1800564e5  lea     rax, [rbp+4Fh+arg_10]
0x1800564e9  mov     [rbp+4Fh+var_28], rax
0x1800564ed  lea     rcx, [rbp+4Fh+ArgList]
0x1800564f1  lea     rax, [rbp+4Fh+arg_18]
0x1800564f5  mov     [rbp+4Fh+var_20], rax
0x1800564f9  call    __crt_seh_guarded_call_int___operator____lambda_740b16f11d3f1d0e3539b6f82067f039___lambda_12129ca491078c9e25e3e1c40c47083e_____lambda_726acf3f6ef76bdfe9ce222780860567___
0x1800564fe  mov     edi, eax
0x180056500  cmp     [rbp+4Fh+var_68], 2
0x180056504  jnz     short loc_180056511
0x180056506  mov     rcx, [rbp+4Fh+var_90]
0x18005650a  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x180056511  cmp     [rbp+4Fh+var_60], 0
0x180056515  jz      short loc_180056526
0x180056517  mov     ebx, [rbp+4Fh+var_64]
0x18005651a  lea     rcx, [rbp+4Fh+var_90]; this
0x18005651e  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056523  mov     [rax+20h], ebx
0x180056526  cmp     [rbp+4Fh+var_58], 0
0x18005652a  jz      short loc_18005653B
0x18005652c  mov     ebx, [rbp+4Fh+var_5C]
0x18005652f  lea     rcx, [rbp+4Fh+var_90]; this
0x180056533  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056538  mov     [rax+24h], ebx
0x18005653b  mov     eax, edi
0x18005653d  add     rsp, 0B0h
0x180056544  pop     rdi
0x180056545  pop     rbx
0x180056546  pop     rbp
0x180056547  retn
```
