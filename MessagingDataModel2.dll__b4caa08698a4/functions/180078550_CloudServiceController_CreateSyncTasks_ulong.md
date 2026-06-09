# CloudServiceController::_CreateSyncTasks(ulong)

- ea: `0x180078550`
- end: `0x180078a0e`
- name: `?_CreateSyncTasks@CloudServiceController@@AEAAJK@Z`
- size: `1214`
- prototype: `__int64 __fastcall(CloudServiceController *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task`

## callees

- `0x1800016a0`
- `0x180001cc4`
- `0x180003e00`
- `0x180015050`
- `0x1800185cc`
- `0x18001e2ac`
- `0x180077240`
- `0x1800774d0`
- `0x1800783a0`
- `0x180078550`
- `0x18007aa78`
- `0x18007b11c`
- `0x18007ca7c`
- `0x18007cc30`
- `0x18007d30c`
- `0x180081584`
- `0x1800c51f4`
- `0x1800c6902`
- `0x1800c6940`

## string_xrefs

- `0x180078641`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x1800786ab`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x1800787a1`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x1800789d1`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x1800785ab`: `CloudServiceController::_CreateSyncTasks`
- `0x18007859a`: `Queue sync tasks`
- `0x1800787cb`: `Require Task: Signin`
- `0x180078727`: `Require Task: SignOut`
- `0x1800788bf`: `Require Task: Download`
- `0x180078845`: `Require Task: Migrate`
- `0x180078938`: `Require Task: Upload`

## pseudocode

```c
__int64 __fastcall CloudServiceController::_CreateSyncTasks(ConfigSet **this, int a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // ebx
  int v8; // esi
  MessagingUserSettings *v10; // rax
  MessagingUserSettings *v11; // rbx
  ConfigSet *v12; // rax
  ConfigSet *v13; // rsi
  int v14; // eax
  unsigned int v15; // r14d
  ConfigSet *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  int v21; // edi
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // [rsp+20h] [rbp-E0h]
  const OLECHAR *v35; // [rsp+30h] [rbp-D0h] BYREF
  int v36; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v37[256]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(v37, 0, sizeof(v37));
  if ( (int)StringCchPrintfW(
              v37,
              0x100u,
              L"%S(%d):%s",
              "CloudServiceController::_CreateSyncTasks",
              288,
              L"Queue sync tasks") >= 0
    && (unsigned int)dword_1800FD5F0 > 4 )
  {
    v36 = a2;
    v35 = v37;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)&unk_1800F02C8,
      v5,
      v6,
      (__int64)&v35,
      (__int64)&v36);
  }
  if ( !(unsigned int)CloudServiceController::_GetSyncState(this) )
  {
    v8 = CloudServiceController::_PostInitialize((CloudServiceController *)this);
    if ( v8 < 0 )
      goto LABEL_7;
    v10 = (MessagingUserSettings *)operator new(0x328u);
    v11 = v10;
    if ( !v10 || (memset_0(v10, 0, 0x328u), v12 = MessagingUserSettings::MessagingUserSettings(v11), (v13 = v12) == 0) )
    {
      v7 = -2147024882;
      goto LABEL_43;
    }
    v14 = ConfigSet::Initialize(v12, 1);
    v15 = v14;
    if ( v14 < 0 )
    {
      Log_HREvent_58(v14);
      tlx::_delete<ConfigSet::ConfigSetListener>((__int64 (__fastcall ***)(_QWORD, __int64))v13);
      return v15;
    }
    v16 = this[16];
    if ( v13 == v16 )
    {
      v13 = this[16];
    }
    else
    {
      if ( v16 )
        tlx::_delete<ConfigSet::ConfigSetListener>((__int64 (__fastcall ***)(_QWORD, __int64))this[16]);
      this[16] = v13;
    }
    v36 = 0;
    v8 = ConfigValueWithDefault<unsigned long>::Get((char *)v13 + 520, &v36);
    if ( v8 < 0 )
    {
LABEL_7:
      Log_HREvent_58(v8);
      return (unsigned int)v8;
    }
    if ( v36 == 2 )
    {
      LODWORD(v34) = 311;
      StringCchPrintfW(
        v37,
        0x100u,
        L"%S(%d):%s",
        "CloudServiceController::_CreateSyncTasks",
        v34,
        L"Require Task: SignOut");
      if ( (unsigned int)dword_1800FD5F0 > 4 )
      {
        v35 = v37;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v17,
          (int)word_1800F028A,
          v18,
          v19,
          &v35);
      }
      v20 = CloudServiceController::_SignOut((CloudServiceController *)this);
      v21 = CloudServiceController::_CheckSyncIterationResult((CloudServiceController *)this, v20);
      if ( v21 < 0 )
        goto LABEL_23;
    }
    else
    {
      if ( (unsigned int)ChatServiceClient::get_Status(this[6]) != 1 )
      {
        LODWORD(v34) = 326;
        StringCchPrintfW(
          v37,
          0x100u,
          L"%S(%d):%s",
          "CloudServiceController::_CreateSyncTasks",
          v34,
          L"Require Task: Signin");
        if ( (unsigned int)dword_1800FD5F0 > 4 )
        {
          v35 = v37;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v22,
            (int)&word_1800F020E,
            v23,
            v24,
            &v35);
        }
        v8 = CloudServiceController::_ScheduleTask(this, 8);
        if ( v8 < 0 )
          goto LABEL_7;
      }
      if ( (a2 & 4) != 0 )
      {
        LODWORD(v34) = 332;
        StringCchPrintfW(
          v37,
          0x100u,
          L"%S(%d):%s",
          "CloudServiceController::_CreateSyncTasks",
          v34,
          L"Require Task: Migrate");
        if ( (unsigned int)dword_1800FD5F0 > 4 )
        {
          v35 = v37;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v25,
            (int)&dword_1800F024C,
            v26,
            v27,
            &v35);
        }
        v8 = CloudServiceController::_ScheduleTask(this, 4);
        if ( v8 < 0 )
          goto LABEL_7;
      }
      if ( (a2 & 2) != 0 )
      {
        LODWORD(v34) = 338;
        StringCchPrintfW(
          v37,
          0x100u,
          L"%S(%d):%s",
          "CloudServiceController::_CreateSyncTasks",
          v34,
          L"Require Task: Download");
        if ( (unsigned int)dword_1800FD5F0 > 4 )
        {
          v35 = v37;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v28,
            (int)word_1800F0192,
            v29,
            v30,
            &v35);
        }
        v8 = CloudServiceController::_ScheduleTask(this, 2);
        if ( v8 < 0 )
          goto LABEL_7;
      }
      if ( (a2 & 1) != 0 )
      {
        LODWORD(v34) = 344;
        StringCchPrintfW(
          v37,
          0x100u,
          L"%S(%d):%s",
          "CloudServiceController::_CreateSyncTasks",
          v34,
          L"Require Task: Upload");
        if ( (unsigned int)dword_1800FD5F0 > 4 )
        {
          v35 = v37;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v31,
            (int)&unk_1800F01D0,
            v32,
            v33,
            &v35);
        }
        v8 = CloudServiceController::_ScheduleTask(this, 1);
        if ( v8 < 0 )
          goto LABEL_7;
      }
      v21 = CloudServiceController::_ScheduleSync((CloudServiceController *)this);
      if ( v21 < 0 )
      {
LABEL_23:
        Log_HREvent_58(v21);
        return (unsigned int)v21;
      }
    }
    return 0;
  }
  v7 = -2147418113;
LABEL_43:
  Log_HREvent_58(v7);
  return v7;
}

```

## disassembly

```asm
0x180078550  mov     [rsp-8+arg_8], rbx
0x180078555  mov     [rsp-8+arg_10], rsi
0x18007855a  push    rbp
0x18007855b  push    rdi
0x18007855c  push    r13
0x18007855e  push    r14
0x180078560  push    r15
0x180078562  lea     rbp, [rsp-150h]
0x18007856a  sub     rsp, 250h
0x180078571  mov     rax, cs:__security_cookie
0x180078578  xor     rax, rsp
0x18007857b  mov     [rbp+170h+var_30], rax
0x180078582  mov     r15d, edx
0x180078585  mov     rdi, rcx
0x180078588  xor     edx, edx; Val
0x18007858a  lea     rcx, [rsp+270h+var_230]; void *
0x18007858f  mov     r8d, 200h; Size
0x180078595  call    memset_0
0x18007859a  lea     rax, aQueueSyncTasks; "Queue sync tasks"
0x1800785a1  mov     edx, 100h; unsigned __int64
0x1800785a6  mov     [rsp+270h+var_248], rax
0x1800785ab  lea     r13, aCloudserviceco_4; "CloudServiceController::_CreateSyncTask"...
0x1800785b2  mov     r9, r13
0x1800785b5  mov     dword ptr [rsp+270h+var_250], 120h
0x1800785bd  lea     r8, aSDS; "%S(%d):%s"
0x1800785c4  lea     rcx, [rsp+270h+var_230]; unsigned __int16 *
0x1800785c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800785ce  test    eax, eax
0x1800785d0  js      short loc_18007860C
0x1800785d2  mov     eax, cs:dword_1800FD5F0
0x1800785d8  cmp     eax, 4
0x1800785db  jbe     short loc_18007860C
0x1800785dd  lea     rax, [rsp+270h+var_230]
0x1800785e2  mov     [rsp+270h+var_238], r15d
0x1800785e7  mov     [rsp+270h+var_240], rax
0x1800785ec  lea     rdx, unk_1800F02C8
0x1800785f3  lea     rax, [rsp+270h+var_238]
0x1800785f8  mov     [rsp+270h+var_248], rax
0x1800785fd  lea     rax, [rsp+270h+var_240]
0x180078602  mov     [rsp+270h+var_250], rax
0x180078607  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18007860c  mov     rcx, rdi
0x18007860f  call    ?_GetSyncState@CloudServiceController@@AEAA?AW4SyncState@1@XZ; CloudServiceController::_GetSyncState(void)
0x180078614  test    eax, eax
0x180078616  jz      short loc_180078628
0x180078618  mov     r9d, 125h
0x18007861e  mov     ebx, 8000FFFFh
0x180078623  jmp     loc_1800789D1
0x180078628  mov     rcx, rdi; this
0x18007862b  call    ?_PostInitialize@CloudServiceController@@AEAAJXZ; CloudServiceController::_PostInitialize(void)
0x180078630  mov     esi, eax
0x180078632  test    eax, eax
0x180078634  jns     short loc_180078656
0x180078636  mov     r9d, 127h
0x18007863c  mov     edx, 1
0x180078641  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x180078648  mov     ecx, esi; int
0x18007864a  call    Log_HREvent_58
0x18007864f  mov     eax, esi
0x180078651  jmp     loc_1800789E3
0x180078656  mov     esi, 328h
0x18007865b  mov     ecx, esi; Size
0x18007865d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180078662  mov     rbx, rax
0x180078665  test    rax, rax
0x180078668  jz      loc_1800789C6
0x18007866e  mov     r8d, esi; Size
0x180078671  xor     edx, edx; Val
0x180078673  mov     rcx, rax; void *
0x180078676  call    memset_0
0x18007867b  mov     rcx, rbx; this
0x18007867e  call    ??0MessagingUserSettings@@QEAA@XZ; MessagingUserSettings::MessagingUserSettings(void)
0x180078683  mov     rsi, rax
0x180078686  test    rax, rax
0x180078689  jz      loc_1800789C6
0x18007868f  mov     ebx, 1
0x180078694  mov     rcx, rax; this
0x180078697  mov     edx, ebx; int
0x180078699  call    ?Initialize@ConfigSet@@QEAAJH@Z; ConfigSet::Initialize(int)
0x18007869e  mov     r14d, eax
0x1800786a1  test    eax, eax
0x1800786a3  jns     short loc_1800786CB
0x1800786a5  mov     r9d, 12Ch
0x1800786ab  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800786b2  mov     edx, ebx
0x1800786b4  mov     ecx, eax; int
0x1800786b6  call    Log_HREvent_58
0x1800786bb  mov     rcx, rsi
0x1800786be  call    ??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAVConfigSetListener@ConfigSet@@@Z; tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)
0x1800786c3  mov     eax, r14d
0x1800786c6  jmp     loc_1800789E3
0x1800786cb  mov     rax, [rdi+80h]
0x1800786d2  cmp     rsi, rax
0x1800786d5  jz      short loc_1800786ED
0x1800786d7  test    rax, rax
0x1800786da  jz      short loc_1800786E4
0x1800786dc  mov     rcx, rax
0x1800786df  call    ??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAVConfigSetListener@ConfigSet@@@Z; tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)
0x1800786e4  mov     [rdi+80h], rsi
0x1800786eb  jmp     short loc_1800786F0
0x1800786ed  mov     rsi, rax
0x1800786f0  lea     rcx, [rsi+208h]
0x1800786f7  mov     [rsp+270h+var_238], 0
0x1800786ff  lea     rdx, [rsp+270h+var_238]
0x180078704  call    ?Get@?$ConfigValueWithDefault@K@@QEAAJPEAK@Z; ConfigValueWithDefault<ulong>::Get(ulong *)
0x180078709  mov     esi, eax
0x18007870b  test    eax, eax
0x18007870d  jns     short loc_18007871C
0x18007870f  mov     r9d, 132h
0x180078715  mov     edx, ebx
0x180078717  jmp     loc_180078641
0x18007871c  cmp     [rsp+270h+var_238], 2
0x180078721  jnz     loc_1800787B8
0x180078727  lea     rax, aRequireTaskSig; "Require Task: SignOut"
0x18007872e  mov     r9, r13
0x180078731  mov     [rsp+270h+var_248], rax
0x180078736  lea     r8, aSDS; "%S(%d):%s"
0x18007873d  mov     edx, 100h; unsigned __int64
0x180078742  mov     dword ptr [rsp+270h+var_250], 137h
0x18007874a  lea     rcx, [rsp+270h+var_230]; unsigned __int16 *
0x18007874f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078754  mov     eax, cs:dword_1800FD5F0
0x18007875a  cmp     eax, 4
0x18007875d  jbe     short loc_18007877F
0x18007875f  lea     rax, [rsp+270h+var_230]
0x180078764  mov     [rsp+270h+var_240], rax
0x180078769  lea     rdx, word_1800F028A
0x180078770  lea     rax, [rsp+270h+var_240]
0x180078775  mov     [rsp+270h+var_250], rax
0x18007877a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007877f  mov     rcx, rdi; this
0x180078782  call    ?_SignOut@CloudServiceController@@AEAAJXZ; CloudServiceController::_SignOut(void)
0x180078787  mov     edx, eax; int
0x180078789  mov     rcx, rdi; this
0x18007878c  call    ?_CheckSyncIterationResult@CloudServiceController@@AEAAJJ@Z; CloudServiceController::_CheckSyncIterationResult(long)
0x180078791  mov     edi, eax
0x180078793  test    eax, eax
0x180078795  jns     loc_1800789C2
0x18007879b  mov     r9d, 13Bh
0x1800787a1  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800787a8  mov     edx, ebx
0x1800787aa  mov     ecx, edi; int
0x1800787ac  call    Log_HREvent_58
0x1800787b1  mov     eax, edi
0x1800787b3  jmp     loc_1800789E3
0x1800787b8  mov     rcx, [rdi+30h]
0x1800787bc  call    ?get_Status@ChatServiceClient@@QEBA?AW4ChatServiceStatus@1@XZ; ChatServiceClient::get_Status(void)
0x1800787c1  mov     r14d, 100h
0x1800787c7  cmp     eax, ebx
0x1800787c9  jz      short loc_18007883F
0x1800787cb  lea     rax, aRequireTaskSig_0; "Require Task: Signin"
0x1800787d2  mov     r9, r13
0x1800787d5  mov     [rsp+270h+var_248], rax
0x1800787da  lea     r8, aSDS; "%S(%d):%s"
0x1800787e1  mov     edx, r14d; unsigned __int64
0x1800787e4  mov     dword ptr [rsp+270h+var_250], 146h
0x1800787ec  lea     rcx, [rsp+270h+var_230]; unsigned __int16 *
0x1800787f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800787f6  mov     eax, cs:dword_1800FD5F0
0x1800787fc  cmp     eax, 4
0x1800787ff  jbe     short loc_180078821
0x180078801  lea     rax, [rsp+270h+var_230]
0x180078806  mov     [rsp+270h+var_240], rax
0x18007880b  lea     rdx, word_1800F020E
0x180078812  lea     rax, [rsp+270h+var_240]
0x180078817  mov     [rsp+270h+var_250], rax
0x18007881c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180078821  mov     edx, 8
0x180078826  mov     rcx, rdi
0x180078829  call    ?_ScheduleTask@CloudServiceController@@AEAAJW4MessagingCloudServiceTaskType@@@Z; CloudServiceController::_ScheduleTask(MessagingCloudServiceTaskType)
0x18007882e  mov     esi, eax
0x180078830  test    eax, eax
0x180078832  jns     short loc_18007883F
0x180078834  mov     r9d, 147h
0x18007883a  jmp     loc_180078715
0x18007883f  test    r15b, 4
0x180078843  jz      short loc_1800788B9
0x180078845  lea     rax, aRequireTaskMig; "Require Task: Migrate"
0x18007884c  mov     r9, r13
0x18007884f  mov     [rsp+270h+var_248], rax
0x180078854  lea     r8, aSDS; "%S(%d):%s"
0x18007885b  mov     rdx, r14; unsigned __int64
0x18007885e  mov     dword ptr [rsp+270h+var_250], 14Ch
0x180078866  lea     rcx, [rsp+270h+var_230]; unsigned __int16 *
0x18007886b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078870  mov     eax, cs:dword_1800FD5F0
0x180078876  cmp     eax, 4
0x180078879  jbe     short loc_18007889B
0x18007887b  lea     rax, [rsp+270h+var_230]
0x180078880  mov     [rsp+270h+var_240], rax
0x180078885  lea     rdx, dword_1800F024C
0x18007888c  lea     rax, [rsp+270h+var_240]
0x180078891  mov     [rsp+270h+var_250], rax
0x180078896  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007889b  mov     edx, 4
0x1800788a0  mov     rcx, rdi
0x1800788a3  call    ?_ScheduleTask@CloudServiceController@@AEAAJW4MessagingCloudServiceTaskType@@@Z; CloudServiceController::_ScheduleTask(MessagingCloudServiceTaskType)
0x1800788a8  mov     esi, eax
0x1800788aa  test    eax, eax
0x1800788ac  jns     short loc_1800788B9
0x1800788ae  mov     r9d, 14Dh
0x1800788b4  jmp     loc_180078715
0x1800788b9  test    r15b, 2
0x1800788bd  jz      short loc_180078933
0x1800788bf  lea     rax, aRequireTaskDow; "Require Task: Download"
0x1800788c6  mov     r9, r13
0x1800788c9  mov     [rsp+270h+var_248], rax
0x1800788ce  lea     r8, aSDS; "%S(%d):%s"
0x1800788d5  mov     rdx, r14; unsigned __int64
0x1800788d8  mov     dword ptr [rsp+270h+var_250], 152h
0x1800788e0  lea     rcx, [rsp+270h+var_230]; unsigned __int16 *
0x1800788e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800788ea  mov     eax, cs:dword_1800FD5F0
0x1800788f0  cmp     eax, 4
0x1800788f3  jbe     short loc_180078915
0x1800788f5  lea     rax, [rsp+270h+var_230]
0x1800788fa  mov     [rsp+270h+var_240], rax
0x1800788ff  lea     rdx, word_1800F0192
0x180078906  lea     rax, [rsp+270h+var_240]
0x18007890b  mov     [rsp+270h+var_250], rax
0x180078910  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180078915  mov     edx, 2
0x18007891a  mov     rcx, rdi
0x18007891d  call    ?_ScheduleTask@CloudServiceController@@AEAAJW4MessagingCloudServiceTaskType@@@Z; CloudServiceController::_ScheduleTask(MessagingCloudServiceTaskType)
0x180078922  mov     esi, eax
0x180078924  test    eax, eax
0x180078926  jns     short loc_180078933
0x180078928  mov     r9d, 153h
0x18007892e  jmp     loc_180078715
0x180078933  test    bl, r15b
0x180078936  jz      short loc_1800789A9
0x180078938  lea     rax, aRequireTaskUpl; "Require Task: Upload"
0x18007893f  mov     r9, r13
0x180078942  mov     [rsp+270h+var_248], rax
0x180078947  lea     r8, aSDS; "%S(%d):%s"
0x18007894e  mov     rdx, r14; unsigned __int64
0x180078951  mov     dword ptr [rsp+270h+var_250], 158h
0x180078959  lea     rcx, [rsp+270h+var_230]; unsigned __int16 *
0x18007895e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078963  mov     eax, cs:dword_1800FD5F0
0x180078969  cmp     eax, 4
0x18007896c  jbe     short loc_18007898E
0x18007896e  lea     rax, [rsp+270h+var_230]
0x180078973  mov     [rsp+270h+var_240], rax
0x180078978  lea     rdx, unk_1800F01D0
0x18007897f  lea     rax, [rsp+270h+var_240]
0x180078984  mov     [rsp+270h+var_250], rax
0x180078989  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007898e  mov     edx, ebx
0x180078990  mov     rcx, rdi
0x180078993  call    ?_ScheduleTask@CloudServiceController@@AEAAJW4MessagingCloudServiceTaskType@@@Z; CloudServiceController::_ScheduleTask(MessagingCloudServiceTaskType)
0x180078998  mov     esi, eax
0x18007899a  test    eax, eax
0x18007899c  jns     short loc_1800789A9
0x18007899e  mov     r9d, 159h
0x1800789a4  jmp     loc_180078715
0x1800789a9  mov     rcx, rdi; this
0x1800789ac  call    ?_ScheduleSync@CloudServiceController@@AEAAJXZ; CloudServiceController::_ScheduleSync(void)
0x1800789b1  mov     edi, eax
0x1800789b3  test    eax, eax
0x1800789b5  jns     short loc_1800789C2
0x1800789b7  mov     r9d, 15Ch
0x1800789bd  jmp     loc_1800787A1
0x1800789c2  xor     eax, eax
0x1800789c4  jmp     short loc_1800789E3
0x1800789c6  mov     r9d, 12Bh
0x1800789cc  mov     ebx, 8007000Eh
0x1800789d1  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800789d8  xor     edx, edx
0x1800789da  mov     ecx, ebx; int
0x1800789dc  call    Log_HREvent_58
0x1800789e1  mov     eax, ebx
0x1800789e3  mov     rcx, [rbp+170h+var_30]
0x1800789ea  xor     rcx, rsp; StackCookie
0x1800789ed  call    __security_check_cookie
0x1800789f2  lea     r11, [rsp+270h+var_20]
0x1800789fa  mov     rbx, [r11+38h]
0x1800789fe  mov     rsi, [r11+40h]
0x180078a02  mov     rsp, r11
0x180078a05  pop     r15
0x180078a07  pop     r14
0x180078a09  pop     r13
0x180078a0b  pop     rdi
0x180078a0c  pop     rbp
0x180078a0d  retn
```
