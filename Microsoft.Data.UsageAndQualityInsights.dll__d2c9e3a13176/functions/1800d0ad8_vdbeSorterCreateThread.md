# vdbeSorterCreateThread

- ea: `0x1800d0ad8`
- end: `0x1800d0bb3`
- name: `vdbeSorterCreateThread`
- size: `219`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800cf768`
- `0x1800cff4c`
- `0x1800d0c74`
- `0x1800d1390`

## callees

- `0x18009ba44`
- `0x1800d0ad8`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800d0b5c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800d0b5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0b8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0b8a`

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
  if ( !(_BYTE)word_1801592E4 || qword_180159470 && (unsigned int)qword_180159470(200) )
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
0x1800d0ad8  push    rbx
0x1800d0ada  push    rbp
0x1800d0adb  push    rsi
0x1800d0adc  push    rdi
0x1800d0add  push    r14
0x1800d0adf  push    r15
0x1800d0ae1  sub     rsp, 38h
0x1800d0ae5  mov     r14, rcx
0x1800d0ae8  mov     qword ptr [rcx], 0
0x1800d0aef  mov     ecx, 28h ; '('
0x1800d0af4  mov     rbp, r8
0x1800d0af7  mov     r15, rdx
0x1800d0afa  call    sqlite3Malloc
0x1800d0aff  mov     rbx, rax
0x1800d0b02  test    rax, rax
0x1800d0b05  jnz     short loc_1800D0B0F
0x1800d0b07  lea     eax, [rbx+7]
0x1800d0b0a  jmp     loc_1800D0BA6
0x1800d0b0f  cmp     byte ptr cs:word_1801592E4, 0
0x1800d0b16  jz      short loc_1800D0B6C
0x1800d0b18  mov     rax, cs:qword_180159470
0x1800d0b1f  test    rax, rax
0x1800d0b22  jz      short loc_1800D0B32
0x1800d0b24  mov     ecx, 0C8h
0x1800d0b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0b2e  test    eax, eax
0x1800d0b30  jnz     short loc_1800D0B6C
0x1800d0b32  lea     rsi, [rbx+8]
0x1800d0b36  mov     [rbx+18h], rbp
0x1800d0b3a  lea     rdi, [rbx+10h]
0x1800d0b3e  mov     [rsp+68h+var_40], rsi
0x1800d0b43  mov     r9, rbx
0x1800d0b46  mov     [rsp+68h+var_48], 0
0x1800d0b4e  lea     r8, sqlite3ThreadProc
0x1800d0b55  mov     [rdi], r15
0x1800d0b58  xor     edx, edx
0x1800d0b5a  xor     ecx, ecx
0x1800d0b5c  call    cs:__imp__o__beginthreadex
0x1800d0b62  mov     [rbx], rax
0x1800d0b65  test    rax, rax
0x1800d0b68  jz      short loc_1800D0B74
0x1800d0b6a  jmp     short loc_1800D0B84
0x1800d0b6c  lea     rdi, [rbx+10h]
0x1800d0b70  lea     rsi, [rbx+8]
0x1800d0b74  xorps   xmm0, xmm0
0x1800d0b77  xor     eax, eax
0x1800d0b79  movups  xmmword ptr [rbx], xmm0
0x1800d0b7c  movups  xmmword ptr [rbx+10h], xmm0
0x1800d0b80  mov     [rbx+20h], rax
0x1800d0b84  cmp     qword ptr [rdi], 0
0x1800d0b88  jnz     short loc_1800D0BA1
0x1800d0b8a  call    cs:__imp_GetCurrentThreadId
0x1800d0b90  mov     [rsi], eax
0x1800d0b92  mov     rcx, rbp
0x1800d0b95  mov     rax, r15
0x1800d0b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0b9d  mov     [rbx+20h], rax
0x1800d0ba1  mov     [r14], rbx
0x1800d0ba4  xor     eax, eax
0x1800d0ba6  add     rsp, 38h
0x1800d0baa  pop     r15
0x1800d0bac  pop     r14
0x1800d0bae  pop     rdi
0x1800d0baf  pop     rsi
0x1800d0bb0  pop     rbp
0x1800d0bb1  pop     rbx
0x1800d0bb2  retn
```
