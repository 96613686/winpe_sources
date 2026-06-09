# findEntryInCache

- ea: `0x18001641c`
- end: `0x1800164b6`
- name: `findEntryInCache`
- size: `154`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016298`

## callees

- `0x18001641c`
- `0x1800164bc`
- `0x18001b7c1`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016493`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016493`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001643e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001643e`

## pseudocode

```c
__int64 __fastcall findEntryInCache(wchar_t *String1)
{
  __int64 result; // rax
  __int64 v3; // rbx
  unsigned int v4; // esi
  __int64 v5; // rdi
  __int64 v6; // rbp

  result = getCache();
  v3 = result;
  if ( result )
  {
    AcquireSRWLockShared(g_pHandleCacheLock);
    v4 = 0;
    while ( 1 )
    {
      v5 = 224LL * v4;
      v6 = *(_QWORD *)(v5 + v3);
      if ( v6 )
      {
        if ( !wcsncmp_0(String1, (const wchar_t *)(v5 + v3 + 24), 0x21u)
          && !*(_DWORD *)(v5 + v3 + 20)
          && !*(_DWORD *)(v5 + v3 + 16) )
        {
          break;
        }
      }
      if ( (int)++v4 >= 8 )
      {
        v6 = 0;
        goto LABEL_9;
      }
    }
    _InterlockedIncrement64((volatile signed __int64 *)(v5 + v3 + 8));
LABEL_9:
    ReleaseSRWLockShared(g_pHandleCacheLock);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18001641c  push    rbx
0x18001641e  push    rbp
0x18001641f  push    rsi
0x180016420  push    rdi
0x180016421  push    r14
0x180016423  sub     rsp, 20h
0x180016427  mov     r14, rcx
0x18001642a  call    getCache
0x18001642f  mov     rbx, rax
0x180016432  test    rax, rax
0x180016435  jz      short loc_1800164A2
0x180016437  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x18001643e  call    cs:__imp_AcquireSRWLockShared
0x180016445  nop     dword ptr [rax+rax+00h]
0x18001644a  xor     esi, esi
0x18001644c  mov     eax, esi
0x18001644e  imul    rdi, rax, 0E0h
0x180016455  mov     rbp, [rdi+rbx]
0x180016459  test    rbp, rbp
0x18001645c  jz      short loc_180016483
0x18001645e  lea     rdx, [rbx+18h]
0x180016462  mov     r8d, 21h ; '!'; MaxCount
0x180016468  add     rdx, rdi; String2
0x18001646b  mov     rcx, r14; String1
0x18001646e  call    wcsncmp_0
0x180016473  test    eax, eax
0x180016475  jnz     short loc_180016483
0x180016477  cmp     [rdi+rbx+14h], eax
0x18001647b  jnz     short loc_180016483
0x18001647d  cmp     [rdi+rbx+10h], eax
0x180016481  jz      short loc_1800164AE
0x180016483  inc     esi
0x180016485  cmp     esi, 8
0x180016488  jl      short loc_18001644C
0x18001648a  xor     ebp, ebp
0x18001648c  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x180016493  call    cs:__imp_ReleaseSRWLockShared
0x18001649a  nop     dword ptr [rax+rax+00h]
0x18001649f  mov     rax, rbp
0x1800164a2  add     rsp, 20h
0x1800164a6  pop     r14
0x1800164a8  pop     rdi
0x1800164a9  pop     rsi
0x1800164aa  pop     rbp
0x1800164ab  pop     rbx
0x1800164ac  retn
0x1800164ae  lock inc qword ptr [rdi+rbx+8]
0x1800164b4  jmp     short loc_18001648C
```
