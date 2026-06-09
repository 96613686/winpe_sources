# CPersistStreamInit::WriteRow(CRowInfo &,unsigned __int64)

- ea: `0x18001e44c`
- end: `0x18001e79d`
- name: `?WriteRow@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_K@Z`
- size: `849`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18001d9f4`

## callees

- `0x180003abc`
- `0x1800041f8`
- `0x18001a6c8`
- `0x18001acfc`
- `0x18001c818`
- `0x18001d168`
- `0x18001d9f4`
- `0x18001e000`
- `0x18001e44c`
- `0x18001eb04`
- `0x18001ec64`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteRow(CPersistStreamInit *this, struct CRowInfo *a2, __int64 a3)
{
  __int64 *v3; // r14
  unsigned int v4; // r13d
  int v8; // edi
  bool v9; // r9
  __int64 v10; // rdx
  unsigned int i; // r12d
  __int64 v12; // r9
  __int64 v13; // r8
  int v14; // eax
  bool v15; // r9
  __int64 v16; // rdx
  unsigned int v17; // ebp
  CPersistStreamInit *v18; // rcx
  __int64 v19; // rbp
  unsigned int j; // r15d
  __int64 v21; // r14
  unsigned int k; // r12d
  unsigned __int16 v23; // dx
  __int64 v24; // rcx
  int v26; // [rsp+20h] [rbp-58h]

  v3 = (__int64 *)*((_QWORD *)a2 + 23);
  v4 = 0;
  if ( *((_DWORD *)a2 + 48)
    || (v8 = CPersistStreamInit::WriteRowHeader(this, a2, 0), v8 >= 0)
    && ((v10 = *((_QWORD *)a2 + 30)) == 0
     || (unsigned int)a3 >= *((_DWORD *)a2 + 62)
     || (*(_BYTE *)(((__int64)(int)a3 >> 3) + v10 + 4) & *((_BYTE *)bits + (a3 & 7))) == 0
     || (v8 = CPersistStreamInit::WriteAttributeDefinition(
                this,
                *(void **)(*((_QWORD *)this + 9) + 496LL),
                *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
                v9,
                65,
                0),
         v8 >= 0)) )
  {
    for ( i = 0; i < *((_DWORD *)a2 + 48); ++i )
    {
      v12 = *((_QWORD *)a2 + 11);
      v13 = *v3;
      if ( ((*((_DWORD *)a2 + 49) - 2) & 0xFFFFFFFD) != 0 )
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)a2 + 13) + 32LL))(
                *((_QWORD *)a2 + 13),
                a3,
                v13,
                v12);
        v8 = v14;
        if ( v14 == -2147217885 )
        {
          v8 = 0;
          goto LABEL_44;
        }
        if ( ((v14 + 0x80000000) & 0x80000000) == 0 && v14 != -2147217887 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048B50[0] )
            bidTraceW(off_1800481F0[0], 2278400, off_180048B50[0], 2225, v26);
          goto LABEL_44;
        }
      }
      else
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)a2 + 14) + 48LL))(
               *((_QWORD *)a2 + 14),
               a3,
               v13,
               v12);
        if ( v8 < 0 )
          goto LABEL_44;
      }
      if ( !i )
      {
        v8 = CPersistStreamInit::WriteRowHeader(this, a2, 0);
        if ( v8 < 0 )
          goto LABEL_44;
        v16 = *((_QWORD *)a2 + 30);
        if ( v16 )
        {
          if ( (unsigned int)a3 < *((_DWORD *)a2 + 62)
            && (*(_BYTE *)(((__int64)(int)a3 >> 3) + v16 + 4) & *((_BYTE *)bits + (a3 & 7))) != 0 )
          {
            v8 = CPersistStreamInit::WriteAttributeDefinition(
                   this,
                   *(void **)(*((_QWORD *)this + 9) + 496LL),
                   *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
                   v15,
                   65,
                   0);
            if ( v8 < 0 )
              goto LABEL_44;
          }
        }
      }
      v17 = 0;
      if ( *((_DWORD *)v3 + 4) )
      {
        while ( 1 )
        {
          v8 = CPersistStreamInit::WriteColumnToStream(
                 this,
                 a2,
                 *((_WORD *)v3 + 10) + (unsigned __int16)v17,
                 (struct tagDBBINDING *)(v3[1] + 88LL * v17));
          if ( v8 < 0 )
            break;
          if ( ++v17 >= *((_DWORD *)v3 + 4) )
            goto LABEL_26;
        }
        CPersistStreamInit::FreeFetchedData(v18, a2, (struct tagDBBINDING *)v3[1], *((_DWORD *)v3 + 4));
        goto LABEL_44;
      }
LABEL_26:
      v3 += 3;
    }
    if ( *((_DWORD *)a2 + 32) )
    {
      CPersistStreamInit::WriteRowHeader(this, a2, 1);
      v19 = *((_QWORD *)a2 + 23);
      for ( j = 0; j < *((_DWORD *)a2 + 48); ++j )
      {
        v21 = *(_QWORD *)(v19 + 8);
        for ( k = 0; k < *(_DWORD *)(v19 + 16); ++k )
        {
          if ( (CMetaData::mdGetFlags(a2, *(_WORD *)v21 - 1) & 0x2000) != 0 || CMetaData::mdGetType(a2, v23) == 136 )
          {
            v24 = *((_QWORD *)a2 + 11);
            if ( !*(_DWORD *)(v24 + *(_QWORD *)(v21 + 24)) )
            {
              v8 = CPersistStreamInit::WriteData(
                     this,
                     (struct CRowInfo *)(*((_QWORD *)a2 + 17) + ((unsigned __int64)v4 << 8)),
                     *(void **)(*(_QWORD *)(v21 + 8) + v24));
              if ( v8 < 0 )
                goto LABEL_44;
              ++v4;
            }
          }
          v21 += 88;
        }
        v19 += 24;
      }
    }
    if ( !*((_WORD *)a2 + 112) || (v8 = CPersistStreamInit::WriteForceNull(this, a2), v8 >= 0) )
      v8 = CPersistStreamInit::WriteRowFooter(this, a2, *((_DWORD *)a2 + 32) != 0);
  }
LABEL_44:
  *((_WORD *)a2 + 112) = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e44c  push    rbx
0x18001e44e  push    rbp
0x18001e44f  push    rsi
0x18001e450  push    rdi
0x18001e451  push    r12
0x18001e453  push    r13
0x18001e455  push    r14
0x18001e457  push    r15
0x18001e459  sub     rsp, 38h
0x18001e45d  mov     r14, [rdx+0B8h]
0x18001e464  lea     rbp, bits
0x18001e46b  xor     r13d, r13d
0x18001e46e  mov     r15, r8
0x18001e471  mov     rbx, rdx
0x18001e474  mov     rsi, rcx
0x18001e477  cmp     [rdx+0C0h], r13d
0x18001e47e  jnz     short loc_18001E4EB
0x18001e480  xor     r8d, r8d; bool
0x18001e483  call    ?WriteRowHeader@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_N@Z; CPersistStreamInit::WriteRowHeader(CRowInfo &,bool)
0x18001e488  mov     edi, eax
0x18001e48a  test    eax, eax
0x18001e48c  js      loc_18001E782
0x18001e492  mov     rdx, [rbx+0F0h]
0x18001e499  test    rdx, rdx
0x18001e49c  jz      short loc_18001E4EB
0x18001e49e  cmp     r15d, [rbx+0F8h]
0x18001e4a5  jnb     short loc_18001E4EB
0x18001e4a7  movsxd  rcx, r15d
0x18001e4aa  mov     rax, rcx
0x18001e4ad  and     ecx, 7
0x18001e4b0  sar     rax, 3
0x18001e4b4  mov     al, [rax+rdx+4]
0x18001e4b8  test    [rcx+rbp], al
0x18001e4bb  jz      short loc_18001E4EB
0x18001e4bd  mov     rdx, [rsi+48h]
0x18001e4c1  mov     rcx, rsi; this
0x18001e4c4  mov     [rsp+78h+var_50], r13b; bool
0x18001e4c9  mov     [rsp+78h+var_58], 41h ; 'A'; char
0x18001e4ce  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001e4d5  mov     rdx, [rdx+1F0h]; void *
0x18001e4dc  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001e4e1  mov     edi, eax
0x18001e4e3  test    eax, eax
0x18001e4e5  js      loc_18001E782
0x18001e4eb  mov     r12d, r13d
0x18001e4ee  mov     edi, 1
0x18001e4f3  mov     ebp, 80000000h
0x18001e4f8  cmp     r12d, [rbx+0C0h]
0x18001e4ff  jnb     loc_18001E68B
0x18001e505  mov     eax, [rbx+0C4h]
0x18001e50b  mov     rdx, r15
0x18001e50e  mov     r9, [rbx+58h]
0x18001e512  sub     eax, 2
0x18001e515  mov     r8, [r14]
0x18001e518  test    eax, 0FFFFFFFDh
0x18001e51d  jz      short loc_18001E58A
0x18001e51f  mov     rcx, [rbx+68h]
0x18001e523  mov     rax, [rcx]
0x18001e526  mov     rax, [rax+20h]
0x18001e52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e52f  mov     edi, eax
0x18001e531  cmp     eax, 80040E23h
0x18001e536  jz      loc_18001E66E
0x18001e53c  add     eax, ebp
0x18001e53e  test    ebp, eax
0x18001e540  jnz     short loc_18001E5A4
0x18001e542  cmp     edi, 80040E21h
0x18001e548  jz      short loc_18001E5A4
0x18001e54a  test    byte ptr cs:_bidGblFlags, 2
0x18001e551  jz      loc_18001E782
0x18001e557  mov     rax, cs:off_180048B50; "<CPersistStreamInit::WriteRow|ADO|ERR> "...
0x18001e55e  test    rax, rax
0x18001e561  jz      loc_18001E782
0x18001e567  mov     r8, cs:off_180048B50; "<CPersistStreamInit::WriteRow|ADO|ERR> "...
0x18001e56e  mov     r9d, 8B1h
0x18001e574  mov     rcx, cs:off_1800481F0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001e57b  mov     edx, 22C400h
0x18001e580  call    _bidTraceW
0x18001e585  jmp     loc_18001E782
0x18001e58a  mov     rcx, [rbx+70h]
0x18001e58e  mov     rax, [rcx]
0x18001e591  mov     rax, [rax+30h]
0x18001e595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e59a  mov     edi, eax
0x18001e59c  test    eax, eax
0x18001e59e  js      loc_18001E782
0x18001e5a4  test    r12d, r12d
0x18001e5a7  jnz     short loc_18001E621
0x18001e5a9  xor     r8d, r8d; bool
0x18001e5ac  mov     rdx, rbx; struct CRowInfo *
0x18001e5af  mov     rcx, rsi; this
0x18001e5b2  call    ?WriteRowHeader@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_N@Z; CPersistStreamInit::WriteRowHeader(CRowInfo &,bool)
0x18001e5b7  mov     edi, eax
0x18001e5b9  test    eax, eax
0x18001e5bb  js      loc_18001E782
0x18001e5c1  mov     rdx, [rbx+0F0h]
0x18001e5c8  test    rdx, rdx
0x18001e5cb  jz      short loc_18001E621
0x18001e5cd  cmp     r15d, [rbx+0F8h]
0x18001e5d4  jnb     short loc_18001E621
0x18001e5d6  movsxd  rcx, r15d
0x18001e5d9  mov     rax, rcx
0x18001e5dc  and     ecx, 7
0x18001e5df  sar     rax, 3
0x18001e5e3  mov     al, [rax+rdx+4]
0x18001e5e7  lea     rdx, bits
0x18001e5ee  test    [rcx+rdx], al
0x18001e5f1  jz      short loc_18001E621
0x18001e5f3  mov     rdx, [rsi+48h]
0x18001e5f7  mov     rcx, rsi; this
0x18001e5fa  mov     [rsp+78h+var_50], r13b; bool
0x18001e5ff  mov     [rsp+78h+var_58], 41h ; 'A'; char
0x18001e604  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001e60b  mov     rdx, [rdx+1F0h]; void *
0x18001e612  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001e617  mov     edi, eax
0x18001e619  test    eax, eax
0x18001e61b  js      loc_18001E782
0x18001e621  mov     ebp, r13d
0x18001e624  cmp     [r14+10h], r13d
0x18001e628  jbe     short loc_18001E65D
0x18001e62a  mov     eax, ebp
0x18001e62c  movzx   r8d, bp
0x18001e630  add     r8w, [r14+14h]; unsigned __int16
0x18001e635  mov     rdx, rbx; struct CRowInfo *
0x18001e638  imul    r9, rax, 58h ; 'X'
0x18001e63c  mov     rcx, rsi; this
0x18001e63f  add     r9, [r14+8]; struct tagDBBINDING *
0x18001e643  call    ?WriteColumnToStream@CPersistStreamInit@@AEAAJAEAVCRowInfo@@GPEAUtagDBBINDING@@@Z; CPersistStreamInit::WriteColumnToStream(CRowInfo &,ushort,tagDBBINDING *)
0x18001e648  mov     edi, eax
0x18001e64a  test    eax, eax
0x18001e64c  js      short loc_18001E676
0x18001e64e  mov     edi, 1
0x18001e653  add     ebp, edi
0x18001e655  cmp     ebp, [r14+10h]
0x18001e659  jb      short loc_18001E62A
0x18001e65b  jmp     short loc_18001E662
0x18001e65d  mov     edi, 1
0x18001e662  add     r12d, edi
0x18001e665  add     r14, 18h
0x18001e669  jmp     loc_18001E4F3
0x18001e66e  mov     edi, r13d
0x18001e671  jmp     loc_18001E782
0x18001e676  mov     r9d, [r14+10h]; unsigned int
0x18001e67a  mov     rdx, rbx; struct CRowInfo *
0x18001e67d  mov     r8, [r14+8]; struct tagDBBINDING *
0x18001e681  call    ?FreeFetchedData@CPersistStreamInit@@AEAAXAEAVCRowInfo@@PEAUtagDBBINDING@@K@Z; CPersistStreamInit::FreeFetchedData(CRowInfo &,tagDBBINDING *,ulong)
0x18001e686  jmp     loc_18001E782
0x18001e68b  cmp     [rbx+80h], r13d
0x18001e692  jz      loc_18001E74A
0x18001e698  mov     r8b, dil; bool
0x18001e69b  mov     rdx, rbx; struct CRowInfo *
0x18001e69e  mov     rcx, rsi; this
0x18001e6a1  call    ?WriteRowHeader@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_N@Z; CPersistStreamInit::WriteRowHeader(CRowInfo &,bool)
0x18001e6a6  mov     rbp, [rbx+0B8h]
0x18001e6ad  xor     r15d, r15d
0x18001e6b0  cmp     r15d, [rbx+0C0h]
0x18001e6b7  jnb     loc_18001E747
0x18001e6bd  mov     r14, [rbp+8]
0x18001e6c1  xor     r12d, r12d
0x18001e6c4  cmp     r12d, [rbp+10h]
0x18001e6c8  jnb     short loc_18001E73B
0x18001e6ca  movzx   eax, word ptr [r14]
0x18001e6ce  mov     rcx, rbx; this
0x18001e6d1  sub     ax, di
0x18001e6d4  movzx   edx, ax; unsigned __int16
0x18001e6d7  movzx   r10d, ax
0x18001e6db  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001e6e0  bt      eax, 0Dh
0x18001e6e4  jb      short loc_18001E6F8
0x18001e6e6  mov     rcx, rbx; this
0x18001e6e9  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001e6ee  mov     ecx, 88h
0x18001e6f3  cmp     ax, cx
0x18001e6f6  jnz     short loc_18001E732
0x18001e6f8  mov     rcx, [rbx+58h]
0x18001e6fc  mov     rax, [r14+18h]
0x18001e700  cmp     dword ptr [rcx+rax], 0
0x18001e704  jnz     short loc_18001E732
0x18001e706  mov     r8, [r14+8]
0x18001e70a  mov     edx, r13d
0x18001e70d  shl     rdx, 8
0x18001e711  add     rdx, [rbx+88h]; struct CRowInfo *
0x18001e718  mov     r8, [r8+rcx]; unsigned __int64
0x18001e71c  mov     rcx, rsi; this
0x18001e71f  call    ?WriteData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_K@Z; CPersistStreamInit::WriteData(CRowInfo &,unsigned __int64)
0x18001e724  mov     edi, eax
0x18001e726  test    eax, eax
0x18001e728  js      short loc_18001E77F
0x18001e72a  mov     edi, 1
0x18001e72f  add     r13d, edi
0x18001e732  add     r12d, edi
0x18001e735  add     r14, 58h ; 'X'
0x18001e739  jmp     short loc_18001E6C4
0x18001e73b  add     r15d, edi
0x18001e73e  add     rbp, 18h
0x18001e742  jmp     loc_18001E6B0
0x18001e747  xor     r13d, r13d
0x18001e74a  cmp     [rbx+0E0h], r13w
0x18001e752  jz      short loc_18001E765
0x18001e754  mov     rdx, rbx; struct CRowInfo *
0x18001e757  mov     rcx, rsi; this
0x18001e75a  call    ?WriteForceNull@CPersistStreamInit@@AEAAJAEAVCRowInfo@@@Z; CPersistStreamInit::WriteForceNull(CRowInfo &)
0x18001e75f  mov     edi, eax
0x18001e761  test    eax, eax
0x18001e763  js      short loc_18001E782
0x18001e765  cmp     [rbx+80h], r13d
0x18001e76c  mov     rdx, rbx; struct CRowInfo *
0x18001e76f  mov     rcx, rsi; this
0x18001e772  setnz   r8b; bool
0x18001e776  call    ?WriteRowFooter@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_N@Z; CPersistStreamInit::WriteRowFooter(CRowInfo &,bool)
0x18001e77b  mov     edi, eax
0x18001e77d  jmp     short loc_18001E782
0x18001e77f  xor     r13d, r13d
0x18001e782  mov     [rbx+0E0h], r13w
0x18001e78a  mov     eax, edi
0x18001e78c  add     rsp, 38h
0x18001e790  pop     r15
0x18001e792  pop     r14
0x18001e794  pop     r13
0x18001e796  pop     r12
0x18001e798  pop     rdi
0x18001e799  pop     rsi
0x18001e79a  pop     rbp
0x18001e79b  pop     rbx
0x18001e79c  retn
```
