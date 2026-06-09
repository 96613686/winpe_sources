# bReadRegistryNTF

- ea: `0x18001c62c`
- end: `0x18001c788`
- name: `bReadRegistryNTF`
- size: `348`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x18001c62c`
- `0x18001c790`
- `0x18001c88c`
- `0x18001cb80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001c748`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001c765`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001c748`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001c765`
- `KERNEL32!LocalFree` at `0x18001c722`
- `KERNEL32!LocalFree` at `0x18001c722`
- `KERNEL32!LocalAlloc` at `0x18001c691`
- `KERNEL32!LocalAlloc` at `0x18001c691`

## pseudocode

```c
__int64 __fastcall bReadRegistryNTF(__int64 a1)
{
  __int64 v1; // rsi
  int v2; // ebp
  _QWORD *v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // r14
  HLOCAL v7; // r15
  char GlyphSetEntry; // al
  _QWORD *v9; // rcx

  v1 = *(_QWORD *)(a1 + 3656);
  v2 = 0;
  v4 = (_QWORD *)(v1 + 40);
  *(_DWORD *)(v1 + 20) = 0;
  *(_QWORD *)(v1 + 40) = 0;
  *(_DWORD *)(v1 + 60) = 0;
  *(_QWORD *)(v1 + 80) = 0;
  v5 = *(_QWORD *)(a1 + 3648);
  if ( v5 )
  {
    if ( *(_DWORD *)(v5 + 44) )
      v6 = v5 + *(unsigned int *)(v5 + 44);
    else
      v6 = 0;
    v7 = LocalAlloc(0x40u, 48 * *(_DWORD *)(v5 + 40));
    if ( !v7 )
    {
LABEL_13:
      *v4 = 0;
      return 0;
    }
    if ( *(int *)(v5 + 40) > 0 )
    {
      while ( (unsigned int)bStoreEntryData(v5, (unsigned int *)(v6 + 32LL * v2), (__int64)v7, v2, 7) )
      {
        if ( ++v2 >= *(_DWORD *)(v5 + 40) )
          goto LABEL_9;
      }
      LocalFree(v7);
      goto LABEL_13;
    }
LABEL_9:
    *(_DWORD *)(v1 + 20) = v2;
    *v4 = v7;
    GlyphSetEntry = pCreateGlyphSetEntry(*(_QWORD *)(a1 + 3648), 18, (int *)(v1 + 60), (const void **)(v1 + 80));
    v9 = (_QWORD *)*v4;
    if ( !GlyphSetEntry )
    {
      vFreeDataEntry(v9, *(_DWORD *)(v1 + 20));
      *v4 = 0;
      *(_DWORD *)(v1 + 20) = 0;
      return 0;
    }
    qsort(v9, *(int *)(v1 + 20), 0x30u, (_CoreCrtNonSecureSearchSortCompareFunction)compare);
    qsort(*(void **)(v1 + 80), *(int *)(v1 + 60), 0x30u, (_CoreCrtNonSecureSearchSortCompareFunction)compare);
  }
  return 1;
}

```

## disassembly

```asm
0x18001c62c  push    rbx
0x18001c62e  push    rbp
0x18001c62f  push    rsi
0x18001c630  push    rdi
0x18001c631  push    r12
0x18001c633  push    r13
0x18001c635  push    r14
0x18001c637  push    r15
0x18001c639  sub     rsp, 38h
0x18001c63d  mov     rsi, [rcx+0E48h]
0x18001c644  xor     ebp, ebp
0x18001c646  mov     r13, rcx
0x18001c649  lea     rdi, [rsi+28h]
0x18001c64d  mov     [rsi+14h], ebp
0x18001c650  lea     r12, [rsi+3Ch]
0x18001c654  mov     [rdi], rbp
0x18001c657  mov     [r12], ebp
0x18001c65b  mov     [rsi+50h], rbp
0x18001c65f  mov     rbx, [rcx+0E40h]
0x18001c666  test    rbx, rbx
0x18001c669  jz      loc_18001C771
0x18001c66f  cmp     [rbx+2Ch], ebp
0x18001c672  jz      short loc_18001C67D
0x18001c674  mov     r14d, [rbx+2Ch]
0x18001c678  add     r14, rbx
0x18001c67b  jmp     short loc_18001C680
0x18001c67d  mov     r14, rbp
0x18001c680  mov     eax, [rbx+28h]
0x18001c683  lea     ecx, [rax+rax*2]
0x18001c686  shl     ecx, 4
0x18001c689  movsxd  rdx, ecx; uBytes
0x18001c68c  mov     ecx, 40h ; '@'; uFlags
0x18001c691  call    cs:__imp_LocalAlloc
0x18001c698  nop     dword ptr [rax+rax+00h]
0x18001c69d  mov     r15, rax
0x18001c6a0  test    rax, rax
0x18001c6a3  jnz     short loc_18001C6AD
0x18001c6a5  mov     rax, rbp
0x18001c6a8  jmp     loc_18001C730
0x18001c6ad  cmp     [rbx+28h], ebp
0x18001c6b0  jle     short loc_18001C6DD
0x18001c6b2  movsxd  rdx, ebp
0x18001c6b5  mov     r9d, ebp
0x18001c6b8  shl     rdx, 5
0x18001c6bc  mov     r8, r15
0x18001c6bf  add     rdx, r14
0x18001c6c2  mov     [rsp+78h+var_58], 7
0x18001c6ca  mov     rcx, rbx
0x18001c6cd  call    bStoreEntryData
0x18001c6d2  test    eax, eax
0x18001c6d4  jz      short loc_18001C71F
0x18001c6d6  inc     ebp
0x18001c6d8  cmp     ebp, [rbx+28h]
0x18001c6db  jl      short loc_18001C6B2
0x18001c6dd  mov     [rsi+14h], ebp
0x18001c6e0  lea     rbx, [rsi+50h]
0x18001c6e4  mov     [rdi], r15
0x18001c6e7  mov     r9, rbx
0x18001c6ea  mov     rcx, [r13+0E40h]
0x18001c6f1  mov     r8, r12
0x18001c6f4  mov     edx, 12h
0x18001c6f9  call    pCreateGlyphSetEntry
0x18001c6fe  mov     rcx, [rdi]; hMem
0x18001c701  test    al, al
0x18001c703  jnz     short loc_18001C735
0x18001c705  mov     edx, [rsi+14h]
0x18001c708  call    vFreeDataEntry
0x18001c70d  mov     qword ptr [rdi], 0
0x18001c714  mov     dword ptr [rsi+14h], 0
0x18001c71b  xor     eax, eax
0x18001c71d  jmp     short loc_18001C776
0x18001c71f  mov     rcx, r15; hMem
0x18001c722  call    cs:__imp_LocalFree
0x18001c729  nop     dword ptr [rax+rax+00h]
0x18001c72e  xor     eax, eax
0x18001c730  mov     [rdi], rax
0x18001c733  jmp     short loc_18001C71B
0x18001c735  movsxd  rdx, dword ptr [rsi+14h]; NumOfElements
0x18001c739  lea     r9, compare; CompareFunction
0x18001c740  mov     esi, 30h ; '0'
0x18001c745  mov     r8d, esi; SizeOfElements
0x18001c748  call    cs:__imp_qsort
0x18001c74f  nop     dword ptr [rax+rax+00h]
0x18001c754  movsxd  rdx, dword ptr [r12]; NumOfElements
0x18001c758  lea     r9, compare; CompareFunction
0x18001c75f  mov     rcx, [rbx]; Base
0x18001c762  mov     r8d, esi; SizeOfElements
0x18001c765  call    cs:__imp_qsort
0x18001c76c  nop     dword ptr [rax+rax+00h]
0x18001c771  mov     eax, 1
0x18001c776  add     rsp, 38h
0x18001c77a  pop     r15
0x18001c77c  pop     r14
0x18001c77e  pop     r13
0x18001c780  pop     r12
0x18001c782  pop     rdi
0x18001c783  pop     rsi
0x18001c784  pop     rbp
0x18001c785  pop     rbx
0x18001c786  retn
```
