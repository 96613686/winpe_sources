# SharedSocket::GetDuplicatedSocketPrivate(unsigned __int64,ulong,_SOCKET_BROKER_RETRIEVE_SOCKET * *)

- ea: `0x180013f04`
- end: `0x1800140d0`
- name: `?GetDuplicatedSocketPrivate@SharedSocket@@IEAAK_KKPEAPEAU_SOCKET_BROKER_RETRIEVE_SOCKET@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, SOCKET s, DWORD, struct _SOCKET_BROKER_RETRIEVE_SOCKET **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013cb0`
- `0x1800277b4`

## callees

- `0x1800026ec`
- `0x180003ed0`
- `0x18000a0a0`
- `0x180013d60`
- `0x180013f04`
- `0x1800140d8`
- `0x180014130`
- `0x180014170`
- `0x1800142d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013f36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013f36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013fee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013fee`

## string_xrefs

- `0x180014053`: `RetrieveSocket: failed to create SbDuplicateSocketInfo`
- `0x180014062`: `GetDuplicatedSocketPrivate: CreateCleanupTimer failed with`

## pseudocode

```c
__int64 __fastcall SharedSocket::GetDuplicatedSocketPrivate(
        struct _RTL_CRITICAL_SECTION *this,
        SOCKET s,
        DWORD a3,
        struct _SOCKET_BROKER_RETRIEVE_SOCKET **a4)
{
  char v7; // bp
  __int64 v8; // rdx
  __int64 v9; // rcx
  char *v10; // rax
  char *v11; // rdi
  HANDLE *v12; // r15
  unsigned int SslContext; // eax
  unsigned int v14; // ebx
  unsigned int CleanupTimer; // eax
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  const wchar_t *v20; // r8
  __int64 v21; // r9
  struct _SOCKET_BROKER_SSL_CONTEXT *v22; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwProcessId; // [rsp+70h] [rbp+18h]

  dwProcessId = a3;
  v22 = 0;
  v7 = 0;
  EnterCriticalSection(this + 1);
  if ( !a4 )
  {
    v11 = 0;
    v14 = 87;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_9;
    v20 = L"GetDuplicatedSocketPrivate: DuplicateSockInfo is NULL";
LABEL_18:
    v21 = v14;
    goto LABEL_19;
  }
  *a4 = 0;
  v10 = (char *)MALLOC(0x38u);
  v11 = v10;
  if ( !v10 )
  {
    v14 = 8;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_9;
    v20 = L"RetrieveSocket: failed to create SbDuplicateSocketInfo";
    goto LABEL_18;
  }
  *(_DWORD *)v10 = 1;
  v12 = (HANDLE *)(v10 + 8);
  *(_OWORD *)(v10 + 8) = 0;
  *(_OWORD *)(v10 + 24) = 0;
  *(_OWORD *)(v10 + 40) = 0;
  *((_DWORD *)v10 + 2) = this[2].OwningThread;
  *((_DWORD *)v10 + 3) = this[2].RecursionCount;
  *((_DWORD *)v10 + 4) = this[2].LockCount;
  if ( s == this->SpinCount )
  {
    SslContext = SharedSocket::GetSslContext((SharedSocket *)this, &v22);
    v14 = SslContext;
    if ( SslContext )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_9;
      v21 = SslContext;
      v20 = L"GetDuplicatedSocketPrivate: DuplicateSocketHelper failed with";
      goto LABEL_19;
    }
    *((_QWORD *)v11 + 5) = v22;
  }
  CleanupTimer = SharedSocket::CreateCleanupTimer(this);
  v14 = CleanupTimer;
  if ( CleanupTimer )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_9;
    v21 = CleanupTimer;
    v20 = L"GetDuplicatedSocketPrivate: CreateCleanupTimer failed with";
LABEL_19:
    McTemplateU0zq_EventWriteTransfer(v9, v8, v20, v21);
    goto LABEL_9;
  }
  v16 = SharedSocket::DuplicateSocketHelper(s, dwProcessId, v12);
  v14 = v16;
  if ( v16 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v18, v17, L"GetDuplicatedSocketPrivate: DuplicateSocketHelper failed with", v16);
    v7 = 1;
  }
  else
  {
    *a4 = (struct _SOCKET_BROKER_RETRIEVE_SOCKET *)v11;
    v11 = 0;
    v22 = 0;
  }
LABEL_9:
  LeaveCriticalSection(this + 1);
  if ( v7 )
    SharedSocket::DeleteCleanupTimer(this);
  if ( v11 )
    VpnFree(v11);
  SharedSocket::FreeSocketBrokerSslContext((LPVOID **)&v22);
  return v14;
}

```

## disassembly

```asm
0x180013f04  mov     [rsp+arg_8], rbx
0x180013f09  mov     [rsp+dwProcessId], r8d
0x180013f0e  push    rbp
0x180013f0f  push    rsi
0x180013f10  push    rdi
0x180013f11  push    r12
0x180013f13  push    r13
0x180013f15  push    r14
0x180013f17  push    r15
0x180013f19  sub     rsp, 20h
0x180013f1d  mov     rsi, rcx
0x180013f20  mov     [rsp+58h+arg_0], 0
0x180013f29  add     rcx, 28h ; '('; lpCriticalSection
0x180013f2d  mov     r14, r9
0x180013f30  mov     r12, rdx
0x180013f33  xor     bpl, bpl
0x180013f36  call    cs:__imp_EnterCriticalSection
0x180013f3c  test    r14, r14
0x180013f3f  jz      loc_180014027
0x180013f45  mov     ecx, 38h ; '8'; dwBytes
0x180013f4a  mov     qword ptr [r14], 0
0x180013f51  call    ?MALLOC@@YAPEAX_K@Z; MALLOC(unsigned __int64)
0x180013f56  mov     rdi, rax
0x180013f59  test    rax, rax
0x180013f5c  jz      loc_180014073
0x180013f62  mov     dword ptr [rax], 1
0x180013f68  lea     r15, [rax+8]
0x180013f6c  xorps   xmm0, xmm0
0x180013f6f  movups  xmmword ptr [r15], xmm0
0x180013f73  movups  xmmword ptr [r15+10h], xmm0
0x180013f78  movups  xmmword ptr [r15+20h], xmm0
0x180013f7d  mov     eax, [rsi+60h]
0x180013f80  mov     [r15], eax
0x180013f83  mov     eax, [rsi+5Ch]
0x180013f86  mov     [rdi+0Ch], eax
0x180013f89  mov     eax, [rsi+58h]
0x180013f8c  mov     [rdi+10h], eax
0x180013f8f  cmp     r12, [rsi+20h]
0x180013f93  jnz     short loc_180013FB5
0x180013f95  lea     rdx, [rsp+58h+arg_0]; struct _SOCKET_BROKER_SSL_CONTEXT **
0x180013f9a  mov     rcx, rsi; this
0x180013f9d  call    ?GetSslContext@SharedSocket@@AEAAKPEAPEAU_SOCKET_BROKER_SSL_CONTEXT@@@Z; SharedSocket::GetSslContext(_SOCKET_BROKER_SSL_CONTEXT * *)
0x180013fa2  mov     ebx, eax
0x180013fa4  test    eax, eax
0x180013fa6  jnz     loc_18001403E
0x180013fac  mov     rax, [rsp+58h+arg_0]
0x180013fb1  mov     [rdi+28h], rax
0x180013fb5  mov     rcx, rsi; pv
0x180013fb8  call    ?CreateCleanupTimer@SharedSocket@@IEAAKK@Z; SharedSocket::CreateCleanupTimer(ulong)
0x180013fbd  mov     ebx, eax
0x180013fbf  test    eax, eax
0x180013fc1  jnz     loc_180014087
0x180013fc7  mov     edx, [rsp+58h+dwProcessId]; dwProcessId
0x180013fcb  mov     r8, r15; struct _SOCKET_BROKER_RETRIEVE_SOCKET_INFORMATION *
0x180013fce  mov     rcx, r12; s
0x180013fd1  call    ?DuplicateSocketHelper@SharedSocket@@SAK_KKPEAU_SOCKET_BROKER_RETRIEVE_SOCKET_INFORMATION@@@Z; SharedSocket::DuplicateSocketHelper(unsigned __int64,ulong,_SOCKET_BROKER_RETRIEVE_SOCKET_INFORMATION *)
0x180013fd6  mov     ebx, eax
0x180013fd8  test    eax, eax
0x180013fda  jnz     loc_180014096
0x180013fe0  mov     [r14], rdi
0x180013fe3  xor     edi, edi
0x180013fe5  mov     [rsp+58h+arg_0], rdi
0x180013fea  lea     rcx, [rsi+28h]; lpCriticalSection
0x180013fee  call    cs:__imp_LeaveCriticalSection
0x180013ff4  test    bpl, bpl
0x180013ff7  jnz     loc_1800140B6
0x180013ffd  test    rdi, rdi
0x180014000  jnz     loc_1800140C3
0x180014006  lea     rcx, [rsp+58h+arg_0]; struct _SOCKET_BROKER_SSL_CONTEXT **
0x18001400b  call    ?FreeSocketBrokerSslContext@SharedSocket@@CAXPEAPEAU_SOCKET_BROKER_SSL_CONTEXT@@@Z; SharedSocket::FreeSocketBrokerSslContext(_SOCKET_BROKER_SSL_CONTEXT * *)
0x180014010  mov     eax, ebx
0x180014012  mov     rbx, [rsp+58h+arg_8]
0x180014017  add     rsp, 20h
0x18001401b  pop     r15
0x18001401d  pop     r14
0x18001401f  pop     r13
0x180014021  pop     r12
0x180014023  pop     rdi
0x180014024  pop     rsi
0x180014025  pop     rbp
0x180014026  retn
0x180014027  xor     edi, edi
0x180014029  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180014030  lea     ebx, [rdi+57h]
0x180014033  jz      short loc_180013FEA
0x180014035  lea     r8, aGetduplicateds; "GetDuplicatedSocketPrivate: DuplicateSo"...
0x18001403c  jmp     short loc_18001405A
0x18001403e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180014045  jz      short loc_180013FEA
0x180014047  mov     r9d, eax
0x18001404a  lea     r8, aGetduplicateds_1; "GetDuplicatedSocketPrivate: DuplicateSo"...
0x180014051  jmp     short loc_180014069
0x180014053  lea     r8, aRetrievesocket_0; "RetrieveSocket: failed to create SbDupl"...
0x18001405a  mov     r9d, ebx
0x18001405d  jmp     short loc_180014069
0x18001405f  mov     r9d, eax
0x180014062  lea     r8, aGetduplicateds_2; "GetDuplicatedSocketPrivate: CreateClean"...
0x180014069  call    McTemplateU0zq_EventWriteTransfer
0x18001406e  jmp     loc_180013FEA
0x180014073  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001407a  mov     ebx, 8
0x18001407f  jz      loc_180013FEA
0x180014085  jmp     short loc_180014053
0x180014087  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001408e  jz      loc_180013FEA
0x180014094  jmp     short loc_18001405F
0x180014096  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001409d  jz      short loc_1800140AE
0x18001409f  mov     r9d, eax
0x1800140a2  lea     r8, aGetduplicateds_1; "GetDuplicatedSocketPrivate: DuplicateSo"...
0x1800140a9  call    McTemplateU0zq_EventWriteTransfer
0x1800140ae  mov     bpl, 1
0x1800140b1  jmp     loc_180013FEA
0x1800140b6  mov     rcx, rsi; this
0x1800140b9  call    ?DeleteCleanupTimer@SharedSocket@@QEAAXXZ; SharedSocket::DeleteCleanupTimer(void)
0x1800140be  jmp     loc_180013FFD
0x1800140c3  mov     rcx, rdi; lpMem
0x1800140c6  call    VpnFree
0x1800140cb  jmp     loc_180014006
```
