# WPP_RECORDER_SF_Ds

- ea: `0x140005778`
- end: `0x1400058ea`
- name: `WPP_RECORDER_SF_Ds`
- size: `370`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140002e10`
- `0x14001abec`
- `0x14001e250`
- `0x14001f4f0`
- `0x14002ec90`
- `0x14002f228`
- `0x140033970`
- `0x14003d580`
- `0x14003daa4`

## callees

- `0x140005778`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400058cc`
- `WppRecorder!WppAutoLogTrace` at `0x1400058cc`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_Ds(
        __int64 a1,
        unsigned __int8 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        char a6,
        const char *a7)
{
  __int64 v7; // rdi
  unsigned __int64 v9; // rsi
  unsigned int v10; // r15d
  __int64 v11; // rbp
  const char *v13; // rbx
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  const char *v17; // rcx
  bool v18; // zf
  int v20; // [rsp+20h] [rbp-78h]
  __int64 v21; // [rsp+A0h] [rbp+8h]

  v21 = a1;
  v7 = -1;
  v9 = (unsigned __int64)a3 >> 16;
  v10 = a2;
  v11 = 5;
  v13 = a7;
  v14 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v9 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v14, ((_BYTE)a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v9 + 1) >= a2 )
  {
    if ( a7 )
    {
      v15 = -1;
      do
        ++v15;
      while ( a7[v15] );
      v16 = v15 + 1;
    }
    else
    {
      v16 = 5;
    }
    v17 = a7;
    if ( !a7 )
      v17 = "NULL";
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, const char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v9),
      43,
      a5,
      a4,
      &a6,
      4,
      v17,
      v16,
      0);
    a1 = v21;
  }
  v18 = v13 == 0;
  if ( v13 )
  {
    do
      ++v7;
    while ( v13[v7] );
    v11 = v7 + 1;
    v18 = v13 == 0;
  }
  if ( v18 )
    v13 = "NULL";
  LOWORD(v20) = a4;
  return WppAutoLogTrace(a1, v10, a3, a5, v20, &a6, 4, v13, v11, 0);
}

```

## disassembly

```asm
0x140005778  mov     [rsp+arg_0], rcx
0x14000577d  push    rbx
0x14000577e  push    rbp
0x14000577f  push    rsi
0x140005780  push    rdi
0x140005781  push    r12
0x140005783  push    r13
0x140005785  push    r14
0x140005787  push    r15
0x140005789  sub     rsp, 58h
0x14000578d  mov     r14, cs:WPP_GLOBAL_Control
0x140005794  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140005798  mov     r13d, r8d
0x14000579b  mov     esi, r8d
0x14000579e  lea     r8, aNull; "NULL"
0x1400057a5  shr     rsi, 10h
0x1400057a9  movzx   r15d, dl
0x1400057ad  lea     ebp, [rdi+6]
0x1400057b0  lea     ebx, [r13-1]
0x1400057b4  movzx   r12d, r9w
0x1400057b8  mov     r10d, ebx
0x1400057bb  and     ebx, 1Fh
0x1400057be  shr     r10, 5
0x1400057c2  lea     rax, [rsi+rsi*4]
0x1400057c6  and     r10d, 7FFh
0x1400057cd  mov     edx, ebx
0x1400057cf  mov     rbx, [rsp+98h+arg_30]
0x1400057d7  lea     r11, [r10+rax*4]
0x1400057db  mov     eax, [r14+r11*4+2Ch]
0x1400057e0  bt      eax, edx
0x1400057e3  jnb     loc_140005876
0x1400057e9  lea     r10, [rsi+rsi*4]
0x1400057ed  add     r10, r10
0x1400057f0  cmp     [r14+r10*8+29h], r15b
0x1400057f5  jb      short loc_140005876
0x1400057f7  mov     r11, cs:pfnWppTraceMessage
0x1400057fe  test    rbx, rbx
0x140005801  jz      short loc_140005814
0x140005803  mov     rax, rdi
0x140005806  inc     rax
0x140005809  cmp     byte ptr [rbx+rax], 0
0x14000580d  jnz     short loc_140005806
0x14000580f  inc     rax
0x140005812  jmp     short loc_140005817
0x140005814  mov     rax, rbp
0x140005817  mov     [rsp+98h+var_58], 0
0x140005820  test    rbx, rbx
0x140005823  mov     [rsp+98h+var_60], rax
0x140005828  mov     rcx, rbx
0x14000582b  cmovz   rcx, r8
0x14000582f  lea     rax, [rsp+98h+arg_28]
0x140005837  mov     r8, [rsp+98h+arg_20]
0x14000583f  mov     r9d, r12d
0x140005842  mov     [rsp+98h+var_68], rcx
0x140005847  mov     edx, 2Bh ; '+'
0x14000584c  mov     rcx, [r14+r10*8+18h]
0x140005851  mov     [rsp+98h+var_70], 4
0x14000585a  mov     [rsp+98h+var_78], rax
0x14000585f  mov     rax, r11
0x140005862  call    _guard_dispatch_icall
0x140005867  mov     rcx, [rsp+98h+arg_0]
0x14000586f  lea     r8, aNull; "NULL"
0x140005876  test    rbx, rbx
0x140005879  jz      short loc_14000588B
0x14000587b  inc     rdi
0x14000587e  cmp     byte ptr [rbx+rdi], 0
0x140005882  jnz     short loc_14000587B
0x140005884  lea     rbp, [rdi+1]
0x140005888  test    rbx, rbx
0x14000588b  mov     r9, [rsp+98h+arg_20]
0x140005893  lea     rax, [rsp+98h+arg_28]
0x14000589b  mov     [rsp+98h+var_50], 0
0x1400058a4  cmovz   rbx, r8
0x1400058a8  mov     [rsp+98h+var_58], rbp
0x1400058ad  mov     r8d, r13d
0x1400058b0  mov     [rsp+98h+var_60], rbx
0x1400058b5  mov     edx, r15d
0x1400058b8  mov     [rsp+98h+var_68], 4
0x1400058c1  mov     [rsp+98h+var_70], rax
0x1400058c6  mov     word ptr [rsp+98h+var_78], r12w
0x1400058cc  call    cs:__imp_WppAutoLogTrace
0x1400058d3  nop     dword ptr [rax+rax+00h]
0x1400058d8  add     rsp, 58h
0x1400058dc  pop     r15
0x1400058de  pop     r14
0x1400058e0  pop     r13
0x1400058e2  pop     r12
0x1400058e4  pop     rdi
0x1400058e5  pop     rsi
0x1400058e6  pop     rbp
0x1400058e7  pop     rbx
0x1400058e8  retn
```
