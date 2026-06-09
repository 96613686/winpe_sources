# StateRepository::Entity::AppUriHandler::TryGet(StateRepository::Database &,__int64,StateRepository::Entity::AppUriHandler &,bool &)

- ea: `0x180020594`
- end: `0x18002065d`
- name: `?TryGet@AppUriHandler@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct StateRepository::Database *this, __int64, struct StateRepository::Entity::AppUriHandler *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e85c`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x18001b5a8`
- `0x1800203cc`
- `0x180020594`
- `0x18002a160`

## string_xrefs

- `0x180020609`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`
- `0x180020630`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`
- `0x1800205c1`: `SELECT _Revision, _WorkId, HostName, Path, Extension, ProgID, AppUriHandlerGroup, _Dictionary FROM AppUriHandler WHERE _AppUriHandlerID=? AND _WorkId=0;`
- `0x1800205cb`: `SELECT _Revision, _WorkId, HostName, Path, Extension, ProgID, AppUriHandlerGroup, _Dictionary FROM AppUriHandler WHERE _AppUriHandlerID=? AND (_WorkId=0 OR _WorkId=?) ORDER BY _WorkId DESC;`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::AppUriHandler::TryGet(
        struct StateRepository::Database *this,
        const char *a2,
        struct StateRepository::Entity::AppUriHandler *a3,
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
         (struct StateRepository::Database *)"SELECT _Revision, _WorkId, HostName, Path, Extension, ProgID, AppUriHandler"
                                             "Group, _Dictionary FROM AppUriHandler WHERE _AppUriHandlerID=? AND _WorkId=0;",
         "SELECT _Revision, _WorkId, HostName, Path, Extension, ProgID, AppUriHandlerGroup, _Dictionary FROM AppUriHandle"
         "r WHERE _AppUriHandlerID=? AND (_WorkId=0 OR _WorkId=?) ORDER BY _WorkId DESC;",
         a2,
         (__int64)v14,
         a4,
         0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 425;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
      (const char *)(unsigned int)v8,
      v13);
    goto LABEL_10;
  }
  if ( *(_BYTE *)a4 )
  {
    v8 = StateRepository::Entity::AppUriHandler::RowToObject(
           (const struct StateRepository::Statement *)v14,
           a3,
           (__int64)a2);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 429;
      goto LABEL_6;
    }
  }
  v11 = StateRepository::Database::AddToCache(this, (struct StateRepository::Statement *)v14);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
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
0x180020594  mov     r11, rsp
0x180020597  push    rbx
0x180020598  push    rbp
0x180020599  push    rsi
0x18002059a  push    rdi
0x18002059b  push    r14
0x18002059d  sub     rsp, 40h
0x1800205a1  mov     [r11-40h], r9
0x1800205a5  lea     rax, [r11-38h]
0x1800205a9  mov     rdi, r9
0x1800205ac  mov     qword ptr [r11-38h], 0
0x1800205b4  mov     r9, rdx; char *
0x1800205b7  mov     [r11-48h], rax
0x1800205bb  mov     r14, r8
0x1800205be  mov     rbp, rdx
0x1800205c1  lea     rdx, aSelectRevision_1; "SELECT _Revision, _WorkId, HostName, Pa"...
0x1800205c8  mov     rsi, rcx
0x1800205cb  lea     r8, aSelectRevision; "SELECT _Revision, _WorkId, HostName, Pa"...
0x1800205d2  call    ?PrepareAndBindAndTryGet@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEAVStatement@2@AEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndTryGet(StateRepository::Database &,char const *,char const *,__int64,StateRepository::Statement &,bool &)
0x1800205d7  mov     ebx, eax
0x1800205d9  test    eax, eax
0x1800205db  jns     short loc_1800205E4
0x1800205dd  mov     edx, 1A9h
0x1800205e2  jmp     short loc_180020604
0x1800205e4  cmp     byte ptr [rdi], 0
0x1800205e7  jz      short loc_18002061A
0x1800205e9  mov     r8, rbp; __int64
0x1800205ec  lea     rcx, [rsp+68h+var_38]; this
0x1800205f1  mov     rdx, r14; struct StateRepository::Entity::AppUriHandler *
0x1800205f4  call    ?RowToObject@AppUriHandler@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::AppUriHandler::RowToObject(StateRepository::Statement const &,StateRepository::Entity::AppUriHandler &,__int64)
0x1800205f9  mov     ebx, eax
0x1800205fb  test    eax, eax
0x1800205fd  jns     short loc_18002061A
0x1800205ff  mov     edx, 1ADh; void *
0x180020604  mov     rcx, [rsp+68h]; this
0x180020609  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x180020610  mov     r9d, eax; char *
0x180020613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020618  jmp     short loc_180020646
0x18002061a  lea     rdx, [rsp+68h+var_38]; struct StateRepository::Statement *
0x18002061f  mov     rcx, rsi; this
0x180020622  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180020627  test    eax, eax
0x180020629  jns     short loc_180020644
0x18002062b  mov     rcx, [rsp+68h]; this
0x180020630  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x180020637  mov     r9d, eax; char *
0x18002063a  mov     edx, 1B0h; void *
0x18002063f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020644  xor     ebx, ebx
0x180020646  lea     rcx, [rsp+68h+var_38]; this
0x18002064b  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180020650  mov     eax, ebx
0x180020652  add     rsp, 40h
0x180020656  pop     r14
0x180020658  pop     rdi
0x180020659  pop     rsi
0x18002065a  pop     rbp
0x18002065b  pop     rbx
0x18002065c  retn
```
