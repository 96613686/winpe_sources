# StateRepository::Entity::ApplicationExtension::UpdateActivationBy_PrimaryKey(StateRepository::Database &,__int64,__int64)

- ea: `0x18001df68`
- end: `0x18001e0c2`
- name: `?UpdateActivationBy_PrimaryKey@ApplicationExtension@Entity@StateRepository@@QEAAJAEAVDatabase@3@_J1@Z`
- size: `346`
- prototype: `int(StateRepository::Entity::ApplicationExtension *__hidden this, struct StateRepository::Database *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d54c`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018e04`
- `0x180018f78`
- `0x180019614`
- `0x18001b5a8`
- `0x18001b64c`
- `0x18001b8d4`
- `0x18001df68`

## string_xrefs

- `0x18001df8f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`
- `0x18001dffc`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`
- `0x18001e079`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`
- `0x18001dfbb`: `UPDATE ApplicationExtension SET Activation=? WHERE _ApplicationExtensionID=? AND _WorkId=?;`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::ApplicationExtension::UpdateActivationBy_PrimaryKey(
        StateRepository::Entity::ApplicationExtension *this,
        struct StateRepository::Database *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v7; // ebx
  int NoRow; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  StateRepository::Entity::ApplicationExtension *v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = this;
  if ( !StateRepository::Database::IsInAutoCommitMode(a2) )
  {
    v15 = 0;
    NoRow = StateRepository::Database::PrepareFromCache(
              a2,
              "UPDATE ApplicationExtension SET Activation=? WHERE _ApplicationExtensionID=? AND _WorkId=?;",
              (struct StateRepository::Statement *)&v15);
    v7 = NoRow;
    if ( NoRow >= 0 )
    {
      NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v15, 1, a4);
      v7 = NoRow;
      if ( NoRow >= 0 )
      {
        NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v15, 2, a3);
        v7 = NoRow;
        if ( NoRow >= 0 )
        {
          NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v15, 3, *((_QWORD *)a2 + 1));
          v7 = NoRow;
          if ( NoRow >= 0 )
          {
            NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v15);
            v7 = NoRow;
            if ( NoRow >= 0 )
            {
              v11 = StateRepository::Database::AddToCache(a2, (struct StateRepository::Statement *)&v15);
              if ( v11 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x308,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
                  (const char *)(unsigned int)v11,
                  v13);
              if ( (unsigned int)StateRepository::Database::GetChanges(a2) )
              {
                v7 = 0;
                goto LABEL_20;
              }
              v7 = -2147023728;
              v9 = 778;
              v10 = 2147943568LL;
LABEL_8:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v9,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
                (const char *)v10,
                v13);
LABEL_20:
              StateRepository::Statement::~Statement((StateRepository::Statement *)&v15);
              return v7;
            }
            v9 = 774;
          }
          else
          {
            v9 = 772;
          }
        }
        else
        {
          v9 = 771;
        }
      }
      else
      {
        v9 = 770;
      }
    }
    else
    {
      v9 = 769;
    }
    v10 = (unsigned int)NoRow;
    goto LABEL_8;
  }
  v7 = -2140733429;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2FD,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
    (const char *)0x8067000BLL,
    v13);
  return v7;
}

```

## disassembly

```asm
0x18001df68  mov     [rsp+arg_0], rcx
0x18001df6d  push    rbx
0x18001df6e  push    rbp
0x18001df6f  push    rsi
0x18001df70  push    rdi
0x18001df71  sub     rsp, 28h
0x18001df75  mov     rcx, rdx; this
0x18001df78  mov     rsi, r9
0x18001df7b  mov     rbp, r8
0x18001df7e  mov     rdi, rdx
0x18001df81  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001df86  test    al, al
0x18001df88  jz      short loc_18001DFAD
0x18001df8a  mov     rcx, [rsp+48h]; this
0x18001df8f  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001df96  mov     ebx, 8067000Bh
0x18001df9b  mov     edx, 2FDh; void *
0x18001dfa0  mov     r9d, ebx; char *
0x18001dfa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dfa8  jmp     loc_18001E0B7
0x18001dfad  lea     r8, [rsp+48h+arg_0]; struct StateRepository::Statement *
0x18001dfb2  mov     [rsp+48h+arg_0], 0
0x18001dfbb  lea     rdx, aUpdateApplicat_3; "UPDATE ApplicationExtension SET Activat"...
0x18001dfc2  mov     rcx, rdi; this
0x18001dfc5  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18001dfca  mov     ebx, eax
0x18001dfcc  test    eax, eax
0x18001dfce  jns     short loc_18001DFD7
0x18001dfd0  mov     edx, 301h
0x18001dfd5  jmp     short loc_18001DFF4
0x18001dfd7  mov     r8, rsi; __int64
0x18001dfda  lea     rcx, [rsp+48h+arg_0]; this
0x18001dfdf  mov     edx, 1; int
0x18001dfe4  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001dfe9  mov     ebx, eax
0x18001dfeb  test    eax, eax
0x18001dfed  jns     short loc_18001E00D
0x18001dfef  mov     edx, 302h; void *
0x18001dff4  mov     r9d, eax; char *
0x18001dff7  mov     rcx, [rsp+48h]; this
0x18001dffc  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001e003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e008  jmp     loc_18001E0AD
0x18001e00d  mov     r8, rbp; __int64
0x18001e010  lea     rcx, [rsp+48h+arg_0]; this
0x18001e015  mov     edx, 2; int
0x18001e01a  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001e01f  mov     ebx, eax
0x18001e021  test    eax, eax
0x18001e023  jns     short loc_18001E02C
0x18001e025  mov     edx, 303h
0x18001e02a  jmp     short loc_18001DFF4
0x18001e02c  mov     r8, [rdi+8]; __int64
0x18001e030  lea     rcx, [rsp+48h+arg_0]; this
0x18001e035  mov     edx, 3; int
0x18001e03a  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001e03f  mov     ebx, eax
0x18001e041  test    eax, eax
0x18001e043  jns     short loc_18001E04C
0x18001e045  mov     edx, 304h
0x18001e04a  jmp     short loc_18001DFF4
0x18001e04c  lea     rcx, [rsp+48h+arg_0]; this
0x18001e051  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x18001e056  mov     ebx, eax
0x18001e058  test    eax, eax
0x18001e05a  jns     short loc_18001E063
0x18001e05c  mov     edx, 306h
0x18001e061  jmp     short loc_18001DFF4
0x18001e063  lea     rdx, [rsp+48h+arg_0]; struct StateRepository::Statement *
0x18001e068  mov     rcx, rdi; this
0x18001e06b  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18001e070  test    eax, eax
0x18001e072  jns     short loc_18001E08D
0x18001e074  mov     rcx, [rsp+48h]; this
0x18001e079  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001e080  mov     r9d, eax; char *
0x18001e083  mov     edx, 308h; void *
0x18001e088  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e08d  mov     rcx, rdi; this
0x18001e090  call    ?GetChanges@Database@StateRepository@@QEBAHXZ; StateRepository::Database::GetChanges(void)
0x18001e095  test    eax, eax
0x18001e097  jnz     short loc_18001E0AB
0x18001e099  mov     ebx, 80070490h
0x18001e09e  mov     edx, 30Ah
0x18001e0a3  mov     r9d, ebx
0x18001e0a6  jmp     loc_18001DFF7
0x18001e0ab  xor     ebx, ebx
0x18001e0ad  lea     rcx, [rsp+48h+arg_0]; this
0x18001e0b2  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18001e0b7  mov     eax, ebx
0x18001e0b9  add     rsp, 28h
0x18001e0bd  pop     rdi
0x18001e0be  pop     rsi
0x18001e0bf  pop     rbp
0x18001e0c0  pop     rbx
0x18001e0c1  retn
```
