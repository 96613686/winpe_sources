# __stdio_common_vswscanf

- ea: `0x180023d3c`
- end: `0x180023e3c`
- name: `__stdio_common_vswscanf`
- size: `256`
- prototype: `int __cdecl(unsigned __int64 Options, const wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800072e8`

## callees

- `0x18000be9c`
- `0x18000bfbc`
- `0x18000c5a4`
- `0x18000fe3c`
- `0x180010b18`
- `0x180022394`
- `0x180023d3c`

## pseudocode

```c
int __cdecl _stdio_common_vswscanf(
        unsigned __int64 Options,
        const wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  int v9; // ebx
  size_t v10; // rbx
  _QWORD v12[7]; // [rsp+28h] [rbp-69h] BYREF
  int v13; // [rsp+60h] [rbp-31h]
  char v14; // [rsp+64h] [rbp-2Dh]
  __int64 v15; // [rsp+68h] [rbp-29h]
  int v16; // [rsp+70h] [rbp-21h]
  char v17; // [rsp+74h] [rbp-1Dh]
  int v18; // [rsp+78h] [rbp-19h]
  void *Block; // [rsp+80h] [rbp-11h]
  _BYTE *v20; // [rsp+88h] [rbp-9h]
  va_list v21; // [rsp+90h] [rbp-1h]
  __int64 v22; // [rsp+98h] [rbp+7h]
  __int64 v23; // [rsp+A8h] [rbp+17h] BYREF
  _BYTE v24[24]; // [rsp+B0h] [rbp+1Fh] BYREF

  if ( Buffer && Format )
  {
    v10 = wcsnlen(Buffer, BufferCount);
    _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)&v23, Locale);
    v12[0] = Options;
    v12[2] = &Buffer[v10];
    v12[1] = Buffer;
    v20 = v24;
    v21 = ArgList;
    v12[3] = Buffer;
    v12[4] = Options;
    v12[5] = Format;
    v12[6] = 0;
    Block = 0;
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v22 = 0;
    v9 = __crt_stdio_input::input_processor<wchar_t,__crt_stdio_input::string_input_adapter<wchar_t>>::process(v12);
    free_base(Block);
    Block = 0;
    if ( v24[16] )
      *(_DWORD *)(v23 + 936) &= ~2u;
  }
  else
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return -1;
  }
  return v9;
}

```

## disassembly

```asm
0x180023d3c  mov     rax, rsp
0x180023d3f  mov     [rax+8], rbx
0x180023d43  mov     [rax+10h], rsi
0x180023d47  mov     [rax+18h], rdi
0x180023d4b  push    rbp
0x180023d4c  push    r14
0x180023d4e  push    r15
0x180023d50  lea     rbp, [rax-4Fh]
0x180023d54  sub     rsp, 0C0h
0x180023d5b  xor     r15d, r15d
0x180023d5e  mov     rsi, r9
0x180023d61  mov     rdi, rdx
0x180023d64  mov     r14, rcx
0x180023d67  test    rdx, rdx
0x180023d6a  jnz     short loc_180023D84
0x180023d6c  call    _errno
0x180023d71  mov     dword ptr [rax], 16h
0x180023d77  call    _invalid_parameter_noinfo
0x180023d7c  or      ebx, 0FFFFFFFFh
0x180023d7f  jmp     loc_180023E1D
0x180023d84  test    rsi, rsi
0x180023d87  jz      short loc_180023D6C
0x180023d89  mov     rdx, r8; MaxCount
0x180023d8c  mov     rcx, rdi; Source
0x180023d8f  call    wcsnlen
0x180023d94  mov     rdx, [rbp+47h+Locale]; struct __crt_locale_pointers *
0x180023d98  lea     rcx, [rbp+47h+var_30]; this
0x180023d9c  mov     rbx, rax
0x180023d9f  call    ??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z; _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)
0x180023da4  lea     rax, [rdi+rbx*2]
0x180023da8  mov     [rbp+47h+var_B0], r14
0x180023dac  mov     [rbp+47h+var_A0], rax
0x180023db0  lea     rcx, [rbp+47h+var_B0]
0x180023db4  lea     rax, [rbp+47h+var_28]
0x180023db8  mov     [rbp+47h+var_A8], rdi
0x180023dbc  mov     [rbp+47h+var_50], rax
0x180023dc0  mov     rax, [rbp+47h+ArgList]
0x180023dc4  mov     [rbp+47h+var_48], rax
0x180023dc8  mov     [rbp+47h+var_98], rdi
0x180023dcc  mov     [rbp+47h+var_90], r14
0x180023dd0  mov     [rbp+47h+var_88], rsi
0x180023dd4  mov     [rbp+47h+var_80], r15
0x180023dd8  mov     [rbp+47h+Block], r15
0x180023ddc  mov     [rbp+47h+var_78], r15d
0x180023de0  mov     [rbp+47h+var_74], r15b
0x180023de4  mov     [rbp+47h+var_70], r15
0x180023de8  mov     [rbp+47h+var_68], r15d
0x180023dec  mov     [rbp+47h+var_64], r15b
0x180023df0  mov     [rbp+47h+var_60], r15d
0x180023df4  mov     [rbp+47h+var_40], r15
0x180023df8  call    ?process@?$input_processor@_WV?$string_input_adapter@_W@__crt_stdio_input@@@__crt_stdio_input@@QEAAHXZ; __crt_stdio_input::input_processor<wchar_t,__crt_stdio_input::string_input_adapter<wchar_t>>::process(void)
0x180023dfd  mov     rcx, [rbp+47h+Block]; Block
0x180023e01  mov     ebx, eax
0x180023e03  call    _free_base
0x180023e08  mov     [rbp+47h+Block], r15
0x180023e0c  cmp     [rbp+47h+var_18], r15b
0x180023e10  jz      short loc_180023E1D
0x180023e12  mov     rcx, [rbp+47h+var_30]
0x180023e16  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x180023e1d  lea     r11, [rsp+0D0h+var_10]
0x180023e25  mov     eax, ebx
0x180023e27  mov     rbx, [r11+20h]
0x180023e2b  mov     rsi, [r11+28h]
0x180023e2f  mov     rdi, [r11+30h]
0x180023e33  mov     rsp, r11
0x180023e36  pop     r15
0x180023e38  pop     r14
0x180023e3a  pop     rbp
0x180023e3b  retn
```
