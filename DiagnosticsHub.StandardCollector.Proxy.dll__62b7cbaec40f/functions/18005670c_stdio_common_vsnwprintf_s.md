# __stdio_common_vsnwprintf_s

- ea: `0x18005670c`
- end: `0x1800568cf`
- name: `__stdio_common_vsnwprintf_s`
- size: `451`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, size_t MaxCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000774c`
- `0x180007b48`
- `0x180033e74`
- `0x18005670c`

## pseudocode

```c
int __cdecl _stdio_common_vsnwprintf_s(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        size_t MaxCount,
        const wchar_t *Format,
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
    v13 = common_vsprintf___crt_stdio_output::format_validation_base_wchar_t_(
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
  v13 = common_vsprintf___crt_stdio_output::format_validation_base_wchar_t_(
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
0x18005670c  mov     rax, rsp
0x18005670f  mov     [rax+8], rbx
0x180056713  mov     [rax+10h], rsi
0x180056717  mov     [rax+18h], rdi
0x18005671b  mov     [rax+20h], r12
0x18005671f  push    rbp
0x180056720  push    r14
0x180056722  push    r15
0x180056724  mov     rbp, rsp
0x180056727  sub     rsp, 70h
0x18005672b  mov     rax, [rbp+Locale]
0x18005672f  xor     r12d, r12d
0x180056732  mov     [rbp+var_40], r12
0x180056736  mov     r15, r9
0x180056739  mov     [rbp+var_30], r12b
0x18005673d  mov     r14, r8
0x180056740  mov     [rbp+var_18], r12b
0x180056744  mov     rsi, rdx
0x180056747  mov     byte ptr [rbp+var_14+4], r12b
0x18005674b  mov     [rbp+var_8], r12b
0x18005674f  test    rax, rax
0x180056752  jz      short loc_180056759
0x180056754  movups  xmm0, xmmword ptr [rax]
0x180056757  jmp     short loc_180056769
0x180056759  cmp     cs:__acrt_locale_changed_data, r12d
0x180056760  jnz     short loc_180056772
0x180056762  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180056769  mov     [rbp+var_18], 1
0x18005676d  movdqu  [rbp+var_28], xmm0
0x180056772  mov     r9, [rbp+Format]; int
0x180056776  test    r9, r9
0x180056779  jz      loc_180056848
0x18005677f  test    r15, r15
0x180056782  jnz     short loc_18005679A
0x180056784  test    rsi, rsi
0x180056787  jnz     short loc_1800567A3
0x180056789  test    r14, r14
0x18005678c  jnz     loc_180056848
0x180056792  mov     edi, r12d
0x180056795  jmp     loc_180056874
0x18005679a  test    rsi, rsi
0x18005679d  jz      loc_180056848
0x1800567a3  test    r14, r14
0x1800567a6  jz      loc_180056848
0x1800567ac  mov     rax, [rbp+ArgList]
0x1800567b0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800567b4  mov     rbx, [rbp+var_14]
0x1800567b8  mov     [rsp+70h+var_48], rax; __int64
0x1800567bd  lea     rax, [rbp+var_40]
0x1800567c1  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x1800567c6  cmp     r14, r15
0x1800567c9  jbe     short loc_1800567F6
0x1800567cb  lea     r8, [r15+1]; int
0x1800567cf  call    common_vsprintf___crt_stdio_output__format_validation_base_wchar_t_
0x1800567d4  cmp     eax, 0FFFFFFFEh
0x1800567d7  jnz     short loc_18005680D
0x1800567d9  cmp     byte ptr [rbp+var_14+4], r12b
0x1800567dd  jz      loc_180056874
0x1800567e3  cmp     dword ptr [rbp+var_14], 22h ; '"'
0x1800567e7  jnz     loc_180056874
0x1800567ed  mov     [rbp+var_14], rbx
0x1800567f1  mov     dword ptr [rbp+var_14], ebx
0x1800567f4  jmp     short loc_180056874
0x1800567f6  call    common_vsprintf___crt_stdio_output__format_validation_base_wchar_t_
0x1800567fb  mov     [rsi+r14*2-2], r12w
0x180056801  cmp     eax, 0FFFFFFFEh
0x180056804  jnz     short loc_18005680D
0x180056806  cmp     r15, rdi
0x180056809  jnz     short loc_180056811
0x18005680b  jmp     short loc_1800567D9
0x18005680d  test    eax, eax
0x18005680f  jns     short loc_180056844
0x180056811  mov     [rsi], r12w
0x180056815  cmp     eax, 0FFFFFFFEh
0x180056818  jnz     short loc_180056874
0x18005681a  lea     rax, [rbp+var_40]
0x18005681e  mov     byte ptr [rbp+var_14+4], 1
0x180056822  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x180056827  xor     r9d, r9d; LineNo
0x18005682a  xor     r8d, r8d; FileName
0x18005682d  mov     [rsp+70h+var_50], r12; uintptr_t
0x180056832  xor     edx, edx; FunctionName
0x180056834  mov     dword ptr [rbp+var_14], 22h ; '"'
0x18005683b  xor     ecx, ecx; Expression
0x18005683d  call    _invalid_parameter_internal
0x180056842  jmp     short loc_180056874
0x180056844  mov     edi, eax
0x180056846  jmp     short loc_180056874
0x180056848  lea     rax, [rbp+var_40]
0x18005684c  mov     byte ptr [rbp+var_14+4], 1
0x180056850  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x180056855  xor     r9d, r9d; LineNo
0x180056858  xor     r8d, r8d; FileName
0x18005685b  mov     [rsp+70h+var_50], r12; uintptr_t
0x180056860  xor     edx, edx; FunctionName
0x180056862  mov     dword ptr [rbp+var_14], 16h
0x180056869  xor     ecx, ecx; Expression
0x18005686b  call    _invalid_parameter_internal
0x180056870  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180056874  cmp     [rbp+var_18], 2
0x180056878  jnz     short loc_180056885
0x18005687a  mov     rax, [rbp+var_40]
0x18005687e  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x180056885  cmp     byte ptr [rbp+var_14+4], r12b
0x180056889  jz      short loc_18005689A
0x18005688b  mov     ebx, dword ptr [rbp+var_14]
0x18005688e  lea     rcx, [rbp+var_40]; this
0x180056892  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056897  mov     [rax+20h], ebx
0x18005689a  cmp     [rbp+var_8], r12b
0x18005689e  jz      short loc_1800568AF
0x1800568a0  mov     ebx, [rbp+var_C]
0x1800568a3  lea     rcx, [rbp+var_40]; this
0x1800568a7  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800568ac  mov     [rax+24h], ebx
0x1800568af  lea     r11, [rsp+70h+var_s0]
0x1800568b4  mov     eax, edi
0x1800568b6  mov     rbx, [r11+20h]
0x1800568ba  mov     rsi, [r11+28h]
0x1800568be  mov     rdi, [r11+30h]
0x1800568c2  mov     r12, [r11+38h]
0x1800568c6  mov     rsp, r11
0x1800568c9  pop     r15
0x1800568cb  pop     r14
0x1800568cd  pop     rbp
0x1800568ce  retn
```
