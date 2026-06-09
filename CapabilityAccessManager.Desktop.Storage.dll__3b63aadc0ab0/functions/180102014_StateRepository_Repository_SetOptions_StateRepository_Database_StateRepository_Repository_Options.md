# StateRepository::Repository::SetOptions(StateRepository::Database &,StateRepository::Repository::Options)

- ea: `0x180102014`
- end: `0x18010225c`
- name: `?SetOptions@Repository@StateRepository@@CAJAEAVDatabase@2@W4Options@12@@Z`
- size: `584`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1801019b8`

## callees

- `0x180002594`
- `0x18000ed50`
- `0x180011c10`
- `0x1800eabf4`
- `0x1800f7630`
- `0x1800fbb98`
- `0x1800fbbf8`
- `0x1800fbc58`
- `0x1800fbed8`
- `0x180101ee0`
- `0x180102014`
- `0x180104c64`

## string_xrefs

- `0x1801020e8`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180102043`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x18010209a`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x18010212b`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180102175`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x1801021b4`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Repository::SetOptions(unsigned int *a1, int a2)
{
  signed int busy; // ebx
  __int64 v5; // rdx
  __int64 v7; // rdx
  int v8; // edx
  unsigned int v9; // edx
  int v10; // ecx
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // esi
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rbx
  __int64 v20; // rcx
  const char *v21; // rax
  int v22; // [rsp+20h] [rbp-38h]
  const char *v23; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v25; // [rsp+70h] [rbp+18h] BYREF
  __int64 v26; // [rsp+78h] [rbp+20h] BYREF

  busy = StateRepository::Database::SetBusyTimeout((StateRepository::Database *)a1, dword_18013F938);
  if ( busy < 0 )
  {
    v5 = 1714;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)busy,
      v22);
    return (unsigned int)busy;
  }
  if ( (a2 & 0x60000) == 0x60000 )
  {
    busy = -2147024809;
    v7 = 1750;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)busy,
      v22);
    v5 = 1717;
    goto LABEL_3;
  }
  v8 = 0x20000;
  if ( (a2 & 0x60000) != 0 )
    v8 = a2;
  busy = StateRepository::Database::SetCheckpointOnClose((StateRepository::Database *)a1, (v8 & 0x20000) != 0);
  if ( busy < 0 )
  {
    v7 = 1756;
    goto LABEL_10;
  }
  busy = StateRepository::Database::SetAutoCheckpointPages((StateRepository::Database *)a1, v9);
  if ( busy < 0 )
  {
    v5 = 1718;
    goto LABEL_3;
  }
  v10 = *(_DWORD *)(StateRepository::Globals::PartitionSettings::Get(a1[4]) + 16);
  if ( v10 )
  {
    v25 = v10;
    if ( !*(_QWORD *)a1 )
    {
      busy = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x799,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)0x8007139FLL,
        v22);
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D2,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)busy,
        v22);
      v5 = 1721;
      goto LABEL_3;
    }
    v11 = sqlite3_file_control(*(_QWORD *)a1, 0, 6, &v25);
    busy = v11;
    if ( v11 > 0 )
      busy = (unsigned __int16)v11 | 0x87AF0000;
    if ( busy < 0 )
      goto LABEL_19;
  }
  v12 = StateRepository::Globals::PartitionSettings::Get(a1[4]);
  if ( *(_DWORD *)(v12 + 20) )
  {
    v14 = StateRepository::Database::SetPragma(
            (StateRepository::Database *)a1,
            "journal_size_limit",
            *(int *)(v12 + 20));
    busy = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E1,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v14,
        v22);
      v5 = 1724;
      goto LABEL_3;
    }
  }
  if ( (a2 & 0x800) == 0 )
  {
    v15 = StateRepository::Repository::SetCacheSize(v13, a1);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6C1,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v15);
      v19 = qword_1801403A0;
      if ( *(_DWORD *)qword_1801403A0 > 3u
        && (*(_QWORD *)(qword_1801403A0 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1801403A0 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1801403A0 + 24) )
      {
        v20 = *(_QWORD *)a1;
        v26 = 0x1000000;
        if ( v20 )
          v21 = (const char *)sqlite3_db_filename(v20, 0);
        else
          v21 = 0;
        v23 = v21;
        v25 = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v19,
          (__int64)&word_18012A1BE,
          v17,
          v18,
          (__int64)&v25,
          &v23,
          (__int64)&v26);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180102014  mov     [rsp+arg_0], rbx
0x180102019  mov     [rsp+arg_8], rsi
0x18010201e  push    rdi
0x18010201f  sub     rsp, 50h
0x180102023  mov     esi, edx
0x180102025  mov     rdi, rcx
0x180102028  mov     edx, cs:dword_18013F938; int
0x18010202e  call    ?SetBusyTimeout@Database@StateRepository@@QEAAJH@Z; StateRepository::Database::SetBusyTimeout(int)
0x180102033  mov     ebx, eax
0x180102035  test    eax, eax
0x180102037  jns     short loc_180102059
0x180102039  mov     edx, 6B2h; void *
0x18010203e  mov     rcx, [rsp+58h]; this
0x180102043  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x18010204a  mov     r9d, ebx; char *
0x18010204d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102052  mov     eax, ebx
0x180102054  jmp     loc_18010224C
0x180102059  mov     ecx, 60000h
0x18010205e  mov     eax, esi
0x180102060  and     eax, ecx
0x180102062  cmp     eax, ecx
0x180102064  jnz     short loc_180102072
0x180102066  mov     ebx, 80070057h
0x18010206b  mov     edx, 6D6h
0x180102070  jmp     short loc_180102095
0x180102072  test    eax, eax
0x180102074  mov     edx, 20000h
0x180102079  mov     rcx, rdi; this
0x18010207c  cmovnz  edx, esi
0x18010207f  shr     edx, 11h
0x180102082  and     dl, 1; bool
0x180102085  call    ?SetCheckpointOnClose@Database@StateRepository@@QEAAJ_N@Z; StateRepository::Database::SetCheckpointOnClose(bool)
0x18010208a  mov     ebx, eax
0x18010208c  test    eax, eax
0x18010208e  jns     short loc_1801020B0
0x180102090  mov     edx, 6DCh; void *
0x180102095  mov     rcx, [rsp+58h]; this
0x18010209a  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x1801020a1  mov     r9d, ebx; char *
0x1801020a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801020a9  mov     edx, 6B5h
0x1801020ae  jmp     short loc_18010203E
0x1801020b0  mov     rcx, rdi; this
0x1801020b3  call    ?SetAutoCheckpointPages@Database@StateRepository@@QEAAJI@Z; StateRepository::Database::SetAutoCheckpointPages(uint)
0x1801020b8  mov     ebx, eax
0x1801020ba  test    eax, eax
0x1801020bc  jns     short loc_1801020C8
0x1801020be  mov     edx, 6B6h
0x1801020c3  jmp     loc_18010203E
0x1801020c8  mov     ecx, [rdi+10h]
0x1801020cb  call    ?Get@PartitionSettings@Globals@StateRepository@@SAPEBU123@W4Partition@3@@Z; StateRepository::Globals::PartitionSettings::Get(StateRepository::Partition)
0x1801020d0  mov     ecx, [rax+10h]
0x1801020d3  test    ecx, ecx
0x1801020d5  jz      short loc_180102149
0x1801020d7  mov     [rsp+58h+arg_10], ecx
0x1801020db  mov     rcx, [rdi]
0x1801020de  test    rcx, rcx
0x1801020e1  jnz     short loc_180102103
0x1801020e3  mov     rcx, [rsp+58h]; this
0x1801020e8  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1801020ef  mov     ebx, 8007139Fh
0x1801020f4  mov     edx, 799h; void *
0x1801020f9  mov     r9d, ebx; char *
0x1801020fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102101  jmp     short loc_180102126
0x180102103  xor     edx, edx
0x180102105  lea     r9, [rsp+58h+arg_10]
0x18010210a  lea     r8d, [rdx+6]
0x18010210e  call    sqlite3_file_control
0x180102113  mov     ebx, eax
0x180102115  test    eax, eax
0x180102117  jle     short loc_180102122
0x180102119  movzx   ebx, ax
0x18010211c  or      ebx, 87AF0000h
0x180102122  test    ebx, ebx
0x180102124  jns     short loc_180102149
0x180102126  mov     rcx, [rsp+58h]; this
0x18010212b  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180102132  mov     r9d, ebx; char *
0x180102135  mov     edx, 5D2h; void *
0x18010213a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010213f  mov     edx, 6B9h
0x180102144  jmp     loc_18010203E
0x180102149  mov     ecx, [rdi+10h]
0x18010214c  call    ?Get@PartitionSettings@Globals@StateRepository@@SAPEBU123@W4Partition@3@@Z; StateRepository::Globals::PartitionSettings::Get(StateRepository::Partition)
0x180102151  cmp     dword ptr [rax+14h], 0
0x180102155  jz      short loc_180102193
0x180102157  movsxd  r8, dword ptr [rax+14h]; __int64
0x18010215b  lea     rdx, aJournalSizeLim; "journal_size_limit"
0x180102162  mov     rcx, rdi; this
0x180102165  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD_J@Z; StateRepository::Database::SetPragma(char const *,__int64)
0x18010216a  mov     ebx, eax
0x18010216c  test    eax, eax
0x18010216e  jns     short loc_180102193
0x180102170  mov     rcx, [rsp+58h]; this
0x180102175  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x18010217c  mov     r9d, eax; char *
0x18010217f  mov     edx, 5E1h; void *
0x180102184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180102189  mov     edx, 6BCh
0x18010218e  jmp     loc_18010203E
0x180102193  bt      esi, 0Bh
0x180102197  jb      loc_18010224A
0x18010219d  mov     rdx, rdi
0x1801021a0  call    ?SetCacheSize@Repository@StateRepository@@CAJW4Options@12@AEAVDatabase@2@@Z; StateRepository::Repository::SetCacheSize(StateRepository::Repository::Options,StateRepository::Database &)
0x1801021a5  mov     esi, eax
0x1801021a7  test    eax, eax
0x1801021a9  jns     loc_18010224A
0x1801021af  mov     rcx, [rsp+58h]; this
0x1801021b4  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x1801021bb  mov     r9d, eax; char *
0x1801021be  mov     edx, 6C1h; void *
0x1801021c3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801021c8  mov     rbx, cs:qword_1801403A0
0x1801021cf  mov     ecx, [rbx]
0x1801021d1  cmp     ecx, 3
0x1801021d4  jbe     short loc_18010224A
0x1801021d6  mov     rcx, [rbx+18h]
0x1801021da  mov     rdx, 200000000000h
0x1801021e4  mov     rax, [rbx+10h]
0x1801021e8  test    rdx, rax
0x1801021eb  jz      short loc_18010224A
0x1801021ed  mov     rax, rcx
0x1801021f0  and     rax, rdx
0x1801021f3  cmp     rax, rcx
0x1801021f6  jnz     short loc_18010224A
0x1801021f8  mov     rcx, [rdi]
0x1801021fb  mov     [rsp+58h+arg_18], 1000000h
0x180102204  test    rcx, rcx
0x180102207  jz      short loc_180102212
0x180102209  xor     edx, edx
0x18010220b  call    sqlite3_db_filename
0x180102210  jmp     short loc_180102214
0x180102212  xor     eax, eax
0x180102214  mov     [rsp+58h+var_18], rax
0x180102219  lea     rdx, word_18012A1BE
0x180102220  lea     rax, [rsp+58h+arg_18]
0x180102225  mov     [rsp+58h+arg_10], esi
0x180102229  mov     [rsp+58h+var_28], rax
0x18010222e  mov     rcx, rbx
0x180102231  lea     rax, [rsp+58h+var_18]
0x180102236  mov     [rsp+58h+var_30], rax
0x18010223b  lea     rax, [rsp+58h+arg_10]
0x180102240  mov     [rsp+58h+var_38], rax
0x180102245  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18010224a  xor     eax, eax
0x18010224c  mov     rbx, [rsp+58h+arg_0]
0x180102251  mov     rsi, [rsp+58h+arg_8]
0x180102256  add     rsp, 50h
0x18010225a  pop     rdi
0x18010225b  retn
```
