# sqlite3ThreadCreate

- ea: `0x1800878e0`
- end: `0x1800879ab`
- name: `sqlite3ThreadCreate`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18004cb28`
- `0x180093de4`
- `0x180093f14`

## callees

- `0x18000bd90`
- `0x18004a0bc`
- `0x1800878e0`
- `0x18009a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180087954`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180087954`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180087982`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180087982`

## pseudocode

```c
__int64 __fastcall sqlite3ThreadCreate(__int64 **a1, __int64 (__fastcall *a2)(__int64), __int64 a3)
{
  __int64 v6; // rdx
  __int64 *v7; // rbx
  DWORD *v9; // rsi
  _QWORD *v10; // rdi
  __int64 v11; // rax

  *a1 = 0;
  v7 = (__int64 *)sqlite3Malloc(40);
  if ( !v7 )
    return 7;
  if ( !(_BYTE)word_1800B5634 || (unsigned int)sqlite3FaultSim(200, v6) )
  {
    v10 = v7 + 2;
    v9 = (DWORD *)(v7 + 1);
  }
  else
  {
    v9 = (DWORD *)(v7 + 1);
    v7[3] = a3;
    v10 = v7 + 2;
    v7[2] = (__int64)a2;
    v11 = _o__beginthreadex(0, 0, sqlite3ThreadProc, v7, 0, v7 + 1);
    *v7 = v11;
    if ( v11 )
      goto LABEL_9;
  }
  *(_OWORD *)v7 = 0;
  *((_OWORD *)v7 + 1) = 0;
  v7[4] = 0;
LABEL_9:
  if ( !*v10 )
  {
    *v9 = GetCurrentThreadId();
    v7[4] = a2(a3);
  }
  *a1 = v7;
  return 0;
}

```

## disassembly

```asm
0x1800878e0  push    rbx
0x1800878e2  push    rbp
0x1800878e3  push    rsi
0x1800878e4  push    rdi
0x1800878e5  push    r14
0x1800878e7  push    r15
0x1800878e9  sub     rsp, 38h
0x1800878ed  mov     r14, rcx
0x1800878f0  mov     qword ptr [rcx], 0
0x1800878f7  mov     ecx, 28h ; '('
0x1800878fc  mov     rbp, r8
0x1800878ff  mov     r15, rdx
0x180087902  call    sqlite3Malloc
0x180087907  mov     rbx, rax
0x18008790a  test    rax, rax
0x18008790d  jnz     short loc_180087917
0x18008790f  lea     eax, [rbx+7]
0x180087912  jmp     loc_18008799E
0x180087917  cmp     byte ptr cs:word_1800B5634, 0
0x18008791e  jz      short loc_180087964
0x180087920  mov     ecx, 0C8h
0x180087925  call    sqlite3FaultSim
0x18008792a  test    eax, eax
0x18008792c  jnz     short loc_180087964
0x18008792e  lea     rsi, [rbx+8]
0x180087932  mov     [rbx+18h], rbp
0x180087936  lea     rdi, [rbx+10h]
0x18008793a  mov     [rsp+68h+var_40], rsi
0x18008793f  mov     r9, rbx
0x180087942  mov     [rsp+68h+var_48], eax
0x180087946  lea     r8, sqlite3ThreadProc
0x18008794d  mov     [rdi], r15
0x180087950  xor     edx, edx
0x180087952  xor     ecx, ecx
0x180087954  call    cs:__imp__o__beginthreadex
0x18008795a  mov     [rbx], rax
0x18008795d  test    rax, rax
0x180087960  jz      short loc_18008796C
0x180087962  jmp     short loc_18008797C
0x180087964  lea     rdi, [rbx+10h]
0x180087968  lea     rsi, [rbx+8]
0x18008796c  xorps   xmm0, xmm0
0x18008796f  xor     eax, eax
0x180087971  movups  xmmword ptr [rbx], xmm0
0x180087974  movups  xmmword ptr [rbx+10h], xmm0
0x180087978  mov     [rbx+20h], rax
0x18008797c  cmp     qword ptr [rdi], 0
0x180087980  jnz     short loc_180087999
0x180087982  call    cs:__imp_GetCurrentThreadId
0x180087988  mov     [rsi], eax
0x18008798a  mov     rcx, rbp
0x18008798d  mov     rax, r15
0x180087990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087995  mov     [rbx+20h], rax
0x180087999  mov     [r14], rbx
0x18008799c  xor     eax, eax
0x18008799e  add     rsp, 38h
0x1800879a2  pop     r15
0x1800879a4  pop     r14
0x1800879a6  pop     rdi
0x1800879a7  pop     rsi
0x1800879a8  pop     rbp
0x1800879a9  pop     rbx
0x1800879aa  retn
```
