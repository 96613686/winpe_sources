# __stdio_common_vswprintf_s

- ea: `0x180057004`
- end: `0x180057115`
- name: `__stdio_common_vswprintf_s`
- size: `273`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000774c`
- `0x180007b48`
- `0x180033e74`
- `0x180057004`

## pseudocode

```c
int __cdecl _stdio_common_vswprintf_s(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  __crt_locale_pointers v7; // xmm0
  int v8; // eax
  int v9; // edi
  int v10; // ebx
  int v11; // ebx
  _QWORD v13[2]; // [rsp+30h] [rbp-40h] BYREF
  char v14; // [rsp+40h] [rbp-30h]
  __crt_locale_pointers v15; // [rsp+48h] [rbp-28h]
  char v16; // [rsp+58h] [rbp-18h]
  int v17; // [rsp+5Ch] [rbp-14h]
  char v18; // [rsp+60h] [rbp-10h]
  int v19; // [rsp+64h] [rbp-Ch]
  char v20; // [rsp+68h] [rbp-8h]

  v13[0] = 0;
  v14 = 0;
  v16 = 0;
  v18 = 0;
  v20 = 0;
  if ( Locale )
  {
    v7 = *Locale;
LABEL_5:
    v16 = 1;
    v15 = v7;
    goto LABEL_6;
  }
  if ( !_acrt_locale_changed_data )
  {
    v7 = *(__crt_locale_pointers *)&_acrt_initial_locale_pointers;
    goto LABEL_5;
  }
LABEL_6:
  if ( !Format || !Buffer || !BufferCount )
  {
    v17 = 22;
    goto LABEL_14;
  }
  v8 = common_vsprintf___crt_stdio_output::format_validation_base_wchar_t_(
         Options,
         Buffer,
         BufferCount,
         (__int64)Format,
         (__crt_cached_ptd_host *)v13,
         (__int64)ArgList);
  v9 = v8;
  if ( v8 < 0 )
    *Buffer = 0;
  if ( v8 == -2 )
  {
    v17 = 34;
LABEL_14:
    v18 = 1;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v13);
    v9 = -1;
  }
  if ( v16 == 2 )
    *(_DWORD *)(v13[0] + 936LL) &= ~2u;
  if ( v18 )
  {
    v10 = v17;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v13) + 8) = v10;
  }
  if ( v20 )
  {
    v11 = v19;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v13) + 9) = v11;
  }
  return v9;
}

```

## disassembly

```asm
0x180057004  mov     [rsp-8+arg_0], rbx
0x180057009  mov     [rsp-8+arg_8], rsi
0x18005700e  mov     [rsp-8+arg_10], rdi
0x180057013  push    rbp
0x180057014  mov     rbp, rsp
0x180057017  sub     rsp, 70h
0x18005701b  mov     rax, [rbp+Locale]
0x18005701f  xor     esi, esi
0x180057021  mov     [rbp+var_40], rsi
0x180057025  mov     rbx, rdx
0x180057028  mov     [rbp+var_30], sil
0x18005702c  mov     [rbp+var_18], sil
0x180057030  mov     [rbp+var_10], sil
0x180057034  mov     [rbp+var_8], sil
0x180057038  test    rax, rax
0x18005703b  jz      short loc_180057042
0x18005703d  movups  xmm0, xmmword ptr [rax]
0x180057040  jmp     short loc_180057051
0x180057042  cmp     cs:__acrt_locale_changed_data, esi
0x180057048  jnz     short loc_18005705A
0x18005704a  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180057051  mov     [rbp+var_18], 1
0x180057055  movdqu  [rbp+var_28], xmm0
0x18005705a  test    r9, r9
0x18005705d  jz      short loc_180057097
0x18005705f  test    rbx, rbx
0x180057062  jz      short loc_180057097
0x180057064  test    r8, r8
0x180057067  jz      short loc_180057097
0x180057069  mov     rax, [rbp+ArgList]
0x18005706d  mov     [rsp+70h+var_48], rax; __int64
0x180057072  lea     rax, [rbp+var_40]
0x180057076  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x18005707b  call    common_vsprintf___crt_stdio_output__format_validation_base_wchar_t_
0x180057080  mov     edi, eax
0x180057082  test    eax, eax
0x180057084  jns     short loc_180057089
0x180057086  mov     [rbx], si
0x180057089  cmp     eax, 0FFFFFFFEh
0x18005708c  jnz     short loc_1800570C2
0x18005708e  mov     [rbp+var_14], 22h ; '"'
0x180057095  jmp     short loc_18005709E
0x180057097  mov     [rbp+var_14], 16h
0x18005709e  lea     rax, [rbp+var_40]
0x1800570a2  mov     [rbp+var_10], 1
0x1800570a6  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x1800570ab  xor     r9d, r9d; LineNo
0x1800570ae  xor     r8d, r8d; FileName
0x1800570b1  mov     [rsp+70h+var_50], rsi; uintptr_t
0x1800570b6  xor     edx, edx; FunctionName
0x1800570b8  xor     ecx, ecx; Expression
0x1800570ba  call    _invalid_parameter_internal
0x1800570bf  or      edi, 0FFFFFFFFh
0x1800570c2  cmp     [rbp+var_18], 2
0x1800570c6  jnz     short loc_1800570D3
0x1800570c8  mov     rax, [rbp+var_40]
0x1800570cc  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x1800570d3  cmp     [rbp+var_10], sil
0x1800570d7  jz      short loc_1800570E8
0x1800570d9  mov     ebx, [rbp+var_14]
0x1800570dc  lea     rcx, [rbp+var_40]; this
0x1800570e0  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800570e5  mov     [rax+20h], ebx
0x1800570e8  cmp     [rbp+var_8], sil
0x1800570ec  jz      short loc_1800570FD
0x1800570ee  mov     ebx, [rbp+var_C]
0x1800570f1  lea     rcx, [rbp+var_40]; this
0x1800570f5  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800570fa  mov     [rax+24h], ebx
0x1800570fd  lea     r11, [rsp+70h+var_s0]
0x180057102  mov     eax, edi
0x180057104  mov     rbx, [r11+10h]
0x180057108  mov     rsi, [r11+18h]
0x18005710c  mov     rdi, [r11+20h]
0x180057110  mov     rsp, r11
0x180057113  pop     rbp
0x180057114  retn
```
