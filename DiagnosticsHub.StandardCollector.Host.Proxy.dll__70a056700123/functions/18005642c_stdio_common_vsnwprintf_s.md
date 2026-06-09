# __stdio_common_vsnwprintf_s

- ea: `0x18005642c`
- end: `0x1800565ef`
- name: `__stdio_common_vsnwprintf_s`
- size: `451`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, size_t MaxCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x180033b94`
- `0x18005642c`

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
0x18005642c  mov     rax, rsp
0x18005642f  mov     [rax+8], rbx
0x180056433  mov     [rax+10h], rsi
0x180056437  mov     [rax+18h], rdi
0x18005643b  mov     [rax+20h], r12
0x18005643f  push    rbp
0x180056440  push    r14
0x180056442  push    r15
0x180056444  mov     rbp, rsp
0x180056447  sub     rsp, 70h
0x18005644b  mov     rax, [rbp+Locale]
0x18005644f  xor     r12d, r12d
0x180056452  mov     [rbp+var_40], r12
0x180056456  mov     r15, r9
0x180056459  mov     [rbp+var_30], r12b
0x18005645d  mov     r14, r8
0x180056460  mov     [rbp+var_18], r12b
0x180056464  mov     rsi, rdx
0x180056467  mov     byte ptr [rbp+var_14+4], r12b
0x18005646b  mov     [rbp+var_8], r12b
0x18005646f  test    rax, rax
0x180056472  jz      short loc_180056479
0x180056474  movups  xmm0, xmmword ptr [rax]
0x180056477  jmp     short loc_180056489
0x180056479  cmp     cs:__acrt_locale_changed_data, r12d
0x180056480  jnz     short loc_180056492
0x180056482  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180056489  mov     [rbp+var_18], 1
0x18005648d  movdqu  [rbp+var_28], xmm0
0x180056492  mov     r9, [rbp+Format]; int
0x180056496  test    r9, r9
0x180056499  jz      loc_180056568
0x18005649f  test    r15, r15
0x1800564a2  jnz     short loc_1800564BA
0x1800564a4  test    rsi, rsi
0x1800564a7  jnz     short loc_1800564C3
0x1800564a9  test    r14, r14
0x1800564ac  jnz     loc_180056568
0x1800564b2  mov     edi, r12d
0x1800564b5  jmp     loc_180056594
0x1800564ba  test    rsi, rsi
0x1800564bd  jz      loc_180056568
0x1800564c3  test    r14, r14
0x1800564c6  jz      loc_180056568
0x1800564cc  mov     rax, [rbp+ArgList]
0x1800564d0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800564d4  mov     rbx, [rbp+var_14]
0x1800564d8  mov     [rsp+70h+var_48], rax; __int64
0x1800564dd  lea     rax, [rbp+var_40]
0x1800564e1  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x1800564e6  cmp     r14, r15
0x1800564e9  jbe     short loc_180056516
0x1800564eb  lea     r8, [r15+1]; int
0x1800564ef  call    common_vsprintf___crt_stdio_output__format_validation_base_wchar_t_
0x1800564f4  cmp     eax, 0FFFFFFFEh
0x1800564f7  jnz     short loc_18005652D
0x1800564f9  cmp     byte ptr [rbp+var_14+4], r12b
0x1800564fd  jz      loc_180056594
0x180056503  cmp     dword ptr [rbp+var_14], 22h ; '"'
0x180056507  jnz     loc_180056594
0x18005650d  mov     [rbp+var_14], rbx
0x180056511  mov     dword ptr [rbp+var_14], ebx
0x180056514  jmp     short loc_180056594
0x180056516  call    common_vsprintf___crt_stdio_output__format_validation_base_wchar_t_
0x18005651b  mov     [rsi+r14*2-2], r12w
0x180056521  cmp     eax, 0FFFFFFFEh
0x180056524  jnz     short loc_18005652D
0x180056526  cmp     r15, rdi
0x180056529  jnz     short loc_180056531
0x18005652b  jmp     short loc_1800564F9
0x18005652d  test    eax, eax
0x18005652f  jns     short loc_180056564
0x180056531  mov     [rsi], r12w
0x180056535  cmp     eax, 0FFFFFFFEh
0x180056538  jnz     short loc_180056594
0x18005653a  lea     rax, [rbp+var_40]
0x18005653e  mov     byte ptr [rbp+var_14+4], 1
0x180056542  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x180056547  xor     r9d, r9d; LineNo
0x18005654a  xor     r8d, r8d; FileName
0x18005654d  mov     [rsp+70h+var_50], r12; uintptr_t
0x180056552  xor     edx, edx; FunctionName
0x180056554  mov     dword ptr [rbp+var_14], 22h ; '"'
0x18005655b  xor     ecx, ecx; Expression
0x18005655d  call    _invalid_parameter_internal
0x180056562  jmp     short loc_180056594
0x180056564  mov     edi, eax
0x180056566  jmp     short loc_180056594
0x180056568  lea     rax, [rbp+var_40]
0x18005656c  mov     byte ptr [rbp+var_14+4], 1
0x180056570  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x180056575  xor     r9d, r9d; LineNo
0x180056578  xor     r8d, r8d; FileName
0x18005657b  mov     [rsp+70h+var_50], r12; uintptr_t
0x180056580  xor     edx, edx; FunctionName
0x180056582  mov     dword ptr [rbp+var_14], 16h
0x180056589  xor     ecx, ecx; Expression
0x18005658b  call    _invalid_parameter_internal
0x180056590  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180056594  cmp     [rbp+var_18], 2
0x180056598  jnz     short loc_1800565A5
0x18005659a  mov     rax, [rbp+var_40]
0x18005659e  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x1800565a5  cmp     byte ptr [rbp+var_14+4], r12b
0x1800565a9  jz      short loc_1800565BA
0x1800565ab  mov     ebx, dword ptr [rbp+var_14]
0x1800565ae  lea     rcx, [rbp+var_40]; this
0x1800565b2  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800565b7  mov     [rax+20h], ebx
0x1800565ba  cmp     [rbp+var_8], r12b
0x1800565be  jz      short loc_1800565CF
0x1800565c0  mov     ebx, [rbp+var_C]
0x1800565c3  lea     rcx, [rbp+var_40]; this
0x1800565c7  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800565cc  mov     [rax+24h], ebx
0x1800565cf  lea     r11, [rsp+70h+var_s0]
0x1800565d4  mov     eax, edi
0x1800565d6  mov     rbx, [r11+20h]
0x1800565da  mov     rsi, [r11+28h]
0x1800565de  mov     rdi, [r11+30h]
0x1800565e2  mov     r12, [r11+38h]
0x1800565e6  mov     rsp, r11
0x1800565e9  pop     r15
0x1800565eb  pop     r14
0x1800565ed  pop     rbp
0x1800565ee  retn
```
