# vdbeSorterCreateThread

- ea: `0x180160b90`
- end: `0x180160c86`
- name: `vdbeSorterCreateThread`
- size: `246`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18015f4f0`
- `0x18015ff70`
- `0x180160d60`
- `0x180161ad0`

## callees

- `0x18011de20`
- `0x180160b90`
- `0x18020c360`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180160c5b`
- `KERNEL32!GetCurrentThreadId` at `0x180160c5b`

## pseudocode

```c
__int64 __fastcall vdbeSorterCreateThread(__int64 *a1, __int64 (__fastcall *a2)(__int64), __int64 a3)
{
  __int64 v6; // rbx
  __int64 result; // rax
  DWORD *v8; // rsi
  _QWORD *v9; // rdi
  uintptr_t v10; // rax

  *a1 = 0;
  v6 = sqlite3Malloc(40);
  if ( !v6 )
    return 7;
  if ( !(_BYTE)word_1803379C4 || qword_180337B50 && (unsigned int)qword_180337B50(200) )
  {
    v9 = (_QWORD *)(v6 + 16);
    v8 = (DWORD *)(v6 + 8);
LABEL_9:
    *(_OWORD *)v6 = 0;
    *(_OWORD *)(v6 + 16) = 0;
    *(_QWORD *)(v6 + 32) = 0;
    goto LABEL_10;
  }
  v8 = (DWORD *)(v6 + 8);
  *(_QWORD *)(v6 + 16) = a2;
  v9 = (_QWORD *)(v6 + 16);
  *(_QWORD *)(v6 + 24) = a3;
  v10 = beginthreadex(0, 0, sqlite3ThreadProc, (void *)v6, 0, (unsigned int *)(v6 + 8));
  *(_QWORD *)v6 = v10;
  if ( !v10 )
    goto LABEL_9;
LABEL_10:
  if ( !*v9 )
  {
    *v8 = GetCurrentThreadId();
    *(_QWORD *)(v6 + 32) = a2(a3);
  }
  result = 0;
  *a1 = v6;
  return result;
}

```

## disassembly

```asm
0x180160b90  mov     [rsp+arg_10], rbx
0x180160b95  push    rbp
0x180160b96  push    r14
0x180160b98  push    r15
0x180160b9a  sub     rsp, 30h
0x180160b9e  mov     r14, rcx
0x180160ba1  mov     qword ptr [rcx], 0
0x180160ba8  mov     ecx, 28h ; '('
0x180160bad  mov     rbp, r8
0x180160bb0  mov     r15, rdx
0x180160bb3  call    sqlite3Malloc
0x180160bb8  mov     rbx, rax
0x180160bbb  test    rax, rax
0x180160bbe  jnz     short loc_180160BD4
0x180160bc0  mov     eax, 7
0x180160bc5  mov     rbx, [rsp+48h+arg_10]
0x180160bca  add     rsp, 30h
0x180160bce  pop     r15
0x180160bd0  pop     r14
0x180160bd2  pop     rbp
0x180160bd3  retn
0x180160bd4  cmp     byte ptr cs:word_1803379C4, 0
0x180160bdb  mov     [rsp+48h+arg_0], rsi
0x180160be0  mov     [rsp+48h+arg_8], rdi
0x180160be5  jz      short loc_180160C38
0x180160be7  mov     rax, cs:qword_180337B50
0x180160bee  test    rax, rax
0x180160bf1  jz      short loc_180160BFE
0x180160bf3  mov     ecx, 0C8h
0x180160bf8  call    rax ; qword_180337B50
0x180160bfa  test    eax, eax
0x180160bfc  jnz     short loc_180160C38
0x180160bfe  lea     rsi, [rbx+8]
0x180160c02  mov     [rbx+10h], r15
0x180160c06  lea     rdi, [rbx+10h]
0x180160c0a  mov     [rsp+48h+ThrdAddr], rsi; ThrdAddr
0x180160c0f  mov     r9, rbx; ArgList
0x180160c12  mov     [rsp+48h+InitFlag], 0; InitFlag
0x180160c1a  lea     r8, sqlite3ThreadProc; StartAddress
0x180160c21  mov     [rbx+18h], rbp
0x180160c25  xor     edx, edx; StackSize
0x180160c27  xor     ecx, ecx; Security
0x180160c29  call    _beginthreadex
0x180160c2e  mov     [rbx], rax
0x180160c31  test    rax, rax
0x180160c34  jnz     short loc_180160C50
0x180160c36  jmp     short loc_180160C40
0x180160c38  lea     rdi, [rbx+10h]
0x180160c3c  lea     rsi, [rbx+8]
0x180160c40  xorps   xmm0, xmm0
0x180160c43  xor     eax, eax
0x180160c45  movups  xmmword ptr [rbx], xmm0
0x180160c48  movups  xmmword ptr [rbx+10h], xmm0
0x180160c4c  mov     [rbx+20h], rax
0x180160c50  cmp     qword ptr [rdi], 0
0x180160c54  mov     rdi, [rsp+48h+arg_8]
0x180160c59  jnz     short loc_180160C6D
0x180160c5b  call    cs:__imp_GetCurrentThreadId
0x180160c61  mov     rcx, rbp
0x180160c64  mov     [rsi], eax
0x180160c66  call    r15
0x180160c69  mov     [rbx+20h], rax
0x180160c6d  mov     rsi, [rsp+48h+arg_0]
0x180160c72  xor     eax, eax
0x180160c74  mov     [r14], rbx
0x180160c77  mov     rbx, [rsp+48h+arg_10]
0x180160c7c  add     rsp, 30h
0x180160c80  pop     r15
0x180160c82  pop     r14
0x180160c84  pop     rbp
0x180160c85  retn
```
