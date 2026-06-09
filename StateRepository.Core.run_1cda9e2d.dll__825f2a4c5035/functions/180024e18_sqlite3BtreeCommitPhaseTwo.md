# sqlite3BtreeCommitPhaseTwo

- ea: `0x180024e18`
- end: `0x180024ead`
- name: `sqlite3BtreeCommitPhaseTwo`
- size: `149`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180024f90`
- `0x18005a498`
- `0x18008c010`

## callees

- `0x180023ad4`
- `0x180023b30`
- `0x180024b1c`
- `0x180024e18`
- `0x1800257ac`
- `0x18006a758`
- `0x180092ea0`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeCommitPhaseTwo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // ebp
  __int64 v7; // rdi
  unsigned int v8; // esi
  __int64 v9; // rcx

  v4 = a2;
  if ( !*(_BYTE *)(a1 + 16) )
    return 0;
  if ( *(_BYTE *)(a1 + 17) )
  {
    ++*(_DWORD *)(a1 + 20);
    if ( !*(_BYTE *)(a1 + 18) )
      btreeLockCarefully(a1, a2, a3, a4);
  }
  if ( *(_BYTE *)(a1 + 16) != 2 )
  {
LABEL_4:
    btreeEndTransaction(a1, a2, a3, a4);
    if ( *(_BYTE *)(a1 + 17) )
    {
      if ( (*(_DWORD *)(a1 + 20))-- == 1 )
        unlockBtreeMutex(a1);
    }
    return 0;
  }
  v7 = *(_QWORD *)(a1 + 8);
  v8 = sqlite3PagerCommitPhaseTwo(*(_QWORD *)v7, a2, a3, a4);
  if ( !v8 || v4 )
  {
    --*(_DWORD *)(a1 + 28);
    v9 = *(_QWORD *)(v7 + 96);
    *(_BYTE *)(v7 + 36) = 1;
    sqlite3BitvecDestroy(v9);
    *(_QWORD *)(v7 + 96) = 0;
    goto LABEL_4;
  }
  sqlite3BtreeLeave(a1);
  return v8;
}

```

## disassembly

```asm
0x180024e18  push    rbx
0x180024e1a  push    rbp
0x180024e1b  push    rsi
0x180024e1c  push    rdi
0x180024e1d  sub     rsp, 28h
0x180024e21  cmp     byte ptr [rcx+10h], 0
0x180024e25  mov     ebp, edx
0x180024e27  mov     rbx, rcx
0x180024e2a  jz      short loc_180024E46
0x180024e2c  cmp     byte ptr [rcx+11h], 0
0x180024e30  jnz     short loc_180024E7D
0x180024e32  cmp     byte ptr [rbx+10h], 2
0x180024e36  jz      short loc_180024E51
0x180024e38  mov     rcx, rbx
0x180024e3b  call    btreeEndTransaction
0x180024e40  cmp     byte ptr [rbx+11h], 0
0x180024e44  jnz     short loc_180024E9D
0x180024e46  xor     eax, eax
0x180024e48  add     rsp, 28h
0x180024e4c  pop     rdi
0x180024e4d  pop     rsi
0x180024e4e  pop     rbp
0x180024e4f  pop     rbx
0x180024e50  retn
0x180024e51  mov     rdi, [rbx+8]
0x180024e55  mov     rcx, [rdi]
0x180024e58  call    sqlite3PagerCommitPhaseTwo
0x180024e5d  mov     esi, eax
0x180024e5f  test    eax, eax
0x180024e61  jnz     short loc_180024E8D
0x180024e63  dec     dword ptr [rbx+1Ch]
0x180024e66  mov     rcx, [rdi+60h]
0x180024e6a  mov     byte ptr [rdi+24h], 1
0x180024e6e  call    sqlite3BitvecDestroy
0x180024e73  mov     qword ptr [rdi+60h], 0
0x180024e7b  jmp     short loc_180024E38
0x180024e7d  inc     dword ptr [rcx+14h]
0x180024e80  cmp     byte ptr [rcx+12h], 0
0x180024e84  jnz     short loc_180024E32
0x180024e86  call    btreeLockCarefully
0x180024e8b  jmp     short loc_180024E32
0x180024e8d  test    ebp, ebp
0x180024e8f  jnz     short loc_180024E63
0x180024e91  mov     rcx, rbx
0x180024e94  call    sqlite3BtreeLeave
0x180024e99  mov     eax, esi
0x180024e9b  jmp     short loc_180024E48
0x180024e9d  sub     dword ptr [rbx+14h], 1
0x180024ea1  jnz     short loc_180024E46
0x180024ea3  mov     rcx, rbx
0x180024ea6  call    unlockBtreeMutex
0x180024eab  jmp     short loc_180024E46
```
