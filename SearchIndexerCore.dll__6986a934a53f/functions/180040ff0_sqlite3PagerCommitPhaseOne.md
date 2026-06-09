# sqlite3PagerCommitPhaseOne

- ea: `0x180040ff0`
- end: `0x1800412a1`
- name: `sqlite3PagerCommitPhaseOne`
- size: `689`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003fb60`
- `0x180040640`
- `0x18005c940`
- `0x18009d2c0`

## callees

- `0x1800263c0`
- `0x180033594`
- `0x180040ff0`
- `0x1800415f4`
- `0x180041824`
- `0x1800419c0`
- `0x180041a4c`
- `0x180041a78`
- `0x180046420`
- `0x180053b3c`
- `0x1800641dc`
- `0x18006bf44`
- `0x18006c0ac`
- `0x18006d53c`
- `0x18006dd5c`
- `0x18006f18c`
- `0x1800b0010`

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
  _QWORD *i; // rsi
  __int64 v19; // rax
  unsigned int v20; // edx
  int v21; // eax
  int v22; // r9d
  __int64 *v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // [rsp+50h] [rbp+8h] BYREF
  __int64 v27; // [rsp+68h] [rbp+20h] BYREF

  result = *(unsigned int *)(a1 + 48);
  if ( !(_DWORD)result )
  {
    if ( qword_1800D0A00 && (unsigned int)qword_1800D0A00(400) )
      return 10;
    if ( *(_BYTE *)(a1 + 21) < 3u )
      return 0;
    if ( !*(_BYTE *)(a1 + 16) )
      goto LABEL_5;
    if ( !**(_QWORD **)(a1 + 72) )
      goto LABEL_42;
    v21 = numberOfCachePages(*(_QWORD *)(a1 + 320), a2, *(_QWORD *)(a1 + 320), 0);
    v24 = *v23;
    while ( v24 )
    {
      v24 = *(_QWORD *)(v24 + 64);
      ++v22;
    }
    if ( v21 && (int)(100LL * v22 / v21) >= 25 )
    {
LABEL_5:
      v7 = (_QWORD *)(a1 + 328);
      if ( *(_QWORD *)(a1 + 328) )
      {
        v8 = *(_QWORD *)(a1 + 320);
        v26 = 0;
        v9 = sqlite3PcacheDirtyList(v8);
        if ( !v9 )
        {
          (*(void (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(a1 + 272))(a1, 1, &v26, 0);
          v9 = v26;
          *(_QWORD *)(v26 + 32) = 0;
        }
        v10 = *(_DWORD *)(a1 + 32);
        v11 = &v27;
        v12 = 0;
        v27 = v9;
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
        v16 = v27;
        *(_DWORD *)(a1 + 256) += v15;
        if ( *(_DWORD *)(v16 + 48) == 1 )
          pager_write_changecounter(v16, 0, v15);
        v17 = sqlite3WalFrames(*v7, *(_DWORD *)(a1 + 200), v16, v10, 1, *(unsigned __int8 *)(a1 + 15));
        if ( !v17 && *(_QWORD *)(a1 + 112) )
        {
          while ( v16 )
          {
            v25 = *(_QWORD *)(a1 + 112);
            if ( v25 )
              backupUpdate(v25, *(_DWORD *)(v16 + 48), *(_QWORD *)(v16 + 8));
            v16 = *(_QWORD *)(v16 + 32);
          }
        }
        sqlite3PagerUnref(v26);
        if ( v17 )
          return v17;
        for ( i = *(_QWORD **)(a1 + 320); *i; sqlite3PcacheMakeClean(*i) )
          ;
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
        v19 = sqlite3PcacheDirtyList(*(_QWORD *)(a1 + 320));
        v17 = pager_write_pagelist(a1, v19);
        if ( v17 )
          return v17;
        sqlite3PcacheCleanAll(*(_QWORD *)(a1 + 320));
        v20 = *(_DWORD *)(a1 + 32);
        if ( v20 > *(_DWORD *)(a1 + 40) )
        {
          v17 = pager_truncate(a1, v20 - (v20 == *(_DWORD *)(a1 + 192)));
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
LABEL_42:
      v17 = 0;
      sqlite3BackupRestart(*(_QWORD *)(a1 + 112));
      v7 = (_QWORD *)(a1 + 328);
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
0x180040ff0  mov     [rsp+arg_8], rbx
0x180040ff5  mov     [rsp+arg_10], rbp
0x180040ffa  push    rsi
0x180040ffb  push    rdi
0x180040ffc  push    r14
0x180040ffe  sub     rsp, 30h
0x180041002  mov     eax, [rcx+30h]
0x180041005  mov     ebp, r8d
0x180041008  mov     rsi, rdx
0x18004100b  mov     rbx, rcx
0x18004100e  test    eax, eax
0x180041010  jnz     loc_1800411E8
0x180041016  mov     rax, cs:qword_1800D0A00
0x18004101d  test    rax, rax
0x180041020  jnz     loc_18004125F
0x180041026  cmp     byte ptr [rbx+15h], 3
0x18004102a  jb      loc_1800411FB
0x180041030  cmp     byte ptr [rbx+10h], 0
0x180041034  mov     edi, 1
0x180041039  jnz     loc_1800411FF
0x18004103f  lea     r14, [rbx+148h]
0x180041046  cmp     qword ptr [r14], 0
0x18004104a  jz      loc_18004114E
0x180041050  mov     rcx, [rbx+140h]
0x180041057  mov     [rsp+48h+arg_0], 0
0x180041060  call    sqlite3PcacheDirtyList
0x180041065  mov     rdx, rax
0x180041068  test    rax, rax
0x18004106b  jnz     short loc_180041093
0x18004106d  mov     rax, [rbx+110h]
0x180041074  lea     r8, [rsp+48h+arg_0]
0x180041079  xor     r9d, r9d
0x18004107c  mov     edx, edi
0x18004107e  mov     rcx, rbx
0x180041081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041086  mov     rdx, [rsp+48h+arg_0]
0x18004108b  mov     qword ptr [rdx+20h], 0
0x180041093  mov     r9d, [rbx+20h]
0x180041097  lea     r10, [rsp+48h+arg_18]
0x18004109c  xor     r8d, r8d
0x18004109f  mov     [rsp+48h+arg_18], rdx
0x1800410a4  cmp     [rdx+30h], r9d
0x1800410a8  lea     rax, [rdx+20h]
0x1800410ac  mov     rdx, [rdx+20h]
0x1800410b0  cmova   rax, r10
0x1800410b4  mov     r10, rax
0x1800410b7  lea     eax, [r8+1]
0x1800410bb  cmova   eax, r8d
0x1800410bf  mov     r8d, eax
0x1800410c2  mov     [r10], rdx
0x1800410c5  test    rdx, rdx
0x1800410c8  jnz     short loc_1800410A4
0x1800410ca  mov     rsi, [rsp+48h+arg_18]
0x1800410cf  add     [rbx+100h], eax
0x1800410d5  cmp     [rsi+30h], edi
0x1800410d8  jnz     short loc_1800410E2
0x1800410da  mov     rcx, rsi
0x1800410dd  call    pager_write_changecounter
0x1800410e2  movzx   eax, byte ptr [rbx+0Fh]
0x1800410e6  mov     r8, rsi
0x1800410e9  mov     edx, [rbx+0C8h]
0x1800410ef  mov     rcx, [r14]
0x1800410f2  mov     [rsp+48h+var_20], eax
0x1800410f6  mov     [rsp+48h+var_28], edi
0x1800410fa  call    sqlite3WalFrames
0x1800410ff  mov     edi, eax
0x180041101  test    eax, eax
0x180041103  jnz     short loc_180041110
0x180041105  cmp     qword ptr [rbx+70h], 0
0x18004110a  jnz     loc_18004127B
0x180041110  mov     rcx, [rsp+48h+arg_0]
0x180041115  call    sqlite3PagerUnref
0x18004111a  test    edi, edi
0x18004111c  jnz     loc_1800411E6
0x180041122  mov     rsi, [rbx+140h]
0x180041129  mov     rax, [rsi]
0x18004112c  test    rax, rax
0x18004112f  jnz     short loc_180041144
0x180041131  cmp     qword ptr [r14], 0
0x180041135  jnz     loc_1800411E6
0x18004113b  mov     byte ptr [rbx+15h], 5
0x18004113f  jmp     loc_1800411E6
0x180041144  mov     rcx, rax
0x180041147  call    sqlite3PcacheMakeClean
0x18004114c  jmp     short loc_180041129
0x18004114e  mov     rcx, rbx
0x180041151  call    pager_incr_changecounter
0x180041156  mov     edi, eax
0x180041158  test    eax, eax
0x18004115a  jnz     loc_1800411E6
0x180041160  mov     rdx, rsi
0x180041163  mov     rcx, rbx
0x180041166  call    writeSuperJournal
0x18004116b  mov     edi, eax
0x18004116d  test    eax, eax
0x18004116f  jnz     short loc_1800411E6
0x180041171  xor     edx, edx
0x180041173  mov     rcx, rbx
0x180041176  call    syncJournal
0x18004117b  mov     edi, eax
0x18004117d  test    eax, eax
0x18004117f  jnz     short loc_1800411E6
0x180041181  mov     rcx, [rbx+140h]
0x180041188  call    sqlite3PcacheDirtyList
0x18004118d  mov     rdx, rax
0x180041190  mov     rcx, rbx
0x180041193  call    pager_write_pagelist
0x180041198  mov     edi, eax
0x18004119a  test    eax, eax
0x18004119c  jnz     short loc_1800411E6
0x18004119e  mov     rcx, [rbx+140h]
0x1800411a5  call    sqlite3PcacheCleanAll
0x1800411aa  mov     edx, [rbx+20h]
0x1800411ad  cmp     edx, [rbx+28h]
0x1800411b0  jbe     short loc_1800411CD
0x1800411b2  xor     eax, eax
0x1800411b4  mov     rcx, rbx
0x1800411b7  cmp     edx, [rbx+0C0h]
0x1800411bd  setz    al
0x1800411c0  sub     edx, eax
0x1800411c2  call    pager_truncate
0x1800411c7  mov     edi, eax
0x1800411c9  test    eax, eax
0x1800411cb  jnz     short loc_1800411E6
0x1800411cd  test    ebp, ebp
0x1800411cf  jnz     short loc_1800411DE
0x1800411d1  mov     rdx, rsi
0x1800411d4  mov     rcx, rbx
0x1800411d7  call    sqlite3PagerSync
0x1800411dc  mov     edi, eax
0x1800411de  test    edi, edi
0x1800411e0  jz      loc_180041131
0x1800411e6  mov     eax, edi
0x1800411e8  mov     rbx, [rsp+48h+arg_8]
0x1800411ed  mov     rbp, [rsp+48h+arg_10]
0x1800411f2  add     rsp, 30h
0x1800411f6  pop     r14
0x1800411f8  pop     rdi
0x1800411f9  pop     rsi
0x1800411fa  retn
0x1800411fb  xor     eax, eax
0x1800411fd  jmp     short loc_1800411E8
0x1800411ff  mov     rax, [rbx+48h]
0x180041203  cmp     qword ptr [rax], 0
0x180041207  jz      short loc_180041248
0x180041209  mov     r8, [rbx+140h]
0x180041210  xor     r9d, r9d
0x180041213  mov     rcx, r8
0x180041216  call    numberOfCachePages
0x18004121b  mov     rcx, [r8]
0x18004121e  movsxd  r10, eax
0x180041221  jmp     short loc_18004122A
0x180041223  mov     rcx, [rcx+40h]
0x180041227  add     r9d, edi
0x18004122a  test    rcx, rcx
0x18004122d  jnz     short loc_180041223
0x18004122f  test    eax, eax
0x180041231  jz      short loc_180041248
0x180041233  movsxd  rax, r9d
0x180041236  imul    rax, 64h ; 'd'
0x18004123a  cqo
0x18004123c  idiv    r10
0x18004123f  cmp     eax, 19h
0x180041242  jge     loc_18004103F
0x180041248  mov     rcx, [rbx+70h]
0x18004124c  xor     edi, edi
0x18004124e  call    sqlite3BackupRestart
0x180041253  lea     r14, [rbx+148h]
0x18004125a  jmp     loc_180041131
0x18004125f  mov     ecx, 190h
0x180041264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041269  test    eax, eax
0x18004126b  jz      loc_180041026
0x180041271  mov     eax, 0Ah
0x180041276  jmp     loc_1800411E8
0x18004127b  test    rsi, rsi
0x18004127e  jz      loc_180041110
0x180041284  mov     rcx, [rbx+70h]
0x180041288  test    rcx, rcx
0x18004128b  jnz     short loc_180041293
0x18004128d  mov     rsi, [rsi+20h]
0x180041291  jmp     short loc_18004127B
0x180041293  mov     r8, [rsi+8]
0x180041297  mov     edx, [rsi+30h]
0x18004129a  call    backupUpdate
0x18004129f  jmp     short loc_18004128D
```
