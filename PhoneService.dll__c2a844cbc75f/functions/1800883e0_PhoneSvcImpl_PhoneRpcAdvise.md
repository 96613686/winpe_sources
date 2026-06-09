# PhoneSvcImpl_PhoneRpcAdvise

- ea: `0x1800883e0`
- end: `0x180088bfa`
- name: `PhoneSvcImpl_PhoneRpcAdvise`
- size: `2074`
- prototype: `__int64 __fastcall(__int64, const enum PH_CHANGEEVENT *, unsigned int, PhoneServiceListener **, BackTraceCollection *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005048`
- `0x180005660`
- `0x1800056a0`
- `0x180006e94`
- `0x180007750`
- `0x180007780`
- `0x18000c628`
- `0x18000c960`
- `0x18000d730`
- `0x180080894`
- `0x180086250`
- `0x180086b04`
- `0x180086b10`
- `0x1800877b4`
- `0x1800883e0`
- `0x18008d0f0`
- `0x18008d1f8`
- `0x18008d5e8`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180088493`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180088493`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180088464`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180088464`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008853f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008853f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18008858a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18008858a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008868a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008868a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800886be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088743`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800886be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088b51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088675`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800886f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088712`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800887d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800887f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088a96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088ab4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088b13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088b31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088bb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088675`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800886f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088712`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800887d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800887f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088a96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088ab4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088b13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088b31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088bb3`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x180088505`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x180088505`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180088703`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800887e8`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180088aa5`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180088b22`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180088ba4`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180088703`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800887e8`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180088aa5`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180088b22`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180088ba4`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x18008842f`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x18008842f`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x1800884bf`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x1800884bf`

## string_xrefs

- `0x1800886a5`: `onecoreuap\private\net\inc\phone\RevokableComPtr.h`
- `0x180088904`: `PublicPhoneRpc: Phone service listener added.`

## pseudocode

```c
__int64 __fastcall PhoneSvcImpl_PhoneRpcAdvise(
        __int64 a1,
        const enum PH_CHANGEEVENT *a2,
        unsigned int a3,
        PhoneServiceListener **a4,
        BackTraceCollection *a5)
{
  int v7; // eax
  BackTraceCollection *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  HRESULT v12; // eax
  BackTraceCollection *v13; // rcx
  __int64 v14; // r15
  __int64 v15; // rdx
  __int64 v16; // rcx
  void **v17; // rax
  int RpcClientThreadToken; // eax
  BackTraceCollection *v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // eax
  BackTraceCollection *v23; // rcx
  HANDLE v24; // rdi
  PhoneServiceListener *v25; // rax
  BackTraceCollection *v26; // rcx
  PhoneServiceListener *v27; // rsi
  struct ATL::CAtlModule *v28; // rcx
  unsigned int v29; // r14d
  __int64 v30; // rax
  int v31; // eax
  BackTraceCollection *v32; // rcx
  __int64 v33; // r8
  PhoneNotificationManager *v34; // rbx
  BackTraceCollection *v35; // rcx
  __int64 v36; // r8
  void (*v37)(void); // rax
  int RpcClientApplicationPackageInfo; // eax
  __int64 v39; // r8
  int v40; // eax
  BackTraceCollection *v41; // rcx
  __int64 v42; // r8
  void (*v43)(void); // rax
  int ListenerIdentity; // eax
  BackTraceCollection *v45; // rcx
  __int64 v46; // r8
  __int64 v47; // rax
  OLECHAR *v48; // rcx
  BackTraceCollection *v49; // rcx
  __int64 v50; // r8
  int v51; // eax
  __int64 v52; // r8
  __int64 v54; // r8
  BackTraceCollection *v55; // rcx
  __int64 v56; // r8
  signed int LastError; // eax
  BackTraceCollection *v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r8
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct ISecurityToken *v64; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-78h] BYREF
  void *v66; // [rsp+90h] [rbp-70h] BYREF
  void *Block[2]; // [rsp+98h] [rbp-68h] BYREF
  __int16 v68; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v69; // [rsp+AAh] [rbp-56h]
  int v70; // [rsp+B2h] [rbp-4Eh]
  __int16 v71; // [rsp+B6h] [rbp-4Ah]
  void *v72[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v73; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v74; // [rsp+CAh] [rbp-36h]
  int v75; // [rsp+D2h] [rbp-2Eh]
  __int16 v76; // [rsp+D6h] [rbp-2Ah]
  GUID pguid; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v78[136]; // [rsp+F0h] [rbp-10h] BYREF
  OLECHAR sz[104]; // [rsp+200h] [rbp+100h] BYREF

  v64 = 0;
  v7 = CreatePerUserSecurityTokenForRpcClient(&v64);
  v9 = v7;
  if ( v7 < 0 )
  {
    BackTraceCollection::Capture(v8, v7);
    v11 = 934;
LABEL_3:
    Log_HREvent_31(v9, 1, v10, v11);
LABEL_99:
    if ( !v64 )
      return v9;
    v37 = *(void (**)(void))(*(_QWORD *)v64 + 16LL);
LABEL_101:
    v37();
    return v9;
  }
  pguid = 0;
  v12 = CoCreateGuid(&pguid);
  v9 = v12;
  if ( v12 < 0 )
  {
    BackTraceCollection::Capture(v13, v12);
    v11 = 939;
    goto LABEL_3;
  }
  v14 = 100;
  if ( !StringFromGUID2(&pguid, sz, 100) )
  {
    Log_AssertionEvent_16(v16, v15, 942);
    __int2c();
  }
  hObject = 0;
  v17 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&hObject);
  RpcClientThreadToken = GetRpcClientThreadToken(8u, v17);
  v9 = RpcClientThreadToken;
  if ( RpcClientThreadToken < 0 )
  {
    BackTraceCollection::Capture(v19, RpcClientThreadToken);
    Log_HREvent_31(v9, 1, v20, 946);
LABEL_97:
    if ( hObject )
      CloseHandle(hObject);
    goto LABEL_99;
  }
  v66 = 0;
  v21 = tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&v66);
  v22 = BuildSecurityDescriptorForSharingAccess(hObject, 0, 0x100000, v21);
  if ( v22 < 0 )
  {
    v9 = v22 | 0x10000000;
    BackTraceCollection::Capture(v23, v22 | 0x10000000);
    Log_HREvent_31(v9, 0, v60, 949);
LABEL_95:
    if ( v66 )
      FreeTransientObjectSecurityDescriptor();
    goto LABEL_97;
  }
  EventAttributes.lpSecurityDescriptor = v66;
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  v24 = CreateEventW(&EventAttributes, 0, 0, sz);
  if ( !v24 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    BackTraceCollection::Capture(v58, v9);
    Log_HREvent_31(v9, 0, v59, 959);
    goto LABEL_23;
  }
  v25 = (PhoneServiceListener *)operator new(0x98u);
  v27 = v25;
  if ( !v25 )
  {
    v29 = -2147024882;
    goto LABEL_82;
  }
  memset_0(v25, 0, 0x98u);
  *(_QWORD *)v27 = &PhoneServiceListener::`vftable';
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)v27 + 32), 0, 0);
  v28 = ATL::_pAtlModule;
  *((_QWORD *)v27 + 9) = (char *)v27 + 72;
  *((_QWORD *)v27 + 10) = (char *)v27 + 72;
  *((_QWORD *)v27 + 11) = 0;
  *((_QWORD *)v27 + 13) = (char *)v27 + 104;
  *((_QWORD *)v27 + 14) = (char *)v27 + 104;
  *((_QWORD *)v27 + 15) = 0;
  *((_QWORD *)v27 + 16) = 0;
  *((_WORD *)v27 + 68) = 2048;
  *(_QWORD *)v27 = &ATL::CComObject<PhoneServiceListener>::`vftable';
  *((_DWORD *)v27 + 24) = 0;
  *((_DWORD *)v27 + 36) = 0;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v28 + 8LL))(v28);
  (*(void (__fastcall **)(PhoneServiceListener *))(*(_QWORD *)v27 + 8LL))(v27);
  v29 = PhoneServiceListener::_Initialize(v27, v24);
  v30 = *(_QWORD *)v27;
  if ( (v29 & 0x80000000) != 0 )
  {
    (*(void (__fastcall **)(PhoneServiceListener *))(v30 + 16))(v27);
LABEL_82:
    BackTraceCollection::Capture(v26, v29);
    Log_HREvent_33(v29, 1, v54, 10);
    BackTraceCollection::Capture(v55, v29);
    Log_HREvent_31(v29, 1, v56, 963);
LABEL_83:
    CloseHandle(v24);
    if ( v66 )
      FreeTransientObjectSecurityDescriptor();
    if ( hObject )
      CloseHandle(hObject);
    if ( !v64 )
      return v29;
    v43 = *(void (**)(void))(*(_QWORD *)v64 + 16LL);
LABEL_89:
    v43();
    return v29;
  }
  (*(void (__fastcall **)(PhoneServiceListener *))(v30 + 8))(v27);
  (*(void (__fastcall **)(PhoneServiceListener *))(*(_QWORD *)v27 + 16LL))(v27);
  v31 = PhoneServiceListener::SetRegisteredChangeEvents(v27, a2, a3);
  v9 = v31;
  if ( v31 < 0 )
  {
    BackTraceCollection::Capture(v32, v31);
    Log_HREvent_31(v9, 1, v33, 964);
    if ( v27 )
      (*(void (__fastcall **)(PhoneServiceListener *))(*(_QWORD *)v27 + 16LL))(v27);
    CloseHandle(v24);
    goto LABEL_95;
  }
  EnterCriticalSection(&stru_1800B4150);
  v34 = qword_1800B4178;
  if ( !qword_1800B4178 )
  {
    v9 = -2147019873;
    Log_HREvent_28(2147947423LL, 0, "onecoreuap\\private\\net\\inc\\phone\\RevokableComPtr.h", 140);
    LeaveCriticalSection(&stru_1800B4150);
    BackTraceCollection::Capture(v35, -2147019873);
    Log_HREvent_31(2147947423LL, 1, v36, 968);
    if ( v27 )
      (*(void (__fastcall **)(PhoneServiceListener *))(*(_QWORD *)v27 + 16LL))(v27);
    CloseHandle(v24);
LABEL_23:
    if ( v66 )
      FreeTransientObjectSecurityDescriptor();
    if ( hObject )
      CloseHandle(hObject);
    if ( !v64 )
      return v9;
    v37 = *(void (**)(void))(*(_QWORD *)v64 + 16LL);
    goto LABEL_101;
  }
  (*(void (__fastcall **)(PhoneNotificationManager *))(*(_QWORD *)qword_1800B4178 + 8LL))(qword_1800B4178);
  LeaveCriticalSection(&stru_1800B4150);
  memset_0(v78, 0, 0x106u);
  RpcClientApplicationPackageInfo = GetRpcClientApplicationPackageInfo((BackTraceCollection *)v78);
  if ( RpcClientApplicationPackageInfo < 0 )
    Log_HREvent_31((unsigned int)RpcClientApplicationPackageInfo, 0, v39, 975);
  v40 = PhoneNotificationManager::AddListener(v34, v27, v64, v78);
  v29 = v40;
  if ( v40 < 0 )
  {
    BackTraceCollection::Capture(v41, v40);
    Log_HREvent_31(v29, 1, v42, 978);
    if ( !v34 )
    {
LABEL_34:
      if ( v27 )
        (*(void (__fastcall **)(PhoneServiceListener *))(*(_QWORD *)v27 + 16LL))(v27);
      CloseHandle(v24);
      if ( v66 )
        FreeTransientObjectSecurityDescriptor();
      if ( hObject )
        CloseHandle(hObject);
      if ( !v64 )
        return v29;
      v43 = *(void (**)(void))(*(_QWORD *)v64 + 16LL);
      goto LABEL_89;
    }
LABEL_33:
    (*(void (__fastcall **)(PhoneNotificationManager *))(*(_QWORD *)v34 + 16LL))(v34);
    goto LABEL_34;
  }
  v74 = 0;
  v72[0] = &v73;
  v75 = 0;
  v72[1] = &v73;
  v76 = 0;
  Block[0] = &v68;
  v73 = 0;
  Block[1] = &v68;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v68 = 0;
  ListenerIdentity = PhoneNotificationManager::GetListenerIdentity(v34, v27, v72, Block);
  v29 = ListenerIdentity;
  if ( ListenerIdentity < 0 )
  {
    BackTraceCollection::Capture(v45, ListenerIdentity);
    Log_HREvent_31(v29, 1, v46, 985);
    if ( Block[0] != &v68 )
      operator delete(Block[0]);
    if ( v72[0] != &v73 )
      operator delete(v72[0]);
    PhoneNotificationManager::RemoveListener(v34, v27);
    if ( !v34 )
      goto LABEL_34;
    goto LABEL_33;
  }
  if ( (unsigned int)dword_1800B3200 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v45,
      &unk_1800AB3C8);
  v47 = 2147483646;
  v48 = sz;
  do
  {
    if ( !v47 )
      break;
    if ( !*v48 )
      break;
    *(_WORD *)a5 = *v48++;
    a5 = (BackTraceCollection *)((char *)a5 + 2);
    --v47;
    --v14;
  }
  while ( v14 );
  v49 = (BackTraceCollection *)((char *)a5 - 2);
  v29 = v14 == 0 ? 0x8007007A : 0;
  if ( v14 )
    v49 = a5;
  *(_WORD *)v49 = 0;
  if ( !v14 )
  {
    BackTraceCollection::Capture(v49, v29);
    Log_HREvent_31(v29, 1, v50, 997);
    if ( Block[0] != &v68 )
      operator delete(Block[0]);
    if ( v72[0] != &v73 )
      operator delete(v72[0]);
    PhoneNotificationManager::RemoveListener(v34, v27);
    if ( v34 )
      (*(void (__fastcall **)(PhoneNotificationManager *))(*(_QWORD *)v34 + 16LL))(v34);
    if ( v27 )
      (*(void (__fastcall **)(PhoneServiceListener *))(*(_QWORD *)v27 + 16LL))(v27);
    goto LABEL_83;
  }
  *a4 = v27;
  v51 = _TrackingRpcClient(v72, Block, v27);
  if ( v51 < 0 )
    Log_HREvent_31((unsigned int)v51, 0, v52, 1000);
  if ( Block[0] != &v68 )
    operator delete(Block[0]);
  if ( v72[0] != &v73 )
    operator delete(v72[0]);
  if ( v34 )
    (*(void (__fastcall **)(PhoneNotificationManager *))(*(_QWORD *)v34 + 16LL))(v34);
  CloseHandle(v24);
  if ( v66 )
    FreeTransientObjectSecurityDescriptor();
  if ( hObject )
    CloseHandle(hObject);
  if ( v64 )
    (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v64 + 16LL))(v64);
  return 0;
}

```

## disassembly

```asm
0x1800883e0  mov     [rsp-8+arg_0], rbx
0x1800883e5  push    rbp
0x1800883e6  push    rsi
0x1800883e7  push    rdi
0x1800883e8  push    r12
0x1800883ea  push    r13
0x1800883ec  push    r14
0x1800883ee  push    r15
0x1800883f0  lea     rbp, [rsp-1E0h]
0x1800883f8  sub     rsp, 2E0h
0x1800883ff  mov     rax, cs:__security_cookie
0x180088406  xor     rax, rsp
0x180088409  mov     [rbp+210h+var_40], rax
0x180088410  mov     r12, [rbp+210h+arg_20]
0x180088417  lea     rcx, [rbp+210h+var_290]
0x18008841b  xor     r14d, r14d
0x18008841e  mov     [rsp+310h+var_2B0], r9
0x180088423  mov     [rbp+210h+var_290], r14
0x180088427  mov     r13, rdx
0x18008842a  mov     [rsp+310h+var_2D0], r8d
0x18008842f  call    cs:__imp_?CreatePerUserSecurityTokenForRpcClient@@YAJPEAPEAUISecurityToken@@@Z; CreatePerUserSecurityTokenForRpcClient(ISecurityToken * *)
0x180088435  mov     ebx, eax
0x180088437  test    eax, eax
0x180088439  jns     short loc_180088459
0x18008843b  mov     edx, eax; int
0x18008843d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180088442  mov     r9d, 3A6h
0x180088448  mov     edx, 1
0x18008844d  mov     ecx, ebx
0x18008844f  call    Log_HREvent_31
0x180088454  jmp     loc_180088BB9
0x180088459  xorps   xmm0, xmm0
0x18008845c  lea     rcx, [rbp+210h+pguid]; pguid
0x180088460  movups  xmmword ptr [rbp+210h+pguid.Data1], xmm0
0x180088464  call    cs:__imp_CoCreateGuid
0x18008846a  mov     ebx, eax
0x18008846c  test    eax, eax
0x18008846e  jns     short loc_18008847F
0x180088470  mov     edx, eax; int
0x180088472  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180088477  mov     r9d, 3ABh
0x18008847d  jmp     short loc_180088448
0x18008847f  mov     r15d, 64h ; 'd'
0x180088485  lea     rdx, [rbp+210h+sz]; lpsz
0x18008848c  mov     r8d, r15d; cchMax
0x18008848f  lea     rcx, [rbp+210h+pguid]; rguid
0x180088493  call    cs:__imp_StringFromGUID2
0x180088499  test    eax, eax
0x18008849b  jnz     short loc_1800884AA
0x18008849d  mov     r8d, 3AEh
0x1800884a3  call    Log_AssertionEvent_16
0x1800884a8  int     2Ch; Windows NT - assertion failure
0x1800884aa  lea     rcx, [rbp+210h+hObject]
0x1800884ae  mov     [rbp+210h+hObject], r14
0x1800884b2  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x1800884b7  mov     rdx, rax
0x1800884ba  mov     ecx, 8
0x1800884bf  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x1800884c5  mov     ebx, eax
0x1800884c7  test    eax, eax
0x1800884c9  jns     short loc_1800884E9
0x1800884cb  mov     edx, eax; int
0x1800884cd  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800884d2  mov     edx, 1
0x1800884d7  mov     r9d, 3B2h
0x1800884dd  mov     ecx, ebx
0x1800884df  call    Log_HREvent_31
0x1800884e4  jmp     loc_180088BAA
0x1800884e9  lea     rcx, [rbp+210h+var_280]
0x1800884ed  mov     [rbp+210h+var_280], r14
0x1800884f1  call    ??$replace@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0> &)
0x1800884f6  mov     rcx, [rbp+210h+hObject]
0x1800884fa  mov     r9, rax
0x1800884fd  xor     edx, edx
0x1800884ff  mov     r8d, 100000h
0x180088505  call    cs:__imp_BuildSecurityDescriptorForSharingAccess
0x18008850b  mov     ebx, eax
0x18008850d  test    eax, eax
0x18008850f  js      loc_180088B81
0x180088515  mov     rax, [rbp+210h+var_280]
0x180088519  lea     r9, [rbp+210h+sz]; lpName
0x180088520  mov     [rsp+310h+EventAttributes.lpSecurityDescriptor], rax
0x180088525  lea     rcx, [rsp+310h+EventAttributes]; lpEventAttributes
0x18008852a  xor     eax, eax
0x18008852c  mov     qword ptr [rsp+310h+EventAttributes.nLength], 18h
0x180088535  xor     r8d, r8d; bInitialState
0x180088538  mov     qword ptr [rsp+310h+EventAttributes.bInheritHandle], rax
0x18008853d  xor     edx, edx; bManualReset
0x18008853f  call    cs:__imp_CreateEventW
0x180088545  mov     rdi, rax
0x180088548  test    rax, rax
0x18008854b  jz      loc_180088B51
0x180088551  mov     ecx, 98h; Size
0x180088556  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008855b  mov     rsi, rax
0x18008855e  test    rax, rax
0x180088561  jz      loc_180088AD6
0x180088567  xor     edx, edx; Val
0x180088569  mov     r8d, 98h; Size
0x18008856f  mov     rcx, rax; void *
0x180088572  call    memset_0
0x180088577  lea     rax, ??_7PhoneServiceListener@@6B@; const PhoneServiceListener::`vftable'
0x18008857e  xor     r8d, r8d; Flags
0x180088581  lea     rcx, [rsi+20h]; lpCriticalSection
0x180088585  mov     [rsi], rax
0x180088588  xor     edx, edx; dwSpinCount
0x18008858a  call    cs:__imp_InitializeCriticalSectionEx
0x180088590  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180088597  lea     rax, [rsi+48h]
0x18008859b  mov     [rax], rax
0x18008859e  mov     [rax+8], rax
0x1800885a2  mov     [rax+10h], r14
0x1800885a6  lea     rax, [rsi+68h]
0x1800885aa  mov     [rax], rax
0x1800885ad  mov     [rax+8], rax
0x1800885b1  mov     [rax+10h], r14
0x1800885b5  mov     [rax+18h], r14
0x1800885b9  mov     word ptr [rax+20h], 800h
0x1800885bf  lea     rax, ??_7?$CComObject@VPhoneServiceListener@@@ATL@@6B@; const ATL::CComObject<PhoneServiceListener>::`vftable'
0x1800885c6  mov     [rsi], rax
0x1800885c9  mov     [rsi+60h], r14d
0x1800885cd  mov     [rsi+90h], r14d
0x1800885d4  mov     rax, [rcx]
0x1800885d7  mov     rax, [rax+8]
0x1800885db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800885e0  mov     rax, [rsi]
0x1800885e3  mov     rcx, rsi
0x1800885e6  mov     rax, [rax+8]
0x1800885ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800885ef  mov     rdx, rdi; void *
0x1800885f2  mov     rcx, rsi; this
0x1800885f5  call    ?_Initialize@PhoneServiceListener@@IEAAJPEAX@Z; PhoneServiceListener::_Initialize(void *)
0x1800885fa  mov     r14d, eax
0x1800885fd  test    eax, eax
0x1800885ff  mov     rax, [rsi]
0x180088602  mov     rcx, rsi
0x180088605  jns     short loc_180088615
0x180088607  mov     rax, [rax+10h]
0x18008860b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088610  jmp     loc_180088ADC
0x180088615  mov     rax, [rax+8]
0x180088619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008861e  mov     rax, [rsi]
0x180088621  mov     rcx, rsi
0x180088624  mov     rax, [rax+10h]
0x180088628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008862d  mov     r8d, [rsp+310h+var_2D0]; unsigned int
0x180088632  mov     rdx, r13; enum PH_CHANGEEVENT *
0x180088635  mov     rcx, rsi; this
0x180088638  call    ?SetRegisteredChangeEvents@PhoneServiceListener@@QEAAJPEBW4PH_CHANGEEVENT@@I@Z; PhoneServiceListener::SetRegisteredChangeEvents(PH_CHANGEEVENT const *,uint)
0x18008863d  xor     r13d, r13d
0x180088640  mov     ebx, eax
0x180088642  test    eax, eax
0x180088644  jns     short loc_180088680
0x180088646  mov     edx, eax; int
0x180088648  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008864d  lea     edx, [r13+1]
0x180088651  mov     r9d, 3C4h
0x180088657  mov     ecx, ebx
0x180088659  call    Log_HREvent_31
0x18008865e  test    rsi, rsi
0x180088661  jz      short loc_180088672
0x180088663  mov     rcx, [rsi]
0x180088666  mov     rax, [rcx+10h]
0x18008866a  mov     rcx, rsi
0x18008866d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088672  mov     rcx, rdi; hObject
0x180088675  call    cs:__imp_CloseHandle
0x18008867b  jmp     loc_180088B9B
0x180088680  lea     r14, stru_1800B4150
0x180088687  mov     rcx, r14; lpCriticalSection
0x18008868a  call    cs:__imp_EnterCriticalSection
0x180088690  mov     rbx, cs:qword_1800B4178
0x180088697  test    rbx, rbx
0x18008869a  jnz     loc_180088731
0x1800886a0  mov     ebx, 8007139Fh
0x1800886a5  lea     r8, aOnecoreuapPriv_3; "onecoreuap\\private\\net\\inc\\phone\\R"...
0x1800886ac  mov     ecx, ebx
0x1800886ae  mov     r9d, 8Ch
0x1800886b4  xor     edx, edx
0x1800886b6  call    Log_HREvent_28
0x1800886bb  mov     rcx, r14; lpCriticalSection
0x1800886be  call    cs:__imp_LeaveCriticalSection
0x1800886c4  mov     edx, ebx; int
0x1800886c6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800886cb  mov     edx, 1
0x1800886d0  mov     r9d, 3C8h
0x1800886d6  mov     ecx, ebx
0x1800886d8  call    Log_HREvent_31
0x1800886dd  test    rsi, rsi
0x1800886e0  jz      short loc_1800886F1
0x1800886e2  mov     rax, [rsi]
0x1800886e5  mov     rcx, rsi
0x1800886e8  mov     rax, [rax+10h]
0x1800886ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800886f1  mov     rcx, rdi; hObject
0x1800886f4  call    cs:__imp_CloseHandle
0x1800886fa  mov     rcx, [rbp+210h+var_280]
0x1800886fe  test    rcx, rcx
0x180088701  jz      short loc_180088709
0x180088703  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180088709  mov     rcx, [rbp+210h+hObject]; hObject
0x18008870d  test    rcx, rcx
0x180088710  jz      short loc_180088718
0x180088712  call    cs:__imp_CloseHandle
0x180088718  mov     rcx, [rbp+210h+var_290]
0x18008871c  test    rcx, rcx
0x18008871f  jz      loc_180088BCE
0x180088725  mov     rdx, [rcx]
0x180088728  mov     rax, [rdx+10h]
0x18008872c  jmp     loc_180088BC9
0x180088731  mov     rax, [rbx]
0x180088734  mov     rcx, rbx
0x180088737  mov     rax, [rax+8]
0x18008873b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088740  mov     rcx, r14; lpCriticalSection
0x180088743  call    cs:__imp_LeaveCriticalSection
0x180088749  xor     edx, edx; Val
0x18008874b  lea     rcx, [rbp+210h+var_220]; void *
0x18008874f  mov     r8d, 106h; Size
0x180088755  call    memset_0
0x18008875a  lea     rcx, [rbp+210h+var_220]; this
0x18008875e  call    GetRpcClientApplicationPackageInfo
0x180088763  test    eax, eax
0x180088765  jns     short loc_180088776
0x180088767  xor     edx, edx
0x180088769  mov     r9d, 3CFh
0x18008876f  mov     ecx, eax
0x180088771  call    Log_HREvent_31
0x180088776  mov     r8, [rbp+210h+var_290]; struct ISecurityToken *
0x18008877a  lea     r9, [rbp+210h+var_220]; unsigned __int16 *
0x18008877e  mov     rdx, rsi; struct IPhoneServiceListener *
0x180088781  mov     rcx, rbx; this
0x180088784  call    ?AddListener@PhoneNotificationManager@@QEAAJPEAUIPhoneServiceListener@@PEAUISecurityToken@@PEBG@Z; PhoneNotificationManager::AddListener(IPhoneServiceListener *,ISecurityToken *,ushort const *)
0x180088789  mov     r14d, eax
0x18008878c  test    eax, eax
0x18008878e  jns     loc_180088816
0x180088794  mov     edx, eax; int
0x180088796  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008879b  mov     edx, 1
0x1800887a0  mov     r9d, 3D2h
0x1800887a6  mov     ecx, r14d
0x1800887a9  call    Log_HREvent_31
0x1800887ae  test    rbx, rbx
0x1800887b1  jz      short loc_1800887C2
0x1800887b3  mov     rcx, [rbx]
0x1800887b6  mov     rax, [rcx+10h]
0x1800887ba  mov     rcx, rbx
0x1800887bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800887c2  test    rsi, rsi
0x1800887c5  jz      short loc_1800887D6
0x1800887c7  mov     rax, [rsi]
0x1800887ca  mov     rcx, rsi
0x1800887cd  mov     rax, [rax+10h]
0x1800887d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800887d6  mov     rcx, rdi; hObject
0x1800887d9  call    cs:__imp_CloseHandle
0x1800887df  mov     rcx, [rbp+210h+var_280]
0x1800887e3  test    rcx, rcx
0x1800887e6  jz      short loc_1800887EE
0x1800887e8  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800887ee  mov     rcx, [rbp+210h+hObject]; hObject
0x1800887f2  test    rcx, rcx
0x1800887f5  jz      short loc_1800887FD
0x1800887f7  call    cs:__imp_CloseHandle
0x1800887fd  mov     rcx, [rbp+210h+var_290]
0x180088801  test    rcx, rcx
0x180088804  jz      loc_180088B4C
0x18008880a  mov     rax, [rcx]
0x18008880d  mov     rax, [rax+10h]
0x180088811  jmp     loc_180088B47
0x180088816  lea     rax, [rbp+210h+var_248]
0x18008881a  mov     [rbp+210h+var_246], r13
0x18008881e  mov     [rbp+210h+var_258], rax
0x180088822  lea     r9, [rbp+210h+Block]
0x180088826  lea     rax, [rbp+210h+var_248]
0x18008882a  mov     [rbp+210h+var_23E], r13d
0x18008882e  mov     [rbp+210h+var_250], rax
0x180088832  lea     r8, [rbp+210h+var_258]
0x180088836  lea     rax, [rbp+210h+var_268]
0x18008883a  mov     [rbp+210h+var_23A], r13w
0x18008883f  mov     [rbp+210h+Block], rax
0x180088843  mov     rdx, rsi
0x180088846  lea     rax, [rbp+210h+var_268]
0x18008884a  mov     [rbp+210h+var_248], r13w
0x18008884f  mov     rcx, rbx
0x180088852  mov     [rbp+210h+var_270], rax
0x180088856  mov     [rbp+210h+var_266], r13
0x18008885a  mov     [rbp+210h+var_25E], r13d
0x18008885e  mov     [rbp+210h+var_25A], r13w
0x180088863  mov     [rbp+210h+var_268], r13w
0x180088868  call    ?GetListenerIdentity@PhoneNotificationManager@@QEAAJPEAUIPhoneServiceListener@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@1@Z; PhoneNotificationManager::GetListenerIdentity(IPhoneServiceListener *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18008886d  mov     r14d, eax
0x180088870  test    eax, eax
0x180088872  jns     short loc_1800888E0
0x180088874  mov     edx, eax; int
0x180088876  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008887b  mov     edx, 1
0x180088880  mov     r9d, 3D9h
0x180088886  mov     ecx, r14d
  ... truncated ...
```
