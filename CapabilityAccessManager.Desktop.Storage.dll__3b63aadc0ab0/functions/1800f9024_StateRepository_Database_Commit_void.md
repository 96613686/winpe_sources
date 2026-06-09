# StateRepository::Database::Commit(void)

- ea: `0x1800f9024`
- end: `0x1800f91e5`
- name: `?Commit@Database@StateRepository@@QEAAJXZ`
- size: `449`
- prototype: `__int64 __fastcall(StateRepository::Database *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800f73fc`

## callees

- `0x1800017e4`
- `0x180003060`
- `0x18000ed50`
- `0x1800eabf4`
- `0x1800edb2c`
- `0x1800f9024`
- `0x1800f9300`
- `0x1800f94fc`
- `0x1800fc9e8`
- `0x180104690`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800f90cf`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800f90cf`

## string_xrefs

- `0x1800f90a8`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f91d0`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f9065`: `COMMIT /*%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X*/;`
- `0x1800f90fb`: `BEGIN -> COMMIT;`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::Commit(StateRepository::Database *this, unsigned __int64 a2)
{
  const struct _GUID *v2; // rsi
  int v4; // eax
  int (*v5)(void *); // r8
  void *v6; // r9
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v10; // r8
  unsigned __int64 v11; // r9
  unsigned __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // r14
  __int64 v15; // rcx
  const char *v16; // rax
  int v17; // [rsp+20h] [rbp-59h]
  unsigned __int64 UnbiasedTime; // [rsp+40h] [rbp-39h] BYREF
  __int64 v19; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-29h] BYREF
  const struct _GUID *v21; // [rsp+58h] [rbp-21h] BYREF
  const char *v22; // [rsp+60h] [rbp-19h] BYREF
  char v23[64]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = (const struct _GUID *)&xmmword_180140340[*((int *)this + 4)];
  v4 = StateRepository::Database::FormatSql(v23, a2, "COMMIT /*%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X*/;", v2);
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x275,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v4,
      v17);
  StateRepository::Database::VerifyResourcePriorities(this, v2, v23);
  v7 = StateRepository::Database::Execute(this, v23, v5, v6);
  v8 = v7;
  if ( v7 >= 0 )
  {
    UnbiasedTime = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    v12 = UnbiasedTime / 0x2710 - *((_QWORD *)this + 3);
    if ( *((_BYTE *)this + 36) )
      StateRepository::Logging::sqliteProfileCallback(0, "BEGIN -> COMMIT;", (const char *)(1000000 * v12), v11);
    xmmword_180140340[*((int *)this + 4)] = (__int128)GUID_00000000_0000_0000_0000_000000000000;
    v13 = *((int *)this + 4);
    dword_180140320[v13] = 0;
    qword_1801402F0[v13] = 0;
    v14 = qword_1801402E8;
    if ( *(_DWORD *)qword_1801402E8 > 5u )
    {
      v15 = *(_QWORD *)this;
      v19 = 0x1000000;
      v20 = v12;
      v21 = v2;
      if ( v15 )
        v16 = (const char *)sqlite3_db_filename(v15, 0);
      else
        v16 = 0;
      v22 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v14,
        (__int64)&unk_18012A0E8,
        v10,
        v11,
        &v22,
        (__int64 *)&v21,
        (__int64)&v20,
        (__int64)&v19);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v7,
      v17);
    return v8;
  }
}

```

## disassembly

```asm
0x1800f9024  mov     [rsp-8+arg_8], rbx
0x1800f9029  mov     [rsp-8+arg_10], rsi
0x1800f902e  push    rbp
0x1800f902f  push    rdi
0x1800f9030  push    r14
0x1800f9032  lea     rbp, [rsp-47h]
0x1800f9037  sub     rsp, 0C0h
0x1800f903e  mov     rax, cs:__security_cookie
0x1800f9045  xor     rax, rsp
0x1800f9048  mov     [rbp+57h+var_20], rax
0x1800f904c  movsxd  rax, dword ptr [rcx+10h]
0x1800f9050  lea     r14, cs:180000000h
0x1800f9057  shl     rax, 4
0x1800f905b  lea     rsi, rva xmmword_180140340[r14]
0x1800f9062  add     rsi, rax
0x1800f9065  lea     r8, aCommit08x04x04; "COMMIT /*%08X-%04X-%04X-%02X%02X-%02X%0"...
0x1800f906c  mov     rdi, rcx
0x1800f906f  mov     r9, rsi; struct _GUID *
0x1800f9072  lea     rcx, [rbp+57h+var_60]; char *
0x1800f9076  call    ?FormatSql@Database@StateRepository@@CAJPEAD_KPEBDAEBU_GUID@@@Z; StateRepository::Database::FormatSql(char *,unsigned __int64,char const *,_GUID const &)
0x1800f907b  test    eax, eax
0x1800f907d  js      loc_1800F91CC
0x1800f9083  lea     r8, [rbp+57h+var_60]; char *
0x1800f9087  mov     rdx, rsi; struct _GUID *
0x1800f908a  mov     rcx, rdi; this
0x1800f908d  call    ?VerifyResourcePriorities@Database@StateRepository@@AEAAXAEBU_GUID@@PEBD@Z; StateRepository::Database::VerifyResourcePriorities(_GUID const &,char const *)
0x1800f9092  lea     rdx, [rbp+57h+var_60]; char *
0x1800f9096  mov     rcx, rdi; this
0x1800f9099  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800f909e  mov     ebx, eax
0x1800f90a0  test    eax, eax
0x1800f90a2  jns     short loc_1800F90C3
0x1800f90a4  mov     rcx, [rbp+5Fh]; this
0x1800f90a8  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f90af  mov     r9d, eax; char *
0x1800f90b2  mov     edx, 279h; void *
0x1800f90b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f90bc  mov     eax, ebx
0x1800f90be  jmp     loc_1800F91A8
0x1800f90c3  lea     rcx, [rbp+57h+UnbiasedTime]; UnbiasedTime
0x1800f90c7  mov     [rbp+57h+UnbiasedTime], 0
0x1800f90cf  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800f90d5  mov     rax, 346DC5D63886594Bh
0x1800f90df  mul     [rbp+57h+UnbiasedTime]
0x1800f90e3  mov     rbx, rdx
0x1800f90e6  shr     rbx, 0Bh
0x1800f90ea  sub     rbx, [rdi+18h]
0x1800f90ee  cmp     byte ptr [rdi+24h], 0
0x1800f90f2  jz      short loc_1800F9109
0x1800f90f4  imul    r8, rbx, 0F4240h; char *
0x1800f90fb  lea     rdx, aBeginCommit; "BEGIN -> COMMIT;"
0x1800f9102  xor     ecx, ecx; this
0x1800f9104  call    ?sqliteProfileCallback@Logging@StateRepository@@YAXPEAXPEBD_K@Z; StateRepository::Logging::sqliteProfileCallback(void *,char const *,unsigned __int64)
0x1800f9109  movsxd  rax, dword ptr [rdi+10h]
0x1800f910d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800f9114  add     rax, rax
0x1800f9117  movdqu  rva xmmword_180140340[r14+rax*8], xmm0
0x1800f9121  movsxd  rax, dword ptr [rdi+10h]
0x1800f9125  mov     rva dword_180140320[r14+rax*4], 0
0x1800f9131  mov     rva qword_1801402F0[r14+rax*8], 0
0x1800f913d  mov     r14, cs:qword_1801402E8
0x1800f9144  mov     eax, [r14]
0x1800f9147  cmp     eax, 5
0x1800f914a  jbe     short loc_1800F91A6
0x1800f914c  mov     rcx, [rdi]
0x1800f914f  mov     [rbp+57h+var_88], 1000000h
0x1800f9157  mov     [rbp+57h+var_80], rbx
0x1800f915b  mov     [rbp+57h+var_78], rsi
0x1800f915f  test    rcx, rcx
0x1800f9162  jz      short loc_1800F916D
0x1800f9164  xor     edx, edx
0x1800f9166  call    sqlite3_db_filename
0x1800f916b  jmp     short loc_1800F916F
0x1800f916d  xor     eax, eax
0x1800f916f  mov     [rbp+57h+var_70], rax
0x1800f9173  lea     rdx, unk_18012A0E8
0x1800f917a  lea     rax, [rbp+57h+var_88]
0x1800f917e  mov     rcx, r14
0x1800f9181  mov     [rsp+0D0h+var_98], rax
0x1800f9186  lea     rax, [rbp+57h+var_80]
0x1800f918a  mov     [rsp+0D0h+var_A0], rax
0x1800f918f  lea     rax, [rbp+57h+var_78]
0x1800f9193  mov     [rsp+0D0h+var_A8], rax
0x1800f9198  lea     rax, [rbp+57h+var_70]
0x1800f919c  mov     [rsp+0D0h+var_B0], rax
0x1800f91a1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800f91a6  xor     eax, eax
0x1800f91a8  mov     rcx, [rbp+57h+var_20]
0x1800f91ac  xor     rcx, rsp; StackCookie
0x1800f91af  call    __security_check_cookie
0x1800f91b4  lea     r11, [rsp+0D0h+var_10]
0x1800f91bc  mov     rbx, [r11+28h]
0x1800f91c0  mov     rsi, [r11+30h]
0x1800f91c4  mov     rsp, r11
0x1800f91c7  pop     r14
0x1800f91c9  pop     rdi
0x1800f91ca  pop     rbp
0x1800f91cb  retn
0x1800f91cc  mov     rcx, [rbp+5Fh]; this
0x1800f91d0  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f91d7  mov     r9d, eax; char *
0x1800f91da  mov     edx, 275h; void *
0x1800f91df  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
