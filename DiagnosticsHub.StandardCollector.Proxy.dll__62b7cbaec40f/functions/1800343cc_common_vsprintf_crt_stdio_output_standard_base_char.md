# common_vsprintf___crt_stdio_output::standard_base_char_

- ea: `0x1800343cc`
- end: `0x18003457b`
- name: `common_vsprintf___crt_stdio_output::standard_base_char_`
- size: `431`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002810`
- `0x180007b48`
- `0x180008040`
- `0x1800343cc`
- `0x180044cb0`

## pseudocode

```c
__int64 __fastcall common_vsprintf___crt_stdio_output::standard_base_char_(
        __int64 a1,
        _BYTE *a2,
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
  __int16 v24; // [rsp+88h] [rbp-78h]
  int v25; // [rsp+98h] [rbp-68h]
  char v26; // [rsp+9Ch] [rbp-64h]
  void *Block[2]; // [rsp+4A0h] [rbp+3A0h]
  _QWORD *v28; // [rsp+4B0h] [rbp+3B0h]
  int v29; // [rsp+4B8h] [rbp+3B8h]

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
  v28 = v13;
  v19[3] = a6;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  *(_OWORD *)Block = 0;
  v19[0] = a1;
  v19[2] = a4;
  v29 = 0;
  v10 = __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(v19);
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
0x1800343cc  push    rbp
0x1800343ce  push    rbx
0x1800343cf  push    rsi
0x1800343d0  push    rdi
0x1800343d1  push    r12
0x1800343d3  push    r14
0x1800343d5  push    r15
0x1800343d7  lea     rbp, [rsp-3D0h]
0x1800343df  sub     rsp, 4D0h
0x1800343e6  mov     rax, cs:__security_cookie
0x1800343ed  xor     rax, rsp
0x1800343f0  mov     [rbp+400h+var_40], rax
0x1800343f7  mov     rax, [rbp+400h+arg_20]
0x1800343fe  xor     r12d, r12d
0x180034401  mov     rdi, r8
0x180034404  mov     rsi, rdx
0x180034407  mov     r15, rcx
0x18003440a  test    r9, r9
0x18003440d  jnz     short loc_18003443B
0x18003440f  mov     byte ptr [rax+30h], 1
0x180034413  xor     r9d, r9d; LineNo
0x180034416  mov     [rsp+500h+var_4D8], rax; __crt_cached_ptd_host *
0x18003441b  xor     r8d, r8d; FileName
0x18003441e  xor     edx, edx; FunctionName
0x180034420  mov     dword ptr [rax+2Ch], 16h
0x180034427  xor     ecx, ecx; Expression
0x180034429  mov     [rsp+500h+var_4E0], r12; uintptr_t
0x18003442e  call    _invalid_parameter_internal
0x180034433  or      eax, 0FFFFFFFFh
0x180034436  jmp     loc_18003453F
0x18003443b  test    rdi, rdi
0x18003443e  jz      short loc_180034445
0x180034440  test    rsi, rsi
0x180034443  jz      short loc_18003440F
0x180034445  mov     r14, r15
0x180034448  mov     [rsp+500h+var_4B7], r12d
0x18003444d  mov     [rsp+500h+var_4B3], r12w
0x180034453  mov     [rsp+500h+var_4B1], r12b
0x180034458  mov     [rsp+500h+var_4D0], rsi
0x18003445d  mov     [rsp+500h+var_4C8], rdi
0x180034462  mov     [rsp+500h+var_4C0], r12
0x180034467  and     r14d, 2
0x18003446b  jnz     short loc_180034477
0x18003446d  mov     [rsp+500h+var_4B8], r12b
0x180034472  test    rsi, rsi
0x180034475  jnz     short loc_18003447C
0x180034477  mov     [rsp+500h+var_4B8], 1
0x18003447c  mov     [rsp+500h+var_4A8], rax
0x180034481  lea     rcx, [rsp+500h+var_4B0]
0x180034486  lea     rax, [rsp+500h+var_4D0]
0x18003448b  mov     [rsp+500h+var_490], r12d
0x180034490  mov     [rbp+400h+var_50], rax
0x180034497  xorps   xmm0, xmm0
0x18003449a  mov     rax, [rbp+400h+arg_28]
0x1800344a1  mov     [rsp+500h+var_498], rax
0x1800344a6  mov     [rsp+500h+var_48C], r12b
0x1800344ab  mov     [rsp+500h+var_488], r12
0x1800344b0  mov     [rbp+400h+var_480], r12d
0x1800344b4  mov     [rbp+400h+var_478], r12w
0x1800344b9  mov     [rbp+400h+var_468], r12d
0x1800344bd  mov     [rbp+400h+var_464], r12b
0x1800344c1  movdqa  xmmword ptr [rbp+400h+Block], xmm0
0x1800344c9  mov     [rsp+500h+var_4B0], r15
0x1800344ce  mov     [rsp+500h+var_4A0], r9
0x1800344d3  mov     [rbp+400h+var_48], r12d
0x1800344da  call    ?process@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(void)
0x1800344df  movsxd  rbx, eax
0x1800344e2  test    rsi, rsi
0x1800344e5  jz      short loc_180034531
0x1800344e7  test    r15b, 1
0x1800344eb  jz      short loc_180034510
0x1800344ed  test    rdi, rdi
0x1800344f0  jnz     short loc_1800344FB
0x1800344f2  test    eax, eax
0x1800344f4  jz      short loc_1800344FB
0x1800344f6  or      ebx, 0FFFFFFFFh
0x1800344f9  jmp     short loc_180034531
0x1800344fb  mov     rax, [rsp+500h+var_4C0]
0x180034500  cmp     rax, rdi
0x180034503  jnz     short loc_18003452D
0x180034505  test    ebx, ebx
0x180034507  js      short loc_180034531
0x180034509  cmp     rbx, rdi
0x18003450c  jbe     short loc_180034531
0x18003450e  jmp     short loc_1800344F6
0x180034510  test    r14, r14
0x180034513  jz      short loc_180034560
0x180034515  test    rdi, rdi
0x180034518  jz      short loc_180034531
0x18003451a  test    eax, eax
0x18003451c  jns     short loc_180034523
0x18003451e  mov     [rsi], r12b
0x180034521  jmp     short loc_180034531
0x180034523  mov     rax, [rsp+500h+var_4C0]
0x180034528  cmp     rax, rdi
0x18003452b  jz      short loc_180034574
0x18003452d  mov     [rsi+rax], r12b
0x180034531  mov     rcx, [rbp+400h+Block+8]; Block
0x180034538  call    _free_base
0x18003453d  mov     eax, ebx
0x18003453f  mov     rcx, [rbp+400h+var_40]
0x180034546  xor     rcx, rsp; StackCookie
0x180034549  call    __security_check_cookie
0x18003454e  add     rsp, 4D0h
0x180034555  pop     r15
0x180034557  pop     r14
0x180034559  pop     r12
0x18003455b  pop     rdi
0x18003455c  pop     rsi
0x18003455d  pop     rbx
0x18003455e  pop     rbp
0x18003455f  retn
0x180034560  test    rdi, rdi
0x180034563  jz      short loc_1800344F6
0x180034565  mov     rax, [rsp+500h+var_4C0]
0x18003456a  cmp     rax, rdi
0x18003456d  jnz     short loc_18003452D
0x18003456f  mov     ebx, 0FFFFFFFEh
0x180034574  mov     [rsi+rdi-1], r12b
0x180034579  jmp     short loc_180034531
```
