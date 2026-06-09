# StateRepository::Migration::StateRepository_Activation_FullTrustProcess(StateRepository::Migration::Context const &)

- ea: `0x180014350`
- end: `0x1800144fe`
- name: `?StateRepository_Activation_FullTrustProcess@Migration@StateRepository@@YAJAEBVContext@12@@Z`
- size: `430`
- prototype: `__int64 __fastcall(StateRepository::Migration *__hidden this, const struct StateRepository::Migration::Context *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180001aac`
- `0x180001b78`
- `0x18000b81c`
- `0x18000b964`
- `0x18000ba20`
- `0x18000ba60`
- `0x18000c1f4`
- `0x18000c3bc`
- `0x18000c984`
- `0x1800141f0`
- `0x180014350`
- `0x1800182b0`
- `0x18001849c`

## import_xrefs

- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x1800143e7`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x180014421`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x1800143e7`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x180014421`

## pseudocode

```c
__int64 __fastcall StateRepository::Migration::StateRepository_Activation_FullTrustProcess(
        StateRepository::Migration *this,
        const struct StateRepository::Migration::Context *a2)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // esi
  int v5; // eax
  StateRepository::Migration::Context *v6; // rcx
  __int64 v7; // rcx
  int v8; // eax
  int v9; // edi
  int v10; // ebx
  int v11; // eax
  const struct _tlgProvider_t *v12; // rax
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  int v17; // [rsp+20h] [rbp-69h]
  _QWORD v18[2]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-39h] BYREF
  int v20; // [rsp+70h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int v22; // [rsp+F8h] [rbp+6Fh] BYREF
  int v23; // [rsp+100h] [rbp+77h] BYREF
  int v24; // [rsp+108h] [rbp+7Fh] BYREF

  StateRepository::Database::Database((StateRepository::Database *)v19);
  v3 = StateRepository::Migration::Context::Open(v2, 1u, (StateRepository::Database *)v19);
  if ( v3 >= 0 )
  {
    v4 = v20;
    v20 = 16;
    v5 = StateRepository::Database::BeginTransaction((StateRepository::Database *)v19, &stru_18003C4F8, 0, 0);
    if ( v5 >= 0 )
    {
      v18[0] = v19;
      StateRepository_Service_UpdateStatus(1);
      v22 = 0;
      v8 = Do_FullTrustProcess(v7, v19, &v22);
      v9 = v8;
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x24,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.activation.full"
                        "trustprocess.cpp",
          (const char *)(unsigned int)v8,
          v17);
      StateRepository_Service_UpdateStatus(1);
      v10 = 0;
      if ( v9 >= 0 )
      {
        v11 = StateRepository::AutoTransaction::Commit((StateRepository::AutoTransaction *)v18);
        v10 = v11;
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x29,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.activation.fu"
                          "lltrustprocess.cpp",
            (const char *)(unsigned int)v11,
            v17);
      }
      v12 = StateRepository::Tracing::Service::Provider();
      if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL, v12) )
      {
        v23 = v10;
        v24 = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v13,
          (unsigned int)byte_180045635,
          v13,
          v14,
          (__int64)&v24,
          (__int64)&v22,
          (__int64)&v23);
      }
      StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)v18);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.activation.fulltrustprocess.cpp",
        (const char *)(unsigned int)v5,
        v17);
    }
    v15 = StateRepository::Migration::Context::Close(v6, (struct StateRepository::Database *)v19);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.activation.fulltrustprocess.cpp",
        (const char *)(unsigned int)v15,
        v17);
    v20 = v4;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.activation.fulltrustprocess.cpp",
      (const char *)(unsigned int)v3,
      v17);
  }
  StateRepository::Database::~Database((StateRepository::Database *)v19);
  return 0;
}

```

## disassembly

```asm
0x180014350  mov     [rsp-8+arg_0], rbx
0x180014355  push    rbp
0x180014356  push    rsi
0x180014357  push    rdi
0x180014358  lea     rbp, [rsp-47h]
0x18001435d  sub     rsp, 0D0h
0x180014364  lea     rcx, [rbp+57h+var_90]; this
0x180014368  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x18001436d  mov     ebx, 1
0x180014372  lea     r8, [rbp+57h+var_90]
0x180014376  mov     edx, ebx
0x180014378  call    ?Open@Context@Migration@StateRepository@@QEBAJW4Partition@3@AEAVDatabase@3@@Z; StateRepository::Migration::Context::Open(StateRepository::Partition,StateRepository::Database &)
0x18001437d  test    eax, eax
0x18001437f  jns     short loc_18001439C
0x180014381  mov     rcx, [rbp+5Fh]; this
0x180014385  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x18001438c  mov     r9d, eax; char *
0x18001438f  lea     edx, [rbx+16h]; void *
0x180014392  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014397  jmp     loc_1800144E0
0x18001439c  mov     esi, [rbp+57h+var_70]
0x18001439f  lea     rdx, stru_18003C4F8; struct _GUID *
0x1800143a6  xor     r9d, r9d; void *
0x1800143a9  mov     [rbp+57h+var_70], 10h
0x1800143b0  xor     r8d, r8d; int (*)(void *)
0x1800143b3  lea     rcx, [rbp+57h+var_90]; this
0x1800143b7  call    ?BeginTransaction@Database@StateRepository@@QEAAJAEBU_GUID@@P6AJPEAX@Z1@Z; StateRepository::Database::BeginTransaction(_GUID const &,long (*)(void *),void *)
0x1800143bc  test    eax, eax
0x1800143be  jns     short loc_1800143DD
0x1800143c0  mov     rcx, [rbp+5Fh]; this
0x1800143c4  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x1800143cb  mov     r9d, eax; char *
0x1800143ce  mov     edx, 1Dh; void *
0x1800143d3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800143d8  jmp     loc_1800144B8
0x1800143dd  lea     rax, [rbp+57h+var_90]
0x1800143e1  mov     ecx, ebx
0x1800143e3  mov     [rbp+57h+var_A0], rax
0x1800143e7  call    cs:__imp_StateRepository_Service_UpdateStatus
0x1800143ed  lea     r8, [rbp+57h+arg_8]
0x1800143f1  mov     [rbp+57h+arg_8], 0
0x1800143f8  lea     rdx, [rbp+57h+var_90]
0x1800143fc  call    Do_FullTrustProcess
0x180014401  mov     edi, eax
0x180014403  test    eax, eax
0x180014405  jns     short loc_18001441F
0x180014407  mov     rcx, [rbp+5Fh]; this
0x18001440b  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x180014412  mov     r9d, eax; char *
0x180014415  mov     edx, 24h ; '$'; void *
0x18001441a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001441f  mov     ecx, ebx
0x180014421  call    cs:__imp_StateRepository_Service_UpdateStatus
0x180014427  xor     ebx, ebx
0x180014429  test    edi, edi
0x18001442b  js      short loc_180014454
0x18001442d  lea     rcx, [rbp+57h+var_A0]; this
0x180014431  call    ?Commit@AutoTransaction@StateRepository@@QEAAJXZ; StateRepository::AutoTransaction::Commit(void)
0x180014436  mov     ebx, eax
0x180014438  test    eax, eax
0x18001443a  jns     short loc_180014454
0x18001443c  mov     rcx, [rbp+5Fh]; this
0x180014440  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x180014447  mov     r9d, eax; char *
0x18001444a  mov     edx, 29h ; ')'; void *
0x18001444f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014454  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x180014459  mov     r8, rax
0x18001445c  mov     ecx, [rax]
0x18001445e  cmp     ecx, 5
0x180014461  jbe     short loc_1800144AF
0x180014463  mov     rdx, 200000000000h
0x18001446d  mov     rcx, rax
0x180014470  call    _tlgKeywordOn
0x180014475  test    al, al
0x180014477  jz      short loc_1800144AF
0x180014479  mov     ecx, [rbp+57h+arg_8]
0x18001447c  lea     rax, [rbp+57h+arg_10]
0x180014480  mov     [rsp+0E0h+var_B0], rax
0x180014485  lea     rdx, byte_180045635
0x18001448c  lea     rax, [rbp+57h+arg_8]
0x180014490  mov     [rbp+57h+arg_8], ecx
0x180014493  mov     [rsp+0E0h+var_B8], rax
0x180014498  mov     rcx, r8
0x18001449b  lea     rax, [rbp+57h+arg_18]
0x18001449f  mov     [rbp+57h+arg_10], ebx
0x1800144a2  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800144a7  mov     [rbp+57h+arg_18], edi
0x1800144aa  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800144af  lea     rcx, [rbp+57h+var_A0]; this
0x1800144b3  call    ??1AutoTransaction@StateRepository@@QEAA@XZ; StateRepository::AutoTransaction::~AutoTransaction(void)
0x1800144b8  lea     rdx, [rbp+57h+var_90]; struct StateRepository::Database *
0x1800144bc  call    ?Close@Context@Migration@StateRepository@@QEBAJAEAVDatabase@3@@Z; StateRepository::Migration::Context::Close(StateRepository::Database &)
0x1800144c1  test    eax, eax
0x1800144c3  jns     short loc_1800144DD
0x1800144c5  mov     rcx, [rbp+5Fh]; this
0x1800144c9  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x1800144d0  mov     r9d, eax; char *
0x1800144d3  mov     edx, 34h ; '4'; void *
0x1800144d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800144dd  mov     [rbp+57h+var_70], esi
0x1800144e0  lea     rcx, [rbp+57h+var_90]; this
0x1800144e4  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x1800144e9  mov     rbx, [rsp+0E0h+arg_0]
0x1800144f1  xor     eax, eax
0x1800144f3  add     rsp, 0D0h
0x1800144fa  pop     rdi
0x1800144fb  pop     rsi
0x1800144fc  pop     rbp
0x1800144fd  retn
```
