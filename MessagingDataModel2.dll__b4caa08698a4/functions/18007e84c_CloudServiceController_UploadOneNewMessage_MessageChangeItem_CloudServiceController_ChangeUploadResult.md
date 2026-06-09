# CloudServiceController::_UploadOneNewMessage(MessageChangeItem *,CloudServiceController::ChangeUploadResult *)

- ea: `0x18007e84c`
- end: `0x18007ec47`
- name: `?_UploadOneNewMessage@CloudServiceController@@AEAAJPEAVMessageChangeItem@@PEAW4ChangeUploadResult@1@@Z`
- size: `1019`
- prototype: `__int64 __fastcall(CloudServiceController *__hidden this, struct MessageChangeItem *, enum CloudServiceController::ChangeUploadResult *)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007e638`

## callees

- `0x180001198`
- `0x1800016a0`
- `0x180001c4c`
- `0x180005c50`
- `0x1800065c8`
- `0x18000bf4c`
- `0x180015050`
- `0x180077498`
- `0x1800774d0`
- `0x18007a844`
- `0x18007aba8`
- `0x18007e84c`
- `0x1800810b8`
- `0x1800824d8`
- `0x18008f690`
- `0x180092580`
- `0x18009893c`
- `0x18009a358`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007e904`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007eb7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007e904`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007eb7f`

## string_xrefs

- `0x18007e8ec`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007e94f`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007e993`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007ea28`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007ea7b`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007eacd`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007eb50`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007e899`: `CloudServiceController::_UploadOneNewMessage`

## pseudocode

```c
__int64 __fastcall CloudServiceController::_UploadOneNewMessage(
        ChatServiceClient **this,
        struct MessageChangeItem *a2,
        enum CloudServiceController::ChangeUploadResult *a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD TickCount; // eax
  __int64 v10; // rdx
  int v11; // esi
  DWORD v12; // r13d
  struct ISmMessage *v13; // rbx
  int v14; // eax
  unsigned int v15; // edi
  int UploadedDocumentFromLocalMessage; // eax
  struct AsyncMediaServiceDocument *v17; // rdi
  int v18; // eax
  int v19; // ebx
  int v20; // eax
  struct ChatServiceMessage *v21; // rbx
  const unsigned __int16 *v22; // r9
  unsigned __int64 v23; // r8
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rcx
  int v26; // eax
  int v27; // r8d
  __int64 v28; // r9
  __int64 v29; // r8
  struct AsyncMediaServiceDocument *v31; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v32; // [rsp+38h] [rbp-C8h] BYREF
  struct ChatServiceMessage *v33; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v34; // [rsp+48h] [rbp-B8h] BYREF
  struct ISmMessage *v35; // [rsp+50h] [rbp-B0h] BYREF
  struct MessageChangeItemRemoteId *v36; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+60h] [rbp-A0h] BYREF
  struct ISmConversation *v38; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID v39; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v40[256]; // [rsp+80h] [rbp-80h] BYREF

  StringCchPrintfW(v40, 0x100u, L"%S(%d):%s", "CloudServiceController::_UploadOneNewMessage", 1681, L"Enter");
  if ( (unsigned int)dword_1800FD5F0 > 5 )
  {
    v35 = (struct ISmMessage *)v40;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v6,
      (int)byte_1800EE7C5,
      v7,
      v8,
      (const OLECHAR **)&v35);
  }
  if ( *((_DWORD *)a2 + 6) != 1 )
  {
    Log_AssertionEvent_43(
      v6,
      "onecoreuap\\base\\appmodel\\messagingom\\cloudservices\\cloudservicecontroller.cpp",
      1683);
    if ( *((_DWORD *)a2 + 6) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  TickCount = GetTickCount();
  v10 = *((_QWORD *)a2 + 6);
  v11 = 0;
  v12 = TickCount;
  v35 = 0;
  ATL::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>(
    &v35,
    v10);
  v13 = v35;
  v38 = 0;
  v14 = (*(__int64 (__fastcall **)(struct ISmMessage *, struct ISmConversation **))(*(_QWORD *)v35 + 400LL))(v35, &v38);
  v15 = v14;
  if ( v14 < 0 )
  {
    Log_HREvent_58(v14);
    goto LABEL_32;
  }
  v32 = 2;
  v31 = 0;
  UploadedDocumentFromLocalMessage = CloudServiceController::_GetUploadedDocumentFromLocalMessage(
                                       (CloudServiceController *)this,
                                       v13,
                                       (enum CloudServiceController::DocumentUploadResult *)&v32,
                                       &v31);
  v15 = UploadedDocumentFromLocalMessage;
  if ( UploadedDocumentFromLocalMessage < 0 )
  {
LABEL_9:
    Log_HREvent_58(UploadedDocumentFromLocalMessage);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    goto LABEL_32;
  }
  if ( v32 == 1 )
  {
    *(_DWORD *)a3 = 2;
LABEL_12:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    v15 = v11;
    goto LABEL_32;
  }
  v39 = GUID_NULL;
  UploadedDocumentFromLocalMessage = CloudServiceController::_GetEndpointId((CloudServiceController *)this, &v39);
  v15 = UploadedDocumentFromLocalMessage;
  if ( UploadedDocumentFromLocalMessage < 0 )
    goto LABEL_9;
  v17 = v31;
  v33 = 0;
  v18 = ChatServiceMessage::CreateInstance(v13, v31, &v39, &v33);
  v19 = v18;
  if ( v18 < 0 )
  {
    Log_HREvent_58(v18);
LABEL_16:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    v15 = v19;
    goto LABEL_32;
  }
  v34 = 0;
  v20 = ChatServiceConversation::CreateInstance(v38, &v39, (struct ChatServiceConversation **)&v34);
  v19 = v20;
  if ( v20 < 0 )
  {
    Log_HREvent_58(v20);
LABEL_19:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    goto LABEL_16;
  }
  v21 = v33;
  if ( *((struct IUnknown **)v33 + 62) != v34 )
    ATL::AtlComPtrAssign((struct IUnknown **)v33 + 62, v34);
  v11 = ChatServiceClient::UploadMessage(this[6], v21);
  if ( v11 < 0 || *((_DWORD *)v17 + 20) && (v11 = AsyncMediaServiceClient::CommitDocument(this[7], v17), v11 < 0) )
  {
    Log_HREvent_58(v11);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
    goto LABEL_12;
  }
  v22 = (const unsigned __int16 *)*((_QWORD *)v17 + 3);
  v23 = *((_QWORD *)v21 + 74);
  v24 = (const unsigned __int16 *)*((_QWORD *)v21 + 7);
  v25 = (const unsigned __int16 *)*((_QWORD *)v21 + 11);
  v36 = 0;
  v26 = MessageChangeItemRemoteId::CreateInstance(v25, v24, v23, v22, &v36);
  v19 = v26;
  if ( v26 < 0 )
  {
    Log_HREvent_58(v26);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
    goto LABEL_19;
  }
  MessageChangeItem::put_RemoteId(a2, v36);
  GetTickCount();
  if ( (unsigned int)dword_1800FD5F0 > 4
    && (unsigned __int8)tlgKeywordOn((unsigned int)dword_1800FD5F0, 0x200000000000LL) )
  {
    v32 = *((_DWORD *)v17 + 20);
    v29 = v27 - v12;
    v37 = v29;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v32,
      (int)&unk_1800EE738,
      v29,
      v28,
      (__int64)&v37,
      (__int64)&v32);
  }
  *(_DWORD *)a3 = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  v15 = 0;
LABEL_32:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  return v15;
}

```

## disassembly

```asm
0x18007e84c  mov     [rsp-8+arg_18], rbx
0x18007e851  push    rbp
0x18007e852  push    rsi
0x18007e853  push    rdi
0x18007e854  push    r12
0x18007e856  push    r13
0x18007e858  push    r14
0x18007e85a  push    r15
0x18007e85c  lea     rbp, [rsp-190h]
0x18007e864  sub     rsp, 290h
0x18007e86b  mov     rax, cs:__security_cookie
0x18007e872  xor     rax, rsp
0x18007e875  mov     [rbp+1C0h+var_40], rax
0x18007e87c  lea     rax, aEnter; "Enter"
0x18007e883  mov     r12, r8
0x18007e886  mov     r14, rdx
0x18007e889  mov     [rsp+2C0h+var_298], rax
0x18007e88e  mov     r15, rcx
0x18007e891  mov     dword ptr [rsp+2C0h+var_2A0], 691h
0x18007e899  lea     r9, aCloudserviceco_7; "CloudServiceController::_UploadOneNewMe"...
0x18007e8a0  mov     edx, 100h; unsigned __int64
0x18007e8a5  lea     r8, aSDS; "%S(%d):%s"
0x18007e8ac  lea     rcx, [rbp+1C0h+var_240]; unsigned __int16 *
0x18007e8b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007e8b5  mov     eax, cs:dword_1800FD5F0
0x18007e8bb  cmp     eax, 5
0x18007e8be  jbe     short loc_18007E8DF
0x18007e8c0  lea     rax, [rbp+1C0h+var_240]
0x18007e8c4  mov     [rsp+2C0h+var_270], rax
0x18007e8c9  lea     rdx, byte_1800EE7C5
0x18007e8d0  lea     rax, [rsp+2C0h+var_270]
0x18007e8d5  mov     [rsp+2C0h+var_2A0], rax
0x18007e8da  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007e8df  cmp     dword ptr [r14+18h], 1
0x18007e8e4  jz      short loc_18007E904
0x18007e8e6  mov     r8d, 693h
0x18007e8ec  lea     rdx, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007e8f3  call    Log_AssertionEvent_43
0x18007e8f8  cmp     dword ptr [r14+18h], 1
0x18007e8fd  jz      short loc_18007E904
0x18007e8ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007e904  call    cs:__imp_GetTickCount
0x18007e90a  mov     rdx, [r14+30h]
0x18007e90e  lea     rcx, [rsp+2C0h+var_270]
0x18007e913  xor     esi, esi
0x18007e915  mov     r13d, eax
0x18007e918  mov     [rsp+2C0h+var_270], rsi
0x18007e91d  call    ??0?$CComPtrBase@VAsyncMediaServiceCommitDocumentTransaction@@@ATL@@IEAA@PEAVAsyncMediaServiceCommitDocumentTransaction@@@Z; ATL::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>(AsyncMediaServiceCommitDocumentTransaction *)
0x18007e922  mov     rbx, [rsp+2C0h+var_270]
0x18007e927  lea     rdx, [rsp+2C0h+var_258]
0x18007e92c  mov     [rsp+2C0h+var_258], rsi
0x18007e931  mov     rcx, [rbx]
0x18007e934  mov     rax, [rcx+190h]
0x18007e93b  mov     rcx, rbx
0x18007e93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e943  mov     edi, eax
0x18007e945  test    eax, eax
0x18007e947  jns     short loc_18007E965
0x18007e949  mov     r9d, 699h
0x18007e94f  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007e956  lea     edx, [rsi+1]
0x18007e959  mov     ecx, eax; int
0x18007e95b  call    Log_HREvent_58
0x18007e960  jmp     loc_18007EC07
0x18007e965  lea     r9, [rsp+2C0h+var_290]; struct AsyncMediaServiceDocument **
0x18007e96a  mov     [rsp+2C0h+var_288], 2
0x18007e972  lea     r8, [rsp+2C0h+var_288]; enum CloudServiceController::DocumentUploadResult *
0x18007e977  mov     [rsp+2C0h+var_290], rsi
0x18007e97c  mov     rdx, rbx; struct ISmMessage *
0x18007e97f  mov     rcx, r15; this
0x18007e982  call    ?_GetUploadedDocumentFromLocalMessage@CloudServiceController@@AEAAJPEAUISmMessage@@PEAW4DocumentUploadResult@1@PEAPEAVAsyncMediaServiceDocument@@@Z; CloudServiceController::_GetUploadedDocumentFromLocalMessage(ISmMessage *,CloudServiceController::DocumentUploadResult *,AsyncMediaServiceDocument * *)
0x18007e987  mov     edi, eax
0x18007e989  test    eax, eax
0x18007e98b  jns     short loc_18007E9B5
0x18007e98d  mov     r9d, 69Eh
0x18007e993  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007e99a  mov     edx, 1
0x18007e99f  mov     ecx, eax; int
0x18007e9a1  call    Log_HREvent_58
0x18007e9a6  lea     rcx, [rsp+2C0h+var_290]
0x18007e9ab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007e9b0  jmp     loc_18007EC07
0x18007e9b5  cmp     [rsp+2C0h+var_288], 1
0x18007e9ba  jnz     short loc_18007E9D5
0x18007e9bc  mov     dword ptr [r12], 2
0x18007e9c4  lea     rcx, [rsp+2C0h+var_290]
0x18007e9c9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007e9ce  mov     edi, esi
0x18007e9d0  jmp     loc_18007EC07
0x18007e9d5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007e9dc  lea     rdx, [rsp+2C0h+var_250]; struct _GUID *
0x18007e9e1  mov     rcx, r15; this
0x18007e9e4  movdqu  xmmword ptr [rsp+2C0h+var_250.Data1], xmm0
0x18007e9ea  call    ?_GetEndpointId@CloudServiceController@@AEAAJPEAU_GUID@@@Z; CloudServiceController::_GetEndpointId(_GUID *)
0x18007e9ef  mov     edi, eax
0x18007e9f1  test    eax, eax
0x18007e9f3  jns     short loc_18007E9FD
0x18007e9f5  mov     r9d, 6A9h
0x18007e9fb  jmp     short loc_18007E993
0x18007e9fd  mov     rdi, [rsp+2C0h+var_290]
0x18007ea02  lea     r9, [rsp+2C0h+var_280]; struct ChatServiceMessage **
0x18007ea07  mov     rdx, rdi; struct AsyncMediaServiceDocument *
0x18007ea0a  mov     [rsp+2C0h+var_280], rsi
0x18007ea0f  lea     r8, [rsp+2C0h+var_250]; struct _GUID *
0x18007ea14  mov     rcx, rbx; struct ISmMessage *
0x18007ea17  call    ?CreateInstance@ChatServiceMessage@@SAJPEAUISmMessage@@PEAVAsyncMediaServiceDocument@@PEBU_GUID@@PEAPEAV1@@Z; ChatServiceMessage::CreateInstance(ISmMessage *,AsyncMediaServiceDocument *,_GUID const *,ChatServiceMessage * *)
0x18007ea1c  mov     ebx, eax
0x18007ea1e  test    eax, eax
0x18007ea20  jns     short loc_18007EA56
0x18007ea22  mov     r9d, 6ACh
0x18007ea28  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007ea2f  mov     edx, 1
0x18007ea34  mov     ecx, eax; int
0x18007ea36  call    Log_HREvent_58
0x18007ea3b  lea     rcx, [rsp+2C0h+var_280]
0x18007ea40  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007ea45  lea     rcx, [rsp+2C0h+var_290]
0x18007ea4a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007ea4f  mov     edi, ebx
0x18007ea51  jmp     loc_18007EC07
0x18007ea56  mov     rcx, [rsp+2C0h+var_258]; struct ISmConversation *
0x18007ea5b  lea     r8, [rsp+2C0h+var_278]; struct ChatServiceConversation **
0x18007ea60  lea     rdx, [rsp+2C0h+var_250]; struct _GUID *
0x18007ea65  mov     [rsp+2C0h+var_278], rsi
0x18007ea6a  call    ?CreateInstance@ChatServiceConversation@@SAJPEAUISmConversation@@PEBU_GUID@@PEAPEAV1@@Z; ChatServiceConversation::CreateInstance(ISmConversation *,_GUID const *,ChatServiceConversation * *)
0x18007ea6f  mov     ebx, eax
0x18007ea71  test    eax, eax
0x18007ea73  jns     short loc_18007EA9A
0x18007ea75  mov     r9d, 6B0h
0x18007ea7b  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007ea82  mov     edx, 1
0x18007ea87  mov     ecx, eax; int
0x18007ea89  call    Log_HREvent_58
0x18007ea8e  lea     rcx, [rsp+2C0h+var_278]
0x18007ea93  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007ea98  jmp     short loc_18007EA3B
0x18007ea9a  mov     rbx, [rsp+2C0h+var_280]
0x18007ea9f  mov     rdx, [rsp+2C0h+var_278]; struct IUnknown *
0x18007eaa4  lea     rcx, [rbx+1F0h]; struct IUnknown **
0x18007eaab  cmp     [rcx], rdx
0x18007eaae  jz      short loc_18007EAB5
0x18007eab0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007eab5  mov     rcx, [r15+30h]; this
0x18007eab9  mov     rdx, rbx; struct ChatServiceMessage *
0x18007eabc  call    ?UploadMessage@ChatServiceClient@@QEAAJPEAVChatServiceMessage@@@Z; ChatServiceClient::UploadMessage(ChatServiceMessage *)
0x18007eac1  mov     esi, eax
0x18007eac3  test    eax, eax
0x18007eac5  jns     short loc_18007EAF9
0x18007eac7  mov     r9d, 6B5h
0x18007eacd  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007ead4  mov     edx, 1
0x18007ead9  mov     ecx, esi; int
0x18007eadb  call    Log_HREvent_58
0x18007eae0  lea     rcx, [rsp+2C0h+var_278]
0x18007eae5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007eaea  lea     rcx, [rsp+2C0h+var_280]
0x18007eaef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007eaf4  jmp     loc_18007E9C4
0x18007eaf9  cmp     dword ptr [rdi+50h], 0
0x18007eafd  jbe     short loc_18007EB19
0x18007eaff  mov     rcx, [r15+38h]; this
0x18007eb03  mov     rdx, rdi; struct AsyncMediaServiceDocument *
0x18007eb06  call    ?CommitDocument@AsyncMediaServiceClient@@QEAAJPEAVAsyncMediaServiceDocument@@@Z; AsyncMediaServiceClient::CommitDocument(AsyncMediaServiceDocument *)
0x18007eb0b  mov     esi, eax
0x18007eb0d  test    eax, eax
0x18007eb0f  jns     short loc_18007EB19
0x18007eb11  mov     r9d, 6BAh
0x18007eb17  jmp     short loc_18007EACD
0x18007eb19  mov     r9, [rdi+18h]; unsigned __int16 *
0x18007eb1d  lea     rax, [rsp+2C0h+var_268]
0x18007eb22  mov     r8, [rbx+250h]; unsigned __int64
0x18007eb29  mov     rdx, [rbx+38h]; unsigned __int16 *
0x18007eb2d  mov     rcx, [rbx+58h]; unsigned __int16 *
0x18007eb31  mov     [rsp+2C0h+var_2A0], rax; struct MessageChangeItemRemoteId **
0x18007eb36  mov     [rsp+2C0h+var_268], 0
0x18007eb3f  call    ?CreateInstance@MessageChangeItemRemoteId@@SAJPEBG0_K0PEAPEAV1@@Z; MessageChangeItemRemoteId::CreateInstance(ushort const *,ushort const *,unsigned __int64,ushort const *,MessageChangeItemRemoteId * *)
0x18007eb44  mov     ebx, eax
0x18007eb46  test    eax, eax
0x18007eb48  jns     short loc_18007EB72
0x18007eb4a  mov     r9d, 6C4h
0x18007eb50  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007eb57  mov     edx, 1
0x18007eb5c  mov     ecx, eax; int
0x18007eb5e  call    Log_HREvent_58
0x18007eb63  lea     rcx, [rsp+2C0h+var_268]
0x18007eb68  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007eb6d  jmp     loc_18007EA8E
0x18007eb72  mov     rdx, [rsp+2C0h+var_268]; struct MessageChangeItemRemoteId *
0x18007eb77  mov     rcx, r14; this
0x18007eb7a  call    ?put_RemoteId@MessageChangeItem@@QEAAXPEAVMessageChangeItemRemoteId@@@Z; MessageChangeItem::put_RemoteId(MessageChangeItemRemoteId *)
0x18007eb7f  call    cs:__imp_GetTickCount
0x18007eb85  mov     ecx, cs:dword_1800FD5F0
0x18007eb8b  mov     r8d, eax
0x18007eb8e  cmp     ecx, 4
0x18007eb91  jbe     short loc_18007EBD5
0x18007eb93  mov     rdx, 200000000000h
0x18007eb9d  call    _tlgKeywordOn
0x18007eba2  test    al, al
0x18007eba4  jz      short loc_18007EBD5
0x18007eba6  mov     ecx, [rdi+50h]
0x18007eba9  lea     rax, [rsp+2C0h+var_288]
0x18007ebae  mov     [rsp+2C0h+var_298], rax
0x18007ebb3  lea     rdx, unk_1800EE738
0x18007ebba  lea     rax, [rsp+2C0h+var_260]
0x18007ebbf  mov     [rsp+2C0h+var_288], ecx
0x18007ebc3  sub     r8d, r13d
0x18007ebc6  mov     [rsp+2C0h+var_2A0], rax
0x18007ebcb  mov     [rsp+2C0h+var_260], r8d
0x18007ebd0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007ebd5  lea     rcx, [rsp+2C0h+var_268]
0x18007ebda  mov     dword ptr [r12], 0
0x18007ebe2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007ebe7  lea     rcx, [rsp+2C0h+var_278]
0x18007ebec  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007ebf1  lea     rcx, [rsp+2C0h+var_280]
0x18007ebf6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007ebfb  lea     rcx, [rsp+2C0h+var_290]
0x18007ec00  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007ec05  xor     edi, edi
0x18007ec07  lea     rcx, [rsp+2C0h+var_258]
0x18007ec0c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007ec11  lea     rcx, [rsp+2C0h+var_270]
0x18007ec16  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007ec1b  mov     eax, edi
0x18007ec1d  mov     rcx, [rbp+1C0h+var_40]
0x18007ec24  xor     rcx, rsp; StackCookie
0x18007ec27  call    __security_check_cookie
0x18007ec2c  mov     rbx, [rsp+2C0h+arg_18]
0x18007ec34  add     rsp, 290h
0x18007ec3b  pop     r15
0x18007ec3d  pop     r14
0x18007ec3f  pop     r13
0x18007ec41  pop     r12
0x18007ec43  pop     rdi
0x18007ec44  pop     rsi
0x18007ec45  pop     rbp
0x18007ec46  retn
```
