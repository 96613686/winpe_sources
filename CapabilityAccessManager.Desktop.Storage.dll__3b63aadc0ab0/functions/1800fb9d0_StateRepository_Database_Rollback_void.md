# StateRepository::Database::Rollback(void)

- ea: `0x1800fb9d0`
- end: `0x1800fbb91`
- name: `?Rollback@Database@StateRepository@@QEAAJXZ`
- size: `449`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800f7130`

## callees

- `0x1800017e4`
- `0x180003060`
- `0x18000ed50`
- `0x1800eabf4`
- `0x1800edb2c`
- `0x1800f9300`
- `0x1800f94fc`
- `0x1800fb9d0`
- `0x1800fc9e8`
- `0x180104690`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800fba7b`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800fba7b`

## string_xrefs

- `0x1800fba54`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fbb7c`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fba11`: `ROLLBACK /*%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X*/;`
- `0x1800fbaa7`: `BEGIN -> ROLLBACK;`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::Rollback(StateRepository::Database *this, __int64 a2)
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
  v4 = StateRepository::Database::FormatSql(
         v23,
         a2,
         "ROLLBACK /*%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X*/;",
         v2);
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x291,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v4,
      v17);
  StateRepository::Database::VerifyResourcePriorities(this, v2, v23);
  v7 = StateRepository::Database::Execute(this, (struct sqlite3 *)v23, v5, v6);
  v8 = v7;
  if ( v7 >= 0 )
  {
    UnbiasedTime = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    v12 = UnbiasedTime / 0x2710 - *((_QWORD *)this + 3);
    if ( *((_BYTE *)this + 36) )
      StateRepository::Logging::sqliteProfileCallback(0, "BEGIN -> ROLLBACK;", (const char *)(1000000 * v12), v11);
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
        (__int64)&byte_18012A07F,
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
      (void *)0x295,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v7,
      v17);
    return v8;
  }
}

```

## disassembly

```asm
0x1800fb9d0  mov     [rsp-8+arg_8], rbx
0x1800fb9d5  mov     [rsp-8+arg_10], rsi
0x1800fb9da  push    rbp
0x1800fb9db  push    rdi
0x1800fb9dc  push    r14
0x1800fb9de  lea     rbp, [rsp-47h]
0x1800fb9e3  sub     rsp, 0C0h
0x1800fb9ea  mov     rax, cs:__security_cookie
0x1800fb9f1  xor     rax, rsp
0x1800fb9f4  mov     [rbp+57h+var_20], rax
0x1800fb9f8  movsxd  rax, dword ptr [rcx+10h]
0x1800fb9fc  lea     r14, cs:180000000h
0x1800fba03  shl     rax, 4
0x1800fba07  lea     rsi, rva xmmword_180140340[r14]
0x1800fba0e  add     rsi, rax
0x1800fba11  lea     r8, aRollback08x04x; "ROLLBACK /*%08X-%04X-%04X-%02X%02X-%02X"...
0x1800fba18  mov     rdi, rcx
0x1800fba1b  mov     r9, rsi; struct _GUID *
0x1800fba1e  lea     rcx, [rbp+57h+var_60]; char *
0x1800fba22  call    ?FormatSql@Database@StateRepository@@CAJPEAD_KPEBDAEBU_GUID@@@Z; StateRepository::Database::FormatSql(char *,unsigned __int64,char const *,_GUID const &)
0x1800fba27  test    eax, eax
0x1800fba29  js      loc_1800FBB78
0x1800fba2f  lea     r8, [rbp+57h+var_60]; char *
0x1800fba33  mov     rdx, rsi; struct _GUID *
0x1800fba36  mov     rcx, rdi; this
0x1800fba39  call    ?VerifyResourcePriorities@Database@StateRepository@@AEAAXAEBU_GUID@@PEBD@Z; StateRepository::Database::VerifyResourcePriorities(_GUID const &,char const *)
0x1800fba3e  lea     rdx, [rbp+57h+var_60]; char *
0x1800fba42  mov     rcx, rdi; this
0x1800fba45  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800fba4a  mov     ebx, eax
0x1800fba4c  test    eax, eax
0x1800fba4e  jns     short loc_1800FBA6F
0x1800fba50  mov     rcx, [rbp+5Fh]; this
0x1800fba54  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fba5b  mov     r9d, eax; char *
0x1800fba5e  mov     edx, 295h; void *
0x1800fba63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fba68  mov     eax, ebx
0x1800fba6a  jmp     loc_1800FBB54
0x1800fba6f  lea     rcx, [rbp+57h+UnbiasedTime]; UnbiasedTime
0x1800fba73  mov     [rbp+57h+UnbiasedTime], 0
0x1800fba7b  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800fba81  mov     rax, 346DC5D63886594Bh
0x1800fba8b  mul     [rbp+57h+UnbiasedTime]
0x1800fba8f  mov     rbx, rdx
0x1800fba92  shr     rbx, 0Bh
0x1800fba96  sub     rbx, [rdi+18h]
0x1800fba9a  cmp     byte ptr [rdi+24h], 0
0x1800fba9e  jz      short loc_1800FBAB5
0x1800fbaa0  imul    r8, rbx, 0F4240h; char *
0x1800fbaa7  lea     rdx, aBeginRollback; "BEGIN -> ROLLBACK;"
0x1800fbaae  xor     ecx, ecx; this
0x1800fbab0  call    ?sqliteProfileCallback@Logging@StateRepository@@YAXPEAXPEBD_K@Z; StateRepository::Logging::sqliteProfileCallback(void *,char const *,unsigned __int64)
0x1800fbab5  movsxd  rax, dword ptr [rdi+10h]
0x1800fbab9  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800fbac0  add     rax, rax
0x1800fbac3  movdqu  rva xmmword_180140340[r14+rax*8], xmm0
0x1800fbacd  movsxd  rax, dword ptr [rdi+10h]
0x1800fbad1  mov     rva dword_180140320[r14+rax*4], 0
0x1800fbadd  mov     rva qword_1801402F0[r14+rax*8], 0
0x1800fbae9  mov     r14, cs:qword_1801402E8
0x1800fbaf0  mov     eax, [r14]
0x1800fbaf3  cmp     eax, 5
0x1800fbaf6  jbe     short loc_1800FBB52
0x1800fbaf8  mov     rcx, [rdi]
0x1800fbafb  mov     [rbp+57h+var_88], 1000000h
0x1800fbb03  mov     [rbp+57h+var_80], rbx
0x1800fbb07  mov     [rbp+57h+var_78], rsi
0x1800fbb0b  test    rcx, rcx
0x1800fbb0e  jz      short loc_1800FBB19
0x1800fbb10  xor     edx, edx
0x1800fbb12  call    sqlite3_db_filename
0x1800fbb17  jmp     short loc_1800FBB1B
0x1800fbb19  xor     eax, eax
0x1800fbb1b  mov     [rbp+57h+var_70], rax
0x1800fbb1f  lea     rdx, byte_18012A07F
0x1800fbb26  lea     rax, [rbp+57h+var_88]
0x1800fbb2a  mov     rcx, r14
0x1800fbb2d  mov     [rsp+0D0h+var_98], rax
0x1800fbb32  lea     rax, [rbp+57h+var_80]
0x1800fbb36  mov     [rsp+0D0h+var_A0], rax
0x1800fbb3b  lea     rax, [rbp+57h+var_78]
0x1800fbb3f  mov     [rsp+0D0h+var_A8], rax
0x1800fbb44  lea     rax, [rbp+57h+var_70]
0x1800fbb48  mov     [rsp+0D0h+var_B0], rax
0x1800fbb4d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800fbb52  xor     eax, eax
0x1800fbb54  mov     rcx, [rbp+57h+var_20]
0x1800fbb58  xor     rcx, rsp; StackCookie
0x1800fbb5b  call    __security_check_cookie
0x1800fbb60  lea     r11, [rsp+0D0h+var_10]
0x1800fbb68  mov     rbx, [r11+28h]
0x1800fbb6c  mov     rsi, [r11+30h]
0x1800fbb70  mov     rsp, r11
0x1800fbb73  pop     r14
0x1800fbb75  pop     rdi
0x1800fbb76  pop     rbp
0x1800fbb77  retn
0x1800fbb78  mov     rcx, [rbp+5Fh]; this
0x1800fbb7c  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fbb83  mov     r9d, eax; char *
0x1800fbb86  mov     edx, 291h; void *
0x1800fbb8b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
