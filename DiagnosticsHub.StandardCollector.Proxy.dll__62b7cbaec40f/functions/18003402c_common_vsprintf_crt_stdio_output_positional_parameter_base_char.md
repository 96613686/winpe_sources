# common_vsprintf___crt_stdio_output::positional_parameter_base_char_

- ea: `0x18003402c`
- end: `0x1800341f7`
- name: `common_vsprintf___crt_stdio_output::positional_parameter_base_char_`
- size: `459`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180056b24`

## callees

- `0x180002810`
- `0x180007b48`
- `0x180008040`
- `0x18003402c`
- `0x1800448b0`

## pseudocode

```c
__int64 __fastcall common_vsprintf___crt_stdio_output::positional_parameter_base_char_(
        __int64 a1,
        _BYTE *a2,
        unsigned __int64 a3,
        __int64 a4,
        __crt_cached_ptd_host *a5,
        __int64 a6)
{
  char v8; // r12
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
  __int64 v30; // [rsp+4C0h] [rbp+3C0h]
  __int64 v31; // [rsp+4C8h] [rbp+3C8h]
  int v32; // [rsp+E30h] [rbp+D30h]
  int v33; // [rsp+E34h] [rbp+D34h]

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
  v32 = -1;
  v33 = -1;
  v19[1] = a5;
  v28 = v13;
  v19[3] = a6;
  v20 = 0;
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
  v30 = 0;
  v31 = a4;
  v10 = __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(v19);
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
0x18003402c  push    rbp
0x18003402e  push    rbx
0x18003402f  push    rsi
0x180034030  push    rdi
0x180034031  push    r12
0x180034033  push    r13
0x180034035  push    r15
0x180034037  lea     rbp, [rsp-0D50h]
0x18003403f  sub     rsp, 0E50h
0x180034046  mov     rax, cs:__security_cookie
0x18003404d  xor     rax, rsp
0x180034050  mov     [rbp+0D80h+var_40], rax
0x180034057  mov     rax, [rbp+0D80h+arg_20]
0x18003405e  xor     r13d, r13d
0x180034061  mov     rdi, r8
0x180034064  mov     rsi, rdx
0x180034067  mov     r12, rcx
0x18003406a  test    r9, r9
0x18003406d  jnz     short loc_18003409B
0x18003406f  mov     byte ptr [rax+30h], 1
0x180034073  xor     r9d, r9d; LineNo
0x180034076  mov     [rsp+0E80h+var_E58], rax; __crt_cached_ptd_host *
0x18003407b  xor     r8d, r8d; FileName
0x18003407e  xor     edx, edx; FunctionName
0x180034080  mov     dword ptr [rax+2Ch], 16h
0x180034087  xor     ecx, ecx; Expression
0x180034089  mov     [rsp+0E80h+var_E60], r13; uintptr_t
0x18003408e  call    _invalid_parameter_internal
0x180034093  or      eax, 0FFFFFFFFh
0x180034096  jmp     loc_1800341BB
0x18003409b  test    rdi, rdi
0x18003409e  jz      short loc_1800340A5
0x1800340a0  test    rsi, rsi
0x1800340a3  jz      short loc_18003406F
0x1800340a5  mov     r15, r12
0x1800340a8  mov     [rsp+0E80h+var_E37], r13d
0x1800340ad  mov     [rsp+0E80h+var_E33], r13w
0x1800340b3  mov     [rsp+0E80h+var_E31], r13b
0x1800340b8  mov     [rsp+0E80h+var_E50], rsi
0x1800340bd  mov     [rsp+0E80h+var_E48], rdi
0x1800340c2  mov     [rsp+0E80h+var_E40], r13
0x1800340c7  and     r15d, 2
0x1800340cb  jnz     short loc_1800340D7
0x1800340cd  mov     [rsp+0E80h+var_E38], r13b
0x1800340d2  test    rsi, rsi
0x1800340d5  jnz     short loc_1800340DC
0x1800340d7  mov     [rsp+0E80h+var_E38], 1
0x1800340dc  or      [rbp+0D80h+var_50], 0FFFFFFFFh
0x1800340e3  lea     rcx, [rsp+0E80h+var_E30]
0x1800340e8  or      [rbp+0D80h+var_4C], 0FFFFFFFFh
0x1800340ef  xorps   xmm0, xmm0
0x1800340f2  mov     [rsp+0E80h+var_E28], rax
0x1800340f7  lea     rax, [rsp+0E80h+var_E50]
0x1800340fc  mov     [rbp+0D80h+var_9D0], rax
0x180034103  mov     rax, [rbp+0D80h+arg_28]
0x18003410a  mov     [rsp+0E80h+var_E18], rax
0x18003410f  mov     [rsp+0E80h+var_E10], r13d
0x180034114  mov     [rsp+0E80h+var_E0C], r13b
0x180034119  mov     [rsp+0E80h+var_E08], r13
0x18003411e  mov     [rbp+0D80h+var_E00], r13d
0x180034122  mov     [rbp+0D80h+var_DF8], r13w
0x180034127  mov     [rbp+0D80h+var_DE8], r13d
0x18003412b  mov     [rbp+0D80h+var_DE4], r13b
0x18003412f  movdqa  xmmword ptr [rbp+0D80h+Block], xmm0
0x180034137  mov     [rsp+0E80h+var_E30], r12
0x18003413c  mov     [rsp+0E80h+var_E20], r9
0x180034141  mov     [rbp+0D80h+var_9C8], r13d
0x180034148  mov     [rbp+0D80h+var_9C0], r13
0x18003414f  mov     [rbp+0D80h+var_9B8], r9
0x180034156  call    ?process@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(void)
0x18003415b  movsxd  rbx, eax
0x18003415e  test    rsi, rsi
0x180034161  jz      short loc_1800341AD
0x180034163  test    r12b, 1
0x180034167  jz      short loc_18003418C
0x180034169  test    rdi, rdi
0x18003416c  jnz     short loc_180034177
0x18003416e  test    eax, eax
0x180034170  jz      short loc_180034177
0x180034172  or      ebx, 0FFFFFFFFh
0x180034175  jmp     short loc_1800341AD
0x180034177  mov     rax, [rsp+0E80h+var_E40]
0x18003417c  cmp     rax, rdi
0x18003417f  jnz     short loc_1800341A9
0x180034181  test    ebx, ebx
0x180034183  js      short loc_1800341AD
0x180034185  cmp     rbx, rdi
0x180034188  jbe     short loc_1800341AD
0x18003418a  jmp     short loc_180034172
0x18003418c  test    r15, r15
0x18003418f  jz      short loc_1800341DC
0x180034191  test    rdi, rdi
0x180034194  jz      short loc_1800341AD
0x180034196  test    eax, eax
0x180034198  jns     short loc_18003419F
0x18003419a  mov     [rsi], r13b
0x18003419d  jmp     short loc_1800341AD
0x18003419f  mov     rax, [rsp+0E80h+var_E40]
0x1800341a4  cmp     rax, rdi
0x1800341a7  jz      short loc_1800341F0
0x1800341a9  mov     [rsi+rax], r13b
0x1800341ad  mov     rcx, [rbp+0D80h+Block+8]; Block
0x1800341b4  call    _free_base
0x1800341b9  mov     eax, ebx
0x1800341bb  mov     rcx, [rbp+0D80h+var_40]
0x1800341c2  xor     rcx, rsp; StackCookie
0x1800341c5  call    __security_check_cookie
0x1800341ca  add     rsp, 0E50h
0x1800341d1  pop     r15
0x1800341d3  pop     r13
0x1800341d5  pop     r12
0x1800341d7  pop     rdi
0x1800341d8  pop     rsi
0x1800341d9  pop     rbx
0x1800341da  pop     rbp
0x1800341db  retn
0x1800341dc  test    rdi, rdi
0x1800341df  jz      short loc_180034172
0x1800341e1  mov     rax, [rsp+0E80h+var_E40]
0x1800341e6  cmp     rax, rdi
0x1800341e9  jnz     short loc_1800341A9
0x1800341eb  mov     ebx, 0FFFFFFFEh
0x1800341f0  mov     [rsi+rdi-1], r13b
0x1800341f5  jmp     short loc_1800341AD
```
