# pCreateGlyphSetEntry

- ea: `0x18001c88c`
- end: `0x18001c9a2`
- name: `pCreateGlyphSetEntry`
- size: `278`
- prototype: `char __fastcall(__int64, int, int *, const void **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c1d8`
- `0x18001c62c`

## callees

- `0x18001c88c`
- `0x18001cb80`
- `0x18005e0c4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001c91a`
- `KERNEL32!LocalFree` at `0x18001c91a`
- `KERNEL32!LocalAlloc` at `0x18001c8d5`
- `KERNEL32!LocalAlloc` at `0x18001c8d5`

## pseudocode

```c
char __fastcall pCreateGlyphSetEntry(__int64 a1, int a2, int *a3, const void **a4)
{
  int v8; // edi
  __int64 v9; // r14
  _DWORD *v10; // rax
  _DWORD *v11; // r15
  char result; // al
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  int i; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax

  v8 = 48 * *a3;
  if ( *(_DWORD *)(a1 + 36) )
    v9 = a1 + *(unsigned int *)(a1 + 36);
  else
    v9 = 0;
  v10 = LocalAlloc(0x40u, v8 + 48 * *(_DWORD *)(a1 + 32));
  v11 = v10;
  if ( v10 )
  {
    if ( v8 > 0 )
    {
      memcpy_0(v10, *a4, v8);
      if ( *a4 )
        LocalFree((HLOCAL)*a4);
    }
    v13 = *a3;
    v14 = *a3;
    v15 = *(_DWORD *)(a1 + 32);
    for ( i = v15 + *a3; v13 < i; i = *a3 + v15 )
    {
      v17 = 32LL * (v13 - v14);
      v18 = 6LL * v13;
      v11[2 * v18] = *(_DWORD *)(v17 + v9 + 4);
      v11[2 * v18 + 1] = *(_DWORD *)(v17 + v9 + 12);
      v11[2 * v18 + 4] = a2;
      if ( *(_DWORD *)(v17 + v9) )
        v19 = a1 + *(unsigned int *)(v17 + v9);
      else
        v19 = 0;
      *(_QWORD *)&v11[12 * v13++ + 2] = v19;
      v15 = *(_DWORD *)(a1 + 32);
      v14 = *a3;
    }
    result = 1;
    *a3 = v15 + v14;
    *a4 = v11;
  }
  else
  {
    vFreeDataEntry(*a4, *a3);
    *a4 = 0;
    result = 0;
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001c88c  push    rbx
0x18001c88e  push    rbp
0x18001c88f  push    rsi
0x18001c890  push    rdi
0x18001c891  push    r12
0x18001c893  push    r14
0x18001c895  push    r15
0x18001c897  sub     rsp, 20h
0x18001c89b  mov     eax, [r8]
0x18001c89e  mov     rsi, r9
0x18001c8a1  mov     rbx, r8
0x18001c8a4  mov     r12d, edx
0x18001c8a7  mov     rbp, rcx
0x18001c8aa  lea     edi, [rax+rax*2]
0x18001c8ad  shl     edi, 4
0x18001c8b0  cmp     dword ptr [rcx+24h], 0
0x18001c8b4  jz      short loc_18001C8BF
0x18001c8b6  mov     r14d, [rcx+24h]
0x18001c8ba  add     r14, rcx
0x18001c8bd  jmp     short loc_18001C8C2
0x18001c8bf  xor     r14d, r14d
0x18001c8c2  mov     eax, [rcx+20h]
0x18001c8c5  lea     ecx, [rax+rax*2]
0x18001c8c8  shl     ecx, 4
0x18001c8cb  add     ecx, edi
0x18001c8cd  movsxd  rdx, ecx; uBytes
0x18001c8d0  mov     ecx, 40h ; '@'; uFlags
0x18001c8d5  call    cs:__imp_LocalAlloc
0x18001c8dc  nop     dword ptr [rax+rax+00h]
0x18001c8e1  mov     r15, rax
0x18001c8e4  test    rax, rax
0x18001c8e7  jnz     short loc_18001C900
0x18001c8e9  mov     edx, [rbx]
0x18001c8eb  mov     rcx, [rsi]; hMem
0x18001c8ee  call    vFreeDataEntry
0x18001c8f3  mov     [rsi], r15
0x18001c8f6  xor     al, al
0x18001c8f8  mov     [rbx], r15d
0x18001c8fb  jmp     loc_18001C992
0x18001c900  test    edi, edi
0x18001c902  jle     short loc_18001C926
0x18001c904  mov     rdx, [rsi]; Src
0x18001c907  mov     rcx, r15; void *
0x18001c90a  movsxd  r8, edi; Size
0x18001c90d  call    memcpy_0
0x18001c912  mov     rcx, [rsi]; hMem
0x18001c915  test    rcx, rcx
0x18001c918  jz      short loc_18001C926
0x18001c91a  call    cs:__imp_LocalFree
0x18001c921  nop     dword ptr [rax+rax+00h]
0x18001c926  mov     edx, [rbx]
0x18001c928  mov     ecx, edx
0x18001c92a  mov     r8d, [rbp+20h]
0x18001c92e  lea     eax, [r8+rdx]
0x18001c932  cmp     edx, eax
0x18001c934  jge     short loc_18001C988
0x18001c936  mov     eax, edx
0x18001c938  sub     eax, ecx
0x18001c93a  movsxd  rcx, eax
0x18001c93d  shl     rcx, 5
0x18001c941  movsxd  rax, edx
0x18001c944  lea     r8, [rax+rax*2]
0x18001c948  mov     eax, [rcx+r14+4]
0x18001c94d  add     r8, r8
0x18001c950  mov     [r15+r8*8], eax
0x18001c954  mov     eax, [rcx+r14+0Ch]
0x18001c959  mov     [r15+r8*8+4], eax
0x18001c95e  mov     [r15+r8*8+10h], r12d
0x18001c963  cmp     dword ptr [rcx+r14], 0
0x18001c968  jz      short loc_18001C973
0x18001c96a  mov     eax, [rcx+r14]
0x18001c96e  add     rax, rbp
0x18001c971  jmp     short loc_18001C975
0x18001c973  xor     eax, eax
0x18001c975  mov     [r15+r8*8+8], rax
0x18001c97a  inc     edx
0x18001c97c  mov     r8d, [rbp+20h]
0x18001c980  mov     ecx, [rbx]
0x18001c982  lea     eax, [rcx+r8]
0x18001c986  jmp     short loc_18001C932
0x18001c988  add     ecx, r8d
0x18001c98b  mov     al, 1
0x18001c98d  mov     [rbx], ecx
0x18001c98f  mov     [rsi], r15
0x18001c992  add     rsp, 20h
0x18001c996  pop     r15
0x18001c998  pop     r14
0x18001c99a  pop     r12
0x18001c99c  pop     rdi
0x18001c99d  pop     rsi
0x18001c99e  pop     rbp
0x18001c99f  pop     rbx
0x18001c9a0  retn
```
