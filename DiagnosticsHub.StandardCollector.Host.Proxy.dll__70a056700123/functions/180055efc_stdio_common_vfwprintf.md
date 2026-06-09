# __stdio_common_vfwprintf

- ea: `0x180055efc`
- end: `0x180056020`
- name: `__stdio_common_vfwprintf`
- size: `292`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x180033218`
- `0x180055efc`

## pseudocode

```c
int __cdecl _stdio_common_vfwprintf(
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
    v6 = _crt_seh_guarded_call_int_::operator()__lambda_613eff765f5c257adf68e381dfe80f05___lambda_ebf663be9fcd9e0b17ed57bdb95b0759_____lambda_872abebd861b7db59b42e49ea65623b0___(
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
0x180055efc  push    rbp
0x180055efe  push    rbx
0x180055eff  push    rdi
0x180055f00  lea     rbp, [rsp-3Fh]
0x180055f05  sub     rsp, 0B0h
0x180055f0c  and     [rbp+4Fh+var_90], 0
0x180055f11  mov     [rbp+4Fh+var_80], 0
0x180055f15  mov     [rbp+4Fh+var_68], 0
0x180055f19  mov     [rbp+4Fh+var_60], 0
0x180055f1d  mov     [rbp+4Fh+var_58], 0
0x180055f21  test    r9, r9
0x180055f24  jz      short loc_180055F2C
0x180055f26  movups  xmm0, xmmword ptr [r9]
0x180055f2a  jmp     short loc_180055F3C
0x180055f2c  cmp     cs:__acrt_locale_changed_data, 0
0x180055f33  jnz     short loc_180055F45
0x180055f35  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180055f3c  mov     [rbp+4Fh+var_68], 1
0x180055f40  movdqu  [rbp+4Fh+var_78], xmm0
0x180055f45  mov     rax, [rbp+4Fh+ArgList]
0x180055f49  mov     [rbp+4Fh+arg_18], rax
0x180055f4d  mov     [rbp+4Fh+arg_10], r8
0x180055f51  mov     [rbp+4Fh+arg_0], rdx
0x180055f55  mov     [rbp+4Fh+arg_8], rcx
0x180055f59  test    rdx, rdx
0x180055f5c  jnz     short loc_180055F8C
0x180055f5e  lea     rax, [rbp+4Fh+var_90]
0x180055f62  mov     [rbp+4Fh+var_60], 1
0x180055f66  mov     [rsp+0C0h+var_98], rax; __crt_cached_ptd_host *
0x180055f6b  xor     r9d, r9d; LineNo
0x180055f6e  and     [rsp+0C0h+var_A0], 0
0x180055f74  xor     r8d, r8d; FileName
0x180055f77  xor     edx, edx; FunctionName
0x180055f79  mov     [rbp+4Fh+var_64], 16h
0x180055f80  xor     ecx, ecx; Expression
0x180055f82  call    _invalid_parameter_internal
0x180055f87  or      edi, 0FFFFFFFFh
0x180055f8a  jmp     short loc_180055FD8
0x180055f8c  test    r8, r8
0x180055f8f  jz      short loc_180055F5E
0x180055f91  lea     rax, [rbp+4Fh+arg_0]
0x180055f95  mov     [rbp+4Fh+var_50], rdx
0x180055f99  mov     [rbp+4Fh+var_40], rax
0x180055f9d  lea     r9, [rbp+4Fh+var_50]
0x180055fa1  lea     rax, [rbp+4Fh+var_90]
0x180055fa5  mov     [rbp+4Fh+var_48], rdx
0x180055fa9  mov     [rbp+4Fh+var_38], rax
0x180055fad  lea     r8, [rbp+4Fh+var_40]
0x180055fb1  lea     rax, [rbp+4Fh+arg_8]
0x180055fb5  mov     [rbp+4Fh+var_30], rax
0x180055fb9  lea     rdx, [rbp+4Fh+var_48]
0x180055fbd  lea     rax, [rbp+4Fh+arg_10]
0x180055fc1  mov     [rbp+4Fh+var_28], rax
0x180055fc5  lea     rcx, [rbp+4Fh+ArgList]
0x180055fc9  lea     rax, [rbp+4Fh+arg_18]
0x180055fcd  mov     [rbp+4Fh+var_20], rax
0x180055fd1  call    __crt_seh_guarded_call_int___operator____lambda_613eff765f5c257adf68e381dfe80f05___lambda_ebf663be9fcd9e0b17ed57bdb95b0759_____lambda_872abebd861b7db59b42e49ea65623b0___
0x180055fd6  mov     edi, eax
0x180055fd8  cmp     [rbp+4Fh+var_68], 2
0x180055fdc  jnz     short loc_180055FE9
0x180055fde  mov     rcx, [rbp+4Fh+var_90]
0x180055fe2  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x180055fe9  cmp     [rbp+4Fh+var_60], 0
0x180055fed  jz      short loc_180055FFE
0x180055fef  mov     ebx, [rbp+4Fh+var_64]
0x180055ff2  lea     rcx, [rbp+4Fh+var_90]; this
0x180055ff6  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180055ffb  mov     [rax+20h], ebx
0x180055ffe  cmp     [rbp+4Fh+var_58], 0
0x180056002  jz      short loc_180056013
0x180056004  mov     ebx, [rbp+4Fh+var_5C]
0x180056007  lea     rcx, [rbp+4Fh+var_90]; this
0x18005600b  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056010  mov     [rax+24h], ebx
0x180056013  mov     eax, edi
0x180056015  add     rsp, 0B0h
0x18005601c  pop     rdi
0x18005601d  pop     rbx
0x18005601e  pop     rbp
0x18005601f  retn
```
