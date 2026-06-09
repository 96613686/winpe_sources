# __stdio_common_vswscanf

- ea: `0x14000af08`
- end: `0x14000b01d`
- name: `__stdio_common_vswscanf`
- size: `277`
- prototype: `int __cdecl(unsigned __int64 Options, const wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003af50`

## callees

- `0x140003e68`
- `0x14000405c`
- `0x1400046cc`
- `0x14000a084`
- `0x14000af08`
- `0x14000fa6c`
- `0x1400107c4`

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
  __int64 v10; // rbx
  __int128 v12; // [rsp+28h] [rbp-89h]
  unsigned __int64 v13; // [rsp+48h] [rbp-69h] BYREF
  __int128 v14; // [rsp+50h] [rbp-61h]
  const wchar_t *v15; // [rsp+60h] [rbp-51h]
  unsigned __int64 v16; // [rsp+68h] [rbp-49h]
  const wchar_t *v17; // [rsp+70h] [rbp-41h]
  __int64 v18; // [rsp+78h] [rbp-39h]
  int v19; // [rsp+80h] [rbp-31h]
  char v20; // [rsp+84h] [rbp-2Dh]
  __int64 v21; // [rsp+88h] [rbp-29h]
  int v22; // [rsp+90h] [rbp-21h]
  char v23; // [rsp+94h] [rbp-1Dh]
  int v24; // [rsp+98h] [rbp-19h]
  void *Block; // [rsp+A0h] [rbp-11h]
  _BYTE *v26; // [rsp+A8h] [rbp-9h]
  va_list v27; // [rsp+B0h] [rbp-1h]
  __int64 v28; // [rsp+B8h] [rbp+7h]
  __int64 v29; // [rsp+C8h] [rbp+17h] BYREF
  _BYTE v30[24]; // [rsp+D0h] [rbp+1Fh] BYREF

  if ( Buffer && Format )
  {
    v10 = sub_140003E68(Buffer, BufferCount);
    _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)&v29, (struct __crt_locale_pointers *const)Locale);
    *(_QWORD *)&v12 = Buffer;
    *((_QWORD *)&v12 + 1) = &Buffer[v10];
    v26 = v30;
    v27 = ArgList;
    v13 = Options;
    v14 = v12;
    v16 = Options;
    v15 = Buffer;
    v17 = Format;
    v18 = 0;
    Block = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v28 = 0;
    v9 = __crt_stdio_input::input_processor<wchar_t,__crt_stdio_input::string_input_adapter<wchar_t>>::process(&v13);
    free_base(Block);
    Block = 0;
    if ( v30[16] )
      *(_DWORD *)(v29 + 936) &= ~2u;
  }
  else
  {
    *(_DWORD *)sub_14000FA6C(Options, Buffer) = 22;
    invalid_parameter_noinfo();
    return -1;
  }
  return v9;
}

```

## disassembly

```asm
0x14000af08  mov     rax, rsp
0x14000af0b  mov     [rax+8], rbx
0x14000af0f  mov     [rax+10h], rsi
0x14000af13  mov     [rax+18h], rdi
0x14000af17  push    rbp
0x14000af18  push    r14
0x14000af1a  push    r15
0x14000af1c  lea     rbp, [rax-4Fh]
0x14000af20  sub     rsp, 0E0h
0x14000af27  xor     r15d, r15d
0x14000af2a  mov     rsi, r9
0x14000af2d  mov     rdi, rdx
0x14000af30  mov     r14, rcx
0x14000af33  test    rdx, rdx
0x14000af36  jnz     short loc_14000AF50
0x14000af38  call    sub_14000FA6C
0x14000af3d  mov     dword ptr [rax], 16h
0x14000af43  call    _invalid_parameter_noinfo
0x14000af48  or      ebx, 0FFFFFFFFh
0x14000af4b  jmp     loc_14000AFFE
0x14000af50  test    rsi, rsi
0x14000af53  jz      short loc_14000AF38
0x14000af55  mov     rdx, r8
0x14000af58  mov     rcx, rdi
0x14000af5b  call    sub_140003E68
0x14000af60  mov     rdx, [rbp+47h+Locale]; struct __crt_locale_pointers *
0x14000af64  lea     rcx, [rbp+47h+var_30]; this
0x14000af68  mov     rbx, rax
0x14000af6b  call    ??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z
0x14000af70  lea     rax, [rdi+rbx*2]
0x14000af74  mov     qword ptr [rsp+0F0h+var_D8+8], rdi
0x14000af79  mov     [rsp+0F0h+var_C8], rax
0x14000af7e  lea     rcx, [rbp+47h+var_B0]
0x14000af82  movups  xmm0, [rsp+0F0h+var_D8+8]
0x14000af87  lea     rax, [rbp+47h+var_28]
0x14000af8b  mov     [rbp+47h+var_C0], rdi
0x14000af8f  movsd   xmm1, [rbp+47h+var_C0]
0x14000af94  mov     [rbp+47h+var_50], rax
0x14000af98  mov     rax, [rbp+47h+ArgList]
0x14000af9c  mov     [rbp+47h+var_48], rax
0x14000afa0  mov     [rbp+47h+var_B0], r14
0x14000afa4  movups  [rbp+47h+var_A8], xmm0
0x14000afa8  mov     [rbp+47h+var_90], r14
0x14000afac  movsd   [rbp+47h+var_98], xmm1
0x14000afb1  mov     [rbp+47h+var_88], rsi
0x14000afb5  mov     [rbp+47h+var_80], r15
0x14000afb9  mov     [rbp+47h+Block], r15
0x14000afbd  mov     [rbp+47h+var_78], r15d
0x14000afc1  mov     [rbp+47h+var_74], r15b
0x14000afc5  mov     [rbp+47h+var_70], r15
0x14000afc9  mov     [rbp+47h+var_68], r15d
0x14000afcd  mov     [rbp+47h+var_64], r15b
0x14000afd1  mov     [rbp+47h+var_60], r15d
0x14000afd5  mov     [rbp+47h+var_40], r15
0x14000afd9  call    ?process@?$input_processor@_WV?$string_input_adapter@_W@__crt_stdio_input@@@__crt_stdio_input@@QEAAHXZ
0x14000afde  mov     rcx, [rbp+47h+Block]; Block
0x14000afe2  mov     ebx, eax
0x14000afe4  call    _free_base
0x14000afe9  mov     [rbp+47h+Block], r15
0x14000afed  cmp     [rbp+47h+var_18], r15b
0x14000aff1  jz      short loc_14000AFFE
0x14000aff3  mov     rcx, [rbp+47h+var_30]
0x14000aff7  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x14000affe  lea     r11, [rsp+0F0h+var_10]
0x14000b006  mov     eax, ebx
0x14000b008  mov     rbx, [r11+20h]
0x14000b00c  mov     rsi, [r11+28h]
0x14000b010  mov     rdi, [r11+30h]
0x14000b014  mov     rsp, r11
0x14000b017  pop     r15
0x14000b019  pop     r14
0x14000b01b  pop     rbp
0x14000b01c  retn
```
