# DbTable::RebuildSecondaryIndexes(void)

- ea: `0x1800150cc`
- end: `0x1800151bb`
- name: `?RebuildSecondaryIndexes@DbTable@@AEAAJXZ`
- size: `239`
- prototype: `__int64 __fastcall(DbTable *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180014a18`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800114e4`
- `0x1800150cc`

## import_xrefs

- `ESENT!JetSetCurrentIndexW` at `0x180015113`
- `ESENT!JetSetCurrentIndexW` at `0x180015113`
- `ESENT!JetCreateIndex2W` at `0x180015138`
- `ESENT!JetCreateIndex2W` at `0x180015138`

## pseudocode

```c
__int64 __fastcall DbTable::RebuildSecondaryIndexes(JET_SESID *this)
{
  int v1; // esi
  int i; // ebx
  __int64 v4; // r8
  __int64 v5; // r14
  __int64 v6; // rcx
  JET_ERR Index2W; // ebp
  int *v8; // rax
  __int64 v9; // rcx
  int *v10; // rax
  __int64 v12; // [rsp+20h] [rbp-38h]
  int v13; // [rsp+28h] [rbp-30h]

  v1 = 0;
  for ( i = 0; i < *(_DWORD *)(*this + 56); ++i )
  {
    v4 = *(_QWORD *)(*this + 48);
    v5 = 80LL * i;
    if ( (*(_DWORD *)(v4 + v5 + 28) | 2) != 2
      && JetSetCurrentIndexW(this[5], this[9], *(JET_PCWSTR *)(v4 + v5 + 8)) == -1404 )
    {
      Index2W = JetCreateIndex2W(this[5], this[9], (JET_INDEXCREATE_W *)(v5 + *(_QWORD *)(*this + 48)), 1u);
      if ( Index2W < 0 )
      {
        v8 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v6);
        LODWORD(v12) = Index2W;
        DSLogger::LogError((DSLogger *)v8, L"DbTable::RebuildSecondaryIndexes", 448, L"JET_ERR : %d", v12);
        v1 = JetToHResult(Index2W);
        if ( v1 < 0 )
        {
          v10 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v9);
          v13 = v1;
          DSLogger::LogError(
            (DSLogger *)v10,
            L"DbTable::RebuildSecondaryIndexes",
            456,
            L"DbTable::RebuildIndexes for table %s failed! hr=0x%x.",
            *(_QWORD *)(*this + 8),
            v13);
          return (unsigned int)v1;
        }
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800150cc  push    rbx
0x1800150ce  push    rbp
0x1800150cf  push    rsi
0x1800150d0  push    rdi
0x1800150d1  push    r14
0x1800150d3  sub     rsp, 30h
0x1800150d7  xor     esi, esi
0x1800150d9  mov     rdi, rcx
0x1800150dc  xor     ebx, ebx
0x1800150de  mov     rcx, [rdi]
0x1800150e1  cmp     ebx, [rcx+38h]
0x1800150e4  jge     loc_1800151AE
0x1800150ea  mov     r8, [rcx+30h]
0x1800150ee  movsxd  rax, ebx
0x1800150f1  lea     r14, [rax+rax*4]
0x1800150f5  shl     r14, 4
0x1800150f9  mov     eax, [r8+r14+1Ch]
0x1800150fe  or      eax, 2
0x180015101  cmp     eax, 2
0x180015104  jz      short loc_180015176
0x180015106  mov     r8, [r8+r14+8]; szIndexName
0x18001510b  mov     rdx, [rdi+48h]; tableid
0x18001510f  mov     rcx, [rdi+28h]; sesid
0x180015113  call    cs:__imp_JetSetCurrentIndexW
0x180015119  cmp     eax, 0FFFFFA84h
0x18001511e  jnz     short loc_180015176
0x180015120  mov     rax, [rdi]
0x180015123  mov     r9d, 1; cIndexCreate
0x180015129  mov     rdx, [rdi+48h]; tableid
0x18001512d  mov     rcx, [rdi+28h]; sesid
0x180015131  mov     r8, [rax+30h]
0x180015135  add     r8, r14; pindexcreate
0x180015138  call    cs:__imp_JetCreateIndex2W
0x18001513e  mov     ebp, eax
0x180015140  test    eax, eax
0x180015142  jns     short loc_180015176
0x180015144  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180015149  lea     r9, aJetErrD; "JET_ERR : %d"
0x180015150  mov     dword ptr [rsp+58h+var_38], ebp
0x180015154  mov     r8d, 1C0h; unsigned int
0x18001515a  lea     rdx, aDbtableRebuild; "DbTable::RebuildSecondaryIndexes"
0x180015161  mov     rcx, rax; this
0x180015164  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180015169  mov     ecx, ebp; int
0x18001516b  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180015170  mov     esi, eax
0x180015172  test    eax, eax
0x180015174  js      short loc_18001517D
0x180015176  inc     ebx
0x180015178  jmp     loc_1800150DE
0x18001517d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180015182  mov     rcx, [rdi]
0x180015185  lea     r9, aDbtableRebuild_0; "DbTable::RebuildIndexes for table %s fa"...
0x18001518c  mov     [rsp+58h+var_30], esi
0x180015190  lea     rdx, aDbtableRebuild; "DbTable::RebuildSecondaryIndexes"
0x180015197  mov     r8d, 1C8h; unsigned int
0x18001519d  mov     rcx, [rcx+8]
0x1800151a1  mov     [rsp+58h+var_38], rcx
0x1800151a6  mov     rcx, rax; this
0x1800151a9  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800151ae  mov     eax, esi
0x1800151b0  add     rsp, 30h
0x1800151b4  pop     r14
0x1800151b6  pop     rdi
0x1800151b7  pop     rsi
0x1800151b8  pop     rbp
0x1800151b9  pop     rbx
0x1800151ba  retn
```
