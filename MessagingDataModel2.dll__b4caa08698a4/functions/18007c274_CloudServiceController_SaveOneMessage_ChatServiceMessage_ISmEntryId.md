# CloudServiceController::_SaveOneMessage(ChatServiceMessage *,ISmEntryId * *)

- ea: `0x18007c274`
- end: `0x18007ca73`
- name: `?_SaveOneMessage@CloudServiceController@@AEAAJPEAVChatServiceMessage@@PEAPEAUISmEntryId@@@Z`
- size: `2047`
- prototype: `int(CloudServiceController *__hidden this, struct ChatServiceMessage *, struct ISmEntryId **)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180078a14`

## callees

- `0x1800016a0`
- `0x180001cc4`
- `0x180002854`
- `0x18000294c`
- `0x180005c50`
- `0x18000cc8c`
- `0x180015050`
- `0x1800774d0`
- `0x18007c274`
- `0x1800832b8`
- `0x180083a0c`
- `0x180086e70`
- `0x1800871b0`
- `0x1800875e4`
- `0x180087a1c`
- `0x18009648c`
- `0x180096bc4`
- `0x18009893c`
- `0x180099d8c`
- `0x1800c6902`
- `0x1800c6940`

## string_xrefs

- `0x18007c363`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c3b7`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c404`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c687`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c731`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c86a`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c43b`: `Downloaded message dropped because the message with the remote ID already exists.`
- `0x18007c2cb`: `CloudServiceController::_SaveOneMessage`
- `0x18007c44c`: `CloudServiceController::_SaveOneMessage`
- `0x18007c520`: `CloudServiceController::_SaveOneMessage`
- `0x18007c5b8`: `CloudServiceController::_SaveOneMessage`
- `0x18007c6c3`: `CloudServiceController::_SaveOneMessage`
- `0x18007c78a`: `CloudServiceController::_SaveOneMessage`
- `0x18007c8e5`: `CloudServiceController::_SaveOneMessage`
- `0x18007c9a2`: `CloudServiceController::_SaveOneMessage`
- `0x18007c6b2`: `Receive a text message from service`
- `0x18007c624`: `Receive a deletion marker from service`
- `0x18007c991`: `Downloaded message dropped because the message with the same client ID already exists.`
- `0x18007c779`: `Receive a multimedia message from service`

## pseudocode

```c
__int64 __fastcall CloudServiceController::_SaveOneMessage(
        CloudServiceController *this,
        struct ChatServiceMessage *a2,
        struct ISmEntryId **a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // eax
  unsigned int v10; // ebx
  struct AsyncMediaServiceDocument *v11; // rdi
  unsigned __int64 v12; // r8
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rcx
  const unsigned __int16 *v15; // r9
  int v16; // eax
  struct MessageChangeItemRemoteId *v17; // rbx
  MessageChangeTracker *v18; // rcx
  int v19; // eax
  int v20; // r15d
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  int Type; // eax
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // edi
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  MessageSaver *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  struct MessageChangeItemRemoteId **v50; // [rsp+20h] [rbp-E0h]
  struct ISmEntryId *v51; // [rsp+40h] [rbp-C0h] BYREF
  struct MessageChangeItemRemoteId *v52; // [rsp+48h] [rbp-B8h] BYREF
  struct MessageChangeItem *v53; // [rsp+50h] [rbp-B0h] BYREF
  const OLECHAR *v54; // [rsp+58h] [rbp-A8h] BYREF
  const OLECHAR *v55; // [rsp+60h] [rbp-A0h] BYREF
  const OLECHAR *v56; // [rsp+68h] [rbp-98h] BYREF
  struct AsyncMediaServiceDocument *v57; // [rsp+70h] [rbp-90h] BYREF
  const OLECHAR *v58; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v59[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v60[256]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v60, 0, sizeof(v60));
  if ( (int)StringCchPrintfW(
              v60,
              0x100u,
              L"%S(%d):%s",
              "CloudServiceController::_SaveOneMessage",
              1229,
              L"Enter: Save the ChatMessage") >= 0
    && (unsigned int)dword_1800FD5F0 > 4 )
  {
    v57 = (struct AsyncMediaServiceDocument *)*((_QWORD *)a2 + 74);
    v52 = (struct MessageChangeItemRemoteId *)*((_QWORD *)a2 + 7);
    v51 = (struct ISmEntryId *)v60;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v6,
      (int)word_1800EEEDA,
      v7,
      v8,
      (const OLECHAR **)&v51,
      (const OLECHAR **)&v52,
      (__int64)&v57);
  }
  v57 = 0;
  v9 = AsyncMediaServiceDocument::CreateInstance(a2, &v57);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = v57;
    v12 = *((_QWORD *)a2 + 74);
    v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
    v14 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
    v15 = (const unsigned __int16 *)*((_QWORD *)v57 + 3);
    v52 = 0;
    v16 = MessageChangeItemRemoteId::CreateInstance(v14, v13, v12, v15, &v52);
    v10 = v16;
    if ( v16 < 0 )
    {
      Log_HREvent_58(v16);
LABEL_8:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
      goto LABEL_55;
    }
    v17 = v52;
    v18 = (MessageChangeTracker *)*((_QWORD *)this + 8);
    LODWORD(v53) = 0;
    v19 = MessageChangeTracker::FindRemoteChange(v18, v52, (int *)&v53);
    v20 = v19;
    if ( v19 < 0 )
    {
      Log_HREvent_58(v19);
LABEL_54:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
      v10 = v20;
      goto LABEL_55;
    }
    v20 = 0;
    if ( (_DWORD)v53 )
    {
      memset_0(v60, 0, sizeof(v60));
      LODWORD(v50) = 1255;
      if ( (int)StringCchPrintfW(
                  v60,
                  0x100u,
                  L"%S(%d):%s",
                  "CloudServiceController::_SaveOneMessage",
                  v50,
                  L"Downloaded message dropped because the message with the remote ID already exists.") >= 0
        && (unsigned int)dword_1800FD5F0 > 3 )
      {
        v51 = (struct ISmEntryId *)*((_QWORD *)v17 + 19);
        v53 = (struct MessageChangeItem *)*((_QWORD *)a2 + 74);
        v55 = (const OLECHAR *)*((_QWORD *)a2 + 7);
        v56 = v60;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          v21,
          (int)byte_1800EEE61,
          v22,
          v23,
          &v56,
          &v55,
          (__int64)&v53,
          (const OLECHAR **)&v51);
      }
      goto LABEL_54;
    }
    Type = ChatServiceMessage::get_Type(a2);
    v51 = 0;
    v59[0] = 0;
    switch ( Type )
    {
      case 0:
        memset_0(v60, 0, sizeof(v60));
        LODWORD(v50) = 1270;
        if ( (int)StringCchPrintfW(
                    v60,
                    0x100u,
                    L"%S(%d):%s",
                    "CloudServiceController::_SaveOneMessage",
                    v50,
                    L"Unknown instance message not saved.") >= 0
          && (unsigned int)dword_1800FD5F0 > 3 )
        {
          v56 = (const OLECHAR *)*((_QWORD *)v17 + 19);
          v55 = (const OLECHAR *)*((_QWORD *)a2 + 74);
          v53 = (struct MessageChangeItem *)*((_QWORD *)a2 + 7);
          v54 = v60;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
            v25,
            (int)&unk_1800EEDE8,
            v26,
            v27,
            &v54,
            (const OLECHAR **)&v53,
            (__int64)&v55,
            &v56);
        }
LABEL_53:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
        goto LABEL_54;
      case 3:
        if ( *((_QWORD *)a2 + 74) )
        {
          LODWORD(v50) = 1285;
          StringCchPrintfW(
            v60,
            0x100u,
            L"%S(%d):%s",
            "CloudServiceController::_SaveOneMessage",
            v50,
            L"Receive a deletion marker from service");
          if ( (unsigned int)dword_1800FD5F0 > 4 )
          {
            v54 = v60;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              v31,
              (int)byte_1800EEDAB,
              v32,
              v33,
              &v54);
          }
          v34 = MessageSaver::TombstoneMessage(*((MessageSaver **)this + 10), *((_QWORD *)a2 + 74));
          v10 = v34;
          if ( v34 < 0 )
          {
            Log_HREvent_58(v34);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
            goto LABEL_8;
          }
        }
        else
        {
          LODWORD(v50) = 1281;
          StringCchPrintfW(
            v60,
            0x100u,
            L"%S(%d):%s",
            "CloudServiceController::_SaveOneMessage",
            v50,
            L"Receive a deletion marker without ClientMessageId");
          if ( (unsigned int)dword_1800FD5F0 > 4 )
          {
            v54 = v60;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              v28,
              (int)&word_1800EED6E,
              v29,
              v30,
              &v54);
          }
        }
        goto LABEL_53;
      case 1:
        LODWORD(v50) = 1293;
        StringCchPrintfW(
          v60,
          0x100u,
          L"%S(%d):%s",
          "CloudServiceController::_SaveOneMessage",
          v50,
          L"Receive a text message from service");
        if ( (unsigned int)dword_1800FD5F0 > 4 )
        {
          v54 = v60;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v35,
            (int)byte_1800EED31,
            v36,
            v37,
            &v54);
        }
        v38 = MessageSaver::SaveTextMessage(*((MessageSaver **)this + 10), a2, &v51, (enum MessageCreationResult *)v59);
        if ( v38 < 0 )
          goto LABEL_31;
        goto LABEL_41;
    }
    if ( Type != 2 )
      goto LABEL_50;
    memset_0(v60, 0, sizeof(v60));
    LODWORD(v50) = 1300;
    if ( (int)StringCchPrintfW(
                v60,
                0x100u,
                L"%S(%d):%s",
                "CloudServiceController::_SaveOneMessage",
                v50,
                L"Receive a multimedia message from service") >= 0
      && (unsigned int)dword_1800FD5F0 > 4 )
    {
      LODWORD(v53) = *((_DWORD *)v11 + 20);
      v54 = v60;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v39,
        (unsigned int)&dword_1800EECE4,
        v40,
        v41,
        (__int64)&v54,
        (__int64)&v53);
    }
    v42 = (MessageSaver *)*((_QWORD *)this + 10);
    if ( *((_DWORD *)v11 + 20) )
    {
      v38 = MessageSaver::SavePendingDownloadMessage(v42, a2, &v51, (enum MessageCreationResult *)v59);
      if ( v38 < 0 )
      {
LABEL_31:
        Log_HREvent_58(v38);
        goto LABEL_32;
      }
    }
    else
    {
      v38 = MessageSaver::SaveMultimediaMessage(v42, a2, v11, &v51, (enum MessageCreationResult *)v59);
      if ( v38 < 0 )
        goto LABEL_31;
    }
LABEL_41:
    if ( v59[0] )
    {
      v53 = 0;
      v38 = MessageChangeItem::CreateInstance(0, v51, v17, &v53);
      if ( v38 >= 0 )
      {
        v38 = MessageChangeTracker::AddUpdateLocalChange(*((MessageChangeTracker **)this + 8), v53);
        if ( v38 >= 0 )
        {
          v38 = ATL::CComPtrBase<ChatServiceAttachment>::CopyTo(&v51, a3);
          if ( v38 >= 0 )
          {
            memset_0(v60, 0, sizeof(v60));
            LODWORD(v50) = 1338;
            if ( (int)StringCchPrintfW(
                        v60,
                        0x100u,
                        L"%S(%d):%s",
                        "CloudServiceController::_SaveOneMessage",
                        v50,
                        L"Downloaded message successfully saved.") >= 0
              && (unsigned int)dword_1800FD5F0 > 3 )
            {
              v54 = (const OLECHAR *)*((_QWORD *)v17 + 19);
              v56 = (const OLECHAR *)*((_QWORD *)a2 + 74);
              v55 = (const OLECHAR *)*((_QWORD *)a2 + 7);
              v58 = v60;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
                v43,
                (int)&word_1800EEBAE,
                v44,
                v45,
                &v58,
                &v55,
                (__int64)&v56,
                &v54);
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
            goto LABEL_53;
          }
        }
      }
      Log_HREvent_58(v38);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
LABEL_32:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
      v10 = v38;
      goto LABEL_55;
    }
LABEL_50:
    memset_0(v60, 0, sizeof(v60));
    LODWORD(v50) = 1321;
    if ( (int)StringCchPrintfW(
                v60,
                0x100u,
                L"%S(%d):%s",
                "CloudServiceController::_SaveOneMessage",
                v50,
                L"Downloaded message dropped because the message with the same client ID already exists.") >= 0
      && (unsigned int)dword_1800FD5F0 > 3 )
    {
      v58 = (const OLECHAR *)*((_QWORD *)v17 + 19);
      v54 = (const OLECHAR *)*((_QWORD *)a2 + 74);
      v56 = (const OLECHAR *)*((_QWORD *)a2 + 7);
      v55 = v60;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v46,
        (int)byte_1800EEC6B,
        v47,
        v48,
        &v55,
        &v56,
        (__int64)&v54,
        &v58);
    }
    goto LABEL_53;
  }
  Log_HREvent_58(v9);
LABEL_55:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
  return v10;
}

```

## disassembly

```asm
0x18007c274  push    rbp
0x18007c276  push    rbx
0x18007c277  push    rdi
0x18007c278  push    r12
0x18007c27a  push    r13
0x18007c27c  push    r14
0x18007c27e  push    r15
0x18007c280  lea     rbp, [rsp-1A0h]
0x18007c288  sub     rsp, 2A0h
0x18007c28f  mov     rax, cs:__security_cookie
0x18007c296  xor     rax, rsp
0x18007c299  mov     [rbp+1D0h+var_40], rax
0x18007c2a0  mov     r12, r8
0x18007c2a3  mov     r14, rdx
0x18007c2a6  mov     r13, rcx
0x18007c2a9  xor     edx, edx; Val
0x18007c2ab  mov     r8d, 200h; Size
0x18007c2b1  lea     rcx, [rbp+1D0h+var_240]; void *
0x18007c2b5  call    memset_0
0x18007c2ba  lea     rax, aEnterSaveTheCh; "Enter: Save the ChatMessage"
0x18007c2c1  mov     edx, 100h; unsigned __int64
0x18007c2c6  mov     [rsp+2D0h+var_2A8], rax
0x18007c2cb  lea     r9, aCloudserviceco_10; "CloudServiceController::_SaveOneMessage"
0x18007c2d2  lea     r8, aSDS; "%S(%d):%s"
0x18007c2d9  mov     dword ptr [rsp+2D0h+var_2B0], 4CDh
0x18007c2e1  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x18007c2e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007c2ea  test    eax, eax
0x18007c2ec  js      short loc_18007C341
0x18007c2ee  mov     eax, cs:dword_1800FD5F0
0x18007c2f4  cmp     eax, 4
0x18007c2f7  jbe     short loc_18007C341
0x18007c2f9  mov     rax, [r14+250h]
0x18007c300  lea     rdx, word_1800EEEDA
0x18007c307  mov     [rsp+2D0h+var_260], rax
0x18007c30c  mov     rax, [r14+38h]
0x18007c310  mov     [rsp+2D0h+var_288], rax
0x18007c315  lea     rax, [rbp+1D0h+var_240]
0x18007c319  mov     [rsp+2D0h+var_290], rax
0x18007c31e  lea     rax, [rsp+2D0h+var_260]
0x18007c323  mov     [rsp+2D0h+var_2A0], rax
0x18007c328  lea     rax, [rsp+2D0h+var_288]
0x18007c32d  mov     [rsp+2D0h+var_2A8], rax
0x18007c332  lea     rax, [rsp+2D0h+var_290]
0x18007c337  mov     [rsp+2D0h+var_2B0], rax
0x18007c33c  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18007c341  lea     rdx, [rsp+2D0h+var_260]; struct AsyncMediaServiceDocument **
0x18007c346  mov     [rsp+2D0h+var_260], 0
0x18007c34f  mov     rcx, r14; struct ChatServiceMessage *
0x18007c352  call    ?CreateInstance@AsyncMediaServiceDocument@@SAJPEAVChatServiceMessage@@PEAPEAV1@@Z; AsyncMediaServiceDocument::CreateInstance(ChatServiceMessage *,AsyncMediaServiceDocument * *)
0x18007c357  mov     ebx, eax
0x18007c359  test    eax, eax
0x18007c35b  jns     short loc_18007C37B
0x18007c35d  mov     r9d, 4D1h
0x18007c363  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007c36a  mov     edx, 1
0x18007c36f  mov     ecx, eax; int
0x18007c371  call    Log_HREvent_58
0x18007c376  jmp     loc_18007CA45
0x18007c37b  mov     rdi, [rsp+2D0h+var_260]
0x18007c380  lea     rax, [rsp+2D0h+var_288]
0x18007c385  mov     r8, [r14+250h]; unsigned __int64
0x18007c38c  mov     rdx, [r14+38h]; unsigned __int16 *
0x18007c390  mov     rcx, [r14+58h]; unsigned __int16 *
0x18007c394  mov     r9, [rdi+18h]; unsigned __int16 *
0x18007c398  mov     [rsp+2D0h+var_288], 0
0x18007c3a1  mov     [rsp+2D0h+var_2B0], rax; struct MessageChangeItemRemoteId **
0x18007c3a6  call    ?CreateInstance@MessageChangeItemRemoteId@@SAJPEBG0_K0PEAPEAV1@@Z; MessageChangeItemRemoteId::CreateInstance(ushort const *,ushort const *,unsigned __int64,ushort const *,MessageChangeItemRemoteId * *)
0x18007c3ab  mov     ebx, eax
0x18007c3ad  test    eax, eax
0x18007c3af  jns     short loc_18007C3D9
0x18007c3b1  mov     r9d, 4DAh
0x18007c3b7  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007c3be  mov     edx, 1
0x18007c3c3  mov     ecx, eax; int
0x18007c3c5  call    Log_HREvent_58
0x18007c3ca  lea     rcx, [rsp+2D0h+var_288]
0x18007c3cf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c3d4  jmp     loc_18007CA45
0x18007c3d9  mov     rbx, [rsp+2D0h+var_288]
0x18007c3de  lea     r8, [rsp+2D0h+var_280]; int *
0x18007c3e3  mov     rcx, [r13+40h]; this
0x18007c3e7  mov     rdx, rbx; struct MessageChangeItemRemoteId *
0x18007c3ea  mov     dword ptr [rsp+2D0h+var_280], 0
0x18007c3f2  call    ?FindRemoteChange@MessageChangeTracker@@QEAAJPEAVMessageChangeItemRemoteId@@PEAH@Z; MessageChangeTracker::FindRemoteChange(MessageChangeItemRemoteId *,int *)
0x18007c3f7  mov     r15d, eax
0x18007c3fa  test    eax, eax
0x18007c3fc  jns     short loc_18007C41C
0x18007c3fe  mov     r9d, 4DEh
0x18007c404  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007c40b  mov     edx, 1
0x18007c410  mov     ecx, eax; int
0x18007c412  call    Log_HREvent_58
0x18007c417  jmp     loc_18007CA38
0x18007c41c  xor     r15d, r15d
0x18007c41f  cmp     dword ptr [rsp+2D0h+var_280], r15d
0x18007c424  jz      loc_18007C4E5
0x18007c42a  xor     edx, edx; Val
0x18007c42c  lea     rcx, [rbp+1D0h+var_240]; void *
0x18007c430  mov     r8d, 200h; Size
0x18007c436  call    memset_0
0x18007c43b  lea     rax, aDownloadedMess_0; "Downloaded message dropped because the "...
0x18007c442  mov     edx, 100h; unsigned __int64
0x18007c447  mov     [rsp+2D0h+var_2A8], rax
0x18007c44c  lea     r9, aCloudserviceco_10; "CloudServiceController::_SaveOneMessage"
0x18007c453  lea     r8, aSDS; "%S(%d):%s"
0x18007c45a  mov     dword ptr [rsp+2D0h+var_2B0], 4E7h
0x18007c462  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x18007c466  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007c46b  test    eax, eax
0x18007c46d  js      loc_18007CA38
0x18007c473  mov     eax, cs:dword_1800FD5F0
0x18007c479  cmp     eax, 3
0x18007c47c  jbe     loc_18007CA38
0x18007c482  mov     rax, [rbx+98h]
0x18007c489  lea     rdx, byte_1800EEE61
0x18007c490  mov     [rsp+2D0h+var_290], rax
0x18007c495  mov     rax, [r14+250h]
0x18007c49c  mov     [rsp+2D0h+var_280], rax
0x18007c4a1  mov     rax, [r14+38h]
0x18007c4a5  mov     [rsp+2D0h+var_270], rax
0x18007c4aa  lea     rax, [rbp+1D0h+var_240]
0x18007c4ae  mov     [rsp+2D0h+var_268], rax
0x18007c4b3  lea     rax, [rsp+2D0h+var_290]
0x18007c4b8  mov     [rsp+2D0h+var_298], rax
0x18007c4bd  lea     rax, [rsp+2D0h+var_280]
0x18007c4c2  mov     [rsp+2D0h+var_2A0], rax
0x18007c4c7  lea     rax, [rsp+2D0h+var_270]
0x18007c4cc  mov     [rsp+2D0h+var_2A8], rax
0x18007c4d1  lea     rax, [rsp+2D0h+var_268]
0x18007c4d6  mov     [rsp+2D0h+var_2B0], rax
0x18007c4db  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18007c4e0  jmp     loc_18007CA38
0x18007c4e5  mov     rcx, r14
0x18007c4e8  call    ?get_Type@ChatServiceMessage@@QEBA?AW4Type@1@XZ; ChatServiceMessage::get_Type(void)
0x18007c4ed  mov     [rsp+2D0h+var_290], r15
0x18007c4f2  mov     [rbp+1D0h+var_250], r15d
0x18007c4f6  test    eax, eax
0x18007c4f8  jnz     loc_18007C5AF
0x18007c4fe  xor     edx, edx; Val
0x18007c500  lea     rcx, [rbp+1D0h+var_240]; void *
0x18007c504  mov     r8d, 200h; Size
0x18007c50a  call    memset_0
0x18007c50f  lea     rax, aUnknownInstanc; "Unknown instance message not saved."
0x18007c516  mov     edx, 100h; unsigned __int64
0x18007c51b  mov     [rsp+2D0h+var_2A8], rax
0x18007c520  lea     r9, aCloudserviceco_10; "CloudServiceController::_SaveOneMessage"
0x18007c527  lea     r8, aSDS; "%S(%d):%s"
0x18007c52e  mov     dword ptr [rsp+2D0h+var_2B0], 4F6h
0x18007c536  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x18007c53a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007c53f  test    eax, eax
0x18007c541  js      loc_18007CA2E
0x18007c547  mov     eax, cs:dword_1800FD5F0
0x18007c54d  cmp     eax, 3
0x18007c550  jbe     loc_18007CA2E
0x18007c556  mov     rax, [rbx+98h]
0x18007c55d  lea     rdx, unk_1800EEDE8
0x18007c564  mov     [rsp+2D0h+var_268], rax
0x18007c569  mov     rax, [r14+250h]
0x18007c570  mov     [rsp+2D0h+var_270], rax
0x18007c575  mov     rax, [r14+38h]
0x18007c579  mov     [rsp+2D0h+var_280], rax
0x18007c57e  lea     rax, [rbp+1D0h+var_240]
0x18007c582  mov     [rsp+2D0h+var_278], rax
0x18007c587  lea     rax, [rsp+2D0h+var_268]
0x18007c58c  mov     [rsp+2D0h+var_298], rax
0x18007c591  lea     rax, [rsp+2D0h+var_270]
0x18007c596  mov     [rsp+2D0h+var_2A0], rax
0x18007c59b  lea     rax, [rsp+2D0h+var_280]
0x18007c5a0  mov     [rsp+2D0h+var_2A8], rax
0x18007c5a5  lea     rax, [rsp+2D0h+var_278]
0x18007c5aa  jmp     loc_18007CA24
0x18007c5af  cmp     eax, 3
0x18007c5b2  jnz     loc_18007C6A9
0x18007c5b8  lea     r9, aCloudserviceco_10; "CloudServiceController::_SaveOneMessage"
0x18007c5bf  mov     edx, 100h; unsigned __int64
0x18007c5c4  lea     r8, aSDS; "%S(%d):%s"
0x18007c5cb  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x18007c5cf  cmp     [r14+250h], r15
0x18007c5d6  jnz     short loc_18007C624
0x18007c5d8  lea     rax, aReceiveADeleti_0; "Receive a deletion marker without Clien"...
0x18007c5df  mov     [rsp+2D0h+var_2A8], rax
0x18007c5e4  mov     dword ptr [rsp+2D0h+var_2B0], 501h
0x18007c5ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007c5f1  mov     eax, cs:dword_1800FD5F0
0x18007c5f7  cmp     eax, 4
0x18007c5fa  jbe     loc_18007CA2E
0x18007c600  lea     rax, [rbp+1D0h+var_240]
0x18007c604  mov     [rsp+2D0h+var_278], rax
0x18007c609  lea     rdx, word_1800EED6E
0x18007c610  lea     rax, [rsp+2D0h+var_278]
0x18007c615  mov     [rsp+2D0h+var_2B0], rax
0x18007c61a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007c61f  jmp     loc_18007CA2E
0x18007c624  lea     rax, aReceiveADeleti; "Receive a deletion marker from service"
0x18007c62b  mov     [rsp+2D0h+var_2A8], rax
0x18007c630  mov     dword ptr [rsp+2D0h+var_2B0], 505h
0x18007c638  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007c63d  mov     eax, cs:dword_1800FD5F0
0x18007c643  cmp     eax, 4
0x18007c646  jbe     short loc_18007C667
0x18007c648  lea     rax, [rbp+1D0h+var_240]
0x18007c64c  mov     [rsp+2D0h+var_278], rax
0x18007c651  lea     rdx, byte_1800EEDAB
0x18007c658  lea     rax, [rsp+2D0h+var_278]
0x18007c65d  mov     [rsp+2D0h+var_2B0], rax
0x18007c662  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007c667  mov     rdx, [r14+250h]; unsigned __int64
0x18007c66e  mov     rcx, [r13+50h]; this
0x18007c672  call    ?TombstoneMessage@MessageSaver@@QEAAJ_K@Z; MessageSaver::TombstoneMessage(unsigned __int64)
0x18007c677  mov     ebx, eax
0x18007c679  test    eax, eax
0x18007c67b  jns     loc_18007CA2E
0x18007c681  mov     r9d, 506h
0x18007c687  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007c68e  mov     edx, 1
0x18007c693  mov     ecx, eax; int
0x18007c695  call    Log_HREvent_58
0x18007c69a  lea     rcx, [rsp+2D0h+var_290]
0x18007c69f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c6a4  jmp     loc_18007C3CA
0x18007c6a9  cmp     eax, 1
0x18007c6ac  jnz     loc_18007C75F
0x18007c6b2  lea     rax, aReceiveATextMe; "Receive a text message from service"
0x18007c6b9  mov     edx, 100h; unsigned __int64
0x18007c6be  mov     [rsp+2D0h+var_2A8], rax
0x18007c6c3  lea     r9, aCloudserviceco_10; "CloudServiceController::_SaveOneMessage"
0x18007c6ca  lea     r8, aSDS; "%S(%d):%s"
0x18007c6d1  mov     dword ptr [rsp+2D0h+var_2B0], 50Dh
0x18007c6d9  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x18007c6dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007c6e2  mov     eax, cs:dword_1800FD5F0
0x18007c6e8  cmp     eax, 4
0x18007c6eb  jbe     short loc_18007C70C
0x18007c6ed  lea     rax, [rbp+1D0h+var_240]
0x18007c6f1  mov     [rsp+2D0h+var_278], rax
0x18007c6f6  lea     rdx, byte_1800EED31
0x18007c6fd  lea     rax, [rsp+2D0h+var_278]
0x18007c702  mov     [rsp+2D0h+var_2B0], rax
0x18007c707  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007c70c  mov     rcx, [r13+50h]; this
0x18007c710  lea     r9, [rbp+1D0h+var_250]; enum MessageCreationResult *
0x18007c714  lea     r8, [rsp+2D0h+var_290]; struct ISmEntryId **
0x18007c719  mov     rdx, r14; struct ChatServiceMessage *
0x18007c71c  call    ?SaveTextMessage@MessageSaver@@QEAAJPEAVChatServiceMessage@@PEAPEAUISmEntryId@@PEAW4MessageCreationResult@@@Z; MessageSaver::SaveTextMessage(ChatServiceMessage *,ISmEntryId * *,MessageCreationResult *)
0x18007c721  mov     edi, eax
0x18007c723  test    eax, eax
0x18007c725  jns     loc_18007C83B
0x18007c72b  mov     r9d, 50Eh
0x18007c731  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007c738  mov     edx, 1
0x18007c73d  mov     ecx, edi; int
0x18007c73f  call    Log_HREvent_58
0x18007c744  lea     rcx, [rsp+2D0h+var_290]
0x18007c749  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c74e  lea     rcx, [rsp+2D0h+var_288]
0x18007c753  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c758  mov     ebx, edi
0x18007c75a  jmp     loc_18007CA45
0x18007c75f  cmp     eax, 2
0x18007c762  jnz     loc_18007C980
0x18007c768  xor     edx, edx; Val
0x18007c76a  lea     rcx, [rbp+1D0h+var_240]; void *
0x18007c76e  mov     r8d, 200h; Size
0x18007c774  call    memset_0
0x18007c779  lea     rax, aReceiveAMultim; "Receive a multimedia message from servi"...
0x18007c780  mov     edx, 100h; unsigned __int64
0x18007c785  mov     [rsp+2D0h+var_2A8], rax
0x18007c78a  lea     r9, aCloudserviceco_10; "CloudServiceController::_SaveOneMessage"
0x18007c791  lea     r8, aSDS; "%S(%d):%s"
0x18007c798  mov     dword ptr [rsp+2D0h+var_2B0], 514h
0x18007c7a0  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x18007c7a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007c7a9  test    eax, eax
0x18007c7ab  js      short loc_18007C7E8
0x18007c7ad  mov     eax, cs:dword_1800FD5F0
0x18007c7b3  cmp     eax, 4
0x18007c7b6  jbe     short loc_18007C7E8
0x18007c7b8  mov     eax, [rdi+50h]
0x18007c7bb  lea     rdx, dword_1800EECE4
0x18007c7c2  mov     dword ptr [rsp+2D0h+var_280], eax
0x18007c7c6  lea     rax, [rbp+1D0h+var_240]
0x18007c7ca  mov     [rsp+2D0h+var_278], rax
0x18007c7cf  lea     rax, [rsp+2D0h+var_280]
0x18007c7d4  mov     [rsp+2D0h+var_2A8], rax
0x18007c7d9  lea     rax, [rsp+2D0h+var_278]
0x18007c7de  mov     [rsp+2D0h+var_2B0], rax
0x18007c7e3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18007c7e8  mov     rdx, r14; struct ChatServiceMessage *
0x18007c7eb  mov     rcx, [r13+50h]; this
0x18007c7ef  cmp     [rdi+50h], r15d
0x18007c7f3  jnz     short loc_18007C81C
0x18007c7f5  lea     rax, [rbp+1D0h+var_250]
0x18007c7f9  mov     r8, rdi; struct AsyncMediaServiceDocument *
0x18007c7fc  lea     r9, [rsp+2D0h+var_290]; struct ISmEntryId **
0x18007c801  mov     [rsp+2D0h+var_2B0], rax; enum MessageCreationResult *
0x18007c806  call    ?SaveMultimediaMessage@MessageSaver@@QEAAJPEAVChatServiceMessage@@PEAVAsyncMediaServiceDocument@@PEAPEAUISmEntryId@@PEAW4MessageCreationResult@@@Z; MessageSaver::SaveMultimediaMessage(ChatServiceMessage *,AsyncMediaServiceDocument *,ISmEntryId * *,MessageCreationResult *)
0x18007c80b  mov     edi, eax
0x18007c80d  test    eax, eax
  ... truncated ...
```
