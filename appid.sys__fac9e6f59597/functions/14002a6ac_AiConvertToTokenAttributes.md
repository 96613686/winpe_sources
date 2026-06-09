# AiConvertToTokenAttributes

- ea: `0x14002a6ac`
- end: `0x14002a83a`
- name: `AiConvertToTokenAttributes`
- size: `398`
- prototype: `__int64 __fastcall(const void **, const void **, unsigned __int16 *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14001f010`
- `0x140036af0`

## callees

- `0x140006c40`
- `0x140006f40`
- `0x14002a6ac`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002a7cd`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002a7cd`

## pseudocode

```c
__int64 __fastcall AiConvertToTokenAttributes(
        const void **a1,
        const void **a2,
        unsigned __int16 *a3,
        __int64 a4,
        _QWORD *a5)
{
  bool v9; // r14
  char *v10; // rax
  char *v11; // rdi
  int v12; // edx
  unsigned int v13; // esi
  unsigned int v14; // ebx
  char *v15; // rax
  char *v16; // r15
  __int64 v17; // rax
  char *v18; // rbx
  __int64 v19; // rax
  char *v20; // rcx

  v9 = a3 && *((_QWORD *)a3 + 1);
  v10 = (char *)AiAlloc(0x50u);
  v11 = v10;
  if ( !v10 )
    goto LABEL_12;
  memset(v10, 0, 0x50u);
  v12 = *(unsigned __int16 *)a1 + *(unsigned __int16 *)a2 + 4;
  if ( v9 )
    v13 = v12 + *a3;
  else
    v13 = v12 + 8;
  if ( v13 > 0xFFFF )
  {
    v14 = -1073741675;
LABEL_13:
    AiFree(0);
    AiFree(v11);
    return v14;
  }
  v15 = (char *)AiAlloc(v13);
  v16 = v15;
  if ( !v15 )
  {
LABEL_12:
    v14 = -1073741801;
    goto LABEL_13;
  }
  memmove(v15, a1[1], *(unsigned __int16 *)a1);
  v17 = *(unsigned __int16 *)a1;
  *(_WORD *)&v16[v17] = 92;
  v18 = &v16[v17 + 2];
  memmove(v18, a2[1], *(unsigned __int16 *)a2);
  v19 = *(unsigned __int16 *)a2;
  *(_WORD *)&v18[v19] = 92;
  v20 = &v18[v19 + 2];
  if ( v9 )
    memmove(v20, *((const void **)a3 + 1), *a3);
  else
    *(_QWORD *)v20 = 0x58005000500041LL;
  *((_WORD *)v11 + 5) = v13;
  *((_WORD *)v11 + 4) = v13;
  *((_QWORD *)v11 + 2) = v16;
  *(_QWORD *)v11 = a4;
  RtlUpcaseUnicodeString((PUNICODE_STRING)(v11 + 8), (PCUNICODE_STRING)(v11 + 8), 0);
  *((_WORD *)v11 + 20) = 4;
  *(_OWORD *)(v11 + 24) = *(_OWORD *)&qword_1400096B8;
  *((_DWORD *)v11 + 12) = 1;
  *((_QWORD *)v11 + 7) = v11;
  v14 = 0;
  *((_DWORD *)v11 + 11) = 3;
  *((_WORD *)v11 + 33) = 0;
  *((_WORD *)v11 + 32) = 1;
  *((_DWORD *)v11 + 17) = 1;
  *((_QWORD *)v11 + 9) = v11 + 24;
  *a5 = v11 + 64;
  return v14;
}

```

## disassembly

```asm
0x14002a6ac  push    rbx
0x14002a6ae  push    rbp
0x14002a6af  push    rsi
0x14002a6b0  push    rdi
0x14002a6b1  push    r12
0x14002a6b3  push    r13
0x14002a6b5  push    r14
0x14002a6b7  push    r15
0x14002a6b9  sub     rsp, 28h
0x14002a6bd  mov     r12, r9
0x14002a6c0  mov     rbp, r8
0x14002a6c3  mov     r13, rdx
0x14002a6c6  mov     rbx, rcx
0x14002a6c9  test    r8, r8
0x14002a6cc  jz      short loc_14002A6DA
0x14002a6ce  cmp     qword ptr [r8+8], 0
0x14002a6d3  jz      short loc_14002A6DA
0x14002a6d5  mov     r14b, 1
0x14002a6d8  jmp     short loc_14002A6DD
0x14002a6da  xor     r14b, r14b
0x14002a6dd  mov     esi, 50h ; 'P'
0x14002a6e2  mov     ecx, esi
0x14002a6e4  call    AiAlloc
0x14002a6e9  mov     rdi, rax
0x14002a6ec  test    rax, rax
0x14002a6ef  jz      short loc_14002A739
0x14002a6f1  mov     r8d, esi; Size
0x14002a6f4  xor     edx, edx; Val
0x14002a6f6  mov     rcx, rax; void *
0x14002a6f9  call    memset
0x14002a6fe  movzx   edx, word ptr [r13+0]
0x14002a703  movzx   ecx, word ptr [rbx]
0x14002a706  add     edx, 4
0x14002a709  add     edx, ecx
0x14002a70b  test    r14b, r14b
0x14002a70e  jz      short loc_14002A718
0x14002a710  movzx   esi, word ptr [rbp+0]
0x14002a714  add     esi, edx
0x14002a716  jmp     short loc_14002A71B
0x14002a718  lea     esi, [rdx+8]
0x14002a71b  cmp     esi, 0FFFFh
0x14002a721  jbe     short loc_14002A72A
0x14002a723  mov     ebx, 0C0000095h
0x14002a728  jmp     short loc_14002A73E
0x14002a72a  mov     ecx, esi
0x14002a72c  call    AiAlloc
0x14002a731  mov     r15, rax
0x14002a734  test    rax, rax
0x14002a737  jnz     short loc_14002A752
0x14002a739  mov     ebx, 0C0000017h
0x14002a73e  xor     ecx, ecx
0x14002a740  call    AiFree
0x14002a745  mov     rcx, rdi
0x14002a748  call    AiFree
0x14002a74d  jmp     loc_14002A826
0x14002a752  movzx   r8d, word ptr [rbx]; Size
0x14002a756  mov     rcx, r15; void *
0x14002a759  mov     rdx, [rbx+8]; Src
0x14002a75d  call    memmove
0x14002a762  movzx   eax, word ptr [rbx]
0x14002a765  mov     word ptr [rax+r15], 5Ch ; '\'
0x14002a76c  lea     rbx, [rax+2]
0x14002a770  movzx   r8d, word ptr [r13+0]; Size
0x14002a775  add     rbx, r15
0x14002a778  mov     rdx, [r13+8]; Src
0x14002a77c  mov     rcx, rbx; void *
0x14002a77f  call    memmove
0x14002a784  movzx   eax, word ptr [r13+0]
0x14002a789  lea     rcx, [rax+2]
0x14002a78d  mov     word ptr [rax+rbx], 5Ch ; '\'
0x14002a793  add     rcx, rbx; void *
0x14002a796  test    r14b, r14b
0x14002a799  jz      short loc_14002A7AB
0x14002a79b  movzx   r8d, word ptr [rbp+0]; Size
0x14002a7a0  mov     rdx, [rbp+8]; Src
0x14002a7a4  call    memmove
0x14002a7a9  jmp     short loc_14002A7B5
0x14002a7ab  mov     rax, cs:qword_14000D4C0
0x14002a7b2  mov     [rcx], rax
0x14002a7b5  lea     rcx, [rdi+8]; DestinationString
0x14002a7b9  mov     [rdi+0Ah], si
0x14002a7bd  mov     rdx, rcx; SourceString
0x14002a7c0  mov     [rcx], si
0x14002a7c3  xor     r8d, r8d; AllocateDestinationString
0x14002a7c6  mov     [rdi+10h], r15
0x14002a7ca  mov     [rdi], r12
0x14002a7cd  call    cs:__imp_RtlUpcaseUnicodeString
0x14002a7d4  nop     dword ptr [rax+rax+00h]
0x14002a7d9  movups  xmm0, xmmword ptr cs:qword_1400096B8
0x14002a7e0  lea     rdx, [rdi+18h]
0x14002a7e4  mov     r8d, 1
0x14002a7ea  mov     word ptr [rdx+10h], 4
0x14002a7f0  lea     rcx, [rdi+40h]
0x14002a7f4  movdqu  xmmword ptr [rdx], xmm0
0x14002a7f8  mov     [rdx+18h], r8d
0x14002a7fc  xor     eax, eax
0x14002a7fe  mov     [rdx+20h], rdi
0x14002a802  xor     ebx, ebx
0x14002a804  mov     dword ptr [rdx+14h], 3
0x14002a80b  mov     [rdi+42h], ax
0x14002a80f  mov     rax, [rsp+68h+arg_20]
0x14002a817  mov     [rcx], r8w
0x14002a81b  mov     [rdi+44h], r8d
0x14002a81f  mov     [rdi+48h], rdx
0x14002a823  mov     [rax], rcx
0x14002a826  mov     eax, ebx
0x14002a828  add     rsp, 28h
0x14002a82c  pop     r15
0x14002a82e  pop     r14
0x14002a830  pop     r13
0x14002a832  pop     r12
0x14002a834  pop     rdi
0x14002a835  pop     rsi
0x14002a836  pop     rbp
0x14002a837  pop     rbx
0x14002a838  retn
```
