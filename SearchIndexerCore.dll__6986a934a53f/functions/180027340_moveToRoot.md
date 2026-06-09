# moveToRoot

- ea: `0x180027340`
- end: `0x180027654`
- name: `moveToRoot`
- size: `788`
- prototype: ``
- caller_count: `7`
- callee_count: `10`
- tags: ``

## callers

- `0x180025a20`
- `0x180034660`
- `0x180034af0`
- `0x1800391a0`
- `0x18003d990`
- `0x18005f9cc`
- `0x180075dfc`

## callees

- `0x1800257e0`
- `0x18002619c`
- `0x18002625c`
- `0x180026740`
- `0x180027340`
- `0x180034ce4`
- `0x180035150`
- `0x180041eb0`
- `0x180060100`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall moveToRoot(__int64 a1)
{
  char v1; // al
  _DWORD *v3; // r14
  unsigned int v4; // ebp
  unsigned int inited; // r15d
  __int64 v6; // rcx
  __int64 v7; // rsi
  __int64 v8; // rax
  unsigned int v9; // esi
  __int64 v10; // rdx
  int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // r8
  char v15; // al
  __int64 v16; // rcx
  __int64 v17; // r8
  char v18; // al
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_BYTE *)(a1 + 84);
  if ( v1 < 0 )
  {
    if ( !*(_DWORD *)(a1 + 80) )
    {
      *(_BYTE *)a1 = 1;
      return 16;
    }
    if ( *(_BYTE *)a1 >= 3u )
    {
      if ( *(_BYTE *)a1 == 4 )
        return *(unsigned int *)(a1 + 4);
      sqlite3_free(*(_QWORD *)(a1 + 24));
      *(_QWORD *)(a1 + 24) = 0;
      *(_BYTE *)a1 = 1;
    }
    v3 = *(_DWORD **)(a1 + 32);
    v4 = *(_DWORD *)(a1 + 80);
    v22 = 0;
    if ( v4 > v3[16] )
    {
      *(_QWORD *)(a1 + 136) = 0;
      inited = sqlite3ReportError(11, 73175, "database corruption");
      if ( inited )
        goto LABEL_33;
    }
    else
    {
      inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v3 + 272LL))(
                 *(_QWORD *)v3,
                 v4,
                 &v22,
                 *(unsigned __int8 *)(a1 + 2));
      if ( inited )
      {
LABEL_30:
        *(_QWORD *)(a1 + 136) = 0;
LABEL_33:
        *(_BYTE *)a1 = 1;
        return inited;
      }
      v6 = v22;
      v7 = *(_QWORD *)(v22 + 16);
      if ( !*(_BYTE *)v7 )
      {
        if ( v4 != *(_DWORD *)(v7 + 4) )
        {
          *(_QWORD *)(v7 + 80) = *(_QWORD *)(v22 + 8);
          v18 = 100;
          if ( v4 != 1 )
            v18 = 0;
          *(_QWORD *)(v7 + 112) = v6;
          *(_BYTE *)(v7 + 9) = v18;
          *(_QWORD *)(v7 + 72) = v3;
          *(_DWORD *)(v7 + 4) = v4;
        }
        inited = btreeInitPage(v7);
        if ( inited )
        {
          releasePage(v7);
          goto LABEL_30;
        }
      }
      *(_QWORD *)(a1 + 136) = v7;
    }
    v8 = *(_QWORD *)(a1 + 136);
    v9 = 0;
    *(_BYTE *)(a1 + 84) = 0;
    *(_BYTE *)(a1 + 85) = *(_BYTE *)(v8 + 1);
    goto LABEL_9;
  }
  v9 = 0;
  if ( !v1 )
  {
LABEL_9:
    v10 = *(_QWORD *)(a1 + 136);
    if ( !*(_BYTE *)v10 || (*(_QWORD *)(a1 + 128) == 0) != *(_BYTE *)(v10 + 1) )
    {
      v12 = 76330;
LABEL_15:
      sqlite3_log(
        11,
        "%s at line %d of [%.10s]",
        "database corruption",
        v12,
        "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
      return 11;
    }
    goto LABEL_11;
  }
  v13 = *(_QWORD *)(a1 + 136);
  v14 = *(_QWORD *)(v13 + 112);
  if ( (*(_BYTE *)(v14 + 52) & 0x20) != 0 )
  {
    v21 = *(_QWORD *)(v14 + 40);
    --*(_DWORD *)(v21 + 152);
    *(_QWORD *)(v14 + 32) = *(_QWORD *)(v21 + 168);
    *(_QWORD *)(v21 + 168) = v14;
    sqlite3OsUnfetch(
      *(_QWORD *)(v21 + 72),
      *(_QWORD *)(v21 + 200) * (unsigned int)(*(_DWORD *)(v14 + 48) - 1),
      *(_QWORD *)(v14 + 8));
  }
  else
  {
    sqlite3PcacheRelease(*(_QWORD *)(v13 + 112));
  }
  v15 = *(_BYTE *)(a1 + 84) - 1;
  for ( *(_BYTE *)(a1 + 84) = v15; v15; *(_BYTE *)(a1 + 84) = v15 )
  {
    v16 = *(_QWORD *)(a1 + 8LL * v15 + 144);
    v17 = *(_QWORD *)(v16 + 112);
    if ( (*(_BYTE *)(v17 + 52) & 0x20) != 0 )
    {
      v19 = *(_QWORD *)(v17 + 40);
      --*(_DWORD *)(v19 + 152);
      *(_QWORD *)(v17 + 32) = *(_QWORD *)(v19 + 168);
      *(_QWORD *)(v19 + 168) = v17;
      sqlite3OsUnfetch(
        *(_QWORD *)(v19 + 72),
        *(_QWORD *)(v19 + 200) * (unsigned int)(*(_DWORD *)(v17 + 48) - 1),
        *(_QWORD *)(v17 + 8));
    }
    else
    {
      sqlite3PcacheRelease(*(_QWORD *)(v16 + 112));
    }
    v15 = *(_BYTE *)(a1 + 84) - 1;
  }
  v10 = *(_QWORD *)(a1 + 144);
  *(_QWORD *)(a1 + 136) = v10;
LABEL_11:
  *(_BYTE *)(a1 + 1) &= 0xF1u;
  *(_WORD *)(a1 + 86) = 0;
  *(_WORD *)(a1 + 70) = 0;
  if ( *(_WORD *)(v10 + 24) )
  {
    *(_BYTE *)a1 = 0;
    return v9;
  }
  if ( *(_BYTE *)(v10 + 8) )
  {
    *(_BYTE *)a1 = 1;
    return 16;
  }
  if ( *(_DWORD *)(v10 + 4) != 1 )
  {
    v12 = 76342;
    goto LABEL_15;
  }
  v20 = _byteswap_ulong(*(_DWORD *)(*(unsigned __int8 *)(v10 + 9) + *(_QWORD *)(v10 + 80) + 8LL));
  *(_BYTE *)a1 = 0;
  return moveToChild(a1, v20);
}

```

## disassembly

```asm
0x180027340  push    rbx
0x180027342  push    rbp
0x180027343  push    rsi
0x180027344  push    rdi
0x180027345  push    r14
0x180027347  push    r15
0x180027349  sub     rsp, 38h
0x18002734d  movzx   eax, byte ptr [rcx+54h]
0x180027351  mov     rbx, rcx
0x180027354  test    al, al
0x180027356  jns     loc_18002745A
0x18002735c  cmp     dword ptr [rcx+50h], 0
0x180027360  jz      loc_18002751A
0x180027366  movzx   eax, byte ptr [rcx]
0x180027369  xor     edi, edi
0x18002736b  cmp     al, 3
0x18002736d  jnb     loc_18002756A
0x180027373  mov     r14, [rbx+20h]
0x180027377  mov     ebp, [rbx+50h]
0x18002737a  mov     [rsp+68h+arg_0], rdi
0x18002737f  cmp     ebp, [r14+40h]
0x180027383  ja      loc_18002752F
0x180027389  mov     rax, [r14]
0x18002738c  lea     r8, [rsp+68h+arg_0]
0x180027391  movzx   r9d, byte ptr [rbx+2]
0x180027396  mov     rcx, rax
0x180027399  mov     edx, ebp
0x18002739b  mov     rax, [rax+110h]
0x1800273a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273a7  mov     r15d, eax
0x1800273aa  test    eax, eax
0x1800273ac  jnz     loc_180027511
0x1800273b2  mov     rcx, [rsp+68h+arg_0]
0x1800273b7  mov     rsi, [rcx+10h]
0x1800273bb  cmp     [rsi], dil
0x1800273be  jz      loc_1800274D0
0x1800273c4  mov     [rbx+88h], rsi
0x1800273cb  mov     rax, [rbx+88h]
0x1800273d2  mov     esi, edi
0x1800273d4  mov     [rbx+54h], sil
0x1800273d8  movzx   ecx, byte ptr [rax+1]
0x1800273dc  mov     [rbx+55h], cl
0x1800273df  mov     rdx, [rbx+88h]
0x1800273e6  cmp     byte ptr [rdx], 0
0x1800273e9  jz      short loc_180027429
0x1800273eb  cmp     qword ptr [rbx+80h], 0
0x1800273f3  mov     ecx, edi
0x1800273f5  movzx   eax, byte ptr [rdx+1]
0x1800273f9  setz    cl
0x1800273fc  cmp     ecx, eax
0x1800273fe  jnz     short loc_180027429
0x180027400  and     byte ptr [rbx+1], 0F1h
0x180027404  mov     [rbx+56h], di
0x180027408  mov     [rbx+46h], di
0x18002740c  cmp     word ptr [rdx+18h], 0
0x180027411  jbe     loc_18002757E
0x180027417  mov     byte ptr [rbx], 0
0x18002741a  mov     eax, esi
0x18002741c  add     rsp, 38h
0x180027420  pop     r15
0x180027422  pop     r14
0x180027424  pop     rdi
0x180027425  pop     rsi
0x180027426  pop     rbp
0x180027427  pop     rbx
0x180027428  retn
0x180027429  mov     r9d, 12A2Ah
0x18002742f  lea     rcx, a20240523134606+14h; "18a3cf29885901ce73120761875ccdd0e3704e3"...
0x180027436  mov     [rsp+68h+var_48], rcx
0x18002743b  lea     r8, aDatabaseCorrup; "database corruption"
0x180027442  mov     ecx, 0Bh
0x180027447  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x18002744e  call    sqlite3_log
0x180027453  mov     eax, 0Bh
0x180027458  jmp     short loc_18002741C
0x18002745a  xor     edi, edi
0x18002745c  mov     esi, edi
0x18002745e  test    al, al
0x180027460  jz      loc_1800273DF
0x180027466  mov     rax, [rcx+88h]
0x18002746d  mov     r8, [rax+70h]
0x180027471  test    byte ptr [r8+34h], 20h
0x180027476  jnz     loc_180027618
0x18002747c  mov     rcx, r8
0x18002747f  call    sqlite3PcacheRelease
0x180027484  movzx   eax, byte ptr [rbx+54h]
0x180027488  sub     al, 1
0x18002748a  mov     [rbx+54h], al
0x18002748d  jz      short loc_1800274BD
0x18002748f  movsx   rax, al
0x180027493  mov     rcx, [rbx+rax*8+90h]
0x18002749b  mov     r8, [rcx+70h]
0x18002749f  test    byte ptr [r8+34h], 20h
0x1800274a4  jnz     loc_1800275A2
0x1800274aa  mov     rcx, r8
0x1800274ad  call    sqlite3PcacheRelease
0x1800274b2  movzx   eax, byte ptr [rbx+54h]
0x1800274b6  sub     al, 1
0x1800274b8  mov     [rbx+54h], al
0x1800274bb  jnz     short loc_18002748F
0x1800274bd  mov     rdx, [rbx+90h]
0x1800274c4  mov     [rbx+88h], rdx
0x1800274cb  jmp     loc_180027400
0x1800274d0  cmp     ebp, [rsi+4]
0x1800274d3  jz      short loc_1800274F6
0x1800274d5  mov     rax, [rcx+8]
0x1800274d9  cmp     ebp, 1
0x1800274dc  mov     [rsi+50h], rax
0x1800274e0  mov     eax, 64h ; 'd'
0x1800274e5  cmovnz  eax, edi
0x1800274e8  mov     [rsi+70h], rcx
0x1800274ec  mov     [rsi+9], al
0x1800274ef  mov     [rsi+48h], r14
0x1800274f3  mov     [rsi+4], ebp
0x1800274f6  mov     rcx, rsi
0x1800274f9  call    btreeInitPage
0x1800274fe  mov     r15d, eax
0x180027501  test    eax, eax
0x180027503  jz      loc_1800273C4
0x180027509  mov     rcx, rsi
0x18002750c  call    releasePage
0x180027511  mov     [rbx+88h], rdi
0x180027518  jmp     short loc_180027557
0x18002751a  mov     byte ptr [rcx], 1
0x18002751d  mov     eax, 10h
0x180027522  add     rsp, 38h
0x180027526  pop     r15
0x180027528  pop     r14
0x18002752a  pop     rdi
0x18002752b  pop     rsi
0x18002752c  pop     rbp
0x18002752d  pop     rbx
0x18002752e  retn
0x18002752f  lea     r8, aDatabaseCorrup; "database corruption"
0x180027536  mov     [rbx+88h], rdi
0x18002753d  mov     edx, 11DD7h
0x180027542  mov     ecx, 0Bh
0x180027547  call    sqlite3ReportError
0x18002754c  mov     r15d, eax
0x18002754f  test    eax, eax
0x180027551  jz      loc_1800273CB
0x180027557  mov     byte ptr [rbx], 1
0x18002755a  mov     eax, r15d
0x18002755d  add     rsp, 38h
0x180027561  pop     r15
0x180027563  pop     r14
0x180027565  pop     rdi
0x180027566  pop     rsi
0x180027567  pop     rbp
0x180027568  pop     rbx
0x180027569  retn
0x18002756a  cmp     al, 4
0x18002756c  jnz     short loc_1800275DE
0x18002756e  mov     eax, [rcx+4]
0x180027571  add     rsp, 38h
0x180027575  pop     r15
0x180027577  pop     r14
0x180027579  pop     rdi
0x18002757a  pop     rsi
0x18002757b  pop     rbp
0x18002757c  pop     rbx
0x18002757d  retn
0x18002757e  cmp     byte ptr [rdx+8], 0
0x180027582  jz      short loc_180027591
0x180027584  mov     byte ptr [rbx], 1
0x180027587  mov     esi, 10h
0x18002758c  jmp     loc_18002741A
0x180027591  cmp     dword ptr [rdx+4], 1
0x180027595  jz      short loc_1800275F3
0x180027597  mov     r9d, 12A36h
0x18002759d  jmp     loc_18002742F
0x1800275a2  mov     rcx, [r8+28h]
0x1800275a6  dec     dword ptr [rcx+98h]
0x1800275ac  mov     rax, [rcx+0A8h]
0x1800275b3  mov     [r8+20h], rax
0x1800275b7  mov     [rcx+0A8h], r8
0x1800275be  mov     edx, [r8+30h]
0x1800275c2  mov     r8, [r8+8]
0x1800275c6  dec     edx
0x1800275c8  imul    rdx, [rcx+0C8h]
0x1800275d0  mov     rcx, [rcx+48h]
0x1800275d4  call    sqlite3OsUnfetch
0x1800275d9  jmp     loc_1800274B2
0x1800275de  mov     rcx, [rcx+18h]
0x1800275e2  call    sqlite3_free
0x1800275e7  mov     [rbx+18h], rdi
0x1800275eb  mov     byte ptr [rbx], 1
0x1800275ee  jmp     loc_180027373
0x1800275f3  movzx   ecx, byte ptr [rdx+9]
0x1800275f7  mov     rax, [rdx+50h]
0x1800275fb  mov     edx, [rcx+rax+8]
0x1800275ff  mov     rcx, rbx
0x180027602  bswap   edx
0x180027604  mov     byte ptr [rbx], 0
0x180027607  add     rsp, 38h
0x18002760b  pop     r15
0x18002760d  pop     r14
0x18002760f  pop     rdi
0x180027610  pop     rsi
0x180027611  pop     rbp
0x180027612  pop     rbx
0x180027613  jmp     moveToChild
0x180027618  mov     rcx, [r8+28h]
0x18002761c  dec     dword ptr [rcx+98h]
0x180027622  mov     rax, [rcx+0A8h]
0x180027629  mov     [r8+20h], rax
0x18002762d  mov     [rcx+0A8h], r8
0x180027634  mov     edx, [r8+30h]
0x180027638  mov     r8, [r8+8]
0x18002763c  dec     edx
0x18002763e  imul    rdx, [rcx+0C8h]
0x180027646  mov     rcx, [rcx+48h]
0x18002764a  call    sqlite3OsUnfetch
0x18002764f  jmp     loc_180027484
```
