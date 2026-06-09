# FreeFaxRegistry

- ea: `0x1800177c8`
- end: `0x180017956`
- name: `FreeFaxRegistry`
- size: `398`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e7e4`
- `0x180016a08`

## callees

- `0x18000eac0`
- `0x1800177c8`

## pseudocode

```c
__int64 __fastcall FreeFaxRegistry(LPVOID lpMem)
{
  __int64 i; // rsi
  __int64 j; // rbp
  __int64 v4; // rcx
  __int64 v5; // r14
  unsigned int k; // ebx
  unsigned int m; // ebx
  __int64 result; // rax

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
    return pMemFree(lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x1800177c8  test    rcx, rcx
0x1800177cb  jz      locret_180017955
0x1800177d1  push    rbx
0x1800177d2  push    rbp
0x1800177d3  push    rsi
0x1800177d4  push    rdi
0x1800177d5  push    r14
0x1800177d7  sub     rsp, 20h
0x1800177db  xor     esi, esi
0x1800177dd  mov     rdi, rcx
0x1800177e0  cmp     [rcx+8], esi
0x1800177e3  jbe     short loc_180017823
0x1800177e5  mov     rcx, [rdi]
0x1800177e8  lea     rbx, [rsi+rsi*4]
0x1800177ec  mov     rcx, [rcx+rbx*8]; lpMem
0x1800177f0  call    pMemFree
0x1800177f5  mov     rcx, [rdi]
0x1800177f8  mov     rcx, [rcx+rbx*8+8]; lpMem
0x1800177fd  call    pMemFree
0x180017802  mov     rcx, [rdi]
0x180017805  mov     rcx, [rcx+rbx*8+10h]; lpMem
0x18001780a  call    pMemFree
0x18001780f  mov     rcx, [rdi]
0x180017812  mov     rcx, [rcx+rbx*8+20h]; lpMem
0x180017817  call    pMemFree
0x18001781c  inc     esi
0x18001781e  cmp     esi, [rdi+8]
0x180017821  jb      short loc_1800177E5
0x180017823  xor     ebp, ebp
0x180017825  cmp     [rdi+18h], ebp
0x180017828  jbe     loc_1800178DE
0x18001782e  mov     rcx, [rdi+10h]
0x180017832  lea     rsi, ds:0[rbp*4]
0x18001783a  add     rsi, rbp
0x18001783d  mov     rcx, [rcx+rsi*8]; lpMem
0x180017841  call    pMemFree
0x180017846  mov     rcx, [rdi+10h]
0x18001784a  mov     rcx, [rcx+rsi*8+8]; lpMem
0x18001784f  call    pMemFree
0x180017854  mov     rcx, [rdi+10h]
0x180017858  mov     rcx, [rcx+rsi*8+10h]; lpMem
0x18001785d  call    pMemFree
0x180017862  mov     rcx, [rdi+10h]
0x180017866  cmp     dword ptr [rcx+rsi*8+18h], 0
0x18001786b  jbe     short loc_1800178C9
0x18001786d  xor     r14d, r14d
0x180017870  mov     rcx, [rcx+rsi*8+20h]
0x180017875  lea     rbx, [r14+r14*4]
0x180017879  mov     rcx, [rcx+rbx*8]; lpMem
0x18001787d  call    pMemFree
0x180017882  mov     rax, [rdi+10h]
0x180017886  mov     rcx, [rax+rsi*8+20h]
0x18001788b  mov     rcx, [rcx+rbx*8+8]; lpMem
0x180017890  call    pMemFree
0x180017895  mov     rax, [rdi+10h]
0x180017899  mov     rcx, [rax+rsi*8+20h]
0x18001789e  mov     rcx, [rcx+rbx*8+10h]; lpMem
0x1800178a3  call    pMemFree
0x1800178a8  mov     rax, [rdi+10h]
0x1800178ac  mov     rcx, [rax+rsi*8+20h]
0x1800178b1  mov     rcx, [rcx+rbx*8+18h]; lpMem
0x1800178b6  call    pMemFree
0x1800178bb  mov     rcx, [rdi+10h]
0x1800178bf  inc     r14d
0x1800178c2  cmp     r14d, [rcx+rsi*8+18h]
0x1800178c7  jb      short loc_180017870
0x1800178c9  mov     rcx, [rcx+rsi*8+20h]; lpMem
0x1800178ce  call    pMemFree
0x1800178d3  inc     ebp
0x1800178d5  cmp     ebp, [rdi+18h]
0x1800178d8  jb      loc_18001782E
0x1800178de  mov     rcx, [rdi]; lpMem
0x1800178e1  call    pMemFree
0x1800178e6  mov     rcx, [rdi+10h]; lpMem
0x1800178ea  call    pMemFree
0x1800178ef  xor     ebx, ebx
0x1800178f1  cmp     [rdi+28h], ebx
0x1800178f4  jbe     short loc_180017911
0x1800178f6  mov     rcx, [rdi+20h]
0x1800178fa  mov     eax, ebx
0x1800178fc  imul    rdx, rax, 58h ; 'X'
0x180017900  mov     rcx, [rdx+rcx+8]; lpMem
0x180017905  call    pMemFree
0x18001790a  inc     ebx
0x18001790c  cmp     ebx, [rdi+28h]
0x18001790f  jb      short loc_1800178F6
0x180017911  mov     rcx, [rdi+20h]; lpMem
0x180017915  call    pMemFree
0x18001791a  xor     ebx, ebx
0x18001791c  cmp     [rdi+38h], ebx
0x18001791f  jbe     short loc_18001793A
0x180017921  mov     rcx, [rdi+30h]
0x180017925  mov     eax, ebx
0x180017927  add     rax, rax
0x18001792a  mov     rcx, [rcx+rax*8]; lpMem
0x18001792e  call    pMemFree
0x180017933  inc     ebx
0x180017935  cmp     ebx, [rdi+38h]
0x180017938  jb      short loc_180017921
0x18001793a  mov     rcx, [rdi+30h]; lpMem
0x18001793e  call    pMemFree
0x180017943  mov     rcx, rdi; lpMem
0x180017946  call    pMemFree
0x18001794b  add     rsp, 20h
0x18001794f  pop     r14
0x180017951  pop     rdi
0x180017952  pop     rsi
0x180017953  pop     rbp
0x180017954  pop     rbx
0x180017955  retn
```
