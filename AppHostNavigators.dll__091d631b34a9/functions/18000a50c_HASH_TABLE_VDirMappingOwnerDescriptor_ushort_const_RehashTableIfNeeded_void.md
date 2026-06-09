# HASH_TABLE<VDirMappingOwnerDescriptor,ushort const *>::RehashTableIfNeeded(void)

- ea: `0x18000a50c`
- end: `0x18000a5fa`
- name: `?RehashTableIfNeeded@?$HASH_TABLE@VVDirMappingOwnerDescriptor@@PEBG@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a2fc`
- `0x180012cc8`

## callees

- `0x18000a50c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000a5d8`
- `KERNEL32!HeapFree` at `0x18000a5d8`
- `KERNEL32!GetProcessHeap` at `0x18000a552`
- `KERNEL32!GetProcessHeap` at `0x18000a5ca`
- `KERNEL32!GetProcessHeap` at `0x18000a552`
- `KERNEL32!GetProcessHeap` at `0x18000a5ca`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a5e9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a5e9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a52c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a52c`
- `KERNEL32!HeapAlloc` at `0x18000a563`
- `KERNEL32!HeapAlloc` at `0x18000a563`

## pseudocode

```c
void __fastcall HASH_TABLE<VDirMappingOwnerDescriptor,unsigned short const *>::RehashTableIfNeeded(__int64 a1)
{
  unsigned int v2; // esi
  HANDLE ProcessHeap; // rax
  char *v4; // r14
  __int64 i; // r8
  char **v6; // r9
  char *v7; // r10
  char *v8; // rdx
  char *j; // rax
  void *v10; // rbx
  HANDLE v11; // rax

  if ( *(_DWORD *)(a1 + 20) > (unsigned int)(2 * *(_DWORD *)(a1 + 16)) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 24));
    v2 = 2 * *(_DWORD *)(a1 + 16);
    if ( *(_DWORD *)(a1 + 20) > v2 && v2 < 0x1FFFFFFF )
    {
      ProcessHeap = GetProcessHeap();
      v4 = (char *)HeapAlloc(ProcessHeap, 8u, 8LL * v2);
      if ( v4 )
      {
        for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 16); i = (unsigned int)(i + 1) )
        {
          v6 = *(char ***)(*(_QWORD *)(a1 + 8) + 8 * i);
          if ( v6 )
          {
            do
            {
              v7 = *v6;
              v8 = &v4[8 * (*((_DWORD *)v6 + 4) % v2)];
              for ( j = *(char **)v8; j && *((_DWORD *)j + 4) <= *((_DWORD *)v6 + 4); j = *(char **)j )
                v8 = j;
              *v6 = j;
              *(_QWORD *)v8 = v6;
              v6 = (char **)v7;
            }
            while ( v7 );
          }
        }
        v10 = *(void **)(a1 + 8);
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v10);
        *(_QWORD *)(a1 + 8) = v4;
        *(_DWORD *)(a1 + 16) = v2;
      }
    }
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 24));
  }
}

```

## disassembly

```asm
0x18000a50c  push    rbx
0x18000a50e  push    rbp
0x18000a50f  push    rsi
0x18000a510  push    rdi
0x18000a511  push    r14
0x18000a513  sub     rsp, 20h
0x18000a517  mov     eax, [rcx+10h]
0x18000a51a  mov     rdi, rcx
0x18000a51d  add     eax, eax
0x18000a51f  cmp     [rcx+14h], eax
0x18000a522  jbe     loc_18000A5EF
0x18000a528  add     rcx, 18h; SRWLock
0x18000a52c  call    cs:__imp_AcquireSRWLockExclusive
0x18000a532  mov     esi, [rdi+10h]
0x18000a535  add     esi, esi
0x18000a537  cmp     [rdi+14h], esi
0x18000a53a  jbe     loc_18000A5E5
0x18000a540  cmp     esi, 1FFFFFFFh
0x18000a546  jnb     loc_18000A5E5
0x18000a54c  mov     ebx, esi
0x18000a54e  shl     rbx, 3
0x18000a552  call    cs:__imp_GetProcessHeap
0x18000a558  mov     r8, rbx; dwBytes
0x18000a55b  mov     edx, 8; dwFlags
0x18000a560  mov     rcx, rax; hHeap
0x18000a563  call    cs:__imp_HeapAlloc
0x18000a569  mov     r14, rax
0x18000a56c  test    rax, rax
0x18000a56f  jz      short loc_18000A5E5
0x18000a571  xor     r8d, r8d
0x18000a574  cmp     [rdi+10h], r8d
0x18000a578  jbe     short loc_18000A5C6
0x18000a57a  mov     rax, [rdi+8]
0x18000a57e  mov     r9, [rax+r8*8]
0x18000a582  test    r9, r9
0x18000a585  jz      short loc_18000A5BD
0x18000a587  mov     r11d, [r9+10h]
0x18000a58b  xor     edx, edx
0x18000a58d  mov     r10, [r9]
0x18000a590  mov     eax, r11d
0x18000a593  div     esi
0x18000a595  lea     rdx, [r14+rdx*8]
0x18000a599  mov     rax, [rdx]
0x18000a59c  jmp     short loc_18000A5AA
0x18000a59e  cmp     [rax+10h], r11d
0x18000a5a2  ja      short loc_18000A5AF
0x18000a5a4  mov     rdx, rax
0x18000a5a7  mov     rax, [rax]
0x18000a5aa  test    rax, rax
0x18000a5ad  jnz     short loc_18000A59E
0x18000a5af  mov     [r9], rax
0x18000a5b2  mov     [rdx], r9
0x18000a5b5  mov     r9, r10
0x18000a5b8  test    r10, r10
0x18000a5bb  jnz     short loc_18000A587
0x18000a5bd  inc     r8d
0x18000a5c0  cmp     r8d, [rdi+10h]
0x18000a5c4  jb      short loc_18000A57A
0x18000a5c6  mov     rbx, [rdi+8]
0x18000a5ca  call    cs:__imp_GetProcessHeap
0x18000a5d0  mov     r8, rbx; lpMem
0x18000a5d3  xor     edx, edx; dwFlags
0x18000a5d5  mov     rcx, rax; hHeap
0x18000a5d8  call    cs:__imp_HeapFree
0x18000a5de  mov     [rdi+8], r14
0x18000a5e2  mov     [rdi+10h], esi
0x18000a5e5  lea     rcx, [rdi+18h]; SRWLock
0x18000a5e9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a5ef  add     rsp, 20h
0x18000a5f3  pop     r14
0x18000a5f5  pop     rdi
0x18000a5f6  pop     rsi
0x18000a5f7  pop     rbp
0x18000a5f8  pop     rbx
0x18000a5f9  retn
```
