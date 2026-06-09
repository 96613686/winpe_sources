# __stdio_common_vfprintf_p

- ea: `0x180055f94`
- end: `0x1800560b8`
- name: `__stdio_common_vfprintf_p`
- size: `292`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000774c`
- `0x180007b48`
- `0x1800334b8`
- `0x180055f94`

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
0x180055f94  push    rbp
0x180055f96  push    rbx
0x180055f97  push    rdi
0x180055f98  lea     rbp, [rsp-3Fh]
0x180055f9d  sub     rsp, 0B0h
0x180055fa4  and     [rbp+4Fh+var_90], 0
0x180055fa9  mov     [rbp+4Fh+var_80], 0
0x180055fad  mov     [rbp+4Fh+var_68], 0
0x180055fb1  mov     [rbp+4Fh+var_60], 0
0x180055fb5  mov     [rbp+4Fh+var_58], 0
0x180055fb9  test    r9, r9
0x180055fbc  jz      short loc_180055FC4
0x180055fbe  movups  xmm0, xmmword ptr [r9]
0x180055fc2  jmp     short loc_180055FD4
0x180055fc4  cmp     cs:__acrt_locale_changed_data, 0
0x180055fcb  jnz     short loc_180055FDD
0x180055fcd  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180055fd4  mov     [rbp+4Fh+var_68], 1
0x180055fd8  movdqu  [rbp+4Fh+var_78], xmm0
0x180055fdd  mov     rax, [rbp+4Fh+ArgList]
0x180055fe1  mov     [rbp+4Fh+arg_18], rax
0x180055fe5  mov     [rbp+4Fh+arg_10], r8
0x180055fe9  mov     [rbp+4Fh+arg_0], rdx
0x180055fed  mov     [rbp+4Fh+arg_8], rcx
0x180055ff1  test    rdx, rdx
0x180055ff4  jnz     short loc_180056024
0x180055ff6  lea     rax, [rbp+4Fh+var_90]
0x180055ffa  mov     [rbp+4Fh+var_60], 1
0x180055ffe  mov     [rsp+0C0h+var_98], rax; __crt_cached_ptd_host *
0x180056003  xor     r9d, r9d; LineNo
0x180056006  and     [rsp+0C0h+var_A0], 0
0x18005600c  xor     r8d, r8d; FileName
0x18005600f  xor     edx, edx; FunctionName
0x180056011  mov     [rbp+4Fh+var_64], 16h
0x180056018  xor     ecx, ecx; Expression
0x18005601a  call    _invalid_parameter_internal
0x18005601f  or      edi, 0FFFFFFFFh
0x180056022  jmp     short loc_180056070
0x180056024  test    r8, r8
0x180056027  jz      short loc_180055FF6
0x180056029  lea     rax, [rbp+4Fh+arg_0]
0x18005602d  mov     [rbp+4Fh+var_50], rdx
0x180056031  mov     [rbp+4Fh+var_40], rax
0x180056035  lea     r9, [rbp+4Fh+var_50]
0x180056039  lea     rax, [rbp+4Fh+var_90]
0x18005603d  mov     [rbp+4Fh+var_48], rdx
0x180056041  mov     [rbp+4Fh+var_38], rax
0x180056045  lea     r8, [rbp+4Fh+var_40]
0x180056049  lea     rax, [rbp+4Fh+arg_8]
0x18005604d  mov     [rbp+4Fh+var_30], rax
0x180056051  lea     rdx, [rbp+4Fh+var_48]
0x180056055  lea     rax, [rbp+4Fh+arg_10]
0x180056059  mov     [rbp+4Fh+var_28], rax
0x18005605d  lea     rcx, [rbp+4Fh+ArgList]
0x180056061  lea     rax, [rbp+4Fh+arg_18]
0x180056065  mov     [rbp+4Fh+var_20], rax
0x180056069  call    __crt_seh_guarded_call_int___operator____lambda_327624876a1fadbdc74949c2cdec3325___lambda_84e9765dc95e3bd10daf0706c0bd69e1_____lambda_aeafa6d5a7ea74141bf18d6a17697d45___
0x18005606e  mov     edi, eax
0x180056070  cmp     [rbp+4Fh+var_68], 2
0x180056074  jnz     short loc_180056081
0x180056076  mov     rcx, [rbp+4Fh+var_90]
0x18005607a  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x180056081  cmp     [rbp+4Fh+var_60], 0
0x180056085  jz      short loc_180056096
0x180056087  mov     ebx, [rbp+4Fh+var_64]
0x18005608a  lea     rcx, [rbp+4Fh+var_90]; this
0x18005608e  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056093  mov     [rax+20h], ebx
0x180056096  cmp     [rbp+4Fh+var_58], 0
0x18005609a  jz      short loc_1800560AB
0x18005609c  mov     ebx, [rbp+4Fh+var_5C]
0x18005609f  lea     rcx, [rbp+4Fh+var_90]; this
0x1800560a3  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800560a8  mov     [rax+24h], ebx
0x1800560ab  mov     eax, edi
0x1800560ad  add     rsp, 0B0h
0x1800560b4  pop     rdi
0x1800560b5  pop     rbx
0x1800560b6  pop     rbp
0x1800560b7  retn
```
