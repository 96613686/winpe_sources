# __stdio_common_vfwprintf_p

- ea: `0x180056300`
- end: `0x180056424`
- name: `__stdio_common_vfwprintf_p`
- size: `292`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000774c`
- `0x180007b48`
- `0x180033478`
- `0x180056300`

## pseudocode

```c
int __cdecl _stdio_common_vfwprintf_p(
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
    v6 = _crt_seh_guarded_call_int_::operator()__lambda_210b5847bcebe834e8440ea2ff9427c3___lambda_53fb32cd781704b5fd5007fea1c00cf5_____lambda_72dd72b2f767e4029b6aec599a836ef7___(
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
0x180056300  push    rbp
0x180056302  push    rbx
0x180056303  push    rdi
0x180056304  lea     rbp, [rsp-3Fh]
0x180056309  sub     rsp, 0B0h
0x180056310  and     [rbp+4Fh+var_90], 0
0x180056315  mov     [rbp+4Fh+var_80], 0
0x180056319  mov     [rbp+4Fh+var_68], 0
0x18005631d  mov     [rbp+4Fh+var_60], 0
0x180056321  mov     [rbp+4Fh+var_58], 0
0x180056325  test    r9, r9
0x180056328  jz      short loc_180056330
0x18005632a  movups  xmm0, xmmword ptr [r9]
0x18005632e  jmp     short loc_180056340
0x180056330  cmp     cs:__acrt_locale_changed_data, 0
0x180056337  jnz     short loc_180056349
0x180056339  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180056340  mov     [rbp+4Fh+var_68], 1
0x180056344  movdqu  [rbp+4Fh+var_78], xmm0
0x180056349  mov     rax, [rbp+4Fh+ArgList]
0x18005634d  mov     [rbp+4Fh+arg_18], rax
0x180056351  mov     [rbp+4Fh+arg_10], r8
0x180056355  mov     [rbp+4Fh+arg_0], rdx
0x180056359  mov     [rbp+4Fh+arg_8], rcx
0x18005635d  test    rdx, rdx
0x180056360  jnz     short loc_180056390
0x180056362  lea     rax, [rbp+4Fh+var_90]
0x180056366  mov     [rbp+4Fh+var_60], 1
0x18005636a  mov     [rsp+0C0h+var_98], rax; __crt_cached_ptd_host *
0x18005636f  xor     r9d, r9d; LineNo
0x180056372  and     [rsp+0C0h+var_A0], 0
0x180056378  xor     r8d, r8d; FileName
0x18005637b  xor     edx, edx; FunctionName
0x18005637d  mov     [rbp+4Fh+var_64], 16h
0x180056384  xor     ecx, ecx; Expression
0x180056386  call    _invalid_parameter_internal
0x18005638b  or      edi, 0FFFFFFFFh
0x18005638e  jmp     short loc_1800563DC
0x180056390  test    r8, r8
0x180056393  jz      short loc_180056362
0x180056395  lea     rax, [rbp+4Fh+arg_0]
0x180056399  mov     [rbp+4Fh+var_50], rdx
0x18005639d  mov     [rbp+4Fh+var_40], rax
0x1800563a1  lea     r9, [rbp+4Fh+var_50]
0x1800563a5  lea     rax, [rbp+4Fh+var_90]
0x1800563a9  mov     [rbp+4Fh+var_48], rdx
0x1800563ad  mov     [rbp+4Fh+var_38], rax
0x1800563b1  lea     r8, [rbp+4Fh+var_40]
0x1800563b5  lea     rax, [rbp+4Fh+arg_8]
0x1800563b9  mov     [rbp+4Fh+var_30], rax
0x1800563bd  lea     rdx, [rbp+4Fh+var_48]
0x1800563c1  lea     rax, [rbp+4Fh+arg_10]
0x1800563c5  mov     [rbp+4Fh+var_28], rax
0x1800563c9  lea     rcx, [rbp+4Fh+ArgList]
0x1800563cd  lea     rax, [rbp+4Fh+arg_18]
0x1800563d1  mov     [rbp+4Fh+var_20], rax
0x1800563d5  call    __crt_seh_guarded_call_int___operator____lambda_210b5847bcebe834e8440ea2ff9427c3___lambda_53fb32cd781704b5fd5007fea1c00cf5_____lambda_72dd72b2f767e4029b6aec599a836ef7___
0x1800563da  mov     edi, eax
0x1800563dc  cmp     [rbp+4Fh+var_68], 2
0x1800563e0  jnz     short loc_1800563ED
0x1800563e2  mov     rcx, [rbp+4Fh+var_90]
0x1800563e6  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x1800563ed  cmp     [rbp+4Fh+var_60], 0
0x1800563f1  jz      short loc_180056402
0x1800563f3  mov     ebx, [rbp+4Fh+var_64]
0x1800563f6  lea     rcx, [rbp+4Fh+var_90]; this
0x1800563fa  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800563ff  mov     [rax+20h], ebx
0x180056402  cmp     [rbp+4Fh+var_58], 0
0x180056406  jz      short loc_180056417
0x180056408  mov     ebx, [rbp+4Fh+var_5C]
0x18005640b  lea     rcx, [rbp+4Fh+var_90]; this
0x18005640f  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056414  mov     [rax+24h], ebx
0x180056417  mov     eax, edi
0x180056419  add     rsp, 0B0h
0x180056420  pop     rdi
0x180056421  pop     rbx
0x180056422  pop     rbp
0x180056423  retn
```
