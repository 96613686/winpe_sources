# SocketBrokerContext::TransferOwnership(ushort const *,int,int,int,ulong,bool,unsigned __int64,void *,ulong,_SOCKET_BROKER_APP_CONTEXT *,_SOCKET_BROKER_SSL_CONTEXT *,_DNS_REGISTRATION_DATA *)

- ea: `0x180012c60`
- end: `0x180013020`
- name: `?TransferOwnership@SocketBrokerContext@@QEAAKPEBGHHHK_N_KPEAXKPEAU_SOCKET_BROKER_APP_CONTEXT@@PEAU_SOCKET_BROKER_SSL_CONTEXT@@PEAU_DNS_REGISTRATION_DATA@@@Z`
- size: `960`
- prototype: `__int64 __fastcall(SocketBrokerContext *this, const unsigned __int16 *, int, int, int, unsigned int, bool, unsigned __int64, TcpListener *ProcessHandle, unsigned int, struct _SOCKET_BROKER_APP_CONTEXT *, struct _SOCKET_BROKER_SSL_CONTEXT *, struct _DNS_REGISTRATION_DATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019470`

## callees

- `0x18000a0a0`
- `0x180012c60`
- `0x180013028`
- `0x1800130dc`
- `0x1800131c8`
- `0x18001dd2c`
- `0x180026b30`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012c95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012cda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012c95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012cda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d70`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180012f2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180012f2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013015`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013015`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180012f7d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180012f7d`

## string_xrefs

- `0x180012da1`: `TransferOwnership: Socket Id size is greater than MAX_PATH`
- `0x180012eed`: `TransferOwnership: Object already exists for the socket Id`
- `0x180012f4e`: `Failed to get Process token`
- `0x180012fa3`: `Failed to get duplicate impersonation Process token `
- `0x180012ede`: `TransferOwnership: Failed to create socket activity monitor`

## pseudocode

```c
__int64 __fastcall SocketBrokerContext::TransferOwnership(
        SocketBrokerContext *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        int a5,
        unsigned int a6,
        bool a7,
        unsigned __int64 a8,
        TcpListener *ProcessHandle,
        unsigned int a10,
        struct _SOCKET_BROKER_APP_CONTEXT *a11,
        struct _SOCKET_BROKER_SSL_CONTEXT *a12,
        struct _DNS_REGISTRATION_DATA *a13)
{
  __int64 v16; // rdx
  __int64 v17; // rcx
  TcpListener *v18; // r12
  unsigned __int64 v19; // rax
  SocketBrokerContext *i; // r9
  TcpListener *v21; // r14
  const unsigned __int16 *v22; // rax
  int v23; // ecx
  int v24; // edx
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned int v27; // ebx
  const wchar_t *v29; // r8
  struct _SOCKET_BROKER_APP_CONTEXT *v30; // rsi
  bool v31; // di
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  DWORD LastError; // eax
  __int64 v36; // r9
  DWORD v37; // eax
  void *TokenHandle; // [rsp+C0h] [rbp+8h] BYREF
  int v39; // [rsp+D0h] [rbp+18h]

  v39 = a3;
  TokenHandle = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v18 = ProcessHandle;
  if ( !ProcessHandle || !a2 )
  {
    v27 = 87;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_18;
    v29 = L"TransferOwnership: Invalid handles or socket Id";
    goto LABEL_45;
  }
  v19 = -1;
  do
    ++v19;
  while ( a2[v19] );
  if ( v19 > 0x100 )
  {
    v27 = 87;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_18;
    v29 = L"TransferOwnership: Socket Id size is greater than MAX_PATH";
    goto LABEL_45;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  for ( i = (SocketBrokerContext *)*((_QWORD *)this + 13); ; i = *(SocketBrokerContext **)i )
  {
    v21 = 0;
    if ( i == (SocketBrokerContext *)((char *)this + 104) )
      break;
    v21 = (SocketBrokerContext *)((char *)i - 8);
    v22 = a2;
    do
    {
      v23 = *(const unsigned __int16 *)((char *)v22 + *((_QWORD *)i + 12) - (_QWORD)a2);
      v24 = *v22 - v23;
      if ( v24 )
        break;
      ++v22;
    }
    while ( v23 );
    if ( !v24 )
    {
      (**(void (__fastcall ***)(__int64))v21)((__int64)i - 8);
      break;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( v21 )
  {
    v27 = 183;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v26, v25, L"TransferOwnership: Object already exists for the socket Id", 183);
LABEL_17:
    (*(void (__fastcall **)(TcpListener *))(*(_QWORD *)v21 + 8LL))(v21);
    goto LABEL_18;
  }
  v30 = a11;
  if ( SocketBrokerContext::IsLimitExceeded(this, a11) )
  {
    v27 = 1292;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_18;
    v29 = L"TransferOwnership: Limits exceeded for this application to transfer socket";
    goto LABEL_45;
  }
  if ( !*((_QWORD *)this + 7) )
  {
    if ( !OpenProcessToken(v18, 0xAu, &TokenHandle) )
    {
      LastError = GetLastError();
      v27 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_18;
      v36 = LastError;
      v29 = L"Failed to get Process token";
      goto LABEL_46;
    }
    if ( !DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)this + 7) )
    {
      v37 = GetLastError();
      v27 = v37;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_18;
      v36 = v37;
      v29 = L"Failed to get duplicate impersonation Process token ";
      goto LABEL_46;
    }
  }
  v31 = a7;
  if ( a7 )
  {
    ProcessHandle = (TcpListener *)operator new(0x370u);
    v21 = TcpListener::TcpListener(ProcessHandle);
  }
  else
  {
    v21 = (TcpListener *)operator new(0x120u);
    ProcessHandle = v21;
    SharedSocket::SharedSocket(v21);
    *(_QWORD *)v21 = &SocketIoMonitor::`vftable';
    *((_QWORD *)v21 + 33) = 0;
    *((_QWORD *)v21 + 34) = 0;
    *((_BYTE *)v21 + 280) = 0;
  }
  if ( v21 )
  {
    v32 = (*(__int64 (__fastcall **)(TcpListener *, SocketBrokerContext *, const unsigned __int16 *, bool, int, int, int, unsigned int, unsigned __int64, TcpListener *, unsigned int, struct _SOCKET_BROKER_APP_CONTEXT *, struct _SOCKET_BROKER_SSL_CONTEXT *, struct _DNS_REGISTRATION_DATA *))(*(_QWORD *)v21 + 16LL))(
            v21,
            this,
            a2,
            v31,
            v39,
            a4,
            a5,
            a6,
            a8,
            v18,
            a10,
            v30,
            a12,
            a13);
    v27 = v32;
    if ( v32 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v34, v33, L"TransferOwnership: socket initialize failed", v32);
    }
    else
    {
      SocketBrokerContext::AddSocketToList(this, v21);
    }
    goto LABEL_17;
  }
  v27 = 8;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v29 = L"TransferOwnership: Failed to create socket activity monitor";
LABEL_45:
    v36 = v27;
LABEL_46:
    McTemplateU0zq_EventWriteTransfer(v17, v16, v29, v36);
  }
LABEL_18:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v27;
}

```

## disassembly

```asm
0x180012c60  mov     [rsp+arg_8], rbx
0x180012c65  mov     [rsp+arg_10], r8d
0x180012c6a  push    rbp
0x180012c6b  push    rsi
0x180012c6c  push    rdi
0x180012c6d  push    r12
0x180012c6f  push    r13
0x180012c71  push    r14
0x180012c73  push    r15
0x180012c75  sub     rsp, 80h
0x180012c7c  mov     r13d, r9d
0x180012c7f  mov     rbx, rdx
0x180012c82  mov     r15, rcx
0x180012c85  mov     [rsp+0B8h+TokenHandle], 0
0x180012c91  add     rcx, 40h ; '@'; lpCriticalSection
0x180012c95  call    cs:__imp_EnterCriticalSection
0x180012c9b  mov     r12, [rsp+0B8h+ProcessHandle]
0x180012ca3  test    r12, r12
0x180012ca6  jz      loc_180012FEF
0x180012cac  test    rbx, rbx
0x180012caf  jz      loc_180012FEF
0x180012cb5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180012cbc  nop     dword ptr [rax+00h]
0x180012cc0  inc     rax
0x180012cc3  cmp     word ptr [rbx+rax*2], 0
0x180012cc8  jnz     short loc_180012CC0
0x180012cca  cmp     rax, 100h
0x180012cd0  ja      loc_180012D93
0x180012cd6  lea     rcx, [r15+40h]; lpCriticalSection
0x180012cda  call    cs:__imp_EnterCriticalSection
0x180012ce0  lea     r10, [r15+68h]
0x180012ce4  mov     r9, [r10]
0x180012ce7  xor     r14d, r14d
0x180012cea  cmp     r9, r10
0x180012ced  jz      short loc_180012D2B
0x180012cef  lea     r14, [r9-8]
0x180012cf3  mov     rax, rbx
0x180012cf6  mov     r8, [r14+68h]
0x180012cfa  sub     r8, rbx
0x180012cfd  nop     dword ptr [rax]
0x180012d00  movzx   edx, word ptr [rax]
0x180012d03  movzx   ecx, word ptr [rax+r8]
0x180012d08  sub     edx, ecx
0x180012d0a  jnz     short loc_180012D14
0x180012d0c  add     rax, 2
0x180012d10  test    ecx, ecx
0x180012d12  jnz     short loc_180012D00
0x180012d14  test    edx, edx
0x180012d16  jz      short loc_180012D1D
0x180012d18  mov     r9, [r9]
0x180012d1b  jmp     short loc_180012CE7
0x180012d1d  mov     rax, [r14]
0x180012d20  mov     rcx, r14
0x180012d23  mov     rax, [rax]
0x180012d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d2b  lea     rcx, [r15+40h]; lpCriticalSection
0x180012d2f  call    cs:__imp_LeaveCriticalSection
0x180012d35  test    r14, r14
0x180012d38  jz      short loc_180012DAD
0x180012d3a  mov     ebx, 0B7h
0x180012d3f  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012d46  jnz     loc_180012EEA
0x180012d4c  mov     rax, [r14]
0x180012d4f  mov     rcx, r14
0x180012d52  mov     rax, [rax+8]
0x180012d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d5b  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x180012d63  test    rcx, rcx
0x180012d66  jnz     loc_180013015
0x180012d6c  lea     rcx, [r15+40h]; lpCriticalSection
0x180012d70  call    cs:__imp_LeaveCriticalSection
0x180012d76  mov     eax, ebx
0x180012d78  mov     rbx, [rsp+0B8h+arg_8]
0x180012d80  add     rsp, 80h
0x180012d87  pop     r15
0x180012d89  pop     r14
0x180012d8b  pop     r13
0x180012d8d  pop     r12
0x180012d8f  pop     rdi
0x180012d90  pop     rsi
0x180012d91  pop     rbp
0x180012d92  retn
0x180012d93  mov     ebx, 57h ; 'W'
0x180012d98  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012d9f  jz      short loc_180012D5B
0x180012da1  lea     r8, aTransferowners_3; "TransferOwnership: Socket Id size is gr"...
0x180012da8  jmp     loc_180013008
0x180012dad  mov     rsi, [rsp+0B8h+arg_50]
0x180012db5  mov     rdx, rsi; struct _SOCKET_BROKER_APP_CONTEXT *
0x180012db8  mov     rcx, r15; this
0x180012dbb  call    ?IsLimitExceeded@SocketBrokerContext@@AEAA_NPEAU_SOCKET_BROKER_APP_CONTEXT@@@Z; SocketBrokerContext::IsLimitExceeded(_SOCKET_BROKER_APP_CONTEXT *)
0x180012dc0  test    al, al
0x180012dc2  jnz     loc_180012EFE
0x180012dc8  lea     rdi, [r15+38h]
0x180012dcc  cmp     qword ptr [rdi], 0
0x180012dd0  jz      loc_180012F1C
0x180012dd6  movzx   edi, [rsp+0B8h+arg_30]
0x180012dde  test    dil, dil
0x180012de1  jnz     loc_180012FAC
0x180012de7  mov     ecx, 120h; Size
0x180012dec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012df1  mov     r14, rax
0x180012df4  mov     [rsp+0B8h+ProcessHandle], rax
0x180012dfc  mov     rcx, rax; this
0x180012dff  call    ??0SharedSocket@@QEAA@XZ; SharedSocket::SharedSocket(void)
0x180012e04  lea     rax, ??_7SocketIoMonitor@@6B@; const SocketIoMonitor::`vftable'
0x180012e0b  mov     [r14], rax
0x180012e0e  mov     qword ptr [r14+108h], 0
0x180012e19  mov     qword ptr [r14+110h], 0
0x180012e24  mov     [r14+118h], dil
0x180012e2b  test    r14, r14
0x180012e2e  jz      loc_180012ECC
0x180012e34  mov     rax, [r14]
0x180012e37  mov     r10, [rax+10h]
0x180012e3b  mov     rax, [rsp+0B8h+arg_60]
0x180012e43  mov     [rsp+0B8h+var_50], rax
0x180012e48  mov     rax, [rsp+0B8h+arg_58]
0x180012e50  mov     [rsp+0B8h+var_58], rax
0x180012e55  mov     [rsp+0B8h+var_60], rsi
0x180012e5a  mov     ecx, [rsp+0B8h+arg_48]
0x180012e61  mov     [rsp+0B8h+var_68], ecx
0x180012e65  mov     [rsp+0B8h+var_70], r12
0x180012e6a  mov     rcx, [rsp+0B8h+arg_38]
0x180012e72  mov     [rsp+0B8h+var_78], rcx
0x180012e77  mov     ecx, [rsp+0B8h+arg_28]
0x180012e7e  mov     [rsp+0B8h+var_80], ecx
0x180012e82  mov     ecx, [rsp+0B8h+arg_20]
0x180012e89  mov     [rsp+0B8h+var_88], ecx
0x180012e8d  mov     dword ptr [rsp+0B8h+phNewToken], r13d
0x180012e92  mov     eax, [rsp+0B8h+arg_10]
0x180012e99  mov     [rsp+0B8h+TokenType], eax
0x180012e9d  movzx   r9d, dil
0x180012ea1  mov     r8, rbx
0x180012ea4  mov     rdx, r15
0x180012ea7  mov     rcx, r14
0x180012eaa  mov     rax, r10
0x180012ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eb2  mov     ebx, eax
0x180012eb4  test    eax, eax
0x180012eb6  jnz     loc_180012FCE
0x180012ebc  mov     rdx, r14; struct SharedSocket *
0x180012ebf  mov     rcx, r15; this
0x180012ec2  call    ?AddSocketToList@SocketBrokerContext@@AEAAXPEAVSharedSocket@@@Z; SocketBrokerContext::AddSocketToList(SharedSocket *)
0x180012ec7  jmp     loc_180012D4C
0x180012ecc  mov     ebx, 8
0x180012ed1  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012ed8  jz      loc_180012D5B
0x180012ede  lea     r8, aTransferowners_0; "TransferOwnership: Failed to create soc"...
0x180012ee5  jmp     loc_180013008
0x180012eea  mov     r9d, ebx
0x180012eed  lea     r8, aTransferowners_2; "TransferOwnership: Object already exist"...
0x180012ef4  call    McTemplateU0zq_EventWriteTransfer
0x180012ef9  jmp     loc_180012D4C
0x180012efe  mov     ebx, 50Ch
0x180012f03  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012f0a  jz      loc_180012D5B
0x180012f10  lea     r8, aTransferowners_4; "TransferOwnership: Limits exceeded for "...
0x180012f17  jmp     loc_180013008
0x180012f1c  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x180012f24  mov     edx, 0Ah; DesiredAccess
0x180012f29  mov     rcx, r12; ProcessHandle
0x180012f2c  call    cs:__imp_OpenProcessToken
0x180012f32  test    eax, eax
0x180012f34  jnz     short loc_180012F5A
0x180012f36  call    cs:__imp_GetLastError
0x180012f3c  mov     ebx, eax
0x180012f3e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012f45  jz      loc_180012D5B
0x180012f4b  mov     r9d, eax
0x180012f4e  lea     r8, aFailedToGetPro_3; "Failed to get Process token"
0x180012f55  jmp     loc_18001300B
0x180012f5a  mov     [rsp+0B8h+phNewToken], rdi; phNewToken
0x180012f5f  mov     [rsp+0B8h+TokenType], 2; TokenType
0x180012f67  mov     r9d, 2; ImpersonationLevel
0x180012f6d  xor     r8d, r8d; lpTokenAttributes
0x180012f70  mov     edx, 0Ch; dwDesiredAccess
0x180012f75  mov     rcx, [rsp+0B8h+TokenHandle]; hExistingToken
0x180012f7d  call    cs:__imp_DuplicateTokenEx
0x180012f83  test    eax, eax
0x180012f85  jnz     loc_180012DD6
0x180012f8b  call    cs:__imp_GetLastError
0x180012f91  mov     ebx, eax
0x180012f93  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012f9a  jz      loc_180012D5B
0x180012fa0  mov     r9d, eax
0x180012fa3  lea     r8, aFailedToGetDup_0; "Failed to get duplicate impersonation P"...
0x180012faa  jmp     short loc_18001300B
0x180012fac  mov     ecx, 370h; Size
0x180012fb1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012fb6  mov     [rsp+0B8h+ProcessHandle], rax
0x180012fbe  mov     rcx, rax; this
0x180012fc1  call    ??0TcpListener@@QEAA@XZ; TcpListener::TcpListener(void)
0x180012fc6  mov     r14, rax
0x180012fc9  jmp     loc_180012E2B
0x180012fce  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012fd5  jz      loc_180012D4C
0x180012fdb  mov     r9d, eax
0x180012fde  lea     r8, aTransferowners; "TransferOwnership: socket initialize fa"...
0x180012fe5  call    McTemplateU0zq_EventWriteTransfer
0x180012fea  jmp     loc_180012D4C
0x180012fef  mov     ebx, 57h ; 'W'
0x180012ff4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012ffb  jz      loc_180012D5B
0x180013001  lea     r8, aTransferowners_1; "TransferOwnership: Invalid handles or s"...
0x180013008  mov     r9d, ebx
0x18001300b  call    McTemplateU0zq_EventWriteTransfer
0x180013010  jmp     loc_180012D5B
0x180013015  call    cs:__imp_CloseHandle
0x18001301b  jmp     loc_180012D6C
```
