# StateRepository::Entity::TileView::FindByUserAndGTChangeIdAndTileViewQueryFilter(StateRepository::Database &,__int64,__int64,StateRepository::Entity::TileViewQueryFilter const &,StateRepository::Statement &)

- ea: `0x180011bfc`
- end: `0x180012224`
- name: `?FindByUserAndGTChangeIdAndTileViewQueryFilter@TileView@Entity@StateRepository@@SAJAEAVDatabase@3@_J1AEBVTileViewQueryFilter@23@AEAVStatement@3@@Z`
- size: `1576`
- prototype: `__int64 __fastcall(struct StateRepository::Database *, __int64, __int64, const struct StateRepository::Entity::TileViewQueryFilter *, struct StateRepository::Statement *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops`

## callers

- `0x180040e40`

## callees

- `0x180010034`
- `0x1800105b8`
- `0x180010630`
- `0x180010754`
- `0x180011bc0`
- `0x180011bfc`
- `0x18001222c`
- `0x180012384`
- `0x1800131f8`
- `0x180017a58`
- `0x18001a548`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180066da0`
- `0x180078ca0`
- `0x1800ad7dc`
- `0x18018fb5c`
- `0x18019914d`
- `0x18020b074`

## import_xrefs

- `StateRepository.Core!sqlite3_bind_int64` at `0x180011ecf`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180011f23`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180011f50`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180011ecf`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180011f23`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180011f50`

## string_xrefs

- `0x180011da3`: `onecore\base\appmodel\staterepository\dataaccesslayer\texta.cpp`
- `0x180011dd0`: `onecore\base\appmodel\staterepository\dataaccesslayer\texta.cpp`
- `0x180011ded`: `onecore\base\appmodel\staterepository\dataaccesslayer\texta.cpp`
- `0x180011c29`: `SELECT tv._TileViewID, tv._Revision, tv._WorkId, tv.Application, tv.Package, tv.Flags, tv.TileType, tv.TileTemplate, tv.TileId, tv.Arguments, tv.EditionId, tv._Dictionary, tv._TileUserID, tv._TileUser_Revision, tv._Created, tv._Modified, tv.User, tv.ApplicationIdentity, tv.State, tv.TileUniqueId, tv.ApplicationUserModelId FROM TileView AS tv WHERE tv.User=? AND (tv._Created>? OR tv._Modified>?)`
- `0x180011c57`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-tileview-custom.cpp`
- `0x180011e58`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-tileview-custom.cpp`
- `0x180011ea9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-tileview-custom.cpp`
- `0x18001202e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-tileview-custom.cpp`
- `0x180012099`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-tileview-custom.cpp`
- `0x1800121eb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-tileview-custom.cpp`
- `0x1800120e9`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180012176`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180011e84`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180011ef4`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180011ff2`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18001215e`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::TileView::FindByUserAndGTChangeIdAndTileViewQueryFilter(
        struct StateRepository::Database *a1,
        __int64 a2,
        __int64 a3,
        const struct StateRepository::Entity::TileViewQueryFilter *a4,
        struct sqlite3_stmt **a5)
{
  __int64 v5; // r15
  struct StateRepository::Database *v6; // r13
  signed int v8; // ebx
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  void *v11; // rcx
  const char *v13; // r12
  __int64 v14; // rsi
  unsigned __int64 v15; // rbx
  void *v16; // rdi
  void *v17; // rax
  void *v18; // r13
  unsigned __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  struct sqlite3_stmt **v22; // rax
  int v23; // r8d
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // ebx
  int v30; // r8d
  int v31; // r8d
  const unsigned __int16 *v32; // r8
  int v33; // r15d
  const unsigned __int16 *v34; // r8
  int v35; // eax
  unsigned __int64 v36; // rdx
  int v37; // eax
  unsigned int v38; // r14d
  unsigned __int64 v39; // rdx
  int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rdx
  unsigned __int64 v43; // rdx
  int v44; // eax
  signed int v45; // r15d
  const char **v46; // [rsp+20h] [rbp-20h]
  int v47; // [rsp+20h] [rbp-20h]
  int v48; // [rsp+20h] [rbp-20h]
  void *Src; // [rsp+30h] [rbp-10h] BYREF
  size_t Size; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v5 = a2;
  v6 = a1;
  Src = 0;
  Size = 0;
  v8 = StateRepository::TextA::SetFromChars(
         (StateRepository::TextA *)&Src,
         "SELECT tv._TileViewID, tv._Revision, tv._WorkId, tv.Application, tv.Package, tv.Flags, tv.TileType, tv.TileTemp"
         "late, tv.TileId, tv.Arguments, tv.EditionId, tv._Dictionary, tv._TileUserID, tv._TileUser_Revision, tv._Created"
         ", tv._Modified, tv.User, tv.ApplicationIdentity, tv.State, tv.TileUniqueId, tv.ApplicationUserModelId FROM Tile"
         "View AS tv WHERE tv.User=? AND (tv._Created>? OR tv._Modified>?)",
         0x18Du);
  if ( v8 < 0 )
  {
    v9 = 17;
    goto LABEL_3;
  }
  if ( *(_DWORD *)a4 )
  {
    v8 = StateRepository::TextA::Append((StateRepository::TextA *)&Src, " AND ((tv.TileType & ?) <> 0)", 0x1Du);
    if ( v8 < 0 )
    {
      v9 = 21;
      goto LABEL_3;
    }
  }
  if ( *((_DWORD *)a4 + 1) )
  {
    v35 = StateRepository::TextA::Append((StateRepository::TextA *)&Src, " AND ((tv.Flags & ?) <> 0)");
    v8 = v35;
    if ( v35 < 0 )
    {
      v25 = 25;
LABEL_100:
      v24 = (unsigned int)v35;
      goto LABEL_39;
    }
  }
  if ( *((_DWORD *)a4 + 2) )
  {
    v35 = StateRepository::TextA::Append((StateRepository::TextA *)&Src, " AND ((tv.NotFlags & ?) = 0)");
    v8 = v35;
    if ( v35 < 0 )
    {
      v25 = 29;
      goto LABEL_100;
    }
  }
  if ( *((_QWORD *)a4 + 2) )
  {
    v8 = StateRepository::TextA::Append((StateRepository::TextA *)&Src, " AND tv.ApplicationUserModelId=?", 0x20u);
    if ( v8 < 0 )
    {
      v9 = 33;
LABEL_3:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-tileview-custom.cpp",
        (const char *)(unsigned int)v8,
        (int)v46);
      v11 = Src;
      if ( !Src )
        return (unsigned int)v8;
LABEL_4:
      operator delete(v11, v10);
      return (unsigned int)v8;
    }
  }
  if ( *((_QWORD *)a4 + 4) )
  {
    v35 = StateRepository::TextA::Append((StateRepository::TextA *)&Src, " AND tv.TileId=?");
    v8 = v35;
    if ( v35 < 0 )
    {
      v25 = 37;
      goto LABEL_100;
    }
  }
  v13 = " AND (tv._WorkId=0 OR tv._WorkId=?);";
  if ( !*((_QWORD *)v6 + 1) )
    v13 = " AND tv._WorkId=0;";
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( v13[v15] );
  if ( !v15 )
    goto LABEL_80;
  v16 = Src;
  if ( !Src )
  {
    v8 = StateRepository::TextA::SetFromChars((StateRepository::TextA *)&Src, v13, v15);
    if ( v8 < 0 )
    {
      v16 = Src;
      goto LABEL_29;
    }
LABEL_80:
    v16 = Src;
    goto LABEL_81;
  }
  do
    ++v14;
  while ( *((_BYTE *)Src + v14) );
  if ( v14 + v15 + 1 <= Size )
    goto LABEL_23;
  v17 = operator new[](v14 + v15 + 1, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( !v17 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\texta.cpp",
      (const char *)0x8007000ELL,
      (int)v46);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\texta.cpp",
      (const char *)0x8007000ELL,
      v47);
LABEL_29:
    v21 = 41;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-tileview-custom.cpp",
      (const char *)(unsigned int)v8,
      (int)v46);
    if ( !v16 )
      return (unsigned int)v8;
    v11 = v16;
    goto LABEL_4;
  }
  memcpy_0(v17, v16, Size);
  operator delete(v16, v19);
  v16 = v18;
  Src = v18;
  v6 = a1;
LABEL_23:
  v20 = StringCchCatNA((char *)v16 + v14, v15 + 1, v13, v15);
  if ( v20 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\texta.cpp",
      (const char *)(unsigned int)v20,
      (int)v46);
  Size = v14 + v15 + 1;
  v5 = a2;
LABEL_81:
  if ( !*(_QWORD *)v6 )
  {
    v8 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8007139FLL,
      (int)v46);
LABEL_33:
    v21 = 43;
    goto LABEL_34;
  }
  if ( *a5 )
  {
    v40 = StateRepository::Statement::dal_finalize(*a5);
    v41 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)(unsigned int)v40,
        (int)v46);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x679,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)v41,
        v48);
    }
    else
    {
      *a5 = 0;
    }
  }
  if ( !StateRepository::StatementCache::Get(
          (struct StateRepository::Database *)((char *)v6 + 40),
          (const char *)v16,
          (struct StateRepository::Statement *)a5) )
  {
    v22 = StateRepository::Statement::FinalizeAndAddressOf((StateRepository::Statement *)a5);
    v8 = StateRepository::Database::dal_prepare_v2(*(struct sqlite3 **)v6, (const char *)v16, v23, v22, v46);
    if ( v8 < 0 )
      goto LABEL_33;
  }
  if ( !*a5 )
  {
    v8 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      (int)v46);
LABEL_38:
    v24 = (unsigned int)v8;
    v25 = 45;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-tileview-custom.cpp",
      (const char *)v24,
      (int)v46);
LABEL_40:
    StateRepository::TextA::Reset((StateRepository::TextA *)&Src);
    return (unsigned int)v8;
  }
  v26 = sqlite3_bind_int64(*a5, 1, v5);
  v8 = v26;
  if ( v26 > 0 )
    v8 = (unsigned __int16)v26 | 0x87AF0000;
  if ( v8 < 0 )
    goto LABEL_38;
  if ( !*a5 )
  {
    v8 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      (int)v46);
LABEL_46:
    v21 = 46;
    goto LABEL_34;
  }
  v27 = sqlite3_bind_int64(*a5, 2, a3);
  v8 = v27;
  if ( v27 > 0 )
    v8 = (unsigned __int16)v27 | 0x87AF0000;
  if ( v8 < 0 )
    goto LABEL_46;
  if ( !*a5 )
  {
    v8 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      (int)v46);
LABEL_66:
    v21 = 47;
    goto LABEL_34;
  }
  v28 = sqlite3_bind_int64(*a5, 3, a3);
  v8 = v28;
  if ( v28 > 0 )
    v8 = (unsigned __int16)v28 | 0x87AF0000;
  if ( v8 < 0 )
    goto LABEL_66;
  v29 = 4;
  if ( *(_DWORD *)a4 )
  {
    v8 = StateRepository::Statement::Bind((StateRepository::Statement *)a5, 4, *(_DWORD *)a4);
    if ( v8 < 0 )
    {
      v21 = 50;
      goto LABEL_34;
    }
    v29 = 5;
  }
  v30 = *((_DWORD *)a4 + 1);
  if ( v30 )
  {
    v33 = StateRepository::Statement::Bind((StateRepository::Statement *)a5, v29, v30);
    if ( v33 < 0 )
    {
      v42 = 54;
      goto LABEL_76;
    }
    ++v29;
  }
  v31 = *((_DWORD *)a4 + 2);
  if ( v31 )
  {
    v44 = StateRepository::Statement::Bind((StateRepository::Statement *)a5, v29, v31);
    v45 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-tileview-custom.cpp",
        (const char *)(unsigned int)v44,
        (int)v46);
      v8 = v45;
      goto LABEL_40;
    }
    ++v29;
  }
  v32 = (const unsigned __int16 *)*((_QWORD *)a4 + 2);
  if ( !v32 )
    goto LABEL_60;
  v33 = StateRepository::Statement::Bind((StateRepository::Statement *)a5, v29, v32);
  if ( v33 < 0 )
  {
    v42 = 62;
LABEL_76:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-tileview-custom.cpp",
      (const char *)(unsigned int)v33,
      (int)v46);
    if ( v16 )
      operator delete(v16, v43);
    return (unsigned int)v33;
  }
  ++v29;
LABEL_60:
  v34 = (const unsigned __int16 *)*((_QWORD *)a4 + 4);
  if ( v34 )
  {
    v37 = StateRepository::Statement::Bind((StateRepository::Statement *)a5, v29, v34);
    v38 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-tileview-custom.cpp",
        (const char *)(unsigned int)v37,
        (int)v46);
      if ( v16 )
        operator delete(v16, v39);
      return v38;
    }
    ++v29;
  }
  v35 = StateRepository::Statement::BindIfWorkInProgress((StateRepository::Statement *)a5, v29, *((_QWORD *)v6 + 1));
  v8 = v35;
  if ( v35 < 0 )
  {
    v25 = 68;
    goto LABEL_100;
  }
  if ( v16 )
    operator delete(v16, v36);
  return 0;
}

```

## disassembly

```asm
0x180011bfc  mov     rax, rsp
0x180011bff  mov     [rax+20h], rbx
0x180011c03  mov     [rax+18h], r8
0x180011c07  mov     [rax+10h], rdx
0x180011c0b  mov     [rax+8], rcx
0x180011c0f  push    rbp
0x180011c10  push    rsi
0x180011c11  push    rdi
0x180011c12  push    r12
0x180011c14  push    r13
0x180011c16  push    r14
0x180011c18  push    r15
0x180011c1a  mov     rbp, rsp
0x180011c1d  sub     rsp, 40h
0x180011c21  mov     r15, rdx
0x180011c24  mov     r13, rcx
0x180011c27  xor     edi, edi
0x180011c29  lea     rdx, aSelectTvTilevi; "SELECT tv._TileViewID, tv._Revision, tv"...
0x180011c30  lea     rcx, [rbp+Src]; this
0x180011c34  mov     [rbp+Src], rdi
0x180011c38  mov     r8d, 18Dh; unsigned __int64
0x180011c3e  mov     [rbp+Size], rdi
0x180011c42  mov     r14, r9
0x180011c45  call    ?SetFromChars@TextA@StateRepository@@QEAAJPEBD_K@Z; StateRepository::TextA::SetFromChars(char const *,unsigned __int64)
0x180011c4a  mov     ebx, eax
0x180011c4c  test    eax, eax
0x180011c4e  jns     short loc_180011C8E
0x180011c50  lea     edx, [rdi+11h]; void *
0x180011c53  mov     rcx, [rbp+38h]; this
0x180011c57  lea     r8, aOnecoreBaseApp_456; "onecore\\base\\appmodel\\staterepositor"...
0x180011c5e  mov     r9d, ebx; char *
0x180011c61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c66  mov     rcx, [rbp+Src]; void *
0x180011c6a  test    rcx, rcx
0x180011c6d  jz      short loc_180011C74
0x180011c6f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011c74  mov     eax, ebx
0x180011c76  mov     rbx, [rsp+40h+arg_18]
0x180011c7e  add     rsp, 40h
0x180011c82  pop     r15
0x180011c84  pop     r14
0x180011c86  pop     r13
0x180011c88  pop     r12
0x180011c8a  pop     rdi
0x180011c8b  pop     rsi
0x180011c8c  pop     rbp
0x180011c8d  retn
0x180011c8e  mov     esi, 1Dh
0x180011c93  cmp     [r14], edi
0x180011c96  jz      short loc_180011CB5
0x180011c98  mov     r8d, esi; unsigned __int64
0x180011c9b  lea     rdx, aAndTvTiletype0; " AND ((tv.TileType & ?) <> 0)"
0x180011ca2  lea     rcx, [rbp+Src]; this
0x180011ca6  call    ?Append@TextA@StateRepository@@QEAAJPEBD_K@Z; StateRepository::TextA::Append(char const *,unsigned __int64)
0x180011cab  mov     ebx, eax
0x180011cad  test    eax, eax
0x180011caf  js      loc_180011DB8
0x180011cb5  cmp     [r14+4], edi
0x180011cb9  jnz     loc_180012111
0x180011cbf  cmp     [r14+8], edi
0x180011cc3  jnz     loc_180012197
0x180011cc9  cmp     [r14+10h], rdi
0x180011ccd  jz      short loc_180011CEF
0x180011ccf  mov     r8d, 20h ; ' '; unsigned __int64
0x180011cd5  lea     rdx, aAndTvApplicati; " AND tv.ApplicationUserModelId=?"
0x180011cdc  lea     rcx, [rbp+Src]; this
0x180011ce0  call    ?Append@TextA@StateRepository@@QEAAJPEBD_K@Z; StateRepository::TextA::Append(char const *,unsigned __int64)
0x180011ce5  mov     ebx, eax
0x180011ce7  test    eax, eax
0x180011ce9  js      loc_180011DC2
0x180011cef  cmp     [r14+20h], rdi
0x180011cf3  jnz     loc_1800121B5
0x180011cf9  cmp     [r13+8], rdi
0x180011cfd  lea     rax, aAndTvWorkid0; " AND tv._WorkId=0;"
0x180011d04  lea     r12, aAndTvWorkid0Or; " AND (tv._WorkId=0 OR tv._WorkId=?);"
0x180011d0b  cmovz   r12, rax
0x180011d0f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011d13  mov     rbx, rsi
0x180011d16  inc     rbx
0x180011d19  cmp     [r12+rbx], dil
0x180011d1d  jnz     short loc_180011D16
0x180011d1f  test    rbx, rbx
0x180011d22  jz      loc_1800120D6
0x180011d28  mov     rdi, [rbp+Src]
0x180011d2c  test    rdi, rdi
0x180011d2f  jz      loc_1800120BD
0x180011d35  inc     rsi
0x180011d38  cmp     byte ptr [rdi+rsi], 0
0x180011d3c  jnz     short loc_180011D35
0x180011d3e  lea     r15, [rbx+1]
0x180011d42  add     r15, rsi
0x180011d45  cmp     r15, [rbp+Size]
0x180011d49  jbe     short loc_180011D84
0x180011d4b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011d52  mov     rcx, r15; unsigned __int64
0x180011d55  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180011d5a  mov     r13, rax
0x180011d5d  test    rax, rax
0x180011d60  jz      short loc_180011DCC
0x180011d62  mov     r8, [rbp+Size]; Size
0x180011d66  mov     rdx, rdi; Src
0x180011d69  mov     rcx, rax; void *
0x180011d6c  call    memcpy_0
0x180011d71  mov     rcx, rdi; void *
0x180011d74  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011d79  mov     rdi, r13
0x180011d7c  mov     [rbp+Src], r13
0x180011d80  mov     r13, [rbp+arg_0]
0x180011d84  lea     rdx, [rbx+1]; unsigned __int64
0x180011d88  mov     r9, rbx; unsigned __int64
0x180011d8b  lea     rcx, [rsi+rdi]; char *
0x180011d8f  mov     r8, r12; char *
0x180011d92  call    ?StringCchCatNA@@YAJPEAD_KPEBD1@Z; StringCchCatNA(char *,unsigned __int64,char const *,unsigned __int64)
0x180011d97  test    eax, eax
0x180011d99  jns     loc_180012150
0x180011d9f  mov     rcx, [rbp+38h]; this
0x180011da3  lea     r8, aOnecoreBaseApp_382; "onecore\\base\\appmodel\\staterepositor"...
0x180011daa  mov     r9d, eax; char *
0x180011dad  mov     edx, 0B3h; void *
0x180011db2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180011db8  mov     edx, 15h
0x180011dbd  jmp     loc_180011C53
0x180011dc2  mov     edx, 21h ; '!'
0x180011dc7  jmp     loc_180011C53
0x180011dcc  mov     rcx, [rbp+38h]; this
0x180011dd0  lea     r8, aOnecoreBaseApp_382; "onecore\\base\\appmodel\\staterepositor"...
0x180011dd7  mov     ebx, 8007000Eh
0x180011ddc  mov     edx, 13Bh; void *
0x180011de1  mov     r9d, ebx; char *
0x180011de4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011de9  mov     rcx, [rbp+38h]; this
0x180011ded  lea     r8, aOnecoreBaseApp_382; "onecore\\base\\appmodel\\staterepositor"...
0x180011df4  mov     r9d, ebx; char *
0x180011df7  mov     edx, 0B2h; void *
0x180011dfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e01  jmp     short loc_180011E07
0x180011e03  mov     rdi, [rbp+Src]
0x180011e07  mov     edx, 29h ; ')'
0x180011e0c  jmp     short loc_180011E54
0x180011e0e  mov     rsi, [rbp+arg_20]
0x180011e12  mov     rcx, [rsi]; struct sqlite3_stmt *
0x180011e15  test    rcx, rcx
0x180011e18  jnz     loc_180012075
0x180011e1e  lea     rcx, [r13+28h]; this
0x180011e22  mov     r8, rsi; struct StateRepository::Statement *
0x180011e25  mov     rdx, rdi; char *
0x180011e28  call    ?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z; StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)
0x180011e2d  test    rax, rax
0x180011e30  jnz     short loc_180011E78
0x180011e32  mov     rcx, rsi; this
0x180011e35  call    ?FinalizeAndAddressOf@Statement@StateRepository@@QEAAPEAPEAUsqlite3_stmt@@XZ; StateRepository::Statement::FinalizeAndAddressOf(void)
0x180011e3a  mov     rcx, [r13+0]; struct sqlite3 *
0x180011e3e  mov     r9, rax; struct sqlite3_stmt **
0x180011e41  mov     rdx, rdi; char *
0x180011e44  call    ?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z; StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)
0x180011e49  mov     ebx, eax
0x180011e4b  test    eax, eax
0x180011e4d  jns     short loc_180011E78
0x180011e4f  mov     edx, 2Bh ; '+'; void *
0x180011e54  mov     rcx, [rbp+38h]; this
0x180011e58  lea     r8, aOnecoreBaseApp_456; "onecore\\base\\appmodel\\staterepositor"...
0x180011e5f  mov     r9d, ebx; char *
0x180011e62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e67  test    rdi, rdi
0x180011e6a  jz      loc_180011C74
0x180011e70  mov     rcx, rdi
0x180011e73  jmp     loc_180011C6F
0x180011e78  mov     rcx, [rsi]
0x180011e7b  test    rcx, rcx
0x180011e7e  jnz     short loc_180011EC3
0x180011e80  mov     rcx, [rbp+38h]; this
0x180011e84  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180011e8b  mov     ebx, 8007139Fh
0x180011e90  mov     edx, 0C9h; void *
0x180011e95  mov     r9d, ebx; char *
0x180011e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e9d  mov     r9d, ebx; char *
0x180011ea0  mov     edx, 2Dh ; '-'; void *
0x180011ea5  mov     rcx, [rbp+38h]; this
0x180011ea9  lea     r8, aOnecoreBaseApp_456; "onecore\\base\\appmodel\\staterepositor"...
0x180011eb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011eb5  lea     rcx, [rbp+Src]; this
0x180011eb9  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180011ebe  jmp     loc_180011C74
0x180011ec3  mov     r12d, 1
0x180011ec9  mov     r8, r15
0x180011ecc  mov     edx, r12d
0x180011ecf  call    cs:__imp_sqlite3_bind_int64
0x180011ed5  mov     ebx, eax
0x180011ed7  test    eax, eax
0x180011ed9  jle     short loc_180011EE4
0x180011edb  movzx   ebx, ax
0x180011ede  or      ebx, 87AF0000h
0x180011ee4  test    ebx, ebx
0x180011ee6  js      short loc_180011E9D
0x180011ee8  mov     rcx, [rsi]
0x180011eeb  test    rcx, rcx
0x180011eee  jnz     short loc_180011F17
0x180011ef0  mov     rcx, [rbp+38h]; this
0x180011ef4  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180011efb  mov     ebx, 8007139Fh
0x180011f00  mov     edx, 0C9h; void *
0x180011f05  mov     r9d, ebx; char *
0x180011f08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011f0d  mov     edx, 2Eh ; '.'
0x180011f12  jmp     loc_180011E54
0x180011f17  mov     r15, [rbp+arg_10]
0x180011f1b  mov     edx, 2
0x180011f20  mov     r8, r15
0x180011f23  call    cs:__imp_sqlite3_bind_int64
0x180011f29  mov     ebx, eax
0x180011f2b  test    eax, eax
0x180011f2d  jle     short loc_180011F38
0x180011f2f  movzx   ebx, ax
0x180011f32  or      ebx, 87AF0000h
0x180011f38  test    ebx, ebx
0x180011f3a  js      short loc_180011F0D
0x180011f3c  mov     rcx, [rsi]
0x180011f3f  test    rcx, rcx
0x180011f42  jz      loc_180011FEE
0x180011f48  mov     r8, r15
0x180011f4b  mov     edx, 3
0x180011f50  call    cs:__imp_sqlite3_bind_int64
0x180011f56  mov     ebx, eax
0x180011f58  test    eax, eax
0x180011f5a  jle     short loc_180011F65
0x180011f5c  movzx   ebx, ax
0x180011f5f  or      ebx, 87AF0000h
0x180011f65  test    ebx, ebx
0x180011f67  js      loc_18001200B
0x180011f6d  mov     r8d, [r14]; int
0x180011f70  mov     ebx, 4
0x180011f75  test    r8d, r8d
0x180011f78  jnz     loc_180012057
0x180011f7e  mov     r8d, [r14+4]; int
0x180011f82  test    r8d, r8d
0x180011f85  jnz     loc_180012135
0x180011f8b  mov     r8d, [r14+8]; int
0x180011f8f  test    r8d, r8d
0x180011f92  jnz     loc_1800121D6
0x180011f98  mov     r8, [r14+10h]; unsigned __int16 *
0x180011f9c  test    r8, r8
0x180011f9f  jz      short loc_180011FB9
0x180011fa1  mov     edx, ebx; int
0x180011fa3  mov     rcx, rsi; this
0x180011fa6  call    ?Bind@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::Bind(int,ushort const *)
0x180011fab  mov     r15d, eax
0x180011fae  test    eax, eax
0x180011fb0  js      loc_180012090
0x180011fb6  add     ebx, r12d
0x180011fb9  mov     r8, [r14+20h]; unsigned __int16 *
0x180011fbd  test    r8, r8
0x180011fc0  jnz     short loc_180012015
0x180011fc2  mov     r8, [r13+8]; __int64
0x180011fc6  mov     edx, ebx; int
0x180011fc8  mov     rcx, rsi; this
0x180011fcb  call    ?BindIfWorkInProgress@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::BindIfWorkInProgress(int,__int64)
0x180011fd0  mov     ebx, eax
0x180011fd2  test    eax, eax
0x180011fd4  js      loc_180012217
0x180011fda  test    rdi, rdi
0x180011fdd  jz      short loc_180011FE7
0x180011fdf  mov     rcx, rdi; void *
0x180011fe2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011fe7  xor     eax, eax
0x180011fe9  jmp     loc_180011C76
0x180011fee  mov     rcx, [rbp+38h]; this
0x180011ff2  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180011ff9  mov     ebx, 8007139Fh
0x180011ffe  mov     edx, 0C9h; void *
0x180012003  mov     r9d, ebx; char *
0x180012006  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001200b  mov     edx, 2Fh ; '/'
0x180012010  jmp     loc_180011E54
0x180012015  mov     edx, ebx; int
0x180012017  mov     rcx, rsi; this
0x18001201a  call    ?Bind@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::Bind(int,ushort const *)
0x18001201f  mov     r14d, eax
0x180012022  test    eax, eax
0x180012024  jns     loc_18001220F
0x18001202a  mov     rcx, [rbp+38h]; this
0x18001202e  lea     r8, aOnecoreBaseApp_456; "onecore\\base\\appmodel\\staterepositor"...
0x180012035  mov     r9d, eax; char *
0x180012038  mov     edx, 42h ; 'B'; void *
0x18001203d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012042  test    rdi, rdi
0x180012045  jz      short loc_18001204F
0x180012047  mov     rcx, rdi; void *
0x18001204a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001204f  mov     eax, r14d
0x180012052  jmp     loc_180011C76
0x180012057  mov     edx, ebx; int
0x180012059  mov     rcx, rsi; this
0x18001205c  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x180012061  mov     ebx, eax
0x180012063  test    eax, eax
0x180012065  js      loc_180012107
0x18001206b  mov     ebx, 5
0x180012070  jmp     loc_180011F7E
0x180012075  call    ?dal_finalize@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_finalize(sqlite3_stmt *)
  ... truncated ...
```
