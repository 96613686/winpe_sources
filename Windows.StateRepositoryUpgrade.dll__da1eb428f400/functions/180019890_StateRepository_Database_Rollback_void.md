# StateRepository::Database::Rollback(void)

- ea: `0x180019890`
- end: `0x180019a3c`
- name: `?Rollback@Database@StateRepository@@QEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18000b964`

## callees

- `0x1800024e0`
- `0x180003980`
- `0x18000a3c0`
- `0x180014ca0`
- `0x180015204`
- `0x180018c40`
- `0x180018d50`
- `0x180018e80`
- `0x1800196c0`
- `0x180019890`
- `0x180019c28`

## string_xrefs

- `0x180019920`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180019a27`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800198d0`: `ROLLBACK /*%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X*/;`
- `0x180019947`: `BEGIN -> ROLLBACK;`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::Rollback(StateRepository::Database *this, unsigned __int64 a2)
{
  const struct _GUID *v2; // rsi
  int v4; // eax
  int v5; // eax
  StateRepository::Time *v6; // rcx
  unsigned int v7; // ebx
  __int64 v9; // rbx
  unsigned __int64 v10; // rbp
  unsigned int *v11; // rbx
  const char *v12; // rdx
  unsigned int v13; // eax
  int v14; // r8d
  int v15; // r9d
  int v16; // [rsp+20h] [rbp-A8h]
  __int64 v17; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 v18; // [rsp+48h] [rbp-80h] BYREF
  const struct _GUID *v19; // [rsp+50h] [rbp-78h] BYREF
  const char *Filename; // [rsp+58h] [rbp-70h] BYREF
  char v21[64]; // [rsp+60h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v2 = (const struct _GUID *)&xmmword_18004BE50[*((int *)this + 4)];
  v4 = StateRepository::Database::FormatSql(
         v21,
         a2,
         "ROLLBACK /*%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X*/;",
         v2);
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x291,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v4,
      v16);
  StateRepository::Database::VerifyResourcePriorities(this, v2, v21);
  v5 = StateRepository::Database::Execute(this, v21, 0, 0);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v9 = *((_QWORD *)this + 3);
    v10 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v6) - v9;
    StateRepository::Database::Profile(this, "BEGIN -> ROLLBACK;", v10);
    v11 = (unsigned int *)qword_18004BDF0;
    xmmword_18004BE50[*((int *)this + 4)] = (__int128)GUID_00000000_0000_0000_0000_000000000000;
    v12 = (const char *)*((int *)this + 4);
    v13 = *v11;
    dword_18004BE30[(_QWORD)v12] = 0;
    qword_18004BE00[(_QWORD)v12] = 0;
    if ( v13 > 5 )
    {
      v17 = 0x1000000;
      v18 = v10;
      v19 = v2;
      Filename = StateRepository::Database::GetFilename(this, v12);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        (_DWORD)v11,
        (unsigned int)&unk_1800458C8,
        v14,
        v15,
        (__int64)&Filename,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v17);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x295,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v5,
      v16);
    return v7;
  }
}

```

## disassembly

```asm
0x180019890  mov     [rsp+arg_8], rbx
0x180019895  mov     [rsp+arg_10], rbp
0x18001989a  push    rsi
0x18001989b  push    rdi
0x18001989c  push    r14
0x18001989e  sub     rsp, 0B0h
0x1800198a5  mov     rax, cs:__security_cookie
0x1800198ac  xor     rax, rsp
0x1800198af  mov     [rsp+0C8h+var_28], rax
0x1800198b7  movsxd  rax, dword ptr [rcx+10h]
0x1800198bb  lea     r14, __ImageBase
0x1800198c2  shl     rax, 4
0x1800198c6  lea     rsi, rva xmmword_18004BE50[r14]
0x1800198cd  add     rsi, rax
0x1800198d0  lea     r8, aRollback08x04x; "ROLLBACK /*%08X-%04X-%04X-%02X%02X-%02X"...
0x1800198d7  mov     rdi, rcx
0x1800198da  mov     r9, rsi; struct _GUID *
0x1800198dd  lea     rcx, [rsp+0C8h+var_68]; char *
0x1800198e2  call    ?FormatSql@Database@StateRepository@@CAJPEAD_KPEBDAEBU_GUID@@@Z; StateRepository::Database::FormatSql(char *,unsigned __int64,char const *,_GUID const &)
0x1800198e7  test    eax, eax
0x1800198e9  js      loc_180019A1F
0x1800198ef  lea     r8, [rsp+0C8h+var_68]; char *
0x1800198f4  mov     rdx, rsi; struct _GUID *
0x1800198f7  mov     rcx, rdi; this
0x1800198fa  call    ?VerifyResourcePriorities@Database@StateRepository@@AEAAXAEBU_GUID@@PEBD@Z; StateRepository::Database::VerifyResourcePriorities(_GUID const &,char const *)
0x1800198ff  xor     r9d, r9d; void *
0x180019902  lea     rdx, [rsp+0C8h+var_68]; char *
0x180019907  xor     r8d, r8d; int (*)(void *)
0x18001990a  mov     rcx, rdi; this
0x18001990d  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180019912  mov     ebx, eax
0x180019914  test    eax, eax
0x180019916  jns     short loc_18001993B
0x180019918  mov     rcx, [rsp+0C8h]; this
0x180019920  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180019927  mov     r9d, eax; char *
0x18001992a  mov     edx, 295h; void *
0x18001992f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019934  mov     eax, ebx
0x180019936  jmp     loc_1800199F7
0x18001993b  mov     rbx, [rdi+18h]
0x18001993f  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x180019944  mov     rbp, rax
0x180019947  lea     rdx, aBeginRollback; "BEGIN -> ROLLBACK;"
0x18001994e  sub     rbp, rbx
0x180019951  mov     rcx, rdi; this
0x180019954  mov     r8, rbp; unsigned __int64
0x180019957  call    ?Profile@Database@StateRepository@@AEBAXPEBD_K@Z; StateRepository::Database::Profile(char const *,unsigned __int64)
0x18001995c  movsxd  rcx, dword ptr [rdi+10h]
0x180019960  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180019967  mov     rbx, cs:qword_18004BDF0
0x18001996e  add     rcx, rcx
0x180019971  movdqu  rva xmmword_18004BE50[r14+rcx*8], xmm0
0x18001997b  movsxd  rdx, dword ptr [rdi+10h]; char *
0x18001997f  mov     eax, [rbx]
0x180019981  mov     rva dword_18004BE30[r14+rdx*4], 0
0x18001998d  mov     rva qword_18004BE00[r14+rdx*8], 0
0x180019999  cmp     eax, 5
0x18001999c  jbe     short loc_1800199F5
0x18001999e  mov     rcx, rdi; this
0x1800199a1  mov     [rsp+0C8h+var_88], 1000000h
0x1800199aa  mov     [rsp+0C8h+var_80], rbp
0x1800199af  mov     [rsp+0C8h+var_78], rsi
0x1800199b4  call    ?GetFilename@Database@StateRepository@@QEBAPEBDPEBD@Z; StateRepository::Database::GetFilename(char const *)
0x1800199b9  mov     [rsp+0C8h+var_70], rax
0x1800199be  lea     rdx, unk_1800458C8
0x1800199c5  lea     rax, [rsp+0C8h+var_88]
0x1800199ca  mov     rcx, rbx
0x1800199cd  mov     [rsp+0C8h+var_90], rax
0x1800199d2  lea     rax, [rsp+0C8h+var_80]
0x1800199d7  mov     [rsp+0C8h+var_98], rax
0x1800199dc  lea     rax, [rsp+0C8h+var_78]
0x1800199e1  mov     [rsp+0C8h+var_A0], rax
0x1800199e6  lea     rax, [rsp+0C8h+var_70]
0x1800199eb  mov     [rsp+0C8h+var_A8], rax
0x1800199f0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800199f5  xor     eax, eax
0x1800199f7  mov     rcx, [rsp+0C8h+var_28]
0x1800199ff  xor     rcx, rsp; StackCookie
0x180019a02  call    __security_check_cookie
0x180019a07  lea     r11, [rsp+0C8h+var_18]
0x180019a0f  mov     rbx, [r11+28h]
0x180019a13  mov     rbp, [r11+30h]
0x180019a17  mov     rsp, r11
0x180019a1a  pop     r14
0x180019a1c  pop     rdi
0x180019a1d  pop     rsi
0x180019a1e  retn
0x180019a1f  mov     rcx, [rsp+0C8h]; this
0x180019a27  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180019a2e  mov     r9d, eax; char *
0x180019a31  mov     edx, 291h; void *
0x180019a36  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
