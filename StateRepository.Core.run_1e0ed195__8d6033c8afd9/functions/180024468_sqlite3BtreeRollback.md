# sqlite3BtreeRollback

- ea: `0x180024468`
- end: `0x1800245b2`
- name: `sqlite3BtreeRollback`
- size: `330`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18004788c`
- `0x18005bbe8`
- `0x18008bd60`

## callees

- `0x1800239a0`
- `0x1800241ec`
- `0x180024440`
- `0x180024468`
- `0x1800245b8`
- `0x180024b1c`
- `0x180024df4`
- `0x1800257ac`
- `0x180025d50`
- `0x180092ea0`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeRollback(__int64 a1, unsigned int a2, unsigned int a3)
{
  _QWORD *v3; // rsi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebp
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned __int32 v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int64 v24; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_QWORD **)(a1 + 8);
  sqlite3BtreeEnter(a1);
  if ( a2 )
  {
    v10 = 0;
LABEL_3:
    v11 = sqlite3BtreeTripAllCursors(a1, a2, a3);
    if ( v11 )
      v10 = v11;
    goto LABEL_11;
  }
  v12 = v3[2];
  if ( v12 )
    a2 = saveCursorsOnList(v12, 0, 0);
  else
    a2 = 0;
  v13 = 0;
  v10 = a2;
  if ( !a2 )
    v13 = a3;
  a3 = v13;
  if ( a2 )
    goto LABEL_3;
LABEL_11:
  if ( *(_BYTE *)(a1 + 16) == 2 )
  {
    v14 = sqlite3PagerRollback(*v3);
    v15 = *v3;
    v24 = 0;
    if ( v14 )
      v10 = v14;
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(v15 + 272))(v15, 1, &v24) )
    {
      v16 = v24;
      v17 = *(_QWORD *)(v24 + 16);
      if ( *(_DWORD *)(v17 + 4) != 1 )
      {
        *(_QWORD *)(v17 + 80) = *(_QWORD *)(v24 + 8);
        *(_QWORD *)(v17 + 112) = v16;
        *(_QWORD *)(v17 + 72) = v3;
        *(_DWORD *)(v17 + 4) = 1;
        *(_BYTE *)(v17 + 9) = 100;
      }
      v18 = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(v17 + 80) + 28LL));
      if ( !v18 )
        v18 = *(_DWORD *)(*v3 + 32LL);
      *((_DWORD *)v3 + 16) = v18;
      v19 = *(_QWORD *)(v17 + 112);
      v20 = *(_QWORD *)(v19 + 40);
      sqlite3PcacheRelease(v19);
      pagerUnlockIfUnused(v20);
    }
    v21 = v3[12];
    *((_BYTE *)v3 + 36) = 1;
    sqlite3BitvecDestroy(v21);
    v3[12] = 0;
  }
  btreeEndTransaction(a1, v7, v8, v9);
  if ( *(_BYTE *)(a1 + 17) )
  {
    if ( (*(_DWORD *)(a1 + 20))-- == 1 )
      unlockBtreeMutex(a1);
  }
  return v10;
}

```

## disassembly

```asm
0x180024468  mov     [rsp+arg_10], rbx
0x18002446d  mov     [rsp+arg_18], rbp
0x180024472  push    rsi
0x180024473  push    rdi
0x180024474  push    r14
0x180024476  sub     rsp, 30h
0x18002447a  mov     rsi, [rcx+8]
0x18002447e  mov     r14d, r8d
0x180024481  mov     ebx, edx
0x180024483  mov     rdi, rcx
0x180024486  call    sqlite3BtreeEnter
0x18002448b  test    ebx, ebx
0x18002448d  jz      short loc_1800244A5
0x18002448f  xor     ebp, ebp
0x180024491  mov     r8d, r14d
0x180024494  mov     edx, ebx
0x180024496  mov     rcx, rdi
0x180024499  call    sqlite3BtreeTripAllCursors
0x18002449e  test    eax, eax
0x1800244a0  cmovnz  ebp, eax
0x1800244a3  jmp     short loc_1800244C3
0x1800244a5  mov     rcx, [rsi+10h]
0x1800244a9  test    rcx, rcx
0x1800244ac  jnz     loc_180024589
0x1800244b2  xor     ebx, ebx
0x1800244b4  xor     eax, eax
0x1800244b6  mov     ebp, ebx
0x1800244b8  test    ebx, ebx
0x1800244ba  cmovz   eax, r14d
0x1800244be  mov     r14d, eax
0x1800244c1  jnz     short loc_180024491
0x1800244c3  cmp     byte ptr [rdi+10h], 2
0x1800244c7  jnz     loc_180024566
0x1800244cd  mov     rcx, [rsi]
0x1800244d0  call    sqlite3PagerRollback
0x1800244d5  mov     rcx, [rsi]
0x1800244d8  lea     r8, [rsp+48h+arg_0]
0x1800244dd  test    eax, eax
0x1800244df  mov     [rsp+48h+arg_0], 0
0x1800244e8  cmovnz  ebp, eax
0x1800244eb  xor     r9d, r9d
0x1800244ee  mov     rax, [rcx+110h]
0x1800244f5  lea     r14d, [r9+1]
0x1800244f9  mov     edx, r14d
0x1800244fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024501  test    eax, eax
0x180024503  jnz     short loc_180024551
0x180024505  mov     rdx, [rsp+48h+arg_0]
0x18002450a  mov     rcx, [rdx+10h]
0x18002450e  cmp     [rcx+4], r14d
0x180024512  jz      short loc_18002452C
0x180024514  mov     rax, [rdx+8]
0x180024518  mov     [rcx+50h], rax
0x18002451c  mov     [rcx+70h], rdx
0x180024520  mov     [rcx+48h], rsi
0x180024524  mov     [rcx+4], r14d
0x180024528  mov     byte ptr [rcx+9], 64h ; 'd'
0x18002452c  mov     rax, [rcx+50h]
0x180024530  mov     edx, [rax+1Ch]
0x180024533  bswap   edx
0x180024535  test    edx, edx
0x180024537  jz      short loc_18002459A
0x180024539  mov     [rsi+40h], edx
0x18002453c  mov     rcx, [rcx+70h]
0x180024540  mov     rbx, [rcx+28h]
0x180024544  call    sqlite3PcacheRelease
0x180024549  mov     rcx, rbx
0x18002454c  call    pagerUnlockIfUnused
0x180024551  mov     rcx, [rsi+60h]
0x180024555  mov     [rsi+24h], r14b
0x180024559  call    sqlite3BitvecDestroy
0x18002455e  mov     qword ptr [rsi+60h], 0
0x180024566  mov     rcx, rdi
0x180024569  call    btreeEndTransaction
0x18002456e  cmp     byte ptr [rdi+11h], 0
0x180024572  jnz     short loc_1800245A2
0x180024574  mov     rbx, [rsp+48h+arg_10]
0x180024579  mov     eax, ebp
0x18002457b  mov     rbp, [rsp+48h+arg_18]
0x180024580  add     rsp, 30h
0x180024584  pop     r14
0x180024586  pop     rdi
0x180024587  pop     rsi
0x180024588  retn
0x180024589  xor     r8d, r8d
0x18002458c  xor     edx, edx
0x18002458e  call    saveCursorsOnList
0x180024593  mov     ebx, eax
0x180024595  jmp     loc_1800244B4
0x18002459a  mov     rax, [rsi]
0x18002459d  mov     edx, [rax+20h]
0x1800245a0  jmp     short loc_180024539
0x1800245a2  sub     dword ptr [rdi+14h], 1
0x1800245a6  jnz     short loc_180024574
0x1800245a8  mov     rcx, rdi
0x1800245ab  call    unlockBtreeMutex
0x1800245b0  jmp     short loc_180024574
```
