# common_vsprintf___crt_stdio_output::format_validation_base_wchar_t_

- ea: `0x180033b94`
- end: `0x180033d4a`
- name: `common_vsprintf___crt_stdio_output::format_validation_base_wchar_t_`
- size: `438`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800338e0`
- `0x1800344e0`
- `0x18005642c`
- `0x180056d24`

## callees

- `0x1800073e8`
- `0x1800078e0`
- `0x180032370`
- `0x180033b94`
- `0x180045620`

## pseudocode

```c
__int64 __fastcall common_vsprintf___crt_stdio_output::format_validation_base_wchar_t_(
        __int64 a1,
        _WORD *a2,
        unsigned __int64 a3,
        __int64 a4,
        __crt_cached_ptd_host *a5,
        __int64 a6)
{
  char v8; // r15
  int v10; // eax
  unsigned __int64 v11; // rbx
  __int64 v12; // rax
  _QWORD v13[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h]
  char v15; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+49h] [rbp-B7h]
  __int16 v17; // [rsp+4Dh] [rbp-B3h]
  char v18; // [rsp+4Fh] [rbp-B1h]
  _QWORD v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+70h] [rbp-90h]
  char v21; // [rsp+74h] [rbp-8Ch]
  __int64 v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+80h] [rbp-80h]
  char v24; // [rsp+88h] [rbp-78h]
  __int16 v25; // [rsp+8Ah] [rbp-76h]
  int v26; // [rsp+98h] [rbp-68h]
  char v27; // [rsp+9Ch] [rbp-64h]
  void *Block[2]; // [rsp+4A0h] [rbp+3A0h]
  _QWORD *v29; // [rsp+4B0h] [rbp+3B0h]
  int v30; // [rsp+4B8h] [rbp+3B8h]

  v8 = a1;
  if ( !a4 || a3 && !a2 )
  {
    *((_BYTE *)a5 + 48) = 1;
    *((_DWORD *)a5 + 11) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, a5);
    return 0xFFFFFFFFLL;
  }
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v13[0] = a2;
  v13[1] = a3;
  v14 = 0;
  if ( (a1 & 2) != 0 || (v15 = 0, !a2) )
    v15 = 1;
  v19[1] = a5;
  v20 = 0;
  v29 = v13;
  v19[3] = a6;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  *(_OWORD *)Block = 0;
  v19[0] = a1;
  v19[2] = a4;
  v30 = 0;
  v10 = __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(v19);
  v11 = v10;
  if ( a2 )
  {
    if ( (v8 & 1) != 0 )
    {
      if ( !a3 && v10 )
        goto LABEL_12;
      v12 = v14;
      if ( v14 == a3 )
      {
        if ( (v11 & 0x80000000) != 0LL || v11 <= a3 )
          goto LABEL_23;
        goto LABEL_12;
      }
      goto LABEL_22;
    }
    if ( (v8 & 2) != 0 )
    {
      if ( !a3 )
        goto LABEL_23;
      if ( v10 < 0 )
      {
        *a2 = 0;
        goto LABEL_23;
      }
      v12 = v14;
      if ( v14 != a3 )
        goto LABEL_22;
    }
    else
    {
      if ( !a3 )
      {
LABEL_12:
        LODWORD(v11) = -1;
        goto LABEL_23;
      }
      v12 = v14;
      if ( v14 != a3 )
      {
LABEL_22:
        a2[v12] = 0;
        goto LABEL_23;
      }
      LODWORD(v11) = -2;
    }
    a2[a3 - 1] = 0;
  }
LABEL_23:
  free_base(Block[1]);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180033b94  push    rbp
0x180033b96  push    rbx
0x180033b97  push    rsi
0x180033b98  push    rdi
0x180033b99  push    r12
0x180033b9b  push    r14
0x180033b9d  push    r15
0x180033b9f  lea     rbp, [rsp-3D0h]
0x180033ba7  sub     rsp, 4D0h
0x180033bae  mov     rax, cs:__security_cookie
0x180033bb5  xor     rax, rsp
0x180033bb8  mov     [rbp+400h+var_40], rax
0x180033bbf  mov     rax, [rbp+400h+arg_20]
0x180033bc6  xor     r12d, r12d
0x180033bc9  mov     rdi, r8
0x180033bcc  mov     rsi, rdx
0x180033bcf  mov     r15, rcx
0x180033bd2  test    r9, r9
0x180033bd5  jnz     short loc_180033C03
0x180033bd7  mov     byte ptr [rax+30h], 1
0x180033bdb  xor     r9d, r9d; LineNo
0x180033bde  mov     [rsp+500h+var_4D8], rax; __crt_cached_ptd_host *
0x180033be3  xor     r8d, r8d; FileName
0x180033be6  xor     edx, edx; FunctionName
0x180033be8  mov     dword ptr [rax+2Ch], 16h
0x180033bef  xor     ecx, ecx; Expression
0x180033bf1  mov     [rsp+500h+var_4E0], r12; uintptr_t
0x180033bf6  call    _invalid_parameter_internal
0x180033bfb  or      eax, 0FFFFFFFFh
0x180033bfe  jmp     loc_180033D0D
0x180033c03  test    rdi, rdi
0x180033c06  jz      short loc_180033C0D
0x180033c08  test    rsi, rsi
0x180033c0b  jz      short loc_180033BD7
0x180033c0d  mov     r14, r15
0x180033c10  mov     [rsp+500h+var_4B7], r12d
0x180033c15  mov     [rsp+500h+var_4B3], r12w
0x180033c1b  mov     [rsp+500h+var_4B1], r12b
0x180033c20  mov     [rsp+500h+var_4D0], rsi
0x180033c25  mov     [rsp+500h+var_4C8], rdi
0x180033c2a  mov     [rsp+500h+var_4C0], r12
0x180033c2f  and     r14d, 2
0x180033c33  jnz     short loc_180033C3F
0x180033c35  mov     [rsp+500h+var_4B8], r12b
0x180033c3a  test    rsi, rsi
0x180033c3d  jnz     short loc_180033C44
0x180033c3f  mov     [rsp+500h+var_4B8], 1
0x180033c44  mov     [rsp+500h+var_4A8], rax
0x180033c49  lea     rcx, [rsp+500h+var_4B0]
0x180033c4e  lea     rax, [rsp+500h+var_4D0]
0x180033c53  mov     [rsp+500h+var_490], r12d
0x180033c58  mov     [rbp+400h+var_50], rax
0x180033c5f  xorps   xmm0, xmm0
0x180033c62  mov     rax, [rbp+400h+arg_28]
0x180033c69  mov     [rsp+500h+var_498], rax
0x180033c6e  mov     [rsp+500h+var_48C], r12b
0x180033c73  mov     [rsp+500h+var_488], r12
0x180033c78  mov     [rbp+400h+var_480], r12d
0x180033c7c  mov     [rbp+400h+var_478], r12b
0x180033c80  mov     [rbp+400h+var_476], r12w
0x180033c85  mov     [rbp+400h+var_468], r12d
0x180033c89  mov     [rbp+400h+var_464], r12b
0x180033c8d  movdqa  xmmword ptr [rbp+400h+Block], xmm0
0x180033c95  mov     [rsp+500h+var_4B0], r15
0x180033c9a  mov     [rsp+500h+var_4A0], r9
0x180033c9f  mov     [rbp+400h+var_48], r12d
0x180033ca6  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$format_validation_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(void)
0x180033cab  movsxd  rbx, eax
0x180033cae  test    rsi, rsi
0x180033cb1  jz      short loc_180033CFF
0x180033cb3  test    r15b, 1
0x180033cb7  jz      short loc_180033CDC
0x180033cb9  test    rdi, rdi
0x180033cbc  jnz     short loc_180033CC7
0x180033cbe  test    eax, eax
0x180033cc0  jz      short loc_180033CC7
0x180033cc2  or      ebx, 0FFFFFFFFh
0x180033cc5  jmp     short loc_180033CFF
0x180033cc7  mov     rax, [rsp+500h+var_4C0]
0x180033ccc  cmp     rax, rdi
0x180033ccf  jnz     short loc_180033CFA
0x180033cd1  test    ebx, ebx
0x180033cd3  js      short loc_180033CFF
0x180033cd5  cmp     rbx, rdi
0x180033cd8  jbe     short loc_180033CFF
0x180033cda  jmp     short loc_180033CC2
0x180033cdc  test    r14, r14
0x180033cdf  jz      short loc_180033D2E
0x180033ce1  test    rdi, rdi
0x180033ce4  jz      short loc_180033CFF
0x180033ce6  test    eax, eax
0x180033ce8  jns     short loc_180033CF0
0x180033cea  mov     [rsi], r12w
0x180033cee  jmp     short loc_180033CFF
0x180033cf0  mov     rax, [rsp+500h+var_4C0]
0x180033cf5  cmp     rax, rdi
0x180033cf8  jz      short loc_180033D42
0x180033cfa  mov     [rsi+rax*2], r12w
0x180033cff  mov     rcx, [rbp+400h+Block+8]; Block
0x180033d06  call    _free_base
0x180033d0b  mov     eax, ebx
0x180033d0d  mov     rcx, [rbp+400h+var_40]
0x180033d14  xor     rcx, rsp; StackCookie
0x180033d17  call    __security_check_cookie
0x180033d1c  add     rsp, 4D0h
0x180033d23  pop     r15
0x180033d25  pop     r14
0x180033d27  pop     r12
0x180033d29  pop     rdi
0x180033d2a  pop     rsi
0x180033d2b  pop     rbx
0x180033d2c  pop     rbp
0x180033d2d  retn
0x180033d2e  test    rdi, rdi
0x180033d31  jz      short loc_180033CC2
0x180033d33  mov     rax, [rsp+500h+var_4C0]
0x180033d38  cmp     rax, rdi
0x180033d3b  jnz     short loc_180033CFA
0x180033d3d  mov     ebx, 0FFFFFFFEh
0x180033d42  mov     [rsi+rdi*2-2], r12w
0x180033d48  jmp     short loc_180033CFF
```
