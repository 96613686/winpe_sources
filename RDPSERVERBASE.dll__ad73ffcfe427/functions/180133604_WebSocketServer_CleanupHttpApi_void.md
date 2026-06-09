# WebSocketServer::CleanupHttpApi(void)

- ea: `0x180133604`
- end: `0x1801336fd`
- name: `?CleanupHttpApi@WebSocketServer@@AEAAXXZ`
- size: `249`
- prototype: `void __fastcall(WebSocketServer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180137640`

## callees

- `0x180133604`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180133687`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180133687`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18013366a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18013366a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18013365d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18013365d`
- `WS2_32!__imp_WSACleanup` at `0x1801336ed`
- `WS2_32!__imp_WSACleanup` at `0x1801336ed`
- `HTTPAPI!HttpTerminate` at `0x1801336dd`
- `HTTPAPI!HttpTerminate` at `0x1801336dd`
- `HTTPAPI!HttpCloseServerSession` at `0x1801336c1`
- `HTTPAPI!HttpCloseServerSession` at `0x1801336c1`
- `HTTPAPI!HttpCloseRequestQueue` at `0x1801336a4`
- `HTTPAPI!HttpCloseRequestQueue` at `0x1801336a4`
- `HTTPAPI!HttpShutdownRequestQueue` at `0x180133649`
- `HTTPAPI!HttpShutdownRequestQueue` at `0x180133649`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18013362c`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18013362c`
- `HTTPAPI!HttpRemoveUrlFromUrlGroup` at `0x18013361f`
- `HTTPAPI!HttpRemoveUrlFromUrlGroup` at `0x18013361f`

## pseudocode

```c
void __fastcall WebSocketServer::CleanupHttpApi(WebSocketServer *this)
{
  HTTP_URL_GROUP_ID v2; // rcx
  void *v3; // rcx
  struct _TP_IO *v4; // rcx
  struct _TP_WORK *v5; // rcx
  void *v6; // rcx
  HTTP_SERVER_SESSION_ID v7; // rcx

  v2 = *((_QWORD *)this + 18);
  if ( v2 )
  {
    HttpRemoveUrlFromUrlGroup(v2, 0, 1u);
    HttpCloseUrlGroup(*((_QWORD *)this + 18));
    *((_QWORD *)this + 18) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 19);
  if ( v3 )
    HttpShutdownRequestQueue(v3);
  v4 = (struct _TP_IO *)*((_QWORD *)this + 20);
  if ( v4 )
  {
    WaitForThreadpoolIoCallbacks(v4, 0);
    CloseThreadpoolIo(*((PTP_IO *)this + 20));
    *((_QWORD *)this + 20) = 0;
  }
  v5 = (struct _TP_WORK *)*((_QWORD *)this + 21);
  if ( v5 )
  {
    CloseThreadpoolWork(v5);
    *((_QWORD *)this + 21) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 19);
  if ( v6 )
  {
    HttpCloseRequestQueue(v6);
    *((_QWORD *)this + 19) = 0;
  }
  v7 = *((_QWORD *)this + 17);
  if ( v7 )
  {
    HttpCloseServerSession(v7);
    *((_QWORD *)this + 17) = 0;
  }
  if ( *((_BYTE *)this + 77) )
  {
    HttpTerminate(3u, 0);
    *((_BYTE *)this + 77) = 0;
  }
  if ( *((_BYTE *)this + 76) )
  {
    WSACleanup();
    *((_BYTE *)this + 76) = 0;
  }
}

```

## disassembly

```asm
0x180133604  push    rbx
0x180133606  sub     rsp, 20h
0x18013360a  mov     rbx, rcx
0x18013360d  mov     rcx, [rcx+90h]; UrlGroupId
0x180133614  test    rcx, rcx
0x180133617  jz      short loc_18013363D
0x180133619  xor     edx, edx; pFullyQualifiedUrl
0x18013361b  lea     r8d, [rdx+1]; Flags
0x18013361f  call    cs:__imp_HttpRemoveUrlFromUrlGroup
0x180133625  mov     rcx, [rbx+90h]; UrlGroupId
0x18013362c  call    cs:__imp_HttpCloseUrlGroup
0x180133632  mov     qword ptr [rbx+90h], 0
0x18013363d  mov     rcx, [rbx+98h]; RequestQueueHandle
0x180133644  test    rcx, rcx
0x180133647  jz      short loc_18013364F
0x180133649  call    cs:__imp_HttpShutdownRequestQueue
0x18013364f  mov     rcx, [rbx+0A0h]; pio
0x180133656  test    rcx, rcx
0x180133659  jz      short loc_18013367B
0x18013365b  xor     edx, edx; fCancelPendingCallbacks
0x18013365d  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180133663  mov     rcx, [rbx+0A0h]; pio
0x18013366a  call    cs:__imp_CloseThreadpoolIo
0x180133670  mov     qword ptr [rbx+0A0h], 0
0x18013367b  mov     rcx, [rbx+0A8h]; pwk
0x180133682  test    rcx, rcx
0x180133685  jz      short loc_180133698
0x180133687  call    cs:__imp_CloseThreadpoolWork
0x18013368d  mov     qword ptr [rbx+0A8h], 0
0x180133698  mov     rcx, [rbx+98h]; RequestQueueHandle
0x18013369f  test    rcx, rcx
0x1801336a2  jz      short loc_1801336B5
0x1801336a4  call    cs:__imp_HttpCloseRequestQueue
0x1801336aa  mov     qword ptr [rbx+98h], 0
0x1801336b5  mov     rcx, [rbx+88h]; ServerSessionId
0x1801336bc  test    rcx, rcx
0x1801336bf  jz      short loc_1801336D2
0x1801336c1  call    cs:__imp_HttpCloseServerSession
0x1801336c7  mov     qword ptr [rbx+88h], 0
0x1801336d2  cmp     byte ptr [rbx+4Dh], 0
0x1801336d6  jz      short loc_1801336E7
0x1801336d8  xor     edx, edx; pReserved
0x1801336da  lea     ecx, [rdx+3]; Flags
0x1801336dd  call    cs:__imp_HttpTerminate
0x1801336e3  mov     byte ptr [rbx+4Dh], 0
0x1801336e7  cmp     byte ptr [rbx+4Ch], 0
0x1801336eb  jz      short loc_1801336F7
0x1801336ed  call    cs:__imp_WSACleanup
0x1801336f3  mov     byte ptr [rbx+4Ch], 0
0x1801336f7  add     rsp, 20h
0x1801336fb  pop     rbx
0x1801336fc  retn
```
