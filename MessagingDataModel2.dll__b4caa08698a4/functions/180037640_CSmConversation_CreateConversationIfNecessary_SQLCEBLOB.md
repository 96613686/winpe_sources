# CSmConversation::CreateConversationIfNecessary(_SQLCEBLOB *)

- ea: `0x180037640`
- end: `0x180037afd`
- name: `?CreateConversationIfNecessary@CSmConversation@@UEAAJPEAU_SQLCEBLOB@@@Z`
- size: `1213`
- prototype: `__int64 __fastcall(CSmConversation *__hidden this, struct _SQLCEBLOB *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800014d4`
- `0x180005c50`
- `0x18000a4a8`
- `0x18000be18`
- `0x18000c434`
- `0x180012e34`
- `0x1800179ac`
- `0x180032848`
- `0x180032f9c`
- `0x180033a84`
- `0x180037064`
- `0x1800372f8`
- `0x180037640`
- `0x18003afb4`
- `0x18003afe4`
- `0x18003e8ec`
- `0x18003fe50`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037aae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037ac1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037aae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037ac1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037771`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037771`
- `CEMAPI!MAPIFreeBuffer` at `0x1800376f6`
- `CEMAPI!MAPIFreeBuffer` at `0x1800379a8`
- `CEMAPI!MAPIFreeBuffer` at `0x180037a09`
- `CEMAPI!MAPIFreeBuffer` at `0x180037a45`
- `CEMAPI!MAPIFreeBuffer` at `0x1800376f6`
- `CEMAPI!MAPIFreeBuffer` at `0x1800379a8`
- `CEMAPI!MAPIFreeBuffer` at `0x180037a09`
- `CEMAPI!MAPIFreeBuffer` at `0x180037a45`
- `CEMAPI!HrGetOneProp` at `0x1800376da`
- `CEMAPI!HrGetOneProp` at `0x180037978`
- `CEMAPI!HrGetOneProp` at `0x1800376da`
- `CEMAPI!HrGetOneProp` at `0x180037978`

## string_xrefs

- `0x18003770b`: `[Messaging] CSmConversation: Recreating deleted conversation`

## pseudocode

```c
__int64 __fastcall CSmConversation::CreateConversationIfNecessary(CSmConversation *this, struct _SQLCEBLOB *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  struct ISmStore *v6; // rcx
  LPVOID v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  BOOL v10; // ebx
  void **v11; // rax
  HRESULT OneProp; // eax
  HRESULT Instance; // eax
  unsigned int v14; // ebx
  int v15; // ecx
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // xmm0_8
  __int64 *v21; // r9
  int v22; // eax
  struct ISmConversation *v23; // rbx
  HRESULT MapiConversation; // esi
  __int64 v25; // xmm0_8
  __int64 v26; // rdx
  void **v27; // rax
  int v28; // eax
  void *v29; // rcx
  const unsigned __int8 *v30; // r8
  unsigned int v31; // edx
  int v32; // eax
  unsigned __int8 v34; // [rsp+28h] [rbp-51h]
  HLOCAL hMem[2]; // [rsp+40h] [rbp-39h] BYREF
  LPMAPIPROP lpMapiProp; // [rsp+50h] [rbp-29h] BYREF
  const char *v37; // [rsp+58h] [rbp-21h] BYREF
  __int64 v38; // [rsp+60h] [rbp-19h] BYREF
  int v39; // [rsp+68h] [rbp-11h]
  LPVOID pv; // [rsp+70h] [rbp-9h] BYREF
  LPVOID v41; // [rsp+78h] [rbp-1h] BYREF
  struct IUnknown *ppv; // [rsp+80h] [rbp+7h] BYREF
  struct IUnknown *v43[2]; // [rsp+88h] [rbp+Fh] BYREF
  __int128 v44; // [rsp+98h] [rbp+1Fh]

  if ( !CSmStoreTransaction::IsOwned(this) )
  {
    Log_AssertionEvent_14(v5, v4, 1166);
    if ( !CSmStoreTransaction::IsOwned(v6) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  lpMapiProp = 0;
  if ( *((_QWORD *)this + 8) )
  {
    if ( (int)CSmConversation::_GetMapiConversation(this, (struct IMAPIConversation **)&lpMapiProp) < 0 )
      goto LABEL_11;
    pv = 0;
    v10 = 0;
    v11 = tlx::replace<_SPropValue *,unsigned long (*)(void *),&unsigned long MAPIFreeBuffer(void *),0>(&pv);
    OneProp = HrGetOneProp(lpMapiProp, 0x82D6000B, (LPSPropValue *)v11);
    v7 = pv;
    if ( OneProp >= 0 )
      v10 = *((_WORD *)pv + 4) != 0;
    if ( pv )
      MAPIFreeBuffer(pv);
    if ( v10 )
    {
LABEL_11:
      if ( (unsigned int)dword_1800FD5F0 > 4 )
      {
        v37 = "[Messaging] CSmConversation: Recreating deleted conversation";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (__int64)v7,
          (int)&byte_1800EA5CF,
          v8,
          v9,
          (const unsigned __int16 **)&v37);
      }
      ATL::CComPtrBase<ConversationAccessor>::Release((char *)this + 64);
    }
    if ( *((_QWORD *)this + 8) )
      goto LABEL_44;
  }
  pv = 0;
  ppv = 0;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  Instance = CoCreateInstance(&CLSID_Application, 0, 0x17u, &GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d, (LPVOID *)&ppv);
  v14 = Instance;
  if ( Instance < 0 )
  {
    Log_HREvent_15(Instance);
LABEL_40:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    MessagingThreading::~MessagingThreading((MessagingThreading *)v43);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pv);
    goto LABEL_47;
  }
  *(_OWORD *)hMem = 0;
  if ( !Comms::ptr_olApp::assign((struct IUnknown **)hMem, ppv) )
  {
    v14 = -2147467259;
    v15 = -2147467259;
LABEL_19:
    Log_HREvent_15(v15);
LABEL_39:
    Comms::ptr_olApp::~ptr_olApp((Comms::ptr_olApp *)hMem);
    goto LABEL_40;
  }
  v16 = MessagingThreading::Initialize(v43, *((struct IUnknown **)this + 9), ppv);
  v14 = v16;
  if ( v16 < 0 )
  {
LABEL_21:
    v15 = v16;
    goto LABEL_19;
  }
  if ( *((_DWORD *)this + 57) )
  {
    v19 = *(_QWORD *)this;
    v37 = (const char *)this;
    (*(void (__fastcall **)(CSmConversation *))(v19 + 8))(this);
    v20 = *((_QWORD *)this + 25);
    v21 = (__int64 *)*((_QWORD *)this + 15);
    v39 = *((_DWORD *)this + 52);
    v34 = *((_BYTE *)this + 166);
    v38 = v20;
    v22 = MessagingThreading::CreateConversationInDatabase(
            (__int64)v43,
            this,
            (__int64)this + 168,
            v21,
            &v38,
            v34,
            (unsigned __int64 *)((char *)this + 220),
            (struct ISmConversation **)&pv);
    v14 = v22;
    if ( v22 < 0 )
    {
      Log_HREvent_15(v22);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
      goto LABEL_39;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
  }
  else
  {
    v25 = *((_QWORD *)this + 25);
    LOBYTE(v18) = *((_BYTE *)this + 165);
    LOBYTE(v17) = *((_BYTE *)this + 166);
    v26 = *((_QWORD *)this + 15);
    v39 = *((_DWORD *)this + 52);
    v38 = v25;
    v16 = MessagingThreading::CreateConversation(v43, v26, v17, v18, &v38, (char *)this + 220, &pv);
    v14 = v16;
    if ( v16 < 0 )
      goto LABEL_21;
  }
  v23 = (struct ISmConversation *)pv;
  MapiConversation = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)pv + 88LL))(pv, (char *)this + 64);
  if ( MapiConversation < 0
    || (MapiConversation = CSmConversation::_GetMapiConversation(this, (struct IMAPIConversation **)&lpMapiProp),
        MapiConversation < 0) )
  {
    Log_HREvent_15(MapiConversation);
LABEL_28:
    Comms::ptr_olApp::~ptr_olApp((Comms::ptr_olApp *)hMem);
    v14 = MapiConversation;
    goto LABEL_40;
  }
  v41 = 0;
  v27 = tlx::replace<_SPropValue *,unsigned long (*)(void *),&unsigned long MAPIFreeBuffer(void *),0>(&v41);
  MapiConversation = HrGetOneProp(lpMapiProp, 0x30130102u, (LPSPropValue *)v27);
  if ( MapiConversation < 0
    || (MapiConversation = CAutoBlob::Set(
                             (CSmConversation *)((char *)this + 184),
                             *((_DWORD *)v41 + 2),
                             *((const unsigned __int8 *const *)v41 + 2)),
        MapiConversation < 0) )
  {
    Log_HREvent_15(MapiConversation);
    if ( v41 )
      MAPIFreeBuffer(v41);
    goto LABEL_28;
  }
  v28 = CSmConversation::CopyConversationProperties(this, v23);
  v14 = v28;
  if ( v28 < 0 )
  {
    Log_HREvent_15(v28);
    if ( v41 )
      MAPIFreeBuffer(v41);
    goto LABEL_39;
  }
  v29 = v41;
  *((_BYTE *)this + 96) = 0;
  if ( v29 )
    MAPIFreeBuffer(v29);
  Comms::ptr_olApp::~ptr_olApp((Comms::ptr_olApp *)hMem);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  MessagingThreading::~MessagingThreading((MessagingThreading *)v43);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pv);
LABEL_44:
  v30 = (const unsigned __int8 *)*((_QWORD *)this + 24);
  v31 = *((_DWORD *)this + 46);
  LODWORD(hMem[0]) = 0;
  hMem[1] = 0;
  v32 = CAutoBlob::Set((CAutoBlob *)hMem, v31, v30);
  v14 = v32;
  if ( v32 >= 0 )
  {
    *(_OWORD *)a2 = *(_OWORD *)hMem;
    LocalFree(0);
    v14 = 0;
  }
  else
  {
    Log_HREvent_15(v32);
    LocalFree(hMem[1]);
  }
LABEL_47:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpMapiProp);
  return v14;
}

```

## disassembly

```asm
0x180037640  mov     [rsp-8+arg_10], rbx
0x180037645  mov     [rsp-8+arg_18], rsi
0x18003764a  push    rbp
0x18003764b  push    rdi
0x18003764c  push    r12
0x18003764e  push    r14
0x180037650  push    r15
0x180037652  lea     rbp, [rsp-37h]
0x180037657  sub     rsp, 0B0h
0x18003765e  mov     rax, cs:__security_cookie
0x180037665  xor     rax, rsp
0x180037668  mov     [rbp+57h+var_28], rax
0x18003766c  mov     r14, rdx
0x18003766f  mov     rdi, rcx
0x180037672  call    ?IsOwned@CSmStoreTransaction@@SA_NPEAUISmStore@@@Z; CSmStoreTransaction::IsOwned(ISmStore *)
0x180037677  xor     r15d, r15d
0x18003767a  test    al, al
0x18003767c  jnz     short loc_180037697
0x18003767e  mov     r8d, 48Eh
0x180037684  call    Log_AssertionEvent_14
0x180037689  call    ?IsOwned@CSmStoreTransaction@@SA_NPEAUISmStore@@@Z; CSmStoreTransaction::IsOwned(ISmStore *)
0x18003768e  test    al, al
0x180037690  jnz     short loc_180037697
0x180037692  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180037697  lea     rsi, [rdi+40h]
0x18003769b  mov     [rbp+57h+lpMapiProp], r15
0x18003769f  mov     r12d, 1
0x1800376a5  cmp     [rsi], r15
0x1800376a8  jz      loc_18003773C
0x1800376ae  lea     rdx, [rbp+57h+lpMapiProp]; struct IMAPIConversation **
0x1800376b2  mov     rcx, rdi; this
0x1800376b5  call    ?_GetMapiConversation@CSmConversation@@IEAAJPEAPEAUIMAPIConversation@@@Z; CSmConversation::_GetMapiConversation(IMAPIConversation * *)
0x1800376ba  test    eax, eax
0x1800376bc  js      short loc_180037700
0x1800376be  lea     rcx, [rbp+57h+pv]
0x1800376c2  mov     [rbp+57h+pv], r15
0x1800376c6  mov     ebx, r15d
0x1800376c9  call    ??$replace@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@tlx@@YAPEAPEAU_SPropValue@@AEAV?$auto_xxx@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@0@@Z; tlx::replace<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0>(tlx::auto_xxx<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0> &)
0x1800376ce  mov     rcx, [rbp+57h+lpMapiProp]; lpMapiProp
0x1800376d2  mov     r8, rax; lppProp
0x1800376d5  mov     edx, 82D6000Bh; ulPropTag
0x1800376da  call    cs:__imp_HrGetOneProp
0x1800376e0  mov     rcx, [rbp+57h+pv]; pv
0x1800376e4  test    eax, eax
0x1800376e6  js      short loc_1800376F1
0x1800376e8  cmp     [rcx+8], r15w
0x1800376ed  cmovnz  ebx, r12d
0x1800376f1  test    rcx, rcx
0x1800376f4  jz      short loc_1800376FC
0x1800376f6  call    cs:__imp_MAPIFreeBuffer
0x1800376fc  test    ebx, ebx
0x1800376fe  jz      short loc_180037733
0x180037700  mov     eax, cs:dword_1800FD5F0
0x180037706  cmp     eax, 4
0x180037709  jbe     short loc_18003772B
0x18003770b  lea     rax, aMessagingCsmco; "[Messaging] CSmConversation: Recreating"...
0x180037712  mov     [rbp+57h+var_78], rax
0x180037716  lea     rdx, byte_1800EA5CF
0x18003771d  lea     rax, [rbp+57h+var_78]
0x180037721  mov     [rsp+0D0h+ppv], rax
0x180037726  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003772b  mov     rcx, rsi
0x18003772e  call    ?Release@?$CComPtrBase@VConversationAccessor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ConversationAccessor>::Release(void)
0x180037733  cmp     [rsi], r15
0x180037736  jnz     loc_180037A6F
0x18003773c  xor     edx, edx; pUnkOuter
0x18003773e  mov     [rbp+57h+pv], r15
0x180037742  xorps   xmm0, xmm0
0x180037745  mov     [rbp+57h+var_50], r15
0x180037749  xorps   xmm1, xmm1
0x18003774c  lea     rax, [rbp+57h+var_50]
0x180037750  lea     r9, _GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d; riid
0x180037757  mov     [rsp+0D0h+ppv], rax; ppv
0x18003775c  lea     r8d, [rdx+17h]; dwClsContext
0x180037760  lea     rcx, CLSID_Application; rclsid
0x180037767  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x18003776c  movdqu  [rbp+57h+var_38], xmm1
0x180037771  call    cs:__imp_CoCreateInstance
0x180037777  mov     ebx, eax
0x180037779  test    eax, eax
0x18003777b  jns     short loc_180037799
0x18003777d  mov     r9d, 4BBh
0x180037783  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003778a  mov     edx, r12d
0x18003778d  mov     ecx, eax; int
0x18003778f  call    Log_HREvent_15
0x180037794  jmp     loc_180037A18
0x180037799  mov     rdx, [rbp+57h+var_50]; struct IUnknown *
0x18003779d  lea     rcx, [rbp+57h+hMem]; this
0x1800377a1  xorps   xmm0, xmm0
0x1800377a4  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x1800377a8  call    ?assign@ptr_olApp@Comms@@QEAA_NPEAUIPOutlookApp3@@@Z; Comms::ptr_olApp::assign(IPOutlookApp3 *)
0x1800377ad  test    al, al
0x1800377af  jnz     short loc_1800377D1
0x1800377b1  mov     ebx, 80004005h
0x1800377b6  mov     r9d, 4BFh
0x1800377bc  mov     ecx, ebx; int
0x1800377be  xor     edx, edx
0x1800377c0  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800377c7  call    Log_HREvent_15
0x1800377cc  jmp     loc_180037A0F
0x1800377d1  mov     r8, [rbp+57h+var_50]; struct IUnknown *
0x1800377d5  lea     rcx, [rbp+57h+var_48]; this
0x1800377d9  mov     rdx, [rdi+48h]; struct IUnknown *
0x1800377dd  call    ?Initialize@MessagingThreading@@QEAAJPEAUISmStorePriv@@PEAUIPOutlookApp3@@@Z; MessagingThreading::Initialize(ISmStorePriv *,IPOutlookApp3 *)
0x1800377e2  mov     ebx, eax
0x1800377e4  test    eax, eax
0x1800377e6  jns     short loc_1800377F5
0x1800377e8  mov     r9d, 4C1h
0x1800377ee  mov     edx, r12d
0x1800377f1  mov     ecx, eax
0x1800377f3  jmp     short loc_1800377C0
0x1800377f5  lea     rbx, [rdi+0DCh]
0x1800377fc  cmp     [rdi+0E4h], r15d
0x180037803  jz      loc_1800378E5
0x180037809  mov     rax, [rdi]
0x18003780c  mov     rcx, rdi
0x18003780f  mov     [rbp+57h+var_78], rdi
0x180037813  mov     rax, [rax+8]
0x180037817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003781c  mov     eax, [rdi+0D0h]
0x180037822  lea     r8, [rdi+0A8h]
0x180037829  movsd   xmm0, qword ptr [rdi+0C8h]
0x180037831  lea     rcx, [rbp+57h+var_48]
0x180037835  mov     r9, [rdi+78h]
0x180037839  mov     rdx, rdi
0x18003783c  mov     [rbp+57h+var_68], eax
0x18003783f  lea     rax, [rbp+57h+pv]
0x180037843  mov     [rsp+0D0h+var_98], rax
0x180037848  mov     al, [rdi+0A6h]
0x18003784e  mov     [rsp+0D0h+var_A0], rbx
0x180037853  mov     byte ptr [rsp+0D0h+var_A8], al
0x180037857  lea     rax, [rbp+57h+var_70]
0x18003785b  mov     [rsp+0D0h+ppv], rax
0x180037860  movsd   [rbp+57h+var_70], xmm0
0x180037865  call    ?CreateConversationInDatabase@MessagingThreading@@QEAAJPEAUISmConversation@@AEAVCAutoBlob@@PEAVISmRecipientCollectionPriv@@UOLITEMID@@_NAEBU_FILETIME@@PEAPEAU2@@Z; MessagingThreading::CreateConversationInDatabase(ISmConversation *,CAutoBlob &,ISmRecipientCollectionPriv *,OLITEMID,bool,_FILETIME const &,ISmConversation * *)
0x18003786a  mov     ebx, eax
0x18003786c  test    eax, eax
0x18003786e  jns     short loc_180037895
0x180037870  mov     r9d, 4C9h
0x180037876  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003787d  mov     edx, r12d
0x180037880  mov     ecx, eax; int
0x180037882  call    Log_HREvent_15
0x180037887  lea     rcx, [rbp+57h+var_78]
0x18003788b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037890  jmp     loc_180037A0F
0x180037895  lea     rcx, [rbp+57h+var_78]
0x180037899  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003789e  mov     rbx, [rbp+57h+pv]
0x1800378a2  mov     rdx, rsi
0x1800378a5  mov     rcx, rbx
0x1800378a8  mov     rax, [rbx]
0x1800378ab  mov     rax, [rax+58h]
0x1800378af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378b4  mov     esi, eax
0x1800378b6  test    eax, eax
0x1800378b8  jns     loc_180037942
0x1800378be  mov     r9d, 4D1h
0x1800378c4  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800378cb  mov     edx, r12d
0x1800378ce  mov     ecx, esi; int
0x1800378d0  call    Log_HREvent_15
0x1800378d5  lea     rcx, [rbp+57h+hMem]; this
0x1800378d9  call    ??1ptr_olApp@Comms@@QEAA@XZ; Comms::ptr_olApp::~ptr_olApp(void)
0x1800378de  mov     ebx, esi
0x1800378e0  jmp     loc_180037A18
0x1800378e5  mov     eax, [rdi+0D0h]
0x1800378eb  lea     rcx, [rbp+57h+var_48]
0x1800378ef  movsd   xmm0, qword ptr [rdi+0C8h]
0x1800378f7  mov     r9b, [rdi+0A5h]
0x1800378fe  mov     r8b, [rdi+0A6h]
0x180037905  mov     rdx, [rdi+78h]
0x180037909  mov     [rbp+57h+var_68], eax
0x18003790c  lea     rax, [rbp+57h+pv]
0x180037910  mov     [rsp+0D0h+var_A0], rax
0x180037915  lea     rax, [rbp+57h+var_70]
0x180037919  mov     [rsp+0D0h+var_A8], rbx
0x18003791e  mov     [rsp+0D0h+ppv], rax
0x180037923  movsd   [rbp+57h+var_70], xmm0
0x180037928  call    ?CreateConversation@MessagingThreading@@QEAAJPEAVISmRecipientCollectionPriv@@_N1UOLITEMID@@AEBU_FILETIME@@PEAPEAUISmConversation@@@Z; MessagingThreading::CreateConversation(ISmRecipientCollectionPriv *,bool,bool,OLITEMID,_FILETIME const &,ISmConversation * *)
0x18003792d  mov     ebx, eax
0x18003792f  test    eax, eax
0x180037931  jns     loc_18003789E
0x180037937  mov     r9d, 4CEh
0x18003793d  jmp     loc_1800377EE
0x180037942  lea     rdx, [rbp+57h+lpMapiProp]; struct IMAPIConversation **
0x180037946  mov     rcx, rdi; this
0x180037949  call    ?_GetMapiConversation@CSmConversation@@IEAAJPEAPEAUIMAPIConversation@@@Z; CSmConversation::_GetMapiConversation(IMAPIConversation * *)
0x18003794e  mov     esi, eax
0x180037950  test    eax, eax
0x180037952  jns     short loc_18003795F
0x180037954  mov     r9d, 4D2h
0x18003795a  jmp     loc_1800378C4
0x18003795f  lea     rcx, [rbp+57h+var_58]
0x180037963  mov     [rbp+57h+var_58], r15
0x180037967  call    ??$replace@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@tlx@@YAPEAPEAU_SPropValue@@AEAV?$auto_xxx@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@0@@Z; tlx::replace<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0>(tlx::auto_xxx<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0> &)
0x18003796c  mov     rcx, [rbp+57h+lpMapiProp]; lpMapiProp
0x180037970  mov     r8, rax; lppProp
0x180037973  mov     edx, 30130102h; ulPropTag
0x180037978  call    cs:__imp_HrGetOneProp
0x18003797e  mov     esi, eax
0x180037980  test    eax, eax
0x180037982  jns     short loc_1800379B3
0x180037984  mov     r9d, 4D5h
0x18003798a  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x180037991  mov     edx, r12d
0x180037994  mov     ecx, esi; int
0x180037996  call    Log_HREvent_15
0x18003799b  mov     rcx, [rbp+57h+var_58]; pv
0x18003799f  test    rcx, rcx
0x1800379a2  jz      loc_1800378D5
0x1800379a8  call    cs:__imp_MAPIFreeBuffer
0x1800379ae  jmp     loc_1800378D5
0x1800379b3  mov     rdx, [rbp+57h+var_58]
0x1800379b7  lea     rcx, [rdi+0B8h]; this
0x1800379be  mov     r8, [rdx+10h]; unsigned __int8 *
0x1800379c2  mov     edx, [rdx+8]; unsigned int
0x1800379c5  call    ?Set@CAutoBlob@@QEAAJKQEBE@Z; CAutoBlob::Set(ulong,uchar const * const)
0x1800379ca  mov     esi, eax
0x1800379cc  test    eax, eax
0x1800379ce  jns     short loc_1800379D8
0x1800379d0  mov     r9d, 4D6h
0x1800379d6  jmp     short loc_18003798A
0x1800379d8  mov     rdx, rbx; struct ISmConversation *
0x1800379db  mov     rcx, rdi; this
0x1800379de  call    ?CopyConversationProperties@CSmConversation@@AEAAJPEAUISmConversation@@@Z; CSmConversation::CopyConversationProperties(ISmConversation *)
0x1800379e3  mov     ebx, eax
0x1800379e5  test    eax, eax
0x1800379e7  jns     short loc_180037A38
0x1800379e9  mov     r9d, 4D8h
0x1800379ef  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800379f6  mov     edx, r12d
0x1800379f9  mov     ecx, eax; int
0x1800379fb  call    Log_HREvent_15
0x180037a00  mov     rcx, [rbp+57h+var_58]; pv
0x180037a04  test    rcx, rcx
0x180037a07  jz      short loc_180037A0F
0x180037a09  call    cs:__imp_MAPIFreeBuffer
0x180037a0f  lea     rcx, [rbp+57h+hMem]; this
0x180037a13  call    ??1ptr_olApp@Comms@@QEAA@XZ; Comms::ptr_olApp::~ptr_olApp(void)
0x180037a18  lea     rcx, [rbp+57h+var_50]
0x180037a1c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037a21  lea     rcx, [rbp+57h+var_48]; this
0x180037a25  call    ??1MessagingThreading@@QEAA@XZ; MessagingThreading::~MessagingThreading(void)
0x180037a2a  lea     rcx, [rbp+57h+pv]
0x180037a2e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037a33  jmp     loc_180037ACA
0x180037a38  mov     rcx, [rbp+57h+var_58]; pv
0x180037a3c  mov     [rdi+60h], r15b
0x180037a40  test    rcx, rcx
0x180037a43  jz      short loc_180037A4B
0x180037a45  call    cs:__imp_MAPIFreeBuffer
0x180037a4b  lea     rcx, [rbp+57h+hMem]; this
0x180037a4f  call    ??1ptr_olApp@Comms@@QEAA@XZ; Comms::ptr_olApp::~ptr_olApp(void)
0x180037a54  lea     rcx, [rbp+57h+var_50]
0x180037a58  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037a5d  lea     rcx, [rbp+57h+var_48]; this
0x180037a61  call    ??1MessagingThreading@@QEAA@XZ; MessagingThreading::~MessagingThreading(void)
0x180037a66  lea     rcx, [rbp+57h+pv]
0x180037a6a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037a6f  mov     r8, [rdi+0C0h]; unsigned __int8 *
0x180037a76  lea     rcx, [rbp+57h+hMem]; this
0x180037a7a  mov     edx, [rdi+0B8h]; unsigned int
0x180037a80  mov     dword ptr [rbp+57h+hMem], r15d
0x180037a84  mov     [rbp+57h+hMem+8], r15
0x180037a88  call    ?Set@CAutoBlob@@QEAAJKQEBE@Z; CAutoBlob::Set(ulong,uchar const * const)
0x180037a8d  mov     ebx, eax
0x180037a8f  test    eax, eax
0x180037a91  jns     short loc_180037AB6
0x180037a93  mov     r9d, 4DEh
0x180037a99  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x180037aa0  mov     edx, r12d
0x180037aa3  mov     ecx, eax; int
0x180037aa5  call    Log_HREvent_15
0x180037aaa  mov     rcx, [rbp+57h+hMem+8]; hMem
0x180037aae  call    cs:__imp_LocalFree
0x180037ab4  jmp     short loc_180037ACA
0x180037ab6  movups  xmm0, xmmword ptr [rbp+57h+hMem]
0x180037aba  xor     ecx, ecx; hMem
0x180037abc  movdqu  xmmword ptr [r14], xmm0
0x180037ac1  call    cs:__imp_LocalFree
0x180037ac7  mov     ebx, r15d
0x180037aca  lea     rcx, [rbp+57h+lpMapiProp]
0x180037ace  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037ad3  mov     eax, ebx
0x180037ad5  mov     rcx, [rbp+57h+var_28]
0x180037ad9  xor     rcx, rsp; StackCookie
0x180037adc  call    __security_check_cookie
0x180037ae1  lea     r11, [rsp+0D0h+var_20]
0x180037ae9  mov     rbx, [r11+40h]
0x180037aed  mov     rsi, [r11+48h]
0x180037af1  mov     rsp, r11
0x180037af4  pop     r15
0x180037af6  pop     r14
0x180037af8  pop     r12
0x180037afa  pop     rdi
0x180037afb  pop     rbp
0x180037afc  retn
```
