# CloudServiceController::_PostInitialize(void)

- ea: `0x18007b11c`
- end: `0x18007b572`
- name: `?_PostInitialize@CloudServiceController@@AEAAJXZ`
- size: `1110`
- prototype: `__int64 __fastcall(CloudServiceController *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180078550`

## callees

- `0x1800016a0`
- `0x180005c50`
- `0x1800065c8`
- `0x180015050`
- `0x1800774d0`
- `0x18007b11c`
- `0x180080650`
- `0x180082608`
- `0x18008374c`
- `0x180084c6c`
- `0x180086794`
- `0x1800899e8`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b24e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b2a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b24e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b2a3`

## string_xrefs

- `0x18007b1ca`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007b201`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007b260`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007b2b5`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007b2fd`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007b340`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007b38b`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007b410`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007b150`: `CloudServiceController::_PostInitialize`
- `0x18007b4b5`: `CloudServiceController::_PostInitialize`

## pseudocode

```c
__int64 __fastcall CloudServiceController::_PostInitialize(CloudServiceController *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  int Instance; // eax
  unsigned int v7; // ebx
  int v8; // eax
  HRESULT v9; // eax
  HRESULT v10; // eax
  int v11; // eax
  int v12; // eax
  struct IUnknown *v13; // rbx
  int v14; // eax
  int v15; // esi
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  struct IUnknown *v22; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v23; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown *v24; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v25; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v26; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *v27; // [rsp+58h] [rbp-A8h] BYREF
  const OLECHAR *v28; // [rsp+60h] [rbp-A0h] BYREF
  struct ISmStore *v29; // [rsp+68h] [rbp-98h] BYREF
  struct IPOSyncServices *v30[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v31[256]; // [rsp+80h] [rbp-80h] BYREF

  ppva = 141;
  StringCchPrintfW(v31, 0x100u, L"%S(%d):%s", "CloudServiceController::_PostInitialize", ppva, L"Enter");
  if ( (unsigned int)dword_1800FD5F0 > 5 )
  {
    v26 = (struct IUnknown *)v31;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v2,
      (int)&unk_1800F0538,
      v3,
      v4,
      (const OLECHAR **)&v26);
  }
  if ( *((_DWORD *)this + 9) )
    return 0;
  v26 = 0;
  Instance = ChatServiceClient::CreateInstance((struct ChatServiceClient **)&v26);
  v7 = Instance;
  if ( Instance < 0 )
  {
    Log_HREvent_58(Instance);
    goto LABEL_41;
  }
  v22 = 0;
  v8 = AsyncMediaServiceClient::CreateInstance((struct AsyncMediaServiceClient **)&v22);
  v7 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent_58(v8);
LABEL_9:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    goto LABEL_41;
  }
  v29 = 0;
  v9 = CoCreateInstance(
         &GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7,
         0,
         0x17u,
         &GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c,
         (LPVOID *)&v29);
  v7 = v9;
  if ( v9 < 0 )
  {
    Log_HREvent_58(v9);
LABEL_12:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    goto LABEL_9;
  }
  v30[0] = 0;
  v10 = CoCreateInstance(
          &GUID_40b47a8f_c442_4f06_8304_aa1058edeea0,
          0,
          0x17u,
          &GUID_21e1b5a4_0010_437a_bfa7_9d1455238f39,
          (LPVOID *)v30);
  v7 = v10;
  if ( v10 < 0 )
  {
    Log_HREvent_58(v10);
LABEL_15:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v30);
    goto LABEL_12;
  }
  v23 = 0;
  v11 = MessageChangeTracker::CreateInstance(v29, v30[0], (struct MessageChangeTracker **)&v23);
  v7 = v11;
  if ( v11 < 0 )
  {
    Log_HREvent_58(v11);
LABEL_18:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    goto LABEL_15;
  }
  v24 = 0;
  v12 = ConversationAccessor::CreateInstance(v29, (struct ConversationAccessor **)&v24);
  v7 = v12;
  if ( v12 < 0 )
  {
    Log_HREvent_58(v12);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
    goto LABEL_18;
  }
  v13 = v24;
  v25 = 0;
  v14 = MessageSaver::CreateInstance(v29, (struct ConversationAccessor *)v24, (struct MessageSaver **)&v25);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v27 = 0;
    v16 = CloudServicePolicyManager::CreateInstance(
            (struct ICloudServicePolicyChangeListener *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
            (struct CloudServicePolicyManager **)&v27);
    v15 = v16;
    if ( v16 >= 0 )
    {
      if ( *((struct IUnknown **)this + 6) != v26 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 6, v26);
      if ( *((struct IUnknown **)this + 7) != v22 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 7, v22);
      if ( *((struct IUnknown **)this + 8) != v23 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 8, v23);
      if ( *((struct IUnknown **)this + 9) != v13 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 9, v13);
      if ( *((struct IUnknown **)this + 10) != v25 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 10, v25);
      if ( *((struct IUnknown **)this + 12) != v27 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 12, v27);
      *((_DWORD *)this + 9) = 1;
      LODWORD(ppv) = 190;
      StringCchPrintfW(v31, 0x100u, L"%S(%d):%s", "CloudServiceController::_PostInitialize", ppv, L"Fully initialized.");
      if ( (unsigned int)dword_1800FD5F0 > 4 )
      {
        v28 = v31;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v17,
          (int)word_1800F04C2,
          v18,
          v19,
          &v28);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v30);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
      v7 = 0;
      goto LABEL_41;
    }
    Log_HREvent_58(v16);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  }
  else
  {
    Log_HREvent_58(v14);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v30);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  v7 = v15;
LABEL_41:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  return v7;
}

```

## disassembly

```asm
0x18007b11c  push    rbp
0x18007b11e  push    rbx
0x18007b11f  push    rsi
0x18007b120  push    rdi
0x18007b121  lea     rbp, [rsp-198h]
0x18007b129  sub     rsp, 298h
0x18007b130  mov     rax, cs:__security_cookie
0x18007b137  xor     rax, rsp
0x18007b13a  mov     [rbp+1B0h+var_30], rax
0x18007b141  lea     rax, aEnter; "Enter"
0x18007b148  mov     rdi, rcx
0x18007b14b  mov     [rsp+2B0h+var_288], rax
0x18007b150  lea     r9, aCloudserviceco_36; "CloudServiceController::_PostInitialize"
0x18007b157  lea     r8, aSDS; "%S(%d):%s"
0x18007b15e  mov     dword ptr [rsp+2B0h+ppv], 8Dh
0x18007b166  mov     edx, 100h; unsigned __int64
0x18007b16b  lea     rcx, [rbp+1B0h+var_230]; unsigned __int16 *
0x18007b16f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007b174  mov     eax, cs:dword_1800FD5F0
0x18007b17a  cmp     eax, 5
0x18007b17d  jbe     short loc_18007B19E
0x18007b17f  lea     rax, [rbp+1B0h+var_230]
0x18007b183  mov     [rsp+2B0h+var_260], rax
0x18007b188  lea     rdx, unk_1800F0538
0x18007b18f  lea     rax, [rsp+2B0h+var_260]
0x18007b194  mov     [rsp+2B0h+ppv], rax
0x18007b199  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007b19e  cmp     dword ptr [rdi+24h], 0
0x18007b1a2  jz      short loc_18007B1AB
0x18007b1a4  xor     eax, eax
0x18007b1a6  jmp     loc_18007B557
0x18007b1ab  lea     rcx, [rsp+2B0h+var_260]; struct ChatServiceClient **
0x18007b1b0  mov     [rsp+2B0h+var_260], 0
0x18007b1b9  call    ?CreateInstance@ChatServiceClient@@SAJPEAPEAV1@@Z; ChatServiceClient::CreateInstance(ChatServiceClient * *)
0x18007b1be  mov     ebx, eax
0x18007b1c0  test    eax, eax
0x18007b1c2  jns     short loc_18007B1E2
0x18007b1c4  mov     r9d, 97h
0x18007b1ca  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007b1d1  mov     edx, 1
0x18007b1d6  mov     ecx, eax; int
0x18007b1d8  call    Log_HREvent_58
0x18007b1dd  jmp     loc_18007B54B
0x18007b1e2  lea     rcx, [rsp+2B0h+var_280]; struct AsyncMediaServiceClient **
0x18007b1e7  mov     [rsp+2B0h+var_280], 0
0x18007b1f0  call    ?CreateInstance@AsyncMediaServiceClient@@SAJPEAPEAV1@@Z; AsyncMediaServiceClient::CreateInstance(AsyncMediaServiceClient * *)
0x18007b1f5  mov     ebx, eax
0x18007b1f7  test    eax, eax
0x18007b1f9  jns     short loc_18007B223
0x18007b1fb  mov     r9d, 9Bh
0x18007b201  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007b208  mov     edx, 1
0x18007b20d  mov     ecx, eax; int
0x18007b20f  call    Log_HREvent_58
0x18007b214  lea     rcx, [rsp+2B0h+var_280]
0x18007b219  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b21e  jmp     loc_18007B54B
0x18007b223  lea     rax, [rsp+2B0h+var_248]
0x18007b228  mov     [rsp+2B0h+var_248], 0
0x18007b231  mov     esi, 17h
0x18007b236  mov     [rsp+2B0h+ppv], rax; ppv
0x18007b23b  mov     r8d, esi; dwClsContext
0x18007b23e  lea     r9, _GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c; riid
0x18007b245  xor     edx, edx; pUnkOuter
0x18007b247  lea     rcx, _GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7; rclsid
0x18007b24e  call    cs:__imp_CoCreateInstance
0x18007b254  mov     ebx, eax
0x18007b256  test    eax, eax
0x18007b258  jns     short loc_18007B27D
0x18007b25a  mov     r9d, 9Fh
0x18007b260  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007b267  lea     edx, [rsi-16h]
0x18007b26a  mov     ecx, eax; int
0x18007b26c  call    Log_HREvent_58
0x18007b271  lea     rcx, [rsp+2B0h+var_248]
0x18007b276  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b27b  jmp     short loc_18007B214
0x18007b27d  lea     rax, [rsp+2B0h+var_240]
0x18007b282  mov     [rsp+2B0h+var_240], 0
0x18007b28b  lea     r9, _GUID_21e1b5a4_0010_437a_bfa7_9d1455238f39; riid
0x18007b292  mov     [rsp+2B0h+ppv], rax; ppv
0x18007b297  mov     r8d, esi; dwClsContext
0x18007b29a  lea     rcx, _GUID_40b47a8f_c442_4f06_8304_aa1058edeea0; rclsid
0x18007b2a1  xor     edx, edx; pUnkOuter
0x18007b2a3  call    cs:__imp_CoCreateInstance
0x18007b2a9  mov     ebx, eax
0x18007b2ab  test    eax, eax
0x18007b2ad  jns     short loc_18007B2D4
0x18007b2af  mov     r9d, 0A3h
0x18007b2b5  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007b2bc  mov     edx, 1
0x18007b2c1  mov     ecx, eax; int
0x18007b2c3  call    Log_HREvent_58
0x18007b2c8  lea     rcx, [rsp+2B0h+var_240]
0x18007b2cd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b2d2  jmp     short loc_18007B271
0x18007b2d4  mov     rdx, [rsp+2B0h+var_240]; struct IPOSyncServices *
0x18007b2d9  lea     r8, [rsp+2B0h+var_278]; struct MessageChangeTracker **
0x18007b2de  mov     rcx, [rsp+2B0h+var_248]; struct ISmStore *
0x18007b2e3  mov     [rsp+2B0h+var_278], 0
0x18007b2ec  call    ?CreateInstance@MessageChangeTracker@@SAJPEAUISmStore@@PEAUIPOSyncServices@@PEAPEAV1@@Z; MessageChangeTracker::CreateInstance(ISmStore *,IPOSyncServices *,MessageChangeTracker * *)
0x18007b2f1  mov     ebx, eax
0x18007b2f3  test    eax, eax
0x18007b2f5  jns     short loc_18007B31C
0x18007b2f7  mov     r9d, 0A6h
0x18007b2fd  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007b304  mov     edx, 1
0x18007b309  mov     ecx, eax; int
0x18007b30b  call    Log_HREvent_58
0x18007b310  lea     rcx, [rsp+2B0h+var_278]
0x18007b315  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b31a  jmp     short loc_18007B2C8
0x18007b31c  mov     rcx, [rsp+2B0h+var_248]; struct ISmStore *
0x18007b321  lea     rdx, [rsp+2B0h+var_270]; struct ConversationAccessor **
0x18007b326  mov     [rsp+2B0h+var_270], 0
0x18007b32f  call    ?CreateInstance@ConversationAccessor@@SAJPEAUISmStore@@PEAPEAV1@@Z; ConversationAccessor::CreateInstance(ISmStore *,ConversationAccessor * *)
0x18007b334  mov     ebx, eax
0x18007b336  test    eax, eax
0x18007b338  jns     short loc_18007B35F
0x18007b33a  mov     r9d, 0AAh
0x18007b340  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007b347  mov     edx, 1
0x18007b34c  mov     ecx, eax; int
0x18007b34e  call    Log_HREvent_58
0x18007b353  lea     rcx, [rsp+2B0h+var_270]
0x18007b358  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b35d  jmp     short loc_18007B310
0x18007b35f  mov     rbx, [rsp+2B0h+var_270]
0x18007b364  lea     r8, [rsp+2B0h+var_268]; struct MessageSaver **
0x18007b369  mov     rcx, [rsp+2B0h+var_248]; struct ISmStore *
0x18007b36e  mov     rdx, rbx; struct ConversationAccessor *
0x18007b371  mov     [rsp+2B0h+var_268], 0
0x18007b37a  call    ?CreateInstance@MessageSaver@@SAJPEAUISmStore@@PEAVConversationAccessor@@PEAPEAV1@@Z; MessageSaver::CreateInstance(ISmStore *,ConversationAccessor *,MessageSaver * *)
0x18007b37f  mov     esi, eax
0x18007b381  test    eax, eax
0x18007b383  jns     short loc_18007B3E1
0x18007b385  mov     r9d, 0AEh
0x18007b38b  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007b392  mov     edx, 1
0x18007b397  mov     ecx, eax; int
0x18007b399  call    Log_HREvent_58
0x18007b39e  lea     rcx, [rsp+2B0h+var_268]
0x18007b3a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b3a8  lea     rcx, [rsp+2B0h+var_270]
0x18007b3ad  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b3b2  lea     rcx, [rsp+2B0h+var_278]
0x18007b3b7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b3bc  lea     rcx, [rsp+2B0h+var_240]
0x18007b3c1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b3c6  lea     rcx, [rsp+2B0h+var_248]
0x18007b3cb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b3d0  lea     rcx, [rsp+2B0h+var_280]
0x18007b3d5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b3da  mov     ebx, esi
0x18007b3dc  jmp     loc_18007B54B
0x18007b3e1  lea     rdx, [rdi+8]
0x18007b3e5  mov     [rsp+2B0h+var_258], 0
0x18007b3ee  mov     rax, rdi
0x18007b3f1  neg     rax
0x18007b3f4  sbb     rcx, rcx
0x18007b3f7  and     rcx, rdx; struct ICloudServicePolicyChangeListener *
0x18007b3fa  lea     rdx, [rsp+2B0h+var_258]; struct CloudServicePolicyManager **
0x18007b3ff  call    ?CreateInstance@CloudServicePolicyManager@@SAJPEAUICloudServicePolicyChangeListener@@PEAPEAV1@@Z; CloudServicePolicyManager::CreateInstance(ICloudServicePolicyChangeListener *,CloudServicePolicyManager * *)
0x18007b404  mov     esi, eax
0x18007b406  test    eax, eax
0x18007b408  jns     short loc_18007B432
0x18007b40a  mov     r9d, 0B2h
0x18007b410  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007b417  mov     edx, 1
0x18007b41c  mov     ecx, eax; int
0x18007b41e  call    Log_HREvent_58
0x18007b423  lea     rcx, [rsp+2B0h+var_258]
0x18007b428  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b42d  jmp     loc_18007B39E
0x18007b432  mov     rdx, [rsp+2B0h+var_260]; struct IUnknown *
0x18007b437  lea     rcx, [rdi+30h]; struct IUnknown **
0x18007b43b  cmp     [rcx], rdx
0x18007b43e  jz      short loc_18007B445
0x18007b440  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007b445  mov     rdx, [rsp+2B0h+var_280]; struct IUnknown *
0x18007b44a  lea     rcx, [rdi+38h]; struct IUnknown **
0x18007b44e  cmp     [rcx], rdx
0x18007b451  jz      short loc_18007B458
0x18007b453  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007b458  mov     rdx, [rsp+2B0h+var_278]; struct IUnknown *
0x18007b45d  lea     rcx, [rdi+40h]; struct IUnknown **
0x18007b461  cmp     [rcx], rdx
0x18007b464  jz      short loc_18007B46B
0x18007b466  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007b46b  lea     rcx, [rdi+48h]; struct IUnknown **
0x18007b46f  cmp     [rcx], rbx
0x18007b472  jz      short loc_18007B47C
0x18007b474  mov     rdx, rbx; struct IUnknown *
0x18007b477  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007b47c  mov     rdx, [rsp+2B0h+var_268]; struct IUnknown *
0x18007b481  lea     rcx, [rdi+50h]; struct IUnknown **
0x18007b485  cmp     [rcx], rdx
0x18007b488  jz      short loc_18007B48F
0x18007b48a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007b48f  mov     rdx, [rsp+2B0h+var_258]; struct IUnknown *
0x18007b494  lea     rcx, [rdi+60h]; struct IUnknown **
0x18007b498  cmp     [rcx], rdx
0x18007b49b  jz      short loc_18007B4A2
0x18007b49d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007b4a2  lea     rax, aFullyInitializ; "Fully initialized."
0x18007b4a9  mov     dword ptr [rdi+24h], 1
0x18007b4b0  mov     [rsp+2B0h+var_288], rax
0x18007b4b5  lea     r9, aCloudserviceco_36; "CloudServiceController::_PostInitialize"
0x18007b4bc  lea     r8, aSDS; "%S(%d):%s"
0x18007b4c3  mov     dword ptr [rsp+2B0h+ppv], 0BEh
0x18007b4cb  mov     edx, 100h; unsigned __int64
0x18007b4d0  lea     rcx, [rbp+1B0h+var_230]; unsigned __int16 *
0x18007b4d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007b4d9  mov     eax, cs:dword_1800FD5F0
0x18007b4df  cmp     eax, 4
0x18007b4e2  jbe     short loc_18007B503
0x18007b4e4  lea     rax, [rbp+1B0h+var_230]
0x18007b4e8  mov     [rsp+2B0h+var_250], rax
0x18007b4ed  lea     rdx, word_1800F04C2
0x18007b4f4  lea     rax, [rsp+2B0h+var_250]
0x18007b4f9  mov     [rsp+2B0h+ppv], rax
0x18007b4fe  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007b503  lea     rcx, [rsp+2B0h+var_258]
0x18007b508  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b50d  lea     rcx, [rsp+2B0h+var_268]
0x18007b512  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b517  lea     rcx, [rsp+2B0h+var_270]
0x18007b51c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b521  lea     rcx, [rsp+2B0h+var_278]
0x18007b526  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b52b  lea     rcx, [rsp+2B0h+var_240]
0x18007b530  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b535  lea     rcx, [rsp+2B0h+var_248]
0x18007b53a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b53f  lea     rcx, [rsp+2B0h+var_280]
0x18007b544  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b549  xor     ebx, ebx
0x18007b54b  lea     rcx, [rsp+2B0h+var_260]
0x18007b550  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007b555  mov     eax, ebx
0x18007b557  mov     rcx, [rbp+1B0h+var_30]
0x18007b55e  xor     rcx, rsp; StackCookie
0x18007b561  call    __security_check_cookie
0x18007b566  add     rsp, 298h
0x18007b56d  pop     rdi
0x18007b56e  pop     rsi
0x18007b56f  pop     rbx
0x18007b570  pop     rbp
0x18007b571  retn
```
