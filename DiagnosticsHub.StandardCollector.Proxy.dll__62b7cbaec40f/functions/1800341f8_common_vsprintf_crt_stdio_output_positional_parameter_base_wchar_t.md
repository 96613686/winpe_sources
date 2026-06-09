# common_vsprintf___crt_stdio_output::positional_parameter_base_wchar_t_

- ea: `0x1800341f8`
- end: `0x1800343ca`
- name: `common_vsprintf___crt_stdio_output::positional_parameter_base_wchar_t_`
- size: `466`
- prototype: `__int64 __fastcall(int, int, int, int, __crt_cached_ptd_host *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180056f4c`

## callees

- `0x180002810`
- `0x180007b48`
- `0x180008040`
- `0x1800341f8`
- `0x180045bbc`

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
0x1800341f8  push    rbp
0x1800341fa  push    rbx
0x1800341fb  push    rsi
0x1800341fc  push    rdi
0x1800341fd  push    r12
0x1800341ff  push    r13
0x180034201  push    r15
0x180034203  lea     rbp, [rsp-0D50h]
0x18003420b  sub     rsp, 0E50h
0x180034212  mov     rax, cs:__security_cookie
0x180034219  xor     rax, rsp
0x18003421c  mov     [rbp+0D80h+var_40], rax
0x180034223  mov     rax, [rbp+0D80h+arg_20]
0x18003422a  xor     r13d, r13d
0x18003422d  mov     rdi, r8
0x180034230  mov     rsi, rdx
0x180034233  mov     r12, rcx
0x180034236  test    r9, r9
0x180034239  jnz     short loc_180034267
0x18003423b  mov     byte ptr [rax+30h], 1
0x18003423f  xor     r9d, r9d; LineNo
0x180034242  mov     [rsp+0E80h+var_E58], rax; __crt_cached_ptd_host *
0x180034247  xor     r8d, r8d; FileName
0x18003424a  xor     edx, edx; FunctionName
0x18003424c  mov     dword ptr [rax+2Ch], 16h
0x180034253  xor     ecx, ecx; Expression
0x180034255  mov     [rsp+0E80h+var_E60], r13; uintptr_t
0x18003425a  call    _invalid_parameter_internal
0x18003425f  or      eax, 0FFFFFFFFh
0x180034262  jmp     loc_18003438D
0x180034267  test    rdi, rdi
0x18003426a  jz      short loc_180034271
0x18003426c  test    rsi, rsi
0x18003426f  jz      short loc_18003423B
0x180034271  mov     r15, r12
0x180034274  mov     [rsp+0E80h+var_E37], r13d
0x180034279  mov     [rsp+0E80h+var_E33], r13w
0x18003427f  mov     [rsp+0E80h+var_E31], r13b
0x180034284  mov     [rsp+0E80h+var_E50], rsi
0x180034289  mov     [rsp+0E80h+var_E48], rdi
0x18003428e  mov     [rsp+0E80h+var_E40], r13
0x180034293  and     r15d, 2
0x180034297  jnz     short loc_1800342A3
0x180034299  mov     [rsp+0E80h+var_E38], r13b
0x18003429e  test    rsi, rsi
0x1800342a1  jnz     short loc_1800342A8
0x1800342a3  mov     [rsp+0E80h+var_E38], 1
0x1800342a8  or      [rbp+0D80h+var_50], 0FFFFFFFFh
0x1800342af  lea     rcx, [rsp+0E80h+var_E30]
0x1800342b4  or      [rbp+0D80h+var_4C], 0FFFFFFFFh
0x1800342bb  xorps   xmm0, xmm0
0x1800342be  mov     [rsp+0E80h+var_E28], rax
0x1800342c3  lea     rax, [rsp+0E80h+var_E50]
0x1800342c8  mov     [rbp+0D80h+var_9D0], rax
0x1800342cf  mov     rax, [rbp+0D80h+arg_28]
0x1800342d6  mov     [rsp+0E80h+var_E18], rax
0x1800342db  mov     [rsp+0E80h+var_E10], r13d
0x1800342e0  mov     [rsp+0E80h+var_E0C], r13b
0x1800342e5  mov     [rsp+0E80h+var_E08], r13
0x1800342ea  mov     [rbp+0D80h+var_E00], r13d
0x1800342ee  mov     [rbp+0D80h+var_DF8], r13b
0x1800342f2  mov     [rbp+0D80h+var_DF6], r13w
0x1800342f7  mov     [rbp+0D80h+var_DE8], r13d
0x1800342fb  mov     [rbp+0D80h+var_DE4], r13b
0x1800342ff  movdqa  xmmword ptr [rbp+0D80h+Block], xmm0
0x180034307  mov     [rsp+0E80h+var_E30], r12
0x18003430c  mov     [rsp+0E80h+var_E20], r9
0x180034311  mov     [rbp+0D80h+var_9C8], r13d
0x180034318  mov     [rbp+0D80h+var_9C0], r13
0x18003431f  mov     [rbp+0D80h+var_9B8], r9
0x180034326  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(void)
0x18003432b  movsxd  rbx, eax
0x18003432e  test    rsi, rsi
0x180034331  jz      short loc_18003437F
0x180034333  test    r12b, 1
0x180034337  jz      short loc_18003435C
0x180034339  test    rdi, rdi
0x18003433c  jnz     short loc_180034347
0x18003433e  test    eax, eax
0x180034340  jz      short loc_180034347
0x180034342  or      ebx, 0FFFFFFFFh
0x180034345  jmp     short loc_18003437F
0x180034347  mov     rax, [rsp+0E80h+var_E40]
0x18003434c  cmp     rax, rdi
0x18003434f  jnz     short loc_18003437A
0x180034351  test    ebx, ebx
0x180034353  js      short loc_18003437F
0x180034355  cmp     rbx, rdi
0x180034358  jbe     short loc_18003437F
0x18003435a  jmp     short loc_180034342
0x18003435c  test    r15, r15
0x18003435f  jz      short loc_1800343AE
0x180034361  test    rdi, rdi
0x180034364  jz      short loc_18003437F
0x180034366  test    eax, eax
0x180034368  jns     short loc_180034370
0x18003436a  mov     [rsi], r13w
0x18003436e  jmp     short loc_18003437F
0x180034370  mov     rax, [rsp+0E80h+var_E40]
0x180034375  cmp     rax, rdi
0x180034378  jz      short loc_1800343C2
0x18003437a  mov     [rsi+rax*2], r13w
0x18003437f  mov     rcx, [rbp+0D80h+Block+8]; Block
0x180034386  call    _free_base
0x18003438b  mov     eax, ebx
0x18003438d  mov     rcx, [rbp+0D80h+var_40]
0x180034394  xor     rcx, rsp; StackCookie
0x180034397  call    __security_check_cookie
0x18003439c  add     rsp, 0E50h
0x1800343a3  pop     r15
0x1800343a5  pop     r13
0x1800343a7  pop     r12
0x1800343a9  pop     rdi
0x1800343aa  pop     rsi
0x1800343ab  pop     rbx
0x1800343ac  pop     rbp
0x1800343ad  retn
0x1800343ae  test    rdi, rdi
0x1800343b1  jz      short loc_180034342
0x1800343b3  mov     rax, [rsp+0E80h+var_E40]
0x1800343b8  cmp     rax, rdi
0x1800343bb  jnz     short loc_18003437A
0x1800343bd  mov     ebx, 0FFFFFFFEh
0x1800343c2  mov     [rsi+rdi*2-2], r13w
0x1800343c8  jmp     short loc_18003437F
```
