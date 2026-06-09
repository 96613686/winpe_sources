# __stdio_common_vsprintf_s

- ea: `0x1800568fc`
- end: `0x180056a0d`
- name: `__stdio_common_vsprintf_s`
- size: `273`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002daac`
- `0x18002db6c`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x1800339e4`
- `0x1800568fc`

## pseudocode

```c
int __cdecl _stdio_common_vsprintf_s(
        unsigned __int64 Options,
        char *Buffer,
        size_t BufferCount,
        const char *Format,
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
  v8 = common_vsprintf___crt_stdio_output::format_validation_base_char_(
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
0x1800568fc  mov     [rsp-8+arg_0], rbx
0x180056901  mov     [rsp-8+arg_8], rsi
0x180056906  mov     [rsp-8+arg_10], rdi
0x18005690b  push    rbp
0x18005690c  mov     rbp, rsp
0x18005690f  sub     rsp, 70h
0x180056913  mov     rax, [rbp+Locale]
0x180056917  xor     esi, esi
0x180056919  mov     [rbp+var_40], rsi
0x18005691d  mov     rbx, rdx
0x180056920  mov     [rbp+var_30], sil
0x180056924  mov     [rbp+var_18], sil
0x180056928  mov     [rbp+var_10], sil
0x18005692c  mov     [rbp+var_8], sil
0x180056930  test    rax, rax
0x180056933  jz      short loc_18005693A
0x180056935  movups  xmm0, xmmword ptr [rax]
0x180056938  jmp     short loc_180056949
0x18005693a  cmp     cs:__acrt_locale_changed_data, esi
0x180056940  jnz     short loc_180056952
0x180056942  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180056949  mov     [rbp+var_18], 1
0x18005694d  movdqu  [rbp+var_28], xmm0
0x180056952  test    r9, r9
0x180056955  jz      short loc_18005698F
0x180056957  test    rbx, rbx
0x18005695a  jz      short loc_18005698F
0x18005695c  test    r8, r8
0x18005695f  jz      short loc_18005698F
0x180056961  mov     rax, [rbp+ArgList]
0x180056965  mov     [rsp+70h+var_48], rax; __int64
0x18005696a  lea     rax, [rbp+var_40]
0x18005696e  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x180056973  call    common_vsprintf___crt_stdio_output__format_validation_base_char_
0x180056978  mov     edi, eax
0x18005697a  test    eax, eax
0x18005697c  jns     short loc_180056981
0x18005697e  mov     [rbx], sil
0x180056981  cmp     eax, 0FFFFFFFEh
0x180056984  jnz     short loc_1800569BA
0x180056986  mov     [rbp+var_14], 22h ; '"'
0x18005698d  jmp     short loc_180056996
0x18005698f  mov     [rbp+var_14], 16h
0x180056996  lea     rax, [rbp+var_40]
0x18005699a  mov     [rbp+var_10], 1
0x18005699e  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x1800569a3  xor     r9d, r9d; LineNo
0x1800569a6  xor     r8d, r8d; FileName
0x1800569a9  mov     [rsp+70h+var_50], rsi; uintptr_t
0x1800569ae  xor     edx, edx; FunctionName
0x1800569b0  xor     ecx, ecx; Expression
0x1800569b2  call    _invalid_parameter_internal
0x1800569b7  or      edi, 0FFFFFFFFh
0x1800569ba  cmp     [rbp+var_18], 2
0x1800569be  jnz     short loc_1800569CB
0x1800569c0  mov     rax, [rbp+var_40]
0x1800569c4  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x1800569cb  cmp     [rbp+var_10], sil
0x1800569cf  jz      short loc_1800569E0
0x1800569d1  mov     ebx, [rbp+var_14]
0x1800569d4  lea     rcx, [rbp+var_40]; this
0x1800569d8  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800569dd  mov     [rax+20h], ebx
0x1800569e0  cmp     [rbp+var_8], sil
0x1800569e4  jz      short loc_1800569F5
0x1800569e6  mov     ebx, [rbp+var_C]
0x1800569e9  lea     rcx, [rbp+var_40]; this
0x1800569ed  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800569f2  mov     [rax+24h], ebx
0x1800569f5  lea     r11, [rsp+70h+var_s0]
0x1800569fa  mov     eax, edi
0x1800569fc  mov     rbx, [r11+10h]
0x180056a00  mov     rsi, [r11+18h]
0x180056a04  mov     rdi, [r11+20h]
0x180056a08  mov     rsp, r11
0x180056a0b  pop     rbp
0x180056a0c  retn
```
