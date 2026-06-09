# SharedSocket::Initialize(SocketBrokerContext *,ushort const *,bool,int,int,int,ulong,unsigned __int64,void *,ulong,_SOCKET_BROKER_APP_CONTEXT *,_SOCKET_BROKER_SSL_CONTEXT *,_DNS_REGISTRATION_DATA *)

- ea: `0x180012490`
- end: `0x1800128a0`
- name: `?Initialize@SharedSocket@@UEAAKPEAVSocketBrokerContext@@PEBG_NHHHK_KPEAXKPEAU_SOCKET_BROKER_APP_CONTEXT@@PEAU_SOCKET_BROKER_SSL_CONTEXT@@PEAU_DNS_REGISTRATION_DATA@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(SharedSocket *this, struct SocketBrokerContext *, const unsigned __int16 *, char, int, int, int, char vInBuffer, void *, void *, unsigned int, struct _SOCKET_BROKER_APP_CONTEXT *, struct _SOCKET_BROKER_SSL_CONTEXT *, struct _DNS_REGISTRATION_DATA *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012260`
- `0x180027150`

## callees

- `0x18000a0a0`
- `0x180012490`
- `0x1800128a8`
- `0x180012900`
- `0x18001d8e0`
- `0x18001e368`
- `0x18001f950`
- `0x1800232dc`
- `0x180027a94`
- `0x180027ba8`
- `0x180027fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012819`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012527`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012527`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012570`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012570`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800125f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800125f9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001269e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001272a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001269e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001272a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001262c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001262c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012895`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012895`
- `WS2_32!WSAIoctl` at `0x18001268f`
- `WS2_32!WSAIoctl` at `0x18001268f`
- `WS2_32!__imp_WSAGetLastError` at `0x180012711`
- `WS2_32!__imp_WSAGetLastError` at `0x180012711`
- `WS2_32!__imp_WSAStartup` at `0x18001253e`
- `WS2_32!__imp_WSAStartup` at `0x18001253e`

## string_xrefs

- `0x1800126fd`: `SharedSocket: CreateKeepAliveTimer failed`
- `0x18001277f`: `SharedSocket: NcbUtilsAllocCopyString failed`
- `0x1800127b1`: `SharedSocket: NcbUtilsCopySBUserContext failed with`
- `0x18001280d`: `SharedSocket::CopyDnsRegistrationData failed with`
- `0x180012742`: `SharedSocket: Impersonate of client failed`
- `0x180012889`: `SharedSocket: KamGetSocketBrokerKeepAliveTime failed`

## pseudocode

```c
__int64 __fastcall SharedSocket::Initialize(
        SharedSocket *this,
        struct SocketBrokerContext *a2,
        const unsigned __int16 *a3,
        char a4,
        int a5,
        int a6,
        int a7,
        char vInBuffer,
        void *a9,
        void *a10,
        unsigned int a11,
        struct _SOCKET_BROKER_APP_CONTEXT *a12,
        struct _SOCKET_BROKER_SSL_CONTEXT *a13,
        struct _DNS_REGISTRATION_DATA *a14)
{
  struct _SOCKET_BROKER_APP_CONTEXT *v15; // r14
  struct _SOCKET_BROKER_SSL_CONTEXT *v17; // r15
  struct _DNS_REGISTRATION_DATA *v19; // r12
  unsigned int LastError; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // ebx
  HANDLE CurrentProcess; // rax
  int *v27; // rsi
  const wchar_t *v28; // r8
  __int64 v29; // r9
  unsigned int Error; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  HANDLE TargetHandle; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbBytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hSourceHandle; // [rsp+60h] [rbp-A0h]
  HANDLE hSourceProcessHandle; // [rsp+68h] [rbp-98h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-90h]
  WSAData WSAData; // [rsp+80h] [rbp-80h] BYREF

  v15 = a12;
  v17 = a13;
  v19 = a14;
  hSourceHandle = a9;
  hSourceProcessHandle = a10;
  memset_0(&WSAData, 0, sizeof(WSAData));
  TargetHandle = 0;
  cbBytesReturned = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  *((_QWORD *)this + 10) = a2;
  _InterlockedIncrement((volatile signed __int32 *)a2 + 6);
  if ( WSAStartup(2u, &WSAData) )
  {
    LastError = GetLastError();
    v24 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_3;
    v28 = L"SharedSocket: WSAStartup failed";
    goto LABEL_20;
  }
  LastError = NcbUtilsAllocCopyString(a3, (char *)this + 104);
  v24 = LastError;
  if ( LastError )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_3;
    v28 = L"SharedSocket: NcbUtilsAllocCopyString failed";
    goto LABEL_20;
  }
  *((_DWORD *)this + 22) = a5;
  *((_DWORD *)this + 23) = a7;
  *((_BYTE *)this + 184) = 1;
  *((_DWORD *)this + 24) = a6;
  *((_BYTE *)this + 112) = a4;
  if ( !v15 || (LastError = NcbUtilsCopySBAppContext(v15, (char *)this + 128), (v24 = LastError) == 0) )
  {
    if ( v17 )
    {
      LastError = SharedSocket::ImportSslContext((struct _RTL_CRITICAL_SECTION *)this, v17);
      v24 = LastError;
      if ( LastError )
      {
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          v28 = L"SharedSocket: ImportSslContext failed with";
          goto LABEL_20;
        }
        goto LABEL_3;
      }
    }
    if ( v19 )
    {
      LastError = SharedSocket::CopyDnsRegistrationData(this, v19);
      v24 = LastError;
      if ( LastError )
      {
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          v28 = L"SharedSocket::CopyDnsRegistrationData failed with";
          goto LABEL_20;
        }
        goto LABEL_3;
      }
    }
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(hSourceProcessHandle, hSourceHandle, CurrentProcess, &TargetHandle, 0, 1, 2u) )
    {
      LastError = GetLastError();
      v24 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v28 = L"SharedSocket: DuplicateHandle failed with";
        goto LABEL_20;
      }
      goto LABEL_3;
    }
    LastError = SocketBrokerContext::Impersonate(*((SocketBrokerContext **)this + 10));
    v24 = LastError;
    if ( LastError )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_3;
      v28 = L"SharedSocket: Impersonate of client failed";
    }
    else
    {
      if ( WSAIoctl((SOCKET)TargetHandle, 0x9800012E, &vInBuffer, 4u, (char *)this + 32, 8u, &cbBytesReturned, 0, 0) == -1 )
      {
        Error = WSAGetLastError();
        v24 = Error;
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(v32, v31, L"SharedSocket: SIO_SOCKET_TRANSFER_END failed", Error);
        SetThreadToken(0, 0);
        goto LABEL_3;
      }
      SetThreadToken(0, 0);
      TargetHandle = 0;
      if ( a6 != 1 || a4 )
      {
        if ( a11 - 1 <= 0xFFFFFFFD )
        {
          v24 = 87;
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
            goto LABEL_5;
          v29 = 87;
          v28 = L"SharedSocket: Keepalive is not supported for listen socket or datagram";
          goto LABEL_21;
        }
        v27 = (int *)((char *)this + 192);
        *((_DWORD *)this + 48) = 0;
      }
      else
      {
        v33 = a11;
        v27 = (int *)((char *)this + 192);
        *((_DWORD *)this + 47) = a11;
        LastError = KamGetSocketBrokerKeepAliveTime(v33, (char *)this + 192);
        v24 = LastError;
        if ( LastError )
        {
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          {
            v28 = L"SharedSocket: KamGetSocketBrokerKeepAliveTime failed";
            goto LABEL_20;
          }
          goto LABEL_3;
        }
      }
      if ( !*v27 )
        goto LABEL_3;
      LastError = SharedSocket::CreateKeepAliveTimer((struct _RTL_CRITICAL_SECTION *)this, *v27);
      v24 = LastError;
      if ( !LastError || (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_3;
      v28 = L"SharedSocket: CreateKeepAliveTimer failed";
    }
LABEL_20:
    v29 = LastError;
LABEL_21:
    McTemplateU0zq_EventWriteTransfer(v23, v22, v28, v29);
    goto LABEL_3;
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v28 = L"SharedSocket: NcbUtilsCopySBUserContext failed with";
    goto LABEL_20;
  }
LABEL_3:
  if ( TargetHandle )
    CloseHandle(TargetHandle);
LABEL_5:
  LeaveCriticalSection(lpCriticalSection);
  return v24;
}

```

## disassembly

```asm
0x180012490  mov     [rsp-8+arg_8], rbx
0x180012495  push    rbp
0x180012496  push    rsi
0x180012497  push    rdi
0x180012498  push    r12
0x18001249a  push    r13
0x18001249c  push    r14
0x18001249e  push    r15
0x1800124a0  lea     rbp, [rsp-130h]
0x1800124a8  sub     rsp, 230h
0x1800124af  mov     rax, cs:__security_cookie
0x1800124b6  xor     rax, rsp
0x1800124b9  mov     [rbp+160h+var_40], rax
0x1800124c0  mov     rax, [rbp+160h+arg_40]
0x1800124c7  mov     rsi, r8
0x1800124ca  mov     r14, [rbp+160h+arg_58]
0x1800124d1  mov     rbx, rdx
0x1800124d4  mov     r15, [rbp+160h+arg_60]
0x1800124db  mov     rdi, rcx
0x1800124de  mov     r12, [rbp+160h+arg_68]
0x1800124e5  lea     rcx, [rbp+160h+WSAData]; void *
0x1800124e9  mov     [rsp+260h+hSourceHandle], rax
0x1800124ee  xor     edx, edx; Val
0x1800124f0  mov     rax, [rbp+160h+arg_48]
0x1800124f7  mov     r8d, 198h; Size
0x1800124fd  mov     [rsp+260h+hSourceProcessHandle], rax
0x180012502  mov     r13b, r9b
0x180012505  call    memset_0
0x18001250a  lea     rax, [rdi+28h]
0x18001250e  mov     [rsp+260h+TargetHandle], 0
0x180012517  mov     rcx, rax; lpCriticalSection
0x18001251a  mov     [rsp+260h+cbBytesReturned], 0
0x180012522  mov     [rsp+260h+lpCriticalSection], rax
0x180012527  call    cs:__imp_EnterCriticalSection
0x18001252d  mov     [rdi+50h], rbx
0x180012531  lock inc dword ptr [rbx+18h]
0x180012535  mov     ecx, 2; wVersionRequested
0x18001253a  lea     rdx, [rbp+160h+WSAData]; lpWSAData
0x18001253e  call    cs:__imp_WSAStartup
0x180012544  test    eax, eax
0x180012546  jz      short loc_1800125A2
0x180012548  call    cs:__imp_GetLastError
0x18001254e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012555  mov     ebx, eax
0x180012557  jnz     loc_180012769
0x18001255d  mov     rcx, [rsp+260h+TargetHandle]; hObject
0x180012562  test    rcx, rcx
0x180012565  jnz     loc_180012895
0x18001256b  mov     rcx, [rsp+260h+lpCriticalSection]; lpCriticalSection
0x180012570  call    cs:__imp_LeaveCriticalSection
0x180012576  mov     eax, ebx
0x180012578  mov     rcx, [rbp+160h+var_40]
0x18001257f  xor     rcx, rsp; StackCookie
0x180012582  call    __security_check_cookie
0x180012587  mov     rbx, [rsp+260h+arg_8]
0x18001258f  add     rsp, 230h
0x180012596  pop     r15
0x180012598  pop     r14
0x18001259a  pop     r13
0x18001259c  pop     r12
0x18001259e  pop     rdi
0x18001259f  pop     rsi
0x1800125a0  pop     rbp
0x1800125a1  retn
0x1800125a2  lea     rdx, [rdi+68h]
0x1800125a6  mov     rcx, rsi
0x1800125a9  call    NcbUtilsAllocCopyString
0x1800125ae  mov     ebx, eax
0x1800125b0  test    eax, eax
0x1800125b2  jnz     loc_180012772
0x1800125b8  mov     eax, [rbp+160h+arg_20]
0x1800125be  mov     esi, [rbp+160h+arg_28]
0x1800125c4  mov     [rdi+58h], eax
0x1800125c7  mov     eax, [rbp+160h+arg_30]
0x1800125cd  mov     [rdi+5Ch], eax
0x1800125d0  mov     byte ptr [rdi+0B8h], 1
0x1800125d7  mov     [rdi+60h], esi
0x1800125da  mov     [rdi+70h], r13b
0x1800125de  test    r14, r14
0x1800125e1  jnz     loc_18001278B
0x1800125e7  test    r15, r15
0x1800125ea  jnz     loc_1800127BD
0x1800125f0  test    r12, r12
0x1800125f3  jnz     loc_1800127EB
0x1800125f9  call    cs:__imp_GetCurrentProcess
0x1800125ff  mov     rdx, [rsp+260h+hSourceHandle]; hSourceHandle
0x180012604  lea     r9, [rsp+260h+TargetHandle]; lpTargetHandle
0x180012609  mov     rcx, [rsp+260h+hSourceProcessHandle]; hSourceProcessHandle
0x18001260e  mov     r14d, 1
0x180012614  mov     [rsp+260h+dwOptions], 2; dwOptions
0x18001261c  mov     r8, rax; hTargetProcessHandle
0x18001261f  mov     [rsp+260h+bInheritHandle], r14d; bInheritHandle
0x180012624  mov     [rsp+260h+dwDesiredAccess], 0; dwDesiredAccess
0x18001262c  call    cs:__imp_DuplicateHandle
0x180012632  test    eax, eax
0x180012634  jz      loc_180012819
0x18001263a  mov     rcx, [rdi+50h]; this
0x18001263e  call    ?Impersonate@SocketBrokerContext@@QEAAKXZ; SocketBrokerContext::Impersonate(void)
0x180012643  mov     ebx, eax
0x180012645  test    eax, eax
0x180012647  jnz     loc_180012735
0x18001264d  mov     [rsp+260h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180012656  lea     rcx, [rsp+260h+cbBytesReturned]
0x18001265b  mov     [rsp+260h+lpOverlapped], 0; lpOverlapped
0x180012664  lea     rax, [rdi+20h]
0x180012668  mov     qword ptr [rsp+260h+dwOptions], rcx; lpcbBytesReturned
0x18001266d  lea     r9d, [r14+3]; cbInBuffer
0x180012671  mov     rcx, [rsp+260h+TargetHandle]; s
0x180012676  lea     r8, [rbp+160h+vInBuffer]; lpvInBuffer
0x18001267d  mov     [rsp+260h+bInheritHandle], 8; cbOutBuffer
0x180012685  mov     edx, 9800012Eh; dwIoControlCode
0x18001268a  mov     qword ptr [rsp+260h+dwDesiredAccess], rax; lpvOutBuffer
0x18001268f  call    cs:__imp_WSAIoctl
0x180012695  cmp     eax, 0FFFFFFFFh
0x180012698  jz      short loc_180012711
0x18001269a  xor     edx, edx; Token
0x18001269c  xor     ecx, ecx; Thread
0x18001269e  call    cs:__imp_SetThreadToken
0x1800126a4  mov     [rsp+260h+TargetHandle], 0
0x1800126ad  cmp     esi, r14d
0x1800126b0  jz      loc_18001284E
0x1800126b6  mov     eax, [rbp+160h+arg_50]
0x1800126bc  dec     eax
0x1800126be  cmp     eax, 0FFFFFFFDh
0x1800126c1  jbe     loc_18001274B
0x1800126c7  lea     rsi, [rdi+0C0h]
0x1800126ce  mov     dword ptr [rsi], 0
0x1800126d4  mov     edx, [rsi]; unsigned int
0x1800126d6  test    edx, edx
0x1800126d8  jz      loc_18001255D
0x1800126de  mov     rcx, rdi; this
0x1800126e1  call    ?CreateKeepAliveTimer@SharedSocket@@AEAAKK@Z; SharedSocket::CreateKeepAliveTimer(ulong)
0x1800126e6  mov     ebx, eax
0x1800126e8  test    eax, eax
0x1800126ea  jz      loc_18001255D
0x1800126f0  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r14b
0x1800126f7  jz      loc_18001255D
0x1800126fd  lea     r8, aSharedsocketCr_1; "SharedSocket: CreateKeepAliveTimer fail"...
0x180012704  mov     r9d, eax
0x180012707  call    McTemplateU0zq_EventWriteTransfer
0x18001270c  jmp     loc_18001255D
0x180012711  call    cs:__imp_WSAGetLastError
0x180012717  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r14b
0x18001271e  mov     ebx, eax
0x180012720  jnz     loc_18001283A
0x180012726  xor     edx, edx; Token
0x180012728  xor     ecx, ecx; Thread
0x18001272a  call    cs:__imp_SetThreadToken
0x180012730  jmp     loc_18001255D
0x180012735  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r14b
0x18001273c  jz      loc_18001255D
0x180012742  lea     r8, aSharedsocketIm; "SharedSocket: Impersonate of client fai"...
0x180012749  jmp     short loc_180012704
0x18001274b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r14b
0x180012752  mov     ebx, 57h ; 'W'
0x180012757  jz      loc_18001256B
0x18001275d  mov     r9d, ebx
0x180012760  lea     r8, aSharedsocketKe; "SharedSocket: Keepalive is not supporte"...
0x180012767  jmp     short loc_180012707
0x180012769  lea     r8, aSharedsocketWs; "SharedSocket: WSAStartup failed"
0x180012770  jmp     short loc_180012704
0x180012772  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012779  jz      loc_18001255D
0x18001277f  lea     r8, aSharedsocketNc; "SharedSocket: NcbUtilsAllocCopyString f"...
0x180012786  jmp     loc_180012704
0x18001278b  lea     rdx, [rdi+80h]
0x180012792  mov     rcx, r14
0x180012795  call    NcbUtilsCopySBAppContext
0x18001279a  mov     ebx, eax
0x18001279c  test    eax, eax
0x18001279e  jz      loc_1800125E7
0x1800127a4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800127ab  jz      loc_18001255D
0x1800127b1  lea     r8, aSharedsocketNc_0; "SharedSocket: NcbUtilsCopySBUserContext"...
0x1800127b8  jmp     loc_180012704
0x1800127bd  mov     rdx, r15; struct _SOCKET_BROKER_SSL_CONTEXT *
0x1800127c0  mov     rcx, rdi; this
0x1800127c3  call    ?ImportSslContext@SharedSocket@@AEAAKPEAU_SOCKET_BROKER_SSL_CONTEXT@@@Z; SharedSocket::ImportSslContext(_SOCKET_BROKER_SSL_CONTEXT *)
0x1800127c8  mov     ebx, eax
0x1800127ca  test    eax, eax
0x1800127cc  jz      loc_1800125F0
0x1800127d2  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800127d9  jz      loc_18001255D
0x1800127df  lea     r8, aSharedsocketIm_2; "SharedSocket: ImportSslContext failed w"...
0x1800127e6  jmp     loc_180012704
0x1800127eb  mov     rdx, r12; struct _DNS_REGISTRATION_DATA *
0x1800127ee  mov     rcx, rdi; this
0x1800127f1  call    ?CopyDnsRegistrationData@SharedSocket@@AEAAKPEAU_DNS_REGISTRATION_DATA@@@Z; SharedSocket::CopyDnsRegistrationData(_DNS_REGISTRATION_DATA *)
0x1800127f6  mov     ebx, eax
0x1800127f8  test    eax, eax
0x1800127fa  jz      loc_1800125F9
0x180012800  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180012807  jz      loc_18001255D
0x18001280d  lea     r8, aSharedsocketCo; "SharedSocket::CopyDnsRegistrationData f"...
0x180012814  jmp     loc_180012704
0x180012819  call    cs:__imp_GetLastError
0x18001281f  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r14b
0x180012826  mov     ebx, eax
0x180012828  jz      loc_18001255D
0x18001282e  lea     r8, aSharedsocketDu; "SharedSocket: DuplicateHandle failed wi"...
0x180012835  jmp     loc_180012704
0x18001283a  mov     r9d, eax
0x18001283d  lea     r8, aSharedsocketSi; "SharedSocket: SIO_SOCKET_TRANSFER_END f"...
0x180012844  call    McTemplateU0zq_EventWriteTransfer
0x180012849  jmp     loc_180012726
0x18001284e  test    r13b, r13b
0x180012851  jnz     loc_1800126B6
0x180012857  mov     ecx, [rbp+160h+arg_50]
0x18001285d  lea     rsi, [rdi+0C0h]
0x180012864  mov     rdx, rsi
0x180012867  mov     [rdi+0BCh], ecx
0x18001286d  call    KamGetSocketBrokerKeepAliveTime
0x180012872  mov     ebx, eax
0x180012874  test    eax, eax
0x180012876  jz      loc_1800126D4
0x18001287c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r14b
0x180012883  jz      loc_18001255D
0x180012889  lea     r8, aSharedsocketKa; "SharedSocket: KamGetSocketBrokerKeepAli"...
0x180012890  jmp     loc_180012704
0x180012895  call    cs:__imp_CloseHandle
0x18001289b  jmp     loc_18001256B
```
