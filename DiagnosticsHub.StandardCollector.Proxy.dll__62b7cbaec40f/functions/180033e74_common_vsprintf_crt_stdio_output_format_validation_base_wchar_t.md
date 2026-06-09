# common_vsprintf___crt_stdio_output::format_validation_base_wchar_t_

- ea: `0x180033e74`
- end: `0x18003402a`
- name: `common_vsprintf___crt_stdio_output::format_validation_base_wchar_t_`
- size: `438`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180033bc0`
- `0x1800347c0`
- `0x18005670c`
- `0x180057004`

## callees

- `0x180002810`
- `0x180007b48`
- `0x180008040`
- `0x180033e74`
- `0x180045900`

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
0x180033e74  push    rbp
0x180033e76  push    rbx
0x180033e77  push    rsi
0x180033e78  push    rdi
0x180033e79  push    r12
0x180033e7b  push    r14
0x180033e7d  push    r15
0x180033e7f  lea     rbp, [rsp-3D0h]
0x180033e87  sub     rsp, 4D0h
0x180033e8e  mov     rax, cs:__security_cookie
0x180033e95  xor     rax, rsp
0x180033e98  mov     [rbp+400h+var_40], rax
0x180033e9f  mov     rax, [rbp+400h+arg_20]
0x180033ea6  xor     r12d, r12d
0x180033ea9  mov     rdi, r8
0x180033eac  mov     rsi, rdx
0x180033eaf  mov     r15, rcx
0x180033eb2  test    r9, r9
0x180033eb5  jnz     short loc_180033EE3
0x180033eb7  mov     byte ptr [rax+30h], 1
0x180033ebb  xor     r9d, r9d; LineNo
0x180033ebe  mov     [rsp+500h+var_4D8], rax; __crt_cached_ptd_host *
0x180033ec3  xor     r8d, r8d; FileName
0x180033ec6  xor     edx, edx; FunctionName
0x180033ec8  mov     dword ptr [rax+2Ch], 16h
0x180033ecf  xor     ecx, ecx; Expression
0x180033ed1  mov     [rsp+500h+var_4E0], r12; uintptr_t
0x180033ed6  call    _invalid_parameter_internal
0x180033edb  or      eax, 0FFFFFFFFh
0x180033ede  jmp     loc_180033FED
0x180033ee3  test    rdi, rdi
0x180033ee6  jz      short loc_180033EED
0x180033ee8  test    rsi, rsi
0x180033eeb  jz      short loc_180033EB7
0x180033eed  mov     r14, r15
0x180033ef0  mov     [rsp+500h+var_4B7], r12d
0x180033ef5  mov     [rsp+500h+var_4B3], r12w
0x180033efb  mov     [rsp+500h+var_4B1], r12b
0x180033f00  mov     [rsp+500h+var_4D0], rsi
0x180033f05  mov     [rsp+500h+var_4C8], rdi
0x180033f0a  mov     [rsp+500h+var_4C0], r12
0x180033f0f  and     r14d, 2
0x180033f13  jnz     short loc_180033F1F
0x180033f15  mov     [rsp+500h+var_4B8], r12b
0x180033f1a  test    rsi, rsi
0x180033f1d  jnz     short loc_180033F24
0x180033f1f  mov     [rsp+500h+var_4B8], 1
0x180033f24  mov     [rsp+500h+var_4A8], rax
0x180033f29  lea     rcx, [rsp+500h+var_4B0]
0x180033f2e  lea     rax, [rsp+500h+var_4D0]
0x180033f33  mov     [rsp+500h+var_490], r12d
0x180033f38  mov     [rbp+400h+var_50], rax
0x180033f3f  xorps   xmm0, xmm0
0x180033f42  mov     rax, [rbp+400h+arg_28]
0x180033f49  mov     [rsp+500h+var_498], rax
0x180033f4e  mov     [rsp+500h+var_48C], r12b
0x180033f53  mov     [rsp+500h+var_488], r12
0x180033f58  mov     [rbp+400h+var_480], r12d
0x180033f5c  mov     [rbp+400h+var_478], r12b
0x180033f60  mov     [rbp+400h+var_476], r12w
0x180033f65  mov     [rbp+400h+var_468], r12d
0x180033f69  mov     [rbp+400h+var_464], r12b
0x180033f6d  movdqa  xmmword ptr [rbp+400h+Block], xmm0
0x180033f75  mov     [rsp+500h+var_4B0], r15
0x180033f7a  mov     [rsp+500h+var_4A0], r9
0x180033f7f  mov     [rbp+400h+var_48], r12d
0x180033f86  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$format_validation_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(void)
0x180033f8b  movsxd  rbx, eax
0x180033f8e  test    rsi, rsi
0x180033f91  jz      short loc_180033FDF
0x180033f93  test    r15b, 1
0x180033f97  jz      short loc_180033FBC
0x180033f99  test    rdi, rdi
0x180033f9c  jnz     short loc_180033FA7
0x180033f9e  test    eax, eax
0x180033fa0  jz      short loc_180033FA7
0x180033fa2  or      ebx, 0FFFFFFFFh
0x180033fa5  jmp     short loc_180033FDF
0x180033fa7  mov     rax, [rsp+500h+var_4C0]
0x180033fac  cmp     rax, rdi
0x180033faf  jnz     short loc_180033FDA
0x180033fb1  test    ebx, ebx
0x180033fb3  js      short loc_180033FDF
0x180033fb5  cmp     rbx, rdi
0x180033fb8  jbe     short loc_180033FDF
0x180033fba  jmp     short loc_180033FA2
0x180033fbc  test    r14, r14
0x180033fbf  jz      short loc_18003400E
0x180033fc1  test    rdi, rdi
0x180033fc4  jz      short loc_180033FDF
0x180033fc6  test    eax, eax
0x180033fc8  jns     short loc_180033FD0
0x180033fca  mov     [rsi], r12w
0x180033fce  jmp     short loc_180033FDF
0x180033fd0  mov     rax, [rsp+500h+var_4C0]
0x180033fd5  cmp     rax, rdi
0x180033fd8  jz      short loc_180034022
0x180033fda  mov     [rsi+rax*2], r12w
0x180033fdf  mov     rcx, [rbp+400h+Block+8]; Block
0x180033fe6  call    _free_base
0x180033feb  mov     eax, ebx
0x180033fed  mov     rcx, [rbp+400h+var_40]
0x180033ff4  xor     rcx, rsp; StackCookie
0x180033ff7  call    __security_check_cookie
0x180033ffc  add     rsp, 4D0h
0x180034003  pop     r15
0x180034005  pop     r14
0x180034007  pop     r12
0x180034009  pop     rdi
0x18003400a  pop     rsi
0x18003400b  pop     rbx
0x18003400c  pop     rbp
0x18003400d  retn
0x18003400e  test    rdi, rdi
0x180034011  jz      short loc_180033FA2
0x180034013  mov     rax, [rsp+500h+var_4C0]
0x180034018  cmp     rax, rdi
0x18003401b  jnz     short loc_180033FDA
0x18003401d  mov     ebx, 0FFFFFFFEh
0x180034022  mov     [rsi+rdi*2-2], r12w
0x180034028  jmp     short loc_180033FDF
```
