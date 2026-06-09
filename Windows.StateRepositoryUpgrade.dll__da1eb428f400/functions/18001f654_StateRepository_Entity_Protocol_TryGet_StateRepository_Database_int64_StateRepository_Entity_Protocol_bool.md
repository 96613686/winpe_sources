# StateRepository::Entity::Protocol::TryGet(StateRepository::Database &,__int64,StateRepository::Entity::Protocol &,bool &)

- ea: `0x18001f654`
- end: `0x18001f71d`
- name: `?TryGet@Protocol@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct StateRepository::Database *this, __int64, struct StateRepository::Entity::Protocol *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000eae4`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x18001b5a8`
- `0x18001f48c`
- `0x18001f654`
- `0x18002a160`

## string_xrefs

- `0x18001f6c9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`
- `0x18001f6f0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`
- `0x18001f681`: `SELECT _Revision, _WorkId, ProtocolName, ReturnResults, Extension, "Index", ProgID, _Dictionary FROM Protocol WHERE _ProtocolID=? AND _WorkId=0;`
- `0x18001f68b`: `SELECT _Revision, _WorkId, ProtocolName, ReturnResults, Extension, "Index", ProgID, _Dictionary FROM Protocol WHERE _ProtocolID=? AND (_WorkId=0 OR _WorkId=?) ORDER BY _WorkId DESC;`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Protocol::TryGet(
        struct StateRepository::Database *this,
        const char *a2,
        struct StateRepository::Entity::Protocol *a3,
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
         (struct StateRepository::Database *)"SELECT _Revision, _WorkId, ProtocolName, ReturnResults, Extension, \"Index\""
                                             ", ProgID, _Dictionary FROM Protocol WHERE _ProtocolID=? AND _WorkId=0;",
         "SELECT _Revision, _WorkId, ProtocolName, ReturnResults, Extension, \"Index\", ProgID, _Dictionary FROM Protocol"
         " WHERE _ProtocolID=? AND (_WorkId=0 OR _WorkId=?) ORDER BY _WorkId DESC;",
         a2,
         (__int64)v14,
         a4,
         0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 518;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
      (const char *)(unsigned int)v8,
      v13);
    goto LABEL_10;
  }
  if ( *(_BYTE *)a4 )
  {
    v8 = StateRepository::Entity::Protocol::RowToObject((const struct StateRepository::Statement *)v14, a3, (__int64)a2);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 522;
      goto LABEL_6;
    }
  }
  v11 = StateRepository::Database::AddToCache(this, (struct StateRepository::Statement *)v14);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
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
0x18001f654  mov     r11, rsp
0x18001f657  push    rbx
0x18001f658  push    rbp
0x18001f659  push    rsi
0x18001f65a  push    rdi
0x18001f65b  push    r14
0x18001f65d  sub     rsp, 40h
0x18001f661  mov     [r11-40h], r9
0x18001f665  lea     rax, [r11-38h]
0x18001f669  mov     rdi, r9
0x18001f66c  mov     qword ptr [r11-38h], 0
0x18001f674  mov     r9, rdx; char *
0x18001f677  mov     [r11-48h], rax
0x18001f67b  mov     r14, r8
0x18001f67e  mov     rbp, rdx
0x18001f681  lea     rdx, aSelectRevision_6; "SELECT _Revision, _WorkId, ProtocolName"...
0x18001f688  mov     rsi, rcx
0x18001f68b  lea     r8, aSelectRevision_5; "SELECT _Revision, _WorkId, ProtocolName"...
0x18001f692  call    ?PrepareAndBindAndTryGet@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEAVStatement@2@AEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndTryGet(StateRepository::Database &,char const *,char const *,__int64,StateRepository::Statement &,bool &)
0x18001f697  mov     ebx, eax
0x18001f699  test    eax, eax
0x18001f69b  jns     short loc_18001F6A4
0x18001f69d  mov     edx, 206h
0x18001f6a2  jmp     short loc_18001F6C4
0x18001f6a4  cmp     byte ptr [rdi], 0
0x18001f6a7  jz      short loc_18001F6DA
0x18001f6a9  mov     r8, rbp; __int64
0x18001f6ac  lea     rcx, [rsp+68h+var_38]; this
0x18001f6b1  mov     rdx, r14; struct StateRepository::Entity::Protocol *
0x18001f6b4  call    ?RowToObject@Protocol@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::Protocol::RowToObject(StateRepository::Statement const &,StateRepository::Entity::Protocol &,__int64)
0x18001f6b9  mov     ebx, eax
0x18001f6bb  test    eax, eax
0x18001f6bd  jns     short loc_18001F6DA
0x18001f6bf  mov     edx, 20Ah; void *
0x18001f6c4  mov     rcx, [rsp+68h]; this
0x18001f6c9  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18001f6d0  mov     r9d, eax; char *
0x18001f6d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f6d8  jmp     short loc_18001F706
0x18001f6da  lea     rdx, [rsp+68h+var_38]; struct StateRepository::Statement *
0x18001f6df  mov     rcx, rsi; this
0x18001f6e2  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18001f6e7  test    eax, eax
0x18001f6e9  jns     short loc_18001F704
0x18001f6eb  mov     rcx, [rsp+68h]; this
0x18001f6f0  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18001f6f7  mov     r9d, eax; char *
0x18001f6fa  mov     edx, 20Dh; void *
0x18001f6ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f704  xor     ebx, ebx
0x18001f706  lea     rcx, [rsp+68h+var_38]; this
0x18001f70b  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18001f710  mov     eax, ebx
0x18001f712  add     rsp, 40h
0x18001f716  pop     r14
0x18001f718  pop     rdi
0x18001f719  pop     rsi
0x18001f71a  pop     rbp
0x18001f71b  pop     rbx
0x18001f71c  retn
```
