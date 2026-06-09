# vdbeSorterCreateThread

- ea: `0x1800b5c28`
- end: `0x1800b5d03`
- name: `vdbeSorterCreateThread`
- size: `219`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800b48b8`
- `0x1800b509c`
- `0x1800b5dc4`
- `0x1800b64e0`

## callees

- `0x180080b94`
- `0x1800b5c28`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800b5cac`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800b5cac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b5cda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b5cda`

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
  if ( !(_BYTE)word_18010EE54 || qword_18010EFE0 && (unsigned int)qword_18010EFE0(200) )
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
0x1800b5c28  push    rbx
0x1800b5c2a  push    rbp
0x1800b5c2b  push    rsi
0x1800b5c2c  push    rdi
0x1800b5c2d  push    r14
0x1800b5c2f  push    r15
0x1800b5c31  sub     rsp, 38h
0x1800b5c35  mov     r14, rcx
0x1800b5c38  mov     qword ptr [rcx], 0
0x1800b5c3f  mov     ecx, 28h ; '('
0x1800b5c44  mov     rbp, r8
0x1800b5c47  mov     r15, rdx
0x1800b5c4a  call    sqlite3Malloc
0x1800b5c4f  mov     rbx, rax
0x1800b5c52  test    rax, rax
0x1800b5c55  jnz     short loc_1800B5C5F
0x1800b5c57  lea     eax, [rbx+7]
0x1800b5c5a  jmp     loc_1800B5CF6
0x1800b5c5f  cmp     byte ptr cs:word_18010EE54, 0
0x1800b5c66  jz      short loc_1800B5CBC
0x1800b5c68  mov     rax, cs:qword_18010EFE0
0x1800b5c6f  test    rax, rax
0x1800b5c72  jz      short loc_1800B5C82
0x1800b5c74  mov     ecx, 0C8h
0x1800b5c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5c7e  test    eax, eax
0x1800b5c80  jnz     short loc_1800B5CBC
0x1800b5c82  lea     rsi, [rbx+8]
0x1800b5c86  mov     [rbx+18h], rbp
0x1800b5c8a  lea     rdi, [rbx+10h]
0x1800b5c8e  mov     [rsp+68h+var_40], rsi
0x1800b5c93  mov     r9, rbx
0x1800b5c96  mov     [rsp+68h+var_48], 0
0x1800b5c9e  lea     r8, sqlite3ThreadProc
0x1800b5ca5  mov     [rdi], r15
0x1800b5ca8  xor     edx, edx
0x1800b5caa  xor     ecx, ecx
0x1800b5cac  call    cs:__imp__o__beginthreadex
0x1800b5cb2  mov     [rbx], rax
0x1800b5cb5  test    rax, rax
0x1800b5cb8  jz      short loc_1800B5CC4
0x1800b5cba  jmp     short loc_1800B5CD4
0x1800b5cbc  lea     rdi, [rbx+10h]
0x1800b5cc0  lea     rsi, [rbx+8]
0x1800b5cc4  xorps   xmm0, xmm0
0x1800b5cc7  xor     eax, eax
0x1800b5cc9  movups  xmmword ptr [rbx], xmm0
0x1800b5ccc  movups  xmmword ptr [rbx+10h], xmm0
0x1800b5cd0  mov     [rbx+20h], rax
0x1800b5cd4  cmp     qword ptr [rdi], 0
0x1800b5cd8  jnz     short loc_1800B5CF1
0x1800b5cda  call    cs:__imp_GetCurrentThreadId
0x1800b5ce0  mov     [rsi], eax
0x1800b5ce2  mov     rcx, rbp
0x1800b5ce5  mov     rax, r15
0x1800b5ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5ced  mov     [rbx+20h], rax
0x1800b5cf1  mov     [r14], rbx
0x1800b5cf4  xor     eax, eax
0x1800b5cf6  add     rsp, 38h
0x1800b5cfa  pop     r15
0x1800b5cfc  pop     r14
0x1800b5cfe  pop     rdi
0x1800b5cff  pop     rsi
0x1800b5d00  pop     rbp
0x1800b5d01  pop     rbx
0x1800b5d02  retn
```
