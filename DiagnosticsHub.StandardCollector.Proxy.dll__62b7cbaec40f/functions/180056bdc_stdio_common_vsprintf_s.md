# __stdio_common_vsprintf_s

- ea: `0x180056bdc`
- end: `0x180056ced`
- name: `__stdio_common_vsprintf_s`
- size: `273`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002e20c`
- `0x18002e2cc`

## callees

- `0x18000774c`
- `0x180007b48`
- `0x180033cc4`
- `0x180056bdc`

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
0x180056bdc  mov     [rsp-8+arg_0], rbx
0x180056be1  mov     [rsp-8+arg_8], rsi
0x180056be6  mov     [rsp-8+arg_10], rdi
0x180056beb  push    rbp
0x180056bec  mov     rbp, rsp
0x180056bef  sub     rsp, 70h
0x180056bf3  mov     rax, [rbp+Locale]
0x180056bf7  xor     esi, esi
0x180056bf9  mov     [rbp+var_40], rsi
0x180056bfd  mov     rbx, rdx
0x180056c00  mov     [rbp+var_30], sil
0x180056c04  mov     [rbp+var_18], sil
0x180056c08  mov     [rbp+var_10], sil
0x180056c0c  mov     [rbp+var_8], sil
0x180056c10  test    rax, rax
0x180056c13  jz      short loc_180056C1A
0x180056c15  movups  xmm0, xmmword ptr [rax]
0x180056c18  jmp     short loc_180056C29
0x180056c1a  cmp     cs:__acrt_locale_changed_data, esi
0x180056c20  jnz     short loc_180056C32
0x180056c22  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180056c29  mov     [rbp+var_18], 1
0x180056c2d  movdqu  [rbp+var_28], xmm0
0x180056c32  test    r9, r9
0x180056c35  jz      short loc_180056C6F
0x180056c37  test    rbx, rbx
0x180056c3a  jz      short loc_180056C6F
0x180056c3c  test    r8, r8
0x180056c3f  jz      short loc_180056C6F
0x180056c41  mov     rax, [rbp+ArgList]
0x180056c45  mov     [rsp+70h+var_48], rax; __int64
0x180056c4a  lea     rax, [rbp+var_40]
0x180056c4e  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x180056c53  call    common_vsprintf___crt_stdio_output__format_validation_base_char_
0x180056c58  mov     edi, eax
0x180056c5a  test    eax, eax
0x180056c5c  jns     short loc_180056C61
0x180056c5e  mov     [rbx], sil
0x180056c61  cmp     eax, 0FFFFFFFEh
0x180056c64  jnz     short loc_180056C9A
0x180056c66  mov     [rbp+var_14], 22h ; '"'
0x180056c6d  jmp     short loc_180056C76
0x180056c6f  mov     [rbp+var_14], 16h
0x180056c76  lea     rax, [rbp+var_40]
0x180056c7a  mov     [rbp+var_10], 1
0x180056c7e  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x180056c83  xor     r9d, r9d; LineNo
0x180056c86  xor     r8d, r8d; FileName
0x180056c89  mov     [rsp+70h+var_50], rsi; uintptr_t
0x180056c8e  xor     edx, edx; FunctionName
0x180056c90  xor     ecx, ecx; Expression
0x180056c92  call    _invalid_parameter_internal
0x180056c97  or      edi, 0FFFFFFFFh
0x180056c9a  cmp     [rbp+var_18], 2
0x180056c9e  jnz     short loc_180056CAB
0x180056ca0  mov     rax, [rbp+var_40]
0x180056ca4  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x180056cab  cmp     [rbp+var_10], sil
0x180056caf  jz      short loc_180056CC0
0x180056cb1  mov     ebx, [rbp+var_14]
0x180056cb4  lea     rcx, [rbp+var_40]; this
0x180056cb8  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056cbd  mov     [rax+20h], ebx
0x180056cc0  cmp     [rbp+var_8], sil
0x180056cc4  jz      short loc_180056CD5
0x180056cc6  mov     ebx, [rbp+var_C]
0x180056cc9  lea     rcx, [rbp+var_40]; this
0x180056ccd  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056cd2  mov     [rax+24h], ebx
0x180056cd5  lea     r11, [rsp+70h+var_s0]
0x180056cda  mov     eax, edi
0x180056cdc  mov     rbx, [r11+10h]
0x180056ce0  mov     rsi, [r11+18h]
0x180056ce4  mov     rdi, [r11+20h]
0x180056ce8  mov     rsp, r11
0x180056ceb  pop     rbp
0x180056cec  retn
```
