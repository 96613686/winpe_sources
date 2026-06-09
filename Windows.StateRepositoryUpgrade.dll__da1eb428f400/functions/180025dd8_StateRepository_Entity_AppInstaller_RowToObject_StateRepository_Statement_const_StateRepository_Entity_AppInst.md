# StateRepository::Entity::AppInstaller::RowToObject(StateRepository::Statement const &,StateRepository::Entity::AppInstaller &,__int64)

- ea: `0x180025dd8`
- end: `0x180025fab`
- name: `?RowToObject@AppInstaller@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z`
- size: `467`
- prototype: `__int64 __fastcall(const struct StateRepository::Statement *this, struct StateRepository::Entity::AppInstaller *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025fb4`

## callees

- `0x18000a3c0`
- `0x18001b9d4`
- `0x18001bc20`
- `0x18001bca0`
- `0x18001bd28`
- `0x18001be40`
- `0x18001bec8`
- `0x18001bf44`
- `0x180025dd8`
- `0x18002db14`

## string_xrefs

- `0x180025e01`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appinstaller.cpp`
- `0x180025e3d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appinstaller.cpp`
- `0x180025e71`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appinstaller.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::AppInstaller::RowToObject(
        const struct StateRepository::Statement *this,
        struct StateRepository::Entity::AppInstaller *a2,
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
    v7 = 721;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appinstaller.cpp",
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
      v11 = 730;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appinstaller.cpp",
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
      (void *)0x2DC,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appinstaller.cpp",
      (const char *)(unsigned int)ColumnUInt64,
      v20);
    return v13;
  }
  v14 = v9 + 1;
  ColumnInt64 = StateRepository::Statement::GetColumnInt64(this, v9 + 1, (__int64 *)a2 + 2);
  if ( ColumnInt64 < 0 )
  {
    v11 = 733;
    goto LABEL_8;
  }
  v15 = v14 + 1;
  ColumnInt64 = StateRepository::Statement::GetColumnText(
                  this,
                  v15,
                  (struct StateRepository::Entity::AppInstaller *)((char *)a2 + 24));
  if ( ColumnInt64 < 0 )
  {
    v11 = 734;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnUInt64(this, v15 + 1, (unsigned __int64 *)a2 + 5);
  if ( ColumnInt64 < 0 )
  {
    v11 = 735;
    goto LABEL_8;
  }
  v16 = v15 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnDateTime(this, v16, (struct _FILETIME *)a2 + 6);
  if ( ColumnInt64 < 0 )
  {
    v11 = 736;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnUInt32(this, v16 + 1, (unsigned int *)a2 + 14);
  if ( ColumnInt64 < 0 )
  {
    v11 = 737;
    goto LABEL_8;
  }
  v17 = v16 + 2;
  ColumnInt64 = StateRepository::Statement::GetColumnInt32(this, v17, (int *)a2 + 15);
  if ( ColumnInt64 < 0 )
  {
    v11 = 739;
    goto LABEL_8;
  }
  ColumnInt64 = StateRepository::Statement::GetColumnDateTime(this, v17 + 1, (struct _FILETIME *)a2 + 8);
  if ( ColumnInt64 < 0 )
  {
    v11 = 740;
    goto LABEL_8;
  }
  v18 = v17 + 2;
  ColumnBlob = StateRepository::Statement::GetColumnBlob(
                 this,
                 v17 + 2,
                 (struct StateRepository::Entity::AppInstaller *)((char *)a2 + 72));
  if ( ColumnBlob < 0 )
  {
    v7 = 741;
    goto LABEL_3;
  }
  if ( a3 )
    v19 = v18 == 8;
  else
    v19 = v18 == 9;
  if ( !v19 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return 0;
}

```

## disassembly

```asm
0x180025dd8  push    rbx
0x180025dda  push    rbp
0x180025ddb  push    rsi
0x180025ddc  push    rdi
0x180025ddd  push    r14; int
0x180025ddf  sub     rsp, 20h
0x180025de3  cmp     qword ptr [rcx], 0
0x180025de7  mov     r14, r8
0x180025dea  mov     rbx, rdx
0x180025ded  mov     rdi, rcx
0x180025df0  jnz     short loc_180025E17
0x180025df2  mov     ebx, 8007139Fh
0x180025df7  mov     edx, 2D1h; void *
0x180025dfc  mov     rcx, [rsp+48h]; this
0x180025e01  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\staterepositor"...
0x180025e08  mov     r9d, ebx; char *
0x180025e0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e10  mov     eax, ebx
0x180025e12  jmp     loc_180025FA0
0x180025e17  test    r14, r14
0x180025e1a  jz      short loc_180025E23
0x180025e1c  mov     [rdx], r14
0x180025e1f  xor     esi, esi
0x180025e21  jmp     short loc_180025E58
0x180025e23  mov     r8, rbx; __int64 *
0x180025e26  xor     edx, edx; int
0x180025e28  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x180025e2d  mov     esi, eax
0x180025e2f  test    eax, eax
0x180025e31  jns     short loc_180025E53
0x180025e33  mov     edx, 2DAh; void *
0x180025e38  mov     rcx, [rsp+48h]; this
0x180025e3d  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\staterepositor"...
0x180025e44  mov     r9d, esi; char *
0x180025e47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e4c  mov     eax, esi
0x180025e4e  jmp     loc_180025FA0
0x180025e53  mov     esi, 1
0x180025e58  lea     r8, [rbx+8]; unsigned __int64 *
0x180025e5c  mov     edx, esi; int
0x180025e5e  mov     rcx, rdi; this
0x180025e61  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180025e66  mov     ebp, eax
0x180025e68  test    eax, eax
0x180025e6a  jns     short loc_180025E8C
0x180025e6c  mov     rcx, [rsp+48h]; this
0x180025e71  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\staterepositor"...
0x180025e78  mov     r9d, eax; char *
0x180025e7b  mov     edx, 2DCh; void *
0x180025e80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e85  mov     eax, ebp
0x180025e87  jmp     loc_180025FA0
0x180025e8c  lea     ebp, [rsi+1]
0x180025e8f  mov     rcx, rdi; this
0x180025e92  mov     edx, ebp; int
0x180025e94  lea     r8, [rbx+10h]; __int64 *
0x180025e98  call    ?GetColumnInt64@Statement@StateRepository@@QEBAJHPEA_J@Z; StateRepository::Statement::GetColumnInt64(int,__int64 *)
0x180025e9d  mov     esi, eax
0x180025e9f  test    eax, eax
0x180025ea1  jns     short loc_180025EAA
0x180025ea3  mov     edx, 2DDh
0x180025ea8  jmp     short loc_180025E38
0x180025eaa  inc     ebp
0x180025eac  lea     r8, [rbx+18h]; struct StateRepository::Text *
0x180025eb0  mov     edx, ebp; int
0x180025eb2  mov     rcx, rdi; this
0x180025eb5  call    ?GetColumnText@Statement@StateRepository@@QEBAJHAEAVText@2@@Z; StateRepository::Statement::GetColumnText(int,StateRepository::Text &)
0x180025eba  mov     esi, eax
0x180025ebc  test    eax, eax
0x180025ebe  jns     short loc_180025ECA
0x180025ec0  mov     edx, 2DEh
0x180025ec5  jmp     loc_180025E38
0x180025eca  lea     r8, [rbx+28h]; unsigned __int64 *
0x180025ece  mov     rcx, rdi; this
0x180025ed1  lea     edx, [rbp+1]; int
0x180025ed4  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180025ed9  mov     esi, eax
0x180025edb  test    eax, eax
0x180025edd  jns     short loc_180025EE9
0x180025edf  mov     edx, 2DFh
0x180025ee4  jmp     loc_180025E38
0x180025ee9  add     ebp, 2
0x180025eec  lea     r8, [rbx+30h]; struct _FILETIME *
0x180025ef0  mov     edx, ebp; int
0x180025ef2  mov     rcx, rdi; this
0x180025ef5  call    ?GetColumnDateTime@Statement@StateRepository@@QEBAJHPEAU_FILETIME@@@Z; StateRepository::Statement::GetColumnDateTime(int,_FILETIME *)
0x180025efa  mov     esi, eax
0x180025efc  test    eax, eax
0x180025efe  jns     short loc_180025F0A
0x180025f00  mov     edx, 2E0h
0x180025f05  jmp     loc_180025E38
0x180025f0a  lea     r8, [rbx+38h]; unsigned int *
0x180025f0e  mov     rcx, rdi; this
0x180025f11  lea     edx, [rbp+1]; int
0x180025f14  call    ?GetColumnUInt32@Statement@StateRepository@@QEBAJHPEAI@Z; StateRepository::Statement::GetColumnUInt32(int,uint *)
0x180025f19  mov     esi, eax
0x180025f1b  test    eax, eax
0x180025f1d  jns     short loc_180025F29
0x180025f1f  mov     edx, 2E1h
0x180025f24  jmp     loc_180025E38
0x180025f29  add     ebp, 2
0x180025f2c  lea     r8, [rbx+3Ch]; int *
0x180025f30  mov     edx, ebp; int
0x180025f32  mov     rcx, rdi; this
0x180025f35  call    ?GetColumnInt32@Statement@StateRepository@@QEBAJHPEAH@Z; StateRepository::Statement::GetColumnInt32(int,int *)
0x180025f3a  mov     esi, eax
0x180025f3c  test    eax, eax
0x180025f3e  jns     short loc_180025F4A
0x180025f40  mov     edx, 2E3h
0x180025f45  jmp     loc_180025E38
0x180025f4a  lea     r8, [rbx+40h]; struct _FILETIME *
0x180025f4e  mov     rcx, rdi; this
0x180025f51  lea     edx, [rbp+1]; int
0x180025f54  call    ?GetColumnDateTime@Statement@StateRepository@@QEBAJHPEAU_FILETIME@@@Z; StateRepository::Statement::GetColumnDateTime(int,_FILETIME *)
0x180025f59  mov     esi, eax
0x180025f5b  test    eax, eax
0x180025f5d  jns     short loc_180025F69
0x180025f5f  mov     edx, 2E4h
0x180025f64  jmp     loc_180025E38
0x180025f69  lea     esi, [rbp+2]
0x180025f6c  mov     rcx, rdi; this
0x180025f6f  mov     edx, esi; int
0x180025f71  lea     r8, [rbx+48h]; struct StateRepository::Blob *
0x180025f75  call    ?GetColumnBlob@Statement@StateRepository@@QEBAJHAEAVBlob@2@@Z; StateRepository::Statement::GetColumnBlob(int,StateRepository::Blob &)
0x180025f7a  mov     ebx, eax
0x180025f7c  test    eax, eax
0x180025f7e  jns     short loc_180025F8A
0x180025f80  mov     edx, 2E5h
0x180025f85  jmp     loc_180025DFC
0x180025f8a  test    r14, r14
0x180025f8d  jz      short loc_180025F94
0x180025f8f  cmp     esi, 8
0x180025f92  jmp     short loc_180025F97
0x180025f94  cmp     esi, 9
0x180025f97  jz      short loc_180025F9E
0x180025f99  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f9e  xor     eax, eax
0x180025fa0  add     rsp, 20h
0x180025fa4  pop     r14
0x180025fa6  pop     rdi
0x180025fa7  pop     rsi
0x180025fa8  pop     rbp
0x180025fa9  pop     rbx
0x180025faa  retn
```
