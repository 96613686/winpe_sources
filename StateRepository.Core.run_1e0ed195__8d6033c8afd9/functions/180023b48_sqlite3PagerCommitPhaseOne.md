# sqlite3PagerCommitPhaseOne

- ea: `0x180023b48`
- end: `0x180023de9`
- name: `sqlite3PagerCommitPhaseOne`
- size: `673`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800238e0`
- `0x180024f90`
- `0x18008c010`

## callees

- `0x1800082c4`
- `0x180023b48`
- `0x180023df0`
- `0x180024d1c`
- `0x180024dd8`
- `0x1800472a4`
- `0x18004aa70`
- `0x180061740`
- `0x180068428`
- `0x18007ae08`
- `0x18007b3c0`
- `0x18007b4a8`
- `0x180081618`
- `0x180085f9c`
- `0x180091fbc`
- `0x1800989cc`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall sqlite3PagerCommitPhaseOne(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax
  _QWORD *v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // r9d
  __int64 *v11; // r10
  unsigned int v12; // r8d
  bool v13; // cc
  __int64 *v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rsi
  unsigned int v17; // edi
  int v18; // eax
  int v19; // r9d
  __int64 *v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // edx
  __int64 v24; // [rsp+50h] [rbp+8h] BYREF
  __int64 v25; // [rsp+68h] [rbp+20h] BYREF

  result = *(unsigned int *)(a1 + 48);
  if ( !(_DWORD)result )
  {
    if ( qword_1800B57C0 && (unsigned int)qword_1800B57C0(400) )
      return 10;
    if ( *(_BYTE *)(a1 + 21) < 3u )
      return 0;
    if ( !*(_BYTE *)(a1 + 16) )
      goto LABEL_6;
    if ( !**(_QWORD **)(a1 + 72) )
      goto LABEL_34;
    v18 = numberOfCachePages(*(_QWORD *)(a1 + 288), a2, *(_QWORD *)(a1 + 288), 0);
    v21 = *v20;
    while ( v21 )
    {
      v21 = *(_QWORD *)(v21 + 64);
      ++v19;
    }
    if ( v18 && (int)(100LL * v19 / v18) >= 25 )
    {
LABEL_6:
      v7 = (_QWORD *)(a1 + 296);
      if ( *(_QWORD *)(a1 + 296) )
      {
        v8 = *(_QWORD *)(a1 + 288);
        v24 = 0;
        v9 = sqlite3PcacheDirtyList(v8);
        if ( !v9 )
        {
          sqlite3PagerGet(a1, 1, &v24, 0);
          v9 = v24;
          *(_QWORD *)(v24 + 32) = 0;
        }
        v10 = *(_DWORD *)(a1 + 32);
        v11 = &v25;
        v12 = 0;
        v25 = v9;
        do
        {
          v13 = *(_DWORD *)(v9 + 48) <= v10;
          v14 = (__int64 *)(v9 + 32);
          v9 = *(_QWORD *)(v9 + 32);
          if ( !v13 )
            v14 = v11;
          v11 = v14;
          v15 = v12 + 1;
          if ( !v13 )
            v15 = v12;
          v12 = v15;
          *v11 = v9;
        }
        while ( v9 );
        v16 = v25;
        *(_DWORD *)(a1 + 256) += v15;
        if ( *(_DWORD *)(v16 + 48) == 1 )
          pager_write_changecounter(v16, 0, v15);
        v17 = sqlite3WalFrames(*v7, *(_DWORD *)(a1 + 200), v16, v10, 1, *(unsigned __int8 *)(a1 + 15));
        if ( !v17 && *(_QWORD *)(a1 + 112) )
        {
          while ( v16 )
          {
            sqlite3BackupUpdate(*(_QWORD *)(a1 + 112), *(unsigned int *)(v16 + 48), *(_QWORD *)(v16 + 8));
            v16 = *(_QWORD *)(v16 + 32);
          }
        }
        sqlite3PagerUnref(v24);
        if ( v17 )
          return v17;
        sqlite3PcacheCleanAll(*(_QWORD *)(a1 + 288));
      }
      else
      {
        v17 = pager_incr_changecounter(a1);
        if ( v17 )
          return v17;
        v17 = writeSuperJournal(a1, a2);
        if ( v17 )
          return v17;
        v17 = syncJournal(a1, 0);
        if ( v17 )
          return v17;
        v22 = sqlite3PcacheDirtyList(*(_QWORD *)(a1 + 288));
        v17 = pager_write_pagelist(a1, v22);
        if ( v17 )
          return v17;
        sqlite3PcacheCleanAll(*(_QWORD *)(a1 + 288));
        v23 = *(_DWORD *)(a1 + 32);
        if ( v23 > *(_DWORD *)(a1 + 40) )
        {
          v17 = pager_truncate(a1, v23 - (v23 == *(_DWORD *)(a1 + 192)));
          if ( v17 )
            return v17;
        }
        if ( !a3 )
          v17 = sqlite3PagerSync(a1, a2);
        if ( v17 )
          return v17;
      }
    }
    else
    {
LABEL_34:
      v17 = 0;
      sqlite3BackupRestart(*(_QWORD *)(a1 + 112));
      v7 = (_QWORD *)(a1 + 296);
    }
    if ( !*v7 )
      *(_BYTE *)(a1 + 21) = 5;
    return v17;
  }
  return result;
}

```

## disassembly

```asm
0x180023b48  mov     [rsp+arg_8], rbx
0x180023b4d  mov     [rsp+arg_10], rbp
0x180023b52  push    rsi
0x180023b53  push    rdi
0x180023b54  push    r14
0x180023b56  sub     rsp, 30h
0x180023b5a  mov     eax, [rcx+30h]
0x180023b5d  mov     ebp, r8d
0x180023b60  mov     rsi, rdx
0x180023b63  mov     rbx, rcx
0x180023b66  test    eax, eax
0x180023b68  jnz     loc_180023C84
0x180023b6e  mov     rax, cs:qword_1800B57C0
0x180023b75  test    rax, rax
0x180023b78  jz      short loc_180023B8C
0x180023b7a  mov     ecx, 190h
0x180023b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b84  test    eax, eax
0x180023b86  jnz     loc_180023C97
0x180023b8c  cmp     byte ptr [rbx+15h], 3
0x180023b90  jb      loc_180023C7A
0x180023b96  cmp     byte ptr [rbx+10h], 0
0x180023b9a  mov     edi, 1
0x180023b9f  jnz     loc_180023C9E
0x180023ba5  lea     r14, [rbx+128h]
0x180023bac  cmp     qword ptr [r14], 0
0x180023bb0  jz      loc_180023D40
0x180023bb6  mov     rcx, [rbx+120h]
0x180023bbd  mov     [rsp+48h+arg_0], 0
0x180023bc6  call    sqlite3PcacheDirtyList
0x180023bcb  mov     rdx, rax
0x180023bce  test    rax, rax
0x180023bd1  jz      loc_180023CFE
0x180023bd7  mov     r9d, [rbx+20h]
0x180023bdb  lea     r10, [rsp+48h+arg_18]
0x180023be0  xor     r8d, r8d
0x180023be3  mov     [rsp+48h+arg_18], rdx
0x180023be8  cmp     [rdx+30h], r9d
0x180023bec  lea     rax, [rdx+20h]
0x180023bf0  mov     rdx, [rdx+20h]
0x180023bf4  cmova   rax, r10
0x180023bf8  mov     r10, rax
0x180023bfb  lea     eax, [r8+1]
0x180023bff  cmova   eax, r8d
0x180023c03  mov     r8d, eax
0x180023c06  mov     [r10], rdx
0x180023c09  test    rdx, rdx
0x180023c0c  jnz     short loc_180023BE8
0x180023c0e  mov     rsi, [rsp+48h+arg_18]
0x180023c13  add     [rbx+100h], eax
0x180023c19  cmp     [rsi+30h], edi
0x180023c1c  jnz     short loc_180023C26
0x180023c1e  mov     rcx, rsi
0x180023c21  call    pager_write_changecounter
0x180023c26  movzx   eax, byte ptr [rbx+0Fh]
0x180023c2a  mov     r8, rsi
0x180023c2d  mov     edx, [rbx+0C8h]
0x180023c33  mov     rcx, [r14]
0x180023c36  mov     [rsp+48h+var_20], eax
0x180023c3a  mov     [rsp+48h+var_28], edi
0x180023c3e  call    sqlite3WalFrames
0x180023c43  mov     edi, eax
0x180023c45  test    eax, eax
0x180023c47  jnz     short loc_180023C54
0x180023c49  cmp     qword ptr [rbx+70h], 0
0x180023c4e  jnz     loc_180023D36
0x180023c54  mov     rcx, [rsp+48h+arg_0]
0x180023c59  call    sqlite3PagerUnref
0x180023c5e  test    edi, edi
0x180023c60  jnz     short loc_180023C82
0x180023c62  mov     rcx, [rbx+120h]
0x180023c69  call    sqlite3PcacheCleanAll
0x180023c6e  cmp     qword ptr [r14], 0
0x180023c72  jnz     short loc_180023C82
0x180023c74  mov     byte ptr [rbx+15h], 5
0x180023c78  jmp     short loc_180023C82
0x180023c7a  xor     eax, eax
0x180023c7c  jmp     short loc_180023C84
0x180023c7e  test    edi, edi
0x180023c80  jz      short loc_180023C6E
0x180023c82  mov     eax, edi
0x180023c84  mov     rbx, [rsp+48h+arg_8]
0x180023c89  mov     rbp, [rsp+48h+arg_10]
0x180023c8e  add     rsp, 30h
0x180023c92  pop     r14
0x180023c94  pop     rdi
0x180023c95  pop     rsi
0x180023c96  retn
0x180023c97  mov     eax, 0Ah
0x180023c9c  jmp     short loc_180023C84
0x180023c9e  mov     rax, [rbx+48h]
0x180023ca2  cmp     qword ptr [rax], 0
0x180023ca6  jz      short loc_180023CE7
0x180023ca8  mov     r8, [rbx+120h]
0x180023caf  xor     r9d, r9d
0x180023cb2  mov     rcx, r8
0x180023cb5  call    numberOfCachePages
0x180023cba  mov     rcx, [r8]
0x180023cbd  movsxd  r10, eax
0x180023cc0  jmp     short loc_180023CC9
0x180023cc2  mov     rcx, [rcx+40h]
0x180023cc6  add     r9d, edi
0x180023cc9  test    rcx, rcx
0x180023ccc  jnz     short loc_180023CC2
0x180023cce  test    eax, eax
0x180023cd0  jz      short loc_180023CE7
0x180023cd2  movsxd  rax, r9d
0x180023cd5  imul    rax, 64h ; 'd'
0x180023cd9  cqo
0x180023cdb  idiv    r10
0x180023cde  cmp     eax, 19h
0x180023ce1  jge     loc_180023BA5
0x180023ce7  mov     rcx, [rbx+70h]
0x180023ceb  xor     edi, edi
0x180023ced  call    sqlite3BackupRestart
0x180023cf2  lea     r14, [rbx+128h]
0x180023cf9  jmp     loc_180023C6E
0x180023cfe  xor     r9d, r9d
0x180023d01  lea     r8, [rsp+48h+arg_0]
0x180023d06  mov     edx, edi
0x180023d08  mov     rcx, rbx
0x180023d0b  call    sqlite3PagerGet
0x180023d10  mov     rdx, [rsp+48h+arg_0]
0x180023d15  mov     qword ptr [rdx+20h], 0
0x180023d1d  jmp     loc_180023BD7
0x180023d22  mov     r8, [rsi+8]
0x180023d26  mov     edx, [rsi+30h]
0x180023d29  mov     rcx, [rbx+70h]
0x180023d2d  call    sqlite3BackupUpdate
0x180023d32  mov     rsi, [rsi+20h]
0x180023d36  test    rsi, rsi
0x180023d39  jnz     short loc_180023D22
0x180023d3b  jmp     loc_180023C54
0x180023d40  mov     rcx, rbx
0x180023d43  call    pager_incr_changecounter
0x180023d48  mov     edi, eax
0x180023d4a  test    eax, eax
0x180023d4c  jnz     loc_180023C82
0x180023d52  mov     rdx, rsi
0x180023d55  mov     rcx, rbx
0x180023d58  call    writeSuperJournal
0x180023d5d  mov     edi, eax
0x180023d5f  test    eax, eax
0x180023d61  jnz     loc_180023C82
0x180023d67  xor     edx, edx
0x180023d69  mov     rcx, rbx
0x180023d6c  call    syncJournal
0x180023d71  mov     edi, eax
0x180023d73  test    eax, eax
0x180023d75  jnz     loc_180023C82
0x180023d7b  mov     rcx, [rbx+120h]
0x180023d82  call    sqlite3PcacheDirtyList
0x180023d87  mov     rdx, rax
0x180023d8a  mov     rcx, rbx
0x180023d8d  call    pager_write_pagelist
0x180023d92  mov     edi, eax
0x180023d94  test    eax, eax
0x180023d96  jnz     loc_180023C82
0x180023d9c  mov     rcx, [rbx+120h]
0x180023da3  call    sqlite3PcacheCleanAll
0x180023da8  mov     edx, [rbx+20h]
0x180023dab  cmp     edx, [rbx+28h]
0x180023dae  jbe     short loc_180023DCF
0x180023db0  xor     eax, eax
0x180023db2  mov     rcx, rbx
0x180023db5  cmp     edx, [rbx+0C0h]
0x180023dbb  setz    al
0x180023dbe  sub     edx, eax
0x180023dc0  call    pager_truncate
0x180023dc5  mov     edi, eax
0x180023dc7  test    eax, eax
0x180023dc9  jnz     loc_180023C82
0x180023dcf  test    ebp, ebp
0x180023dd1  jnz     loc_180023C7E
0x180023dd7  mov     rdx, rsi
0x180023dda  mov     rcx, rbx
0x180023ddd  call    sqlite3PagerSync
0x180023de2  mov     edi, eax
0x180023de4  jmp     loc_180023C7E
```
