# TcpListener::HandleInComingConnection(_TP_CALLBACK_INSTANCE *,ulong)

- ea: `0x180026fc8`
- end: `0x18002713d`
- name: `?HandleInComingConnection@TcpListener@@AEAAKPEAU_TP_CALLBACK_INSTANCE@@K@Z`
- size: `373`
- prototype: `__int64 __fastcall(TcpListener *this, PTP_CALLBACK_INSTANCE pci, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800272d0`

## callees

- `0x180001ebc`
- `0x18000a0a0`
- `0x1800267d8`
- `0x180026fc8`
- `0x1800272e8`
- `0x180027c50`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026fee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026fee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800270de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800270de`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x1800270e7`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x1800270e7`
- `WS2_32!__imp_setsockopt` at `0x180027063`
- `WS2_32!__imp_setsockopt` at `0x180027063`
- `WS2_32!__imp_WSAGetLastError` at `0x18002706d`
- `WS2_32!__imp_WSAGetLastError` at `0x18002706d`

## string_xrefs

- `0x18002702e`: `HandleInComingConnection: IO Result`
- `0x1800270ba`: `HandleInComingConnection: m_AcceptSock is NULL`
- `0x180027081`: `HandleInComingConnection: setsockopt SO_UPDATE_ACCEPT_CONTEXT failed with`

## pseudocode

```c
__int64 __fastcall TcpListener::HandleInComingConnection(TcpListener *this, PTP_CALLBACK_INSTANCE pci, unsigned int a3)
{
  unsigned int v4; // edi
  SocketBrokerContext *v7; // rbp
  unsigned int v8; // r14d
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // r15d
  bool v12; // zf
  __int64 v13; // r9
  const wchar_t *v14; // r8
  unsigned int Error; // eax
  __int64 v16; // rax

  v4 = 0;
  v7 = 0;
  v8 = 4;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v11 = *((_DWORD *)this + 218);
  v12 = *((_QWORD *)this + 4) == -1;
  *((_DWORD *)this + 219) = 0;
  if ( !v12 && !v11 )
  {
    if ( a3 )
    {
      v4 = a3;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_16;
      v13 = a3;
      v14 = L"HandleInComingConnection: IO Result";
LABEL_15:
      McTemplateU0zq_EventWriteTransfer(v10, v9, v14, v13);
      goto LABEL_16;
    }
    v10 = *((_QWORD *)this + 40);
    if ( !v10 || !*((_QWORD *)this + 10) )
    {
      v4 = 87;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_16;
      v13 = 87;
      v14 = L"HandleInComingConnection: m_AcceptSock is NULL";
      goto LABEL_15;
    }
    if ( setsockopt(*(_QWORD *)(v10 + 16), 0xFFFF, 28683, (const char *)this + 32, 8) )
    {
      Error = WSAGetLastError();
      v4 = Error;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_16;
      v13 = Error;
      v14 = L"HandleInComingConnection: setsockopt SO_UPDATE_ACCEPT_CONTEXT failed with";
      goto LABEL_15;
    }
    *(_BYTE *)(*((_QWORD *)this + 40) + 28LL) = 1;
    v4 = TcpListener::PostAccept(this);
    if ( !v4 )
      v8 = 2;
  }
LABEL_16:
  v16 = *((_QWORD *)this + 10);
  if ( v16 )
  {
    v7 = (SocketBrokerContext *)*((_QWORD *)this + 10);
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 24));
  }
  *((_DWORD *)this + 29) = v8;
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  DisassociateCurrentThreadFromCallback(pci);
  if ( v7 )
  {
    if ( !v11 )
    {
      SocketBrokerContext::NotifyApp(v7, this, v4, v8);
      SharedSocket::CreateRetryTriggerMonitor((__int64)this, v8);
    }
    SocketBrokerContext::ReleaseRef(v7);
  }
  (*(void (__fastcall **)(TcpListener *))(*(_QWORD *)this + 8LL))(this);
  return v4;
}

```

## disassembly

```asm
0x180026fc8  push    rbx
0x180026fca  push    rbp
0x180026fcb  push    rsi
0x180026fcc  push    rdi
0x180026fcd  push    r12
0x180026fcf  push    r13
0x180026fd1  push    r14
0x180026fd3  push    r15
0x180026fd5  sub     rsp, 38h
0x180026fd9  mov     rbx, rcx
0x180026fdc  xor     edi, edi
0x180026fde  add     rcx, 28h ; '('; lpCriticalSection
0x180026fe2  mov     esi, r8d
0x180026fe5  mov     r13, rdx
0x180026fe8  xor     ebp, ebp
0x180026fea  lea     r14d, [rdi+4]
0x180026fee  call    cs:__imp_EnterCriticalSection
0x180026ff4  mov     r15d, [rbx+368h]
0x180026ffb  lea     r9, [rbx+20h]; optval
0x180026fff  cmp     qword ptr [r9], 0FFFFFFFFFFFFFFFFh
0x180027003  mov     [rbx+36Ch], edi
0x180027009  jz      loc_1800270C6
0x18002700f  test    r15d, r15d
0x180027012  jnz     loc_1800270C6
0x180027018  test    esi, esi
0x18002701a  jz      short loc_18002703A
0x18002701c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027023  mov     edi, esi
0x180027025  jz      loc_1800270C6
0x18002702b  mov     r9d, esi
0x18002702e  lea     r8, aHandleincoming; "HandleInComingConnection: IO Result"
0x180027035  jmp     loc_1800270C1
0x18002703a  mov     rcx, [rbx+140h]
0x180027041  test    rcx, rcx
0x180027044  jz      short loc_1800270A9
0x180027046  cmp     [rbx+50h], rdi
0x18002704a  jz      short loc_1800270A9
0x18002704c  mov     rcx, [rcx+10h]; s
0x180027050  mov     edx, 0FFFFh; level
0x180027055  mov     r8d, 700Bh; optname
0x18002705b  mov     [rsp+78h+optlen], 8; optlen
0x180027063  call    cs:__imp_setsockopt
0x180027069  test    eax, eax
0x18002706b  jz      short loc_18002708A
0x18002706d  call    cs:__imp_WSAGetLastError
0x180027073  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002707a  mov     edi, eax
0x18002707c  jz      short loc_1800270C6
0x18002707e  mov     r9d, eax
0x180027081  lea     r8, aHandleincoming_0; "HandleInComingConnection: setsockopt SO"...
0x180027088  jmp     short loc_1800270C1
0x18002708a  mov     rax, [rbx+140h]
0x180027091  mov     rcx, rbx; this
0x180027094  mov     byte ptr [rax+1Ch], 1
0x180027098  call    ?PostAccept@TcpListener@@AEAAKXZ; TcpListener::PostAccept(void)
0x18002709d  mov     edi, eax
0x18002709f  test    eax, eax
0x1800270a1  jnz     short loc_1800270C6
0x1800270a3  lea     r14d, [rax+2]
0x1800270a7  jmp     short loc_1800270C6
0x1800270a9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800270b0  mov     edi, 57h ; 'W'
0x1800270b5  jz      short loc_1800270C6
0x1800270b7  mov     r9d, edi
0x1800270ba  lea     r8, aHandleincoming_1; "HandleInComingConnection: m_AcceptSock "...
0x1800270c1  call    McTemplateU0zq_EventWriteTransfer
0x1800270c6  mov     rax, [rbx+50h]
0x1800270ca  test    rax, rax
0x1800270cd  jz      short loc_1800270D6
0x1800270cf  mov     rbp, rax
0x1800270d2  lock inc dword ptr [rax+18h]
0x1800270d6  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800270da  mov     [rbx+74h], r14d
0x1800270de  call    cs:__imp_LeaveCriticalSection
0x1800270e4  mov     rcx, r13; pci
0x1800270e7  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x1800270ed  test    rbp, rbp
0x1800270f0  jz      short loc_18002711B
0x1800270f2  test    r15d, r15d
0x1800270f5  jnz     short loc_180027113
0x1800270f7  mov     r9d, r14d
0x1800270fa  mov     r8d, edi
0x1800270fd  mov     rdx, rbx
0x180027100  mov     rcx, rbp
0x180027103  call    ?NotifyApp@SocketBrokerContext@@QEAAXPEAVSharedSocket@@KW4_SOCKET_BROKER_TRIGGER_REASON@@@Z; SocketBrokerContext::NotifyApp(SharedSocket *,ulong,_SOCKET_BROKER_TRIGGER_REASON)
0x180027108  mov     edx, r14d
0x18002710b  mov     rcx, rbx
0x18002710e  call    ?CreateRetryTriggerMonitor@SharedSocket@@IEAAKW4_SOCKET_BROKER_TRIGGER_REASON@@@Z; SharedSocket::CreateRetryTriggerMonitor(_SOCKET_BROKER_TRIGGER_REASON)
0x180027113  mov     rcx, rbp; this
0x180027116  call    ?ReleaseRef@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::ReleaseRef(void)
0x18002711b  mov     rax, [rbx]
0x18002711e  mov     rcx, rbx
0x180027121  mov     rax, [rax+8]
0x180027125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002712a  mov     eax, edi
0x18002712c  add     rsp, 38h
0x180027130  pop     r15
0x180027132  pop     r14
0x180027134  pop     r13
0x180027136  pop     r12
0x180027138  pop     rdi
0x180027139  pop     rsi
0x18002713a  pop     rbp
0x18002713b  pop     rbx
0x18002713c  retn
```
