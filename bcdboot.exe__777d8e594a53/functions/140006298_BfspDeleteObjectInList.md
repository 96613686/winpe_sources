# BfspDeleteObjectInList

- ea: `0x140006298`
- end: `0x140006364`
- name: `BfspDeleteObjectInList`
- size: `204`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000619c`

## callees

- `0x140006298`
- `0x1400265fa`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000633b`
- `KERNEL32!HeapFree` at `0x14000633b`
- `KERNEL32!HeapAlloc` at `0x1400062c5`
- `KERNEL32!HeapAlloc` at `0x1400062c5`
- `KERNEL32!GetProcessHeap` at `0x1400062b4`
- `KERNEL32!GetProcessHeap` at `0x14000632d`
- `KERNEL32!GetProcessHeap` at `0x1400062b4`
- `KERNEL32!GetProcessHeap` at `0x14000632d`

## pseudocode

```c
__int64 __fastcall BfspDeleteObjectInList(__int64 a1, unsigned int a2, _QWORD *a3, _QWORD *a4, _DWORD *a5)
{
  size_t v6; // rbp
  HANDLE ProcessHeap; // rax
  _OWORD *v10; // rax
  int v11; // ebx
  _OWORD *v12; // rdi
  unsigned int v13; // esi
  unsigned int v14; // ecx
  unsigned int v15; // ebp
  _OWORD *v16; // r8
  HANDLE v17; // rax
  __int64 result; // rax

  v6 = a2;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v6);
  v11 = 0;
  v12 = v10;
  if ( v10 )
  {
    v13 = 0;
    memset_0(v10, 0, v6);
    v14 = 0;
    v15 = (unsigned int)v6 >> 4;
    v16 = v12;
    if ( !v15 )
      goto LABEL_9;
    do
    {
      if ( *(_QWORD *)(a1 + 16LL * v14) != *a3 || *(_QWORD *)(a1 + 16LL * v14 + 8) != a3[1] )
      {
        v11 += 16;
        *v16++ = *(_OWORD *)(a1 + 16LL * v14);
      }
      ++v14;
    }
    while ( v14 < v15 );
    if ( !v11 )
    {
LABEL_9:
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v12);
      v12 = 0;
    }
  }
  else
  {
    v13 = -1073741801;
  }
  result = v13;
  *a4 = v12;
  *a5 = v11;
  return result;
}

```

## disassembly

```asm
0x140006298  push    rbx
0x14000629a  push    rbp
0x14000629b  push    rsi
0x14000629c  push    rdi
0x14000629d  push    r12
0x14000629f  push    r13
0x1400062a1  push    r14
0x1400062a3  push    r15
0x1400062a5  sub     rsp, 28h
0x1400062a9  mov     r13, r9
0x1400062ac  mov     ebp, edx
0x1400062ae  mov     r12, r8
0x1400062b1  mov     r14, rcx
0x1400062b4  call    cs:__imp_GetProcessHeap
0x1400062ba  mov     r8d, ebp; dwBytes
0x1400062bd  mov     edx, 8; dwFlags
0x1400062c2  mov     rcx, rax; hHeap
0x1400062c5  call    cs:__imp_HeapAlloc
0x1400062cb  xor     ebx, ebx
0x1400062cd  mov     rdi, rax
0x1400062d0  test    rax, rax
0x1400062d3  jnz     short loc_1400062DC
0x1400062d5  mov     esi, 0C0000017h
0x1400062da  jmp     short loc_140006343
0x1400062dc  mov     r8, rbp; Size
0x1400062df  xor     edx, edx; Val
0x1400062e1  mov     rcx, rdi; void *
0x1400062e4  xor     esi, esi
0x1400062e6  call    memset_0
0x1400062eb  xor     ecx, ecx
0x1400062ed  shr     ebp, 4
0x1400062f0  mov     r8, rdi
0x1400062f3  test    ebp, ebp
0x1400062f5  jz      short loc_14000632D
0x1400062f7  mov     edx, ecx
0x1400062f9  add     rdx, rdx
0x1400062fc  mov     rax, [r14+rdx*8]
0x140006300  cmp     rax, [r12]
0x140006304  jnz     short loc_140006312
0x140006306  mov     rax, [r14+rdx*8+8]
0x14000630b  cmp     rax, [r12+8]
0x140006310  jz      short loc_140006323
0x140006312  movups  xmm0, xmmword ptr [r14+rdx*8]
0x140006317  add     ebx, 10h
0x14000631a  movdqu  xmmword ptr [r8], xmm0
0x14000631f  add     r8, 10h
0x140006323  inc     ecx
0x140006325  cmp     ecx, ebp
0x140006327  jb      short loc_1400062F7
0x140006329  test    ebx, ebx
0x14000632b  jnz     short loc_140006343
0x14000632d  call    cs:__imp_GetProcessHeap
0x140006333  mov     r8, rdi; lpMem
0x140006336  xor     edx, edx; dwFlags
0x140006338  mov     rcx, rax; hHeap
0x14000633b  call    cs:__imp_HeapFree
0x140006341  xor     edi, edi
0x140006343  mov     rcx, [rsp+68h+arg_20]
0x14000634b  mov     eax, esi
0x14000634d  mov     [r13+0], rdi
0x140006351  mov     [rcx], ebx
0x140006353  add     rsp, 28h
0x140006357  pop     r15
0x140006359  pop     r14
0x14000635b  pop     r13
0x14000635d  pop     r12
0x14000635f  pop     rdi
0x140006360  pop     rsi
0x140006361  pop     rbp
0x140006362  pop     rbx
0x140006363  retn
```
