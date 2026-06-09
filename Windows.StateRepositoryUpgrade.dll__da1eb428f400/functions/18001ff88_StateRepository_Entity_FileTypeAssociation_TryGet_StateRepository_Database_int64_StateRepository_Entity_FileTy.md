# StateRepository::Entity::FileTypeAssociation::TryGet(StateRepository::Database &,__int64,StateRepository::Entity::FileTypeAssociation &,bool &)

- ea: `0x18001ff88`
- end: `0x180020051`
- name: `?TryGet@FileTypeAssociation@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct StateRepository::Database *this, __int64, struct StateRepository::Entity::FileTypeAssociation *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000e99c`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x18001b5a8`
- `0x18001fdc0`
- `0x18001ff88`
- `0x18002a160`

## string_xrefs

- `0x18001fffd`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`
- `0x180020024`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`
- `0x18001ffb5`: `SELECT _Revision, _WorkId, FileType, ContentType, Extension, "Index", ProgID, _Dictionary FROM FileTypeAssociation WHERE _FileTypeAssociationID=? AND _WorkId=0;`
- `0x18001ffbf`: `SELECT _Revision, _WorkId, FileType, ContentType, Extension, "Index", ProgID, _Dictionary FROM FileTypeAssociation WHERE _FileTypeAssociationID=? AND (_WorkId=0 OR _WorkId=?) ORDER BY _WorkId DESC;`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::FileTypeAssociation::TryGet(
        struct StateRepository::Database *this,
        const char *a2,
        struct StateRepository::Entity::FileTypeAssociation *a3,
        struct StateRepository::Statement *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  int v13; // [rsp+20h] [rbp-48h]
  _BYTE v14[56]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = StateRepository::StatementExecution::PrepareAndBindAndTryGet(
         this,
         (struct StateRepository::Database *)"SELECT _Revision, _WorkId, FileType, ContentType, Extension, \"Index\", Pro"
                                             "gID, _Dictionary FROM FileTypeAssociation WHERE _FileTypeAssociationID=? AND _WorkId=0;",
         "SELECT _Revision, _WorkId, FileType, ContentType, Extension, \"Index\", ProgID, _Dictionary FROM FileTypeAssoci"
         "ation WHERE _FileTypeAssociationID=? AND (_WorkId=0 OR _WorkId=?) ORDER BY _WorkId DESC;",
         a2,
         (__int64)v14,
         a4,
         0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 577;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
      (const char *)(unsigned int)v8,
      v13);
    goto LABEL_10;
  }
  if ( *(_BYTE *)a4 )
  {
    v8 = StateRepository::Entity::FileTypeAssociation::RowToObject(
           (const struct StateRepository::Statement *)v14,
           a3,
           (__int64)a2);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 581;
      goto LABEL_6;
    }
  }
  v11 = StateRepository::Database::AddToCache(this, (struct StateRepository::Statement *)v14);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
      (const char *)(unsigned int)v11,
      v13);
  v9 = 0;
LABEL_10:
  StateRepository::Statement::~Statement((StateRepository::Statement *)v14);
  return v9;
}

```

## disassembly

```asm
0x18001ff88  mov     r11, rsp
0x18001ff8b  push    rbx
0x18001ff8c  push    rbp
0x18001ff8d  push    rsi
0x18001ff8e  push    rdi
0x18001ff8f  push    r14
0x18001ff91  sub     rsp, 40h
0x18001ff95  mov     [r11-40h], r9
0x18001ff99  lea     rax, [r11-38h]
0x18001ff9d  mov     rdi, r9
0x18001ffa0  mov     qword ptr [r11-38h], 0
0x18001ffa8  mov     r9, rdx; char *
0x18001ffab  mov     [r11-48h], rax
0x18001ffaf  mov     r14, r8
0x18001ffb2  mov     rbp, rdx
0x18001ffb5  lea     rdx, aSelectRevision_2; "SELECT _Revision, _WorkId, FileType, Co"...
0x18001ffbc  mov     rsi, rcx
0x18001ffbf  lea     r8, aSelectRevision_0; "SELECT _Revision, _WorkId, FileType, Co"...
0x18001ffc6  call    ?PrepareAndBindAndTryGet@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEAVStatement@2@AEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndTryGet(StateRepository::Database &,char const *,char const *,__int64,StateRepository::Statement &,bool &)
0x18001ffcb  mov     ebx, eax
0x18001ffcd  test    eax, eax
0x18001ffcf  jns     short loc_18001FFD8
0x18001ffd1  mov     edx, 241h
0x18001ffd6  jmp     short loc_18001FFF8
0x18001ffd8  cmp     byte ptr [rdi], 0
0x18001ffdb  jz      short loc_18002000E
0x18001ffdd  mov     r8, rbp; __int64
0x18001ffe0  lea     rcx, [rsp+68h+var_38]; this
0x18001ffe5  mov     rdx, r14; struct StateRepository::Entity::FileTypeAssociation *
0x18001ffe8  call    ?RowToObject@FileTypeAssociation@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::FileTypeAssociation::RowToObject(StateRepository::Statement const &,StateRepository::Entity::FileTypeAssociation &,__int64)
0x18001ffed  mov     ebx, eax
0x18001ffef  test    eax, eax
0x18001fff1  jns     short loc_18002000E
0x18001fff3  mov     edx, 245h; void *
0x18001fff8  mov     rcx, [rsp+68h]; this
0x18001fffd  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x180020004  mov     r9d, eax; char *
0x180020007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002000c  jmp     short loc_18002003A
0x18002000e  lea     rdx, [rsp+68h+var_38]; struct StateRepository::Statement *
0x180020013  mov     rcx, rsi; this
0x180020016  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18002001b  test    eax, eax
0x18002001d  jns     short loc_180020038
0x18002001f  mov     rcx, [rsp+68h]; this
0x180020024  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x18002002b  mov     r9d, eax; char *
0x18002002e  mov     edx, 248h; void *
0x180020033  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020038  xor     ebx, ebx
0x18002003a  lea     rcx, [rsp+68h+var_38]; this
0x18002003f  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180020044  mov     eax, ebx
0x180020046  add     rsp, 40h
0x18002004a  pop     r14
0x18002004c  pop     rdi
0x18002004d  pop     rsi
0x18002004e  pop     rbp
0x18002004f  pop     rbx
0x180020050  retn
```
