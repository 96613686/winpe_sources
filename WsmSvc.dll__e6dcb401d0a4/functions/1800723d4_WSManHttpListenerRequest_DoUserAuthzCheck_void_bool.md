# WSManHttpListenerRequest::DoUserAuthzCheck(void *,bool)

- ea: `0x1800723d4`
- end: `0x1800729a2`
- name: `?DoUserAuthzCheck@WSManHttpListenerRequest@@AEAAHPEAX_N@Z`
- size: `1486`
- prototype: `__int64 __fastcall(WSManHttpListenerRequest *this, void *, char)`
- caller_count: `6`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800572e0`
- `0x18005936c`
- `0x180059ec0`
- `0x18005b250`
- `0x18016be14`
- `0x18016de18`

## callees

- `0x180005d10`
- `0x180010030`
- `0x180019950`
- `0x1800224f0`
- `0x180025d90`
- `0x18004a900`
- `0x180071400`
- `0x1800723d4`
- `0x18007e530`
- `0x180082fa0`
- `0x18008926c`
- `0x180089da0`
- `0x18008a614`
- `0x18008d16c`
- `0x1800d7920`
- `0x1801123a8`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072819`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800727bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800727bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072486`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072547`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072486`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072547`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800727b1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800727b1`
- `WS2_32!getnameinfo` at `0x180072766`
- `WS2_32!getnameinfo` at `0x180072766`
- `WS2_32!__imp_WSAStartup` at `0x1800726e3`
- `WS2_32!__imp_WSAStartup` at `0x1800726e3`
- `WS2_32!__imp_WSACleanup` at `0x1800727fb`
- `WS2_32!__imp_WSACleanup` at `0x180072868`
- `WS2_32!__imp_WSACleanup` at `0x1800727fb`
- `WS2_32!__imp_WSACleanup` at `0x180072868`

## string_xrefs

- `0x180072465`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180072526`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x1800728ac`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x180072917`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`

## pseudocode

```c
__int64 __fastcall WSManHttpListenerRequest::DoUserAuthzCheck(WSManHttpListenerRequest *this, void *a2, char a3)
{
  CHeap *v6; // rcx
  CHeap *v7; // rcx
  InboundRequestDetails *v8; // rax
  void *Handle; // rax
  InboundRequestDetails *v10; // rbx
  struct InboundRequestDetails **v11; // rsi
  CHeap *v12; // rcx
  CHeap *v13; // rcx
  CRequestContext *v14; // rax
  void *v15; // rax
  CRequestContext *v16; // rdi
  struct InboundRequestDetails *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rdi
  struct InboundRequestDetails *v20; // rbx
  struct InboundRequestDetails *v21; // rbx
  __int64 v22; // rdx
  _OWORD *v23; // rax
  __int64 v24; // rbx
  const SOCKADDR *v25; // r13
  const unsigned __int16 *v26; // r8
  unsigned int v27; // edx
  WCHAR *v28; // r12
  unsigned int v29; // eax
  DWORD LastError; // edi
  socklen_t v31; // edx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rbx
  DWORD ServiceBufferSize; // [rsp+28h] [rbp-D8h]
  DWORD ServiceBufferSizea; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *Flags; // [rsp+30h] [rbp-D0h]
  int v40; // [rsp+40h] [rbp-C0h] BYREF
  void *v41; // [rsp+48h] [rbp-B8h] BYREF
  CRequestContext *v42; // [rsp+50h] [rbp-B0h]
  InboundRequestDetails *v43; // [rsp+58h] [rbp-A8h]
  WSAData WSAData; // [rsp+60h] [rbp-A0h] BYREF
  CHAR pNodeBuffer[80]; // [rsp+200h] [rbp+100h] BYREF

  if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTHORIZING_USER) )
    WSMan::EventHandler::Write(&LOG_WSMAN_AN_AUTHORIZING_USER, 0, 0);
  v41 = a2;
  v40 = 0;
  v42 = (CRequestContext *)&v40;
  if ( CHeap::GetHandle(v6) )
  {
    Handle = CHeap::GetHandle(v7);
    v8 = (InboundRequestDetails *)HeapAlloc(Handle, 0, 0x2D0u);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0xAAu, L"170", 0x54Fu, 0);
    v8 = 0;
  }
  v43 = v8;
  if ( v8 )
    v10 = InboundRequestDetails::InboundRequestDetails(v8);
  else
    v10 = 0;
  v11 = (struct InboundRequestDetails **)((char *)this + 4584);
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr((char *)this + 4584);
  *((_QWORD *)this + 573) = v10;
  if ( !v10 )
    goto LABEL_10;
  (**(void (__fastcall ***)(InboundRequestDetails *))v10)(v10);
  v40 = 0;
  v43 = (InboundRequestDetails *)&v40;
  if ( CHeap::GetHandle(v12) )
  {
    v15 = CHeap::GetHandle(v13);
    v14 = (CRequestContext *)HeapAlloc(v15, 0, 0x2A0u);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0xAAu, L"170", 0x54Fu, 0);
    v14 = 0;
  }
  v42 = v14;
  v16 = v14 ? CRequestContext::CRequestContext(v14) : 0LL;
  v17 = *v11;
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr((char *)*v11 + 72);
  *((_QWORD *)v17 + 9) = v16;
  v18 = *((_QWORD *)*v11 + 9);
  if ( !v18 )
  {
LABEL_10:
    if ( !a3 )
      goto LABEL_57;
    Flags = L"Not enough memory to carry out the request";
    ServiceBufferSize = 14;
LABEL_56:
    WSManHttpListenerRequest::SendHttpError(this, 0x1F4u, 1, 0, 0, ServiceBufferSize, Flags, &Class);
    goto LABEL_57;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 10) + 16LL) + 112LL))(
          *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
          v18,
          *((_QWORD *)this + 55));
  v20 = *v11;
  AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr((char *)*v11 + 80);
  *((_QWORD *)v20 + 10) = v19;
  if ( !*((_QWORD *)*v11 + 10)
    || !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)*v11 + 9) + 144LL))(*((_QWORD *)*v11 + 9)) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x126Fu, L"4719", 0x54Fu, 0);
    if ( !a3 )
      goto LABEL_57;
    Flags = L"Cannot retrieve server settings";
    ServiceBufferSize = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v11 + 9) + 152LL))(*((_QWORD *)*v11 + 9));
    goto LABEL_56;
  }
  *((_QWORD *)*v11 + 8) = *(_QWORD *)(*((_QWORD *)this + 10) + 16LL);
  *((_QWORD *)*v11 + 11) = this;
  *((_QWORD *)*v11 + 13) = *((_QWORD *)this + 55);
  v41 = 0;
  v21 = *v11;
  AutoCleanup<AutoHandle,void *>::ReleasePtr((char *)*v11 + 112);
  *((_QWORD *)v21 + 14) = a2;
  v22 = ((unsigned __int64)*v11 + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)*v11 >> 64);
  v23 = (_OWORD *)*((_QWORD *)this + 14);
  *(_OWORD *)v22 = v23[14];
  *(_OWORD *)(v22 + 16) = v23[15];
  *(_OWORD *)(v22 + 32) = v23[16];
  *(_QWORD *)(v22 + 24) = *((_QWORD *)*v11 + 14);
  memset_0((char *)*v11 + 120, 0, 0x82u);
  v24 = *((_QWORD *)*v11 + 9);
  v25 = *(const SOCKADDR **)(*((_QWORD *)this + 19) + 104LL);
  if ( !v25 )
  {
    v26 = L"1208";
    v27 = 1208;
LABEL_23:
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp",
      v27,
      v26,
      0x54Fu,
      *((struct IRequestContext **)*v11 + 9));
LABEL_45:
    if ( a3 )
    {
      ServiceBufferSizea = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v11 + 9) + 152LL))(*((_QWORD *)*v11 + 9));
      WSManHttpListenerRequest::SendHttpError(
        this,
        0x1F4u,
        1,
        0,
        0,
        ServiceBufferSizea,
        L"Cannot retrieve remote IP",
        &Class);
    }
    goto LABEL_57;
  }
  v28 = (WCHAR *)((char *)*v11 + 120);
  if ( *v11 == (struct InboundRequestDetails *)-120LL )
  {
    v26 = L"1209";
    v27 = 1209;
    goto LABEL_23;
  }
  LOWORD(v40) = v25->sa_family;
  memset_0(&WSAData, 0, sizeof(WSAData));
  v29 = WSAStartup(0x202u, &WSAData);
  LastError = v29;
  if ( v29 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, v29);
    goto LABEL_42;
  }
  v31 = 16;
  if ( (_WORD)v40 != 2 )
    v31 = 28;
  LastError = getnameinfo(v25, v31, pNodeBuffer, 0x41u, 0, 0, 2);
  if ( LastError )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_41;
    v33 = 37;
LABEL_40:
    WPP_SF_d(v32[2], v33, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, LastError);
LABEL_41:
    WSACleanup();
LABEL_42:
    if ( v24 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, LastError);
    SetLastError(LastError);
    goto LABEL_45;
  }
  if ( !MultiByteToWideChar(3u, 0, pNodeBuffer, 65, v28, 65) )
  {
    LastError = GetLastError();
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_41;
    v33 = 38;
    goto LABEL_40;
  }
  WSACleanup();
  if ( a3 )
  {
    CSoapProcessor::AsyncGetUser(*(CSoapProcessor **)(*((_QWORD *)this + 10) + 16LL), *v11);
LABEL_53:
    AutoCleanup<AutoHandle,void *>::ReleasePtr(&v41);
    return 1;
  }
  v34 = *((_QWORD *)this + 14);
  v35 = *(_QWORD *)(v34 + 272);
  if ( v35 )
  {
    if ( UserRecord::AddRef(*(UserRecord **)(v34 + 272), *((struct IRequestContext **)*v11 + 9)) )
    {
      AutoCleanup<AutoRelease<UserRecord>,UserRecord *>::operator=((char *)*v11 + 656, v35);
      InboundRequestDetails::SetOperationToken(*v11);
      goto LABEL_53;
    }
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x129Bu, L"4763", 0x54Fu, 0);
  }
LABEL_57:
  AutoCleanup<AutoHandle,void *>::ReleasePtr(&v41);
  return 0;
}

```

## disassembly

```asm
0x1800723d4  push    rbp
0x1800723d6  push    rbx
0x1800723d7  push    rsi
0x1800723d8  push    rdi
0x1800723d9  push    r12
0x1800723db  push    r13
0x1800723dd  push    r14
0x1800723df  push    r15
0x1800723e1  lea     rbp, [rsp-168h]
0x1800723e9  sub     rsp, 268h
0x1800723f0  mov     rax, cs:__security_cookie
0x1800723f7  xor     rax, rsp
0x1800723fa  mov     [rbp+1A0h+var_50], rax
0x180072401  mov     r15b, r8b
0x180072404  mov     r12, rdx
0x180072407  mov     r14, rcx
0x18007240a  lea     rcx, LOG_WSMAN_AN_AUTHORIZING_USER; struct _EVENT_DESCRIPTOR *
0x180072411  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x180072416  xor     r13d, r13d
0x180072419  test    al, al
0x18007241b  jz      short loc_18007242E
0x18007241d  xor     r8d, r8d; struct _EVENT_DATA_DESCRIPTOR *
0x180072420  xor     edx, edx; unsigned int
0x180072422  lea     rcx, LOG_WSMAN_AN_AUTHORIZING_USER; struct _EVENT_DESCRIPTOR *
0x180072429  call    ?Write@EventHandler@WSMan@@SAXAEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; WSMan::EventHandler::Write(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18007242e  mov     [rsp+2A0h+var_258], r12
0x180072433  mov     [rsp+2A0h+var_260], r13d
0x180072438  lea     rax, [rsp+2A0h+var_260]
0x18007243d  mov     [rsp+2A0h+var_250], rax
0x180072442  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180072447  mov     edi, 54Fh
0x18007244c  test    rax, rax
0x18007244f  jnz     short loc_180072476
0x180072451  mov     [rsp+2A0h+pServiceBuffer], r13; struct IRequestContext *
0x180072456  mov     r9d, edi; unsigned int
0x180072459  lea     r8, a170; "170"
0x180072460  mov     edx, 0AAh; unsigned int
0x180072465  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18007246c  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180072471  mov     rax, r13
0x180072474  jmp     short loc_18007248C
0x180072476  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18007247b  xor     edx, edx; dwFlags
0x18007247d  mov     r8d, 2D0h; dwBytes
0x180072483  mov     rcx, rax; hHeap
0x180072486  call    cs:__imp_HeapAlloc
0x18007248c  mov     [rsp+2A0h+var_248], rax
0x180072491  test    rax, rax
0x180072494  jz      short loc_1800724A3
0x180072496  mov     rcx, rax; this
0x180072499  call    ??0InboundRequestDetails@@QEAA@XZ; InboundRequestDetails::InboundRequestDetails(void)
0x18007249e  mov     rbx, rax
0x1800724a1  jmp     short loc_1800724A6
0x1800724a3  mov     rbx, r13
0x1800724a6  lea     rsi, [r14+11E8h]
0x1800724ad  mov     rcx, rsi
0x1800724b0  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800724b5  mov     [rsi], rbx
0x1800724b8  test    rbx, rbx
0x1800724bb  jnz     short loc_1800724EB
0x1800724bd  test    r15b, r15b
0x1800724c0  jz      loc_180072973
0x1800724c6  lea     r8, Class
0x1800724cd  mov     [rsp+2A0h+var_268], r8
0x1800724d2  lea     rax, aNotEnoughMemor; "Not enough memory to carry out the requ"...
0x1800724d9  mov     qword ptr [rsp+2A0h+Flags], rax
0x1800724de  mov     [rsp+2A0h+ServiceBufferSize], 0Eh
0x1800724e6  jmp     loc_18007295A
0x1800724eb  mov     rax, [rbx]
0x1800724ee  mov     rcx, rbx
0x1800724f1  mov     rax, [rax]
0x1800724f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800724f9  mov     [rsp+2A0h+var_260], r13d
0x1800724fe  lea     rax, [rsp+2A0h+var_260]
0x180072503  mov     [rsp+2A0h+var_248], rax
0x180072508  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18007250d  test    rax, rax
0x180072510  jnz     short loc_180072537
0x180072512  mov     [rsp+2A0h+pServiceBuffer], r13; struct IRequestContext *
0x180072517  mov     r9d, edi; unsigned int
0x18007251a  lea     r8, a170; "170"
0x180072521  mov     edx, 0AAh; unsigned int
0x180072526  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18007252d  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180072532  mov     rax, r13
0x180072535  jmp     short loc_18007254D
0x180072537  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18007253c  xor     edx, edx; dwFlags
0x18007253e  mov     r8d, 2A0h; dwBytes
0x180072544  mov     rcx, rax; hHeap
0x180072547  call    cs:__imp_HeapAlloc
0x18007254d  mov     [rsp+2A0h+var_250], rax
0x180072552  test    rax, rax
0x180072555  jz      short loc_180072564
0x180072557  mov     rcx, rax; this
0x18007255a  call    ??0CRequestContext@@QEAA@XZ; CRequestContext::CRequestContext(void)
0x18007255f  mov     rdi, rax
0x180072562  jmp     short loc_180072567
0x180072564  mov     rdi, r13
0x180072567  mov     rbx, [rsi]
0x18007256a  lea     rcx, [rbx+48h]
0x18007256e  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180072573  mov     [rbx+48h], rdi
0x180072577  mov     rax, [rsi]
0x18007257a  mov     rdx, [rax+48h]
0x18007257e  test    rdx, rdx
0x180072581  jz      loc_1800724BD
0x180072587  mov     rax, [r14+50h]
0x18007258b  mov     rcx, [rax+10h]
0x18007258f  mov     rax, [rcx]
0x180072592  mov     r8, [r14+1B8h]
0x180072599  mov     rax, [rax+70h]
0x18007259d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725a2  mov     rdi, rax
0x1800725a5  mov     rbx, [rsi]
0x1800725a8  lea     rcx, [rbx+50h]
0x1800725ac  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x1800725b1  mov     [rbx+50h], rdi
0x1800725b5  mov     rcx, [rsi]
0x1800725b8  cmp     [rcx+50h], r13
0x1800725bc  jz      loc_180072900
0x1800725c2  mov     rcx, [rcx+48h]
0x1800725c6  mov     rax, [rcx]
0x1800725c9  mov     rax, [rax+90h]
0x1800725d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725d5  test    eax, eax
0x1800725d7  jz      loc_180072900
0x1800725dd  mov     rax, [r14+50h]
0x1800725e1  mov     rcx, [rsi]
0x1800725e4  mov     rax, [rax+10h]
0x1800725e8  mov     [rcx+40h], rax
0x1800725ec  mov     rax, [rsi]
0x1800725ef  mov     [rax+58h], r14
0x1800725f3  mov     rcx, [rsi]
0x1800725f6  mov     rax, [r14+1B8h]
0x1800725fd  mov     [rcx+68h], rax
0x180072601  mov     [rsp+2A0h+var_258], r13
0x180072606  mov     rbx, [rsi]
0x180072609  lea     rcx, [rbx+70h]
0x18007260d  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x180072612  mov     [rbx+70h], r12
0x180072616  mov     rax, [rsi]
0x180072619  lea     rcx, [rax+10h]
0x18007261d  neg     rax
0x180072620  sbb     rdx, rdx
0x180072623  and     rdx, rcx
0x180072626  mov     rax, [r14+70h]
0x18007262a  movups  xmm0, xmmword ptr [rax+0E0h]
0x180072631  movups  xmmword ptr [rdx], xmm0
0x180072634  movups  xmm1, xmmword ptr [rax+0F0h]
0x18007263b  movups  xmmword ptr [rdx+10h], xmm1
0x18007263f  movups  xmm0, xmmword ptr [rax+100h]
0x180072646  movups  xmmword ptr [rdx+20h], xmm0
0x18007264a  mov     rax, [rsi]
0x18007264d  mov     rcx, [rax+70h]
0x180072651  mov     [rdx+18h], rcx
0x180072655  mov     rcx, [rsi]
0x180072658  add     rcx, 78h ; 'x'; void *
0x18007265c  xor     edx, edx; Val
0x18007265e  mov     r8d, 82h; Size
0x180072664  call    memset_0
0x180072669  mov     r12, [rsi]
0x18007266c  mov     rbx, [r12+48h]
0x180072671  mov     rax, [r14+98h]
0x180072678  mov     r13, [rax+68h]
0x18007267c  test    r13, r13
0x18007267f  jnz     short loc_1800726A9
0x180072681  lea     r8, a1208; "1208"
0x180072688  mov     edx, 4B8h; unsigned int
0x18007268d  mov     r9d, 54Fh; unsigned int
0x180072693  mov     [rsp+2A0h+pServiceBuffer], rbx; struct IRequestContext *
0x180072698  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x18007269f  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800726a4  jmp     loc_18007281F
0x1800726a9  add     r12, 78h ; 'x'
0x1800726ad  jnz     short loc_1800726BD
0x1800726af  lea     r8, a1209; "1209"
0x1800726b6  mov     edx, 4B9h
0x1800726bb  jmp     short loc_18007268D
0x1800726bd  movzx   eax, word ptr [r13+0]
0x1800726c2  mov     word ptr [rsp+2A0h+var_260], ax
0x1800726c7  xor     edx, edx; Val
0x1800726c9  mov     r8d, 198h; Size
0x1800726cf  lea     rcx, [rsp+2A0h+WSAData]; void *
0x1800726d4  call    memset_0
0x1800726d9  mov     ecx, 202h; wVersionRequested
0x1800726de  lea     rdx, [rsp+2A0h+WSAData]; lpWSAData
0x1800726e3  call    cs:__imp_WSAStartup
0x1800726e9  mov     edi, eax
0x1800726eb  test    eax, eax
0x1800726ed  jz      short loc_180072730
0x1800726ef  lea     rdx, WPP_GLOBAL_Control
0x1800726f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800726fd  cmp     rcx, rdx
0x180072700  jz      loc_180072801
0x180072706  test    dword ptr [rcx+1Ch], 800h
0x18007270d  jz      loc_180072801
0x180072713  mov     edx, 24h ; '$'
0x180072718  mov     r9d, eax
0x18007271b  lea     r8, WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids
0x180072722  mov     rcx, [rcx+10h]
0x180072726  call    WPP_SF_d
0x18007272b  jmp     loc_180072801
0x180072730  mov     edx, 10h
0x180072735  lea     eax, [rdx+0Ch]
0x180072738  lea     ecx, [rdx-0Eh]
0x18007273b  cmp     word ptr [rsp+2A0h+var_260], cx
0x180072740  cmovnz  edx, eax; SockaddrLength
0x180072743  mov     [rsp+2A0h+Flags], ecx; Flags
0x180072747  mov     [rsp+2A0h+ServiceBufferSize], 0; ServiceBufferSize
0x18007274f  mov     [rsp+2A0h+pServiceBuffer], 0; pServiceBuffer
0x180072758  lea     r9d, [rax+25h]; NodeBufferSize
0x18007275c  lea     r8, [rbp+1A0h+pNodeBuffer]; pNodeBuffer
0x180072763  mov     rcx, r13; pSockaddr
0x180072766  call    cs:__imp_getnameinfo
0x18007276c  mov     edi, eax
0x18007276e  test    eax, eax
0x180072770  jz      short loc_180072795
0x180072772  lea     rdx, WPP_GLOBAL_Control
0x180072779  mov     rcx, cs:WPP_GLOBAL_Control
0x180072780  cmp     rcx, rdx
0x180072783  jz      short loc_1800727FB
0x180072785  test    dword ptr [rcx+1Ch], 800h
0x18007278c  jz      short loc_1800727FB
0x18007278e  mov     edx, 25h ; '%'
0x180072793  jmp     short loc_1800727E8
0x180072795  mov     r9d, 41h ; 'A'; cbMultiByte
0x18007279b  mov     [rsp+2A0h+ServiceBufferSize], r9d; cchWideChar
0x1800727a0  mov     [rsp+2A0h+pServiceBuffer], r12; lpWideCharStr
0x1800727a5  lea     r8, [rbp+1A0h+pNodeBuffer]; lpMultiByteStr
0x1800727ac  xor     edx, edx; dwFlags
0x1800727ae  lea     ecx, [rdx+3]; CodePage
0x1800727b1  call    cs:__imp_MultiByteToWideChar
0x1800727b7  test    eax, eax
0x1800727b9  jnz     loc_180072868
0x1800727bf  call    cs:__imp_GetLastError
0x1800727c5  mov     edi, eax
0x1800727c7  lea     rdx, WPP_GLOBAL_Control
0x1800727ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800727d5  cmp     rcx, rdx
0x1800727d8  jz      short loc_1800727FB
0x1800727da  test    dword ptr [rcx+1Ch], 200h
0x1800727e1  jz      short loc_1800727FB
0x1800727e3  mov     edx, 26h ; '&'
0x1800727e8  mov     r9d, edi
0x1800727eb  lea     r8, WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids
0x1800727f2  mov     rcx, [rcx+10h]
0x1800727f6  call    WPP_SF_d
0x1800727fb  call    cs:__imp_WSACleanup
0x180072801  test    rbx, rbx
0x180072804  jz      short loc_180072817
0x180072806  mov     rax, [rbx]
0x180072809  mov     edx, edi
0x18007280b  mov     rcx, rbx
0x18007280e  mov     rax, [rax+48h]
0x180072812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072817  mov     ecx, edi; dwErrCode
0x180072819  call    cs:__imp_SetLastError
0x18007281f  test    r15b, r15b
0x180072822  jz      loc_180072973
0x180072828  mov     rax, [rsi]
0x18007282b  mov     rcx, [rax+48h]
0x18007282f  mov     rax, [rcx]
0x180072832  mov     rax, [rax+98h]
0x180072839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007283e  lea     r8, Class
0x180072845  mov     [rsp+2A0h+var_268], r8
0x18007284a  lea     rcx, aCannotRetrieve; "Cannot retrieve remote IP"
0x180072851  mov     qword ptr [rsp+2A0h+Flags], rcx
0x180072856  mov     [rsp+2A0h+ServiceBufferSize], eax
0x18007285a  mov     [rsp+2A0h+pServiceBuffer], 0
0x180072863  jmp     loc_18007295F
0x180072868  call    cs:__imp_WSACleanup
0x18007286e  test    r15b, r15b
0x180072871  jz      short loc_180072885
0x180072873  mov     rcx, [r14+50h]
0x180072877  mov     rdx, [rsi]; struct InboundRequestDetails *
0x18007287a  mov     rcx, [rcx+10h]; this
0x18007287e  call    ?AsyncGetUser@CSoapProcessor@@QEAAXPEAVInboundRequestDetails@@@Z; CSoapProcessor::AsyncGetUser(InboundRequestDetails *)
0x180072883  jmp     short loc_1800728EF
0x180072885  mov     rax, [r14+70h]
0x180072889  mov     rbx, [rax+110h]
0x180072890  test    rbx, rbx
0x180072893  jnz     short loc_1800728BD
0x180072895  mov     [rsp+2A0h+pServiceBuffer], rbx; struct IRequestContext *
0x18007289a  mov     r9d, 54Fh; unsigned int
0x1800728a0  lea     r8, a4763; "4763"
0x1800728a7  mov     edx, 129Bh; unsigned int
0x1800728ac  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x1800728b3  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800728b8  jmp     loc_180072973
0x1800728bd  mov     rdx, [rsi]
0x1800728c0  mov     rdx, [rdx+48h]; struct IRequestContext *
0x1800728c4  mov     rcx, rbx; this
0x1800728c7  call    ?AddRef@UserRecord@@QEAA_NAEAVIRequestContext@@@Z; UserRecord::AddRef(IRequestContext &)
0x1800728cc  test    al, al
0x1800728ce  jz      loc_180072973
0x1800728d4  mov     rcx, [rsi]
0x1800728d7  add     rcx, 290h
0x1800728de  mov     rdx, rbx
  ... truncated ...
```
