# __stdio_common_vswprintf_s

- ea: `0x180056d24`
- end: `0x180056e35`
- name: `__stdio_common_vswprintf_s`
- size: `273`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x180033b94`
- `0x180056d24`

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
0x180056d24  mov     [rsp-8+arg_0], rbx
0x180056d29  mov     [rsp-8+arg_8], rsi
0x180056d2e  mov     [rsp-8+arg_10], rdi
0x180056d33  push    rbp
0x180056d34  mov     rbp, rsp
0x180056d37  sub     rsp, 70h
0x180056d3b  mov     rax, [rbp+Locale]
0x180056d3f  xor     esi, esi
0x180056d41  mov     [rbp+var_40], rsi
0x180056d45  mov     rbx, rdx
0x180056d48  mov     [rbp+var_30], sil
0x180056d4c  mov     [rbp+var_18], sil
0x180056d50  mov     [rbp+var_10], sil
0x180056d54  mov     [rbp+var_8], sil
0x180056d58  test    rax, rax
0x180056d5b  jz      short loc_180056D62
0x180056d5d  movups  xmm0, xmmword ptr [rax]
0x180056d60  jmp     short loc_180056D71
0x180056d62  cmp     cs:__acrt_locale_changed_data, esi
0x180056d68  jnz     short loc_180056D7A
0x180056d6a  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180056d71  mov     [rbp+var_18], 1
0x180056d75  movdqu  [rbp+var_28], xmm0
0x180056d7a  test    r9, r9
0x180056d7d  jz      short loc_180056DB7
0x180056d7f  test    rbx, rbx
0x180056d82  jz      short loc_180056DB7
0x180056d84  test    r8, r8
0x180056d87  jz      short loc_180056DB7
0x180056d89  mov     rax, [rbp+ArgList]
0x180056d8d  mov     [rsp+70h+var_48], rax; __int64
0x180056d92  lea     rax, [rbp+var_40]
0x180056d96  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x180056d9b  call    common_vsprintf___crt_stdio_output__format_validation_base_wchar_t_
0x180056da0  mov     edi, eax
0x180056da2  test    eax, eax
0x180056da4  jns     short loc_180056DA9
0x180056da6  mov     [rbx], si
0x180056da9  cmp     eax, 0FFFFFFFEh
0x180056dac  jnz     short loc_180056DE2
0x180056dae  mov     [rbp+var_14], 22h ; '"'
0x180056db5  jmp     short loc_180056DBE
0x180056db7  mov     [rbp+var_14], 16h
0x180056dbe  lea     rax, [rbp+var_40]
0x180056dc2  mov     [rbp+var_10], 1
0x180056dc6  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x180056dcb  xor     r9d, r9d; LineNo
0x180056dce  xor     r8d, r8d; FileName
0x180056dd1  mov     [rsp+70h+var_50], rsi; uintptr_t
0x180056dd6  xor     edx, edx; FunctionName
0x180056dd8  xor     ecx, ecx; Expression
0x180056dda  call    _invalid_parameter_internal
0x180056ddf  or      edi, 0FFFFFFFFh
0x180056de2  cmp     [rbp+var_18], 2
0x180056de6  jnz     short loc_180056DF3
0x180056de8  mov     rax, [rbp+var_40]
0x180056dec  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x180056df3  cmp     [rbp+var_10], sil
0x180056df7  jz      short loc_180056E08
0x180056df9  mov     ebx, [rbp+var_14]
0x180056dfc  lea     rcx, [rbp+var_40]; this
0x180056e00  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056e05  mov     [rax+20h], ebx
0x180056e08  cmp     [rbp+var_8], sil
0x180056e0c  jz      short loc_180056E1D
0x180056e0e  mov     ebx, [rbp+var_C]
0x180056e11  lea     rcx, [rbp+var_40]; this
0x180056e15  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056e1a  mov     [rax+24h], ebx
0x180056e1d  lea     r11, [rsp+70h+var_s0]
0x180056e22  mov     eax, edi
0x180056e24  mov     rbx, [r11+10h]
0x180056e28  mov     rsi, [r11+18h]
0x180056e2c  mov     rdi, [r11+20h]
0x180056e30  mov     rsp, r11
0x180056e33  pop     rbp
0x180056e34  retn
```
