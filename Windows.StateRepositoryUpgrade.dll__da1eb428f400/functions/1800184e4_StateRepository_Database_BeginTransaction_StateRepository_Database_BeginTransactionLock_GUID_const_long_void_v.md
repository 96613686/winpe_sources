# StateRepository::Database::BeginTransaction(StateRepository::Database::BeginTransactionLock,_GUID const &,long (*)(void *),void *)

- ea: `0x1800184e4`
- end: `0x18001868b`
- name: `?BeginTransaction@Database@StateRepository@@QEAAJW4BeginTransactionLock@12@AEBU_GUID@@P6AJPEAX@Z2@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001849c`

## callees

- `0x1800024e0`
- `0x180003980`
- `0x18000a3c0`
- `0x180014ca0`
- `0x180015204`
- `0x1800184e4`
- `0x180018c40`
- `0x180018d50`
- `0x180018e80`
- `0x180018ef0`
- `0x180019c28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800185ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800185ca`

## string_xrefs

- `0x18001852f`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180018595`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180018676`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::BeginTransaction(
        __int64 a1,
        unsigned __int64 a2,
        const struct _GUID *a3,
        int (*a4)(void *),
        void *a5)
{
  int v9; // eax
  int v10; // eax
  unsigned int v11; // esi
  DWORD CurrentThreadId; // eax
  StateRepository::DataType::Temporal *v13; // rcx
  unsigned __int64 Now; // rax
  StateRepository::Time *v15; // rcx
  unsigned __int64 UnbiasedInterruptTimeAsMSec; // rax
  const char *v17; // rdx
  _DWORD *v18; // rsi
  int v19; // r8d
  int v20; // r9d
  int v21; // [rsp+20h] [rbp-61h]
  __int64 v22; // [rsp+40h] [rbp-41h] BYREF
  __int64 v23; // [rsp+48h] [rbp-39h] BYREF
  const struct _GUID *v24; // [rsp+50h] [rbp-31h] BYREF
  const char *Filename; // [rsp+58h] [rbp-29h] BYREF
  char v26[64]; // [rsp+60h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
    && *(_QWORD *)a3->Data4 == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  else
  {
    v9 = StateRepository::Database::FormatSql(
           v26,
           a2,
           "BEGIN EXCLUSIVE /*%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X*/;",
           a3);
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x212,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v9,
        v21);
    StateRepository::Database::VerifyResourcePriorities((StateRepository::Database *)a1, a3, v26);
    v10 = StateRepository::Database::Execute((StateRepository::Database *)a1, v26, a4, a5);
    v11 = v10;
    if ( v10 >= 0 )
    {
      xmmword_18004BE50[*(int *)(a1 + 16)] = (__int128)*a3;
      CurrentThreadId = GetCurrentThreadId();
      v13 = (StateRepository::DataType::Temporal *)*(int *)(a1 + 16);
      dword_18004BE30[(_QWORD)v13] = CurrentThreadId;
      Now = StateRepository::DataType::Temporal::GetNow(v13);
      v15 = (StateRepository::Time *)*(int *)(a1 + 16);
      qword_18004BE00[(_QWORD)v15] = Now;
      UnbiasedInterruptTimeAsMSec = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v15);
      v18 = (_DWORD *)qword_18004BDF0;
      *(_QWORD *)(a1 + 24) = UnbiasedInterruptTimeAsMSec;
      if ( *v18 > 5u )
      {
        v23 = *(_QWORD *)(a1 + 24);
        v22 = 0x1000000;
        v24 = a3;
        Filename = StateRepository::Database::GetFilename((StateRepository::Database *)a1, v17);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (_DWORD)v18,
          (unsigned int)&unk_180045998,
          v19,
          v20,
          (__int64)&Filename,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)&v22);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x216,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v10,
        v21);
      return v11;
    }
  }
}

```

## disassembly

```asm
0x1800184e4  push    rbp
0x1800184e6  push    rbx
0x1800184e7  push    rsi
0x1800184e8  push    rdi
0x1800184e9  push    r14
0x1800184eb  lea     rbp, [rsp-2Fh]
0x1800184f0  sub     rsp, 0B0h
0x1800184f7  mov     rax, cs:__security_cookie
0x1800184fe  xor     rax, rsp
0x180018501  mov     [rbp+4Fh+var_30], rax
0x180018505  mov     rax, [r8]
0x180018508  mov     rsi, r9
0x18001850b  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180018512  mov     rbx, r8
0x180018515  mov     r14, [rbp+4Fh+arg_20]
0x180018519  mov     rdi, rcx
0x18001851c  jnz     short loc_18001854F
0x18001851e  mov     rax, [r8+8]
0x180018522  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180018529  jnz     short loc_18001854F
0x18001852b  mov     rcx, [rbp+57h]; this
0x18001852f  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018536  mov     ebx, 80070057h
0x18001853b  mov     edx, 206h; void *
0x180018540  mov     r9d, ebx; char *
0x180018543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018548  mov     eax, ebx
0x18001854a  jmp     loc_180018658
0x18001854f  mov     r9, rbx; struct _GUID *
0x180018552  lea     r8, aBeginExclusive; "BEGIN EXCLUSIVE /*%08X-%04X-%04X-%02X%0"...
0x180018559  lea     rcx, [rbp+4Fh+var_70]; char *
0x18001855d  call    ?FormatSql@Database@StateRepository@@CAJPEAD_KPEBDAEBU_GUID@@@Z; StateRepository::Database::FormatSql(char *,unsigned __int64,char const *,_GUID const &)
0x180018562  test    eax, eax
0x180018564  js      loc_180018672
0x18001856a  lea     r8, [rbp+4Fh+var_70]; char *
0x18001856e  mov     rdx, rbx; struct _GUID *
0x180018571  mov     rcx, rdi; this
0x180018574  call    ?VerifyResourcePriorities@Database@StateRepository@@AEAAXAEBU_GUID@@PEBD@Z; StateRepository::Database::VerifyResourcePriorities(_GUID const &,char const *)
0x180018579  mov     r9, r14; void *
0x18001857c  lea     rdx, [rbp+4Fh+var_70]; char *
0x180018580  mov     r8, rsi; int (*)(void *)
0x180018583  mov     rcx, rdi; this
0x180018586  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18001858b  mov     esi, eax
0x18001858d  test    eax, eax
0x18001858f  jns     short loc_1800185B0
0x180018591  mov     rcx, [rbp+57h]; this
0x180018595  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x18001859c  mov     r9d, eax; char *
0x18001859f  mov     edx, 216h; void *
0x1800185a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185a9  mov     eax, esi
0x1800185ab  jmp     loc_180018658
0x1800185b0  movsxd  rax, dword ptr [rdi+10h]
0x1800185b4  lea     rsi, __ImageBase
0x1800185bb  movups  xmm0, xmmword ptr [rbx]
0x1800185be  add     rax, rax
0x1800185c1  movdqu  rva xmmword_18004BE50[rsi+rax*8], xmm0
0x1800185ca  call    cs:__imp_GetCurrentThreadId
0x1800185d0  movsxd  rcx, dword ptr [rdi+10h]; this
0x1800185d4  mov     rva dword_18004BE30[rsi+rcx*4], eax
0x1800185db  call    ?GetNow@Temporal@DataType@StateRepository@@YA_KXZ; StateRepository::DataType::Temporal::GetNow(void)
0x1800185e0  movsxd  rcx, dword ptr [rdi+10h]; this
0x1800185e4  mov     rva qword_18004BE00[rsi+rcx*8], rax
0x1800185ec  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1800185f1  mov     rsi, cs:qword_18004BDF0
0x1800185f8  mov     [rdi+18h], rax
0x1800185fc  mov     eax, [rsi]
0x1800185fe  cmp     eax, 5
0x180018601  jbe     short loc_180018656
0x180018603  mov     rax, [rdi+18h]
0x180018607  mov     rcx, rdi; this
0x18001860a  mov     [rbp+4Fh+var_88], rax
0x18001860e  mov     [rbp+4Fh+var_90], 1000000h
0x180018616  mov     [rbp+4Fh+var_80], rbx
0x18001861a  call    ?GetFilename@Database@StateRepository@@QEBAPEBDPEBD@Z; StateRepository::Database::GetFilename(char const *)
0x18001861f  mov     [rbp+4Fh+var_78], rax
0x180018623  lea     rdx, unk_180045998
0x18001862a  lea     rax, [rbp+4Fh+var_90]
0x18001862e  mov     rcx, rsi
0x180018631  mov     [rsp+0D0h+var_98], rax
0x180018636  lea     rax, [rbp+4Fh+var_88]
0x18001863a  mov     [rsp+0D0h+var_A0], rax
0x18001863f  lea     rax, [rbp+4Fh+var_80]
0x180018643  mov     [rsp+0D0h+var_A8], rax
0x180018648  lea     rax, [rbp+4Fh+var_78]
0x18001864c  mov     [rsp+0D0h+var_B0], rax
0x180018651  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180018656  xor     eax, eax
0x180018658  mov     rcx, [rbp+4Fh+var_30]
0x18001865c  xor     rcx, rsp; StackCookie
0x18001865f  call    __security_check_cookie
0x180018664  add     rsp, 0B0h
0x18001866b  pop     r14
0x18001866d  pop     rdi
0x18001866e  pop     rsi
0x18001866f  pop     rbx
0x180018670  pop     rbp
0x180018671  retn
0x180018672  mov     rcx, [rbp+57h]; this
0x180018676  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x18001867d  mov     r9d, eax; char *
0x180018680  mov     edx, 212h; void *
0x180018685  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
