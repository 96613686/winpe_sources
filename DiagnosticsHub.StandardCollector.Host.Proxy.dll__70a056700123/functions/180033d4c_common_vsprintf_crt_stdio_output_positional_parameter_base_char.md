# common_vsprintf___crt_stdio_output::positional_parameter_base_char_

- ea: `0x180033d4c`
- end: `0x180033f17`
- name: `common_vsprintf___crt_stdio_output::positional_parameter_base_char_`
- size: `459`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180056844`

## callees

- `0x1800073e8`
- `0x1800078e0`
- `0x180032370`
- `0x180033d4c`
- `0x1800445d0`

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
0x180033d4c  push    rbp
0x180033d4e  push    rbx
0x180033d4f  push    rsi
0x180033d50  push    rdi
0x180033d51  push    r12
0x180033d53  push    r13
0x180033d55  push    r15
0x180033d57  lea     rbp, [rsp-0D50h]
0x180033d5f  sub     rsp, 0E50h
0x180033d66  mov     rax, cs:__security_cookie
0x180033d6d  xor     rax, rsp
0x180033d70  mov     [rbp+0D80h+var_40], rax
0x180033d77  mov     rax, [rbp+0D80h+arg_20]
0x180033d7e  xor     r13d, r13d
0x180033d81  mov     rdi, r8
0x180033d84  mov     rsi, rdx
0x180033d87  mov     r12, rcx
0x180033d8a  test    r9, r9
0x180033d8d  jnz     short loc_180033DBB
0x180033d8f  mov     byte ptr [rax+30h], 1
0x180033d93  xor     r9d, r9d; LineNo
0x180033d96  mov     [rsp+0E80h+var_E58], rax; __crt_cached_ptd_host *
0x180033d9b  xor     r8d, r8d; FileName
0x180033d9e  xor     edx, edx; FunctionName
0x180033da0  mov     dword ptr [rax+2Ch], 16h
0x180033da7  xor     ecx, ecx; Expression
0x180033da9  mov     [rsp+0E80h+var_E60], r13; uintptr_t
0x180033dae  call    _invalid_parameter_internal
0x180033db3  or      eax, 0FFFFFFFFh
0x180033db6  jmp     loc_180033EDB
0x180033dbb  test    rdi, rdi
0x180033dbe  jz      short loc_180033DC5
0x180033dc0  test    rsi, rsi
0x180033dc3  jz      short loc_180033D8F
0x180033dc5  mov     r15, r12
0x180033dc8  mov     [rsp+0E80h+var_E37], r13d
0x180033dcd  mov     [rsp+0E80h+var_E33], r13w
0x180033dd3  mov     [rsp+0E80h+var_E31], r13b
0x180033dd8  mov     [rsp+0E80h+var_E50], rsi
0x180033ddd  mov     [rsp+0E80h+var_E48], rdi
0x180033de2  mov     [rsp+0E80h+var_E40], r13
0x180033de7  and     r15d, 2
0x180033deb  jnz     short loc_180033DF7
0x180033ded  mov     [rsp+0E80h+var_E38], r13b
0x180033df2  test    rsi, rsi
0x180033df5  jnz     short loc_180033DFC
0x180033df7  mov     [rsp+0E80h+var_E38], 1
0x180033dfc  or      [rbp+0D80h+var_50], 0FFFFFFFFh
0x180033e03  lea     rcx, [rsp+0E80h+var_E30]
0x180033e08  or      [rbp+0D80h+var_4C], 0FFFFFFFFh
0x180033e0f  xorps   xmm0, xmm0
0x180033e12  mov     [rsp+0E80h+var_E28], rax
0x180033e17  lea     rax, [rsp+0E80h+var_E50]
0x180033e1c  mov     [rbp+0D80h+var_9D0], rax
0x180033e23  mov     rax, [rbp+0D80h+arg_28]
0x180033e2a  mov     [rsp+0E80h+var_E18], rax
0x180033e2f  mov     [rsp+0E80h+var_E10], r13d
0x180033e34  mov     [rsp+0E80h+var_E0C], r13b
0x180033e39  mov     [rsp+0E80h+var_E08], r13
0x180033e3e  mov     [rbp+0D80h+var_E00], r13d
0x180033e42  mov     [rbp+0D80h+var_DF8], r13w
0x180033e47  mov     [rbp+0D80h+var_DE8], r13d
0x180033e4b  mov     [rbp+0D80h+var_DE4], r13b
0x180033e4f  movdqa  xmmword ptr [rbp+0D80h+Block], xmm0
0x180033e57  mov     [rsp+0E80h+var_E30], r12
0x180033e5c  mov     [rsp+0E80h+var_E20], r9
0x180033e61  mov     [rbp+0D80h+var_9C8], r13d
0x180033e68  mov     [rbp+0D80h+var_9C0], r13
0x180033e6f  mov     [rbp+0D80h+var_9B8], r9
0x180033e76  call    ?process@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(void)
0x180033e7b  movsxd  rbx, eax
0x180033e7e  test    rsi, rsi
0x180033e81  jz      short loc_180033ECD
0x180033e83  test    r12b, 1
0x180033e87  jz      short loc_180033EAC
0x180033e89  test    rdi, rdi
0x180033e8c  jnz     short loc_180033E97
0x180033e8e  test    eax, eax
0x180033e90  jz      short loc_180033E97
0x180033e92  or      ebx, 0FFFFFFFFh
0x180033e95  jmp     short loc_180033ECD
0x180033e97  mov     rax, [rsp+0E80h+var_E40]
0x180033e9c  cmp     rax, rdi
0x180033e9f  jnz     short loc_180033EC9
0x180033ea1  test    ebx, ebx
0x180033ea3  js      short loc_180033ECD
0x180033ea5  cmp     rbx, rdi
0x180033ea8  jbe     short loc_180033ECD
0x180033eaa  jmp     short loc_180033E92
0x180033eac  test    r15, r15
0x180033eaf  jz      short loc_180033EFC
0x180033eb1  test    rdi, rdi
0x180033eb4  jz      short loc_180033ECD
0x180033eb6  test    eax, eax
0x180033eb8  jns     short loc_180033EBF
0x180033eba  mov     [rsi], r13b
0x180033ebd  jmp     short loc_180033ECD
0x180033ebf  mov     rax, [rsp+0E80h+var_E40]
0x180033ec4  cmp     rax, rdi
0x180033ec7  jz      short loc_180033F10
0x180033ec9  mov     [rsi+rax], r13b
0x180033ecd  mov     rcx, [rbp+0D80h+Block+8]; Block
0x180033ed4  call    _free_base
0x180033ed9  mov     eax, ebx
0x180033edb  mov     rcx, [rbp+0D80h+var_40]
0x180033ee2  xor     rcx, rsp; StackCookie
0x180033ee5  call    __security_check_cookie
0x180033eea  add     rsp, 0E50h
0x180033ef1  pop     r15
0x180033ef3  pop     r13
0x180033ef5  pop     r12
0x180033ef7  pop     rdi
0x180033ef8  pop     rsi
0x180033ef9  pop     rbx
0x180033efa  pop     rbp
0x180033efb  retn
0x180033efc  test    rdi, rdi
0x180033eff  jz      short loc_180033E92
0x180033f01  mov     rax, [rsp+0E80h+var_E40]
0x180033f06  cmp     rax, rdi
0x180033f09  jnz     short loc_180033EC9
0x180033f0b  mov     ebx, 0FFFFFFFEh
0x180033f10  mov     [rsi+rdi-1], r13b
0x180033f15  jmp     short loc_180033ECD
```
