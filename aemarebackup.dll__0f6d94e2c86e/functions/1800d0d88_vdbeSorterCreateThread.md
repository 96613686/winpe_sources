# vdbeSorterCreateThread

- ea: `0x1800d0d88`
- end: `0x1800d0e63`
- name: `vdbeSorterCreateThread`
- size: `219`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800cfa18`
- `0x1800d01fc`
- `0x1800d0f24`
- `0x1800d1638`

## callees

- `0x18009d49c`
- `0x1800d0d88`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800d0e0c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800d0e0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0e3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0e3a`

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
  if ( !(_BYTE)word_180119F84 || qword_18011A110 && (unsigned int)qword_18011A110(200) )
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
0x1800d0d88  push    rbx
0x1800d0d8a  push    rbp
0x1800d0d8b  push    rsi
0x1800d0d8c  push    rdi
0x1800d0d8d  push    r14
0x1800d0d8f  push    r15
0x1800d0d91  sub     rsp, 38h
0x1800d0d95  mov     r14, rcx
0x1800d0d98  mov     qword ptr [rcx], 0
0x1800d0d9f  mov     ecx, 28h ; '('
0x1800d0da4  mov     rbp, r8
0x1800d0da7  mov     r15, rdx
0x1800d0daa  call    sqlite3Malloc
0x1800d0daf  mov     rbx, rax
0x1800d0db2  test    rax, rax
0x1800d0db5  jnz     short loc_1800D0DBF
0x1800d0db7  lea     eax, [rbx+7]
0x1800d0dba  jmp     loc_1800D0E56
0x1800d0dbf  cmp     byte ptr cs:word_180119F84, 0
0x1800d0dc6  jz      short loc_1800D0E1C
0x1800d0dc8  mov     rax, cs:qword_18011A110
0x1800d0dcf  test    rax, rax
0x1800d0dd2  jz      short loc_1800D0DE2
0x1800d0dd4  mov     ecx, 0C8h
0x1800d0dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0dde  test    eax, eax
0x1800d0de0  jnz     short loc_1800D0E1C
0x1800d0de2  lea     rsi, [rbx+8]
0x1800d0de6  mov     [rbx+18h], rbp
0x1800d0dea  lea     rdi, [rbx+10h]
0x1800d0dee  mov     [rsp+68h+var_40], rsi
0x1800d0df3  mov     r9, rbx
0x1800d0df6  mov     [rsp+68h+var_48], 0
0x1800d0dfe  lea     r8, sqlite3ThreadProc
0x1800d0e05  mov     [rdi], r15
0x1800d0e08  xor     edx, edx
0x1800d0e0a  xor     ecx, ecx
0x1800d0e0c  call    cs:__imp__o__beginthreadex
0x1800d0e12  mov     [rbx], rax
0x1800d0e15  test    rax, rax
0x1800d0e18  jz      short loc_1800D0E24
0x1800d0e1a  jmp     short loc_1800D0E34
0x1800d0e1c  lea     rdi, [rbx+10h]
0x1800d0e20  lea     rsi, [rbx+8]
0x1800d0e24  xorps   xmm0, xmm0
0x1800d0e27  xor     eax, eax
0x1800d0e29  movups  xmmword ptr [rbx], xmm0
0x1800d0e2c  movups  xmmword ptr [rbx+10h], xmm0
0x1800d0e30  mov     [rbx+20h], rax
0x1800d0e34  cmp     qword ptr [rdi], 0
0x1800d0e38  jnz     short loc_1800D0E51
0x1800d0e3a  call    cs:__imp_GetCurrentThreadId
0x1800d0e40  mov     [rsi], eax
0x1800d0e42  mov     rcx, rbp
0x1800d0e45  mov     rax, r15
0x1800d0e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0e4d  mov     [rbx+20h], rax
0x1800d0e51  mov     [r14], rbx
0x1800d0e54  xor     eax, eax
0x1800d0e56  add     rsp, 38h
0x1800d0e5a  pop     r15
0x1800d0e5c  pop     r14
0x1800d0e5e  pop     rdi
0x1800d0e5f  pop     rsi
0x1800d0e60  pop     rbp
0x1800d0e61  pop     rbx
0x1800d0e62  retn
```
