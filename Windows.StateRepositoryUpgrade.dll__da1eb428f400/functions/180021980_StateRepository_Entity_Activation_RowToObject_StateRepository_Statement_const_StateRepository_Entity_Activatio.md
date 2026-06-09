# StateRepository::Entity::Activation::RowToObject(StateRepository::Statement const &,StateRepository::Entity::Activation &,__int64)

- ea: `0x180021980`
- end: `0x180021b76`
- name: `?RowToObject@Activation@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z`
- size: `502`
- prototype: `__int64 __fastcall(const struct StateRepository::Statement *this, struct StateRepository::Entity::Activation *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180021b7c`
- `0x180021c48`

## callees

- `0x18000a3c0`
- `0x18001b9d4`
- `0x18001bca0`
- `0x18001bd28`
- `0x18001be40`
- `0x18001bf44`
- `0x180021980`
- `0x18002db14`

## string_xrefs

- `0x1800219a9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-activation.cpp`
- `0x1800219e5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-activation.cpp`
- `0x180021a19`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-activation.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Activation::RowToObject(
        const struct StateRepository::Statement *this,
        struct StateRepository::Entity::Activation *a2,
        __int64 a3)
{
  int ColumnBlob; // ebx
  __int64 v7; // rdx
  int v9; // esi
  int ColumnInt64; // esi
  __int64 v11; // rdx
  int ColumnUInt64; // eax
  unsigned int v13; // ebp
  int v14; // ebp
  int v15; // ebp
  int v16; // ebp
  int v17; // ebp
  int v18; // esi
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !*(_QWORD *)this )
  {
    ColumnBlob = -2147019873;
    v7 = 685;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-activation.cpp",
      (const char *)(unsigned int)ColumnBlob,
      v20);
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
      v11 = 694;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-activation.cpp",
        (const char *)(unsigned int)ColumnInt64,
        v20);
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
      (void *)0x2B8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-activation.cpp",
      (const char *)(unsigned int)ColumnUInt64,
      v20);
    return v13;
  }
  v14 = v9 + 1;
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v9 + 1,
                  (struct StateRepository::Entity::Activation *)((char *)a2 + 16));
  if ( ColumnInt64 < 0 )
  {
    v11 = 697;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnInt32(this, v14 + 1, (int *)a2 + 8);
  if ( ColumnInt64 < 0 )
  {
    v11 = 699;
    goto LABEL_8;
  }
  v15 = v14 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v15,
                  (struct StateRepository::Entity::Activation *)((char *)a2 + 40));
  if ( ColumnInt64 < 0 )
  {
    v11 = 700;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v15 + 1,
                  (struct StateRepository::Entity::Activation *)((char *)a2 + 56));
  if ( ColumnInt64 < 0 )
  {
    v11 = 701;
    goto LABEL_8;
  }
  v16 = v15 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v16,
                  (struct StateRepository::Entity::Activation *)((char *)a2 + 72));
  if ( ColumnInt64 < 0 )
  {
    v11 = 702;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v16 + 1,
                  (struct StateRepository::Entity::Activation *)((char *)a2 + 88));
  if ( ColumnInt64 < 0 )
  {
    v11 = 703;
    goto LABEL_8;
  }
  v17 = v16 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v17,
                  (struct StateRepository::Entity::Activation *)((char *)a2 + 104));
  if ( ColumnInt64 < 0 )
  {
    v11 = 704;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v17 + 1,
                  (struct StateRepository::Entity::Activation *)((char *)a2 + 120));
  if ( ColumnInt64 < 0 )
  {
    v11 = 705;
    goto LABEL_8;
  }
  v18 = v17 + 2;
  ColumnBlob = StateRepository::Statement::GetColumnBlob(
                 this,
                 v17 + 2,
                 (struct StateRepository::Entity::Activation *)((char *)a2 + 136));
  if ( ColumnBlob < 0 )
  {
    v7 = 706;
    goto LABEL_3;
  }
  if ( a3 )
    v19 = v18 == 9;
  else
    v19 = v18 == 10;
  if ( !v19 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return 0;
}

```

## disassembly

```asm
0x180021980  push    rbx
0x180021982  push    rbp
0x180021983  push    rsi
0x180021984  push    rdi
0x180021985  push    r14; int
0x180021987  sub     rsp, 20h
0x18002198b  cmp     qword ptr [rcx], 0
0x18002198f  mov     r14, r8
0x180021992  mov     rbx, rdx
0x180021995  mov     rdi, rcx
0x180021998  jnz     short loc_1800219BF
0x18002199a  mov     ebx, 8007139Fh
0x18002199f  mov     edx, 2ADh; void *
0x1800219a4  mov     rcx, [rsp+48h]; this
0x1800219a9  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x1800219b0  mov     r9d, ebx; char *
0x1800219b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800219b8  mov     eax, ebx
0x1800219ba  jmp     loc_180021B6B
0x1800219bf  test    r14, r14
0x1800219c2  jz      short loc_1800219CB
0x1800219c4  mov     [rdx], r14
0x1800219c7  xor     esi, esi
0x1800219c9  jmp     short loc_180021A00
0x1800219cb  mov     r8, rbx; __int64 *
0x1800219ce  xor     edx, edx; int
0x1800219d0  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x1800219d5  mov     esi, eax
0x1800219d7  test    eax, eax
0x1800219d9  jns     short loc_1800219FB
0x1800219db  mov     edx, 2B6h; void *
0x1800219e0  mov     rcx, [rsp+48h]; this
0x1800219e5  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x1800219ec  mov     r9d, esi; char *
0x1800219ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800219f4  mov     eax, esi
0x1800219f6  jmp     loc_180021B6B
0x1800219fb  mov     esi, 1
0x180021a00  lea     r8, [rbx+8]; unsigned __int64 *
0x180021a04  mov     edx, esi; int
0x180021a06  mov     rcx, rdi; this
0x180021a09  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180021a0e  mov     ebp, eax
0x180021a10  test    eax, eax
0x180021a12  jns     short loc_180021A34
0x180021a14  mov     rcx, [rsp+48h]; this
0x180021a19  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x180021a20  mov     r9d, eax; char *
0x180021a23  mov     edx, 2B8h; void *
0x180021a28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021a2d  mov     eax, ebp
0x180021a2f  jmp     loc_180021B6B
0x180021a34  lea     ebp, [rsi+1]
0x180021a37  mov     rcx, rdi; this
0x180021a3a  mov     edx, ebp; int
0x180021a3c  lea     r8, [rbx+10h]; struct StateRepository::Text *
0x180021a40  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x180021a45  mov     esi, eax
0x180021a47  test    eax, eax
0x180021a49  jns     short loc_180021A52
0x180021a4b  mov     edx, 2B9h
0x180021a50  jmp     short loc_1800219E0
0x180021a52  lea     r8, [rbx+20h]; int *
0x180021a56  mov     rcx, rdi; this
0x180021a59  lea     edx, [rbp+1]; int
0x180021a5c  call    ?GetColumnInt32@Statement@StateRepository@@QEBAJHPEAH@Z; StateRepository::Statement::GetColumnInt32(int,int *)
0x180021a61  mov     esi, eax
0x180021a63  test    eax, eax
0x180021a65  jns     short loc_180021A71
0x180021a67  mov     edx, 2BBh
0x180021a6c  jmp     loc_1800219E0
0x180021a71  add     ebp, 2
0x180021a74  lea     r8, [rbx+28h]; struct StateRepository::Text *
0x180021a78  mov     edx, ebp; int
0x180021a7a  mov     rcx, rdi; this
0x180021a7d  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x180021a82  mov     esi, eax
0x180021a84  test    eax, eax
0x180021a86  jns     short loc_180021A92
0x180021a88  mov     edx, 2BCh
0x180021a8d  jmp     loc_1800219E0
0x180021a92  lea     r8, [rbx+38h]; struct StateRepository::Text *
0x180021a96  mov     rcx, rdi; this
0x180021a99  lea     edx, [rbp+1]; int
0x180021a9c  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x180021aa1  mov     esi, eax
0x180021aa3  test    eax, eax
0x180021aa5  jns     short loc_180021AB1
0x180021aa7  mov     edx, 2BDh
0x180021aac  jmp     loc_1800219E0
0x180021ab1  add     ebp, 2
0x180021ab4  lea     r8, [rbx+48h]; struct StateRepository::Text *
0x180021ab8  mov     edx, ebp; int
0x180021aba  mov     rcx, rdi; this
0x180021abd  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x180021ac2  mov     esi, eax
0x180021ac4  test    eax, eax
0x180021ac6  jns     short loc_180021AD2
0x180021ac8  mov     edx, 2BEh
0x180021acd  jmp     loc_1800219E0
0x180021ad2  lea     r8, [rbx+58h]; struct StateRepository::Text *
0x180021ad6  mov     rcx, rdi; this
0x180021ad9  lea     edx, [rbp+1]; int
0x180021adc  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x180021ae1  mov     esi, eax
0x180021ae3  test    eax, eax
0x180021ae5  jns     short loc_180021AF1
0x180021ae7  mov     edx, 2BFh
0x180021aec  jmp     loc_1800219E0
0x180021af1  add     ebp, 2
0x180021af4  lea     r8, [rbx+68h]; struct StateRepository::Text *
0x180021af8  mov     edx, ebp; int
0x180021afa  mov     rcx, rdi; this
0x180021afd  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x180021b02  mov     esi, eax
0x180021b04  test    eax, eax
0x180021b06  jns     short loc_180021B12
0x180021b08  mov     edx, 2C0h
0x180021b0d  jmp     loc_1800219E0
0x180021b12  lea     r8, [rbx+78h]; struct StateRepository::Text *
0x180021b16  mov     rcx, rdi; this
0x180021b19  lea     edx, [rbp+1]; int
0x180021b1c  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x180021b21  mov     esi, eax
0x180021b23  test    eax, eax
0x180021b25  jns     short loc_180021B31
0x180021b27  mov     edx, 2C1h
0x180021b2c  jmp     loc_1800219E0
0x180021b31  lea     esi, [rbp+2]
0x180021b34  mov     rcx, rdi; this
0x180021b37  mov     edx, esi; int
0x180021b39  lea     r8, [rbx+88h]; struct StateRepository::Blob *
0x180021b40  call    ?GetColumnBlob@Statement@StateRepository@@QEBAJHAEAVBlob@2@@Z; StateRepository::Statement::GetColumnBlob(int,StateRepository::Blob &)
0x180021b45  mov     ebx, eax
0x180021b47  test    eax, eax
0x180021b49  jns     short loc_180021B55
0x180021b4b  mov     edx, 2C2h
0x180021b50  jmp     loc_1800219A4
0x180021b55  test    r14, r14
0x180021b58  jz      short loc_180021B5F
0x180021b5a  cmp     esi, 9
0x180021b5d  jmp     short loc_180021B62
0x180021b5f  cmp     esi, 0Ah
0x180021b62  jz      short loc_180021B69
0x180021b64  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180021b69  xor     eax, eax
0x180021b6b  add     rsp, 20h
0x180021b6f  pop     r14
0x180021b71  pop     rdi
0x180021b72  pop     rsi
0x180021b73  pop     rbp
0x180021b74  pop     rbx
0x180021b75  retn
```
