# WSManProvHost::ProcessRequest(uchar *,ulong,_WSMAN_PROVHOST_SENDERDETAILS *,_WSMAN_PROVHOST_CONFIGDETAILS *,_WSMAN_PROVHOST_RESPONSE *)

- ea: `0x180049860`
- end: `0x18004a8f1`
- name: `?ProcessRequest@WSManProvHost@@UEAAJPEAEKPEAU_WSMAN_PROVHOST_SENDERDETAILS@@PEAU_WSMAN_PROVHOST_CONFIGDETAILS@@PEAU_WSMAN_PROVHOST_RESPONSE@@@Z`
- size: `4241`
- prototype: `__int64 __fastcall(WSManProvHost *this, unsigned __int8 *, unsigned int, struct _WSMAN_PROVHOST_SENDERDETAILS *, struct _WSMAN_PROVHOST_CONFIGDETAILS *, struct _WSMAN_PROVHOST_RESPONSE *)`
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005d10`
- `0x180010030`
- `0x1800224f0`
- `0x180025d90`
- `0x180026310`
- `0x180031600`
- `0x180033e10`
- `0x180049860`
- `0x18004a900`
- `0x18004e0d0`
- `0x180053c24`
- `0x18005d800`
- `0x18005f000`
- `0x180071cdc`
- `0x180099f70`
- `0x1800bf830`
- `0x1800bf864`
- `0x1800c5460`
- `0x1800c6124`
- `0x1800ce6a0`
- `0x1800d7920`
- `0x1800ec300`
- `0x1800eeea4`
- `0x1800f4100`
- `0x1800f7bac`
- `0x1800fe630`
- `0x18010d8c6`
- `0x180112380`
- `0x1801123a8`
- `0x180174a18`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a353`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180049cde`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180049cde`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049d11`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180049d11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800498f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049997`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049b5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049beb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049c60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800498f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049997`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049b5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049beb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049c60`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180049e83`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180049e83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a432`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a6e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a432`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a6e3`

## string_xrefs

- `0x18004a031`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004a09d`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004a117`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004a1a9`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004a1e4`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WSManProvHost::ProcessRequest(
        WSManProvHost *this,
        unsigned __int8 *a2,
        unsigned int a3,
        struct _WSMAN_PROVHOST_SENDERDETAILS *a4,
        struct _WSMAN_PROVHOST_CONFIGDETAILS *a5,
        struct _WSMAN_PROVHOST_RESPONSE *a6)
{
  SIZE_T v7; // r15
  CHeap *v9; // rcx
  CHeap *v10; // rcx
  void *Handle; // rax
  InboundRequestDetails *v12; // rax
  InboundRequestDetails *v13; // rsi
  CHeap *v14; // rcx
  CHeap *v15; // rcx
  void *v16; // rax
  CServiceCommonConfigSettings *v17; // rdi
  int v18; // ebx
  int v19; // r12d
  _WORD *v20; // rdx
  unsigned __int64 v21; // r8
  __int64 PoolItem; // rax
  CHeap *v23; // rcx
  __int64 v24; // rbx
  const void *v25; // rdi
  CHeap *v26; // rcx
  void *v27; // rax
  LPVOID v28; // rdi
  void *v29; // rcx
  __int64 v30; // rax
  CHAR *v31; // rbx
  void *v32; // rdi
  int v33; // eax
  CHeap *v34; // rcx
  CHeap *v35; // rcx
  void *v36; // rax
  CRequestContext *v37; // rax
  CRequestContext *v38; // rbx
  struct IRequestContext **v39; // r15
  CHeap *v40; // rcx
  CHeap *v41; // rcx
  void *v42; // rax
  IPCListenerRequest *v43; // rax
  IPCListenerRequest *v44; // r14
  unsigned int v45; // eax
  signed int LastError; // ebx
  void *v47; // rbx
  DWORD v48; // eax
  unsigned __int16 *v49; // rbx
  Packet *v50; // rcx
  struct _WSMAN_PROVHOST_RESPONSE *v51; // rcx
  int v52; // eax
  void *Heap; // rax
  int v55; // ecx
  unsigned __int8 *ListenerShellOperation; // rax
  struct CListenerShell *v57; // rsi
  bool v58; // cc
  __int64 (*v59)(void); // rax
  unsigned int v60; // ebx
  struct IPCListener *v61; // rdx
  __int64 (*v62)(void); // rax
  unsigned int v63; // ebx
  InboundRequestDetails *v64; // [rsp+30h] [rbp-D0h] BYREF
  SIZE_T *p_cb; // [rsp+38h] [rbp-C8h] BYREF
  SIZE_T cb; // [rsp+40h] [rbp-C0h] BYREF
  void *v67; // [rsp+48h] [rbp-B8h] BYREF
  void *v68; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v69; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 *v70; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v72; // [rsp+70h] [rbp-90h]
  int v73; // [rsp+78h] [rbp-88h]
  int v74; // [rsp+7Ch] [rbp-84h]
  int v75; // [rsp+80h] [rbp-80h]
  int v76; // [rsp+84h] [rbp-7Ch]
  int v77; // [rsp+88h] [rbp-78h]
  int v78; // [rsp+8Ch] [rbp-74h]
  _QWORD v79[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v80; // [rsp+A0h] [rbp-60h]
  __int128 v81; // [rsp+B0h] [rbp-50h]
  __int64 v82; // [rsp+C0h] [rbp-40h]
  int v83; // [rsp+C8h] [rbp-38h]
  struct _WSMAN_PROVHOST_RESPONSE *v84; // [rsp+D0h] [rbp-30h]
  HANDLE Handles[2]; // [rsp+D8h] [rbp-28h] BYREF
  struct _WSMAN_CERTIFICATE_DETAILS v86; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v87[672]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v88[323]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned int v89; // [rsp+DC8h] [rbp+CC8h]

  v7 = a3;
  Src = a2;
  v84 = a6;
  v9 = (CHeap *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_769441059adc374bf6ea72702644ec2e_Traceguids);
  *(_OWORD *)a6 = 0;
  *((_OWORD *)a6 + 1) = 0;
  LODWORD(cb) = 0;
  p_cb = &cb;
  if ( CHeap::GetHandle(v9) )
  {
    Handle = CHeap::GetHandle(v10);
    v12 = (InboundRequestDetails *)HeapAlloc(Handle, 0, 0x2D0u);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0xAAu, L"170", 0x54Fu, 0);
    v12 = 0;
  }
  v64 = v12;
  if ( v12 )
    v13 = InboundRequestDetails::InboundRequestDetails(v12);
  else
    v13 = 0;
  p_cb = (SIZE_T *)v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, 2147942414LL);
    goto LABEL_49;
  }
  (**(void (__fastcall ***)(InboundRequestDetails *))v13)(v13);
  v80 = 0;
  v79[0] = *(_QWORD *)a4;
  *((_QWORD *)&v81 + 1) = *((_QWORD *)a4 + 1);
  v79[1] = *((_QWORD *)a4 + 2);
  *(_QWORD *)&v81 = *((_QWORD *)a4 + 7);
  v86 = *(struct _WSMAN_CERTIFICATE_DETAILS *)((char *)a4 + 24);
  if ( !CHeap::GetHandle(v14) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0xAAu, L"170", 0x54Fu, 0);
    goto LABEL_46;
  }
  v16 = CHeap::GetHandle(v15);
  v17 = (CServiceCommonConfigSettings *)HeapAlloc(v16, 0, 0x70u);
  if ( !v17 )
  {
LABEL_46:
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr((char *)v13 + 80);
    *((_QWORD *)v13 + 10) = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, 2147942414LL);
LABEL_49:
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
    return 2147942414LL;
  }
  v18 = *((_DWORD *)a5 + 13);
  v19 = *((_DWORD *)a5 + 12);
  LODWORD(v64) = *((_DWORD *)a5 + 11);
  LODWORD(v67) = *((_DWORD *)a5 + 10);
  LODWORD(v69) = *((_DWORD *)a5 + 9);
  LODWORD(v68) = *((_DWORD *)a5 + 8);
  LODWORD(v70) = *((_DWORD *)a5 + 7);
  LODWORD(v72) = *((_DWORD *)a5 + 6);
  v78 = *((_DWORD *)a5 + 5);
  v77 = *((_DWORD *)a5 + 4);
  v76 = *((_DWORD *)a5 + 3);
  v75 = *((_DWORD *)a5 + 2);
  v74 = *((_DWORD *)a5 + 1);
  v73 = *(_DWORD *)a5;
  CServiceCommonConfigSettings::CServiceCommonConfigSettings(v17);
  *(_QWORD *)v17 = &IPCConfigSettings::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6896eec05d4b3c500138a16dc71a8881_Traceguids);
  *((_DWORD *)v17 + 4) = v73;
  *((_DWORD *)v17 + 5) = v74;
  *((_DWORD *)v17 + 6) = v75;
  *((_DWORD *)v17 + 7) = v76;
  *((_DWORD *)v17 + 8) = v77;
  *((_DWORD *)v17 + 9) = v78;
  *((_DWORD *)v17 + 10) = (_DWORD)v72;
  *((_DWORD *)v17 + 11) = (_DWORD)v70;
  *((_DWORD *)v17 + 12) = (_DWORD)v68;
  *((_DWORD *)v17 + 20) = (_DWORD)v69;
  *((_DWORD *)v17 + 22) = (_DWORD)v67;
  *((_DWORD *)v17 + 23) = (_DWORD)v64;
  *((_DWORD *)v17 + 24) = v19;
  *((_DWORD *)v17 + 26) = v18;
  *((_DWORD *)v17 + 13) = 1;
  *((_DWORD *)v17 + 14) = 1;
  *((_DWORD *)v17 + 15) = 1;
  *((_DWORD *)v17 + 16) = 1;
  *((_DWORD *)v17 + 17) = 1;
  *((_DWORD *)v17 + 18) = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6896eec05d4b3c500138a16dc71a8881_Traceguids);
  AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr((char *)v13 + 80);
  *((_QWORD *)v13 + 10) = v17;
  v20 = (_WORD *)*((_QWORD *)a4 + 9);
  if ( !v20 )
    goto LABEL_140;
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  if ( v21 >= 0x41 )
  {
LABEL_140:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\provhost\\class\\provhostclass.cpp", 0x1F4u, L"500", 0x54Fu, 0);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
    return 2147943759LL;
  }
  memcpy_0((char *)v13 + 120, v20, 2 * v21 + 2);
  PoolItem = LocklessPool<Packet>::GetPoolItem((char *)this + 48);
  v24 = PoolItem;
  *((_QWORD *)v13 + 32) = PoolItem;
  if ( !PoolItem )
  {
LABEL_81:
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
    return 2147942414LL;
  }
  v25 = *(const void **)(PoolItem + 32);
  if ( v25 )
  {
    Heap = WSManMemory::GetHeap();
    if ( HeapSize(Heap, 0, v25) >= v7 )
    {
      v28 = *(LPVOID *)(v24 + 32);
      goto LABEL_22;
    }
  }
  if ( !CHeap::GetHandle(v23) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0xAAu, L"170", 0x54Fu, 0);
    goto LABEL_80;
  }
  v27 = CHeap::GetHandle(v26);
  v28 = HeapAlloc(v27, 0, v7);
  if ( !v28 )
  {
LABEL_80:
    Packet::Recycle(*((Packet **)v13 + 32));
    *((_QWORD *)v13 + 32) = 0;
    goto LABEL_81;
  }
  v29 = *(void **)(v24 + 32);
  if ( v29 )
    WSManMemory::Free(v29, 0);
  *(_QWORD *)(v24 + 32) = v28;
LABEL_22:
  *(_QWORD *)(v24 + 40) = v28;
  *(_DWORD *)(v24 + 48) = v7;
  v30 = *((_QWORD *)v13 + 32);
  v31 = *(CHAR **)(v30 + 40);
  v32 = 0;
  if ( v31 )
  {
    v33 = *(_DWORD *)(v30 + 48);
  }
  else
  {
    v31 = (CHAR *)Buf1;
    v33 = 0;
  }
  if ( v33 != (_DWORD)v7 )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\provhost\\class\\provhostclass.cpp", 0x202u, L"514", 0x54Fu, 0);
  memcpy_0(v31, Src, v7);
  LODWORD(v64) = 0;
  Src = &v64;
  if ( CHeap::GetHandle(v34) )
  {
    v36 = CHeap::GetHandle(v35);
    v37 = (CRequestContext *)HeapAlloc(v36, 0, 0x2A0u);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0xAAu, L"170", 0x54Fu, 0);
    v37 = 0;
  }
  v67 = v37;
  if ( v37 )
    v38 = CRequestContext::CRequestContext(v37);
  else
    v38 = 0;
  v39 = (struct IRequestContext **)((char *)v13 + 72);
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr((char *)v13 + 72);
  *((_QWORD *)v13 + 9) = v38;
  if ( !v38 )
  {
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
    return 2147942414LL;
  }
  *((_QWORD *)v13 + 8) = *((_QWORD *)this + 4);
  *((_DWORD *)v13 + 170) = *((_DWORD *)a4 + 16);
  *((_DWORD *)v13 + 171) = *((_DWORD *)a4 + 17);
  if ( !CHeap::GetHandle(v40) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0xAAu, L"170", 0x54Fu, 0);
    goto LABEL_33;
  }
  v42 = CHeap::GetHandle(v41);
  v43 = (IPCListenerRequest *)HeapAlloc(v42, 0, 0x88u);
  if ( !v43 )
  {
LABEL_33:
    v44 = 0;
    goto LABEL_34;
  }
  v61 = 0;
  if ( this )
    v61 = (WSManProvHost *)((char *)this + 16);
  v44 = IPCListenerRequest::IPCListenerRequest(v43, v61);
LABEL_34:
  v64 = v44;
  if ( !v44 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, 2147942414LL);
    AutoCleanup<AutoRelease<IPCListenerRequest>,IPCListenerRequest *>::ReleasePtr(&v64);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
    return 2147942414LL;
  }
  v45 = IPCListenerRequest::Initialize(v44, v13, (struct WSMAN_SENDER_DETAILS_INTERNAL *)v79, &v86);
  LastError = v45;
  if ( v45 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, v45);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_108;
  }
  *((_QWORD *)v13 + 11) = v44;
  v47 = (void *)*((_QWORD *)v44 + 10);
  if ( !v47 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\provhost\\class\\provhostclass.cpp", 0x22Cu, L"556", 0x54Fu, 0);
    AutoCleanup<AutoRelease<IPCListenerRequest>,IPCListenerRequest *>::ReleasePtr(&v64);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
    return 2147943759LL;
  }
  (*(void (__fastcall **)(WSManProvHost *))(*(_QWORD *)this + 8LL))(this);
  (**((void (__fastcall ***)(__int64))v44 + 4))((__int64)v44 + 32);
  if ( !QueueUserWorkItem(WSManProvHost::ExecuteIPCRequest, v44, 0x10u) )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(WSManProvHost *))(*(_QWORD *)this + 16LL))(this);
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*((_QWORD *)v44 + 4) + 8LL))((__int64)v44 + 32, 0, 0);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_108;
  }
  Handles[0] = v47;
  Handles[1] = *((HANDLE *)this + 49);
  v48 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
  if ( v48 )
  {
    if ( v48 == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_769441059adc374bf6ea72702644ec2e_Traceguids);
      AutoCleanup<AutoRelease<IPCListenerRequest>,IPCListenerRequest *>::ReleasePtr(&v64);
      AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
      return 2147943395LL;
    }
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        WPP_769441059adc374bf6ea72702644ec2e_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_108:
    AutoCleanup<AutoRelease<IPCListenerRequest>,IPCListenerRequest *>::ReleasePtr(&v64);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
    return (unsigned int)LastError;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_769441059adc374bf6ea72702644ec2e_Traceguids);
  v68 = 0;
  LODWORD(cb) = 0;
  v69 = 0;
  v49 = 0;
  v67 = 0;
  v50 = (Packet *)*((_QWORD *)v44 + 2);
  if ( v50 )
  {
    v70 = 0;
    LODWORD(cb) = 0;
    Packet::GetBuffer(v50, &v70, (unsigned int *)&cb);
    Src = (void *)(unsigned int)cb;
    v32 = CoTaskMemAlloc((unsigned int)cb);
    AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v68);
    v68 = v32;
    if ( !v32 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_769441059adc374bf6ea72702644ec2e_Traceguids, 2147942414LL);
      goto LABEL_63;
    }
    memcpy_0(v32, v70, (size_t)Src);
  }
  v72 = 0;
  if ( !*((_DWORD *)v44 + 16) )
  {
    v55 = *((_DWORD *)v13 + 116);
    if ( v55 == 13 || (unsigned int)(v55 - 19) <= 1 || (v72 = 0, v55 == 21) )
    {
      v72 = (unsigned __int16 *)CoTaskMemAlloc(0x4Au);
      AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v69);
      v69 = v72;
      if ( !v72 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_769441059adc374bf6ea72702644ec2e_Traceguids,
            2147942414LL);
LABEL_63:
        AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v67);
        AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v69);
        AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v68);
        AutoCleanup<AutoRelease<IPCListenerRequest>,IPCListenerRequest *>::ReleasePtr(&v64);
        AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
        return 2147942414LL;
      }
      if ( (int)StringCchCopyW(v72, 0x25u, (const unsigned __int16 *)v13 + 260) < 0 )
      {
        WSManError(
          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\provhost\\class\\provhostclass.cpp",
          0x28Fu,
          L"655",
          0x54Fu,
          0);
        AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v67);
        AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v69);
        AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v68);
        AutoCleanup<AutoRelease<IPCListenerRequest>,IPCListenerRequest *>::ReleasePtr(&v64);
        AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
        return 2147549183LL;
      }
      CRequestContext::CRequestContext((CRequestContext *)v87);
      ListenerShellOperation = (unsigned __int8 *)CSoapProcessor::FindListenerShellOperation(
                                                    *((CSoapProcessor **)this + 4),
                                                    (const unsigned __int16 *)v13 + 260,
                                                    (struct IRequestContext *)v87);
      v57 = (struct CListenerShell *)ListenerShellOperation;
      v70 = ListenerShellOperation;
      if ( (v87[16] & 2) != 0 )
      {
        CRequestContext::CopyTo((CRequestContext *)v87, *v39);
        v58 = (*(int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)*v39 + 152LL))(*v39) <= 0;
        v59 = *(__int64 (**)(void))(*(_QWORD *)*v39 + 152LL);
        if ( v58 )
          v60 = v59();
        else
          v60 = (unsigned __int16)v59() | 0x80070000;
        AutoCleanup<AutoRelease<CListenerMasterOperation>,CListenerMasterOperation *>::ReleasePtr(&v70);
        CRequestContext::~CRequestContext((CRequestContext *)v87);
        AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v67);
        AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v69);
        AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v68);
        AutoCleanup<AutoRelease<IPCListenerRequest>,IPCListenerRequest *>::ReleasePtr(&v64);
        AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
        return v60;
      }
      if ( ListenerShellOperation )
      {
        v79[0] = 0;
        v80 = 0;
        v81 = 0;
        v82 = 0;
        v83 = 0;
        RBUFFER::RBUFFER((RBUFFER *)v88, 0);
        v89 = 0;
        if ( !ShellProvider::GetXmlFromShellOperation(
                (ShellProvider *)v79,
                (struct TSTRBUFFER *)v88,
                v57,
                (struct IRequestContext *)v87) )
        {
          CRequestContext::CopyTo((CRequestContext *)v87, *v39);
          v58 = (*(int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)*v39 + 152LL))(*v39) <= 0;
          v62 = *(__int64 (**)(void))(*(_QWORD *)*v39 + 152LL);
          if ( v58 )
            v63 = v62();
          else
            v63 = (unsigned __int16)v62() | 0x80070000;
          RBUFFER::~RBUFFER((RBUFFER *)v88);
          ShellProvider::~ShellProvider((ShellProvider *)v79);
          AutoCleanup<AutoRelease<CListenerMasterOperation>,CListenerMasterOperation *>::ReleasePtr(&v70);
          CRequestContext::~CRequestContext((CRequestContext *)v87);
          AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v67);
          AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v69);
          AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v68);
          AutoCleanup<AutoRelease<IPCListenerRequest>,IPCListenerRequest *>::ReleasePtr(&v64);
          AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
          return v63;
        }
        v49 = (unsigned __int16 *)CoTaskMemAlloc(v89 + 2LL);
        AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v67);
        v67 = v49;
        if ( !v49 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              61,
              WPP_769441059adc374bf6ea72702644ec2e_Traceguids,
              2147942414LL);
          RBUFFER::~RBUFFER((RBUFFER *)v88);
          ShellProvider::~ShellProvider((ShellProvider *)v79);
          AutoCleanup<AutoRelease<CListenerMasterOperation>,CListenerMasterOperation *>::ReleasePtr(&v70);
          CRequestContext::~CRequestContext((CRequestContext *)v87);
          AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v67);
          AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v69);
          AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v68);
          AutoCleanup<AutoRelease<IPCListenerRequest>,IPCListenerRequest *>::ReleasePtr(&v64);
          AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
          return 2147942414LL;
        }
        if ( (int)StringCchCopyW(v49, ((unsigned __int64)v89 + 2) >> 1, v88[0]) < 0 )
        {
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\provhost\\class\\provhostclass.cpp",
            0x2B2u,
            L"690",
            0x54Fu,
            0);
          RBUFFER::~RBUFFER((RBUFFER *)v88);
          ShellProvider::~ShellProvider((ShellProvider *)v79);
          AutoCleanup<AutoRelease<CListenerMasterOperation>,CListenerMasterOperation *>::ReleasePtr(&v70);
          CRequestContext::~CRequestContext((CRequestContext *)v87);
          AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v67);
          AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v69);
          AutoCleanup<AutoCoTaskMemFree,void *>::ReleasePtr(&v68);
          AutoCleanup<AutoRelease<IPCListenerRequest>,IPCListenerRequest *>::ReleasePtr(&v64);
          AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
          return 2147549183LL;
        }
        RBUFFER::~RBUFFER((RBUFFER *)v88);
        ShellProvider::~ShellProvider((ShellProvider *)v79);
      }
      AutoCleanup<AutoRelease<CListenerMasterOperation>,CListenerMasterOperation *>::ReleasePtr(&v70);
      CRequestContext::~CRequestContext((CRequestContext *)v87);
    }
  }
  v51 = v84;
  *((_DWORD *)v84 + 3) = *((_DWORD *)v44 + 16);
  *(_QWORD *)v51 = v32;
  *((_DWORD *)v51 + 2) = cb;
  *((_QWORD *)v51 + 2) = v72;
  *((_QWORD *)v51 + 3) = v49;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_769441059adc374bf6ea72702644ec2e_Traceguids);
  v52 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*((_QWORD *)v44 + 4) + 8LL))((__int64)v44 + 32, 0, 0);
  PrintReleaseTrace(v44, v52);
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&p_cb);
  return 0;
}

```

## disassembly

```asm
0x180049860  push    rbp
0x180049862  push    rbx
0x180049863  push    rsi
0x180049864  push    rdi
0x180049865  push    r12
0x180049867  push    r13
0x180049869  push    r14
0x18004986b  push    r15
0x18004986d  lea     rbp, [rsp-0CE8h]
0x180049875  sub     rsp, 0DE8h
0x18004987c  mov     rax, cs:__security_cookie
0x180049883  xor     rax, rsp
0x180049886  mov     [rbp+0D20h+var_50], rax
0x18004988d  mov     r14, r9
0x180049890  mov     r15d, r8d
0x180049893  mov     [rsp+0E20h+Src], rdx
0x180049898  mov     r13, rcx
0x18004989b  mov     rbx, [rbp+0D20h+arg_28]
0x1800498a2  mov     [rbp+0D20h+var_D50], rbx
0x1800498a6  lea     rdi, WPP_GLOBAL_Control
0x1800498ad  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800498b4  cmp     rcx, rdi
0x1800498b7  jnz     loc_180049FF3
0x1800498bd  xorps   xmm0, xmm0
0x1800498c0  movups  xmmword ptr [rbx], xmm0
0x1800498c3  movups  xmmword ptr [rbx+10h], xmm0
0x1800498c7  xor     r12d, r12d
0x1800498ca  mov     dword ptr [rsp+0E20h+cb], r12d
0x1800498cf  lea     rax, [rsp+0E20h+cb]
0x1800498d4  mov     [rsp+0E20h+var_DE8], rax
0x1800498d9  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800498de  test    rax, rax
0x1800498e1  jz      loc_18004A01A
0x1800498e7  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800498ec  xor     edx, edx; dwFlags
0x1800498ee  mov     r8d, 2D0h; dwBytes
0x1800498f4  mov     rcx, rax; hHeap
0x1800498f7  call    cs:__imp_HeapAlloc
0x1800498fd  mov     [rsp+0E20h+var_DF0], rax
0x180049902  test    rax, rax
0x180049905  jz      loc_180049E04
0x18004990b  mov     rcx, rax; this
0x18004990e  call    ??0InboundRequestDetails@@QEAA@XZ; InboundRequestDetails::InboundRequestDetails(void)
0x180049913  mov     rsi, rax
0x180049916  mov     [rsp+0E20h+var_DE8], rsi
0x18004991b  test    rsi, rsi
0x18004991e  jz      loc_18004A045
0x180049924  mov     rax, [rsi]
0x180049927  mov     rcx, rsi
0x18004992a  mov     rax, [rax]
0x18004992d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049932  xorps   xmm0, xmm0
0x180049935  movdqu  [rbp+0D20h+var_D80], xmm0
0x18004993a  mov     rax, [r14]
0x18004993d  mov     [rbp+0D20h+var_D90], rax
0x180049941  mov     rax, [r14+8]
0x180049945  mov     qword ptr [rbp+0D20h+var_D70+8], rax
0x180049949  mov     rax, [r14+10h]
0x18004994d  mov     [rbp+0D20h+var_D88], rax
0x180049951  mov     rax, [r14+38h]
0x180049955  mov     qword ptr [rbp+0D20h+var_D70], rax
0x180049959  mov     rax, [r14+18h]
0x18004995d  mov     [rbp+0D20h+var_D38.subject], rax
0x180049961  mov     rax, [r14+20h]
0x180049965  mov     [rbp+0D20h+var_D38.issuerName], rax
0x180049969  mov     rax, [r14+28h]
0x18004996d  mov     [rbp+0D20h+var_D38.issuerThumbprint], rax
0x180049971  mov     rax, [r14+30h]
0x180049975  mov     [rbp+0D20h+var_D38.subjectName], rax
0x180049979  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004997e  test    rax, rax
0x180049981  jz      loc_18004A086
0x180049987  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004998c  xor     edx, edx; dwFlags
0x18004998e  mov     r8d, 70h ; 'p'; dwBytes
0x180049994  mov     rcx, rax; hHeap
0x180049997  call    cs:__imp_HeapAlloc
0x18004999d  mov     rdi, rax
0x1800499a0  test    rax, rax
0x1800499a3  jz      loc_180049E14
0x1800499a9  mov     rcx, [rbp+0D20h+arg_20]
0x1800499b0  mov     ebx, [rcx+34h]
0x1800499b3  mov     r12d, [rcx+30h]
0x1800499b7  mov     eax, [rcx+2Ch]
0x1800499ba  mov     dword ptr [rsp+0E20h+var_DF0], eax
0x1800499be  mov     eax, [rcx+28h]
0x1800499c1  mov     dword ptr [rsp+0E20h+var_DD8], eax
0x1800499c5  mov     eax, [rcx+24h]
0x1800499c8  mov     dword ptr [rsp+0E20h+var_DC8], eax
0x1800499cc  mov     eax, [rcx+20h]
0x1800499cf  mov     dword ptr [rsp+0E20h+var_DD0], eax
0x1800499d3  mov     eax, [rcx+1Ch]
0x1800499d6  mov     dword ptr [rsp+0E20h+var_DC0], eax
0x1800499da  mov     eax, [rcx+18h]
0x1800499dd  mov     dword ptr [rsp+0E20h+var_DB0], eax
0x1800499e1  mov     eax, [rcx+14h]
0x1800499e4  mov     [rbp+0D20h+var_D94], eax
0x1800499e7  mov     eax, [rcx+10h]
0x1800499ea  mov     [rbp+0D20h+var_D98], eax
0x1800499ed  mov     eax, [rcx+0Ch]
0x1800499f0  mov     [rbp+0D20h+var_D9C], eax
0x1800499f3  mov     eax, [rcx+8]
0x1800499f6  mov     [rbp+0D20h+var_DA0], eax
0x1800499f9  mov     eax, [rcx+4]
0x1800499fc  mov     [rsp+0E20h+var_DA4], eax
0x180049a00  mov     eax, [rcx]
0x180049a02  mov     [rsp+0E20h+var_DA8], eax
0x180049a06  mov     rcx, rdi; this
0x180049a09  call    ??0CServiceCommonConfigSettings@@IEAA@XZ; CServiceCommonConfigSettings::CServiceCommonConfigSettings(void)
0x180049a0e  lea     rax, ??_7IPCConfigSettings@@6B@; const IPCConfigSettings::`vftable'
0x180049a15  mov     [rdi], rax
0x180049a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a1f  lea     rax, WPP_GLOBAL_Control
0x180049a26  cmp     rcx, rax
0x180049a29  jnz     loc_18004A0AE
0x180049a2f  mov     eax, [rsp+0E20h+var_DA8]
0x180049a33  mov     [rdi+10h], eax
0x180049a36  mov     eax, [rsp+0E20h+var_DA4]
0x180049a3a  mov     [rdi+14h], eax
0x180049a3d  mov     eax, [rbp+0D20h+var_DA0]
0x180049a40  mov     [rdi+18h], eax
0x180049a43  mov     eax, [rbp+0D20h+var_D9C]
0x180049a46  mov     [rdi+1Ch], eax
0x180049a49  mov     eax, [rbp+0D20h+var_D98]
0x180049a4c  mov     [rdi+20h], eax
0x180049a4f  mov     eax, [rbp+0D20h+var_D94]
0x180049a52  mov     [rdi+24h], eax
0x180049a55  mov     eax, dword ptr [rsp+0E20h+var_DB0]
0x180049a59  mov     [rdi+28h], eax
0x180049a5c  mov     eax, dword ptr [rsp+0E20h+var_DC0]
0x180049a60  mov     [rdi+2Ch], eax
0x180049a63  mov     eax, dword ptr [rsp+0E20h+var_DD0]
0x180049a67  mov     [rdi+30h], eax
0x180049a6a  mov     eax, dword ptr [rsp+0E20h+var_DC8]
0x180049a6e  mov     [rdi+50h], eax
0x180049a71  mov     eax, dword ptr [rsp+0E20h+var_DD8]
0x180049a75  mov     [rdi+58h], eax
0x180049a78  mov     eax, dword ptr [rsp+0E20h+var_DF0]
0x180049a7c  mov     [rdi+5Ch], eax
0x180049a7f  mov     [rdi+60h], r12d
0x180049a83  mov     [rdi+68h], ebx
0x180049a86  mov     dword ptr [rdi+34h], 1
0x180049a8d  mov     dword ptr [rdi+38h], 1
0x180049a94  mov     dword ptr [rdi+3Ch], 1
0x180049a9b  mov     dword ptr [rdi+40h], 1
0x180049aa2  mov     dword ptr [rdi+44h], 1
0x180049aa9  mov     dword ptr [rdi+48h], 1
0x180049ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ab7  lea     r12, WPP_GLOBAL_Control
0x180049abe  cmp     rcx, r12
0x180049ac1  jnz     loc_18004A0D5
0x180049ac7  lea     rcx, [rsi+50h]
0x180049acb  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x180049ad0  mov     [rsi+50h], rdi
0x180049ad4  mov     rdx, [r14+48h]; Src
0x180049ad8  test    rdx, rdx
0x180049adb  jz      loc_18004A8B4
0x180049ae1  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180049ae8  nop     dword ptr [rax+rax+00000000h]
0x180049af0  inc     r8
0x180049af3  cmp     word ptr [rdx+r8*2], 0
0x180049af9  jnz     short loc_180049AF0
0x180049afb  cmp     r8, 41h ; 'A'
0x180049aff  jnb     loc_18004A8B4
0x180049b05  lea     r8, ds:2[r8*2]; Size
0x180049b0d  lea     rcx, [rsi+78h]; void *
0x180049b11  call    memcpy_0
0x180049b16  lea     rcx, [r13+30h]
0x180049b1a  call    ?GetPoolItem@?$LocklessPool@VPacket@@@@QEAAPEAVPacket@@PEA_N@Z; LocklessPool<Packet>::GetPoolItem(bool *)
0x180049b1f  mov     rbx, rax
0x180049b22  mov     [rsi+100h], rax
0x180049b29  test    rax, rax
0x180049b2c  jz      loc_18004A13A
0x180049b32  mov     rdi, [rax+20h]
0x180049b36  test    rdi, rdi
0x180049b39  jnz     loc_180049E76
0x180049b3f  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180049b44  test    rax, rax
0x180049b47  jz      loc_18004A0FC
0x180049b4d  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180049b52  mov     r8, r15; dwBytes
0x180049b55  xor     edx, edx; dwFlags
0x180049b57  mov     rcx, rax; hHeap
0x180049b5a  call    cs:__imp_HeapAlloc
0x180049b60  mov     rdi, rax
0x180049b63  test    rax, rax
0x180049b66  jz      loc_18004A123
0x180049b6c  mov     rcx, [rbx+20h]; void *
0x180049b70  test    rcx, rcx
0x180049b73  jnz     loc_18004A15E
0x180049b79  mov     [rbx+20h], rdi
0x180049b7d  mov     eax, r15d
0x180049b80  mov     [rbx+28h], rdi
0x180049b84  mov     [rbx+30h], eax
0x180049b87  mov     rax, [rsi+100h]
0x180049b8e  mov     rbx, [rax+28h]
0x180049b92  xor     edi, edi
0x180049b94  test    rbx, rbx
0x180049b97  jnz     loc_180049E6E
0x180049b9d  lea     rbx, Buf1
0x180049ba4  mov     eax, edi
0x180049ba6  cmp     eax, r15d
0x180049ba9  jnz     loc_18004A16A
0x180049baf  mov     r8, r15; Size
0x180049bb2  mov     rdx, [rsp+0E20h+Src]; Src
0x180049bb7  mov     rcx, rbx; void *
0x180049bba  call    memcpy_0
0x180049bbf  mov     dword ptr [rsp+0E20h+var_DF0], edi
0x180049bc3  lea     rax, [rsp+0E20h+var_DF0]
0x180049bc8  mov     [rsp+0E20h+Src], rax
0x180049bcd  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180049bd2  test    rax, rax
0x180049bd5  jz      loc_18004A192
0x180049bdb  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180049be0  xor     edx, edx; dwFlags
0x180049be2  mov     r8d, 2A0h; dwBytes
0x180049be8  mov     rcx, rax; hHeap
0x180049beb  call    cs:__imp_HeapAlloc
0x180049bf1  mov     [rsp+0E20h+var_DD8], rax
0x180049bf6  test    rax, rax
0x180049bf9  jz      loc_180049E0C
0x180049bff  mov     rcx, rax; this
0x180049c02  call    ??0CRequestContext@@QEAA@XZ; CRequestContext::CRequestContext(void)
0x180049c07  mov     rbx, rax
0x180049c0a  lea     r15, [rsi+48h]
0x180049c0e  mov     rcx, r15
0x180049c11  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180049c16  mov     [r15], rbx
0x180049c19  test    rbx, rbx
0x180049c1c  jz      loc_18004A1BD
0x180049c22  lea     rbx, [r13+10h]
0x180049c26  mov     rax, [rbx+10h]
0x180049c2a  mov     [rsi+40h], rax
0x180049c2e  mov     eax, [r14+40h]
0x180049c32  mov     [rsi+2A8h], eax
0x180049c38  mov     eax, [r14+44h]
0x180049c3c  mov     [rsi+2ACh], eax
0x180049c42  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180049c47  test    rax, rax
0x180049c4a  jz      loc_18004A1CD
0x180049c50  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180049c55  xor     edx, edx; dwFlags
0x180049c57  mov     r8d, 88h; dwBytes
0x180049c5d  mov     rcx, rax; hHeap
0x180049c60  call    cs:__imp_HeapAlloc
0x180049c66  test    rax, rax
0x180049c69  jnz     loc_18004A1F5
0x180049c6f  mov     r14, rdi
0x180049c72  mov     [rsp+0E20h+var_DF0], r14
0x180049c77  test    r14, r14
0x180049c7a  jz      loc_18004A20F
0x180049c80  lea     r9, [rbp+0D20h+var_D38]; struct _WSMAN_CERTIFICATE_DETAILS *
0x180049c84  lea     r8, [rbp+0D20h+var_D90]; struct WSMAN_SENDER_DETAILS_INTERNAL *
0x180049c88  mov     rdx, rsi; struct InboundRequestDetails *
0x180049c8b  mov     rcx, r14; this
0x180049c8e  call    ?Initialize@IPCListenerRequest@@QEAAKPEAVInboundRequestDetails@@PEAVWSMAN_SENDER_DETAILS_INTERNAL@@PEAU_WSMAN_CERTIFICATE_DETAILS@@@Z; IPCListenerRequest::Initialize(InboundRequestDetails *,WSMAN_SENDER_DETAILS_INTERNAL *,_WSMAN_CERTIFICATE_DETAILS *)
0x180049c93  mov     ebx, eax
0x180049c95  test    eax, eax
0x180049c97  jnz     loc_18004A25B
0x180049c9d  mov     [rsi+58h], r14
0x180049ca1  mov     rbx, [r14+50h]
0x180049ca5  test    rbx, rbx
0x180049ca8  jz      loc_18004A2B2
0x180049cae  mov     rax, [r13+0]
0x180049cb2  mov     rcx, r13
0x180049cb5  mov     rax, [rax+8]
0x180049cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cbe  mov     rax, [r14+20h]
0x180049cc2  lea     rcx, [r14+20h]
0x180049cc6  mov     rax, [rax]
0x180049cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cce  mov     r8d, 10h; Flags
0x180049cd4  mov     rdx, r14; Context
0x180049cd7  lea     rcx, ?ExecuteIPCRequest@WSManProvHost@@SAKPEAX@Z; Function
0x180049cde  call    cs:__imp_QueueUserWorkItem
0x180049ce4  test    eax, eax
0x180049ce6  jz      loc_18004A2F6
0x180049cec  mov     [rbp+0D20h+Handles], rbx
0x180049cf0  mov     rax, [r13+188h]
0x180049cf7  mov     [rbp+0D20h+var_D40], rax
0x180049cfb  mov     [rsp+0E20h+bAlertable], edi; bAlertable
0x180049cff  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180049d05  xor     r8d, r8d; bWaitAll
0x180049d08  lea     rdx, [rbp+0D20h+Handles]; lpHandles
0x180049d0c  mov     ecx, 2; nCount
0x180049d11  call    cs:__imp_WaitForMultipleObjectsEx
0x180049d17  test    eax, eax
0x180049d19  jnz     loc_18004A34E
0x180049d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d26  lea     rax, WPP_GLOBAL_Control
0x180049d2d  cmp     rcx, rax
0x180049d30  jnz     loc_180049E9B
0x180049d36  cmp     dword ptr [rsi+1D0h], 0Dh
0x180049d3d  jnz     short loc_180049D46
0x180049d3f  mov     eax, [r13+110h]
0x180049d46  mov     [rsp+0E20h+var_DD0], rdi
0x180049d4b  xor     edx, edx
0x180049d4d  mov     dword ptr [rsp+0E20h+cb], edx
0x180049d51  mov     [rsp+0E20h+var_DC8], rdx
0x180049d56  mov     ebx, edx
  ... truncated ...
```
