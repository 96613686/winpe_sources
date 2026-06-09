# StateRepository::Database::Commit(void)

- ea: `0x180018934`
- end: `0x180018ae0`
- name: `?Commit@Database@StateRepository@@QEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000ba60`

## callees

- `0x1800024e0`
- `0x180003980`
- `0x18000a3c0`
- `0x180014ca0`
- `0x180015204`
- `0x180018934`
- `0x180018c40`
- `0x180018d50`
- `0x180018e80`
- `0x1800196c0`
- `0x180019c28`

## string_xrefs

- `0x1800189c4`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180018acb`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180018974`: `COMMIT /*%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X*/;`
- `0x1800189eb`: `BEGIN -> COMMIT;`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::Commit(StateRepository::Database *this, unsigned __int64 a2)
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
  v4 = StateRepository::Database::FormatSql(v21, a2, "COMMIT /*%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X*/;", v2);
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x275,
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
    StateRepository::Database::Profile(this, "BEGIN -> COMMIT;", v10);
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
        (unsigned int)byte_180045931,
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
      (void *)0x279,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v5,
      v16);
    return v7;
  }
}

```

## disassembly

```asm
0x180018934  mov     [rsp+arg_8], rbx
0x180018939  mov     [rsp+arg_10], rbp
0x18001893e  push    rsi
0x18001893f  push    rdi
0x180018940  push    r14
0x180018942  sub     rsp, 0B0h
0x180018949  mov     rax, cs:__security_cookie
0x180018950  xor     rax, rsp
0x180018953  mov     [rsp+0C8h+var_28], rax
0x18001895b  movsxd  rax, dword ptr [rcx+10h]
0x18001895f  lea     r14, __ImageBase
0x180018966  shl     rax, 4
0x18001896a  lea     rsi, rva xmmword_18004BE50[r14]
0x180018971  add     rsi, rax
0x180018974  lea     r8, aCommit08x04x04; "COMMIT /*%08X-%04X-%04X-%02X%02X-%02X%0"...
0x18001897b  mov     rdi, rcx
0x18001897e  mov     r9, rsi; struct _GUID *
0x180018981  lea     rcx, [rsp+0C8h+var_68]; char *
0x180018986  call    ?FormatSql@Database@StateRepository@@CAJPEAD_KPEBDAEBU_GUID@@@Z; StateRepository::Database::FormatSql(char *,unsigned __int64,char const *,_GUID const &)
0x18001898b  test    eax, eax
0x18001898d  js      loc_180018AC3
0x180018993  lea     r8, [rsp+0C8h+var_68]; char *
0x180018998  mov     rdx, rsi; struct _GUID *
0x18001899b  mov     rcx, rdi; this
0x18001899e  call    ?VerifyResourcePriorities@Database@StateRepository@@AEAAXAEBU_GUID@@PEBD@Z; StateRepository::Database::VerifyResourcePriorities(_GUID const &,char const *)
0x1800189a3  xor     r9d, r9d; void *
0x1800189a6  lea     rdx, [rsp+0C8h+var_68]; char *
0x1800189ab  xor     r8d, r8d; int (*)(void *)
0x1800189ae  mov     rcx, rdi; this
0x1800189b1  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800189b6  mov     ebx, eax
0x1800189b8  test    eax, eax
0x1800189ba  jns     short loc_1800189DF
0x1800189bc  mov     rcx, [rsp+0C8h]; this
0x1800189c4  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x1800189cb  mov     r9d, eax; char *
0x1800189ce  mov     edx, 279h; void *
0x1800189d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800189d8  mov     eax, ebx
0x1800189da  jmp     loc_180018A9B
0x1800189df  mov     rbx, [rdi+18h]
0x1800189e3  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1800189e8  mov     rbp, rax
0x1800189eb  lea     rdx, aBeginCommit; "BEGIN -> COMMIT;"
0x1800189f2  sub     rbp, rbx
0x1800189f5  mov     rcx, rdi; this
0x1800189f8  mov     r8, rbp; unsigned __int64
0x1800189fb  call    ?Profile@Database@StateRepository@@AEBAXPEBD_K@Z; StateRepository::Database::Profile(char const *,unsigned __int64)
0x180018a00  movsxd  rcx, dword ptr [rdi+10h]
0x180018a04  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180018a0b  mov     rbx, cs:qword_18004BDF0
0x180018a12  add     rcx, rcx
0x180018a15  movdqu  rva xmmword_18004BE50[r14+rcx*8], xmm0
0x180018a1f  movsxd  rdx, dword ptr [rdi+10h]; char *
0x180018a23  mov     eax, [rbx]
0x180018a25  mov     rva dword_18004BE30[r14+rdx*4], 0
0x180018a31  mov     rva qword_18004BE00[r14+rdx*8], 0
0x180018a3d  cmp     eax, 5
0x180018a40  jbe     short loc_180018A99
0x180018a42  mov     rcx, rdi; this
0x180018a45  mov     [rsp+0C8h+var_88], 1000000h
0x180018a4e  mov     [rsp+0C8h+var_80], rbp
0x180018a53  mov     [rsp+0C8h+var_78], rsi
0x180018a58  call    ?GetFilename@Database@StateRepository@@QEBAPEBDPEBD@Z; StateRepository::Database::GetFilename(char const *)
0x180018a5d  mov     [rsp+0C8h+var_70], rax
0x180018a62  lea     rdx, byte_180045931
0x180018a69  lea     rax, [rsp+0C8h+var_88]
0x180018a6e  mov     rcx, rbx
0x180018a71  mov     [rsp+0C8h+var_90], rax
0x180018a76  lea     rax, [rsp+0C8h+var_80]
0x180018a7b  mov     [rsp+0C8h+var_98], rax
0x180018a80  lea     rax, [rsp+0C8h+var_78]
0x180018a85  mov     [rsp+0C8h+var_A0], rax
0x180018a8a  lea     rax, [rsp+0C8h+var_70]
0x180018a8f  mov     [rsp+0C8h+var_A8], rax
0x180018a94  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180018a99  xor     eax, eax
0x180018a9b  mov     rcx, [rsp+0C8h+var_28]
0x180018aa3  xor     rcx, rsp; StackCookie
0x180018aa6  call    __security_check_cookie
0x180018aab  lea     r11, [rsp+0C8h+var_18]
0x180018ab3  mov     rbx, [r11+28h]
0x180018ab7  mov     rbp, [r11+30h]
0x180018abb  mov     rsp, r11
0x180018abe  pop     r14
0x180018ac0  pop     rdi
0x180018ac1  pop     rsi
0x180018ac2  retn
0x180018ac3  mov     rcx, [rsp+0C8h]; this
0x180018acb  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018ad2  mov     r9d, eax; char *
0x180018ad5  mov     edx, 275h; void *
0x180018ada  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
