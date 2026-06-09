# sqlite3BtreeRollback

- ea: `0x18003f974`
- end: `0x18003fa9f`
- name: `sqlite3BtreeRollback`
- size: `299`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18003f560`
- `0x180046be0`
- `0x180074b90`

## callees

- `0x18003e6b8`
- `0x18003f2cc`
- `0x18003f974`
- `0x18003faa8`
- `0x18003fb44`
- `0x180040ecc`
- `0x180041490`
- `0x180046508`
- `0x180048614`
- `0x1800487ec`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeRollback(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 *v3; // rsi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebp
  unsigned int v11; // eax
  __int64 v13; // rcx
  unsigned int v14; // eax
  unsigned int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(__int64 **)(a1 + 8);
  sqlite3BtreeEnter(a1);
  if ( a2 )
  {
    v10 = 0;
LABEL_3:
    v11 = sqlite3BtreeTripAllCursors(a1, a2, a3);
    if ( v11 )
      v10 = v11;
    goto LABEL_5;
  }
  v13 = v3[2];
  if ( v13 )
    a2 = saveCursorsOnList(v13, 0, 0);
  else
    a2 = 0;
  v14 = 0;
  v10 = a2;
  if ( !a2 )
    v14 = a3;
  a3 = v14;
  if ( a2 )
    goto LABEL_3;
LABEL_5:
  if ( *(_BYTE *)(a1 + 16) == 2 )
  {
    v16 = sqlite3PagerRollback(*v3);
    v17 = *v3;
    v22 = 0;
    if ( v16 )
      v10 = v16;
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(v17 + 272))(v17, 1, &v22) )
    {
      v18 = v22;
      v19 = *(_QWORD *)(v22 + 16);
      if ( *(_DWORD *)(v19 + 4) != 1 )
      {
        *(_QWORD *)(v19 + 80) = *(_QWORD *)(v22 + 8);
        *(_QWORD *)(v19 + 112) = v18;
        *(_QWORD *)(v19 + 72) = v3;
        *(_DWORD *)(v19 + 4) = 1;
        *(_BYTE *)(v19 + 9) = 100;
      }
      btreeSetNPage(v3, v19);
      sqlite3PagerUnrefPageOne(*(_QWORD *)(v20 + 112));
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
0x18003f974  mov     [rsp+arg_10], rbx
0x18003f979  mov     [rsp+arg_18], rbp
0x18003f97e  push    rsi
0x18003f97f  push    rdi
0x18003f980  push    r14
0x18003f982  sub     rsp, 30h
0x18003f986  mov     rsi, [rcx+8]
0x18003f98a  mov     r14d, r8d
0x18003f98d  mov     edi, edx
0x18003f98f  mov     rbx, rcx
0x18003f992  call    sqlite3BtreeEnter
0x18003f997  test    edi, edi
0x18003f999  jz      short loc_18003F9D8
0x18003f99b  xor     ebp, ebp
0x18003f99d  mov     r8d, r14d
0x18003f9a0  mov     edx, edi
0x18003f9a2  mov     rcx, rbx
0x18003f9a5  call    sqlite3BtreeTripAllCursors
0x18003f9aa  test    eax, eax
0x18003f9ac  cmovnz  ebp, eax
0x18003f9af  cmp     byte ptr [rbx+10h], 2
0x18003f9b3  jz      short loc_18003FA12
0x18003f9b5  mov     rcx, rbx
0x18003f9b8  call    btreeEndTransaction
0x18003f9bd  cmp     byte ptr [rbx+11h], 0
0x18003f9c1  jnz     short loc_18003FA02
0x18003f9c3  mov     rbx, [rsp+48h+arg_10]
0x18003f9c8  mov     eax, ebp
0x18003f9ca  mov     rbp, [rsp+48h+arg_18]
0x18003f9cf  add     rsp, 30h
0x18003f9d3  pop     r14
0x18003f9d5  pop     rdi
0x18003f9d6  pop     rsi
0x18003f9d7  retn
0x18003f9d8  mov     rcx, [rsi+10h]
0x18003f9dc  test    rcx, rcx
0x18003f9df  jz      short loc_18003F9FE
0x18003f9e1  xor     r8d, r8d
0x18003f9e4  xor     edx, edx
0x18003f9e6  call    saveCursorsOnList
0x18003f9eb  mov     edi, eax
0x18003f9ed  xor     eax, eax
0x18003f9ef  mov     ebp, edi
0x18003f9f1  test    edi, edi
0x18003f9f3  cmovz   eax, r14d
0x18003f9f7  mov     r14d, eax
0x18003f9fa  jnz     short loc_18003F99D
0x18003f9fc  jmp     short loc_18003F9AF
0x18003f9fe  xor     edi, edi
0x18003fa00  jmp     short loc_18003F9ED
0x18003fa02  sub     dword ptr [rbx+14h], 1
0x18003fa06  jnz     short loc_18003F9C3
0x18003fa08  mov     rcx, rbx
0x18003fa0b  call    unlockBtreeMutex
0x18003fa10  jmp     short loc_18003F9C3
0x18003fa12  mov     rcx, [rsi]
0x18003fa15  call    sqlite3PagerRollback
0x18003fa1a  mov     rcx, [rsi]
0x18003fa1d  lea     r8, [rsp+48h+arg_0]
0x18003fa22  test    eax, eax
0x18003fa24  mov     [rsp+48h+arg_0], 0
0x18003fa2d  cmovnz  ebp, eax
0x18003fa30  xor     r9d, r9d
0x18003fa33  mov     rax, [rcx+110h]
0x18003fa3a  lea     edi, [r9+1]
0x18003fa3e  mov     edx, edi
0x18003fa40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa45  test    eax, eax
0x18003fa47  jnz     short loc_18003FA85
0x18003fa49  mov     rcx, [rsp+48h+arg_0]
0x18003fa4e  mov     r8, [rcx+10h]
0x18003fa52  cmp     [r8+4], edi
0x18003fa56  jz      short loc_18003FA71
0x18003fa58  mov     rax, [rcx+8]
0x18003fa5c  mov     [r8+50h], rax
0x18003fa60  mov     [r8+70h], rcx
0x18003fa64  mov     [r8+48h], rsi
0x18003fa68  mov     [r8+4], edi
0x18003fa6c  mov     byte ptr [r8+9], 64h ; 'd'
0x18003fa71  mov     rdx, r8
0x18003fa74  mov     rcx, rsi
0x18003fa77  call    btreeSetNPage
0x18003fa7c  mov     rcx, [r8+70h]
0x18003fa80  call    sqlite3PagerUnrefPageOne
0x18003fa85  mov     rcx, [rsi+60h]
0x18003fa89  mov     [rsi+24h], dil
0x18003fa8d  call    sqlite3BitvecDestroy
0x18003fa92  mov     qword ptr [rsi+60h], 0
0x18003fa9a  jmp     loc_18003F9B5
```
