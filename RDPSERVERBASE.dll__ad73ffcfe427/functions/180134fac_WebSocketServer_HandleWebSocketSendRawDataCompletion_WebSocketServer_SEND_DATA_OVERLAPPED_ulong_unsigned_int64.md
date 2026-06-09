# WebSocketServer::HandleWebSocketSendRawDataCompletion(WebSocketServer::SEND_DATA_OVERLAPPED *,ulong,unsigned __int64)

- ea: `0x180134fac`
- end: `0x180135154`
- name: `?HandleWebSocketSendRawDataCompletion@WebSocketServer@@AEAAXPEAUSEND_DATA_OVERLAPPED@1@K_K@Z`
- size: `424`
- prototype: `void __fastcall(WebSocketServer *__hidden this, struct WebSocketServer::SEND_DATA_OVERLAPPED *Block, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180135290`

## callees

- `0x180076090`
- `0x180079724`
- `0x18007f6a4`
- `0x180134fac`
- `0x180137c30`
- `0x18013893c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180134fdb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180134fdb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013501a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801350e1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013511c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013501a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801350e1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013511c`
- `websocket!WebSocketCompleteAction` at `0x180135078`
- `websocket!WebSocketCompleteAction` at `0x180135078`
- `websocket!WebSocketAbortHandle` at `0x180135060`
- `websocket!WebSocketAbortHandle` at `0x180135060`

## string_xrefs

- `0x180135020`: `HandleWebSocketSendRawDataCompletion reports IO error`

## pseudocode

```c
void __fastcall WebSocketServer::HandleWebSocketSendRawDataCompletion(
        WebSocketServer *this,
        struct WebSocketServer::SEND_DATA_OVERLAPPED *Block,
        int a3,
        unsigned int a4)
{
  __int64 v8; // rdx
  struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *v9; // rsi
  __int64 v10; // r12
  const char *v11; // r14
  int ActivityIdPrefix; // eax
  int v13; // edi
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rdx
  int v17; // ebx
  unsigned int v18; // eax
  GUID ActivityId; // [rsp+30h] [rbp-48h] BYREF

  ActivityId = *(GUID *)((char *)Block + 36);
  EventActivityIdControl(2u, &ActivityId);
  v9 = (struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *)*((_QWORD *)Block + 20);
  v10 = *((_QWORD *)Block + 21);
  v11 = (const char *)*((_QWORD *)Block + 22);
  if ( a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v8);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
        ActivityIdPrefix,
        (__int64)"HandleWebSocketSendRawDataCompletion reports IO error",
        a3);
    }
    *((_DWORD *)Block + 46) = 0;
    a4 = 0;
    WebSocketAbortHandle(*((_QWORD *)v9 + 6));
  }
  else
  {
    *((_DWORD *)Block + 46) += a4;
  }
  WebSocketCompleteAction(*((_QWORD *)v9 + 6), v10, a4);
  *((_QWORD *)Block + 21) = 0;
  if ( *((_QWORD *)Block + 17) == 0xDEADCA11DEADCA11uLL )
  {
    v13 = WebSocketServer::WebSocketReceiveLoop(this, v9, (unsigned __int64)v11, 1);
    operator delete(Block);
    if ( v13 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v14);
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_b1a8cc76119c395613772ef098e23945_Traceguids, v15, v13);
    }
  }
  else
  {
    v17 = WebSocketServer::WebSocketSendLoop(this, v9, v11, 1);
    if ( v17 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v16);
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_b1a8cc76119c395613772ef098e23945_Traceguids, v18, v17);
    }
  }
}

```

## disassembly

```asm
0x180134fac  push    rbx
0x180134fae  push    rbp
0x180134faf  push    rsi
0x180134fb0  push    rdi
0x180134fb1  push    r12
0x180134fb3  push    r14
0x180134fb5  push    r15
0x180134fb7  sub     rsp, 40h
0x180134fbb  movups  xmm0, xmmword ptr [rdx+24h]
0x180134fbf  mov     rbx, rdx
0x180134fc2  mov     rbp, rcx
0x180134fc5  lea     rdx, [rsp+78h+ActivityId]; ActivityId
0x180134fca  mov     ecx, 2; ControlCode
0x180134fcf  movdqu  xmmword ptr [rsp+78h+ActivityId.Data1], xmm0
0x180134fd5  mov     rdi, r9
0x180134fd8  mov     r15d, r8d
0x180134fdb  call    cs:__imp_EventActivityIdControl
0x180134fe1  mov     rsi, [rbx+0A0h]
0x180134fe8  lea     rcx, WPP_GLOBAL_Control
0x180134fef  mov     r12, [rbx+0A8h]
0x180134ff6  mov     r14, [rbx+0B0h]
0x180134ffd  test    r15d, r15d
0x180135000  jz      short loc_180135068
0x180135002  mov     rax, cs:WPP_GLOBAL_Control
0x180135009  cmp     rax, rcx
0x18013500c  jz      short loc_180135050
0x18013500e  test    byte ptr [rax+1Ch], 1
0x180135012  jz      short loc_180135050
0x180135014  cmp     byte ptr [rax+19h], 2
0x180135018  jb      short loc_180135050
0x18013501a  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180135020  lea     rcx, aHandlewebsocke; "HandleWebSocketSendRawDataCompletion re"...
0x180135027  mov     [rsp+78h+var_50], r15d
0x18013502c  mov     [rsp+78h+var_58], rcx
0x180135031  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180135038  mov     rcx, cs:WPP_GLOBAL_Control
0x18013503f  mov     edx, 20h ; ' '
0x180135044  mov     r9d, eax
0x180135047  mov     rcx, [rcx+10h]
0x18013504b  call    WPP_SF_DsD
0x180135050  mov     dword ptr [rbx+0B8h], 0
0x18013505a  xor     edi, edi
0x18013505c  mov     rcx, [rsi+30h]
0x180135060  call    cs:__imp_WebSocketAbortHandle
0x180135066  jmp     short loc_18013506E
0x180135068  add     [rbx+0B8h], edi
0x18013506e  mov     rcx, [rsi+30h]
0x180135072  mov     r8d, edi
0x180135075  mov     rdx, r12
0x180135078  call    cs:__imp_WebSocketCompleteAction
0x18013507e  mov     rax, 0DEADCA11DEADCA11h
0x180135088  mov     qword ptr [rbx+0A8h], 0
0x180135093  mov     r9d, 1; int
0x180135099  mov     r8, r14; unsigned __int64
0x18013509c  mov     rdx, rsi; struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *
0x18013509f  mov     rcx, rbp; this
0x1801350a2  cmp     [rbx+88h], rax
0x1801350a9  jnz     short loc_1801350F2
0x1801350ab  call    ?WebSocketReceiveLoop@WebSocketServer@@AEAAJPEAUWEB_SOCKET_SHARED_HANDLE@1@_KH@Z; WebSocketServer::WebSocketReceiveLoop(WebSocketServer::WEB_SOCKET_SHARED_HANDLE *,unsigned __int64,int)
0x1801350b0  mov     rcx, rbx; Block
0x1801350b3  mov     edi, eax
0x1801350b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801350ba  test    edi, edi
0x1801350bc  jns     loc_180135145
0x1801350c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801350c9  lea     rax, WPP_GLOBAL_Control
0x1801350d0  cmp     rcx, rax
0x1801350d3  jz      short loc_180135145
0x1801350d5  test    byte ptr [rcx+1Ch], 1
0x1801350d9  jz      short loc_180135145
0x1801350db  cmp     byte ptr [rcx+19h], 2
0x1801350df  jb      short loc_180135145
0x1801350e1  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801350e7  mov     edx, 21h ; '!'
0x1801350ec  mov     dword ptr [rsp+78h+var_58], edi
0x1801350f0  jmp     short loc_18013512B
0x1801350f2  call    ?WebSocketSendLoop@WebSocketServer@@AEAAJPEAUWEB_SOCKET_SHARED_HANDLE@1@_KH@Z; WebSocketServer::WebSocketSendLoop(WebSocketServer::WEB_SOCKET_SHARED_HANDLE *,unsigned __int64,int)
0x1801350f7  mov     ebx, eax
0x1801350f9  test    eax, eax
0x1801350fb  jns     short loc_180135145
0x1801350fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180135104  lea     rax, WPP_GLOBAL_Control
0x18013510b  cmp     rcx, rax
0x18013510e  jz      short loc_180135145
0x180135110  test    byte ptr [rcx+1Ch], 1
0x180135114  jz      short loc_180135145
0x180135116  cmp     byte ptr [rcx+19h], 2
0x18013511a  jb      short loc_180135145
0x18013511c  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180135122  mov     edx, 22h ; '"'
0x180135127  mov     dword ptr [rsp+78h+var_58], ebx
0x18013512b  mov     rcx, cs:WPP_GLOBAL_Control
0x180135132  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180135139  mov     r9d, eax
0x18013513c  mov     rcx, [rcx+10h]
0x180135140  call    WPP_SF_Dd
0x180135145  add     rsp, 40h
0x180135149  pop     r15
0x18013514b  pop     r14
0x18013514d  pop     r12
0x18013514f  pop     rdi
0x180135150  pop     rsi
0x180135151  pop     rbp
0x180135152  pop     rbx
0x180135153  retn
```
