# addEntryToCache

- ea: `0x180016318`
- end: `0x180016416`
- name: `addEntryToCache`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016298`

## callees

- `0x180005b00`
- `0x18000da50`
- `0x180016318`
- `0x1800164bc`
- `0x18001b7a9`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001633f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001633f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016400`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016400`

## pseudocode

```c
void __fastcall addEntryToCache(__int64 a1, const wchar_t *a2)
{
  __int64 Cache; // rdi
  int i; // r8d
  wchar_t *v6; // rbx
  unsigned int v7; // r8d
  int j; // edx

  Cache = getCache();
  if ( Cache )
  {
    AcquireSRWLockExclusive(g_pHandleCacheLock);
    for ( i = 0; i < 8; ++i )
    {
      v6 = (wchar_t *)(Cache + 224LL * i);
      if ( !*(_QWORD *)v6 )
      {
        if ( v6 )
        {
LABEL_12:
          if ( StringCchCopyW(v6 + 12, 0x21u, a2) >= 0 )
          {
            *((_QWORD *)v6 + 2) = 0;
            *(_QWORD *)v6 = a1;
            *((_QWORD *)v6 + 1) = 1;
          }
          else
          {
            memset_0(v6, 0, 0xE0u);
          }
          goto LABEL_15;
        }
        break;
      }
    }
    v7 = g_handleCacheNextReplace;
    for ( j = 0; j < 8; ++j )
    {
      v6 = (wchar_t *)(Cache + 224LL * v7);
      v7 = ((_BYTE)v7 + 1) & 7;
      g_handleCacheNextReplace = v7;
      if ( !*((_QWORD *)v6 + 1) )
      {
        BCryptCloseAlgorithmProvider(*(BCRYPT_ALG_HANDLE *)v6, 0);
        memset_0(v6, 0, 0xE0u);
        goto LABEL_12;
      }
    }
LABEL_15:
    ReleaseSRWLockExclusive(g_pHandleCacheLock);
  }
}

```

## disassembly

```asm
0x180016318  push    rbx
0x18001631a  push    rbp
0x18001631b  push    rsi
0x18001631c  push    rdi
0x18001631d  sub     rsp, 28h
0x180016321  mov     rbp, rdx
0x180016324  mov     rsi, rcx
0x180016327  call    getCache
0x18001632c  mov     rdi, rax
0x18001632f  test    rax, rax
0x180016332  jz      loc_18001640C
0x180016338  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x18001633f  call    cs:__imp_AcquireSRWLockExclusive
0x180016346  nop     dword ptr [rax+rax+00h]
0x18001634b  xor     r8d, r8d
0x18001634e  cmp     r8d, 8
0x180016352  jge     short loc_180016371
0x180016354  movsxd  rax, r8d
0x180016357  imul    rbx, rax, 0E0h
0x18001635e  add     rbx, rdi
0x180016361  cmp     qword ptr [rbx], 0
0x180016365  jz      short loc_18001636C
0x180016367  inc     r8d
0x18001636a  jmp     short loc_18001634E
0x18001636c  test    rbx, rbx
0x18001636f  jnz     short loc_1800163BF
0x180016371  mov     r8d, cs:g_handleCacheNextReplace
0x180016378  xor     edx, edx
0x18001637a  cmp     edx, 8
0x18001637d  jge     short loc_1800163F9
0x18001637f  mov     eax, r8d
0x180016382  imul    rbx, rax, 0E0h
0x180016389  add     rbx, rdi
0x18001638c  inc     r8d
0x18001638f  and     r8d, 7
0x180016393  mov     cs:g_handleCacheNextReplace, r8d
0x18001639a  cmp     qword ptr [rbx+8], 0
0x18001639f  jz      short loc_1800163A5
0x1800163a1  inc     edx
0x1800163a3  jmp     short loc_18001637A
0x1800163a5  mov     rcx, [rbx]; hAlgorithm
0x1800163a8  xor     edx, edx; dwFlags
0x1800163aa  call    BCryptCloseAlgorithmProvider
0x1800163af  xor     edx, edx; Val
0x1800163b1  mov     r8d, 0E0h; Size
0x1800163b7  mov     rcx, rbx; void *
0x1800163ba  call    memset_0
0x1800163bf  lea     rcx, [rbx+18h]; pszDest
0x1800163c3  mov     r8, rbp; pszSrc
0x1800163c6  mov     edx, 21h ; '!'; cchDest
0x1800163cb  call    StringCchCopyW
0x1800163d0  test    eax, eax
0x1800163d2  jns     short loc_1800163E6
0x1800163d4  xor     edx, edx; Val
0x1800163d6  mov     r8d, 0E0h; Size
0x1800163dc  mov     rcx, rbx; void *
0x1800163df  call    memset_0
0x1800163e4  jmp     short loc_1800163F9
0x1800163e6  mov     qword ptr [rbx+10h], 0
0x1800163ee  mov     [rbx], rsi
0x1800163f1  mov     qword ptr [rbx+8], 1
0x1800163f9  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x180016400  call    cs:__imp_ReleaseSRWLockExclusive
0x180016407  nop     dword ptr [rax+rax+00h]
0x18001640c  add     rsp, 28h
0x180016410  pop     rdi
0x180016411  pop     rsi
0x180016412  pop     rbp
0x180016413  pop     rbx
0x180016414  retn
```
