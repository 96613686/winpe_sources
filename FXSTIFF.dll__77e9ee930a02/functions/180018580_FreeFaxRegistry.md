# FreeFaxRegistry

- ea: `0x180018580`
- end: `0x18001870f`
- name: `FreeFaxRegistry`
- size: `399`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ee54`
- `0x180017744`

## callees

- `0x18000f1c8`
- `0x180018580`

## pseudocode

```c
void __fastcall FreeFaxRegistry(LPVOID lpMem)
{
  __int64 i; // rsi
  __int64 j; // rbp
  __int64 v4; // rcx
  __int64 v5; // r14
  unsigned int k; // ebx
  unsigned int m; // ebx

  if ( lpMem )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)lpMem + 2); i = (unsigned int)(i + 1) )
    {
      pMemFree(*(LPVOID *)(*(_QWORD *)lpMem + 40 * i));
      pMemFree(*(LPVOID *)(*(_QWORD *)lpMem + 40 * i + 8));
      pMemFree(*(LPVOID *)(*(_QWORD *)lpMem + 40 * i + 16));
      pMemFree(*(LPVOID *)(*(_QWORD *)lpMem + 40 * i + 32));
    }
    for ( j = 0; (unsigned int)j < *((_DWORD *)lpMem + 6); j = (unsigned int)(j + 1) )
    {
      pMemFree(*(LPVOID *)(*((_QWORD *)lpMem + 2) + 40 * j));
      pMemFree(*(LPVOID *)(*((_QWORD *)lpMem + 2) + 40 * j + 8));
      pMemFree(*(LPVOID *)(*((_QWORD *)lpMem + 2) + 40 * j + 16));
      v4 = *((_QWORD *)lpMem + 2);
      if ( *(_DWORD *)(v4 + 40 * j + 24) )
      {
        v5 = 0;
        do
        {
          pMemFree(*(LPVOID *)(*(_QWORD *)(v4 + 40 * j + 32) + 40 * v5));
          pMemFree(*(LPVOID *)(*(_QWORD *)(*((_QWORD *)lpMem + 2) + 40 * j + 32) + 40 * v5 + 8));
          pMemFree(*(LPVOID *)(*(_QWORD *)(*((_QWORD *)lpMem + 2) + 40 * j + 32) + 40 * v5 + 16));
          pMemFree(*(LPVOID *)(*(_QWORD *)(*((_QWORD *)lpMem + 2) + 40 * j + 32) + 40 * v5 + 24));
          v4 = *((_QWORD *)lpMem + 2);
          v5 = (unsigned int)(v5 + 1);
        }
        while ( (unsigned int)v5 < *(_DWORD *)(v4 + 40 * j + 24) );
      }
      pMemFree(*(LPVOID *)(v4 + 40 * j + 32));
    }
    pMemFree(*(LPVOID *)lpMem);
    pMemFree(*((LPVOID *)lpMem + 2));
    for ( k = 0; k < *((_DWORD *)lpMem + 10); ++k )
      pMemFree(*(LPVOID *)(88LL * k + *((_QWORD *)lpMem + 4) + 8));
    pMemFree(*((LPVOID *)lpMem + 4));
    for ( m = 0; m < *((_DWORD *)lpMem + 14); ++m )
      pMemFree(*(LPVOID *)(*((_QWORD *)lpMem + 6) + 16LL * m));
    pMemFree(*((LPVOID *)lpMem + 6));
    pMemFree(lpMem);
  }
}

```

## disassembly

```asm
0x180018580  test    rcx, rcx
0x180018583  jz      locret_18001870D
0x180018589  push    rbx
0x18001858a  push    rbp
0x18001858b  push    rsi
0x18001858c  push    rdi
0x18001858d  push    r14
0x18001858f  sub     rsp, 20h
0x180018593  xor     esi, esi
0x180018595  mov     rdi, rcx
0x180018598  cmp     [rcx+8], esi
0x18001859b  jbe     short loc_1800185DB
0x18001859d  mov     rcx, [rdi]
0x1800185a0  lea     rbx, [rsi+rsi*4]
0x1800185a4  mov     rcx, [rcx+rbx*8]; lpMem
0x1800185a8  call    pMemFree
0x1800185ad  mov     rcx, [rdi]
0x1800185b0  mov     rcx, [rcx+rbx*8+8]; lpMem
0x1800185b5  call    pMemFree
0x1800185ba  mov     rcx, [rdi]
0x1800185bd  mov     rcx, [rcx+rbx*8+10h]; lpMem
0x1800185c2  call    pMemFree
0x1800185c7  mov     rcx, [rdi]
0x1800185ca  mov     rcx, [rcx+rbx*8+20h]; lpMem
0x1800185cf  call    pMemFree
0x1800185d4  inc     esi
0x1800185d6  cmp     esi, [rdi+8]
0x1800185d9  jb      short loc_18001859D
0x1800185db  xor     ebp, ebp
0x1800185dd  cmp     [rdi+18h], ebp
0x1800185e0  jbe     loc_180018696
0x1800185e6  mov     rcx, [rdi+10h]
0x1800185ea  lea     rsi, ds:0[rbp*4]
0x1800185f2  add     rsi, rbp
0x1800185f5  mov     rcx, [rcx+rsi*8]; lpMem
0x1800185f9  call    pMemFree
0x1800185fe  mov     rcx, [rdi+10h]
0x180018602  mov     rcx, [rcx+rsi*8+8]; lpMem
0x180018607  call    pMemFree
0x18001860c  mov     rcx, [rdi+10h]
0x180018610  mov     rcx, [rcx+rsi*8+10h]; lpMem
0x180018615  call    pMemFree
0x18001861a  mov     rcx, [rdi+10h]
0x18001861e  cmp     dword ptr [rcx+rsi*8+18h], 0
0x180018623  jbe     short loc_180018681
0x180018625  xor     r14d, r14d
0x180018628  mov     rcx, [rcx+rsi*8+20h]
0x18001862d  lea     rbx, [r14+r14*4]
0x180018631  mov     rcx, [rcx+rbx*8]; lpMem
0x180018635  call    pMemFree
0x18001863a  mov     rax, [rdi+10h]
0x18001863e  mov     rcx, [rax+rsi*8+20h]
0x180018643  mov     rcx, [rcx+rbx*8+8]; lpMem
0x180018648  call    pMemFree
0x18001864d  mov     rax, [rdi+10h]
0x180018651  mov     rcx, [rax+rsi*8+20h]
0x180018656  mov     rcx, [rcx+rbx*8+10h]; lpMem
0x18001865b  call    pMemFree
0x180018660  mov     rax, [rdi+10h]
0x180018664  mov     rcx, [rax+rsi*8+20h]
0x180018669  mov     rcx, [rcx+rbx*8+18h]; lpMem
0x18001866e  call    pMemFree
0x180018673  mov     rcx, [rdi+10h]
0x180018677  inc     r14d
0x18001867a  cmp     r14d, [rcx+rsi*8+18h]
0x18001867f  jb      short loc_180018628
0x180018681  mov     rcx, [rcx+rsi*8+20h]; lpMem
0x180018686  call    pMemFree
0x18001868b  inc     ebp
0x18001868d  cmp     ebp, [rdi+18h]
0x180018690  jb      loc_1800185E6
0x180018696  mov     rcx, [rdi]; lpMem
0x180018699  call    pMemFree
0x18001869e  mov     rcx, [rdi+10h]; lpMem
0x1800186a2  call    pMemFree
0x1800186a7  xor     ebx, ebx
0x1800186a9  cmp     [rdi+28h], ebx
0x1800186ac  jbe     short loc_1800186C9
0x1800186ae  mov     rcx, [rdi+20h]
0x1800186b2  mov     eax, ebx
0x1800186b4  imul    rdx, rax, 58h ; 'X'
0x1800186b8  mov     rcx, [rdx+rcx+8]; lpMem
0x1800186bd  call    pMemFree
0x1800186c2  inc     ebx
0x1800186c4  cmp     ebx, [rdi+28h]
0x1800186c7  jb      short loc_1800186AE
0x1800186c9  mov     rcx, [rdi+20h]; lpMem
0x1800186cd  call    pMemFree
0x1800186d2  xor     ebx, ebx
0x1800186d4  cmp     [rdi+38h], ebx
0x1800186d7  jbe     short loc_1800186F2
0x1800186d9  mov     rcx, [rdi+30h]
0x1800186dd  mov     eax, ebx
0x1800186df  add     rax, rax
0x1800186e2  mov     rcx, [rcx+rax*8]; lpMem
0x1800186e6  call    pMemFree
0x1800186eb  inc     ebx
0x1800186ed  cmp     ebx, [rdi+38h]
0x1800186f0  jb      short loc_1800186D9
0x1800186f2  mov     rcx, [rdi+30h]; lpMem
0x1800186f6  call    pMemFree
0x1800186fb  mov     rcx, rdi; lpMem
0x1800186fe  call    pMemFree
0x180018703  add     rsp, 20h
0x180018707  pop     r14
0x180018709  pop     rdi
0x18001870a  pop     rsi
0x18001870b  pop     rbp
0x18001870c  pop     rbx
0x18001870d  retn
```
