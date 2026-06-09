# WSManHttpListenerRequest::ReceivedDataComplete(void)

- ea: `0x18008b0a0`
- end: `0x18008b808`
- name: `?ReceivedDataComplete@WSManHttpListenerRequest@@AEAAXXZ`
- size: `1896`
- prototype: `void __fastcall(struct InboundRequestDetails **this)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008a000`
- `0x18008a930`

## callees

- `0x180005d10`
- `0x1800174c0`
- `0x180019950`
- `0x18001a120`
- `0x18001e9b0`
- `0x18001ec50`
- `0x18004a900`
- `0x18004e7e4`
- `0x18007089c`
- `0x180071d20`
- `0x180072ba0`
- `0x180080470`
- `0x18008b0a0`
- `0x18008b810`
- `0x18008d16c`
- `0x18008d404`
- `0x18010d8c6`
- `0x180112380`
- `0x1801123a8`
- `0x18011349c`
- `0x18011a6d4`
- `0x180121064`
- `0x180123604`
- `0x18016c7ec`
- `0x1801714f0`
- `0x1801a4220`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008b3a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008b405`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008b3a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008b405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b371`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008b184`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008b184`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18008b12c`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18008b12c`

## string_xrefs

- `0x18008b6fd`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18008b0dd`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18008b7b8`: `Failed to allocate memory for packet copy`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall WSManHttpListenerRequest::ReceivedDataComplete(struct InboundRequestDetails **this)
{
  PVOID *v2; // rcx
  CHeap *v3; // rcx
  CHeap *v4; // rcx
  void *Handle; // rax
  PacketParser *v6; // rax
  PacketParser *v7; // rax
  struct InboundRequestDetails *v8; // r14
  struct Packet *v9; // rdi
  struct InboundRequestDetails *v10; // rbx
  struct InboundRequestDetails *v11; // rbx
  struct InboundRequestDetails *v12; // rdi
  struct InboundRequestDetails *v13; // r15
  struct CServiceCommonConfigSettings *v14; // r13
  struct IRequestContext *v15; // r12
  DWORD v16; // ecx
  unsigned int v17; // ebx
  const unsigned __int16 *v18; // rbx
  unsigned int v19; // edi
  union _LARGE_INTEGER HighResTimer; // rax
  DWORD LastError; // eax
  unsigned int v22; // eax
  unsigned int ClientCertificate; // eax
  unsigned int v24; // edi
  const unsigned __int16 *v25; // rax
  int v26; // [rsp+20h] [rbp-30h]
  struct Packet *pulNumLanguages; // [rsp+90h] [rbp+40h] BYREF
  struct Packet **p_pulNumLanguages; // [rsp+98h] [rbp+48h]
  PacketParser *v29; // [rsp+A0h] [rbp+50h]

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_qLd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      219,
      &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
      this,
      *((_DWORD *)this + 46),
      *((_DWORD *)this + 48));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !this[19] )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0xFA3u, L"4003", 0x54Fu, 0);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !this[14] )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0xFA4u, L"4004", 0x54Fu, 0);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 408) )
  {
    ClientCertificate = WSManHttpListenerRequest::GetClientCertificate((WSManHttpListenerRequest *)this);
    v24 = ClientCertificate;
    if ( ClientCertificate )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          220,
          &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
          ClientCertificate);
      WSManHttpListenerRequest::SendHttpError(
        (WSManHttpListenerRequest *)this,
        0x1F7u,
        1,
        0,
        0,
        v24,
        L"Failed to retrieve client certificate",
        &Class);
    }
    goto LABEL_9;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 )
  {
    HighResTimer = GetHighResTimer();
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      221,
      &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
      (union _LARGE_INTEGER)HighResTimer.QuadPart,
      this);
  }
  if ( WSManHttpListenerRequest::EvaluateHeaders((WSManHttpListenerRequest *)this) )
  {
    if ( !WSManHttpListenerRequest::ProcessPacket((WSManHttpListenerRequest *)this) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      goto LABEL_9;
    }
    LODWORD(pulNumLanguages) = 0;
    p_pulNumLanguages = &pulNumLanguages;
    if ( CHeap::GetHandle(v3) )
    {
      Handle = CHeap::GetHandle(v4);
      v6 = (PacketParser *)HeapAlloc(Handle, 0, 0x10E8u);
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0xAAu, L"170", 0x54Fu, 0);
      v6 = 0;
    }
    v29 = v6;
    if ( v6 )
      v7 = PacketParser::PacketParser(v6);
    else
      v7 = 0;
    this[576] = v7;
    if ( v7 )
    {
      if ( !this[661] )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0xFC9u, L"4041", 0x54Fu, 0);
      if ( !this[573] )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0xFCAu, L"4042", 0x54Fu, 0);
        goto LABEL_9;
      }
      (*((void (__fastcall **)(char *, __int64))this[577] + 25))((char *)this + 4616, 1);
      v8 = this[22];
      pulNumLanguages = 0;
      if ( PacketPool::GetPacket(*((PacketPool **)v8 + 3), *((_DWORD *)v8 + 12), &pulNumLanguages) )
      {
        v9 = 0;
      }
      else
      {
        v9 = pulNumLanguages;
        if ( *((_DWORD *)pulNumLanguages + 12) != *((_DWORD *)v8 + 12) )
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\packetpool.h", 0x19Fu, L"415", 0x54Fu, 0);
        memcpy_0(*((void **)v9 + 5), *((const void **)v8 + 5), *((unsigned int *)v8 + 12));
      }
      v10 = this[573];
      AutoCleanup<AutoLocklessItemRecycle<Packet>,Packet *>::ReleasePtr((char *)v10 + 512);
      *((_QWORD *)v10 + 64) = v9;
      v11 = this[573];
      if ( *((_QWORD *)v11 + 64) )
      {
        this[22] = 0;
        *((_BYTE *)this + 5312) = 0;
        v12 = this[576];
        AutoCleanup<AutoDelete<PacketParser>,PacketParser *>::ReleasePtr((char *)v11 + 264);
        *((_QWORD *)v11 + 33) = v12;
        *((_DWORD *)this[573] + 170) = *((_DWORD *)this + 30);
        *((_DWORD *)this[573] + 171) = *((_DWORD *)this + 34);
        v13 = this[576];
        v14 = this[661];
        v15 = (struct IRequestContext *)*((_QWORD *)this[573] + 9);
        if ( !v15 )
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\packetparser.cpp", 0x69u, L"105", 0x54Fu, 0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_19bfc108516638e631769676a3097d1e_Traceguids, v8);
        *((_QWORD *)v13 + 4) = *((_QWORD *)v8 + 3);
        *((_QWORD *)v13 + 3) = v8;
        if ( v14 )
        {
          *((_DWORD *)v13 + 940) = (*(__int64 (__fastcall **)(struct CServiceCommonConfigSettings *))(*(_QWORD *)v14 + 48LL))(v14);
          *((_DWORD *)v13 + 939) = 1;
          *((_DWORD *)v13 + 944) = (*(__int64 (__fastcall **)(struct CServiceCommonConfigSettings *))(*(_QWORD *)v14 + 32LL))(v14);
          *((_DWORD *)v13 + 943) = 1;
        }
        v16 = *((_DWORD *)v13 + 664);
        if ( v16 )
        {
          SetLastError(v16);
          (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)v15 + 24LL))(v15);
        }
        else
        {
          v17 = FwXmlParserCreate(2, (char *)v13 + 2720);
          if ( v17 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_19bfc108516638e631769676a3097d1e_Traceguids, v17);
            (*(void (__fastcall **)(struct IRequestContext *, __int64, _QWORD))(*(_QWORD *)v15 + 64LL))(
              v15,
              1077134251,
              v17);
          }
          else
          {
            v18 = (const unsigned __int16 *)*((_QWORD *)v8 + 5);
            if ( v18 )
            {
              v19 = *((_DWORD *)v8 + 12) >> 1;
            }
            else
            {
              v18 = &Class;
              v19 = 0;
            }
            if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_SOAP_LISTENER_RECEIVING) )
              WSMan::EventHandler::WriteSoapW(&LOG_WSMAN_AN_SOAP_LISTENER_RECEIVING, v18, v19);
            LastError = GetLastError();
            LODWORD(pulNumLanguages) = LastError;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 3) != 0 )
            {
              LOBYTE(v26) = 0;
              TraceSoapMessageW((unsigned int)(v14 != 0) + 1, 2, v18, v19, v26);
              LastError = (unsigned int)pulNumLanguages;
            }
            SetLastError(LastError);
            if ( !(unsigned int)FwXmlParseText(*((_QWORD *)v13 + 340), (int)v18, v19, 0, (__int64)v13 + 2712, v15)
              && (unsigned int)PacketParser::ParsePacketInternal(
                                 v13,
                                 v15,
                                 *(struct _FWXML_ELEMENT **)(*((_QWORD *)v13 + 339) + 16LL),
                                 v14) == 1 )
            {
              WSManHttpListenerRequest::ProcessDocument((WSManHttpListenerRequest *)this);
LABEL_43:
              LODWORD(pulNumLanguages) = 0;
              goto LABEL_10;
            }
          }
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this[573] + 9) + 152LL))(*((_QWORD *)this[573] + 9));
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v22);
        }
        CSoapProcessor::SendRequestContextError(*((CSoapProcessor **)this[10] + 2), this[573]);
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      v25 = L"Failed to allocate memory for packet copy";
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      v25 = L"Failed to allocate memory for packet parser";
    }
    WSManHttpListenerRequest::SendHttpError((WSManHttpListenerRequest *)this, 0x1F4u, 1, 0, 0, 0xEu, v25, &Class);
  }
LABEL_9:
  LODWORD(pulNumLanguages) = 0;
LABEL_10:
  SetThreadPreferredUILanguages(0, 0, (PULONG)&pulNumLanguages);
}

```

## disassembly

```asm
0x18008b0a0  mov     [rsp-38h+arg_18], rbx
0x18008b0a5  push    rbp
0x18008b0a6  push    rsi
0x18008b0a7  push    rdi
0x18008b0a8  push    r12
0x18008b0aa  push    r13
0x18008b0ac  push    r14
0x18008b0ae  push    r15
0x18008b0b0  mov     rbp, rsp
0x18008b0b3  sub     rsp, 50h
0x18008b0b7  mov     rsi, rcx
0x18008b0ba  lea     r12, WPP_GLOBAL_Control
0x18008b0c1  lea     r13, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18008b0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b0cf  cmp     rcx, r12
0x18008b0d2  jnz     loc_18008B5AC
0x18008b0d8  mov     ebx, 54Fh
0x18008b0dd  lea     rdi, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x18008b0e4  xor     r15d, r15d
0x18008b0e7  cmp     [rsi+98h], r15
0x18008b0ee  jz      loc_18008B5ED
0x18008b0f4  cmp     [rsi+70h], r15
0x18008b0f8  jz      loc_18008B615
0x18008b0fe  cmp     [rsi+198h], r15b
0x18008b105  jnz     loc_18008B63D
0x18008b10b  cmp     rcx, r12
0x18008b10e  jnz     loc_18008B30E
0x18008b114  mov     rcx, rsi; this
0x18008b117  call    ?EvaluateHeaders@WSManHttpListenerRequest@@AEAA_NXZ; WSManHttpListenerRequest::EvaluateHeaders(void)
0x18008b11c  test    al, al
0x18008b11e  jnz     short loc_18008B14A
0x18008b120  mov     dword ptr [rbp+pulNumLanguages], r15d
0x18008b124  lea     r8, [rbp+pulNumLanguages]; pulNumLanguages
0x18008b128  xor     edx, edx; pwszLanguagesBuffer
0x18008b12a  xor     ecx, ecx; dwFlags
0x18008b12c  call    cs:__imp_SetThreadPreferredUILanguages
0x18008b132  mov     rbx, [rsp+50h+arg_18]
0x18008b13a  add     rsp, 50h
0x18008b13e  pop     r15
0x18008b140  pop     r14
0x18008b142  pop     r13
0x18008b144  pop     r12
0x18008b146  pop     rdi
0x18008b147  pop     rsi
0x18008b148  pop     rbp
0x18008b149  retn
0x18008b14a  mov     rcx, rsi; this
0x18008b14d  call    ?ProcessPacket@WSManHttpListenerRequest@@AEAA_NXZ; WSManHttpListenerRequest::ProcessPacket(void)
0x18008b152  test    al, al
0x18008b154  jz      loc_18008B553
0x18008b15a  mov     dword ptr [rbp+pulNumLanguages], r15d
0x18008b15e  lea     rax, [rbp+pulNumLanguages]
0x18008b162  mov     [rbp+arg_8], rax
0x18008b166  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18008b16b  test    rax, rax
0x18008b16e  jz      loc_18008B6E9
0x18008b174  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18008b179  xor     edx, edx; dwFlags
0x18008b17b  mov     r8d, 10E8h; dwBytes
0x18008b181  mov     rcx, rax; hHeap
0x18008b184  call    cs:__imp_HeapAlloc
0x18008b18a  mov     [rbp+arg_10], rax
0x18008b18e  test    rax, rax
0x18008b191  jz      loc_18008B342
0x18008b197  mov     rcx, rax; this
0x18008b19a  call    ??0PacketParser@@QEAA@XZ; PacketParser::PacketParser(void)
0x18008b19f  nop
0x18008b1a0  mov     [rsi+1200h], rax
0x18008b1a7  test    rax, rax
0x18008b1aa  jz      loc_18008B711
0x18008b1b0  cmp     [rsi+14A8h], r15
0x18008b1b7  jz      loc_18008B72B
0x18008b1bd  cmp     [rsi+11E8h], r15
0x18008b1c4  jz      loc_18008B74C
0x18008b1ca  lea     rcx, [rsi+1208h]
0x18008b1d1  mov     rax, [rcx]
0x18008b1d4  mov     edx, 1
0x18008b1d9  mov     rax, [rax+0C8h]
0x18008b1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b1e5  mov     r14, [rsi+0B0h]
0x18008b1ec  mov     [rbp+pulNumLanguages], r15
0x18008b1f0  lea     r8, [rbp+pulNumLanguages]; struct Packet **
0x18008b1f4  mov     edx, [r14+30h]; unsigned int
0x18008b1f8  mov     rcx, [r14+18h]; this
0x18008b1fc  call    ?GetPacket@PacketPool@@QEAAKKPEAPEAVPacket@@@Z; PacketPool::GetPacket(ulong,Packet * *)
0x18008b201  test    eax, eax
0x18008b203  jz      loc_18008B52C
0x18008b209  mov     rdi, r15
0x18008b20c  mov     rbx, [rsi+11E8h]
0x18008b213  lea     rcx, [rbx+200h]
0x18008b21a  call    ?ReleasePtr@?$AutoCleanup@V?$AutoLocklessItemRecycle@VPacket@@@@PEAVPacket@@@@AEAAXXZ; AutoCleanup<AutoLocklessItemRecycle<Packet>,Packet *>::ReleasePtr(void)
0x18008b21f  mov     [rbx+200h], rdi
0x18008b226  mov     rbx, [rsi+11E8h]
0x18008b22d  cmp     [rbx+200h], r15
0x18008b234  jz      loc_18008B792
0x18008b23a  mov     [rsi+0B0h], r15
0x18008b241  mov     [rsi+14C0h], r15b
0x18008b248  mov     rdi, [rsi+1200h]
0x18008b24f  lea     rcx, [rbx+108h]
0x18008b256  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VPacketParser@@@@PEAVPacketParser@@@@AEAAXXZ; AutoCleanup<AutoDelete<PacketParser>,PacketParser *>::ReleasePtr(void)
0x18008b25b  mov     [rbx+108h], rdi
0x18008b262  mov     rcx, [rsi+11E8h]
0x18008b269  mov     eax, [rsi+78h]
0x18008b26c  mov     [rcx+2A8h], eax
0x18008b272  mov     rcx, [rsi+11E8h]
0x18008b279  mov     eax, [rsi+88h]
0x18008b27f  mov     [rcx+2ACh], eax
0x18008b285  mov     r15, [rsi+1200h]
0x18008b28c  mov     r13, [rsi+14A8h]
0x18008b293  mov     rax, [rsi+11E8h]
0x18008b29a  mov     r12, [rax+48h]
0x18008b29e  test    r12, r12
0x18008b2a1  jz      loc_18008B7C4
0x18008b2a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b2ae  lea     rax, WPP_GLOBAL_Control
0x18008b2b5  cmp     rcx, rax
0x18008b2b8  jnz     loc_18008B489
0x18008b2be  mov     rax, [r14+18h]
0x18008b2c2  mov     [r15+20h], rax
0x18008b2c6  mov     [r15+18h], r14
0x18008b2ca  test    r13, r13
0x18008b2cd  jnz     loc_18008B4B3
0x18008b2d3  mov     ecx, [r15+0A60h]; dwErrCode
0x18008b2da  test    ecx, ecx
0x18008b2dc  jnz     loc_18008B405
0x18008b2e2  lea     rdx, [r15+0AA0h]
0x18008b2e9  mov     ecx, 2
0x18008b2ee  call    FwXmlParserCreate
0x18008b2f3  mov     ebx, eax
0x18008b2f5  test    eax, eax
0x18008b2f7  jnz     loc_18008B4FC
0x18008b2fd  mov     rbx, [r14+28h]
0x18008b301  test    rbx, rbx
0x18008b304  jz      short loc_18008B34A
0x18008b306  mov     edi, [r14+30h]
0x18008b30a  shr     edi, 1
0x18008b30c  jmp     short loc_18008B353
0x18008b30e  test    byte ptr [rcx+1Ch], 40h
0x18008b312  jz      loc_18008B114
0x18008b318  call    ?GetHighResTimer@@YA?AT_LARGE_INTEGER@@XZ; GetHighResTimer(void)
0x18008b31d  mov     edx, 0DDh
0x18008b322  mov     [rsp+50h+var_30], rsi
0x18008b327  mov     r9, rax
0x18008b32a  mov     r8, r13
0x18008b32d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b334  mov     rcx, [rcx+10h]
0x18008b338  call    WPP_SF_qq
0x18008b33d  jmp     loc_18008B114
0x18008b342  mov     rax, r15
0x18008b345  jmp     loc_18008B1A0
0x18008b34a  lea     rbx, Class
0x18008b351  xor     edi, edi
0x18008b353  lea     rcx, LOG_WSMAN_AN_SOAP_LISTENER_RECEIVING; struct _EVENT_DESCRIPTOR *
0x18008b35a  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x18008b35f  test    al, al
0x18008b361  jnz     loc_18008B7F0
0x18008b367  xor     r14d, r14d
0x18008b36a  test    r13, r13
0x18008b36d  setnz   r14b
0x18008b371  call    cs:__imp_GetLastError
0x18008b377  mov     dword ptr [rbp+pulNumLanguages], eax
0x18008b37a  mov     r8, cs:WPP_GLOBAL_Control
0x18008b381  test    byte ptr [r8+1Ch], 3
0x18008b386  jz      short loc_18008B3A4
0x18008b388  mov     byte ptr [rsp+50h+var_30], 0
0x18008b38d  mov     r9d, edi
0x18008b390  mov     r8, rbx
0x18008b393  mov     edx, 2
0x18008b398  lea     ecx, [r14+1]
0x18008b39c  call    ?TraceSoapMessageW@@YAXW4TraceRole@@W4TraceDirection@@PEBGK_N@Z; TraceSoapMessageW(TraceRole,TraceDirection,ushort const *,ulong,bool)
0x18008b3a1  mov     eax, dword ptr [rbp+pulNumLanguages]
0x18008b3a4  mov     ecx, eax; dwErrCode
0x18008b3a6  call    cs:__imp_SetLastError
0x18008b3ac  lea     r14, [r15+0A98h]
0x18008b3b3  mov     [rsp+50h+var_28], r12; struct IRequestContext *
0x18008b3b8  mov     [rsp+50h+var_30], r14; __int64
0x18008b3bd  xor     r9d, r9d; int
0x18008b3c0  mov     r8d, edi; int
0x18008b3c3  mov     rdx, rbx; int
0x18008b3c6  mov     rcx, [r15+0AA0h]; int
0x18008b3cd  call    FwXmlParseText
0x18008b3d2  test    eax, eax
0x18008b3d4  jnz     short loc_18008B41B
0x18008b3d6  mov     r8, [r14]
0x18008b3d9  mov     r9, r13; struct CServiceCommonConfigSettings *
0x18008b3dc  mov     r8, [r8+10h]; struct _FWXML_ELEMENT *
0x18008b3e0  mov     rdx, r12; struct CRequestContext *
0x18008b3e3  mov     rcx, r15; this
0x18008b3e6  call    ?ParsePacketInternal@PacketParser@@AEAAHPEAVCRequestContext@@PEAU_FWXML_ELEMENT@@PEAVCServiceCommonConfigSettings@@@Z; PacketParser::ParsePacketInternal(CRequestContext *,_FWXML_ELEMENT *,CServiceCommonConfigSettings *)
0x18008b3eb  cmp     eax, 1
0x18008b3ee  jnz     short loc_18008B41B
0x18008b3f0  mov     rcx, rsi; this
0x18008b3f3  call    ?ProcessDocument@WSManHttpListenerRequest@@AEAAXXZ; WSManHttpListenerRequest::ProcessDocument(void)
0x18008b3f8  nop
0x18008b3f9  mov     dword ptr [rbp+pulNumLanguages], 0
0x18008b400  jmp     loc_18008B124
0x18008b405  call    cs:__imp_SetLastError
0x18008b40b  mov     rax, [r12]
0x18008b40f  mov     rcx, r12
0x18008b412  mov     rax, [rax+18h]
0x18008b416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b41b  mov     rax, cs:WPP_GLOBAL_Control
0x18008b422  lea     rcx, WPP_GLOBAL_Control
0x18008b429  cmp     rax, rcx
0x18008b42c  jz      short loc_18008B470
0x18008b42e  test    dword ptr [rax+1Ch], 200h
0x18008b435  jz      short loc_18008B470
0x18008b437  mov     rax, [rsi+11E8h]
0x18008b43e  mov     rcx, [rax+48h]
0x18008b442  mov     rax, [rcx]
0x18008b445  mov     rax, [rax+98h]
0x18008b44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b451  mov     edx, 0E1h
0x18008b456  mov     r9d, eax
0x18008b459  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18008b460  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b467  mov     rcx, [rcx+10h]
0x18008b46b  call    WPP_SF_d
0x18008b470  mov     rcx, [rsi+50h]
0x18008b474  mov     rdx, [rsi+11E8h]; struct InboundRequestDetails *
0x18008b47b  mov     rcx, [rcx+10h]; this
0x18008b47f  call    ?SendRequestContextError@CSoapProcessor@@QEAAXPEAVInboundRequestDetails@@@Z; CSoapProcessor::SendRequestContextError(InboundRequestDetails *)
0x18008b484  jmp     loc_18008B3F9
0x18008b489  test    dword ptr [rcx+1Ch], 400h
0x18008b490  jz      loc_18008B2BE
0x18008b496  mov     edx, 0Ah
0x18008b49b  mov     r9, r14
0x18008b49e  lea     r8, WPP_19bfc108516638e631769676a3097d1e_Traceguids
0x18008b4a5  mov     rcx, [rcx+10h]
0x18008b4a9  call    WPP_SF_q
0x18008b4ae  jmp     loc_18008B2BE
0x18008b4b3  mov     rax, [r13+0]
0x18008b4b7  mov     rcx, r13
0x18008b4ba  mov     rax, [rax+30h]
0x18008b4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b4c3  mov     [r15+0EB0h], eax
0x18008b4ca  mov     dword ptr [r15+0EACh], 1
0x18008b4d5  mov     rax, [r13+0]
0x18008b4d9  mov     rcx, r13
0x18008b4dc  mov     rax, [rax+20h]
0x18008b4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b4e5  mov     [r15+0EC0h], eax
0x18008b4ec  mov     dword ptr [r15+0EBCh], 1
0x18008b4f7  jmp     loc_18008B2D3
0x18008b4fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b503  lea     rax, WPP_GLOBAL_Control
0x18008b50a  cmp     rcx, rax
0x18008b50d  jnz     short loc_18008B586
0x18008b50f  mov     rax, [r12]
0x18008b513  mov     r8d, ebx
0x18008b516  mov     edx, 4033C3ABh
0x18008b51b  mov     rcx, r12
0x18008b51e  mov     rax, [rax+40h]
0x18008b522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b527  jmp     loc_18008B41B
0x18008b52c  mov     eax, [r14+30h]
0x18008b530  mov     rdi, [rbp+pulNumLanguages]
0x18008b534  cmp     [rdi+30h], eax
0x18008b537  jnz     loc_18008B76D
0x18008b53d  mov     r8d, [r14+30h]; Size
0x18008b541  mov     rdx, [r14+28h]; Src
0x18008b545  mov     rcx, [rdi+28h]; void *
0x18008b549  call    memcpy_0
0x18008b54e  jmp     loc_18008B20C
0x18008b553  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b55a  cmp     rcx, r12
0x18008b55d  jz      loc_18008B120
0x18008b563  test    dword ptr [rcx+1Ch], 200h
0x18008b56a  jz      loc_18008B120
0x18008b570  mov     edx, 0DEh
0x18008b575  mov     r8, r13
0x18008b578  mov     rcx, [rcx+10h]
0x18008b57c  call    WPP_SF_
0x18008b581  jmp     loc_18008B120
0x18008b586  test    dword ptr [rcx+1Ch], 200h
0x18008b58d  jz      short loc_18008B50F
0x18008b58f  mov     edx, 0Bh
0x18008b594  mov     r9d, ebx
0x18008b597  lea     r8, WPP_19bfc108516638e631769676a3097d1e_Traceguids
0x18008b59e  mov     rcx, [rcx+10h]
0x18008b5a2  call    WPP_SF_d
0x18008b5a7  jmp     loc_18008B50F
0x18008b5ac  test    dword ptr [rcx+1Ch], 400h
0x18008b5b3  jz      loc_18008B0D8
0x18008b5b9  mov     edx, 0DBh
0x18008b5be  mov     eax, [rsi+0C0h]
0x18008b5c4  mov     dword ptr [rsp+50h+var_28], eax
0x18008b5c8  mov     eax, [rsi+0B8h]
0x18008b5ce  mov     dword ptr [rsp+50h+var_30], eax
0x18008b5d2  mov     r9, rsi
0x18008b5d5  mov     r8, r13
0x18008b5d8  mov     rcx, [rcx+10h]
0x18008b5dc  call    WPP_SF_qLd
0x18008b5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b5e8  jmp     loc_18008B0D8
0x18008b5ed  mov     [rsp+50h+var_30], r15; struct IRequestContext *
0x18008b5f2  mov     r9d, ebx; unsigned int
0x18008b5f5  lea     r8, a4003; "4003"
0x18008b5fc  mov     edx, 0FA3h; unsigned int
0x18008b601  mov     rcx, rdi; String1
  ... truncated ...
```
