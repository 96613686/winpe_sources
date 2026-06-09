# SEEventMgr::Initialize(std::function<void (void)>,std::function<void (void)>)

- ea: `0x18001cb70`
- end: `0x18001cd6a`
- name: `?Initialize@SEEventMgr@@QEAAJV?$function@$$A6AXXZ@std@@0@Z`
- size: `506`
- prototype: `__int64 __fastcall(SEEventMgr *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180011a64`

## callees

- `0x180001194`
- `0x18000f740`
- `0x18001bf7c`
- `0x18001cb70`
- `0x18001f2f8`
- `0x18001fce4`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cd0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cd0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cbd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cbd1`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x18001cc9f`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x18001cc9f`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18001cc7e`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18001cc7e`

## string_xrefs

- `0x18001cc4c`: `onecoreuap\ds\nfc\product\semanagement\common\seeventmgr\src\seeventmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SEEventMgr::Initialize(SEEventMgr *this, __int64 a2, __int64 *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r12
  int v7; // r8d
  int v8; // r9d
  int AudioHelper; // eax
  int BrokerInstance2; // eax
  signed int v11; // ebx
  int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 *v18; // rcx
  __int64 v19; // rdx
  int v21; // [rsp+20h] [rbp-50h]
  _QWORD v22[6]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  const char *v24; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+48h]
  __int64 *v26; // [rsp+C0h] [rbp+50h]
  const char *v27; // [rsp+C8h] [rbp+58h] BYREF

  v26 = a3;
  v25 = a2;
  v22[0] = &SEEventMgr::OnCreateBrokerEvent;
  v22[1] = &SEEventMgr::OnDeleteBrokerEvent;
  v22[2] = &SEEventMgr::OnEnableBrokerEvent;
  v22[3] = &SEEventMgr::OnDisableBrokerEvent;
  v22[4] = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    v24 = "SEEventMgr::Initialize starts";
    v27 = "SEEventMgr::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"SEEventMgr::Initialize",
      (unsigned int)qword_18011A270,
      v7,
      v8,
      (__int64)&v27,
      (__int64)&v24);
  }
  std::function<void (void)>::operator=((char *)this + 104, a2);
  std::function<void (void)>::operator=((char *)this + 168, a3);
  AudioHelper = IAudioPlayHelper::CreateAudioHelper((void (__fastcall ****)(_QWORD, __int64))this + 29);
  if ( AudioHelper < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seeventmgr\\src\\seeventmgr.cpp",
      (const char *)(unsigned int)AudioHelper,
      v21);
  BrokerInstance2 = BrCreateBrokerInstance2(v22, &GUID_SmartCardBrokerId, 1, &qword_1800A8008);
  v11 = BrokerInstance2;
  if ( BrokerInstance2 > 0 )
    v11 = (unsigned __int16)BrokerInstance2 | 0x80070000;
  if ( v11 < 0 )
    goto LABEL_12;
  v12 = BrInitializeBrokerInstance2(*((_QWORD *)this + 11), 0, 0);
  v11 = v12;
  if ( v12 > 0 )
    v11 = (unsigned __int16)v12 | 0x80070000;
  if ( v11 < 0 )
LABEL_12:
    SEEventMgr::Uninitialize(this);
  else
    *((_DWORD *)this + 12) = 1;
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    v24 = "SEEventMgr::Initialize ends";
    v27 = "SEEventMgr::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v13,
      (unsigned int)qword_18011A438,
      v14,
      v15,
      (__int64)&v27,
      (__int64)&v24);
  }
  LeaveCriticalSection(v6);
  v17 = *(_QWORD *)(a2 + 56);
  if ( v17 )
  {
    LOBYTE(v16) = v17 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 32LL))(v17, v16);
    *(_QWORD *)(a2 + 56) = 0;
  }
  v18 = (__int64 *)a3[7];
  if ( v18 )
  {
    v19 = *v18;
    LOBYTE(v19) = v18 != a3;
    (*(void (__fastcall **)(__int64 *, __int64))(*v18 + 32))(v18, v19);
    a3[7] = 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001cb70  mov     [rsp-38h+arg_10], r8
0x18001cb75  mov     [rsp-38h+arg_8], rdx
0x18001cb7a  push    rbp
0x18001cb7b  push    rbx
0x18001cb7c  push    rsi
0x18001cb7d  push    rdi
0x18001cb7e  push    r12
0x18001cb80  push    r14
0x18001cb82  push    r15
0x18001cb84  mov     rbp, rsp
0x18001cb87  sub     rsp, 70h
0x18001cb8b  mov     rsi, r8
0x18001cb8e  mov     r14, rdx
0x18001cb91  mov     rdi, rcx
0x18001cb94  lea     rax, ?OnCreateBrokerEvent@SEEventMgr@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z; SEEventMgr::OnCreateBrokerEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)
0x18001cb9b  mov     [rbp+var_30], rax
0x18001cb9f  lea     rax, ?OnDeleteBrokerEvent@SEEventMgr@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; SEEventMgr::OnDeleteBrokerEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001cba6  mov     [rbp+var_28], rax
0x18001cbaa  lea     rax, ?OnEnableBrokerEvent@SEEventMgr@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; SEEventMgr::OnEnableBrokerEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001cbb1  mov     [rbp+var_20], rax
0x18001cbb5  lea     rax, ?OnDisableBrokerEvent@SEEventMgr@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; SEEventMgr::OnDisableBrokerEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001cbbc  mov     [rbp+var_18], rax
0x18001cbc0  xor     eax, eax
0x18001cbc2  mov     [rbp+var_10], rax
0x18001cbc6  lea     r12, [rcx+8]
0x18001cbca  mov     [rbp+var_40], r12
0x18001cbce  mov     rcx, r12; lpCriticalSection
0x18001cbd1  call    cs:__imp_EnterCriticalSection
0x18001cbd7  mov     [rbp+var_38], 1
0x18001cbdb  mov     eax, cs:dword_18012F048
0x18001cbe1  lea     rcx, aSeeventmgrInit; "SEEventMgr::Initialize"
0x18001cbe8  cmp     eax, 5
0x18001cbeb  jbe     short loc_18001CC1A
0x18001cbed  lea     rax, aSeeventmgrInit_1; "SEEventMgr::Initialize starts"
0x18001cbf4  mov     [rbp+arg_0], rax
0x18001cbf8  mov     [rbp+arg_18], rcx
0x18001cbfc  lea     rax, [rbp+arg_0]
0x18001cc00  mov     [rsp+70h+var_48], rax
0x18001cc05  lea     rax, [rbp+arg_18]
0x18001cc09  mov     qword ptr [rsp+70h+var_50], rax; int
0x18001cc0e  lea     rdx, qword_18011A270
0x18001cc15  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001cc1a  lea     rcx, [rdi+68h]
0x18001cc1e  mov     rdx, r14
0x18001cc21  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> const &)
0x18001cc26  lea     rcx, [rdi+0A8h]
0x18001cc2d  mov     rdx, rsi
0x18001cc30  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> const &)
0x18001cc35  lea     rcx, [rdi+0E8h]
0x18001cc3c  call    ?CreateAudioHelper@IAudioPlayHelper@@SAJAEAV?$unique_ptr@VIAudioPlayHelper@@U?$default_delete@VIAudioPlayHelper@@@std@@@std@@@Z; IAudioPlayHelper::CreateAudioHelper(std::unique_ptr<IAudioPlayHelper> &)
0x18001cc41  mov     rcx, [rbp+38h]; this
0x18001cc45  test    eax, eax
0x18001cc47  jns     short loc_18001CC5D
0x18001cc49  mov     r9d, eax; char *
0x18001cc4c  lea     r8, aOnecoreuapDsNf_30; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18001cc53  mov     edx, 63h ; 'c'; void *
0x18001cc58  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cc5d  lea     r15, [rdi+58h]
0x18001cc61  mov     qword ptr [rsp+70h+var_50], r15
0x18001cc66  lea     r9, qword_1800A8008
0x18001cc6d  mov     r8d, 1
0x18001cc73  lea     rdx, ?GUID_SmartCardBrokerId@@3U_GUID@@B; _GUID const GUID_SmartCardBrokerId
0x18001cc7a  lea     rcx, [rbp+var_30]
0x18001cc7e  call    cs:__imp_BrCreateBrokerInstance2
0x18001cc84  mov     ebx, eax
0x18001cc86  test    eax, eax
0x18001cc88  jle     short loc_18001CC93
0x18001cc8a  movzx   ebx, ax
0x18001cc8d  or      ebx, 80070000h
0x18001cc93  test    ebx, ebx
0x18001cc95  js      short loc_18001CCC1
0x18001cc97  xor     r8d, r8d
0x18001cc9a  xor     edx, edx
0x18001cc9c  mov     rcx, [r15]
0x18001cc9f  call    cs:__imp_BrInitializeBrokerInstance2
0x18001cca5  mov     ebx, eax
0x18001cca7  test    eax, eax
0x18001cca9  jle     short loc_18001CCB4
0x18001ccab  movzx   ebx, ax
0x18001ccae  or      ebx, 80070000h
0x18001ccb4  test    ebx, ebx
0x18001ccb6  js      short loc_18001CCC1
0x18001ccb8  mov     dword ptr [rdi+30h], 1
0x18001ccbf  jmp     short loc_18001CCC9
0x18001ccc1  mov     rcx, rdi; this
0x18001ccc4  call    ?Uninitialize@SEEventMgr@@QEAAJXZ; SEEventMgr::Uninitialize(void)
0x18001ccc9  mov     eax, cs:dword_18012F048
0x18001cccf  cmp     eax, 5
0x18001ccd2  jbe     short loc_18001CD09
0x18001ccd4  lea     rax, aSeeventmgrInit_0; "SEEventMgr::Initialize ends"
0x18001ccdb  mov     [rbp+arg_0], rax
0x18001ccdf  lea     rax, aSeeventmgrInit; "SEEventMgr::Initialize"
0x18001cce6  mov     [rbp+arg_18], rax
0x18001ccea  lea     rax, [rbp+arg_0]
0x18001ccee  mov     [rsp+70h+var_48], rax
0x18001ccf3  lea     rax, [rbp+arg_18]
0x18001ccf7  mov     qword ptr [rsp+70h+var_50], rax
0x18001ccfc  lea     rdx, qword_18011A438
0x18001cd03  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001cd08  nop
0x18001cd09  mov     rcx, r12; lpCriticalSection
0x18001cd0c  call    cs:__imp_LeaveCriticalSection
0x18001cd12  nop
0x18001cd13  mov     rcx, [r14+38h]
0x18001cd17  test    rcx, rcx
0x18001cd1a  jz      short loc_18001CD36
0x18001cd1c  mov     rax, [rcx]
0x18001cd1f  cmp     rcx, r14
0x18001cd22  setnz   dl
0x18001cd25  mov     rax, [rax+20h]
0x18001cd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd2e  mov     qword ptr [r14+38h], 0
0x18001cd36  mov     rcx, [rsi+38h]
0x18001cd3a  test    rcx, rcx
0x18001cd3d  jz      short loc_18001CD59
0x18001cd3f  mov     rdx, [rcx]
0x18001cd42  mov     rax, [rdx+20h]
0x18001cd46  cmp     rcx, rsi
0x18001cd49  setnz   dl
0x18001cd4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd51  mov     qword ptr [rsi+38h], 0
0x18001cd59  mov     eax, ebx
0x18001cd5b  add     rsp, 70h
0x18001cd5f  pop     r15
0x18001cd61  pop     r14
0x18001cd63  pop     r12
0x18001cd65  pop     rdi
0x18001cd66  pop     rsi
0x18001cd67  pop     rbx
0x18001cd68  pop     rbp
0x18001cd69  retn
```
