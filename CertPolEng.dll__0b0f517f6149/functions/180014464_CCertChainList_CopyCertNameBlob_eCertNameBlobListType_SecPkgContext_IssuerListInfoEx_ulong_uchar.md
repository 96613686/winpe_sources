# CCertChainList::CopyCertNameBlob(eCertNameBlobListType,_SecPkgContext_IssuerListInfoEx *,ulong *,uchar * *)

- ea: `0x180014464`
- end: `0x18001450a`
- name: `?CopyCertNameBlob@CCertChainList@@QEAAKW4eCertNameBlobListType@@PEAU_SecPkgContext_IssuerListInfoEx@@PEAKPEAPEAE@Z`
- size: `166`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014c2c`

## callees

- `0x18000e8d6`
- `0x180014464`

## pseudocode

```c
__int64 __fastcall CCertChainList::CopyCertNameBlob(__int64 a1, __int64 a2, _QWORD *a3, unsigned int *a4, void **a5)
{
  __int64 v5; // rbx
  unsigned int v7; // esi
  char *i; // rdi
  __int64 v11; // r13
  __int64 v12; // rdx

  v5 = 0;
  v7 = *a4;
  for ( i = (char *)*a5; (unsigned int)v5 < *(_DWORD *)(a1 + 8); v5 = (unsigned int)(v5 + 1) )
  {
    v11 = *(_QWORD *)(*(_QWORD *)(**(_QWORD **)(**(_QWORD **)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v5) + 16LL) + 16LL)
                                + 8LL)
                    + 24LL);
    if ( *(_DWORD *)(v11 + 80) )
    {
      memcpy_0(i, *(const void **)(v11 + 88), *(unsigned int *)(v11 + 80));
      v12 = 2LL * v7;
      *(_DWORD *)(*a3 + 8 * v12) = *(_DWORD *)(v11 + 80);
      *(_QWORD *)(*a3 + 8 * v12 + 8) = i;
      i += *(unsigned int *)(v11 + 80);
      ++v7;
    }
  }
  *a4 = v7;
  *a5 = i;
  return 0;
}

```

## disassembly

```asm
0x180014464  push    rbx
0x180014466  push    rbp
0x180014467  push    rsi
0x180014468  push    rdi
0x180014469  push    r12
0x18001446b  push    r13
0x18001446d  push    r14
0x18001446f  push    r15
0x180014471  sub     rsp, 28h
0x180014475  mov     r15, [rsp+68h+arg_20]
0x18001447d  xor     ebx, ebx
0x18001447f  mov     r14, r9
0x180014482  mov     esi, [r9]
0x180014485  mov     r12, r8
0x180014488  mov     rbp, rcx
0x18001448b  mov     rdi, [r15]
0x18001448e  cmp     [rcx+8], ebx
0x180014491  jbe     short loc_1800144F1
0x180014493  mov     rax, [rbp+10h]
0x180014497  mov     rcx, [rax+rbx*8]
0x18001449b  mov     rax, [rcx+10h]
0x18001449f  mov     rcx, [rax]
0x1800144a2  mov     rax, [rcx+10h]
0x1800144a6  mov     rcx, [rax]
0x1800144a9  mov     rax, [rcx+8]
0x1800144ad  mov     r13, [rax+18h]
0x1800144b1  cmp     dword ptr [r13+50h], 0
0x1800144b6  jbe     short loc_1800144EA
0x1800144b8  mov     r8d, [r13+50h]; Size
0x1800144bc  mov     rcx, rdi; void *
0x1800144bf  mov     rdx, [r13+58h]; Src
0x1800144c3  call    memcpy_0
0x1800144c8  mov     eax, [r13+50h]
0x1800144cc  mov     rcx, [r12]
0x1800144d0  mov     edx, esi
0x1800144d2  add     rdx, rdx
0x1800144d5  mov     [rcx+rdx*8], eax
0x1800144d8  mov     rax, [r12]
0x1800144dc  mov     [rax+rdx*8+8], rdi
0x1800144e1  mov     eax, [r13+50h]
0x1800144e5  add     rdi, rax
0x1800144e8  inc     esi
0x1800144ea  inc     ebx
0x1800144ec  cmp     ebx, [rbp+8]
0x1800144ef  jb      short loc_180014493
0x1800144f1  mov     [r14], esi
0x1800144f4  mov     [r15], rdi
0x1800144f7  xor     eax, eax
0x1800144f9  add     rsp, 28h
0x1800144fd  pop     r15
0x1800144ff  pop     r14
0x180014501  pop     r13
0x180014503  pop     r12
0x180014505  pop     rdi
0x180014506  pop     rsi
0x180014507  pop     rbp
0x180014508  pop     rbx
0x180014509  retn
```
