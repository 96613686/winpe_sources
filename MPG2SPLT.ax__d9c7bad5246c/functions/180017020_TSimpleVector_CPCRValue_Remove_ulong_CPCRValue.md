# TSimpleVector<CPCRValue *>::Remove(ulong,CPCRValue * *)

- ea: `0x180017020`
- end: `0x1800170ae`
- name: `?Remove@?$TSimpleVector@PEAVCPCRValue@@@@QEAAJKPEAPEAVCPCRValue@@@Z`
- size: `142`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180014608`
- `0x180021bfc`
- `0x180021d08`
- `0x1800310f8`

## callees

- `0x180017020`
- `0x180020854`
- `0x180033e09`

## import_xrefs

- `KERNEL32!HeapReAlloc` at `0x180017093`
- `KERNEL32!HeapReAlloc` at `0x180017093`

## pseudocode

```c
__int64 __fastcall TSimpleVector<CPCRValue *>::Remove(__int64 a1, unsigned int a2)
{
  unsigned int v3; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // eax
  unsigned int v7; // edi
  LPVOID v8; // rax

  v3 = *(_DWORD *)(a1 + 8);
  if ( a2 >= v3 )
    return 2147942487LL;
  if ( a2 < v3 - 1 )
    memmove_0((void *)(*(_QWORD *)a1 + 8LL * a2), (const void *)(*(_QWORD *)a1 + 8LL * (a2 + 1)), 8LL * (v3 + ~a2));
  v5 = *(_DWORD *)(a1 + 8) - 1;
  *(_DWORD *)(a1 + 8) = v5;
  if ( v5 >= *(_DWORD *)(a1 + 16) )
  {
    v6 = *(_DWORD *)(a1 + 32) / *(_DWORD *)(a1 + 12);
    v7 = v6;
    if ( v5 <= v6 )
    {
      v8 = HeapReAlloc(*(HANDLE *)(a1 + 24), 4u, *(LPVOID *)a1, 8LL * v6);
      *(_DWORD *)(a1 + 32) = v7;
      *(_QWORD *)a1 = v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017020  mov     [rsp+arg_0], rbx
0x180017025  push    rdi
0x180017026  sub     rsp, 20h
0x18001702a  mov     rbx, rcx
0x18001702d  mov     ecx, [rcx+8]
0x180017030  cmp     edx, ecx
0x180017032  jb      short loc_18001703B
0x180017034  mov     eax, 80070057h
0x180017039  jmp     short loc_1800170A3
0x18001703b  lea     eax, [rcx-1]
0x18001703e  cmp     edx, eax
0x180017040  jnb     short loc_180017065
0x180017042  mov     r10d, edx
0x180017045  mov     r9, [rbx]
0x180017048  mov     r8d, edx
0x18001704b  not     r8d
0x18001704e  add     r8d, ecx
0x180017051  shl     r8, 3; Size
0x180017055  lea     eax, [rdx+1]
0x180017058  lea     rdx, [r9+rax*8]; Src
0x18001705c  lea     rcx, [r9+r10*8]; void *
0x180017060  call    memmove_0
0x180017065  mov     ecx, [rbx+8]
0x180017068  dec     ecx
0x18001706a  mov     [rbx+8], ecx
0x18001706d  cmp     ecx, [rbx+10h]
0x180017070  jb      short loc_18001709F
0x180017072  xor     edx, edx
0x180017074  mov     eax, [rbx+20h]
0x180017077  div     dword ptr [rbx+0Ch]
0x18001707a  mov     edi, eax
0x18001707c  cmp     ecx, eax
0x18001707e  ja      short loc_18001709F
0x180017080  mov     r9d, edi
0x180017083  shl     r9, 3; dwBytes
0x180017087  mov     r8, [rbx]; lpMem
0x18001708a  mov     edx, 4; dwFlags
0x18001708f  mov     rcx, [rbx+18h]; hHeap
0x180017093  call    cs:__imp_HeapReAlloc
0x180017099  mov     [rbx+20h], edi
0x18001709c  mov     [rbx], rax
0x18001709f  jmp     short $+2
0x1800170a1  xor     eax, eax
0x1800170a3  mov     rbx, [rsp+28h+arg_0]
0x1800170a8  add     rsp, 20h
0x1800170ac  pop     rdi
0x1800170ad  retn
0x180033f4c  push    rbp
0x180033f4e  sub     rsp, 20h
0x180033f52  mov     rbp, rdx
0x180033f55  mov     rax, [rcx]
0x180033f58  cmp     dword ptr [rax], 0C0000017h
0x180033f5e  jz      short loc_180033F6C
0x180033f60  cmp     dword ptr [rax], 0C0000005h
0x180033f66  jz      short loc_180033F6C
0x180033f68  xor     eax, eax
0x180033f6a  jmp     short loc_180033F71
0x180033f6c  mov     eax, 1
0x180033f71  add     rsp, 20h
0x180033f75  pop     rbp
0x180033f76  retn
```
