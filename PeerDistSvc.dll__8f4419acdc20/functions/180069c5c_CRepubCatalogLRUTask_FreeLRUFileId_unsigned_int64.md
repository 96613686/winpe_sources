# CRepubCatalogLRUTask::FreeLRUFileId(unsigned __int64)

- ea: `0x180069c5c`
- end: `0x180069f33`
- name: `?FreeLRUFileId@CRepubCatalogLRUTask@@IEAAK_K@Z`
- size: `727`
- prototype: `unsigned int __fastcall(CRepubCatalogLRUTask *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x18006b9fc`

## callees

- `0x1800024a4`
- `0x180008290`
- `0x1800082d0`
- `0x18000e58c`
- `0x18002a878`
- `0x180069c5c`
- `0x180069f3c`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180069e24`
- `ESENT!JetPrepareUpdate` at `0x180069e24`
- `ESENT!JetSetColumns` at `0x180069e7f`
- `ESENT!JetSetColumns` at `0x180069e7f`
- `ESENT!JetUpdate` at `0x180069ec4`
- `ESENT!JetUpdate` at `0x180069ec4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRepubCatalogLRUTask::FreeLRUFileId(JET_SETCOLUMN **this, __int64 a2)
{
  unsigned int BlockDatabaseIndex; // eax
  unsigned int v5; // edi
  CHostedCacheMsgEncoding *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rdx
  void **v9; // r8
  __int64 v10; // r9
  JET_SESID *v11; // rsi
  JET_SETCOLUMN *v12; // rcx
  JET_SESID v13; // rax
  __int64 v14; // r14
  JET_COLUMNID v15; // edx
  JET_SETCOLUMN *v16; // rax
  unsigned int v17; // ebp
  CHostedCacheMsgEncoding *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // esi
  _QWORD v24[7]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v25; // [rsp+80h] [rbp+18h] BYREF
  __int64 (__fastcall ***v26)(_QWORD, __int64); // [rsp+88h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 506, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
  }
  v26 = 0;
  v25 = 0;
  BlockDatabaseIndex = CRepubCatalogLRUTask::GetBlockDatabaseIndex((CRepubCatalogLRUTask *)this, &v25);
  v5 = BlockDatabaseIndex;
  if ( BlockDatabaseIndex )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v7 = 507;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v6 + 12), v7, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, BlockDatabaseIndex);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  v8 = operator new(0x20u);
  v24[1] = v8;
  v11 = (JET_SESID *)(this + 47);
  if ( v8 )
  {
    v12 = this[v25 + 67];
    v13 = *v11;
    v9 = &CFileTableFileIdIterator::`vftable';
    *v8 = &CFileTableFileIdIterator::`vftable';
    v8[2] = v13;
    v8[3] = v12;
    v8[1] = a2;
  }
  else
  {
    v8 = 0;
  }
  std::auto_ptr<TnoHashKey>::reset(&v26, v8, v9, v10);
  BlockDatabaseIndex = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64)))(*v26)[1])(v26);
  v5 = BlockDatabaseIndex;
  if ( !BlockDatabaseIndex )
  {
    v24[0] = 1;
    v14 = v25;
    v15 = *(&this[52][15].err + 192 * v25 + 1);
    v16 = this[50];
    *(&v16->columnid + 1) = 0;
    *(_QWORD *)&v16->grbit = 0;
    *(_QWORD *)&v16->err = 0;
    v16->columnid = v15;
    v16->cbData = 8;
    v16->pvData = v24;
    v16->itagSequence = 1;
    v17 = JetPrepareUpdate(*v11, (JET_TABLEID)this[v14 + 67], 2u);
    if ( v17 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_25;
      }
      v19 = 509;
    }
    else
    {
      v17 = JetSetColumns(*v11, (JET_TABLEID)this[v14 + 67], this[50], 1u);
      if ( !v17 )
      {
        v21 = JetUpdate(*v11, (JET_TABLEID)this[v14 + 67], 0, 0, 0);
        v22 = v21;
        if ( !v21 )
          goto LABEL_38;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 511, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v21);
        }
        v20 = v22;
LABEL_37:
        v5 = ((__int64 (__fastcall *)(JET_SETCOLUMN **, __int64))(*this)[1].pvData)(this, v20);
        goto LABEL_38;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
LABEL_25:
        v20 = v17;
        goto LABEL_37;
      }
      v19 = 510;
    }
    WPP_SF_d(*((_QWORD *)v18 + 12), v19, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v17);
    goto LABEL_25;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v7 = 508;
    goto LABEL_10;
  }
LABEL_38:
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(&v26);
  return v5;
}

```

## disassembly

```asm
0x180069c5c  mov     [rsp+arg_0], rbx
0x180069c61  push    rbp
0x180069c62  push    rsi
0x180069c63  push    rdi
0x180069c64  push    r13
0x180069c66  push    r14
0x180069c68  sub     rsp, 40h
0x180069c6c  mov     rbp, rdx
0x180069c6f  mov     rbx, rcx
0x180069c72  lea     r13, WPP_GLOBAL_Control
0x180069c79  lea     r14, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180069c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180069c87  cmp     rcx, r13
0x180069c8a  jz      short loc_180069CAC
0x180069c8c  test    byte ptr [rcx+6Ch], 4
0x180069c90  jz      short loc_180069CAC
0x180069c92  cmp     byte ptr [rcx+69h], 4
0x180069c96  jb      short loc_180069CAC
0x180069c98  mov     edx, 1FAh
0x180069c9d  mov     r9, rbp
0x180069ca0  mov     r8, r14
0x180069ca3  mov     rcx, [rcx+60h]
0x180069ca7  call    WPP_SF_q
0x180069cac  mov     [rsp+68h+arg_18], 0
0x180069cb8  mov     [rsp+68h+arg_10], 0
0x180069cc3  lea     rdx, [rsp+68h+arg_10]; unsigned int *
0x180069ccb  mov     rcx, rbx; this
0x180069cce  call    ?GetBlockDatabaseIndex@CRepubCatalogLRUTask@@IEAAKPEAK@Z; CRepubCatalogLRUTask::GetBlockDatabaseIndex(ulong *)
0x180069cd3  mov     edi, eax
0x180069cd5  test    eax, eax
0x180069cd7  jz      short loc_180069D16
0x180069cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180069ce0  cmp     rcx, r13
0x180069ce3  jz      loc_180069F13
0x180069ce9  test    byte ptr [rcx+6Ch], 4
0x180069ced  jz      loc_180069F13
0x180069cf3  cmp     byte ptr [rcx+69h], 1
0x180069cf7  jb      loc_180069F13
0x180069cfd  mov     edx, 1FBh
0x180069d02  mov     r9d, eax
0x180069d05  mov     r8, r14
0x180069d08  mov     rcx, [rcx+60h]
0x180069d0c  call    WPP_SF_d
0x180069d11  jmp     loc_180069F13
0x180069d16  mov     ecx, 20h ; ' '; Size
0x180069d1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069d20  mov     rdx, rax
0x180069d23  mov     [rsp+68h+var_30], rax
0x180069d28  lea     rsi, [rbx+178h]
0x180069d2f  test    rax, rax
0x180069d32  jz      short loc_180069D5E
0x180069d34  mov     eax, [rsp+68h+arg_10]
0x180069d3b  mov     rcx, [rbx+rax*8+218h]
0x180069d43  mov     rax, [rsi]
0x180069d46  lea     r8, ??_7CFileTableFileIdIterator@@6B@; const CFileTableFileIdIterator::`vftable'
0x180069d4d  mov     [rdx], r8
0x180069d50  mov     [rdx+10h], rax
0x180069d54  mov     [rdx+18h], rcx
0x180069d58  mov     [rdx+8], rbp
0x180069d5c  jmp     short loc_180069D60
0x180069d5e  xor     edx, edx
0x180069d60  lea     rcx, [rsp+68h+arg_18]
0x180069d68  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x180069d6d  mov     rcx, [rsp+68h+arg_18]
0x180069d75  mov     rax, [rcx]
0x180069d78  mov     rax, [rax+8]
0x180069d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d81  mov     edi, eax
0x180069d83  test    eax, eax
0x180069d85  jz      short loc_180069DB5
0x180069d87  mov     rcx, cs:WPP_GLOBAL_Control
0x180069d8e  cmp     rcx, r13
0x180069d91  jz      loc_180069F13
0x180069d97  test    byte ptr [rcx+6Ch], 4
0x180069d9b  jz      loc_180069F13
0x180069da1  cmp     byte ptr [rcx+69h], 1
0x180069da5  jb      loc_180069F13
0x180069dab  mov     edx, 1FCh
0x180069db0  jmp     loc_180069D02
0x180069db5  mov     [rsp+68h+var_38], 1
0x180069dbe  mov     r14d, [rsp+68h+arg_10]
0x180069dc6  lea     rcx, [r14+r14*2]
0x180069dca  shl     rcx, 8
0x180069dce  mov     rax, [rbx+1A0h]
0x180069dd5  mov     edx, [rcx+rax+27Ch]
0x180069ddc  mov     rax, [rbx+190h]
0x180069de3  mov     dword ptr [rax+4], 0
0x180069dea  mov     qword ptr [rax+14h], 0
0x180069df2  mov     qword ptr [rax+20h], 0
0x180069dfa  mov     [rax], edx
0x180069dfc  mov     dword ptr [rax+10h], 8
0x180069e03  lea     rcx, [rsp+68h+var_38]
0x180069e08  mov     [rax+8], rcx
0x180069e0c  mov     dword ptr [rax+1Ch], 1
0x180069e13  mov     r8d, 2; prep
0x180069e19  mov     rdx, [rbx+r14*8+218h]; tableid
0x180069e21  mov     rcx, [rsi]; sesid
0x180069e24  call    cs:__imp_JetPrepareUpdate
0x180069e2a  mov     ebp, eax
0x180069e2c  test    eax, eax
0x180069e2e  jz      short loc_180069E67
0x180069e30  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e37  cmp     rcx, r13
0x180069e3a  jz      short loc_180069E60
0x180069e3c  test    byte ptr [rcx+6Ch], 4
0x180069e40  jz      short loc_180069E60
0x180069e42  cmp     byte ptr [rcx+69h], 1
0x180069e46  jb      short loc_180069E60
0x180069e48  mov     edx, 1FDh
0x180069e4d  mov     r9d, ebp
0x180069e50  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180069e57  mov     rcx, [rcx+60h]
0x180069e5b  call    WPP_SF_d
0x180069e60  mov     edx, ebp
0x180069e62  jmp     loc_180069F02
0x180069e67  mov     r9d, 1; csetcolumn
0x180069e6d  mov     r8, [rbx+190h]; psetcolumn
0x180069e74  mov     rdx, [rbx+r14*8+218h]; tableid
0x180069e7c  mov     rcx, [rsi]; sesid
0x180069e7f  call    cs:__imp_JetSetColumns
0x180069e85  mov     ebp, eax
0x180069e87  test    eax, eax
0x180069e89  jz      short loc_180069EAA
0x180069e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e92  cmp     rcx, r13
0x180069e95  jz      short loc_180069E60
0x180069e97  test    byte ptr [rcx+6Ch], 4
0x180069e9b  jz      short loc_180069E60
0x180069e9d  cmp     byte ptr [rcx+69h], 1
0x180069ea1  jb      short loc_180069E60
0x180069ea3  mov     edx, 1FEh
0x180069ea8  jmp     short loc_180069E4D
0x180069eaa  mov     [rsp+68h+pcbActual], 0; pcbActual
0x180069eb3  xor     r9d, r9d; cbBookmark
0x180069eb6  xor     r8d, r8d; pvBookmark
0x180069eb9  mov     rdx, [rbx+r14*8+218h]; tableid
0x180069ec1  mov     rcx, [rsi]; sesid
0x180069ec4  call    cs:__imp_JetUpdate
0x180069eca  mov     esi, eax
0x180069ecc  test    eax, eax
0x180069ece  jz      short loc_180069F13
0x180069ed0  mov     rcx, cs:WPP_GLOBAL_Control
0x180069ed7  cmp     rcx, r13
0x180069eda  jz      short loc_180069F00
0x180069edc  test    byte ptr [rcx+6Ch], 4
0x180069ee0  jz      short loc_180069F00
0x180069ee2  cmp     byte ptr [rcx+69h], 1
0x180069ee6  jb      short loc_180069F00
0x180069ee8  mov     edx, 1FFh
0x180069eed  mov     r9d, eax
0x180069ef0  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180069ef7  mov     rcx, [rcx+60h]
0x180069efb  call    WPP_SF_d
0x180069f00  mov     edx, esi
0x180069f02  mov     rax, [rbx]
0x180069f05  mov     rcx, rbx
0x180069f08  mov     rax, [rax+30h]
0x180069f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f11  mov     edi, eax
0x180069f13  lea     rcx, [rsp+68h+arg_18]
0x180069f1b  call    ??1?$auto_ptr@VCRepubCacheMigrateWorkItem@@@std@@QEAA@XZ; std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(void)
0x180069f20  mov     eax, edi
0x180069f22  mov     rbx, [rsp+68h+arg_0]
0x180069f27  add     rsp, 40h
0x180069f2b  pop     r14
0x180069f2d  pop     r13
0x180069f2f  pop     rdi
0x180069f30  pop     rsi
0x180069f31  pop     rbp
0x180069f32  retn
```
