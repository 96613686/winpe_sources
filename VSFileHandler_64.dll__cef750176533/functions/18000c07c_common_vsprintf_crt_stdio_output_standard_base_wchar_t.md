# common_vsprintf___crt_stdio_output::standard_base_wchar_t_

- ea: `0x18000c07c`
- end: `0x18000c24e`
- name: `common_vsprintf___crt_stdio_output::standard_base_wchar_t_`
- size: `466`
- prototype: `__int64 __fastcall(__int64, _WORD *, unsigned __int64, __int64, struct __crt_locale_pointers *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d6a4`

## callees

- `0x180007700`
- `0x18000be9c`
- `0x18000bfbc`
- `0x18000c07c`
- `0x18000c5a4`
- `0x18000c7fc`
- `0x18000fe3c`

## pseudocode

```c
__int64 __fastcall common_vsprintf___crt_stdio_output::standard_base_wchar_t_(
        __int64 a1,
        _WORD *a2,
        unsigned __int64 a3,
        __int64 a4,
        struct __crt_locale_pointers *a5,
        __int64 a6)
{
  int v11; // eax
  unsigned __int64 v12; // rbx
  __int64 v13; // rax
  _QWORD v14[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+30h] [rbp-D0h]
  char v16; // [rsp+38h] [rbp-C8h]
  int v17; // [rsp+39h] [rbp-C7h]
  __int16 v18; // [rsp+3Dh] [rbp-C3h]
  char v19; // [rsp+3Fh] [rbp-C1h]
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[24]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v22[7]; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+98h] [rbp-68h]
  char v24; // [rsp+A0h] [rbp-60h]
  __int16 v25; // [rsp+A2h] [rbp-5Eh]
  int v26; // [rsp+B0h] [rbp-50h]
  char v27; // [rsp+B4h] [rbp-4Ch]
  __int64 v28; // [rsp+4B8h] [rbp+3B8h]
  void *Block; // [rsp+4C0h] [rbp+3C0h]
  _QWORD *v30; // [rsp+4C8h] [rbp+3C8h]
  int v31; // [rsp+4D0h] [rbp+3D0h]

  if ( !a4 || a3 && !a2 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return 0xFFFFFFFFLL;
  }
  _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)&v20, a5);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v14[0] = a2;
  v14[1] = a3;
  v15 = 0;
  if ( (a1 & 2) != 0 || (v16 = 0, !a2) )
    v16 = 1;
  v22[2] = 0;
  v30 = v14;
  v22[5] = 0;
  v22[1] = v21;
  v22[4] = a6;
  v22[6] = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  Block = 0;
  v22[0] = a1;
  v22[3] = a4;
  v31 = 0;
  v11 = __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(v22);
  v12 = v11;
  if ( !a2 )
    goto LABEL_22;
  if ( (a1 & 1) == 0 )
  {
    if ( (a1 & 2) != 0 )
    {
      if ( !a3 )
        goto LABEL_22;
      if ( v11 < 0 )
      {
        *a2 = 0;
        goto LABEL_22;
      }
      v13 = v15;
      if ( v15 != a3 )
      {
LABEL_21:
        a2[v13] = 0;
        goto LABEL_22;
      }
    }
    else
    {
      if ( !a3 )
      {
LABEL_26:
        LODWORD(v12) = -1;
        goto LABEL_22;
      }
      v13 = v15;
      if ( v15 != a3 )
        goto LABEL_21;
      LODWORD(v12) = -2;
    }
    a2[a3 - 1] = 0;
    goto LABEL_22;
  }
  if ( !a3 && v11 )
    goto LABEL_26;
  v13 = v15;
  if ( v15 != a3 )
    goto LABEL_21;
  if ( (v12 & 0x80000000) == 0LL && v12 > a3 )
    goto LABEL_26;
LABEL_22:
  free_base(Block);
  Block = 0;
  if ( v21[16] )
    *(_DWORD *)(v20 + 936) &= ~2u;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000c07c  push    rbp
0x18000c07e  push    rbx
0x18000c07f  push    rsi
0x18000c080  push    rdi
0x18000c081  push    r12
0x18000c083  push    r14
0x18000c085  push    r15
0x18000c087  lea     rbp, [rsp-3F0h]
0x18000c08f  sub     rsp, 4F0h
0x18000c096  mov     rax, cs:__security_cookie
0x18000c09d  xor     rax, rsp
0x18000c0a0  mov     [rbp+420h+var_40], rax
0x18000c0a7  xor     r12d, r12d
0x18000c0aa  mov     rbx, r9
0x18000c0ad  mov     rdi, r8
0x18000c0b0  mov     rsi, rdx
0x18000c0b3  mov     r15, rcx
0x18000c0b6  test    r9, r9
0x18000c0b9  jnz     short loc_18000C0D3
0x18000c0bb  call    _errno
0x18000c0c0  mov     dword ptr [rax], 16h
0x18000c0c6  call    _invalid_parameter_noinfo
0x18000c0cb  or      eax, 0FFFFFFFFh
0x18000c0ce  jmp     loc_18000C20C
0x18000c0d3  test    rdi, rdi
0x18000c0d6  jz      short loc_18000C0DD
0x18000c0d8  test    rsi, rsi
0x18000c0db  jz      short loc_18000C0BB
0x18000c0dd  mov     rdx, [rbp+420h+arg_20]; struct __crt_locale_pointers *
0x18000c0e4  lea     rcx, [rsp+520h+var_4E0]; this
0x18000c0e9  call    ??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z; _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)
0x18000c0ee  mov     r14, r15
0x18000c0f1  mov     [rsp+520h+var_4E7], r12d
0x18000c0f6  mov     [rsp+520h+var_4E3], r12w
0x18000c0fc  mov     [rsp+520h+var_4E1], r12b
0x18000c101  mov     [rsp+520h+var_500], rsi
0x18000c106  mov     [rsp+520h+var_4F8], rdi
0x18000c10b  mov     [rsp+520h+var_4F0], r12
0x18000c110  and     r14d, 2
0x18000c114  jnz     short loc_18000C120
0x18000c116  mov     [rsp+520h+var_4E8], r12b
0x18000c11b  test    rsi, rsi
0x18000c11e  jnz     short loc_18000C125
0x18000c120  mov     [rsp+520h+var_4E8], 1
0x18000c125  lea     rax, [rsp+520h+var_500]
0x18000c12a  mov     [rsp+520h+var_4B0], r12
0x18000c12f  mov     [rbp+420h+var_58], rax
0x18000c136  lea     rcx, [rsp+520h+var_4C0]
0x18000c13b  lea     rax, [rsp+520h+var_4D8]
0x18000c140  mov     [rbp+420h+var_498], r12
0x18000c144  mov     [rsp+520h+var_4B8], rax
0x18000c149  mov     rax, [rbp+420h+arg_28]
0x18000c150  mov     [rbp+420h+var_4A0], rax
0x18000c154  mov     [rbp+420h+var_490], r12
0x18000c158  mov     [rbp+420h+var_488], r12d
0x18000c15c  mov     [rbp+420h+var_480], r12b
0x18000c160  mov     [rbp+420h+var_47E], r12w
0x18000c165  mov     [rbp+420h+var_470], r12d
0x18000c169  mov     [rbp+420h+var_46C], r12b
0x18000c16d  mov     [rbp+420h+var_68], r12
0x18000c174  mov     [rbp+420h+Block], r12
0x18000c17b  mov     [rsp+520h+var_4C0], r15
0x18000c180  mov     [rsp+520h+var_4A8], rbx
0x18000c185  mov     [rbp+420h+var_50], r12d
0x18000c18c  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(void)
0x18000c191  movsxd  rbx, eax
0x18000c194  test    rsi, rsi
0x18000c197  jz      short loc_18000C1E4
0x18000c199  test    r15b, 1
0x18000c19d  jz      short loc_18000C1C1
0x18000c19f  test    rdi, rdi
0x18000c1a2  jnz     short loc_18000C1AC
0x18000c1a4  test    eax, eax
0x18000c1a6  jnz     loc_18000C232
0x18000c1ac  mov     rax, [rsp+520h+var_4F0]
0x18000c1b1  cmp     rax, rdi
0x18000c1b4  jnz     short loc_18000C1DF
0x18000c1b6  test    ebx, ebx
0x18000c1b8  js      short loc_18000C1E4
0x18000c1ba  cmp     rbx, rdi
0x18000c1bd  jbe     short loc_18000C1E4
0x18000c1bf  jmp     short loc_18000C232
0x18000c1c1  test    r14, r14
0x18000c1c4  jz      short loc_18000C22D
0x18000c1c6  test    rdi, rdi
0x18000c1c9  jz      short loc_18000C1E4
0x18000c1cb  test    eax, eax
0x18000c1cd  jns     short loc_18000C1D5
0x18000c1cf  mov     [rsi], r12w
0x18000c1d3  jmp     short loc_18000C1E4
0x18000c1d5  mov     rax, [rsp+520h+var_4F0]
0x18000c1da  cmp     rax, rdi
0x18000c1dd  jz      short loc_18000C246
0x18000c1df  mov     [rsi+rax*2], r12w
0x18000c1e4  mov     rcx, [rbp+420h+Block]; Block
0x18000c1eb  call    _free_base
0x18000c1f0  mov     [rbp+420h+Block], r12
0x18000c1f7  cmp     [rsp+520h+var_4C8], r12b
0x18000c1fc  jz      short loc_18000C20A
0x18000c1fe  mov     rcx, [rsp+520h+var_4E0]
0x18000c203  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x18000c20a  mov     eax, ebx
0x18000c20c  mov     rcx, [rbp+420h+var_40]
0x18000c213  xor     rcx, rsp; StackCookie
0x18000c216  call    __security_check_cookie
0x18000c21b  add     rsp, 4F0h
0x18000c222  pop     r15
0x18000c224  pop     r14
0x18000c226  pop     r12
0x18000c228  pop     rdi
0x18000c229  pop     rsi
0x18000c22a  pop     rbx
0x18000c22b  pop     rbp
0x18000c22c  retn
0x18000c22d  test    rdi, rdi
0x18000c230  jnz     short loc_18000C237
0x18000c232  or      ebx, 0FFFFFFFFh
0x18000c235  jmp     short loc_18000C1E4
0x18000c237  mov     rax, [rsp+520h+var_4F0]
0x18000c23c  cmp     rax, rdi
0x18000c23f  jnz     short loc_18000C1DF
0x18000c241  mov     ebx, 0FFFFFFFEh
0x18000c246  mov     [rsi+rdi*2-2], r12w
0x18000c24c  jmp     short loc_18000C1E4
```
