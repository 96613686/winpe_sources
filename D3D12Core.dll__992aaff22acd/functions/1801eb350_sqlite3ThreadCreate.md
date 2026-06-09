# sqlite3ThreadCreate

- ea: `0x1801eb350`
- end: `0x1801eb41b`
- name: `sqlite3ThreadCreate`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18020f204`
- `0x18020f334`
- `0x1802100d0`

## callees

- `0x1801d51dc`
- `0x1801dd58c`
- `0x1801eb350`
- `0x180262020`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1801eb3c4`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1801eb3c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801eb3f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801eb3f2`

## pseudocode

```c
__int64 __fastcall sqlite3ThreadCreate(__int64 **a1, __int64 (__fastcall *a2)(__int64), __int64 a3)
{
  __int64 *v6; // rbx
  DWORD *v8; // rsi
  _QWORD *v9; // rdi
  __int64 v10; // rax

  *a1 = 0;
  v6 = (__int64 *)sqlite3Malloc(40);
  if ( !v6 )
    return 7;
  if ( !(_BYTE)word_180329984 || (unsigned int)sqlite3FaultSim(200) )
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
      goto LABEL_9;
  }
  *(_OWORD *)v6 = 0;
  *((_OWORD *)v6 + 1) = 0;
  v6[4] = 0;
LABEL_9:
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
0x1801eb350  push    rbx
0x1801eb352  push    rbp
0x1801eb353  push    rsi
0x1801eb354  push    rdi
0x1801eb355  push    r14
0x1801eb357  push    r15
0x1801eb359  sub     rsp, 38h
0x1801eb35d  mov     r14, rcx
0x1801eb360  mov     qword ptr [rcx], 0
0x1801eb367  mov     ecx, 28h ; '('
0x1801eb36c  mov     rbp, r8
0x1801eb36f  mov     r15, rdx
0x1801eb372  call    sqlite3Malloc
0x1801eb377  mov     rbx, rax
0x1801eb37a  test    rax, rax
0x1801eb37d  jnz     short loc_1801EB387
0x1801eb37f  lea     eax, [rbx+7]
0x1801eb382  jmp     loc_1801EB40E
0x1801eb387  cmp     byte ptr cs:word_180329984, 0
0x1801eb38e  jz      short loc_1801EB3D4
0x1801eb390  mov     ecx, 0C8h
0x1801eb395  call    sqlite3FaultSim
0x1801eb39a  test    eax, eax
0x1801eb39c  jnz     short loc_1801EB3D4
0x1801eb39e  lea     rsi, [rbx+8]
0x1801eb3a2  mov     [rbx+18h], rbp
0x1801eb3a6  lea     rdi, [rbx+10h]
0x1801eb3aa  mov     [rsp+68h+var_40], rsi
0x1801eb3af  mov     r9, rbx
0x1801eb3b2  mov     [rsp+68h+var_48], eax
0x1801eb3b6  lea     r8, sqlite3ThreadProc
0x1801eb3bd  mov     [rdi], r15
0x1801eb3c0  xor     edx, edx
0x1801eb3c2  xor     ecx, ecx
0x1801eb3c4  call    cs:__imp__o__beginthreadex
0x1801eb3ca  mov     [rbx], rax
0x1801eb3cd  test    rax, rax
0x1801eb3d0  jz      short loc_1801EB3DC
0x1801eb3d2  jmp     short loc_1801EB3EC
0x1801eb3d4  lea     rdi, [rbx+10h]
0x1801eb3d8  lea     rsi, [rbx+8]
0x1801eb3dc  xorps   xmm0, xmm0
0x1801eb3df  xor     eax, eax
0x1801eb3e1  movups  xmmword ptr [rbx], xmm0
0x1801eb3e4  movups  xmmword ptr [rbx+10h], xmm0
0x1801eb3e8  mov     [rbx+20h], rax
0x1801eb3ec  cmp     qword ptr [rdi], 0
0x1801eb3f0  jnz     short loc_1801EB409
0x1801eb3f2  call    cs:__imp_GetCurrentThreadId
0x1801eb3f8  mov     [rsi], eax
0x1801eb3fa  mov     rcx, rbp
0x1801eb3fd  mov     rax, r15
0x1801eb400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eb405  mov     [rbx+20h], rax
0x1801eb409  mov     [r14], rbx
0x1801eb40c  xor     eax, eax
0x1801eb40e  add     rsp, 38h
0x1801eb412  pop     r15
0x1801eb414  pop     r14
0x1801eb416  pop     rdi
0x1801eb417  pop     rsi
0x1801eb418  pop     rbp
0x1801eb419  pop     rbx
0x1801eb41a  retn
```
