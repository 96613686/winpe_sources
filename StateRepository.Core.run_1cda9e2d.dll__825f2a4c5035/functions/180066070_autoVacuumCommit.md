# autoVacuumCommit

- ea: `0x180066070`
- end: `0x180066226`
- name: `autoVacuumCommit`
- size: `438`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800238e0`
- `0x180024f90`

## callees

- `0x1800217c0`
- `0x18002395c`
- `0x1800245b8`
- `0x180060134`
- `0x180066070`
- `0x18006622c`
- `0x18006641c`
- `0x18006eef8`
- `0x180071cc4`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall autoVacuumCommit(__int64 a1)
{
  __int64 *v1; // rbx
  unsigned int v2; // esi
  __int64 v3; // r12
  __int64 v4; // rcx
  unsigned int v5; // edi
  __int64 *v6; // r10
  unsigned int v7; // r8d
  __int64 v8; // rcx
  unsigned __int32 v9; // r14d
  __int64 (__fastcall *v10)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int); // r11
  unsigned int i; // edx
  unsigned __int32 v12; // r15d
  unsigned int v14; // eax
  unsigned int v15; // ebp
  __int64 v16; // rdx
  unsigned int j; // eax

  v1 = *(__int64 **)(a1 + 8);
  v2 = 0;
  v3 = *v1;
  invalidateAllOverflowCache(v1);
  if ( *((_BYTE *)v1 + 34) )
    return v2;
  v5 = *((_DWORD *)v1 + 16);
  if ( (unsigned int)ptrmapPageno(v4, v5) == v5 || (v7 = *((_DWORD *)v1 + 13), v5 == dword_1800B561C / v7 + 1) )
  {
    v16 = 74849;
    return sqlite3ReportError(11, v16, "database corruption");
  }
  v8 = *v6;
  v9 = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(v1[3] + 80) + 36LL));
  v10 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(*v6 + 344);
  if ( v10 )
  {
    for ( i = 0; (signed int)i < *(_DWORD *)(v8 + 40); ++i )
    {
      if ( *(__int64 **)(32LL * i + *(_QWORD *)(v8 + 32) + 8) == v6 )
        break;
    }
    v12 = v10(*(_QWORD *)(v8 + 328), *(_QWORD *)(32LL * (int)i + *(_QWORD *)(v8 + 32)), v5, v9, v7);
    if ( v12 > v9 )
      v12 = v9;
    if ( !v12 )
      return 0;
  }
  else
  {
    v12 = v9;
  }
  v14 = finalDbSize(v1, v5, v12);
  v15 = v14;
  if ( v14 <= v5 )
  {
    if ( v14 >= v5 )
      goto LABEL_20;
    for ( j = saveAllCursors(v1, 0, 0); ; j = incrVacuumStep(v1, v15, v5--, v12 == v9) )
    {
      v2 = j;
LABEL_20:
      if ( v5 <= v15 || v2 )
        break;
    }
    if ( v2 != 101 && v2 )
      goto LABEL_28;
    if ( v9 )
    {
      v2 = sqlite3PagerWrite(*(_QWORD *)(v1[3] + 112));
      if ( v12 == v9 )
      {
        *(_DWORD *)(*(_QWORD *)(v1[3] + 80) + 32LL) = 0;
        *(_DWORD *)(*(_QWORD *)(v1[3] + 80) + 36LL) = 0;
      }
      *(_DWORD *)(*(_QWORD *)(v1[3] + 80) + 28LL) = _byteswap_ulong(v15);
      *((_BYTE *)v1 + 35) = 1;
      *((_DWORD *)v1 + 16) = v15;
    }
    if ( v2 )
LABEL_28:
      sqlite3PagerRollback(v3);
    return v2;
  }
  v16 = 74876;
  return sqlite3ReportError(11, v16, "database corruption");
}

```

## disassembly

```asm
0x180066070  push    rbx
0x180066072  push    rbp
0x180066073  push    rsi
0x180066074  push    rdi
0x180066075  push    r12
0x180066077  push    r14
0x180066079  push    r15
0x18006607b  sub     rsp, 30h
0x18006607f  mov     rbx, [rcx+8]
0x180066083  mov     r10, rcx
0x180066086  mov     rcx, rbx
0x180066089  xor     esi, esi
0x18006608b  mov     r12, [rbx]
0x18006608e  call    invalidateAllOverflowCache
0x180066093  cmp     [rbx+22h], sil
0x180066097  jnz     loc_1800661FD
0x18006609d  mov     edi, [rbx+40h]
0x1800660a0  mov     edx, edi
0x1800660a2  call    ptrmapPageno
0x1800660a7  cmp     eax, edi
0x1800660a9  jz      loc_18006620E
0x1800660af  mov     eax, cs:dword_1800B561C
0x1800660b5  xor     edx, edx
0x1800660b7  mov     r8d, [rbx+34h]
0x1800660bb  div     r8d
0x1800660be  inc     eax
0x1800660c0  cmp     edi, eax
0x1800660c2  jz      loc_18006620E
0x1800660c8  mov     rax, [rbx+18h]
0x1800660cc  mov     rcx, [rax+50h]
0x1800660d0  mov     r14d, [rcx+24h]
0x1800660d4  mov     rcx, [r10]
0x1800660d7  bswap   r14d
0x1800660da  mov     r11, [rcx+158h]
0x1800660e1  test    r11, r11
0x1800660e4  jz      short loc_180066144
0x1800660e6  xor     edx, edx
0x1800660e8  cmp     [rcx+28h], edx
0x1800660eb  jle     short loc_180066105
0x1800660ed  mov     r9, [rcx+20h]
0x1800660f1  mov     eax, edx
0x1800660f3  shl     rax, 5
0x1800660f7  cmp     [rax+r9+8], r10
0x1800660fc  jz      short loc_180066105
0x1800660fe  inc     edx
0x180066100  cmp     edx, [rcx+28h]
0x180066103  jl      short loc_1800660F1
0x180066105  movsxd  r10, edx
0x180066108  mov     r9d, r14d
0x18006610b  mov     rdx, [rcx+20h]
0x18006610f  mov     rax, r11
0x180066112  mov     rcx, [rcx+148h]
0x180066119  shl     r10, 5
0x18006611d  mov     [rsp+68h+var_48], r8d
0x180066122  mov     r8d, edi
0x180066125  mov     rdx, [r10+rdx]
0x180066129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006612e  cmp     eax, r14d
0x180066131  mov     r15d, eax
0x180066134  cmova   r15d, r14d
0x180066138  test    r15d, r15d
0x18006613b  jnz     short loc_180066147
0x18006613d  xor     eax, eax
0x18006613f  jmp     loc_1800661FF
0x180066144  mov     r15d, r14d
0x180066147  mov     r8d, r15d
0x18006614a  mov     edx, edi
0x18006614c  mov     rcx, rbx
0x18006614f  call    finalDbSize
0x180066154  mov     ebp, eax
0x180066156  cmp     eax, edi
0x180066158  jbe     short loc_180066164
0x18006615a  mov     edx, 1247Ch
0x18006615f  jmp     loc_180066213
0x180066164  jnb     short loc_180066194
0x180066166  xor     r8d, r8d
0x180066169  xor     edx, edx
0x18006616b  mov     rcx, rbx
0x18006616e  call    saveAllCursors
0x180066173  jmp     short loc_180066192
0x180066175  test    esi, esi
0x180066177  jnz     short loc_180066198
0x180066179  xor     r9d, r9d
0x18006617c  mov     r8d, edi
0x18006617f  cmp     r15d, r14d
0x180066182  mov     edx, ebp
0x180066184  mov     rcx, rbx
0x180066187  setz    r9b
0x18006618b  call    incrVacuumStep
0x180066190  dec     edi
0x180066192  mov     esi, eax
0x180066194  cmp     edi, ebp
0x180066196  ja      short loc_180066175
0x180066198  cmp     esi, 65h ; 'e'
0x18006619b  jz      short loc_1800661A1
0x18006619d  test    esi, esi
0x18006619f  jnz     short loc_1800661F5
0x1800661a1  test    r14d, r14d
0x1800661a4  jz      short loc_1800661F1
0x1800661a6  mov     rcx, [rbx+18h]
0x1800661aa  mov     rcx, [rcx+70h]
0x1800661ae  call    sqlite3PagerWrite
0x1800661b3  mov     esi, eax
0x1800661b5  cmp     r15d, r14d
0x1800661b8  jnz     short loc_1800661D8
0x1800661ba  mov     rax, [rbx+18h]
0x1800661be  mov     rcx, [rax+50h]
0x1800661c2  mov     dword ptr [rcx+20h], 0
0x1800661c9  mov     rax, [rbx+18h]
0x1800661cd  mov     rcx, [rax+50h]
0x1800661d1  mov     dword ptr [rcx+24h], 0
0x1800661d8  mov     rax, [rbx+18h]
0x1800661dc  mov     r8d, ebp
0x1800661df  bswap   r8d
0x1800661e2  mov     rdx, [rax+50h]
0x1800661e6  mov     [rdx+1Ch], r8d
0x1800661ea  mov     byte ptr [rbx+23h], 1
0x1800661ee  mov     [rbx+40h], ebp
0x1800661f1  test    esi, esi
0x1800661f3  jz      short loc_1800661FD
0x1800661f5  mov     rcx, r12
0x1800661f8  call    sqlite3PagerRollback
0x1800661fd  mov     eax, esi
0x1800661ff  add     rsp, 30h
0x180066203  pop     r15
0x180066205  pop     r14
0x180066207  pop     r12
0x180066209  pop     rdi
0x18006620a  pop     rsi
0x18006620b  pop     rbp
0x18006620c  pop     rbx
0x18006620d  retn
0x18006620e  mov     edx, 12461h
0x180066213  lea     r8, aDatabaseCorrup; "database corruption"
0x18006621a  mov     ecx, 0Bh
0x18006621f  call    sqlite3ReportError
0x180066224  jmp     short loc_1800661FF
```
