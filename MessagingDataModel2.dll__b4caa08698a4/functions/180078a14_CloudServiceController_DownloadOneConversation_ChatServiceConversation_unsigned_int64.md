# CloudServiceController::_DownloadOneConversation(ChatServiceConversation *,unsigned __int64)

- ea: `0x180078a14`
- end: `0x1800795c9`
- name: `?_DownloadOneConversation@CloudServiceController@@AEAAJPEAVChatServiceConversation@@_K@Z`
- size: `2997`
- prototype: `__int64 __fastcall(CloudServiceController *__hidden this, struct ChatServiceConversation *, unsigned __int64)`
- caller_count: `1`
- callee_count: `42`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800798bc`

## callees

- `0x180001198`
- `0x1800011c8`
- `0x1800016a0`
- `0x180001f50`
- `0x1800026bc`
- `0x180002b58`
- `0x180002c54`
- `0x180002fc0`
- `0x180004d18`
- `0x180004d60`
- `0x180004dd0`
- `0x180005c50`
- `0x1800065c8`
- `0x180008870`
- `0x1800088c4`
- `0x18000b7fc`
- `0x18000bf4c`
- `0x180015050`
- `0x180017a70`
- `0x180024224`
- `0x1800242c4`
- `0x180046c98`
- `0x180046fbc`
- `0x18004c28c`
- `0x180075cc0`
- `0x180075f3c`
- `0x1800760fc`
- `0x1800767a0`
- `0x1800774d0`
- `0x180078a14`
- `0x1800795d0`
- `0x18007c274`
- `0x18007dbe0`
- `0x1800807c8`
- `0x1800836d0`
- `0x180083cac`
- `0x180084e28`
- `0x1800852d8`
- `0x18009648c`
- `0x1800964ec`
- `0x1800c6902`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180078bcf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180079039`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007916c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180078bcf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180079039`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007916c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078d95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078dac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078d95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078dac`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180078db7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180078db7`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180078d9e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180078d9e`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x180078fdf`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x1800792e1`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x180079472`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x180078fdf`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x1800792e1`
- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x180079472`

## string_xrefs

- `0x180079245`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007928e`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x1800792b2`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x180079328`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007933f`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x180079450`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x180079510`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007953d`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x180078a75`: `CloudServiceController::_DownloadOneConversation`
- `0x180078b4d`: `CloudServiceController::_DownloadOneConversation`
- `0x180078cc4`: `CloudServiceController::_DownloadOneConversation`
- `0x180078f4a`: `CloudServiceController::_DownloadOneConversation`
- `0x180079379`: `CloudServiceController::_DownloadOneConversation`
- `0x1800794b6`: `CloudServiceController::_DownloadOneConversation`

## pseudocode

```c
__int64 __fastcall CloudServiceController::_DownloadOneConversation(
        CloudServiceController *this,
        struct IUnknown *a2,
        unsigned __int64 a3)
{
  struct ISmEntryId *v3; // rsi
  struct IUnknown *v4; // rdi
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  int v10; // r13d
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  DWORD TickCount; // eax
  __int64 v18; // rcx
  int ConversationSyncState; // ebx
  __m128i si128; // xmm6
  const OLECHAR *v21; // r15
  struct IUnknownVtbl *lpVtbl; // rdx
  __int64 v23; // rcx
  int v24; // eax
  struct ChatServiceMessage **v25; // rdi
  __int64 v26; // rbx
  __int64 v27; // rsi
  __int64 v28; // rcx
  __int64 v29; // rcx
  HANDLE CurrentThread; // rax
  HANDLE v31; // rax
  int started; // eax
  struct IUnknown *v33; // r15
  struct ChatServiceMessage **v34; // rbx
  DWORD v35; // r12d
  int v36; // eax
  int v37; // esi
  struct IUnknown **v38; // rcx
  struct ChatServiceMessage *v39; // rdx
  int v40; // eax
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  int v45; // eax
  struct ChatServiceMessage **v46; // rbx
  unsigned __int64 v47; // r15
  int v48; // eax
  int v49; // r8d
  __int64 v50; // rsi
  DWORD v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  int v56; // eax
  int v57; // ecx
  __int64 v58; // rcx
  int v60; // eax
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // r9
  ULONG v64[2]; // [rsp+28h] [rbp-E0h]
  ULONG v65[2]; // [rsp+28h] [rbp-E0h]
  __int64 *v66; // [rsp+28h] [rbp-E0h]
  unsigned __int16 *v67; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v68; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v69; // [rsp+58h] [rbp-B0h] BYREF
  DWORD v70; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 *v71; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v72; // [rsp+70h] [rbp-98h]
  const OLECHAR *v73; // [rsp+78h] [rbp-90h] BYREF
  struct IUnknown *v74; // [rsp+80h] [rbp-88h]
  unsigned __int64 v75; // [rsp+88h] [rbp-80h]
  enum _PRIORITY_HINT v76; // [rsp+90h] [rbp-78h] BYREF
  int v77; // [rsp+94h] [rbp-74h]
  int v78; // [rsp+98h] [rbp-70h] BYREF
  struct ISmEntryId *v79; // [rsp+A0h] [rbp-68h] BYREF
  const OLECHAR *v80; // [rsp+A8h] [rbp-60h] BYREF
  const OLECHAR *v81; // [rsp+B0h] [rbp-58h]
  __int16 v82; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v83; // [rsp+BAh] [rbp-4Eh]
  int v84; // [rsp+C2h] [rbp-46h]
  __int16 v85; // [rsp+C6h] [rbp-42h]
  __m128i v86; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v87; // [rsp+D8h] [rbp-30h]
  __m128i v88; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v89; // [rsp+F0h] [rbp-18h]
  unsigned __int16 *v90; // [rsp+F8h] [rbp-10h] BYREF
  __int16 *v91; // [rsp+100h] [rbp-8h]
  __int16 v92; // [rsp+108h] [rbp+0h] BYREF
  __int64 v93; // [rsp+10Ah] [rbp+2h]
  int v94; // [rsp+112h] [rbp+Ah]
  __int16 v95; // [rsp+116h] [rbp+Eh]
  __int64 v96; // [rsp+118h] [rbp+10h] BYREF
  char v97[8]; // [rsp+120h] [rbp+18h] BYREF
  _QWORD v98[2]; // [rsp+128h] [rbp+20h] BYREF
  __int16 v99; // [rsp+138h] [rbp+30h] BYREF
  __int64 v100; // [rsp+13Ah] [rbp+32h]
  int v101; // [rsp+142h] [rbp+3Ah]
  __int16 v102; // [rsp+146h] [rbp+3Eh]
  struct _EVENT_DATA_DESCRIPTOR v103; // [rsp+148h] [rbp+40h] BYREF
  __int64 *v104; // [rsp+168h] [rbp+60h]
  __int64 v105; // [rsp+170h] [rbp+68h]
  unsigned __int16 **v106; // [rsp+178h] [rbp+70h]
  __int64 v107; // [rsp+180h] [rbp+78h]
  DWORD *v108; // [rsp+188h] [rbp+80h]
  __int64 v109; // [rsp+190h] [rbp+88h]
  __int64 *v110; // [rsp+198h] [rbp+90h]
  __int64 v111; // [rsp+1A0h] [rbp+98h]
  unsigned __int16 v112[256]; // [rsp+1A8h] [rbp+A0h] BYREF

  v75 = a3;
  v3 = (struct ISmEntryId *)a3;
  v74 = a2;
  v4 = a2;
  StringCchPrintfW(v112, 0x100u, L"%S(%d):%s", "CloudServiceController::_DownloadOneConversation", 1052, L"Enter");
  if ( (unsigned int)dword_1800FD5F0 > 5 )
  {
    v79 = (struct ISmEntryId *)v112;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v6,
      (int)word_1800EF262,
      v7,
      v8,
      (const OLECHAR **)&v79);
  }
  v9 = (unsigned int)tls_index;
  v10 = 0;
  v98[0] = &v99;
  v98[1] = &v99;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v12 = ThreadLocalStoragePointer[tls_index];
  v99 = 0;
  if ( dword_1800FE9B8 > *(_DWORD *)(v12 + 4) )
  {
    Init_thread_header(&dword_1800FE9B8);
    if ( dword_1800FE9B8 == -1 )
    {
      atexit(CloudServiceController::_DownloadOneConversation_::_2_::_dynamic_atexit_destructor_for__s_lastSyncedMessageIds__);
      Init_thread_footer(&dword_1800FE9B8);
    }
  }
  v13 = qword_1800FDC78 - qword_1800FDC70;
  qword_1800FDC78 = qword_1800FDC70;
  utl::_RangeDestroyApc<utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
    v9,
    qword_1800FDC70,
    v13 >> 5);
  memset_0(v112, 0, sizeof(v112));
  v64[0] = 1060;
  if ( (int)StringCchPrintfW(
              v112,
              0x100u,
              L"%S(%d):%s",
              "CloudServiceController::_DownloadOneConversation",
              *(_QWORD *)v64,
              L"Start download the messages of one conversation") >= 0
    && (unsigned int)dword_1800FD5F0 > 4 )
  {
    v79 = v3;
    v67 = v112;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v14,
      (unsigned int)word_1800EF20A,
      v15,
      v16,
      (__int64)&v67,
      (__int64)&v79);
  }
  v83 = 0;
  v80 = (const OLECHAR *)&v82;
  v81 = (const OLECHAR *)&v82;
  v84 = 0;
  v85 = 0;
  v82 = 0;
  TickCount = GetTickCount();
  v18 = *((_QWORD *)this + 9);
  v70 = TickCount;
  v78 = 0;
  ConversationSyncState = ConversationAccessor::GetConversationSyncState(v18, v4, &v80, &v78);
  if ( ConversationSyncState < 0 )
  {
LABEL_94:
    Log_HREvent_58(ConversationSyncState);
    goto LABEL_95;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  while ( 1 )
  {
    if ( !v78 )
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        &v80,
        v98);
    v21 = v80;
    v23 = *((_QWORD *)this + 6);
    if ( v80 == v81 )
      v21 = 0;
    lpVtbl = v4[7].lpVtbl;
    v90 = (unsigned __int16 *)&v92;
    v89 = -1;
    v91 = &v92;
    v88 = si128;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v92 = 0;
    v24 = ChatServiceClient::DownloadConversation(
            v23,
            (_DWORD)lpVtbl,
            (_DWORD)v3,
            (_DWORD)v21,
            20,
            (__int64)&v88,
            (__int64)&v90);
    ConversationSyncState = v24;
    if ( v24 < 0 )
    {
LABEL_92:
      Log_HREvent_58(v24);
      goto LABEL_93;
    }
    v25 = (struct ChatServiceMessage **)v88.m128i_i64[1];
    v26 = v88.m128i_i64[1] - v88.m128i_i64[0];
    v27 = (v88.m128i_i64[1] - v88.m128i_i64[0]) >> 3;
    *((_DWORD *)this + 46) += v27;
    memset_0(v112, 0, sizeof(v112));
    v65[0] = 1095;
    if ( (int)StringCchPrintfW(
                v112,
                0x100u,
                L"%S(%d):%s",
                "CloudServiceController::_DownloadOneConversation",
                *(_QWORD *)v65,
                L"Download Messages in One Conversation") >= 0
      && (unsigned int)dword_1800FD5F0 > 4 )
    {
      v71 = v90;
      v69 = (__int64)v112;
      v66 = &v69;
      v73 = v21;
      LODWORD(v68) = v27;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v28,
        &unk_1800EF158);
    }
    if ( v26 != 160 )
    {
      if ( v26 )
        goto LABEL_22;
      LODWORD(v66) = 1123;
      StringCchPrintfW(
        v112,
        0x100u,
        L"%S(%d):%s",
        "CloudServiceController::_DownloadOneConversation",
        v66,
        L"Zero message was received, the sync client shall return early");
      if ( (unsigned int)dword_1800FD5F0 > 4 )
      {
        v69 = (__int64)v112;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v61,
          (int)word_1800EF112,
          v62,
          v63,
          (const OLECHAR **)&v69);
      }
LABEL_91:
      ConversationSyncState = 0;
      goto LABEL_93;
    }
    if ( (unsigned int)_AreIdListEqual<ATL::CComPtr<ChatServiceMessage>>(v88.m128i_i64) )
    {
      if ( (unsigned int)dword_1800FD5F0 > 2 && (unsigned __int8)tlgKeywordOn(v29, 0x200000000000LL) )
      {
        LODWORD(v68) = *((_DWORD *)this + 40);
        v69 = (__int64)"InfiniteDownloadingMessages";
        v73 = (const OLECHAR *)((char *)this + 136);
        LODWORD(v71) = -2147467260;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v53,
          (int)byte_1800EF0C9,
          v54,
          v55,
          (__int64 *)&v73,
          (const unsigned __int16 **)&v69,
          (__int64)&v68,
          (__int64)&v71);
      }
      goto LABEL_91;
    }
    v24 = _SaveIdListToVector<ATL::CComPtr<ChatServiceMessage>>(v88.m128i_i64);
    ConversationSyncState = v24;
    if ( v24 < 0 )
      goto LABEL_92;
    v25 = (struct ChatServiceMessage **)v88.m128i_i64[1];
LABEL_22:
    v86 = si128;
    v87 = -1;
    HIDWORD(v67) = 0;
    CurrentThread = GetCurrentThread();
    LODWORD(v67) = GetThreadPriority(CurrentThread);
    if ( (_DWORD)v67 )
    {
      v31 = GetCurrentThread();
      HIDWORD(v67) = SetThreadPriority(v31, 0);
    }
    v77 = 0;
    started = auto_iopriority::ChangePriority((auto_iopriority *)&v76, IoPriorityHintNormal);
    ConversationSyncState = started;
    if ( started < 0 )
      break;
    started = MessageChangeTracker::StartSyncSession(*((MessageChangeTracker **)this + 8));
    ConversationSyncState = started;
    if ( started < 0 )
      break;
    v33 = v74;
    v34 = (struct ChatServiceMessage **)v88.m128i_i64[0];
    v35 = 0;
    v72 = 1;
    v71 = (unsigned __int16 *)this;
    while ( v34 != v25 )
    {
      v36 = ChatServiceMessage::put_Participants(*v34, &v33[21]);
      v37 = v36;
      if ( v36 < 0 )
      {
        Log_HREvent_58(v36);
        goto LABEL_70;
      }
      v38 = (struct IUnknown **)((char *)*v34 + 496);
      if ( *v38 != v33 )
        ATL::AtlComPtrAssign(v38, v33);
      v39 = *v34;
      v79 = 0;
      v40 = CloudServiceController::_SaveOneMessage(this, v39, &v79);
      v37 = v40;
      if ( v40 < 0 )
      {
        Log_HREvent_58(v40);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
LABEL_70:
        tlx::_UndoSolo__lambda_0850e548dd4e893481926ca4186b9d50___::__UndoSolo__lambda_0850e548dd4e893481926ca4186b9d50___(&v71);
        if ( v77 )
        {
          v77 = 0;
          v56 = SetThreadIOPriority(v76, 0);
          if ( v56 < 0 )
            Log_HREvent_21(v56);
        }
        auto_threadpriority::Reset((auto_threadpriority *)&v67);
LABEL_74:
        utl::vector<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>,utl::allocator<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>>>::_Uninit(&v86);
        ConversationSyncState = v37;
        goto LABEL_93;
      }
      if ( v79 )
      {
        ATL::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>(
          &v96,
          *v34);
        ATL::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>(
          v97,
          v79);
        if ( !utl::vector<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>,utl::allocator<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>>>::emplace_back<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>> &,0>(
                &v86,
                &v96) )
        {
          ConversationSyncState = -2147024882;
          Log_HREvent_58(-2147024882);
          utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>::~pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>(&v96);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
LABEL_66:
          tlx::_UndoSolo__lambda_0850e548dd4e893481926ca4186b9d50___::__UndoSolo__lambda_0850e548dd4e893481926ca4186b9d50___(&v71);
          if ( !v77 )
            goto LABEL_88;
          v77 = 0;
          goto LABEL_86;
        }
        if ( (unsigned int)ChatServiceMessage::get_Type(v96) == 2 )
        {
          ++v35;
        }
        else if ( (unsigned int)ChatServiceMessage::get_Type(v96) == 1 )
        {
          ++v10;
        }
        utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>::~pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>(&v96);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
      ++v34;
    }
    v41 = ConversationAccessor::SetConversationSyncState(
            *((ConversationAccessor **)this + 9),
            (struct ChatServiceConversation *)v33,
            v90,
            &v78);
    ConversationSyncState = v41;
    if ( v41 < 0 )
    {
LABEL_82:
      v57 = v41;
      goto LABEL_76;
    }
    if ( !v78 )
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v98,
                               v90,
                               ((char *)v91 - (char *)v90) >> 1) )
      {
        ConversationSyncState = -2147024882;
        v57 = -2147024882;
LABEL_76:
        Log_HREvent_58(v57);
        goto LABEL_66;
      }
      memset_0(v112, 0, sizeof(v112));
      LODWORD(v66) = 1183;
      if ( (int)StringCchPrintfW(
                  v112,
                  0x100u,
                  L"%S(%d):%s",
                  "CloudServiceController::_DownloadOneConversation",
                  v66,
                  L"can't persist the sync state without a saved conversation") >= 0
        && (unsigned int)dword_1800FD5F0 > 3 )
      {
        v69 = v98[0];
        v73 = v112;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v42,
          (int)&byte_1800EF05F,
          v43,
          v44,
          &v73,
          (const OLECHAR **)&v69);
      }
    }
    v41 = MessageChangeTracker::CommitSyncSession(*((MessageChangeTracker **)this + 8));
    ConversationSyncState = v41;
    if ( v41 < 0 )
      goto LABEL_82;
    LOBYTE(v72) = 0;
    tlx::_UndoSolo__lambda_0850e548dd4e893481926ca4186b9d50___::__UndoSolo__lambda_0850e548dd4e893481926ca4186b9d50___(&v71);
    if ( v77 )
    {
      v77 = 0;
      v45 = SetThreadIOPriority(v76, 0);
      if ( v45 < 0 )
        Log_HREvent_21(v45);
    }
    auto_threadpriority::Reset((auto_threadpriority *)&v67);
    v46 = (struct ChatServiceMessage **)v86.m128i_i64[0];
    v47 = v75;
    while ( v46 != (struct ChatServiceMessage **)v86.m128i_i64[1] )
    {
      v48 = CloudServiceController::_DownloadOneMessage(this, *v46, v46[1], v47);
      v37 = v48;
      if ( v48 < 0 )
      {
        Log_HREvent_58(v48);
        goto LABEL_74;
      }
      v46 += 2;
    }
    GetTickCount();
    if ( (unsigned int)dword_1800FD5F0 > 4
      && (unsigned __int8)tlgKeywordOn((unsigned int)dword_1800FD5F0, 0x200000000000LL) )
    {
      v50 = v88.m128i_i64[0];
      LODWORD(v68) = v49 - v70;
      LODWORD(v71) = v10;
      v10 = 0;
      v69 = ((__int64)v25 - v88.m128i_i64[0]) >> 3;
      v70 = v35;
      v110 = &v68;
      v111 = 4;
      v108 = &v70;
      v106 = &v71;
      v104 = &v69;
      v109 = 4;
      v107 = 4;
      v105 = 8;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_1800FD5F0, (int)&byte_1800EEF37, 0, 0, 6u, &v103);
    }
    else
    {
      v50 = v88.m128i_i64[0];
      v10 = 0;
    }
    if ( (unsigned __int64)(((__int64)v25 - v50) >> 3) < 0x14 )
    {
      memset_0(v112, 0, sizeof(v112));
      LODWORD(v66) = 1215;
      if ( (int)StringCchPrintfW(
                  v112,
                  0x100u,
                  L"%S(%d):%s",
                  "CloudServiceController::_DownloadOneConversation",
                  v66,
                  L"All Messages in this conversation is downloaded") >= 0
        && (unsigned int)dword_1800FD5F0 > 4 )
      {
        v69 = (__int64)v90;
        LODWORD(v71) = *((_DWORD *)this + 46);
        v73 = v112;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v58,
          word_1800EEFCA);
      }
      utl::vector<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>,utl::allocator<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>>>::_Uninit(&v86);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v90);
      utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&v88);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v80);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v98);
      return 0;
    }
    utl::vector<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>,utl::allocator<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>>>::_Uninit(&v86);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v90);
    utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&v88);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v80);
    v83 = 0;
    v80 = (const OLECHAR *)&v82;
    v81 = (const OLECHAR *)&v82;
    v84 = 0;
    v85 = 0;
    v82 = 0;
    v51 = GetTickCount();
    v4 = v74;
    v52 = *((_QWORD *)this + 9);
    v70 = v51;
    v78 = 0;
    ConversationSyncState = ConversationAccessor::GetConversationSyncState(v52, v74, &v80, &v78);
    if ( ConversationSyncState < 0 )
      goto LABEL_94;
    LODWORD(v3) = v47;
  }
  Log_HREvent_58(started);
  if ( v77 )
  {
    v77 = 0;
LABEL_86:
    v60 = SetThreadIOPriority(v76, 0);
    if ( v60 < 0 )
      Log_HREvent_21(v60);
  }
LABEL_88:
  auto_threadpriority::Reset((auto_threadpriority *)&v67);
  utl::vector<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>,utl::allocator<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>>>::_Uninit(&v86);
LABEL_93:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v90);
  utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&v88);
LABEL_95:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v80);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v98);
  return (unsigned int)ConversationSyncState;
}

```

## disassembly

```asm
0x180078a14  mov     rax, rsp
0x180078a17  mov     [rax+20h], rbx
0x180078a1b  push    rbp
0x180078a1c  push    rsi
0x180078a1d  push    rdi
0x180078a1e  push    r12
0x180078a20  push    r13
0x180078a22  push    r14
0x180078a24  push    r15
0x180078a26  lea     rbp, [rax-2F8h]
0x180078a2d  sub     rsp, 3C0h
0x180078a34  movaps  xmmword ptr [rax-48h], xmm6
0x180078a38  mov     rax, cs:__security_cookie
0x180078a3f  xor     rax, rsp
0x180078a42  mov     [rbp+2F0h+var_50], rax
0x180078a49  lea     rax, aEnter; "Enter"
0x180078a50  mov     [rbp+2F0h+var_370], r8
0x180078a54  mov     rsi, r8
0x180078a57  mov     [rsp+3F0h+var_378], rdx
0x180078a5c  mov     rdi, rdx
0x180078a5f  mov     [rsp+3F0h+var_3C8], rax
0x180078a64  mov     r14, rcx
0x180078a67  mov     [rsp+3F0h+var_3D0], 41Ch
0x180078a6f  mov     r12d, 100h
0x180078a75  lea     r9, aCloudserviceco_14; "CloudServiceController::_DownloadOneCon"...
0x180078a7c  mov     edx, r12d; unsigned __int64
0x180078a7f  lea     r8, aSDS; "%S(%d):%s"
0x180078a86  lea     rcx, [rbp+2F0h+var_250]; unsigned __int16 *
0x180078a8d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078a92  mov     eax, cs:dword_1800FD5F0
0x180078a98  cmp     eax, 5
0x180078a9b  jbe     short loc_180078ABD
0x180078a9d  lea     rax, [rbp+2F0h+var_250]
0x180078aa4  mov     [rbp+2F0h+var_358], rax
0x180078aa8  lea     rdx, word_1800EF262
0x180078aaf  lea     rax, [rbp+2F0h+var_358]
0x180078ab3  mov     qword ptr [rsp+3F0h+var_3D0], rax
0x180078ab8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180078abd  mov     ecx, cs:_tls_index
0x180078ac3  lea     rax, [rbp+2F0h+var_2C0]
0x180078ac7  xor     r13d, r13d
0x180078aca  mov     [rbp+2F0h+var_2D0], rax
0x180078ace  lea     rax, [rbp+2F0h+var_2C0]
0x180078ad2  mov     edx, 4
0x180078ad7  mov     [rbp+2F0h+var_2C8], rax
0x180078adb  mov     rax, gs:58h
0x180078ae4  mov     [rbp+2F0h+var_2BE], r13
0x180078ae8  mov     [rbp+2F0h+var_2B6], r13d
0x180078aec  mov     [rbp+2F0h+var_2B2], r13w
0x180078af1  mov     rax, [rax+rcx*8]
0x180078af5  mov     [rbp+2F0h+var_2C0], r13w
0x180078afa  mov     eax, [rdx+rax]
0x180078afd  cmp     cs:dword_1800FE9B8, eax
0x180078b03  jg      loc_180079593
0x180078b09  mov     rdx, cs:qword_1800FDC70
0x180078b10  mov     r8, cs:qword_1800FDC78
0x180078b17  sub     r8, rdx
0x180078b1a  mov     cs:qword_1800FDC78, rdx
0x180078b21  sar     r8, 5
0x180078b25  call    ??$_RangeDestroyApc@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@0@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,unsigned __int64)
0x180078b2a  xor     edx, edx; Val
0x180078b2c  lea     rcx, [rbp+2F0h+var_250]; void *
0x180078b33  mov     r8d, 200h; Size
0x180078b39  call    memset_0
0x180078b3e  lea     rax, aStartDownloadT; "Start download the messages of one conv"...
0x180078b45  mov     rdx, r12; unsigned __int64
0x180078b48  mov     [rsp+3F0h+var_3C8], rax
0x180078b4d  lea     r9, aCloudserviceco_14; "CloudServiceController::_DownloadOneCon"...
0x180078b54  lea     r8, aSDS; "%S(%d):%s"
0x180078b5b  mov     [rsp+3F0h+var_3D0], 424h
0x180078b63  lea     rcx, [rbp+2F0h+var_250]; unsigned __int16 *
0x180078b6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078b6f  test    eax, eax
0x180078b71  js      short loc_180078BAD
0x180078b73  mov     eax, cs:dword_1800FD5F0
0x180078b79  cmp     eax, 4
0x180078b7c  jbe     short loc_180078BAD
0x180078b7e  lea     rax, [rbp+2F0h+var_250]
0x180078b85  mov     [rbp+2F0h+var_358], rsi
0x180078b89  mov     qword ptr [rsp+3F0h+var_3B0], rax
0x180078b8e  lea     rdx, word_1800EF20A
0x180078b95  lea     rax, [rbp+2F0h+var_358]
0x180078b99  mov     [rsp+3F0h+var_3C8], rax
0x180078b9e  lea     rax, [rsp+3F0h+var_3B0]
0x180078ba3  mov     qword ptr [rsp+3F0h+var_3D0], rax
0x180078ba8  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180078bad  lea     rax, [rbp+2F0h+var_340]
0x180078bb1  mov     [rbp+2F0h+var_33E], r13
0x180078bb5  mov     [rbp+2F0h+var_350], rax
0x180078bb9  lea     rax, [rbp+2F0h+var_340]
0x180078bbd  mov     [rbp+2F0h+var_348], rax
0x180078bc1  mov     [rbp+2F0h+var_336], r13d
0x180078bc5  mov     [rbp+2F0h+var_332], r13w
0x180078bca  mov     [rbp+2F0h+var_340], r13w
0x180078bcf  call    cs:__imp_GetTickCount
0x180078bd5  mov     rcx, [r14+48h]
0x180078bd9  lea     r9, [rbp+2F0h+var_360]
0x180078bdd  lea     r8, [rbp+2F0h+var_350]
0x180078be1  mov     dword ptr [rsp+3F0h+var_398], eax
0x180078be5  mov     rdx, rdi
0x180078be8  mov     [rbp+2F0h+var_360], r13d
0x180078bec  call    ?GetConversationSyncState@ConversationAccessor@@QEAAJPEAVChatServiceConversation@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAH@Z; ConversationAccessor::GetConversationSyncState(ChatServiceConversation *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,int *)
0x180078bf1  mov     ebx, eax
0x180078bf3  test    eax, eax
0x180078bf5  js      loc_180079537
0x180078bfb  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180078c03  cmp     [rbp+2F0h+var_360], r13d
0x180078c07  jnz     short loc_180078C16
0x180078c09  lea     rdx, [rbp+2F0h+var_2D0]
0x180078c0d  lea     rcx, [rbp+2F0h+var_350]
0x180078c11  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180078c16  mov     r15, [rbp+2F0h+var_350]
0x180078c1a  lea     rax, [rbp+2F0h+var_2F0]
0x180078c1e  cmp     r15, [rbp+2F0h+var_348]
0x180078c22  mov     r8, rsi
0x180078c25  mov     rdx, [rdi+38h]
0x180078c29  mov     rcx, [r14+30h]
0x180078c2d  cmovz   r15, r13
0x180078c31  mov     [rbp+2F0h+var_300], rax
0x180078c35  mov     r9, r15
0x180078c38  lea     rax, [rbp+2F0h+var_2F0]
0x180078c3c  mov     [rbp+2F0h+var_308], 0FFFFFFFFFFFFFFFFh
0x180078c44  mov     [rbp+2F0h+var_2F8], rax
0x180078c48  lea     rax, [rbp+2F0h+var_300]
0x180078c4c  mov     [rsp+3F0h+var_3C0], rax
0x180078c51  lea     rax, [rbp+2F0h+var_318]
0x180078c55  mov     [rsp+3F0h+var_3C8], rax
0x180078c5a  mov     [rsp+3F0h+var_3D0], 14h
0x180078c62  movdqu  [rbp+2F0h+var_318], xmm6
0x180078c67  mov     [rbp+2F0h+var_2EE], r13
0x180078c6b  mov     [rbp+2F0h+var_2E6], r13d
0x180078c6f  mov     [rbp+2F0h+var_2E2], r13w
0x180078c74  mov     [rbp+2F0h+var_2F0], r13w
0x180078c79  call    ?DownloadConversation@ChatServiceClient@@QEAAJPEBG_K0IPEAV?$vector@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceMessage@@@ATL@@@utl@@@utl@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@3@@Z; ChatServiceClient::DownloadConversation(ushort const *,unsigned __int64,ushort const *,uint,utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180078c7e  mov     ebx, eax
0x180078c80  test    eax, eax
0x180078c82  js      loc_18007950A
0x180078c88  mov     rdi, qword ptr [rbp+2F0h+var_318+8]
0x180078c8c  lea     rcx, [rbp+2F0h+var_250]; void *
0x180078c93  mov     rbx, rdi
0x180078c96  xor     edx, edx; Val
0x180078c98  sub     rbx, qword ptr [rbp+2F0h+var_318]
0x180078c9c  mov     r8d, 200h; Size
0x180078ca2  mov     rsi, rbx
0x180078ca5  sar     rsi, 3
0x180078ca9  add     [r14+0B8h], esi
0x180078cb0  call    memset_0
0x180078cb5  lea     rax, aDownloadMessag; "Download Messages in One Conversation"
0x180078cbc  mov     rdx, r12; unsigned __int64
0x180078cbf  mov     [rsp+3F0h+var_3C8], rax
0x180078cc4  lea     r9, aCloudserviceco_14; "CloudServiceController::_DownloadOneCon"...
0x180078ccb  lea     r8, aSDS; "%S(%d):%s"
0x180078cd2  mov     [rsp+3F0h+var_3D0], 447h
0x180078cda  lea     rcx, [rbp+2F0h+var_250]; unsigned __int16 *
0x180078ce1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078ce6  test    eax, eax
0x180078ce8  js      short loc_180078D47
0x180078cea  mov     eax, cs:dword_1800FD5F0
0x180078cf0  cmp     eax, 4
0x180078cf3  jbe     short loc_180078D47
0x180078cf5  mov     rax, [rbp+2F0h+var_300]
0x180078cf9  lea     rdx, unk_1800EF158
0x180078d00  mov     qword ptr [rsp+3F0h+var_398+8], rax
0x180078d05  lea     rax, [rbp+2F0h+var_250]
0x180078d0c  mov     [rsp+3F0h+var_3A0], rax
0x180078d11  lea     rax, [rsp+3F0h+var_398+8]
0x180078d16  mov     [rsp+3F0h+var_3B8], rax
0x180078d1b  lea     rax, [rsp+3F0h+var_380]
0x180078d20  mov     [rsp+3F0h+var_3C0], rax
0x180078d25  lea     rax, [rsp+3F0h+var_3A8]
0x180078d2a  mov     [rsp+3F0h+var_3C8], rax
0x180078d2f  lea     rax, [rsp+3F0h+var_3A0]
0x180078d34  mov     qword ptr [rsp+3F0h+var_3D0], rax
0x180078d39  mov     [rsp+3F0h+var_380], r15
0x180078d3e  mov     dword ptr [rsp+3F0h+var_3A8], esi
0x180078d42  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180078d47  cmp     rbx, 0A0h
0x180078d4e  jnz     short loc_180078D7A
0x180078d50  lea     rcx, [rbp+2F0h+var_318]
0x180078d54  call    ??$_AreIdListEqual@V?$CComPtr@VChatServiceMessage@@@ATL@@@@YAHAEBV?$vector@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceMessage@@@ATL@@@utl@@@utl@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@1@@Z; _AreIdListEqual<ATL::CComPtr<ChatServiceMessage>>(utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>> const &,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x180078d59  test    eax, eax
0x180078d5b  jnz     loc_1800791B6
0x180078d61  lea     rcx, [rbp+2F0h+var_318]
0x180078d65  call    ??$_SaveIdListToVector@V?$CComPtr@VChatServiceMessage@@@ATL@@@@YAJAEBV?$vector@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceMessage@@@ATL@@@utl@@@utl@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@1@@Z; _SaveIdListToVector<ATL::CComPtr<ChatServiceMessage>>(utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>> const &,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x180078d6a  mov     ebx, eax
0x180078d6c  test    eax, eax
0x180078d6e  js      loc_1800791AB
0x180078d74  mov     rdi, qword ptr [rbp+2F0h+var_318+8]
0x180078d78  jmp     short loc_180078D83
0x180078d7a  test    rbx, rbx
0x180078d7d  jz      loc_1800794A7
0x180078d83  movdqu  [rbp+2F0h+var_330], xmm6
0x180078d88  mov     [rbp+2F0h+var_320], 0FFFFFFFFFFFFFFFFh
0x180078d90  mov     [rsp+3F0h+var_3AC], r13d
0x180078d95  call    cs:__imp_GetCurrentThread
0x180078d9b  mov     rcx, rax; hThread
0x180078d9e  call    cs:__imp_GetThreadPriority
0x180078da4  mov     [rsp+3F0h+var_3B0], eax
0x180078da8  test    eax, eax
0x180078daa  jz      short loc_180078DC1
0x180078dac  call    cs:__imp_GetCurrentThread
0x180078db2  mov     rcx, rax; hThread
0x180078db5  xor     edx, edx; nPriority
0x180078db7  call    cs:__imp_SetThreadPriority
0x180078dbd  mov     [rsp+3F0h+var_3AC], eax
0x180078dc1  mov     edx, 2; enum _PRIORITY_HINT
0x180078dc6  mov     [rbp+2F0h+var_364], r13d
0x180078dca  lea     rcx, [rbp+2F0h+var_368]; this
0x180078dce  call    ?ChangePriority@auto_iopriority@@QEAAJW4_PRIORITY_HINT@@@Z; auto_iopriority::ChangePriority(_PRIORITY_HINT)
0x180078dd3  mov     ebx, eax
0x180078dd5  test    eax, eax
0x180078dd7  js      loc_18007944A
0x180078ddd  mov     rcx, [r14+40h]; this
0x180078de1  call    ?StartSyncSession@MessageChangeTracker@@QEAAJXZ; MessageChangeTracker::StartSyncSession(void)
0x180078de6  mov     ebx, eax
0x180078de8  test    eax, eax
0x180078dea  js      loc_180079442
0x180078df0  mov     r15, [rsp+3F0h+var_378]
0x180078df5  xorps   xmm0, xmm0
0x180078df8  mov     rbx, qword ptr [rbp+2F0h+var_318]
0x180078dfc  mov     r12d, r13d
0x180078dff  movups  [rsp+3F0h+var_398+8], xmm0
0x180078e04  mov     qword ptr [rsp+3F0h+var_398+8], r14
0x180078e09  xor     esi, esi
0x180078e0b  mov     byte ptr [rsp+3F0h+var_388], 1
0x180078e10  cmp     rbx, rdi
0x180078e13  jz      loc_180078EDF
0x180078e19  mov     rcx, [rbx]
0x180078e1c  lea     rdx, [r15+0A8h]
0x180078e23  call    ?put_Participants@ChatServiceMessage@@QEAAJPEBV?$vector@V?$CComPtr@VChatServiceParticipant@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceParticipant@@@ATL@@@utl@@@utl@@@Z; ChatServiceMessage::put_Participants(utl::vector<ATL::CComPtr<ChatServiceParticipant>,utl::allocator<ATL::CComPtr<ChatServiceParticipant>>> const *)
0x180078e28  mov     esi, eax
0x180078e2a  test    eax, eax
0x180078e2c  js      loc_1800792AC
0x180078e32  mov     rcx, [rbx]
0x180078e35  add     rcx, 1F0h; struct IUnknown **
0x180078e3c  cmp     [rcx], r15
0x180078e3f  jz      short loc_180078E49
0x180078e41  mov     rdx, r15; struct IUnknown *
0x180078e44  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180078e49  mov     rdx, [rbx]; struct ChatServiceMessage *
0x180078e4c  lea     r8, [rbp+2F0h+var_358]; struct ISmEntryId **
0x180078e50  mov     rcx, r14; this
0x180078e53  mov     [rbp+2F0h+var_358], 0
0x180078e5b  call    ?_SaveOneMessage@CloudServiceController@@AEAAJPEAVChatServiceMessage@@PEAPEAUISmEntryId@@@Z; CloudServiceController::_SaveOneMessage(ChatServiceMessage *,ISmEntryId * *)
0x180078e60  mov     esi, eax
0x180078e62  test    eax, eax
0x180078e64  js      loc_180079288
0x180078e6a  xor     esi, esi
0x180078e6c  cmp     [rbp+2F0h+var_358], rsi
0x180078e70  jz      short loc_180078ECD
0x180078e72  mov     rdx, [rbx]
0x180078e75  lea     rcx, [rbp+2F0h+var_2E0]
0x180078e79  call    ??0?$CComPtrBase@VAsyncMediaServiceCommitDocumentTransaction@@@ATL@@IEAA@PEAVAsyncMediaServiceCommitDocumentTransaction@@@Z; ATL::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>(AsyncMediaServiceCommitDocumentTransaction *)
0x180078e7e  mov     rdx, [rbp+2F0h+var_358]
0x180078e82  lea     rcx, [rbp+2F0h+var_2D8]
0x180078e86  call    ??0?$CComPtrBase@VAsyncMediaServiceCommitDocumentTransaction@@@ATL@@IEAA@PEAVAsyncMediaServiceCommitDocumentTransaction@@@Z; ATL::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>(AsyncMediaServiceCommitDocumentTransaction *)
0x180078e8b  lea     rdx, [rbp+2F0h+var_2E0]
0x180078e8f  lea     rcx, [rbp+2F0h+var_330]
0x180078e93  call    ??$emplace_back@AEAU?$pair@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$CComPtr@UISmEntryId@@@2@@utl@@$0A@@?$vector@U?$pair@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$CComPtr@UISmEntryId@@@2@@utl@@V?$allocator@U?$pair@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$CComPtr@UISmEntryId@@@2@@utl@@@2@@utl@@QEAA_NAEAU?$pair@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$CComPtr@UISmEntryId@@@2@@1@@Z; utl::vector<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>,utl::allocator<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>>>::emplace_back<utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>> &,0>(utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>> &)
0x180078e98  test    al, al
0x180078e9a  jz      loc_180079240
0x180078ea0  mov     rcx, [rbp+2F0h+var_2E0]
0x180078ea4  call    ?get_Type@ChatServiceMessage@@QEBA?AW4Type@1@XZ; ChatServiceMessage::get_Type(void)
0x180078ea9  cmp     eax, 2
0x180078eac  jnz     short loc_180078EB3
0x180078eae  inc     r12d
0x180078eb1  jmp     short loc_180078EC4
0x180078eb3  mov     rcx, [rbp+2F0h+var_2E0]
0x180078eb7  call    ?get_Type@ChatServiceMessage@@QEBA?AW4Type@1@XZ; ChatServiceMessage::get_Type(void)
0x180078ebc  cmp     eax, 1
0x180078ebf  jnz     short loc_180078EC4
0x180078ec1  inc     r13d
0x180078ec4  lea     rcx, [rbp+2F0h+var_2E0]
0x180078ec8  call    ??1?$pair@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$CComPtr@UISmEntryId@@@2@@utl@@QEAA@XZ; utl::pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>::~pair<ATL::CComPtr<ChatServiceMessage>,ATL::CComPtr<ISmEntryId>>(void)
0x180078ecd  lea     rcx, [rbp+2F0h+var_358]
0x180078ed1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180078ed6  add     rbx, 8
0x180078eda  jmp     loc_180078E10
0x180078edf  mov     r8, [rbp+2F0h+var_300]; unsigned __int16 *
0x180078ee3  lea     r9, [rbp+2F0h+var_360]; int *
0x180078ee7  mov     rcx, [r14+48h]; this
0x180078eeb  mov     rdx, r15; struct ChatServiceConversation *
0x180078eee  call    ?SetConversationSyncState@ConversationAccessor@@QEAAJPEAVChatServiceConversation@@PEBGPEAH@Z; ConversationAccessor::SetConversationSyncState(ChatServiceConversation *,ushort const *,int *)
0x180078ef3  mov     ebx, eax
0x180078ef5  test    eax, eax
0x180078ef7  js      loc_18007943A
0x180078efd  cmp     [rbp+2F0h+var_360], esi
0x180078f00  jnz     loc_180078FB0
0x180078f06  mov     r8, [rbp+2F0h+var_2F8]
0x180078f0a  lea     rcx, [rbp+2F0h+var_2D0]
0x180078f0e  mov     rdx, [rbp+2F0h+var_300]
0x180078f12  sub     r8, rdx
0x180078f15  sar     r8, 1
0x180078f18  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180078f1d  xor     edx, edx; Val
0x180078f1f  test    al, al
0x180078f21  jz      loc_18007931B
0x180078f27  mov     r8d, 200h; Size
0x180078f2d  lea     rcx, [rbp+2F0h+var_250]; void *
0x180078f34  call    memset_0
  ... truncated ...
```
