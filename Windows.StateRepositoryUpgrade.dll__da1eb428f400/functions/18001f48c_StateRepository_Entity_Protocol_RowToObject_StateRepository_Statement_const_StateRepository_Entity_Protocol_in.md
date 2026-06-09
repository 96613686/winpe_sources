# StateRepository::Entity::Protocol::RowToObject(StateRepository::Statement const &,StateRepository::Entity::Protocol &,__int64)

- ea: `0x18001f48c`
- end: `0x18001f64b`
- name: `?RowToObject@Protocol@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z`
- size: `447`
- prototype: `__int64 __fastcall(const struct StateRepository::Statement *this, struct StateRepository::Entity::Protocol *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001f654`

## callees

- `0x18000a3c0`
- `0x18001b9d4`
- `0x18001bca0`
- `0x18001bd28`
- `0x18001be40`
- `0x18001bf44`
- `0x18001f48c`
- `0x18002db14`

## string_xrefs

- `0x18001f4b5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`
- `0x18001f4f1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`
- `0x18001f526`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Protocol::RowToObject(
        const struct StateRepository::Statement *this,
        struct StateRepository::Entity::Protocol *a2,
        __int64 a3)
{
  int ColumnBlob; // ebx
  __int64 v7; // rdx
  int v9; // esi
  int ColumnInt64; // esi
  __int64 v11; // rdx
  int ColumnUInt64; // eax
  unsigned int v13; // r14d
  int v14; // r14d
  int v15; // r14d
  int v16; // r14d
  int v17; // esi
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !*(_QWORD *)this )
  {
    ColumnBlob = -2147019873;
    v7 = 996;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
      (const char *)(unsigned int)ColumnBlob,
      v19);
    return (unsigned int)ColumnBlob;
  }
  if ( a3 )
  {
    *(_QWORD *)a2 = a3;
    v9 = 0;
  }
  else
  {
    ColumnInt64 = StateRepository::Statement::GetColumnInt64(this, 0, (__int64 *)a2);
    if ( ColumnInt64 < 0 )
    {
      v11 = 1005;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
        (const char *)(unsigned int)ColumnInt64,
        v19);
      return (unsigned int)ColumnInt64;
    }
    v9 = 1;
  }
  ColumnUInt64 = StateRepository::Statement::GetColumnUInt64(this, v9, (unsigned __int64 *)a2 + 1);
  v13 = ColumnUInt64;
  if ( ColumnUInt64 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3EF,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
      (const char *)(unsigned int)ColumnUInt64,
      v19);
    return v13;
  }
  v14 = v9 + 1;
  ColumnInt64 = StateRepository::Statement::GetColumnInt64(this, v9 + 1, (__int64 *)a2 + 2);
  if ( ColumnInt64 < 0 )
  {
    v11 = 1008;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v14 + 1,
                  (struct StateRepository::Entity::Protocol *)((char *)a2 + 24));
  if ( ColumnInt64 < 0 )
  {
    v11 = 1009;
    goto LABEL_8;
  }
  v15 = v14 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnInt32(this, v15, (int *)a2 + 10);
  if ( ColumnInt64 < 0 )
  {
    v11 = 1011;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnInt64(this, v15 + 1, (__int64 *)a2 + 6);
  if ( ColumnInt64 < 0 )
  {
    v11 = 1012;
    goto LABEL_8;
  }
  v16 = v15 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnInt32(this, v16, (int *)a2 + 14);
  if ( ColumnInt64 < 0 )
  {
    v11 = 1013;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v16 + 1,
                  (struct StateRepository::Entity::Protocol *)((char *)a2 + 64));
  if ( ColumnInt64 < 0 )
  {
    v11 = 1014;
    goto LABEL_8;
  }
  v17 = v16 + 2;
  ColumnBlob = StateRepository::Statement::GetColumnBlob(
                 this,
                 v16 + 2,
                 (struct StateRepository::Entity::Protocol *)((char *)a2 + 80));
  if ( ColumnBlob < 0 )
  {
    v7 = 1015;
    goto LABEL_3;
  }
  if ( a3 )
    v18 = v17 == 7;
  else
    v18 = v17 == 8;
  if ( !v18 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return 0;
}

```

## disassembly

```asm
0x18001f48c  push    rbx
0x18001f48e  push    rbp
0x18001f48f  push    rsi
0x18001f490  push    rdi
0x18001f491  push    r14; int
0x18001f493  sub     rsp, 20h
0x18001f497  cmp     qword ptr [rcx], 0
0x18001f49b  mov     rbp, r8
0x18001f49e  mov     rbx, rdx
0x18001f4a1  mov     rdi, rcx
0x18001f4a4  jnz     short loc_18001F4CB
0x18001f4a6  mov     ebx, 8007139Fh
0x18001f4ab  mov     edx, 3E4h; void *
0x18001f4b0  mov     rcx, [rsp+48h]; this
0x18001f4b5  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18001f4bc  mov     r9d, ebx; char *
0x18001f4bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f4c4  mov     eax, ebx
0x18001f4c6  jmp     loc_18001F640
0x18001f4cb  test    rbp, rbp
0x18001f4ce  jz      short loc_18001F4D7
0x18001f4d0  mov     [rdx], rbp
0x18001f4d3  xor     esi, esi
0x18001f4d5  jmp     short loc_18001F50C
0x18001f4d7  mov     r8, rbx; __int64 *
0x18001f4da  xor     edx, edx; int
0x18001f4dc  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x18001f4e1  mov     esi, eax
0x18001f4e3  test    eax, eax
0x18001f4e5  jns     short loc_18001F507
0x18001f4e7  mov     edx, 3EDh; void *
0x18001f4ec  mov     rcx, [rsp+48h]; this
0x18001f4f1  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18001f4f8  mov     r9d, esi; char *
0x18001f4fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f500  mov     eax, esi
0x18001f502  jmp     loc_18001F640
0x18001f507  mov     esi, 1
0x18001f50c  lea     r8, [rbx+8]; unsigned __int64 *
0x18001f510  mov     edx, esi; int
0x18001f512  mov     rcx, rdi; this
0x18001f515  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x18001f51a  mov     r14d, eax
0x18001f51d  test    eax, eax
0x18001f51f  jns     short loc_18001F542
0x18001f521  mov     rcx, [rsp+48h]; this
0x18001f526  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18001f52d  mov     r9d, eax; char *
0x18001f530  mov     edx, 3EFh; void *
0x18001f535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f53a  mov     eax, r14d
0x18001f53d  jmp     loc_18001F640
0x18001f542  lea     r14d, [rsi+1]
0x18001f546  mov     rcx, rdi; this
0x18001f549  mov     edx, r14d; int
0x18001f54c  lea     r8, [rbx+10h]; __int64 *
0x18001f550  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x18001f555  mov     esi, eax
0x18001f557  test    eax, eax
0x18001f559  jns     short loc_18001F562
0x18001f55b  mov     edx, 3F0h
0x18001f560  jmp     short loc_18001F4EC
0x18001f562  lea     r8, [rbx+18h]; struct StateRepository::Text *
0x18001f566  mov     rcx, rdi; this
0x18001f569  lea     edx, [r14+1]; int
0x18001f56d  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x18001f572  mov     esi, eax
0x18001f574  test    eax, eax
0x18001f576  jns     short loc_18001F582
0x18001f578  mov     edx, 3F1h
0x18001f57d  jmp     loc_18001F4EC
0x18001f582  add     r14d, 2
0x18001f586  lea     r8, [rbx+28h]; int *
0x18001f58a  mov     edx, r14d; int
0x18001f58d  mov     rcx, rdi; this
0x18001f590  call    ?GetColumnInt32@Statement@StateRepository@@QEBAJHPEAH@Z; StateRepository::Statement::GetColumnInt32(int,int *)
0x18001f595  mov     esi, eax
0x18001f597  test    eax, eax
0x18001f599  jns     short loc_18001F5A5
0x18001f59b  mov     edx, 3F3h
0x18001f5a0  jmp     loc_18001F4EC
0x18001f5a5  lea     r8, [rbx+30h]; __int64 *
0x18001f5a9  mov     rcx, rdi; this
0x18001f5ac  lea     edx, [r14+1]; int
0x18001f5b0  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x18001f5b5  mov     esi, eax
0x18001f5b7  test    eax, eax
0x18001f5b9  jns     short loc_18001F5C5
0x18001f5bb  mov     edx, 3F4h
0x18001f5c0  jmp     loc_18001F4EC
0x18001f5c5  add     r14d, 2
0x18001f5c9  lea     r8, [rbx+38h]; int *
0x18001f5cd  mov     edx, r14d; int
0x18001f5d0  mov     rcx, rdi; this
0x18001f5d3  call    ?GetColumnInt32@Statement@StateRepository@@QEBAJHPEAH@Z; StateRepository::Statement::GetColumnInt32(int,int *)
0x18001f5d8  mov     esi, eax
0x18001f5da  test    eax, eax
0x18001f5dc  jns     short loc_18001F5E8
0x18001f5de  mov     edx, 3F5h
0x18001f5e3  jmp     loc_18001F4EC
0x18001f5e8  lea     r8, [rbx+40h]; struct StateRepository::Text *
0x18001f5ec  mov     rcx, rdi; this
0x18001f5ef  lea     edx, [r14+1]; int
0x18001f5f3  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x18001f5f8  mov     esi, eax
0x18001f5fa  test    eax, eax
0x18001f5fc  jns     short loc_18001F608
0x18001f5fe  mov     edx, 3F6h
0x18001f603  jmp     loc_18001F4EC
0x18001f608  lea     esi, [r14+2]
0x18001f60c  mov     rcx, rdi; this
0x18001f60f  mov     edx, esi; int
0x18001f611  lea     r8, [rbx+50h]; struct StateRepository::Blob *
0x18001f615  call    ?GetColumnBlob@Statement@StateRepository@@QEBAJHAEAVBlob@2@@Z; StateRepository::Statement::GetColumnBlob(int,StateRepository::Blob &)
0x18001f61a  mov     ebx, eax
0x18001f61c  test    eax, eax
0x18001f61e  jns     short loc_18001F62A
0x18001f620  mov     edx, 3F7h
0x18001f625  jmp     loc_18001F4B0
0x18001f62a  test    rbp, rbp
0x18001f62d  jz      short loc_18001F634
0x18001f62f  cmp     esi, 7
0x18001f632  jmp     short loc_18001F637
0x18001f634  cmp     esi, 8
0x18001f637  jz      short loc_18001F63E
0x18001f639  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f63e  xor     eax, eax
0x18001f640  add     rsp, 20h
0x18001f644  pop     r14
0x18001f646  pop     rdi
0x18001f647  pop     rsi
0x18001f648  pop     rbp
0x18001f649  pop     rbx
0x18001f64a  retn
```
