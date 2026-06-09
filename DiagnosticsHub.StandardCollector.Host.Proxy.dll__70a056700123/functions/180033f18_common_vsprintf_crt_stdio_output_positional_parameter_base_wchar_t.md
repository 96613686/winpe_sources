# common_vsprintf___crt_stdio_output::positional_parameter_base_wchar_t_

- ea: `0x180033f18`
- end: `0x1800340ea`
- name: `common_vsprintf___crt_stdio_output::positional_parameter_base_wchar_t_`
- size: `466`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180056c6c`

## callees

- `0x1800073e8`
- `0x1800078e0`
- `0x180032370`
- `0x180033f18`
- `0x1800458dc`

## pseudocode

```c
__int64 __fastcall common_vsprintf___crt_stdio_output::positional_parameter_base_wchar_t_(
        __int64 a1,
        _WORD *a2,
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
  char v24; // [rsp+88h] [rbp-78h]
  __int16 v25; // [rsp+8Ah] [rbp-76h]
  int v26; // [rsp+98h] [rbp-68h]
  char v27; // [rsp+9Ch] [rbp-64h]
  void *Block[2]; // [rsp+4A0h] [rbp+3A0h]
  _QWORD *v29; // [rsp+4B0h] [rbp+3B0h]
  int v30; // [rsp+4B8h] [rbp+3B8h]
  __int64 v31; // [rsp+4C0h] [rbp+3C0h]
  __int64 v32; // [rsp+4C8h] [rbp+3C8h]
  int v33; // [rsp+E30h] [rbp+D30h]
  int v34; // [rsp+E34h] [rbp+D34h]

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
  v33 = -1;
  v34 = -1;
  v19[1] = a5;
  v29 = v13;
  v19[3] = a6;
  v20 = 0;
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
  v31 = 0;
  v32 = a4;
  v10 = __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(v19);
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
0x180033f18  push    rbp
0x180033f1a  push    rbx
0x180033f1b  push    rsi
0x180033f1c  push    rdi
0x180033f1d  push    r12
0x180033f1f  push    r13
0x180033f21  push    r15
0x180033f23  lea     rbp, [rsp-0D50h]
0x180033f2b  sub     rsp, 0E50h
0x180033f32  mov     rax, cs:__security_cookie
0x180033f39  xor     rax, rsp
0x180033f3c  mov     [rbp+0D80h+var_40], rax
0x180033f43  mov     rax, [rbp+0D80h+arg_20]
0x180033f4a  xor     r13d, r13d
0x180033f4d  mov     rdi, r8
0x180033f50  mov     rsi, rdx
0x180033f53  mov     r12, rcx
0x180033f56  test    r9, r9
0x180033f59  jnz     short loc_180033F87
0x180033f5b  mov     byte ptr [rax+30h], 1
0x180033f5f  xor     r9d, r9d; LineNo
0x180033f62  mov     [rsp+0E80h+var_E58], rax; __crt_cached_ptd_host *
0x180033f67  xor     r8d, r8d; FileName
0x180033f6a  xor     edx, edx; FunctionName
0x180033f6c  mov     dword ptr [rax+2Ch], 16h
0x180033f73  xor     ecx, ecx; Expression
0x180033f75  mov     [rsp+0E80h+var_E60], r13; uintptr_t
0x180033f7a  call    _invalid_parameter_internal
0x180033f7f  or      eax, 0FFFFFFFFh
0x180033f82  jmp     loc_1800340AD
0x180033f87  test    rdi, rdi
0x180033f8a  jz      short loc_180033F91
0x180033f8c  test    rsi, rsi
0x180033f8f  jz      short loc_180033F5B
0x180033f91  mov     r15, r12
0x180033f94  mov     [rsp+0E80h+var_E37], r13d
0x180033f99  mov     [rsp+0E80h+var_E33], r13w
0x180033f9f  mov     [rsp+0E80h+var_E31], r13b
0x180033fa4  mov     [rsp+0E80h+var_E50], rsi
0x180033fa9  mov     [rsp+0E80h+var_E48], rdi
0x180033fae  mov     [rsp+0E80h+var_E40], r13
0x180033fb3  and     r15d, 2
0x180033fb7  jnz     short loc_180033FC3
0x180033fb9  mov     [rsp+0E80h+var_E38], r13b
0x180033fbe  test    rsi, rsi
0x180033fc1  jnz     short loc_180033FC8
0x180033fc3  mov     [rsp+0E80h+var_E38], 1
0x180033fc8  or      [rbp+0D80h+var_50], 0FFFFFFFFh
0x180033fcf  lea     rcx, [rsp+0E80h+var_E30]
0x180033fd4  or      [rbp+0D80h+var_4C], 0FFFFFFFFh
0x180033fdb  xorps   xmm0, xmm0
0x180033fde  mov     [rsp+0E80h+var_E28], rax
0x180033fe3  lea     rax, [rsp+0E80h+var_E50]
0x180033fe8  mov     [rbp+0D80h+var_9D0], rax
0x180033fef  mov     rax, [rbp+0D80h+arg_28]
0x180033ff6  mov     [rsp+0E80h+var_E18], rax
0x180033ffb  mov     [rsp+0E80h+var_E10], r13d
0x180034000  mov     [rsp+0E80h+var_E0C], r13b
0x180034005  mov     [rsp+0E80h+var_E08], r13
0x18003400a  mov     [rbp+0D80h+var_E00], r13d
0x18003400e  mov     [rbp+0D80h+var_DF8], r13b
0x180034012  mov     [rbp+0D80h+var_DF6], r13w
0x180034017  mov     [rbp+0D80h+var_DE8], r13d
0x18003401b  mov     [rbp+0D80h+var_DE4], r13b
0x18003401f  movdqa  xmmword ptr [rbp+0D80h+Block], xmm0
0x180034027  mov     [rsp+0E80h+var_E30], r12
0x18003402c  mov     [rsp+0E80h+var_E20], r9
0x180034031  mov     [rbp+0D80h+var_9C8], r13d
0x180034038  mov     [rbp+0D80h+var_9C0], r13
0x18003403f  mov     [rbp+0D80h+var_9B8], r9
0x180034046  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(void)
0x18003404b  movsxd  rbx, eax
0x18003404e  test    rsi, rsi
0x180034051  jz      short loc_18003409F
0x180034053  test    r12b, 1
0x180034057  jz      short loc_18003407C
0x180034059  test    rdi, rdi
0x18003405c  jnz     short loc_180034067
0x18003405e  test    eax, eax
0x180034060  jz      short loc_180034067
0x180034062  or      ebx, 0FFFFFFFFh
0x180034065  jmp     short loc_18003409F
0x180034067  mov     rax, [rsp+0E80h+var_E40]
0x18003406c  cmp     rax, rdi
0x18003406f  jnz     short loc_18003409A
0x180034071  test    ebx, ebx
0x180034073  js      short loc_18003409F
0x180034075  cmp     rbx, rdi
0x180034078  jbe     short loc_18003409F
0x18003407a  jmp     short loc_180034062
0x18003407c  test    r15, r15
0x18003407f  jz      short loc_1800340CE
0x180034081  test    rdi, rdi
0x180034084  jz      short loc_18003409F
0x180034086  test    eax, eax
0x180034088  jns     short loc_180034090
0x18003408a  mov     [rsi], r13w
0x18003408e  jmp     short loc_18003409F
0x180034090  mov     rax, [rsp+0E80h+var_E40]
0x180034095  cmp     rax, rdi
0x180034098  jz      short loc_1800340E2
0x18003409a  mov     [rsi+rax*2], r13w
0x18003409f  mov     rcx, [rbp+0D80h+Block+8]; Block
0x1800340a6  call    _free_base
0x1800340ab  mov     eax, ebx
0x1800340ad  mov     rcx, [rbp+0D80h+var_40]
0x1800340b4  xor     rcx, rsp; StackCookie
0x1800340b7  call    __security_check_cookie
0x1800340bc  add     rsp, 0E50h
0x1800340c3  pop     r15
0x1800340c5  pop     r13
0x1800340c7  pop     r12
0x1800340c9  pop     rdi
0x1800340ca  pop     rsi
0x1800340cb  pop     rbx
0x1800340cc  pop     rbp
0x1800340cd  retn
0x1800340ce  test    rdi, rdi
0x1800340d1  jz      short loc_180034062
0x1800340d3  mov     rax, [rsp+0E80h+var_E40]
0x1800340d8  cmp     rax, rdi
0x1800340db  jnz     short loc_18003409A
0x1800340dd  mov     ebx, 0FFFFFFFEh
0x1800340e2  mov     [rsi+rdi*2-2], r13w
0x1800340e8  jmp     short loc_18003409F
```
