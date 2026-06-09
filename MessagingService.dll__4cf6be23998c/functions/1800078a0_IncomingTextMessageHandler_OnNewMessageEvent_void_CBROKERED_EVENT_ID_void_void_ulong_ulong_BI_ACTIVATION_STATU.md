# IncomingTextMessageHandler::_OnNewMessageEvent(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *)

- ea: `0x1800078a0`
- end: `0x180007927`
- name: `?_OnNewMessageEvent@IncomingTextMessageHandler@@CAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z`
- size: `135`
- prototype: `void __fastcall(__int64, __int64, __int64, const IID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001394`
- `0x180007248`
- `0x180007594`
- `0x1800078a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800078b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800078b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007920`

## pseudocode

```c
void __fastcall IncomingTextMessageHandler::_OnNewMessageEvent(__int64 a1, __int64 a2, __int64 a3, const IID *a4)
{
  __int64 v5; // r8
  int v6; // eax
  __int64 v7; // r8
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // [rsp+30h] [rbp-18h] BYREF
  __int64 v12; // [rsp+38h] [rbp-10h] BYREF

  EnterCriticalSection(&IncomingTextMessageHandler::sm_instanceLock);
  if ( IncomingTextMessageHandler::sm_incomingTextMessageHandler )
  {
    v6 = IncomingTextMessageHandler::_OnNewMessage(IncomingTextMessageHandler::sm_incomingTextMessageHandler, a4, v5);
    v8 = v6;
    if ( v6 < 0 )
    {
      Log_HREvent_3((unsigned int)v6, 0, v7, 80);
      if ( dword_180013018 )
      {
        v12 = 2048;
        v11 = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (unsigned int)dword_180013018,
          (int)byte_1800104B3,
          v9,
          v10,
          (__int64)&v11,
          (__int64)&v12);
      }
    }
  }
  LeaveCriticalSection(&IncomingTextMessageHandler::sm_instanceLock);
}

```

## disassembly

```asm
0x1800078a0  push    rbx
0x1800078a2  sub     rsp, 40h
0x1800078a6  lea     rcx, ?sm_instanceLock@IncomingTextMessageHandler@@0Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800078ad  mov     rbx, r9
0x1800078b0  call    cs:__imp_EnterCriticalSection
0x1800078b6  mov     rcx, cs:?sm_incomingTextMessageHandler@IncomingTextMessageHandler@@0V?$CComPtr@VIncomingTextMessageHandler@@@ATL@@A; this
0x1800078bd  test    rcx, rcx
0x1800078c0  jz      short loc_180007914
0x1800078c2  mov     rdx, rbx; void *
0x1800078c5  call    ?_OnNewMessage@IncomingTextMessageHandler@@AEAAJPEAX@Z; IncomingTextMessageHandler::_OnNewMessage(void *)
0x1800078ca  mov     ebx, eax
0x1800078cc  test    eax, eax
0x1800078ce  jns     short loc_180007914
0x1800078d0  xor     edx, edx
0x1800078d2  mov     ecx, eax
0x1800078d4  lea     r9d, [rdx+50h]
0x1800078d8  call    Log_HREvent_3
0x1800078dd  mov     ecx, cs:dword_180013018
0x1800078e3  test    ecx, ecx
0x1800078e5  jz      short loc_180007914
0x1800078e7  lea     rax, [rsp+48h+var_10]
0x1800078ec  mov     [rsp+48h+var_10], 800h
0x1800078f5  mov     [rsp+48h+var_20], rax
0x1800078fa  lea     rdx, byte_1800104B3
0x180007901  lea     rax, [rsp+48h+var_18]
0x180007906  mov     [rsp+48h+var_18], ebx
0x18000790a  mov     [rsp+48h+var_28], rax
0x18000790f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180007914  lea     rcx, ?sm_instanceLock@IncomingTextMessageHandler@@0Vrecursive_mutex@utl@@A; utl::recursive_mutex IncomingTextMessageHandler::sm_instanceLock
0x18000791b  add     rsp, 40h
0x18000791f  pop     rbx
0x180007920  jmp     cs:__imp_LeaveCriticalSection
```
