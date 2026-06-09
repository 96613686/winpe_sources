# common_vsprintf___crt_stdio_output::standard_base_wchar_t_

- ea: `0x18003429c`
- end: `0x180034452`
- name: `common_vsprintf___crt_stdio_output::standard_base_wchar_t_`
- size: `438`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800073e8`
- `0x1800078e0`
- `0x180032370`
- `0x18003429c`
- `0x180045c3c`

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
0x18003429c  push    rbp
0x18003429e  push    rbx
0x18003429f  push    rsi
0x1800342a0  push    rdi
0x1800342a1  push    r12
0x1800342a3  push    r14
0x1800342a5  push    r15
0x1800342a7  lea     rbp, [rsp-3D0h]
0x1800342af  sub     rsp, 4D0h
0x1800342b6  mov     rax, cs:__security_cookie
0x1800342bd  xor     rax, rsp
0x1800342c0  mov     [rbp+400h+var_40], rax
0x1800342c7  mov     rax, [rbp+400h+arg_20]
0x1800342ce  xor     r12d, r12d
0x1800342d1  mov     rdi, r8
0x1800342d4  mov     rsi, rdx
0x1800342d7  mov     r15, rcx
0x1800342da  test    r9, r9
0x1800342dd  jnz     short loc_18003430B
0x1800342df  mov     byte ptr [rax+30h], 1
0x1800342e3  xor     r9d, r9d; LineNo
0x1800342e6  mov     [rsp+500h+var_4D8], rax; __crt_cached_ptd_host *
0x1800342eb  xor     r8d, r8d; FileName
0x1800342ee  xor     edx, edx; FunctionName
0x1800342f0  mov     dword ptr [rax+2Ch], 16h
0x1800342f7  xor     ecx, ecx; Expression
0x1800342f9  mov     [rsp+500h+var_4E0], r12; uintptr_t
0x1800342fe  call    _invalid_parameter_internal
0x180034303  or      eax, 0FFFFFFFFh
0x180034306  jmp     loc_180034415
0x18003430b  test    rdi, rdi
0x18003430e  jz      short loc_180034315
0x180034310  test    rsi, rsi
0x180034313  jz      short loc_1800342DF
0x180034315  mov     r14, r15
0x180034318  mov     [rsp+500h+var_4B7], r12d
0x18003431d  mov     [rsp+500h+var_4B3], r12w
0x180034323  mov     [rsp+500h+var_4B1], r12b
0x180034328  mov     [rsp+500h+var_4D0], rsi
0x18003432d  mov     [rsp+500h+var_4C8], rdi
0x180034332  mov     [rsp+500h+var_4C0], r12
0x180034337  and     r14d, 2
0x18003433b  jnz     short loc_180034347
0x18003433d  mov     [rsp+500h+var_4B8], r12b
0x180034342  test    rsi, rsi
0x180034345  jnz     short loc_18003434C
0x180034347  mov     [rsp+500h+var_4B8], 1
0x18003434c  mov     [rsp+500h+var_4A8], rax
0x180034351  lea     rcx, [rsp+500h+var_4B0]
0x180034356  lea     rax, [rsp+500h+var_4D0]
0x18003435b  mov     [rsp+500h+var_490], r12d
0x180034360  mov     [rbp+400h+var_50], rax
0x180034367  xorps   xmm0, xmm0
0x18003436a  mov     rax, [rbp+400h+arg_28]
0x180034371  mov     [rsp+500h+var_498], rax
0x180034376  mov     [rsp+500h+var_48C], r12b
0x18003437b  mov     [rsp+500h+var_488], r12
0x180034380  mov     [rbp+400h+var_480], r12d
0x180034384  mov     [rbp+400h+var_478], r12b
0x180034388  mov     [rbp+400h+var_476], r12w
0x18003438d  mov     [rbp+400h+var_468], r12d
0x180034391  mov     [rbp+400h+var_464], r12b
0x180034395  movdqa  xmmword ptr [rbp+400h+Block], xmm0
0x18003439d  mov     [rsp+500h+var_4B0], r15
0x1800343a2  mov     [rsp+500h+var_4A0], r9
0x1800343a7  mov     [rbp+400h+var_48], r12d
0x1800343ae  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(void)
0x1800343b3  movsxd  rbx, eax
0x1800343b6  test    rsi, rsi
0x1800343b9  jz      short loc_180034407
0x1800343bb  test    r15b, 1
0x1800343bf  jz      short loc_1800343E4
0x1800343c1  test    rdi, rdi
0x1800343c4  jnz     short loc_1800343CF
0x1800343c6  test    eax, eax
0x1800343c8  jz      short loc_1800343CF
0x1800343ca  or      ebx, 0FFFFFFFFh
0x1800343cd  jmp     short loc_180034407
0x1800343cf  mov     rax, [rsp+500h+var_4C0]
0x1800343d4  cmp     rax, rdi
0x1800343d7  jnz     short loc_180034402
0x1800343d9  test    ebx, ebx
0x1800343db  js      short loc_180034407
0x1800343dd  cmp     rbx, rdi
0x1800343e0  jbe     short loc_180034407
0x1800343e2  jmp     short loc_1800343CA
0x1800343e4  test    r14, r14
0x1800343e7  jz      short loc_180034436
0x1800343e9  test    rdi, rdi
0x1800343ec  jz      short loc_180034407
0x1800343ee  test    eax, eax
0x1800343f0  jns     short loc_1800343F8
0x1800343f2  mov     [rsi], r12w
0x1800343f6  jmp     short loc_180034407
0x1800343f8  mov     rax, [rsp+500h+var_4C0]
0x1800343fd  cmp     rax, rdi
0x180034400  jz      short loc_18003444A
0x180034402  mov     [rsi+rax*2], r12w
0x180034407  mov     rcx, [rbp+400h+Block+8]; Block
0x18003440e  call    _free_base
0x180034413  mov     eax, ebx
0x180034415  mov     rcx, [rbp+400h+var_40]
0x18003441c  xor     rcx, rsp; StackCookie
0x18003441f  call    __security_check_cookie
0x180034424  add     rsp, 4D0h
0x18003442b  pop     r15
0x18003442d  pop     r14
0x18003442f  pop     r12
0x180034431  pop     rdi
0x180034432  pop     rsi
0x180034433  pop     rbx
0x180034434  pop     rbp
0x180034435  retn
0x180034436  test    rdi, rdi
0x180034439  jz      short loc_1800343CA
0x18003443b  mov     rax, [rsp+500h+var_4C0]
0x180034440  cmp     rax, rdi
0x180034443  jnz     short loc_180034402
0x180034445  mov     ebx, 0FFFFFFFEh
0x18003444a  mov     [rsi+rdi*2-2], r12w
0x180034450  jmp     short loc_180034407
```
