# WebSocketServer::SetupHttpApi(void)

- ea: `0x180136d90`
- end: `0x18013725d`
- name: `?SetupHttpApi@WebSocketServer@@AEAAJXZ`
- size: `1229`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180137270`

## callees

- `0x180001574`
- `0x180001f84`
- `0x180079724`
- `0x18007e9e0`
- `0x18007f42c`
- `0x18013568c`
- `0x180136d90`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180136e0c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180136e8a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180136ee4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180136f3b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180137033`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801370b3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013711e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013716f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801371e4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180136e0c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180136e8a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180136ee4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180136f3b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180137033`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801370b3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013711e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013716f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801371e4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180137001`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180137001`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18013713e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18013713e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801371b3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801371b3`
- `WS2_32!__imp_WSAStartup` at `0x180136ddc`
- `WS2_32!__imp_WSAStartup` at `0x180136ddc`
- `HTTPAPI!HttpCreateUrlGroup` at `0x180136f04`
- `HTTPAPI!HttpCreateUrlGroup` at `0x180136f04`
- `HTTPAPI!HttpInitialize` at `0x180136e5f`
- `HTTPAPI!HttpInitialize` at `0x180136e5f`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x180136f69`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x180136f69`
- `HTTPAPI!HttpCreateRequestQueue` at `0x180137088`
- `HTTPAPI!HttpCreateRequestQueue` at `0x180137088`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x1801370e7`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x1801370e7`
- `HTTPAPI!HttpCreateServerSession` at `0x180136ead`
- `HTTPAPI!HttpCreateServerSession` at `0x180136ead`

## pseudocode

```c
__int64 __fastcall WebSocketServer::SetupHttpApi(char *pv)
{
  int ServerSession; // ebx
  unsigned int ActivityIdPrefix; // eax
  __int64 v4; // rdx
  HTTP_URL_GROUP_ID *v5; // r12
  unsigned int i; // r15d
  const WCHAR *v7; // rax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rdx
  HANDLE *v14; // r15
  HANDLE v15; // rax
  HTTP_URL_GROUP_ID v16; // rcx
  PTP_IO ThreadpoolIo; // rax
  unsigned int v18; // eax
  __int64 v19; // rdx
  PTP_WORK ThreadpoolWork; // rax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  const char *v25; // [rsp+30h] [rbp-D0h] BYREF
  const char *v26; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD PropertyInformation[2]; // [rsp+40h] [rbp-C0h] BYREF
  WSAData WSAData; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  ServerSession = WSAStartup(0x202u, &WSAData);
  if ( ServerSession )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      v4 = 21;
LABEL_6:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        &WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
        ActivityIdPrefix,
        ServerSession);
      goto LABEL_7;
    }
    goto LABEL_7;
  }
  pv[76] = 1;
  LODWORD(v25) = 2;
  ServerSession = HttpInitialize((HTTPAPI_VERSION)2, 3u, 0);
  if ( ServerSession )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      v4 = 22;
      goto LABEL_6;
    }
LABEL_7:
    if ( ServerSession > 0 )
      return (unsigned __int16)ServerSession | 0x80070000;
    return (unsigned int)ServerSession;
  }
  pv[77] = 1;
  LODWORD(v25) = 2;
  ServerSession = HttpCreateServerSession((HTTPAPI_VERSION)2, (PHTTP_SERVER_SESSION_ID)pv + 17, 0);
  if ( ServerSession )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      v4 = 23;
      goto LABEL_6;
    }
    goto LABEL_7;
  }
  v5 = (HTTP_URL_GROUP_ID *)(pv + 144);
  ServerSession = HttpCreateUrlGroup(*((_QWORD *)pv + 17), (PHTTP_URL_GROUP_ID)pv + 18, 0);
  if ( ServerSession )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      v4 = 24;
      goto LABEL_6;
    }
    goto LABEL_7;
  }
  for ( i = 0; i < 0xA; ++i )
  {
    v7 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(pv + 88);
    ServerSession = HttpAddUrlToUrlGroup(*v5, v7, 0, 0);
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v25) = ServerSession;
      v26 = "HttpAddUrlToUrlGroup returned win32 result = %d";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)&dword_180293BAC,
        v9,
        v10,
        (__int64)&v26,
        (__int64)&v25);
    }
    if ( !ServerSession )
    {
      v14 = (HANDLE *)(pv + 152);
      LODWORD(v25) = 2;
      ServerSession = HttpCreateRequestQueue((HTTPAPI_VERSION)2, 0, 0, 0, (PHANDLE)pv + 19);
      if ( ServerSession )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_39;
        }
        v12 = RdpX_GetActivityIdPrefix();
        v13 = 26;
        goto LABEL_38;
      }
      v15 = *v14;
      v16 = *v5;
      PropertyInformation[0] = 1;
      PropertyInformation[1] = v15;
      ServerSession = HttpSetUrlGroupProperty(v16, HttpServerBindingProperty, PropertyInformation, 0x10u);
      if ( ServerSession )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_39;
        }
        v12 = RdpX_GetActivityIdPrefix();
        v13 = 27;
LABEL_38:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          &WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
          v12,
          ServerSession);
        goto LABEL_39;
      }
      ThreadpoolIo = CreateThreadpoolIo(*v14, WebSocketServer::IoCompletionCallback, pv, 0);
      *((_QWORD *)pv + 20) = ThreadpoolIo;
      if ( ThreadpoolIo )
      {
        ThreadpoolWork = CreateThreadpoolWork(WebSocketServer::DeferredWebSocketReceiveNotification, pv, 0);
        *((_QWORD *)pv + 21) = ThreadpoolWork;
        if ( ThreadpoolWork )
        {
          ServerSession = 0;
          if ( (unsigned int)CallbackContext > 4 )
          {
            v26 = (const char *)CBaseStringT<unsigned short>::PContents(pv + 88);
            v25 = "HTTP Listener set up";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              v21,
              (unsigned int)byte_180293B43,
              v22,
              v23,
              (__int64)&v25,
              (__int64)&v26);
          }
          return (unsigned int)ServerSession;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)-2147467259;
        }
        v18 = RdpX_GetActivityIdPrefix();
        v19 = 29;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)-2147467259;
        }
        v18 = RdpX_GetActivityIdPrefix();
        v19 = 28;
      }
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        &WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
        v18,
        -2147467259);
      return (unsigned int)-2147467259;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      if ( ServerSession > 0 )
        v11 = (unsigned __int16)ServerSession | 0x80070000;
      else
        v11 = ServerSession;
      LODWORD(v25) = v11;
      v26 = "HttpAddUrlToUrlGroup failed (0x%x) - retrying...";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)&dword_180293B6C,
        v9,
        v10,
        (__int64)&v26,
        (__int64)&v25);
    }
    Sleep(0x3E8u);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpX_GetActivityIdPrefix();
    v13 = 25;
    goto LABEL_38;
  }
LABEL_39:
  if ( ServerSession > 0 )
    return (unsigned __int16)ServerSession | 0x80070000;
  return (unsigned int)ServerSession;
}

```

## disassembly

```asm
0x180136d90  push    rbp
0x180136d92  push    rbx
0x180136d93  push    rsi
0x180136d94  push    rdi
0x180136d95  push    r12
0x180136d97  push    r13
0x180136d99  push    r14
0x180136d9b  push    r15
0x180136d9d  lea     rbp, [rsp-108h]
0x180136da5  sub     rsp, 208h
0x180136dac  mov     rax, cs:__security_cookie
0x180136db3  xor     rax, rsp
0x180136db6  mov     [rbp+140h+var_50], rax
0x180136dbd  mov     r14, rcx
0x180136dc0  xor     edx, edx; Val
0x180136dc2  lea     rcx, [rsp+240h+WSAData]; void *
0x180136dc7  mov     r8d, 198h; Size
0x180136dcd  call    memset_0
0x180136dd2  mov     ecx, 202h; wVersionRequested
0x180136dd7  lea     rdx, [rsp+240h+WSAData]; lpWSAData
0x180136ddc  call    cs:__imp_WSAStartup
0x180136de2  mov     ebx, eax
0x180136de4  test    eax, eax
0x180136de6  jz      short loc_180136E49
0x180136de8  mov     rcx, cs:WPP_GLOBAL_Control
0x180136def  lea     rax, WPP_GLOBAL_Control
0x180136df6  cmp     rcx, rax
0x180136df9  jz      short loc_180136E33
0x180136dfb  test    byte ptr [rcx+1Ch], 8
0x180136dff  jz      short loc_180136E33
0x180136e01  mov     edi, 2
0x180136e06  cmp     [rcx+19h], dil
0x180136e0a  jb      short loc_180136E33
0x180136e0c  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180136e12  lea     edx, [rdi+13h]
0x180136e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180136e1c  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180136e23  mov     r9d, eax
0x180136e26  mov     dword ptr [rsp+240h+RequestQueueHandle], ebx
0x180136e2a  mov     rcx, [rcx+10h]
0x180136e2e  call    WPP_SF_Dd
0x180136e33  test    ebx, ebx
0x180136e35  jle     loc_180137238
0x180136e3b  movzx   ebx, bx
0x180136e3e  or      ebx, 80070000h
0x180136e44  jmp     loc_180137238
0x180136e49  mov     edi, 2
0x180136e4e  mov     byte ptr [r14+4Ch], 1
0x180136e53  xor     r8d, r8d; pReserved
0x180136e56  mov     dword ptr [rsp+240h+var_210], edi
0x180136e5a  mov     ecx, edi; Version
0x180136e5c  lea     edx, [rdi+1]; Flags
0x180136e5f  call    cs:__imp_HttpInitialize
0x180136e65  mov     ebx, eax
0x180136e67  test    eax, eax
0x180136e69  jz      short loc_180136E95
0x180136e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180136e72  lea     rax, WPP_GLOBAL_Control
0x180136e79  cmp     rcx, rax
0x180136e7c  jz      short loc_180136E33
0x180136e7e  test    byte ptr [rcx+1Ch], 8
0x180136e82  jz      short loc_180136E33
0x180136e84  cmp     [rcx+19h], dil
0x180136e88  jb      short loc_180136E33
0x180136e8a  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180136e90  lea     edx, [rdi+14h]
0x180136e93  jmp     short loc_180136E15
0x180136e95  lea     rsi, [r14+88h]
0x180136e9c  mov     byte ptr [r14+4Dh], 1
0x180136ea1  mov     rdx, rsi; ServerSessionId
0x180136ea4  mov     dword ptr [rsp+240h+var_210], edi
0x180136ea8  xor     r8d, r8d; Reserved
0x180136eab  mov     ecx, edi; Version
0x180136ead  call    cs:__imp_HttpCreateServerSession
0x180136eb3  mov     ebx, eax
0x180136eb5  test    eax, eax
0x180136eb7  jz      short loc_180136EF4
0x180136eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180136ec0  lea     rax, WPP_GLOBAL_Control
0x180136ec7  cmp     rcx, rax
0x180136eca  jz      loc_180136E33
0x180136ed0  test    byte ptr [rcx+1Ch], 8
0x180136ed4  jz      loc_180136E33
0x180136eda  cmp     [rcx+19h], dil
0x180136ede  jb      loc_180136E33
0x180136ee4  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180136eea  mov     edx, 17h
0x180136eef  jmp     loc_180136E15
0x180136ef4  mov     rcx, [rsi]; ServerSessionId
0x180136ef7  lea     r12, [r14+90h]
0x180136efe  mov     rdx, r12; pUrlGroupId
0x180136f01  xor     r8d, r8d; Reserved
0x180136f04  call    cs:__imp_HttpCreateUrlGroup
0x180136f0a  mov     ebx, eax
0x180136f0c  test    eax, eax
0x180136f0e  jz      short loc_180136F4B
0x180136f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180136f17  lea     rax, WPP_GLOBAL_Control
0x180136f1e  cmp     rcx, rax
0x180136f21  jz      loc_180136E33
0x180136f27  test    byte ptr [rcx+1Ch], 8
0x180136f2b  jz      loc_180136E33
0x180136f31  cmp     [rcx+19h], dil
0x180136f35  jb      loc_180136E33
0x180136f3b  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180136f41  mov     edx, 18h
0x180136f46  jmp     loc_180136E15
0x180136f4b  xor     r15d, r15d
0x180136f4e  mov     esi, 80070000h
0x180136f53  lea     rcx, [r14+58h]
0x180136f57  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180136f5c  mov     rcx, [r12]; UrlGroupId
0x180136f60  xor     r8d, r8d; UrlContext
0x180136f63  mov     rdx, rax; pFullyQualifiedUrl
0x180136f66  xor     r9d, r9d; Reserved
0x180136f69  call    cs:__imp_HttpAddUrlToUrlGroup
0x180136f6f  mov     ebx, eax
0x180136f71  mov     eax, cs:CallbackContext
0x180136f77  cmp     eax, 4
0x180136f7a  jbe     short loc_180136FAC
0x180136f7c  lea     rax, aHttpaddurltour_1; "HttpAddUrlToUrlGroup returned win32 res"...
0x180136f83  mov     dword ptr [rsp+240h+var_210], ebx
0x180136f87  mov     [rsp+240h+var_208], rax
0x180136f8c  lea     rdx, dword_180293BAC
0x180136f93  lea     rax, [rsp+240h+var_210]
0x180136f98  mov     [rsp+240h+var_218], rax
0x180136f9d  lea     rax, [rsp+240h+var_208]
0x180136fa2  mov     [rsp+240h+RequestQueueHandle], rax
0x180136fa7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180136fac  test    ebx, ebx
0x180136fae  jz      loc_18013706E
0x180136fb4  mov     eax, cs:CallbackContext
0x180136fba  cmp     eax, 4
0x180136fbd  jbe     short loc_180136FFC
0x180136fbf  test    ebx, ebx
0x180136fc1  jg      short loc_180136FC7
0x180136fc3  mov     eax, ebx
0x180136fc5  jmp     short loc_180136FCC
0x180136fc7  movzx   eax, bx
0x180136fca  or      eax, esi
0x180136fcc  mov     dword ptr [rsp+240h+var_210], eax
0x180136fd0  lea     rdx, dword_180293B6C
0x180136fd7  lea     rax, aHttpaddurltour_0; "HttpAddUrlToUrlGroup failed (0x%x) - re"...
0x180136fde  mov     [rsp+240h+var_208], rax
0x180136fe3  lea     rax, [rsp+240h+var_210]
0x180136fe8  mov     [rsp+240h+var_218], rax
0x180136fed  lea     rax, [rsp+240h+var_208]
0x180136ff2  mov     [rsp+240h+RequestQueueHandle], rax
0x180136ff7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180136ffc  mov     ecx, 3E8h; dwMilliseconds
0x180137001  call    cs:__imp_Sleep
0x180137007  inc     r15d
0x18013700a  cmp     r15d, 0Ah
0x18013700e  jb      loc_180136F53
0x180137014  mov     rcx, cs:WPP_GLOBAL_Control
0x18013701b  lea     rax, WPP_GLOBAL_Control
0x180137022  cmp     rcx, rax
0x180137025  jz      short loc_18013705C
0x180137027  test    byte ptr [rcx+1Ch], 8
0x18013702b  jz      short loc_18013705C
0x18013702d  cmp     [rcx+19h], dil
0x180137031  jb      short loc_18013705C
0x180137033  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180137039  mov     edx, 19h
0x18013703e  mov     rcx, cs:WPP_GLOBAL_Control
0x180137045  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x18013704c  mov     r9d, eax
0x18013704f  mov     dword ptr [rsp+240h+RequestQueueHandle], ebx
0x180137053  mov     rcx, [rcx+10h]
0x180137057  call    WPP_SF_Dd
0x18013705c  test    ebx, ebx
0x18013705e  jle     loc_180137238
0x180137064  movzx   ebx, bx
0x180137067  or      ebx, esi
0x180137069  jmp     loc_180137238
0x18013706e  lea     r15, [r14+98h]
0x180137075  mov     dword ptr [rsp+240h+var_210], edi
0x180137079  xor     r9d, r9d; Flags
0x18013707c  mov     [rsp+240h+RequestQueueHandle], r15; RequestQueueHandle
0x180137081  xor     r8d, r8d; SecurityAttributes
0x180137084  xor     edx, edx; Name
0x180137086  mov     ecx, edi; Version
0x180137088  call    cs:__imp_HttpCreateRequestQueue
0x18013708e  mov     ebx, eax
0x180137090  test    eax, eax
0x180137092  jz      short loc_1801370C3
0x180137094  mov     rcx, cs:WPP_GLOBAL_Control
0x18013709b  lea     rax, WPP_GLOBAL_Control
0x1801370a2  cmp     rcx, rax
0x1801370a5  jz      short loc_18013705C
0x1801370a7  test    byte ptr [rcx+1Ch], 8
0x1801370ab  jz      short loc_18013705C
0x1801370ad  cmp     [rcx+19h], dil
0x1801370b1  jb      short loc_18013705C
0x1801370b3  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801370b9  mov     edx, 1Ah
0x1801370be  jmp     loc_18013703E
0x1801370c3  mov     rax, [r15]
0x1801370c6  lea     r8, [rsp+240h+PropertyInformation]; PropertyInformation
0x1801370cb  mov     rcx, [r12]; UrlGroupId
0x1801370cf  mov     r9d, 10h; PropertyInformationLength
0x1801370d5  mov     [rsp+240h+PropertyInformation], 1
0x1801370de  mov     [rsp+240h+var_1F8], rax
0x1801370e3  lea     edx, [r9-9]; Property
0x1801370e7  call    cs:__imp_HttpSetUrlGroupProperty
0x1801370ed  mov     ebx, eax
0x1801370ef  test    eax, eax
0x1801370f1  jz      short loc_18013712E
0x1801370f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801370fa  lea     rax, WPP_GLOBAL_Control
0x180137101  cmp     rcx, rax
0x180137104  jz      loc_18013705C
0x18013710a  test    byte ptr [rcx+1Ch], 8
0x18013710e  jz      loc_18013705C
0x180137114  cmp     [rcx+19h], dil
0x180137118  jb      loc_18013705C
0x18013711e  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180137124  mov     edx, 1Bh
0x180137129  jmp     loc_18013703E
0x18013712e  mov     rcx, [r15]; fl
0x180137131  lea     rdx, ?IoCompletionCallback@WebSocketServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@_K1K1PEAU_TP_IO@@@Z; pfnio
0x180137138  xor     r9d, r9d; pcbe
0x18013713b  mov     r8, r14; pv
0x18013713e  call    cs:__imp_CreateThreadpoolIo
0x180137144  mov     [r14+0A0h], rax
0x18013714b  test    rax, rax
0x18013714e  jnz     short loc_1801371A6
0x180137150  mov     rcx, cs:WPP_GLOBAL_Control
0x180137157  lea     rax, WPP_GLOBAL_Control
0x18013715e  cmp     rcx, rax
0x180137161  jz      short loc_18013719C
0x180137163  test    byte ptr [rcx+1Ch], 8
0x180137167  jz      short loc_18013719C
0x180137169  cmp     [rcx+19h], dil
0x18013716d  jb      short loc_18013719C
0x18013716f  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180137175  mov     edx, 1Ch
0x18013717a  mov     rcx, cs:WPP_GLOBAL_Control
0x180137181  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180137188  mov     r9d, eax
0x18013718b  mov     dword ptr [rsp+240h+RequestQueueHandle], 80004005h
0x180137193  mov     rcx, [rcx+10h]
0x180137197  call    WPP_SF_Dd
0x18013719c  mov     ebx, 80004005h
0x1801371a1  jmp     loc_180137238
0x1801371a6  xor     r8d, r8d; pcbe
0x1801371a9  lea     rcx, ?DeferredWebSocketReceiveNotification@WebSocketServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801371b0  mov     rdx, r14; pv
0x1801371b3  call    cs:__imp_CreateThreadpoolWork
0x1801371b9  mov     [r14+0A8h], rax
0x1801371c0  test    rax, rax
0x1801371c3  jnz     short loc_1801371F1
0x1801371c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801371cc  lea     rax, WPP_GLOBAL_Control
0x1801371d3  cmp     rcx, rax
0x1801371d6  jz      short loc_18013719C
0x1801371d8  test    byte ptr [rcx+1Ch], 8
0x1801371dc  jz      short loc_18013719C
0x1801371de  cmp     [rcx+19h], dil
0x1801371e2  jb      short loc_18013719C
0x1801371e4  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801371ea  mov     edx, 1Dh
0x1801371ef  jmp     short loc_18013717A
0x1801371f1  mov     eax, cs:CallbackContext
0x1801371f7  xor     ebx, ebx
0x1801371f9  cmp     eax, 4
0x1801371fc  jbe     short loc_180137238
0x1801371fe  lea     rcx, [r14+58h]
0x180137202  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180137207  mov     [rsp+240h+var_208], rax
0x18013720c  lea     rdx, byte_180293B43
0x180137213  lea     rax, aHttpListenerSe; "HTTP Listener set up"
0x18013721a  mov     [rsp+240h+var_210], rax
0x18013721f  lea     rax, [rsp+240h+var_208]
0x180137224  mov     [rsp+240h+var_218], rax
0x180137229  lea     rax, [rsp+240h+var_210]
0x18013722e  mov     [rsp+240h+RequestQueueHandle], rax
0x180137233  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180137238  mov     eax, ebx
0x18013723a  mov     rcx, [rbp+140h+var_50]
0x180137241  xor     rcx, rsp; StackCookie
0x180137244  call    __security_check_cookie
0x180137249  add     rsp, 208h
0x180137250  pop     r15
0x180137252  pop     r14
0x180137254  pop     r13
0x180137256  pop     r12
0x180137258  pop     rdi
0x180137259  pop     rsi
0x18013725a  pop     rbx
0x18013725b  pop     rbp
0x18013725c  retn
```
