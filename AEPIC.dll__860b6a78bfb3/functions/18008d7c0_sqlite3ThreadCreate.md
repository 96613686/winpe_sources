# sqlite3ThreadCreate

- ea: `0x18008d7c0`
- end: `0x18008d88b`
- name: `sqlite3ThreadCreate`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800b0744`
- `0x1800b0874`
- `0x1800b1610`

## callees

- `0x1800780e8`
- `0x18008035c`
- `0x18008d7c0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008d834`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008d834`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d862`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d862`

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
  if ( !(_BYTE)word_180120994 || (unsigned int)sqlite3FaultSim(200) )
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
0x18008d7c0  push    rbx
0x18008d7c2  push    rbp
0x18008d7c3  push    rsi
0x18008d7c4  push    rdi
0x18008d7c5  push    r14
0x18008d7c7  push    r15
0x18008d7c9  sub     rsp, 38h
0x18008d7cd  mov     r14, rcx
0x18008d7d0  mov     qword ptr [rcx], 0
0x18008d7d7  mov     ecx, 28h ; '('
0x18008d7dc  mov     rbp, r8
0x18008d7df  mov     r15, rdx
0x18008d7e2  call    sqlite3Malloc
0x18008d7e7  mov     rbx, rax
0x18008d7ea  test    rax, rax
0x18008d7ed  jnz     short loc_18008D7F7
0x18008d7ef  lea     eax, [rbx+7]
0x18008d7f2  jmp     loc_18008D87E
0x18008d7f7  cmp     byte ptr cs:word_180120994, 0
0x18008d7fe  jz      short loc_18008D844
0x18008d800  mov     ecx, 0C8h
0x18008d805  call    sqlite3FaultSim
0x18008d80a  test    eax, eax
0x18008d80c  jnz     short loc_18008D844
0x18008d80e  lea     rsi, [rbx+8]
0x18008d812  mov     [rbx+18h], rbp
0x18008d816  lea     rdi, [rbx+10h]
0x18008d81a  mov     [rsp+68h+var_40], rsi
0x18008d81f  mov     r9, rbx
0x18008d822  mov     [rsp+68h+var_48], eax
0x18008d826  lea     r8, sqlite3ThreadProc
0x18008d82d  mov     [rdi], r15
0x18008d830  xor     edx, edx
0x18008d832  xor     ecx, ecx
0x18008d834  call    cs:__imp__o__beginthreadex
0x18008d83a  mov     [rbx], rax
0x18008d83d  test    rax, rax
0x18008d840  jz      short loc_18008D84C
0x18008d842  jmp     short loc_18008D85C
0x18008d844  lea     rdi, [rbx+10h]
0x18008d848  lea     rsi, [rbx+8]
0x18008d84c  xorps   xmm0, xmm0
0x18008d84f  xor     eax, eax
0x18008d851  movups  xmmword ptr [rbx], xmm0
0x18008d854  movups  xmmword ptr [rbx+10h], xmm0
0x18008d858  mov     [rbx+20h], rax
0x18008d85c  cmp     qword ptr [rdi], 0
0x18008d860  jnz     short loc_18008D879
0x18008d862  call    cs:__imp_GetCurrentThreadId
0x18008d868  mov     [rsi], eax
0x18008d86a  mov     rcx, rbp
0x18008d86d  mov     rax, r15
0x18008d870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d875  mov     [rbx+20h], rax
0x18008d879  mov     [r14], rbx
0x18008d87c  xor     eax, eax
0x18008d87e  add     rsp, 38h
0x18008d882  pop     r15
0x18008d884  pop     r14
0x18008d886  pop     rdi
0x18008d887  pop     rsi
0x18008d888  pop     rbp
0x18008d889  pop     rbx
0x18008d88a  retn
```
