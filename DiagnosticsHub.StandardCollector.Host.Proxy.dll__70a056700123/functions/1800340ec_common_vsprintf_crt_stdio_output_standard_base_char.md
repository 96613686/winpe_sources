# common_vsprintf___crt_stdio_output::standard_base_char_

- ea: `0x1800340ec`
- end: `0x18003429b`
- name: `common_vsprintf___crt_stdio_output::standard_base_char_`
- size: `431`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800073e8`
- `0x1800078e0`
- `0x180032370`
- `0x1800340ec`
- `0x1800449d0`

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
0x1800340ec  push    rbp
0x1800340ee  push    rbx
0x1800340ef  push    rsi
0x1800340f0  push    rdi
0x1800340f1  push    r12
0x1800340f3  push    r14
0x1800340f5  push    r15
0x1800340f7  lea     rbp, [rsp-3D0h]
0x1800340ff  sub     rsp, 4D0h
0x180034106  mov     rax, cs:__security_cookie
0x18003410d  xor     rax, rsp
0x180034110  mov     [rbp+400h+var_40], rax
0x180034117  mov     rax, [rbp+400h+arg_20]
0x18003411e  xor     r12d, r12d
0x180034121  mov     rdi, r8
0x180034124  mov     rsi, rdx
0x180034127  mov     r15, rcx
0x18003412a  test    r9, r9
0x18003412d  jnz     short loc_18003415B
0x18003412f  mov     byte ptr [rax+30h], 1
0x180034133  xor     r9d, r9d; LineNo
0x180034136  mov     [rsp+500h+var_4D8], rax; __crt_cached_ptd_host *
0x18003413b  xor     r8d, r8d; FileName
0x18003413e  xor     edx, edx; FunctionName
0x180034140  mov     dword ptr [rax+2Ch], 16h
0x180034147  xor     ecx, ecx; Expression
0x180034149  mov     [rsp+500h+var_4E0], r12; uintptr_t
0x18003414e  call    _invalid_parameter_internal
0x180034153  or      eax, 0FFFFFFFFh
0x180034156  jmp     loc_18003425F
0x18003415b  test    rdi, rdi
0x18003415e  jz      short loc_180034165
0x180034160  test    rsi, rsi
0x180034163  jz      short loc_18003412F
0x180034165  mov     r14, r15
0x180034168  mov     [rsp+500h+var_4B7], r12d
0x18003416d  mov     [rsp+500h+var_4B3], r12w
0x180034173  mov     [rsp+500h+var_4B1], r12b
0x180034178  mov     [rsp+500h+var_4D0], rsi
0x18003417d  mov     [rsp+500h+var_4C8], rdi
0x180034182  mov     [rsp+500h+var_4C0], r12
0x180034187  and     r14d, 2
0x18003418b  jnz     short loc_180034197
0x18003418d  mov     [rsp+500h+var_4B8], r12b
0x180034192  test    rsi, rsi
0x180034195  jnz     short loc_18003419C
0x180034197  mov     [rsp+500h+var_4B8], 1
0x18003419c  mov     [rsp+500h+var_4A8], rax
0x1800341a1  lea     rcx, [rsp+500h+var_4B0]
0x1800341a6  lea     rax, [rsp+500h+var_4D0]
0x1800341ab  mov     [rsp+500h+var_490], r12d
0x1800341b0  mov     [rbp+400h+var_50], rax
0x1800341b7  xorps   xmm0, xmm0
0x1800341ba  mov     rax, [rbp+400h+arg_28]
0x1800341c1  mov     [rsp+500h+var_498], rax
0x1800341c6  mov     [rsp+500h+var_48C], r12b
0x1800341cb  mov     [rsp+500h+var_488], r12
0x1800341d0  mov     [rbp+400h+var_480], r12d
0x1800341d4  mov     [rbp+400h+var_478], r12w
0x1800341d9  mov     [rbp+400h+var_468], r12d
0x1800341dd  mov     [rbp+400h+var_464], r12b
0x1800341e1  movdqa  xmmword ptr [rbp+400h+Block], xmm0
0x1800341e9  mov     [rsp+500h+var_4B0], r15
0x1800341ee  mov     [rsp+500h+var_4A0], r9
0x1800341f3  mov     [rbp+400h+var_48], r12d
0x1800341fa  call    ?process@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(void)
0x1800341ff  movsxd  rbx, eax
0x180034202  test    rsi, rsi
0x180034205  jz      short loc_180034251
0x180034207  test    r15b, 1
0x18003420b  jz      short loc_180034230
0x18003420d  test    rdi, rdi
0x180034210  jnz     short loc_18003421B
0x180034212  test    eax, eax
0x180034214  jz      short loc_18003421B
0x180034216  or      ebx, 0FFFFFFFFh
0x180034219  jmp     short loc_180034251
0x18003421b  mov     rax, [rsp+500h+var_4C0]
0x180034220  cmp     rax, rdi
0x180034223  jnz     short loc_18003424D
0x180034225  test    ebx, ebx
0x180034227  js      short loc_180034251
0x180034229  cmp     rbx, rdi
0x18003422c  jbe     short loc_180034251
0x18003422e  jmp     short loc_180034216
0x180034230  test    r14, r14
0x180034233  jz      short loc_180034280
0x180034235  test    rdi, rdi
0x180034238  jz      short loc_180034251
0x18003423a  test    eax, eax
0x18003423c  jns     short loc_180034243
0x18003423e  mov     [rsi], r12b
0x180034241  jmp     short loc_180034251
0x180034243  mov     rax, [rsp+500h+var_4C0]
0x180034248  cmp     rax, rdi
0x18003424b  jz      short loc_180034294
0x18003424d  mov     [rsi+rax], r12b
0x180034251  mov     rcx, [rbp+400h+Block+8]; Block
0x180034258  call    _free_base
0x18003425d  mov     eax, ebx
0x18003425f  mov     rcx, [rbp+400h+var_40]
0x180034266  xor     rcx, rsp; StackCookie
0x180034269  call    __security_check_cookie
0x18003426e  add     rsp, 4D0h
0x180034275  pop     r15
0x180034277  pop     r14
0x180034279  pop     r12
0x18003427b  pop     rdi
0x18003427c  pop     rsi
0x18003427d  pop     rbx
0x18003427e  pop     rbp
0x18003427f  retn
0x180034280  test    rdi, rdi
0x180034283  jz      short loc_180034216
0x180034285  mov     rax, [rsp+500h+var_4C0]
0x18003428a  cmp     rax, rdi
0x18003428d  jnz     short loc_18003424D
0x18003428f  mov     ebx, 0FFFFFFFEh
0x180034294  mov     [rsi+rdi-1], r12b
0x180034299  jmp     short loc_180034251
```
