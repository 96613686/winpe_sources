# StateRepository::Entity::FileTypeAssociation::RowToObject(StateRepository::Statement const &,StateRepository::Entity::FileTypeAssociation &,__int64)

- ea: `0x18001fdc0`
- end: `0x18001ff7f`
- name: `?RowToObject@FileTypeAssociation@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z`
- size: `447`
- prototype: `__int64 __fastcall(const struct StateRepository::Statement *this, struct StateRepository::Entity::FileTypeAssociation *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001ff88`

## callees

- `0x18000a3c0`
- `0x18001b9d4`
- `0x18001bca0`
- `0x18001bd28`
- `0x18001be40`
- `0x18001bf44`
- `0x18001fdc0`
- `0x18002db14`

## string_xrefs

- `0x18001fde9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`
- `0x18001fe25`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`
- `0x18001fe5a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::FileTypeAssociation::RowToObject(
        const struct StateRepository::Statement *this,
        struct StateRepository::Entity::FileTypeAssociation *a2,
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
    v7 = 1078;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
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
      v11 = 1087;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
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
      (void *)0x441,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
      (const char *)(unsigned int)ColumnUInt64,
      v19);
    return v13;
  }
  v14 = v9 + 1;
  ColumnInt64 = StateRepository::Statement::GetColumnInt64(this, v9 + 1, (__int64 *)a2 + 2);
  if ( ColumnInt64 < 0 )
  {
    v11 = 1090;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v14 + 1,
                  (struct StateRepository::Entity::FileTypeAssociation *)((char *)a2 + 24));
  if ( ColumnInt64 < 0 )
  {
    v11 = 1091;
    goto LABEL_8;
  }
  v15 = v14 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v15,
                  (struct StateRepository::Entity::FileTypeAssociation *)((char *)a2 + 40));
  if ( ColumnInt64 < 0 )
  {
    v11 = 1092;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnInt64(this, v15 + 1, (__int64 *)a2 + 7);
  if ( ColumnInt64 < 0 )
  {
    v11 = 1093;
    goto LABEL_8;
  }
  v16 = v15 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnInt32(this, v16, (int *)a2 + 16);
  if ( ColumnInt64 < 0 )
  {
    v11 = 1094;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v16 + 1,
                  (struct StateRepository::Entity::FileTypeAssociation *)((char *)a2 + 72));
  if ( ColumnInt64 < 0 )
  {
    v11 = 1095;
    goto LABEL_8;
  }
  v17 = v16 + 2;
  ColumnBlob = StateRepository::Statement::GetColumnBlob(
                 this,
                 v16 + 2,
                 (struct StateRepository::Entity::FileTypeAssociation *)((char *)a2 + 88));
  if ( ColumnBlob < 0 )
  {
    v7 = 1096;
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
0x18001fdc0  push    rbx
0x18001fdc2  push    rbp
0x18001fdc3  push    rsi
0x18001fdc4  push    rdi
0x18001fdc5  push    r14; int
0x18001fdc7  sub     rsp, 20h
0x18001fdcb  cmp     qword ptr [rcx], 0
0x18001fdcf  mov     rbp, r8
0x18001fdd2  mov     rbx, rdx
0x18001fdd5  mov     rdi, rcx
0x18001fdd8  jnz     short loc_18001FDFF
0x18001fdda  mov     ebx, 8007139Fh
0x18001fddf  mov     edx, 436h; void *
0x18001fde4  mov     rcx, [rsp+48h]; this
0x18001fde9  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x18001fdf0  mov     r9d, ebx; char *
0x18001fdf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fdf8  mov     eax, ebx
0x18001fdfa  jmp     loc_18001FF74
0x18001fdff  test    rbp, rbp
0x18001fe02  jz      short loc_18001FE0B
0x18001fe04  mov     [rdx], rbp
0x18001fe07  xor     esi, esi
0x18001fe09  jmp     short loc_18001FE40
0x18001fe0b  mov     r8, rbx; __int64 *
0x18001fe0e  xor     edx, edx; int
0x18001fe10  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x18001fe15  mov     esi, eax
0x18001fe17  test    eax, eax
0x18001fe19  jns     short loc_18001FE3B
0x18001fe1b  mov     edx, 43Fh; void *
0x18001fe20  mov     rcx, [rsp+48h]; this
0x18001fe25  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x18001fe2c  mov     r9d, esi; char *
0x18001fe2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe34  mov     eax, esi
0x18001fe36  jmp     loc_18001FF74
0x18001fe3b  mov     esi, 1
0x18001fe40  lea     r8, [rbx+8]; unsigned __int64 *
0x18001fe44  mov     edx, esi; int
0x18001fe46  mov     rcx, rdi; this
0x18001fe49  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x18001fe4e  mov     r14d, eax
0x18001fe51  test    eax, eax
0x18001fe53  jns     short loc_18001FE76
0x18001fe55  mov     rcx, [rsp+48h]; this
0x18001fe5a  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x18001fe61  mov     r9d, eax; char *
0x18001fe64  mov     edx, 441h; void *
0x18001fe69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe6e  mov     eax, r14d
0x18001fe71  jmp     loc_18001FF74
0x18001fe76  lea     r14d, [rsi+1]
0x18001fe7a  mov     rcx, rdi; this
0x18001fe7d  mov     edx, r14d; int
0x18001fe80  lea     r8, [rbx+10h]; __int64 *
0x18001fe84  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x18001fe89  mov     esi, eax
0x18001fe8b  test    eax, eax
0x18001fe8d  jns     short loc_18001FE96
0x18001fe8f  mov     edx, 442h
0x18001fe94  jmp     short loc_18001FE20
0x18001fe96  lea     r8, [rbx+18h]; struct StateRepository::Text *
0x18001fe9a  mov     rcx, rdi; this
0x18001fe9d  lea     edx, [r14+1]; int
0x18001fea1  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x18001fea6  mov     esi, eax
0x18001fea8  test    eax, eax
0x18001feaa  jns     short loc_18001FEB6
0x18001feac  mov     edx, 443h
0x18001feb1  jmp     loc_18001FE20
0x18001feb6  add     r14d, 2
0x18001feba  lea     r8, [rbx+28h]; struct StateRepository::Text *
0x18001febe  mov     edx, r14d; int
0x18001fec1  mov     rcx, rdi; this
0x18001fec4  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x18001fec9  mov     esi, eax
0x18001fecb  test    eax, eax
0x18001fecd  jns     short loc_18001FED9
0x18001fecf  mov     edx, 444h
0x18001fed4  jmp     loc_18001FE20
0x18001fed9  lea     r8, [rbx+38h]; __int64 *
0x18001fedd  mov     rcx, rdi; this
0x18001fee0  lea     edx, [r14+1]; int
0x18001fee4  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x18001fee9  mov     esi, eax
0x18001feeb  test    eax, eax
0x18001feed  jns     short loc_18001FEF9
0x18001feef  mov     edx, 445h
0x18001fef4  jmp     loc_18001FE20
0x18001fef9  add     r14d, 2
0x18001fefd  lea     r8, [rbx+40h]; int *
0x18001ff01  mov     edx, r14d; int
0x18001ff04  mov     rcx, rdi; this
0x18001ff07  call    ?GetColumnInt32@Statement@StateRepository@@QEBAJHPEAH@Z; StateRepository::Statement::GetColumnInt32(int,int *)
0x18001ff0c  mov     esi, eax
0x18001ff0e  test    eax, eax
0x18001ff10  jns     short loc_18001FF1C
0x18001ff12  mov     edx, 446h
0x18001ff17  jmp     loc_18001FE20
0x18001ff1c  lea     r8, [rbx+48h]; struct StateRepository::Text *
0x18001ff20  mov     rcx, rdi; this
0x18001ff23  lea     edx, [r14+1]; int
0x18001ff27  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x18001ff2c  mov     esi, eax
0x18001ff2e  test    eax, eax
0x18001ff30  jns     short loc_18001FF3C
0x18001ff32  mov     edx, 447h
0x18001ff37  jmp     loc_18001FE20
0x18001ff3c  lea     esi, [r14+2]
0x18001ff40  mov     rcx, rdi; this
0x18001ff43  mov     edx, esi; int
0x18001ff45  lea     r8, [rbx+58h]; struct StateRepository::Blob *
0x18001ff49  call    ?GetColumnBlob@Statement@StateRepository@@QEBAJHAEAVBlob@2@@Z; StateRepository::Statement::GetColumnBlob(int,StateRepository::Blob &)
0x18001ff4e  mov     ebx, eax
0x18001ff50  test    eax, eax
0x18001ff52  jns     short loc_18001FF5E
0x18001ff54  mov     edx, 448h
0x18001ff59  jmp     loc_18001FDE4
0x18001ff5e  test    rbp, rbp
0x18001ff61  jz      short loc_18001FF68
0x18001ff63  cmp     esi, 7
0x18001ff66  jmp     short loc_18001FF6B
0x18001ff68  cmp     esi, 8
0x18001ff6b  jz      short loc_18001FF72
0x18001ff6d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ff72  xor     eax, eax
0x18001ff74  add     rsp, 20h
0x18001ff78  pop     r14
0x18001ff7a  pop     rdi
0x18001ff7b  pop     rsi
0x18001ff7c  pop     rbp
0x18001ff7d  pop     rbx
0x18001ff7e  retn
```
