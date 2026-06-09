# sqlite3ThreadCreate

- ea: `0x180098818`
- end: `0x1800988e3`
- name: `sqlite3ThreadCreate`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18006f5c0`
- `0x1800a1e48`
- `0x1800a23b0`

## callees

- `0x180035450`
- `0x18003c510`
- `0x180098818`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18009888c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18009888c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800988ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800988ba`

## pseudocode

```c
__int64 __fastcall sqlite3ThreadCreate(__int64 **a1, __int64 (__fastcall *a2)(__int64), __int64 a3)
{
  __int64 v6; // rdx
  __int64 *v7; // rbx
  __int64 v8; // r8
  __int64 v9; // r9
  DWORD *v11; // rsi
  _QWORD *v12; // rdi
  __int64 v13; // rax

  *a1 = 0;
  v7 = (__int64 *)sqlite3Malloc(40);
  if ( !v7 )
    return 7;
  if ( !(_BYTE)word_1800D0874 || (unsigned int)sqlite3FaultSim(200, v6, v8, v9) )
  {
    v12 = v7 + 2;
    v11 = (DWORD *)(v7 + 1);
  }
  else
  {
    v11 = (DWORD *)(v7 + 1);
    v7[3] = a3;
    v12 = v7 + 2;
    v7[2] = (__int64)a2;
    v13 = _o__beginthreadex(0, 0, sqlite3ThreadProc, v7, 0, v7 + 1);
    *v7 = v13;
    if ( v13 )
      goto LABEL_9;
  }
  *(_OWORD *)v7 = 0;
  *((_OWORD *)v7 + 1) = 0;
  v7[4] = 0;
LABEL_9:
  if ( !*v12 )
  {
    *v11 = GetCurrentThreadId();
    v7[4] = a2(a3);
  }
  *a1 = v7;
  return 0;
}

```

## disassembly

```asm
0x180098818  push    rbx
0x18009881a  push    rbp
0x18009881b  push    rsi
0x18009881c  push    rdi
0x18009881d  push    r14
0x18009881f  push    r15
0x180098821  sub     rsp, 38h
0x180098825  mov     r14, rcx
0x180098828  mov     qword ptr [rcx], 0
0x18009882f  mov     ecx, 28h ; '('
0x180098834  mov     rbp, r8
0x180098837  mov     r15, rdx
0x18009883a  call    sqlite3Malloc
0x18009883f  mov     rbx, rax
0x180098842  test    rax, rax
0x180098845  jnz     short loc_18009884F
0x180098847  lea     eax, [rbx+7]
0x18009884a  jmp     loc_1800988D6
0x18009884f  cmp     byte ptr cs:word_1800D0874, 0
0x180098856  jz      short loc_18009889C
0x180098858  mov     ecx, 0C8h
0x18009885d  call    sqlite3FaultSim
0x180098862  test    eax, eax
0x180098864  jnz     short loc_18009889C
0x180098866  lea     rsi, [rbx+8]
0x18009886a  mov     [rbx+18h], rbp
0x18009886e  lea     rdi, [rbx+10h]
0x180098872  mov     [rsp+68h+var_40], rsi
0x180098877  mov     r9, rbx
0x18009887a  mov     [rsp+68h+var_48], eax
0x18009887e  lea     r8, sqlite3ThreadProc
0x180098885  mov     [rdi], r15
0x180098888  xor     edx, edx
0x18009888a  xor     ecx, ecx
0x18009888c  call    cs:__imp__o__beginthreadex
0x180098892  mov     [rbx], rax
0x180098895  test    rax, rax
0x180098898  jz      short loc_1800988A4
0x18009889a  jmp     short loc_1800988B4
0x18009889c  lea     rdi, [rbx+10h]
0x1800988a0  lea     rsi, [rbx+8]
0x1800988a4  xorps   xmm0, xmm0
0x1800988a7  xor     eax, eax
0x1800988a9  movups  xmmword ptr [rbx], xmm0
0x1800988ac  movups  xmmword ptr [rbx+10h], xmm0
0x1800988b0  mov     [rbx+20h], rax
0x1800988b4  cmp     qword ptr [rdi], 0
0x1800988b8  jnz     short loc_1800988D1
0x1800988ba  call    cs:__imp_GetCurrentThreadId
0x1800988c0  mov     [rsi], eax
0x1800988c2  mov     rcx, rbp
0x1800988c5  mov     rax, r15
0x1800988c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800988cd  mov     [rbx+20h], rax
0x1800988d1  mov     [r14], rbx
0x1800988d4  xor     eax, eax
0x1800988d6  add     rsp, 38h
0x1800988da  pop     r15
0x1800988dc  pop     r14
0x1800988de  pop     rdi
0x1800988df  pop     rsi
0x1800988e0  pop     rbp
0x1800988e1  pop     rbx
0x1800988e2  retn
```
