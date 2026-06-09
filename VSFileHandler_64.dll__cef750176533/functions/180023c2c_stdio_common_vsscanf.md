# __stdio_common_vsscanf

- ea: `0x180023c2c`
- end: `0x180023d39`
- name: `__stdio_common_vsscanf`
- size: `269`
- prototype: `int __cdecl(unsigned __int64 Options, const char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007340`

## callees

- `0x180007700`
- `0x18000be9c`
- `0x18000bfbc`
- `0x18000c5a4`
- `0x1800109c8`
- `0x1800222a0`
- `0x180023c2c`

## pseudocode

```c
int __cdecl _stdio_common_vsscanf(
        unsigned __int64 Options,
        const char *Buffer,
        size_t BufferCount,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  int result; // eax
  size_t v10; // rbx
  __int64 v11; // [rsp+20h] [rbp-89h] BYREF
  _BYTE v12[24]; // [rsp+28h] [rbp-81h] BYREF
  int v13[2]; // [rsp+40h] [rbp-69h] BYREF
  const char *v14; // [rsp+48h] [rbp-61h]
  const char *v15; // [rsp+50h] [rbp-59h]
  const char *v16; // [rsp+58h] [rbp-51h]
  unsigned __int64 v17; // [rsp+60h] [rbp-49h]
  const char *v18; // [rsp+68h] [rbp-41h]
  int v19; // [rsp+70h] [rbp-39h]
  int v20; // [rsp+74h] [rbp-35h]
  __int16 v21; // [rsp+78h] [rbp-31h]
  char v22; // [rsp+7Ah] [rbp-2Fh]
  __int64 v23; // [rsp+80h] [rbp-29h]
  int v24; // [rsp+88h] [rbp-21h]
  char v25; // [rsp+8Ch] [rbp-1Dh]
  int v26; // [rsp+90h] [rbp-19h]
  __int128 v27; // [rsp+94h] [rbp-15h]
  __int128 v28; // [rsp+A4h] [rbp-5h]
  _BYTE *v29; // [rsp+B8h] [rbp+Fh]
  va_list v30; // [rsp+C0h] [rbp+17h]
  __int64 v31; // [rsp+C8h] [rbp+1Fh]

  if ( Buffer && Format )
  {
    v10 = strnlen(Buffer, BufferCount);
    _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)&v11, Locale);
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v23 = 0;
    v24 = 0;
    v26 = 0;
    v31 = 0;
    v15 = &Buffer[v10];
    v29 = v12;
    v30 = ArgList;
    *(_QWORD *)v13 = Options;
    v14 = Buffer;
    v16 = Buffer;
    v17 = Options;
    v18 = Format;
    v27 = 0;
    v22 = 0;
    v28 = 0;
    v25 = 0;
    result = __crt_stdio_input::input_processor<char,__crt_stdio_input::string_input_adapter<char>>::process((int)v13);
    if ( v12[16] )
      *(_DWORD *)(v11 + 936) &= ~2u;
  }
  else
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x180023c2c  mov     [rsp-8+arg_0], rbx
0x180023c31  mov     [rsp-8+arg_18], rsi
0x180023c36  push    rbp
0x180023c37  push    rdi
0x180023c38  push    r14
0x180023c3a  lea     rbp, [rsp-37h]
0x180023c3f  sub     rsp, 0E0h
0x180023c46  mov     rax, cs:__security_cookie
0x180023c4d  xor     rax, rsp
0x180023c50  mov     [rbp+47h+var_20], rax
0x180023c54  mov     rsi, r9
0x180023c57  mov     rdi, rdx
0x180023c5a  mov     r14, rcx
0x180023c5d  test    rdx, rdx
0x180023c60  jnz     short loc_180023C7A
0x180023c62  call    _errno
0x180023c67  mov     dword ptr [rax], 16h
0x180023c6d  call    _invalid_parameter_noinfo
0x180023c72  or      eax, 0FFFFFFFFh
0x180023c75  jmp     loc_180023D15
0x180023c7a  test    rsi, rsi
0x180023c7d  jz      short loc_180023C62
0x180023c7f  mov     rdx, r8; MaxCount
0x180023c82  mov     rcx, rdi; String
0x180023c85  call    strnlen
0x180023c8a  mov     rdx, [rbp+47h+Locale]; struct __crt_locale_pointers *
0x180023c8e  lea     rcx, [rsp+0F0h+var_D0]; this
0x180023c93  mov     rbx, rax
0x180023c96  call    ??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z; _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)
0x180023c9b  and     [rbp+47h+var_80], 0
0x180023c9f  lea     rax, [rbx+rdi]
0x180023ca3  and     [rbp+47h+var_7C], 0
0x180023ca7  lea     rcx, [rbp+47h+var_B0]; int
0x180023cab  and     [rbp+47h+var_78], 0
0x180023cb0  xorps   xmm0, xmm0
0x180023cb3  and     [rbp+47h+var_70], 0
0x180023cb8  and     [rbp+47h+var_68], 0
0x180023cbc  and     [rbp+47h+var_60], 0
0x180023cc0  and     [rbp+47h+var_28], 0
0x180023cc5  mov     [rbp+47h+var_A0], rax
0x180023cc9  lea     rax, [rsp+0F0h+var_C8]
0x180023cce  mov     [rbp+47h+var_38], rax
0x180023cd2  mov     rax, [rbp+47h+ArgList]
0x180023cd6  mov     [rbp+47h+var_30], rax
0x180023cda  mov     qword ptr [rbp+47h+var_B0], r14
0x180023cde  mov     [rbp+47h+var_A8], rdi
0x180023ce2  mov     [rbp+47h+var_98], rdi
0x180023ce6  mov     [rbp+47h+var_90], r14
0x180023cea  mov     [rbp+47h+var_88], rsi
0x180023cee  movups  [rbp+47h+var_5C], xmm0
0x180023cf2  mov     [rbp+47h+var_76], 0
0x180023cf6  movups  [rbp+47h+var_4C], xmm0
0x180023cfa  mov     [rbp+47h+var_64], 0
0x180023cfe  call    ?process@?$input_processor@DV?$string_input_adapter@D@__crt_stdio_input@@@__crt_stdio_input@@QEAAHXZ; __crt_stdio_input::input_processor<char,__crt_stdio_input::string_input_adapter<char>>::process(void)
0x180023d03  cmp     [rbp+47h+var_B8], 0
0x180023d07  jz      short loc_180023D15
0x180023d09  mov     rcx, [rsp+0F0h+var_D0]
0x180023d0e  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x180023d15  mov     rcx, [rbp+47h+var_20]
0x180023d19  xor     rcx, rsp; StackCookie
0x180023d1c  call    __security_check_cookie
0x180023d21  lea     r11, [rsp+0F0h+var_10]
0x180023d29  mov     rbx, [r11+20h]
0x180023d2d  mov     rsi, [r11+38h]
0x180023d31  mov     rsp, r11
0x180023d34  pop     r14
0x180023d36  pop     rdi
0x180023d37  pop     rbp
0x180023d38  retn
```
