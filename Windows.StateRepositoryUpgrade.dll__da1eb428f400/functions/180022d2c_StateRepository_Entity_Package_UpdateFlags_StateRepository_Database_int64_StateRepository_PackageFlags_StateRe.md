# StateRepository::Entity::Package::UpdateFlags(StateRepository::Database &,__int64,StateRepository::PackageFlags,StateRepository::PackageFlags)

- ea: `0x180022d2c`
- end: `0x180022ebb`
- name: `?UpdateFlags@Package@Entity@StateRepository@@SAJAEAVDatabase@3@_JW4PackageFlags@3@2@Z`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800132e8`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018e04`
- `0x180018f78`
- `0x180019614`
- `0x18001b5a8`
- `0x18001b5dc`
- `0x18001b64c`
- `0x18001b810`
- `0x18001b8d4`
- `0x180022d2c`

## string_xrefs

- `0x180022d4f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package-custom.cpp`
- `0x180022dcb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package-custom.cpp`
- `0x180022e6b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package-custom.cpp`
- `0x180022d72`: `UPDATE Package SET Flags=((Flags & ~?) | ?) WHERE _PackageID=? AND _WorkId=0;`
- `0x180022d79`: `UPDATE Package SET Flags=((Flags & ~?) | ?) WHERE _PackageID=? AND (_WorkId=0 OR _WorkId=?);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Package::UpdateFlags(__int64 *a1, __int64 a2)
{
  unsigned int v4; // ebx
  bool v5; // zf
  const char *v6; // rdx
  int NoRow; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  int v12[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !StateRepository::Database::IsInAutoCommitMode((StateRepository::Database *)a1) )
  {
    v5 = a1[1] == 0;
    v6 = "UPDATE Package SET Flags=((Flags & ~?) | ?) WHERE _PackageID=? AND (_WorkId=0 OR _WorkId=?);";
    *(_QWORD *)v12 = 0;
    if ( v5 )
      v6 = "UPDATE Package SET Flags=((Flags & ~?) | ?) WHERE _PackageID=? AND _WorkId=0;";
    NoRow = StateRepository::Database::PrepareFromCache(
              (StateRepository::Database *)a1,
              v6,
              (struct StateRepository::Statement *)v12);
    v4 = NoRow;
    if ( NoRow >= 0 )
    {
      NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v12, 1, 0);
      v4 = NoRow;
      if ( NoRow >= 0 )
      {
        NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v12, 2, 64);
        v4 = NoRow;
        if ( NoRow >= 0 )
        {
          NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v12, 3, a2);
          v4 = NoRow;
          if ( NoRow >= 0 )
          {
            NoRow = StateRepository::Statement::BindIfWorkInProgress((StateRepository::Statement *)v12, 4, a1[1]);
            v4 = NoRow;
            if ( NoRow >= 0 )
            {
              NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)v12);
              v4 = NoRow;
              if ( NoRow >= 0 )
              {
                v10 = StateRepository::Database::AddToCache(
                        (StateRepository::Database *)a1,
                        (struct StateRepository::Statement *)v12);
                if ( v10 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x12A9,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package-custom.cpp",
                    (const char *)(unsigned int)v10,
                    v12[0]);
                if ( (unsigned int)StateRepository::Database::GetChanges((StateRepository::Database *)a1) )
                {
                  v4 = 0;
                  goto LABEL_24;
                }
                v4 = -2147023728;
                v8 = 4779;
                v9 = 2147943568LL;
LABEL_10:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package-custom.cpp",
                  (const char *)v9,
                  v12[0]);
LABEL_24:
                StateRepository::Statement::~Statement((StateRepository::Statement *)v12);
                return v4;
              }
              v8 = 4775;
            }
            else
            {
              v8 = 4773;
            }
          }
          else
          {
            v8 = 4772;
          }
        }
        else
        {
          v8 = 4771;
        }
      }
      else
      {
        v8 = 4770;
      }
    }
    else
    {
      v8 = 4769;
    }
    v9 = (unsigned int)NoRow;
    goto LABEL_10;
  }
  v4 = -2140733429;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x129B,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package-custom.cpp",
    (const char *)0x8067000BLL,
    v12[0]);
  return v4;
}

```

## disassembly

```asm
0x180022d2c  mov     [rsp+arg_0], rbx
0x180022d31  mov     [rsp+arg_8], rsi
0x180022d36  push    rdi
0x180022d37  sub     rsp, 30h
0x180022d3b  mov     rsi, rdx
0x180022d3e  mov     rdi, rcx
0x180022d41  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180022d46  test    al, al
0x180022d48  jz      short loc_180022D6D
0x180022d4a  mov     rcx, [rsp+38h]; this
0x180022d4f  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180022d56  mov     ebx, 8067000Bh
0x180022d5b  mov     edx, 129Bh; void *
0x180022d60  mov     r9d, ebx; char *
0x180022d63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022d68  jmp     loc_180022EA9
0x180022d6d  cmp     qword ptr [rdi+8], 0
0x180022d72  lea     rax, aUpdatePackageS_0; "UPDATE Package SET Flags=((Flags & ~?) "...
0x180022d79  lea     rdx, aUpdatePackageS; "UPDATE Package SET Flags=((Flags & ~?) "...
0x180022d80  mov     qword ptr [rsp+38h+var_18], 0; int
0x180022d89  cmovz   rdx, rax; char *
0x180022d8d  lea     r8, [rsp+38h+var_18]; struct StateRepository::Statement *
0x180022d92  mov     rcx, rdi; this
0x180022d95  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180022d9a  mov     ebx, eax
0x180022d9c  test    eax, eax
0x180022d9e  jns     short loc_180022DA7
0x180022da0  mov     edx, 12A1h
0x180022da5  jmp     short loc_180022DC3
0x180022da7  xor     r8d, r8d; int
0x180022daa  lea     rcx, [rsp+38h+var_18]; this
0x180022daf  lea     edx, [r8+1]; int
0x180022db3  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x180022db8  mov     ebx, eax
0x180022dba  test    eax, eax
0x180022dbc  jns     short loc_180022DDC
0x180022dbe  mov     edx, 12A2h; void *
0x180022dc3  mov     r9d, eax; char *
0x180022dc6  mov     rcx, [rsp+38h]; this
0x180022dcb  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180022dd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022dd7  jmp     loc_180022E9F
0x180022ddc  mov     edx, 2; int
0x180022de1  lea     rcx, [rsp+38h+var_18]; this
0x180022de6  lea     r8d, [rdx+3Eh]; int
0x180022dea  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x180022def  mov     ebx, eax
0x180022df1  test    eax, eax
0x180022df3  jns     short loc_180022DFC
0x180022df5  mov     edx, 12A3h
0x180022dfa  jmp     short loc_180022DC3
0x180022dfc  mov     r8, rsi; __int64
0x180022dff  lea     rcx, [rsp+38h+var_18]; this
0x180022e04  mov     edx, 3; int
0x180022e09  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180022e0e  mov     ebx, eax
0x180022e10  test    eax, eax
0x180022e12  jns     short loc_180022E1B
0x180022e14  mov     edx, 12A4h
0x180022e19  jmp     short loc_180022DC3
0x180022e1b  mov     r8, [rdi+8]; __int64
0x180022e1f  lea     rcx, [rsp+38h+var_18]; this
0x180022e24  mov     edx, 4; int
0x180022e29  call    ?BindIfWorkInProgress@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::BindIfWorkInProgress(int,__int64)
0x180022e2e  mov     ebx, eax
0x180022e30  test    eax, eax
0x180022e32  jns     short loc_180022E3B
0x180022e34  mov     edx, 12A5h
0x180022e39  jmp     short loc_180022DC3
0x180022e3b  lea     rcx, [rsp+38h+var_18]; this
0x180022e40  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x180022e45  mov     ebx, eax
0x180022e47  test    eax, eax
0x180022e49  jns     short loc_180022E55
0x180022e4b  mov     edx, 12A7h
0x180022e50  jmp     loc_180022DC3
0x180022e55  lea     rdx, [rsp+38h+var_18]; struct StateRepository::Statement *
0x180022e5a  mov     rcx, rdi; this
0x180022e5d  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180022e62  test    eax, eax
0x180022e64  jns     short loc_180022E7F
0x180022e66  mov     rcx, [rsp+38h]; this
0x180022e6b  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180022e72  mov     r9d, eax; char *
0x180022e75  mov     edx, 12A9h; void *
0x180022e7a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022e7f  mov     rcx, rdi; this
0x180022e82  call    ?GetChanges@Database@StateRepository@@QEBAHXZ; StateRepository::Database::GetChanges(void)
0x180022e87  test    eax, eax
0x180022e89  jnz     short loc_180022E9D
0x180022e8b  mov     ebx, 80070490h
0x180022e90  mov     edx, 12ABh
0x180022e95  mov     r9d, ebx
0x180022e98  jmp     loc_180022DC6
0x180022e9d  xor     ebx, ebx
0x180022e9f  lea     rcx, [rsp+38h+var_18]; this
0x180022ea4  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180022ea9  mov     rsi, [rsp+38h+arg_8]
0x180022eae  mov     eax, ebx
0x180022eb0  mov     rbx, [rsp+38h+arg_0]
0x180022eb5  add     rsp, 30h
0x180022eb9  pop     rdi
0x180022eba  retn
```
