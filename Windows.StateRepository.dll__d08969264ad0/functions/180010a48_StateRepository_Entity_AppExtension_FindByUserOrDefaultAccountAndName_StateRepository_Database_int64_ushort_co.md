# StateRepository::Entity::AppExtension::FindByUserOrDefaultAccountAndName(StateRepository::Database &,__int64,ushort const *,StateRepository::Statement &)

- ea: `0x180010a48`
- end: `0x180010d20`
- name: `?FindByUserOrDefaultAccountAndName@AppExtension@Entity@StateRepository@@SAJAEAVDatabase@3@_JPEBGAEAVStatement@3@@Z`
- size: `728`
- prototype: `__int64 __fastcall(struct StateRepository::Database *, __int64, const unsigned __int16 *, struct StateRepository::Statement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000f090`

## callees

- `0x180010a48`
- `0x180010d28`
- `0x180011bc0`
- `0x1800131f8`
- `0x180017a58`
- `0x18001a548`
- `0x18001a9e0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180010be0`
- `ntdll!RtlLengthSid` at `0x180010be0`
- `ntdll!RtlValidSid` at `0x180010bb7`
- `ntdll!RtlValidSid` at `0x180010bcf`
- `ntdll!RtlValidSid` at `0x180010bb7`
- `ntdll!RtlValidSid` at `0x180010bcf`
- `StateRepository.Core!sqlite3_bind_blob` at `0x180010c2b`
- `StateRepository.Core!sqlite3_bind_blob` at `0x180010c2b`
- `StateRepository.Core!sqlite3_bind_text16` at `0x180010b97`
- `StateRepository.Core!sqlite3_bind_text16` at `0x180010b97`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180010b3b`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180010c5b`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180010b3b`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180010c5b`

## string_xrefs

- `0x180010aa7`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appextension-custom.cpp`
- `0x180010cfb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appextension-custom.cpp`
- `0x180010a62`: `SELECT ae._AppExtensionID, ae._Revision, ae._WorkId, ae.Name, ae.Id, ae.PublicFolder, ae.DisplayName, ae.Description, ae.Extension, ae._Dictionary FROM AppExtension AS ae INNER JOIN ApplicationExtension AS ae2 ON ae2._ApplicationExtensionID=ae.Extension INNER JOIN Application AS a ON a._ApplicationID=ae2.Application INNER JOIN PackageUser AS pu ON pu.Package=a.Package WHERE (pu.User=?1 OR (pu.User IN (SELECT _UserID FROM User AS u WHERE u.UserSid=?3))) AND AND ae.Name=?2 AND (ae._WorkId=0 OR ae.`
- `0x180010a5b`: `SELECT ae._AppExtensionID, ae._Revision, ae._WorkId, ae.Name, ae.Id, ae.PublicFolder, ae.DisplayName, ae.Description, ae.Extension, ae._Dictionary FROM AppExtension AS ae INNER JOIN ApplicationExtension AS ae2 ON ae2._ApplicationExtensionID=ae.Extension INNER JOIN Application AS a ON a._ApplicationID=ae2.Application INNER JOIN PackageUser AS pu ON pu.Package=a.Package WHERE (pu.User=?1 OR (pu.User IN (SELECT _UserID FROM User AS u WHERE u.UserSid=?3))) AND ae.Name=?2 AND ae._WorkId=0 AND ae2._Wo`
- `0x180010a84`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180010ad7`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180010b10`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180010b64`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180010bbd`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::AppExtension::FindByUserOrDefaultAccountAndName(
        struct StateRepository::Database *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        struct StateRepository::Statement *a4)
{
  char *v4; // rbx
  int v9; // ebx
  __int64 v10; // rdx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  ULONG v15; // eax
  unsigned int v16; // edi
  int v17; // eax
  __int64 v18; // r8
  int v19; // eax
  struct sqlite3_stmt **v20; // rax
  __int64 v21; // r8
  __int64 v22; // rdx
  int v23; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = "SELECT ae._AppExtensionID, ae._Revision, ae._WorkId, ae.Name, ae.Id, ae.PublicFolder, ae.DisplayName, ae.Descript"
       "ion, ae.Extension, ae._Dictionary FROM AppExtension AS ae INNER JOIN ApplicationExtension AS ae2 ON ae2._Applicat"
       "ionExtensionID=ae.Extension INNER JOIN Application AS a ON a._ApplicationID=ae2.Application INNER JOIN PackageUse"
       "r AS pu ON pu.Package=a.Package WHERE (pu.User=?1 OR (pu.User IN (SELECT _UserID FROM User AS u WHERE u.UserSid=?"
       "3))) AND AND ae.Name=?2 AND (ae._WorkId=0 OR ae._WorkId=?4) AND (ae2._WorkId=0 OR ae._WorkId=?4) AND (a._WorkId=0"
       " OR a._WorkId=?4) AND (pu._WorkId=0 OR pu._WorkId=?4)";
  if ( !*((_QWORD *)a1 + 1) )
    v4 = "SELECT ae._AppExtensionID, ae._Revision, ae._WorkId, ae.Name, ae.Id, ae.PublicFolder, ae.DisplayName, ae.Descri"
         "ption, ae.Extension, ae._Dictionary FROM AppExtension AS ae INNER JOIN ApplicationExtension AS ae2 ON ae2._Appl"
         "icationExtensionID=ae.Extension INNER JOIN Application AS a ON a._ApplicationID=ae2.Application INNER JOIN Pack"
         "ageUser AS pu ON pu.Package=a.Package WHERE (pu.User=?1 OR (pu.User IN (SELECT _UserID FROM User AS u WHERE u.U"
         "serSid=?3))) AND ae.Name=?2 AND ae._WorkId=0 AND ae2._WorkId=0 AND a._WorkId=0 AND pu._WorkId=0";
  if ( !*(_QWORD *)a1 )
  {
    v9 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8007139FLL,
      v23);
LABEL_5:
    v10 = 82;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appextension-custom.cpp",
      (const char *)(unsigned int)v9,
      v23);
    return (unsigned int)v9;
  }
  v12 = StateRepository::Statement::Finalize(a4);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x679,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v12,
      v23);
  if ( !StateRepository::StatementCache::Get((struct StateRepository::Database *)((char *)a1 + 40), v4, a4) )
  {
    v20 = StateRepository::Statement::FinalizeAndAddressOf(a4);
    v9 = StateRepository::Database::dal_prepare_v2(*(struct sqlite3 **)a1, v4, v21, v20);
    if ( v9 < 0 )
      goto LABEL_5;
  }
  if ( !*(_QWORD *)a4 )
  {
    v9 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v23);
LABEL_12:
    v10 = 83;
    goto LABEL_6;
  }
  v13 = sqlite3_bind_int64(*(_QWORD *)a4, 1, a2);
  v9 = v13;
  if ( v13 > 0 )
    v9 = (unsigned __int16)v13 | 0x87AF0000;
  if ( v9 < 0 )
    goto LABEL_12;
  if ( !*(_QWORD *)a4 )
  {
    v9 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v23);
LABEL_18:
    v10 = 84;
    goto LABEL_6;
  }
  v23 = -1;
  v14 = sqlite3_bind_text16(*(_QWORD *)a4, 2, a3);
  v9 = v14;
  if ( v14 > 0 )
    v9 = (unsigned __int16)v14 | 0x87AF0000;
  if ( v9 < 0 )
    goto LABEL_18;
  if ( !RtlValidSid(qword_1804E01E0) )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x203,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8000FFFFLL,
      -1);
  if ( !RtlValidSid(qword_1804E01E0) )
  {
    v22 = 516;
LABEL_42:
    v16 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x80070057LL,
      v23);
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appextension-custom.cpp",
      (const char *)v16,
      v23);
    return v16;
  }
  v15 = RtlLengthSid(qword_1804E01E0);
  if ( v15 == 0x7FFFFFFF )
  {
    v22 = 494;
    goto LABEL_42;
  }
  v9 = -2147019873;
  if ( *(_QWORD *)a4 )
  {
    v17 = sqlite3_bind_blob(*(_QWORD *)a4, 3, qword_1804E01E0, v15, 0);
    v16 = v17;
    if ( v17 > 0 )
      v16 = (unsigned __int16)v17 | 0x87AF0000;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v23);
    v16 = -2147019873;
  }
  if ( (v16 & 0x80000000) != 0 )
    goto LABEL_43;
  v18 = *((_QWORD *)a1 + 1);
  if ( v18 )
  {
    if ( *(_QWORD *)a4 )
    {
      v19 = sqlite3_bind_int64(*(_QWORD *)a4, 4, v18);
      v9 = v19;
      if ( v19 > 0 )
        v9 = (unsigned __int16)v19 | 0x87AF0000;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)0x8007139FLL,
        v23);
    }
    if ( v9 < 0 )
    {
      v10 = 86;
      goto LABEL_6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010a48  push    rbx
0x180010a4a  push    rsi
0x180010a4b  push    rdi
0x180010a4c  push    r12
0x180010a4e  push    r14
0x180010a50  push    r15
0x180010a52  sub     rsp, 38h
0x180010a56  cmp     qword ptr [rcx+8], 0
0x180010a5b  lea     rax, aSelectAeAppext_1; "SELECT ae._AppExtensionID, ae._Revision"...
0x180010a62  lea     rbx, aSelectAeAppext; "SELECT ae._AppExtensionID, ae._Revision"...
0x180010a69  mov     r14, r9
0x180010a6c  cmovz   rbx, rax
0x180010a70  mov     rsi, r8
0x180010a73  cmp     qword ptr [rcx], 0
0x180010a77  mov     rdi, rdx
0x180010a7a  mov     r15, rcx
0x180010a7d  jnz     short loc_180010AC6
0x180010a7f  mov     rcx, [rsp+68h]; this
0x180010a84  lea     r8, aOnecoreBaseApp_370; "onecore\\base\\appmodel\\staterepositor"...
0x180010a8b  mov     ebx, 8007139Fh
0x180010a90  mov     edx, 66Eh; void *
0x180010a95  mov     r9d, ebx; char *
0x180010a98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a9d  mov     edx, 52h ; 'R'; void *
0x180010aa2  mov     rcx, [rsp+68h]; this
0x180010aa7  lea     r8, aOnecoreBaseApp_481; "onecore\\base\\appmodel\\staterepositor"...
0x180010aae  mov     r9d, ebx; char *
0x180010ab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ab6  mov     eax, ebx
0x180010ab8  add     rsp, 38h
0x180010abc  pop     r15
0x180010abe  pop     r14
0x180010ac0  pop     r12
0x180010ac2  pop     rdi
0x180010ac3  pop     rsi
0x180010ac4  pop     rbx
0x180010ac5  retn
0x180010ac6  mov     rcx, r14; this
0x180010ac9  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180010ace  test    eax, eax
0x180010ad0  jns     short loc_180010AEB
0x180010ad2  mov     rcx, [rsp+68h]; this
0x180010ad7  lea     r8, aOnecoreBaseApp_370; "onecore\\base\\appmodel\\staterepositor"...
0x180010ade  mov     r9d, eax; char *
0x180010ae1  mov     edx, 679h; void *
0x180010ae6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010aeb  lea     rcx, [r15+28h]; this
0x180010aef  mov     r8, r14; struct StateRepository::Statement *
0x180010af2  mov     rdx, rbx; char *
0x180010af5  call    ?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z; StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)
0x180010afa  test    rax, rax
0x180010afd  jz      loc_180010C93
0x180010b03  mov     rcx, [r14]
0x180010b06  test    rcx, rcx
0x180010b09  jnz     short loc_180010B33
0x180010b0b  mov     rcx, [rsp+68h]; this
0x180010b10  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180010b17  mov     ebx, 8007139Fh
0x180010b1c  mov     edx, 0C9h; void *
0x180010b21  mov     r9d, ebx; char *
0x180010b24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b29  mov     edx, 53h ; 'S'
0x180010b2e  jmp     loc_180010AA2
0x180010b33  mov     r8, rdi
0x180010b36  mov     edx, 1
0x180010b3b  call    cs:__imp_sqlite3_bind_int64
0x180010b41  mov     ebx, eax
0x180010b43  mov     r12d, 87AF0000h
0x180010b49  test    eax, eax
0x180010b4b  jle     short loc_180010B53
0x180010b4d  movzx   ebx, ax
0x180010b50  or      ebx, r12d
0x180010b53  test    ebx, ebx
0x180010b55  js      short loc_180010B29
0x180010b57  mov     rcx, [r14]
0x180010b5a  test    rcx, rcx
0x180010b5d  jnz     short loc_180010B87
0x180010b5f  mov     rcx, [rsp+68h]; this
0x180010b64  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180010b6b  mov     ebx, 8007139Fh
0x180010b70  mov     edx, 13Bh; void *
0x180010b75  mov     r9d, ebx; char *
0x180010b78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b7d  mov     edx, 54h ; 'T'
0x180010b82  jmp     loc_180010AA2
0x180010b87  or      r9, 0FFFFFFFFFFFFFFFFh
0x180010b8b  mov     r8, rsi
0x180010b8e  mov     qword ptr [rsp+68h+var_48], r9; int
0x180010b93  lea     edx, [r9+3]
0x180010b97  call    cs:__imp_sqlite3_bind_text16
0x180010b9d  mov     ebx, eax
0x180010b9f  test    eax, eax
0x180010ba1  jle     short loc_180010BA9
0x180010ba3  movzx   ebx, ax
0x180010ba6  or      ebx, r12d
0x180010ba9  test    ebx, ebx
0x180010bab  js      short loc_180010B7D
0x180010bad  lea     rdi, qword_1804E01E0
0x180010bb4  mov     rcx, rdi; Sid
0x180010bb7  call    cs:__imp_RtlValidSid
0x180010bbd  lea     rsi, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180010bc4  test    al, al
0x180010bc6  jz      loc_180010CB8
0x180010bcc  mov     rcx, rdi; Sid
0x180010bcf  call    cs:__imp_RtlValidSid
0x180010bd5  test    al, al
0x180010bd7  jz      loc_180010CD5
0x180010bdd  mov     rcx, rdi; Sid
0x180010be0  call    cs:__imp_RtlLengthSid
0x180010be6  cmp     eax, 7FFFFFFFh
0x180010beb  jz      loc_180010CDC
0x180010bf1  mov     rcx, [r14]
0x180010bf4  mov     ebx, 8007139Fh
0x180010bf9  test    rcx, rcx
0x180010bfc  jnz     short loc_180010C17
0x180010bfe  mov     rcx, [rsp+68h]; this
0x180010c03  mov     r9d, ebx; char *
0x180010c06  mov     r8, rsi; unsigned int
0x180010c09  mov     edx, 1E4h; void *
0x180010c0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c13  mov     edi, ebx
0x180010c15  jmp     short loc_180010C3D
0x180010c17  mov     r9d, eax
0x180010c1a  mov     qword ptr [rsp+68h+var_48], 0; int
0x180010c23  mov     r8, rdi
0x180010c26  mov     edx, 3
0x180010c2b  call    cs:__imp_sqlite3_bind_blob
0x180010c31  mov     edi, eax
0x180010c33  test    eax, eax
0x180010c35  jle     short loc_180010C3D
0x180010c37  movzx   edi, ax
0x180010c3a  or      edi, r12d
0x180010c3d  test    edi, edi
0x180010c3f  js      loc_180010CF6
0x180010c45  mov     r8, [r15+8]
0x180010c49  test    r8, r8
0x180010c4c  jz      short loc_180010C75
0x180010c4e  mov     rcx, [r14]
0x180010c51  test    rcx, rcx
0x180010c54  jz      short loc_180010C7C
0x180010c56  mov     edx, 4
0x180010c5b  call    cs:__imp_sqlite3_bind_int64
0x180010c61  mov     ebx, eax
0x180010c63  test    eax, eax
0x180010c65  jle     short loc_180010C6D
0x180010c67  movzx   ebx, ax
0x180010c6a  or      ebx, r12d
0x180010c6d  test    ebx, ebx
0x180010c6f  js      loc_180010D16
0x180010c75  xor     eax, eax
0x180010c77  jmp     loc_180010AB8
0x180010c7c  mov     rcx, [rsp+68h]; this
0x180010c81  mov     r9d, ebx; char *
0x180010c84  mov     r8, rsi; unsigned int
0x180010c87  mov     edx, 0C9h; void *
0x180010c8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c91  jmp     short loc_180010C6D
0x180010c93  mov     rcx, r14; this
0x180010c96  call    ?FinalizeAndAddressOf@Statement@StateRepository@@QEAAPEAPEAUsqlite3_stmt@@XZ; StateRepository::Statement::FinalizeAndAddressOf(void)
0x180010c9b  mov     rcx, [r15]; struct sqlite3 *
0x180010c9e  mov     r9, rax; struct sqlite3_stmt **
0x180010ca1  mov     rdx, rbx; char *
0x180010ca4  call    ?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z; StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)
0x180010ca9  mov     ebx, eax
0x180010cab  test    eax, eax
0x180010cad  js      loc_180010A9D
0x180010cb3  jmp     loc_180010B03
0x180010cb8  mov     rcx, [rsp+68h]; this
0x180010cbd  mov     r9d, 8000FFFFh; char *
0x180010cc3  mov     r8, rsi; unsigned int
0x180010cc6  mov     edx, 203h; void *
0x180010ccb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010cd0  jmp     loc_180010BCC
0x180010cd5  mov     edx, 204h
0x180010cda  jmp     short loc_180010CE1
0x180010cdc  mov     edx, 1EEh; void *
0x180010ce1  mov     rcx, [rsp+68h]; this
0x180010ce6  mov     edi, 80070057h
0x180010ceb  mov     r9d, edi; char *
0x180010cee  mov     r8, rsi; unsigned int
0x180010cf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010cf6  mov     rcx, [rsp+68h]; this
0x180010cfb  lea     r8, aOnecoreBaseApp_481; "onecore\\base\\appmodel\\staterepositor"...
0x180010d02  mov     r9d, edi; char *
0x180010d05  mov     edx, 55h ; 'U'; void *
0x180010d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010d0f  mov     eax, edi
0x180010d11  jmp     loc_180010AB8
0x180010d16  mov     edx, 56h ; 'V'
0x180010d1b  jmp     loc_180010AA2
```
