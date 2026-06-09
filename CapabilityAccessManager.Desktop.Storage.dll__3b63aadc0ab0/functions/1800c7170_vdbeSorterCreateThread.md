# vdbeSorterCreateThread

- ea: `0x1800c7170`
- end: `0x1800c726f`
- name: `vdbeSorterCreateThread`
- size: `255`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800c5c90`
- `0x1800c65c0`
- `0x1800c7340`
- `0x1800c7f50`

## callees

- `0x180088560`
- `0x1800c7170`
- `0x18010d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800c720c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800c720c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c723f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c723f`

## pseudocode

```c
__int64 __fastcall vdbeSorterCreateThread(__int64 **a1, __int64 (__fastcall *a2)(__int64), __int64 a3)
{
  __int64 *v6; // rbx
  __int64 result; // rax
  DWORD *v8; // rsi
  _QWORD *v9; // rdi
  __int64 v10; // rax

  *a1 = 0;
  v6 = (__int64 *)sqlite3Malloc(40);
  if ( !v6 )
    return 7;
  if ( !(_BYTE)word_18013C1B4 || qword_18013C340 && (unsigned int)qword_18013C340(200) )
  {
    v9 = v6 + 2;
    v8 = (DWORD *)(v6 + 1);
  }
  else
  {
    v8 = (DWORD *)(v6 + 1);
    v6[2] = (__int64)a2;
    v9 = v6 + 2;
    v6[3] = a3;
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
  result = 0;
  *a1 = v6;
  return result;
}

```

## disassembly

```asm
0x1800c7170  mov     [rsp+arg_10], rbx
0x1800c7175  push    rbp
0x1800c7176  push    r14
0x1800c7178  push    r15
0x1800c717a  sub     rsp, 30h
0x1800c717e  mov     r14, rcx
0x1800c7181  mov     qword ptr [rcx], 0
0x1800c7188  mov     ecx, 28h ; '('
0x1800c718d  mov     rbp, r8
0x1800c7190  mov     r15, rdx
0x1800c7193  call    sqlite3Malloc
0x1800c7198  mov     rbx, rax
0x1800c719b  test    rax, rax
0x1800c719e  jnz     short loc_1800C71B4
0x1800c71a0  mov     eax, 7
0x1800c71a5  mov     rbx, [rsp+48h+arg_10]
0x1800c71aa  add     rsp, 30h
0x1800c71ae  pop     r15
0x1800c71b0  pop     r14
0x1800c71b2  pop     rbp
0x1800c71b3  retn
0x1800c71b4  cmp     byte ptr cs:word_18013C1B4, 0
0x1800c71bb  mov     [rsp+48h+arg_0], rsi
0x1800c71c0  mov     [rsp+48h+arg_8], rdi
0x1800c71c5  jz      short loc_1800C721C
0x1800c71c7  mov     rax, cs:qword_18013C340
0x1800c71ce  test    rax, rax
0x1800c71d1  jz      short loc_1800C71E1
0x1800c71d3  mov     ecx, 0C8h
0x1800c71d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c71dd  test    eax, eax
0x1800c71df  jnz     short loc_1800C721C
0x1800c71e1  lea     rsi, [rbx+8]
0x1800c71e5  mov     [rbx+10h], r15
0x1800c71e9  lea     rdi, [rbx+10h]
0x1800c71ed  mov     [rsp+48h+var_20], rsi
0x1800c71f2  mov     r9, rbx
0x1800c71f5  mov     [rsp+48h+var_28], 0
0x1800c71fd  lea     r8, sqlite3ThreadProc
0x1800c7204  mov     [rbx+18h], rbp
0x1800c7208  xor     edx, edx
0x1800c720a  xor     ecx, ecx
0x1800c720c  call    cs:__imp__o__beginthreadex
0x1800c7212  mov     [rbx], rax
0x1800c7215  test    rax, rax
0x1800c7218  jz      short loc_1800C7224
0x1800c721a  jmp     short loc_1800C7234
0x1800c721c  lea     rdi, [rbx+10h]
0x1800c7220  lea     rsi, [rbx+8]
0x1800c7224  xorps   xmm0, xmm0
0x1800c7227  xor     eax, eax
0x1800c7229  movups  xmmword ptr [rbx], xmm0
0x1800c722c  movups  xmmword ptr [rbx+10h], xmm0
0x1800c7230  mov     [rbx+20h], rax
0x1800c7234  cmp     qword ptr [rdi], 0
0x1800c7238  mov     rdi, [rsp+48h+arg_8]
0x1800c723d  jnz     short loc_1800C7256
0x1800c723f  call    cs:__imp_GetCurrentThreadId
0x1800c7245  mov     [rsi], eax
0x1800c7247  mov     rcx, rbp
0x1800c724a  mov     rax, r15
0x1800c724d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7252  mov     [rbx+20h], rax
0x1800c7256  mov     rsi, [rsp+48h+arg_0]
0x1800c725b  xor     eax, eax
0x1800c725d  mov     [r14], rbx
0x1800c7260  mov     rbx, [rsp+48h+arg_10]
0x1800c7265  add     rsp, 30h
0x1800c7269  pop     r15
0x1800c726b  pop     r14
0x1800c726d  pop     rbp
0x1800c726e  retn
```
