# StateRepository::Migration::Deployment_Activation(StateRepository::Migration::Context const &)

- ea: `0x18000d0a0`
- end: `0x18000d316`
- name: `?Deployment_Activation@Migration@StateRepository@@YAJAEBVContext@12@@Z`
- size: `630`
- prototype: `__int64 __fastcall(StateRepository::Migration *__hidden this, const struct StateRepository::Migration::Context *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001aac`
- `0x180001c0c`
- `0x18000b81c`
- `0x18000b964`
- `0x18000ba20`
- `0x18000ba60`
- `0x18000c1f4`
- `0x18000c3bc`
- `0x18000c984`
- `0x18000d0a0`
- `0x18000d31c`
- `0x18000d54c`
- `0x18000d734`
- `0x1800182b0`
- `0x18001849c`

## import_xrefs

- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d13d`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d178`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d1b2`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d1ed`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d13d`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d178`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d1b2`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d1ed`

## pseudocode

```c
__int64 __fastcall StateRepository::Migration::Deployment_Activation(
        StateRepository::Migration *this,
        const struct StateRepository::Migration::Context *a2)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // r12d
  int v5; // eax
  StateRepository::Migration::Context *v6; // rcx
  __int64 v7; // rcx
  int v8; // eax
  int v9; // r15d
  __int64 v10; // rcx
  int v11; // eax
  int v12; // esi
  __int64 v13; // rcx
  int v14; // eax
  int v15; // r14d
  int v16; // edi
  int v17; // eax
  const struct _tlgProvider_t *v18; // rax
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  int v23; // [rsp+20h] [rbp-A9h]
  int v24; // [rsp+60h] [rbp-69h] BYREF
  int v25; // [rsp+64h] [rbp-65h] BYREF
  int v26; // [rsp+68h] [rbp-61h] BYREF
  int v27; // [rsp+6Ch] [rbp-5Dh] BYREF
  _QWORD v28[2]; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v29[32]; // [rsp+80h] [rbp-49h] BYREF
  int v30; // [rsp+A0h] [rbp-29h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]
  int v32; // [rsp+138h] [rbp+6Fh] BYREF
  int v33; // [rsp+140h] [rbp+77h] BYREF
  int v34; // [rsp+148h] [rbp+7Fh] BYREF

  StateRepository::Database::Database((StateRepository::Database *)v29);
  v3 = StateRepository::Migration::Context::Open(v2, 1u, (StateRepository::Database *)v29);
  if ( v3 >= 0 )
  {
    v4 = v30;
    v30 = 16;
    v5 = StateRepository::Database::BeginTransaction((StateRepository::Database *)v29, &stru_18003BA88, 0, 0);
    if ( v5 >= 0 )
    {
      v28[0] = v29;
      StateRepository_Service_UpdateStatus(1);
      v34 = 0;
      v8 = Do_Application(v7, v29, &v34);
      v9 = v8;
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
          (const char *)(unsigned int)v8,
          v23);
      StateRepository_Service_UpdateStatus(1);
      v33 = 0;
      v11 = Do_ApplicationExtension(v10, v29, &v33);
      v12 = v11;
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x30,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
          (const char *)(unsigned int)v11,
          v23);
      StateRepository_Service_UpdateStatus(1);
      v32 = 0;
      v14 = Do_PackageExtension(v13, v29, &v32);
      v15 = v14;
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
          (const char *)(unsigned int)v14,
          v23);
      StateRepository_Service_UpdateStatus(1);
      if ( v9 >= 0 || v12 >= 0 || (v16 = 0, v15 >= 0) )
      {
        v17 = StateRepository::AutoTransaction::Commit((StateRepository::AutoTransaction *)v28);
        v16 = v17;
        if ( v17 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x38,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
            (const char *)(unsigned int)v17,
            v23);
      }
      v18 = StateRepository::Tracing::Service::Provider();
      if ( *(_DWORD *)v18 > 5u && (unsigned __int8)tlgKeywordOn(v18, 0x200000000000LL, v18) )
      {
        v24 = v16;
        v25 = v15;
        v26 = v12;
        v27 = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)word_1800454AA,
          v19,
          v20,
          (__int64)&v27,
          (__int64)&v34,
          (__int64)&v26,
          (__int64)&v33,
          (__int64)&v25,
          (__int64)&v32,
          (__int64)&v24);
      }
      StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)v28);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
        (const char *)(unsigned int)v5,
        v23);
    }
    v21 = StateRepository::Migration::Context::Close(v6, (struct StateRepository::Database *)v29);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
        (const char *)(unsigned int)v21,
        v23);
    v30 = v4;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
      (const char *)(unsigned int)v3,
      v23);
  }
  StateRepository::Database::~Database((StateRepository::Database *)v29);
  return 0;
}

```

## disassembly

```asm
0x18000d0a0  mov     [rsp-8+arg_0], rsi
0x18000d0a5  push    rbp
0x18000d0a6  push    rdi
0x18000d0a7  push    r12
0x18000d0a9  push    r14
0x18000d0ab  push    r15
0x18000d0ad  lea     rbp, [rsp-37h]
0x18000d0b2  sub     rsp, 100h
0x18000d0b9  lea     rcx, [rbp+57h+var_A0]; this
0x18000d0bd  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x18000d0c2  mov     edi, 1
0x18000d0c7  lea     r8, [rbp+57h+var_A0]
0x18000d0cb  mov     edx, edi
0x18000d0cd  call    ?Open@Context@Migration@StateRepository@@QEBAJW4Partition@3@AEAVDatabase@3@@Z; StateRepository::Migration::Context::Open(StateRepository::Partition,StateRepository::Database &)
0x18000d0d2  test    eax, eax
0x18000d0d4  jns     short loc_18000D0F1
0x18000d0d6  mov     rcx, [rbp+5Fh]; this
0x18000d0da  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d0e1  mov     r9d, eax; char *
0x18000d0e4  lea     edx, [rdi+1Eh]; void *
0x18000d0e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d0ec  jmp     loc_18000D2F3
0x18000d0f1  mov     r12d, [rbp+57h+var_80]
0x18000d0f5  lea     rdx, stru_18003BA88; struct _GUID *
0x18000d0fc  xor     r9d, r9d; void *
0x18000d0ff  mov     [rbp+57h+var_80], 10h
0x18000d106  xor     r8d, r8d; int (*)(void *)
0x18000d109  lea     rcx, [rbp+57h+var_A0]; this
0x18000d10d  call    ?BeginTransaction@Database@StateRepository@@QEAAJAEBU_GUID@@P6AJPEAX@Z1@Z; StateRepository::Database::BeginTransaction(_GUID const &,long (*)(void *),void *)
0x18000d112  test    eax, eax
0x18000d114  jns     short loc_18000D133
0x18000d116  mov     rcx, [rbp+5Fh]; this
0x18000d11a  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d121  mov     r9d, eax; char *
0x18000d124  mov     edx, 25h ; '%'; void *
0x18000d129  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d12e  jmp     loc_18000D2CA
0x18000d133  lea     rax, [rbp+57h+var_A0]
0x18000d137  mov     ecx, edi
0x18000d139  mov     [rbp+57h+var_B0], rax
0x18000d13d  call    cs:__imp_StateRepository_Service_UpdateStatus
0x18000d143  lea     r8, [rbp+57h+arg_18]
0x18000d147  mov     [rbp+57h+arg_18], 0
0x18000d14e  lea     rdx, [rbp+57h+var_A0]
0x18000d152  call    Do_Application
0x18000d157  mov     r15d, eax
0x18000d15a  test    eax, eax
0x18000d15c  jns     short loc_18000D176
0x18000d15e  mov     rcx, [rbp+5Fh]; this
0x18000d162  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d169  mov     r9d, eax; char *
0x18000d16c  mov     edx, 2Dh ; '-'; void *
0x18000d171  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d176  mov     ecx, edi
0x18000d178  call    cs:__imp_StateRepository_Service_UpdateStatus
0x18000d17e  lea     r8, [rbp+57h+arg_10]
0x18000d182  mov     [rbp+57h+arg_10], 0
0x18000d189  lea     rdx, [rbp+57h+var_A0]
0x18000d18d  call    Do_ApplicationExtension
0x18000d192  mov     esi, eax
0x18000d194  test    eax, eax
0x18000d196  jns     short loc_18000D1B0
0x18000d198  mov     rcx, [rbp+5Fh]; this
0x18000d19c  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d1a3  mov     r9d, eax; char *
0x18000d1a6  mov     edx, 30h ; '0'; void *
0x18000d1ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d1b0  mov     ecx, edi
0x18000d1b2  call    cs:__imp_StateRepository_Service_UpdateStatus
0x18000d1b8  lea     r8, [rbp+57h+arg_8]
0x18000d1bc  mov     [rbp+57h+arg_8], 0
0x18000d1c3  lea     rdx, [rbp+57h+var_A0]
0x18000d1c7  call    Do_PackageExtension
0x18000d1cc  mov     r14d, eax
0x18000d1cf  test    eax, eax
0x18000d1d1  jns     short loc_18000D1EB
0x18000d1d3  mov     rcx, [rbp+5Fh]; this
0x18000d1d7  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d1de  mov     r9d, eax; char *
0x18000d1e1  mov     edx, 33h ; '3'; void *
0x18000d1e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d1eb  mov     ecx, edi
0x18000d1ed  call    cs:__imp_StateRepository_Service_UpdateStatus
0x18000d1f3  test    r15d, r15d
0x18000d1f6  jns     short loc_18000D203
0x18000d1f8  test    esi, esi
0x18000d1fa  jns     short loc_18000D203
0x18000d1fc  xor     edi, edi
0x18000d1fe  test    r14d, r14d
0x18000d201  js      short loc_18000D22A
0x18000d203  lea     rcx, [rbp+57h+var_B0]; this
0x18000d207  call    ?Commit@AutoTransaction@StateRepository@@QEAAJXZ; StateRepository::AutoTransaction::Commit(void)
0x18000d20c  mov     edi, eax
0x18000d20e  test    eax, eax
0x18000d210  jns     short loc_18000D22A
0x18000d212  mov     rcx, [rbp+5Fh]; this
0x18000d216  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d21d  mov     r9d, eax; char *
0x18000d220  mov     edx, 38h ; '8'; void *
0x18000d225  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d22a  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x18000d22f  mov     r8, rax
0x18000d232  mov     ecx, [rax]
0x18000d234  cmp     ecx, 5
0x18000d237  jbe     loc_18000D2C1
0x18000d23d  mov     rdx, 200000000000h
0x18000d247  mov     rcx, rax
0x18000d24a  call    _tlgKeywordOn
0x18000d24f  test    al, al
0x18000d251  jz      short loc_18000D2C1
0x18000d253  mov     eax, [rbp+57h+arg_10]
0x18000d256  lea     rdx, word_1800454AA
0x18000d25d  mov     ecx, [rbp+57h+arg_8]
0x18000d260  mov     [rbp+57h+arg_10], eax
0x18000d263  mov     eax, [rbp+57h+arg_18]
0x18000d266  mov     [rbp+57h+arg_18], eax
0x18000d269  lea     rax, [rbp+57h+var_C0]
0x18000d26d  mov     [rsp+120h+var_D0], rax
0x18000d272  lea     rax, [rbp+57h+arg_8]
0x18000d276  mov     [rsp+120h+var_D8], rax
0x18000d27b  lea     rax, [rbp+57h+var_BC]
0x18000d27f  mov     [rsp+120h+var_E0], rax
0x18000d284  lea     rax, [rbp+57h+arg_10]
0x18000d288  mov     [rsp+120h+var_E8], rax
0x18000d28d  lea     rax, [rbp+57h+var_B8]
0x18000d291  mov     [rsp+120h+var_F0], rax
0x18000d296  lea     rax, [rbp+57h+arg_18]
0x18000d29a  mov     [rsp+120h+var_F8], rax
0x18000d29f  lea     rax, [rbp+57h+var_B4]
0x18000d2a3  mov     [rbp+57h+arg_8], ecx
0x18000d2a6  mov     rcx, r8
0x18000d2a9  mov     qword ptr [rsp+120h+var_100], rax; int
0x18000d2ae  mov     [rbp+57h+var_C0], edi
0x18000d2b1  mov     [rbp+57h+var_BC], r14d
0x18000d2b5  mov     [rbp+57h+var_B8], esi
0x18000d2b8  mov     [rbp+57h+var_B4], r15d
0x18000d2bc  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d2c1  lea     rcx, [rbp+57h+var_B0]; this
0x18000d2c5  call    ??1AutoTransaction@StateRepository@@QEAA@XZ; StateRepository::AutoTransaction::~AutoTransaction(void)
0x18000d2ca  lea     rdx, [rbp+57h+var_A0]; struct StateRepository::Database *
0x18000d2ce  call    ?Close@Context@Migration@StateRepository@@QEBAJAEAVDatabase@3@@Z; StateRepository::Migration::Context::Close(StateRepository::Database &)
0x18000d2d3  test    eax, eax
0x18000d2d5  jns     short loc_18000D2EF
0x18000d2d7  mov     rcx, [rbp+5Fh]; this
0x18000d2db  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d2e2  mov     r9d, eax; char *
0x18000d2e5  mov     edx, 47h ; 'G'; void *
0x18000d2ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d2ef  mov     [rbp+57h+var_80], r12d
0x18000d2f3  lea     rcx, [rbp+57h+var_A0]; this
0x18000d2f7  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x18000d2fc  mov     rsi, [rsp+120h+arg_0]
0x18000d304  xor     eax, eax
0x18000d306  add     rsp, 100h
0x18000d30d  pop     r15
0x18000d30f  pop     r14
0x18000d311  pop     r12
0x18000d313  pop     rdi
0x18000d314  pop     rbp
0x18000d315  retn
```
