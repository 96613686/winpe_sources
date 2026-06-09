# vdbeSorterCreateThread

- ea: `0x1800adc08`
- end: `0x1800adce3`
- name: `vdbeSorterCreateThread`
- size: `219`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800ac898`
- `0x1800ad07c`
- `0x1800adda4`
- `0x1800ae4b8`

## callees

- `0x18007a31c`
- `0x1800adc08`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800adc8c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800adc8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800adcba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800adcba`

## pseudocode

```c
__int64 __fastcall vdbeSorterCreateThread(__int64 **a1, __int64 (__fastcall *a2)(__int64), __int64 a3)
{
  __int64 *v6; // rbx
  DWORD *v8; // rsi
  _QWORD *v9; // rdi
  __int64 v10; // rax

  *a1 = 0;
  v6 = (__int64 *)sqlite3Malloc(40);
  if ( !v6 )
    return 7;
  if ( !(_BYTE)word_1800FE4B4 || qword_1800FE640 && (unsigned int)qword_1800FE640(200) )
  {
    v9 = v6 + 2;
    v8 = (DWORD *)(v6 + 1);
  }
  else
  {
    v8 = (DWORD *)(v6 + 1);
    v6[3] = a3;
    v9 = v6 + 2;
    v6[2] = (__int64)a2;
    v10 = _o__beginthreadex(0, 0, sqlite3ThreadProc, v6, 0, v6 + 1);
    *v6 = v10;
    if ( v10 )
      goto LABEL_10;
  }
  *(_OWORD *)v6 = 0;
  *((_OWORD *)v6 + 1) = 0;
  v6[4] = 0;
LABEL_10:
  if ( !*v9 )
  {
    *v8 = GetCurrentThreadId();
    v6[4] = a2(a3);
  }
  *a1 = v6;
  return 0;
}

```

## disassembly

```asm
0x1800adc08  push    rbx
0x1800adc0a  push    rbp
0x1800adc0b  push    rsi
0x1800adc0c  push    rdi
0x1800adc0d  push    r14
0x1800adc0f  push    r15
0x1800adc11  sub     rsp, 38h
0x1800adc15  mov     r14, rcx
0x1800adc18  mov     qword ptr [rcx], 0
0x1800adc1f  mov     ecx, 28h ; '('
0x1800adc24  mov     rbp, r8
0x1800adc27  mov     r15, rdx
0x1800adc2a  call    sqlite3Malloc
0x1800adc2f  mov     rbx, rax
0x1800adc32  test    rax, rax
0x1800adc35  jnz     short loc_1800ADC3F
0x1800adc37  lea     eax, [rbx+7]
0x1800adc3a  jmp     loc_1800ADCD6
0x1800adc3f  cmp     byte ptr cs:word_1800FE4B4, 0
0x1800adc46  jz      short loc_1800ADC9C
0x1800adc48  mov     rax, cs:qword_1800FE640
0x1800adc4f  test    rax, rax
0x1800adc52  jz      short loc_1800ADC62
0x1800adc54  mov     ecx, 0C8h
0x1800adc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc5e  test    eax, eax
0x1800adc60  jnz     short loc_1800ADC9C
0x1800adc62  lea     rsi, [rbx+8]
0x1800adc66  mov     [rbx+18h], rbp
0x1800adc6a  lea     rdi, [rbx+10h]
0x1800adc6e  mov     [rsp+68h+var_40], rsi
0x1800adc73  mov     r9, rbx
0x1800adc76  mov     [rsp+68h+var_48], 0
0x1800adc7e  lea     r8, sqlite3ThreadProc
0x1800adc85  mov     [rdi], r15
0x1800adc88  xor     edx, edx
0x1800adc8a  xor     ecx, ecx
0x1800adc8c  call    cs:__imp__o__beginthreadex
0x1800adc92  mov     [rbx], rax
0x1800adc95  test    rax, rax
0x1800adc98  jz      short loc_1800ADCA4
0x1800adc9a  jmp     short loc_1800ADCB4
0x1800adc9c  lea     rdi, [rbx+10h]
0x1800adca0  lea     rsi, [rbx+8]
0x1800adca4  xorps   xmm0, xmm0
0x1800adca7  xor     eax, eax
0x1800adca9  movups  xmmword ptr [rbx], xmm0
0x1800adcac  movups  xmmword ptr [rbx+10h], xmm0
0x1800adcb0  mov     [rbx+20h], rax
0x1800adcb4  cmp     qword ptr [rdi], 0
0x1800adcb8  jnz     short loc_1800ADCD1
0x1800adcba  call    cs:__imp_GetCurrentThreadId
0x1800adcc0  mov     [rsi], eax
0x1800adcc2  mov     rcx, rbp
0x1800adcc5  mov     rax, r15
0x1800adcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adccd  mov     [rbx+20h], rax
0x1800adcd1  mov     [r14], rbx
0x1800adcd4  xor     eax, eax
0x1800adcd6  add     rsp, 38h
0x1800adcda  pop     r15
0x1800adcdc  pop     r14
0x1800adcde  pop     rdi
0x1800adcdf  pop     rsi
0x1800adce0  pop     rbp
0x1800adce1  pop     rbx
0x1800adce2  retn
```
