# StateRepository::Entity::AppUriHandler::RowToObject(StateRepository::Statement const &,StateRepository::Entity::AppUriHandler &,__int64)

- ea: `0x1800203cc`
- end: `0x18002058b`
- name: `?RowToObject@AppUriHandler@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z`
- size: `447`
- prototype: `__int64 __fastcall(const struct StateRepository::Statement *this, struct StateRepository::Entity::AppUriHandler *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020594`

## callees

- `0x18000a3c0`
- `0x18001b9d4`
- `0x18001bd28`
- `0x18001be40`
- `0x18001bf44`
- `0x1800203cc`
- `0x18002db14`

## string_xrefs

- `0x1800203f5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`
- `0x180020431`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`
- `0x180020466`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::AppUriHandler::RowToObject(
        const struct StateRepository::Statement *this,
        struct StateRepository::Entity::AppUriHandler *a2,
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
    v7 = 869;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
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
      v11 = 878;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
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
      (void *)0x370,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
      (const char *)(unsigned int)ColumnUInt64,
      v19);
    return v13;
  }
  v14 = v9 + 1;
  ColumnInt64 = StateRepository::Statement::GetColumnInt64(this, v9 + 1, (__int64 *)a2 + 2);
  if ( ColumnInt64 < 0 )
  {
    v11 = 881;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v14 + 1,
                  (struct StateRepository::Entity::AppUriHandler *)((char *)a2 + 24));
  if ( ColumnInt64 < 0 )
  {
    v11 = 882;
    goto LABEL_8;
  }
  v15 = v14 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v15,
                  (struct StateRepository::Entity::AppUriHandler *)((char *)a2 + 40));
  if ( ColumnInt64 < 0 )
  {
    v11 = 883;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnInt64(this, v15 + 1, (__int64 *)a2 + 7);
  if ( ColumnInt64 < 0 )
  {
    v11 = 884;
    goto LABEL_8;
  }
  v16 = v15 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v16,
                  (struct StateRepository::Entity::AppUriHandler *)((char *)a2 + 64));
  if ( ColumnInt64 < 0 )
  {
    v11 = 885;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnInt64(this, v16 + 1, (__int64 *)a2 + 10);
  if ( ColumnInt64 < 0 )
  {
    v11 = 886;
    goto LABEL_8;
  }
  v17 = v16 + 2;
  ColumnBlob = StateRepository::Statement::GetColumnBlob(
                 this,
                 v16 + 2,
                 (struct StateRepository::Entity::AppUriHandler *)((char *)a2 + 88));
  if ( ColumnBlob < 0 )
  {
    v7 = 887;
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
0x1800203cc  push    rbx
0x1800203ce  push    rbp
0x1800203cf  push    rsi
0x1800203d0  push    rdi
0x1800203d1  push    r14; int
0x1800203d3  sub     rsp, 20h
0x1800203d7  cmp     qword ptr [rcx], 0
0x1800203db  mov     rbp, r8
0x1800203de  mov     rbx, rdx
0x1800203e1  mov     rdi, rcx
0x1800203e4  jnz     short loc_18002040B
0x1800203e6  mov     ebx, 8007139Fh
0x1800203eb  mov     edx, 365h; void *
0x1800203f0  mov     rcx, [rsp+48h]; this
0x1800203f5  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x1800203fc  mov     r9d, ebx; char *
0x1800203ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020404  mov     eax, ebx
0x180020406  jmp     loc_180020580
0x18002040b  test    rbp, rbp
0x18002040e  jz      short loc_180020417
0x180020410  mov     [rdx], rbp
0x180020413  xor     esi, esi
0x180020415  jmp     short loc_18002044C
0x180020417  mov     r8, rbx; __int64 *
0x18002041a  xor     edx, edx; int
0x18002041c  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x180020421  mov     esi, eax
0x180020423  test    eax, eax
0x180020425  jns     short loc_180020447
0x180020427  mov     edx, 36Eh; void *
0x18002042c  mov     rcx, [rsp+48h]; this
0x180020431  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x180020438  mov     r9d, esi; char *
0x18002043b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020440  mov     eax, esi
0x180020442  jmp     loc_180020580
0x180020447  mov     esi, 1
0x18002044c  lea     r8, [rbx+8]; unsigned __int64 *
0x180020450  mov     edx, esi; int
0x180020452  mov     rcx, rdi; this
0x180020455  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x18002045a  mov     r14d, eax
0x18002045d  test    eax, eax
0x18002045f  jns     short loc_180020482
0x180020461  mov     rcx, [rsp+48h]; this
0x180020466  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x18002046d  mov     r9d, eax; char *
0x180020470  mov     edx, 370h; void *
0x180020475  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002047a  mov     eax, r14d
0x18002047d  jmp     loc_180020580
0x180020482  lea     r14d, [rsi+1]
0x180020486  mov     rcx, rdi; this
0x180020489  mov     edx, r14d; int
0x18002048c  lea     r8, [rbx+10h]; __int64 *
0x180020490  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x180020495  mov     esi, eax
0x180020497  test    eax, eax
0x180020499  jns     short loc_1800204A2
0x18002049b  mov     edx, 371h
0x1800204a0  jmp     short loc_18002042C
0x1800204a2  lea     r8, [rbx+18h]; struct StateRepository::Text *
0x1800204a6  mov     rcx, rdi; this
0x1800204a9  lea     edx, [r14+1]; int
0x1800204ad  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x1800204b2  mov     esi, eax
0x1800204b4  test    eax, eax
0x1800204b6  jns     short loc_1800204C2
0x1800204b8  mov     edx, 372h
0x1800204bd  jmp     loc_18002042C
0x1800204c2  add     r14d, 2
0x1800204c6  lea     r8, [rbx+28h]; struct StateRepository::Text *
0x1800204ca  mov     edx, r14d; int
0x1800204cd  mov     rcx, rdi; this
0x1800204d0  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x1800204d5  mov     esi, eax
0x1800204d7  test    eax, eax
0x1800204d9  jns     short loc_1800204E5
0x1800204db  mov     edx, 373h
0x1800204e0  jmp     loc_18002042C
0x1800204e5  lea     r8, [rbx+38h]; __int64 *
0x1800204e9  mov     rcx, rdi; this
0x1800204ec  lea     edx, [r14+1]; int
0x1800204f0  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x1800204f5  mov     esi, eax
0x1800204f7  test    eax, eax
0x1800204f9  jns     short loc_180020505
0x1800204fb  mov     edx, 374h
0x180020500  jmp     loc_18002042C
0x180020505  add     r14d, 2
0x180020509  lea     r8, [rbx+40h]; struct StateRepository::Text *
0x18002050d  mov     edx, r14d; int
0x180020510  mov     rcx, rdi; this
0x180020513  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x180020518  mov     esi, eax
0x18002051a  test    eax, eax
0x18002051c  jns     short loc_180020528
0x18002051e  mov     edx, 375h
0x180020523  jmp     loc_18002042C
0x180020528  lea     r8, [rbx+50h]; __int64 *
0x18002052c  mov     rcx, rdi; this
0x18002052f  lea     edx, [r14+1]; int
0x180020533  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x180020538  mov     esi, eax
0x18002053a  test    eax, eax
0x18002053c  jns     short loc_180020548
0x18002053e  mov     edx, 376h
0x180020543  jmp     loc_18002042C
0x180020548  lea     esi, [r14+2]
0x18002054c  mov     rcx, rdi; this
0x18002054f  mov     edx, esi; int
0x180020551  lea     r8, [rbx+58h]; struct StateRepository::Blob *
0x180020555  call    ?GetColumnBlob@Statement@StateRepository@@QEBAJHAEAVBlob@2@@Z; StateRepository::Statement::GetColumnBlob(int,StateRepository::Blob &)
0x18002055a  mov     ebx, eax
0x18002055c  test    eax, eax
0x18002055e  jns     short loc_18002056A
0x180020560  mov     edx, 377h
0x180020565  jmp     loc_1800203F0
0x18002056a  test    rbp, rbp
0x18002056d  jz      short loc_180020574
0x18002056f  cmp     esi, 7
0x180020572  jmp     short loc_180020577
0x180020574  cmp     esi, 8
0x180020577  jz      short loc_18002057E
0x180020579  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002057e  xor     eax, eax
0x180020580  add     rsp, 20h
0x180020584  pop     r14
0x180020586  pop     rdi
0x180020587  pop     rsi
0x180020588  pop     rbp
0x180020589  pop     rbx
0x18002058a  retn
```
