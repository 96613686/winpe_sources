# common_vsprintf___crt_stdio_output::standard_base_wchar_t_

- ea: `0x18003457c`
- end: `0x180034732`
- name: `common_vsprintf___crt_stdio_output::standard_base_wchar_t_`
- size: `438`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002810`
- `0x180007b48`
- `0x180008040`
- `0x18003457c`
- `0x180045f1c`

## pseudocode

```c
__int64 __fastcall common_vsprintf___crt_stdio_output::standard_base_wchar_t_(
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
  v10 = __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(v19);
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
0x18003457c  push    rbp
0x18003457e  push    rbx
0x18003457f  push    rsi
0x180034580  push    rdi
0x180034581  push    r12
0x180034583  push    r14
0x180034585  push    r15
0x180034587  lea     rbp, [rsp-3D0h]
0x18003458f  sub     rsp, 4D0h
0x180034596  mov     rax, cs:__security_cookie
0x18003459d  xor     rax, rsp
0x1800345a0  mov     [rbp+400h+var_40], rax
0x1800345a7  mov     rax, [rbp+400h+arg_20]
0x1800345ae  xor     r12d, r12d
0x1800345b1  mov     rdi, r8
0x1800345b4  mov     rsi, rdx
0x1800345b7  mov     r15, rcx
0x1800345ba  test    r9, r9
0x1800345bd  jnz     short loc_1800345EB
0x1800345bf  mov     byte ptr [rax+30h], 1
0x1800345c3  xor     r9d, r9d; LineNo
0x1800345c6  mov     [rsp+500h+var_4D8], rax; __crt_cached_ptd_host *
0x1800345cb  xor     r8d, r8d; FileName
0x1800345ce  xor     edx, edx; FunctionName
0x1800345d0  mov     dword ptr [rax+2Ch], 16h
0x1800345d7  xor     ecx, ecx; Expression
0x1800345d9  mov     [rsp+500h+var_4E0], r12; uintptr_t
0x1800345de  call    _invalid_parameter_internal
0x1800345e3  or      eax, 0FFFFFFFFh
0x1800345e6  jmp     loc_1800346F5
0x1800345eb  test    rdi, rdi
0x1800345ee  jz      short loc_1800345F5
0x1800345f0  test    rsi, rsi
0x1800345f3  jz      short loc_1800345BF
0x1800345f5  mov     r14, r15
0x1800345f8  mov     [rsp+500h+var_4B7], r12d
0x1800345fd  mov     [rsp+500h+var_4B3], r12w
0x180034603  mov     [rsp+500h+var_4B1], r12b
0x180034608  mov     [rsp+500h+var_4D0], rsi
0x18003460d  mov     [rsp+500h+var_4C8], rdi
0x180034612  mov     [rsp+500h+var_4C0], r12
0x180034617  and     r14d, 2
0x18003461b  jnz     short loc_180034627
0x18003461d  mov     [rsp+500h+var_4B8], r12b
0x180034622  test    rsi, rsi
0x180034625  jnz     short loc_18003462C
0x180034627  mov     [rsp+500h+var_4B8], 1
0x18003462c  mov     [rsp+500h+var_4A8], rax
0x180034631  lea     rcx, [rsp+500h+var_4B0]
0x180034636  lea     rax, [rsp+500h+var_4D0]
0x18003463b  mov     [rsp+500h+var_490], r12d
0x180034640  mov     [rbp+400h+var_50], rax
0x180034647  xorps   xmm0, xmm0
0x18003464a  mov     rax, [rbp+400h+arg_28]
0x180034651  mov     [rsp+500h+var_498], rax
0x180034656  mov     [rsp+500h+var_48C], r12b
0x18003465b  mov     [rsp+500h+var_488], r12
0x180034660  mov     [rbp+400h+var_480], r12d
0x180034664  mov     [rbp+400h+var_478], r12b
0x180034668  mov     [rbp+400h+var_476], r12w
0x18003466d  mov     [rbp+400h+var_468], r12d
0x180034671  mov     [rbp+400h+var_464], r12b
0x180034675  movdqa  xmmword ptr [rbp+400h+Block], xmm0
0x18003467d  mov     [rsp+500h+var_4B0], r15
0x180034682  mov     [rsp+500h+var_4A0], r9
0x180034687  mov     [rbp+400h+var_48], r12d
0x18003468e  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(void)
0x180034693  movsxd  rbx, eax
0x180034696  test    rsi, rsi
0x180034699  jz      short loc_1800346E7
0x18003469b  test    r15b, 1
0x18003469f  jz      short loc_1800346C4
0x1800346a1  test    rdi, rdi
0x1800346a4  jnz     short loc_1800346AF
0x1800346a6  test    eax, eax
0x1800346a8  jz      short loc_1800346AF
0x1800346aa  or      ebx, 0FFFFFFFFh
0x1800346ad  jmp     short loc_1800346E7
0x1800346af  mov     rax, [rsp+500h+var_4C0]
0x1800346b4  cmp     rax, rdi
0x1800346b7  jnz     short loc_1800346E2
0x1800346b9  test    ebx, ebx
0x1800346bb  js      short loc_1800346E7
0x1800346bd  cmp     rbx, rdi
0x1800346c0  jbe     short loc_1800346E7
0x1800346c2  jmp     short loc_1800346AA
0x1800346c4  test    r14, r14
0x1800346c7  jz      short loc_180034716
0x1800346c9  test    rdi, rdi
0x1800346cc  jz      short loc_1800346E7
0x1800346ce  test    eax, eax
0x1800346d0  jns     short loc_1800346D8
0x1800346d2  mov     [rsi], r12w
0x1800346d6  jmp     short loc_1800346E7
0x1800346d8  mov     rax, [rsp+500h+var_4C0]
0x1800346dd  cmp     rax, rdi
0x1800346e0  jz      short loc_18003472A
0x1800346e2  mov     [rsi+rax*2], r12w
0x1800346e7  mov     rcx, [rbp+400h+Block+8]; Block
0x1800346ee  call    _free_base
0x1800346f3  mov     eax, ebx
0x1800346f5  mov     rcx, [rbp+400h+var_40]
0x1800346fc  xor     rcx, rsp; StackCookie
0x1800346ff  call    __security_check_cookie
0x180034704  add     rsp, 4D0h
0x18003470b  pop     r15
0x18003470d  pop     r14
0x18003470f  pop     r12
0x180034711  pop     rdi
0x180034712  pop     rsi
0x180034713  pop     rbx
0x180034714  pop     rbp
0x180034715  retn
0x180034716  test    rdi, rdi
0x180034719  jz      short loc_1800346AA
0x18003471b  mov     rax, [rsp+500h+var_4C0]
0x180034720  cmp     rax, rdi
0x180034723  jnz     short loc_1800346E2
0x180034725  mov     ebx, 0FFFFFFFEh
0x18003472a  mov     [rsi+rdi*2-2], r12w
0x180034730  jmp     short loc_1800346E7
```
