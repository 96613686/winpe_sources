# __stdio_common_vsnprintf_s

- ea: `0x180056268`
- end: `0x180056429`
- name: `__stdio_common_vsnprintf_s`
- size: `449`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, size_t MaxCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x1800339e4`
- `0x180056268`

## pseudocode

```c
int __cdecl _stdio_common_vsnprintf_s(
        unsigned __int64 Options,
        char *Buffer,
        size_t BufferCount,
        size_t MaxCount,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  __crt_locale_pointers v10; // xmm0
  int v11; // edi
  __int64 v12; // rbx
  int v13; // eax
  int v14; // ebx
  int v15; // ebx
  _QWORD v17[2]; // [rsp+30h] [rbp-40h] BYREF
  char v18; // [rsp+40h] [rbp-30h]
  __crt_locale_pointers v19; // [rsp+48h] [rbp-28h]
  char v20; // [rsp+58h] [rbp-18h]
  __int64 v21; // [rsp+5Ch] [rbp-14h]
  int v22; // [rsp+64h] [rbp-Ch]
  char v23; // [rsp+68h] [rbp-8h]

  v17[0] = 0;
  v18 = 0;
  v20 = 0;
  BYTE4(v21) = 0;
  v23 = 0;
  if ( Locale )
  {
    v10 = *Locale;
  }
  else
  {
    if ( _acrt_locale_changed_data )
      goto LABEL_6;
    v10 = *(__crt_locale_pointers *)&_acrt_initial_locale_pointers;
  }
  v20 = 1;
  v19 = v10;
LABEL_6:
  if ( !Format )
    goto LABEL_25;
  if ( MaxCount )
  {
    if ( Buffer )
      goto LABEL_12;
LABEL_25:
    BYTE4(v21) = 1;
    LODWORD(v21) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v17);
    v11 = -1;
    goto LABEL_26;
  }
  if ( !Buffer )
  {
    if ( !BufferCount )
    {
      v11 = 0;
      goto LABEL_26;
    }
    goto LABEL_25;
  }
LABEL_12:
  if ( !BufferCount )
    goto LABEL_25;
  v11 = -1;
  v12 = v21;
  if ( BufferCount > MaxCount )
  {
    v13 = common_vsprintf___crt_stdio_output::format_validation_base_char_(
            Options,
            Buffer,
            MaxCount + 1,
            (__int64)Format,
            (__crt_cached_ptd_host *)v17,
            (__int64)ArgList);
    if ( v13 == -2 )
    {
LABEL_15:
      if ( BYTE4(v21) && (_DWORD)v21 == 34 )
        v21 = v12;
      goto LABEL_26;
    }
    goto LABEL_21;
  }
  v13 = common_vsprintf___crt_stdio_output::format_validation_base_char_(
          Options,
          Buffer,
          BufferCount,
          (__int64)Format,
          (__crt_cached_ptd_host *)v17,
          (__int64)ArgList);
  Buffer[BufferCount - 1] = 0;
  if ( v13 != -2 )
  {
LABEL_21:
    if ( v13 >= 0 )
    {
      v11 = v13;
      goto LABEL_26;
    }
    goto LABEL_22;
  }
  if ( MaxCount == -1 )
    goto LABEL_15;
LABEL_22:
  *Buffer = 0;
  if ( v13 == -2 )
  {
    BYTE4(v21) = 1;
    LODWORD(v21) = 34;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v17);
  }
LABEL_26:
  if ( v20 == 2 )
    *(_DWORD *)(v17[0] + 936LL) &= ~2u;
  if ( BYTE4(v21) )
  {
    v14 = v21;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v17) + 8) = v14;
  }
  if ( v23 )
  {
    v15 = v22;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v17) + 9) = v15;
  }
  return v11;
}

```

## disassembly

```asm
0x180056268  mov     rax, rsp
0x18005626b  mov     [rax+8], rbx
0x18005626f  mov     [rax+10h], rsi
0x180056273  mov     [rax+18h], rdi
0x180056277  mov     [rax+20h], r12
0x18005627b  push    rbp
0x18005627c  push    r14
0x18005627e  push    r15
0x180056280  mov     rbp, rsp
0x180056283  sub     rsp, 70h
0x180056287  mov     rax, [rbp+Locale]
0x18005628b  xor     r12d, r12d
0x18005628e  mov     [rbp+var_40], r12
0x180056292  mov     r15, r9
0x180056295  mov     [rbp+var_30], r12b
0x180056299  mov     r14, r8
0x18005629c  mov     [rbp+var_18], r12b
0x1800562a0  mov     rsi, rdx
0x1800562a3  mov     byte ptr [rbp+var_14+4], r12b
0x1800562a7  mov     [rbp+var_8], r12b
0x1800562ab  test    rax, rax
0x1800562ae  jz      short loc_1800562B5
0x1800562b0  movups  xmm0, xmmword ptr [rax]
0x1800562b3  jmp     short loc_1800562C5
0x1800562b5  cmp     cs:__acrt_locale_changed_data, r12d
0x1800562bc  jnz     short loc_1800562CE
0x1800562be  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x1800562c5  mov     [rbp+var_18], 1
0x1800562c9  movdqu  [rbp+var_28], xmm0
0x1800562ce  mov     r9, [rbp+Format]; int
0x1800562d2  test    r9, r9
0x1800562d5  jz      loc_1800563A2
0x1800562db  test    r15, r15
0x1800562de  jnz     short loc_1800562F6
0x1800562e0  test    rsi, rsi
0x1800562e3  jnz     short loc_1800562FF
0x1800562e5  test    r14, r14
0x1800562e8  jnz     loc_1800563A2
0x1800562ee  mov     edi, r12d
0x1800562f1  jmp     loc_1800563CE
0x1800562f6  test    rsi, rsi
0x1800562f9  jz      loc_1800563A2
0x1800562ff  test    r14, r14
0x180056302  jz      loc_1800563A2
0x180056308  mov     rax, [rbp+ArgList]
0x18005630c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180056310  mov     rbx, [rbp+var_14]
0x180056314  mov     [rsp+70h+var_48], rax; __int64
0x180056319  lea     rax, [rbp+var_40]
0x18005631d  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x180056322  cmp     r14, r15
0x180056325  jbe     short loc_180056352
0x180056327  lea     r8, [r15+1]; int
0x18005632b  call    common_vsprintf___crt_stdio_output__format_validation_base_char_
0x180056330  cmp     eax, 0FFFFFFFEh
0x180056333  jnz     short loc_180056368
0x180056335  cmp     byte ptr [rbp+var_14+4], r12b
0x180056339  jz      loc_1800563CE
0x18005633f  cmp     dword ptr [rbp+var_14], 22h ; '"'
0x180056343  jnz     loc_1800563CE
0x180056349  mov     [rbp+var_14], rbx
0x18005634d  mov     dword ptr [rbp+var_14], ebx
0x180056350  jmp     short loc_1800563CE
0x180056352  call    common_vsprintf___crt_stdio_output__format_validation_base_char_
0x180056357  mov     [rsi+r14-1], r12b
0x18005635c  cmp     eax, 0FFFFFFFEh
0x18005635f  jnz     short loc_180056368
0x180056361  cmp     r15, rdi
0x180056364  jnz     short loc_18005636C
0x180056366  jmp     short loc_180056335
0x180056368  test    eax, eax
0x18005636a  jns     short loc_18005639E
0x18005636c  mov     [rsi], r12b
0x18005636f  cmp     eax, 0FFFFFFFEh
0x180056372  jnz     short loc_1800563CE
0x180056374  lea     rax, [rbp+var_40]
0x180056378  mov     byte ptr [rbp+var_14+4], 1
0x18005637c  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x180056381  xor     r9d, r9d; LineNo
0x180056384  xor     r8d, r8d; FileName
0x180056387  mov     [rsp+70h+var_50], r12; uintptr_t
0x18005638c  xor     edx, edx; FunctionName
0x18005638e  mov     dword ptr [rbp+var_14], 22h ; '"'
0x180056395  xor     ecx, ecx; Expression
0x180056397  call    _invalid_parameter_internal
0x18005639c  jmp     short loc_1800563CE
0x18005639e  mov     edi, eax
0x1800563a0  jmp     short loc_1800563CE
0x1800563a2  lea     rax, [rbp+var_40]
0x1800563a6  mov     byte ptr [rbp+var_14+4], 1
0x1800563aa  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x1800563af  xor     r9d, r9d; LineNo
0x1800563b2  xor     r8d, r8d; FileName
0x1800563b5  mov     [rsp+70h+var_50], r12; uintptr_t
0x1800563ba  xor     edx, edx; FunctionName
0x1800563bc  mov     dword ptr [rbp+var_14], 16h
0x1800563c3  xor     ecx, ecx; Expression
0x1800563c5  call    _invalid_parameter_internal
0x1800563ca  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800563ce  cmp     [rbp+var_18], 2
0x1800563d2  jnz     short loc_1800563DF
0x1800563d4  mov     rax, [rbp+var_40]
0x1800563d8  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x1800563df  cmp     byte ptr [rbp+var_14+4], r12b
0x1800563e3  jz      short loc_1800563F4
0x1800563e5  mov     ebx, dword ptr [rbp+var_14]
0x1800563e8  lea     rcx, [rbp+var_40]; this
0x1800563ec  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800563f1  mov     [rax+20h], ebx
0x1800563f4  cmp     [rbp+var_8], r12b
0x1800563f8  jz      short loc_180056409
0x1800563fa  mov     ebx, [rbp+var_C]
0x1800563fd  lea     rcx, [rbp+var_40]; this
0x180056401  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056406  mov     [rax+24h], ebx
0x180056409  lea     r11, [rsp+70h+var_s0]
0x18005640e  mov     eax, edi
0x180056410  mov     rbx, [r11+20h]
0x180056414  mov     rsi, [r11+28h]
0x180056418  mov     rdi, [r11+30h]
0x18005641c  mov     r12, [r11+38h]
0x180056420  mov     rsp, r11
0x180056423  pop     r15
0x180056425  pop     r14
0x180056427  pop     rbp
0x180056428  retn
```
