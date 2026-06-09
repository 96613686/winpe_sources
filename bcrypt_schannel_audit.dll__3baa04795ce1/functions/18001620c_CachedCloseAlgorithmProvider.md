# CachedCloseAlgorithmProvider

- ea: `0x18001620c`
- end: `0x180016291`
- name: `CachedCloseAlgorithmProvider`
- size: `133`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180014084`
- `0x180014d6c`
- `0x180016b60`
- `0x180017420`

## callees

- `0x180005b00`
- `0x18001620c`
- `0x1800164bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016269`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016269`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180016230`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180016230`

## pseudocode

```c
__int64 __fastcall CachedCloseAlgorithmProvider(BCRYPT_ALG_HANDLE hAlgorithm)
{
  __int64 Cache; // rbx
  int v3; // esi
  unsigned int v4; // edi
  int i; // edx
  __int64 v6; // rcx

  Cache = getCache();
  if ( !Cache )
    return (unsigned int)BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  v3 = 0;
  v4 = 0;
  AcquireSRWLockShared(g_pHandleCacheLock);
  for ( i = 0; i < 8; ++i )
  {
    v6 = 224LL * i;
    if ( *(BCRYPT_ALG_HANDLE *)(v6 + Cache) == hAlgorithm )
    {
      _InterlockedDecrement64((volatile signed __int64 *)(v6 + Cache + 8));
      v3 = 1;
      break;
    }
  }
  ReleaseSRWLockShared(g_pHandleCacheLock);
  if ( !v3 )
    return (unsigned int)BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  return v4;
}

```

## disassembly

```asm
0x18001620c  push    rbx
0x18001620e  push    rbp
0x18001620f  push    rsi
0x180016210  push    rdi
0x180016211  sub     rsp, 28h
0x180016215  mov     rbp, rcx
0x180016218  call    getCache
0x18001621d  mov     rbx, rax
0x180016220  test    rax, rax
0x180016223  jz      short loc_180016279
0x180016225  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x18001622c  xor     esi, esi
0x18001622e  xor     edi, edi
0x180016230  call    cs:__imp_AcquireSRWLockShared
0x180016237  nop     dword ptr [rax+rax+00h]
0x18001623c  xor     edx, edx
0x18001623e  cmp     edx, 8
0x180016241  jge     short loc_180016262
0x180016243  movsxd  rax, edx
0x180016246  imul    rcx, rax, 0E0h
0x18001624d  cmp     [rcx+rbx], rbp
0x180016251  jz      short loc_180016257
0x180016253  inc     edx
0x180016255  jmp     short loc_18001623E
0x180016257  lock dec qword ptr [rcx+rbx+8]
0x18001625d  mov     esi, 1
0x180016262  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x180016269  call    cs:__imp_ReleaseSRWLockShared
0x180016270  nop     dword ptr [rax+rax+00h]
0x180016275  test    esi, esi
0x180016277  jnz     short loc_180016285
0x180016279  xor     edx, edx; dwFlags
0x18001627b  mov     rcx, rbp; hAlgorithm
0x18001627e  call    BCryptCloseAlgorithmProvider
0x180016283  mov     edi, eax
0x180016285  mov     eax, edi
0x180016287  add     rsp, 28h
0x18001628b  pop     rdi
0x18001628c  pop     rsi
0x18001628d  pop     rbp
0x18001628e  pop     rbx
0x18001628f  retn
```
