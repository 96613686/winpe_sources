# GameInputServer::WorkerThreadProc(void)

- ea: `0x180042b60`
- end: `0x180042f4f`
- name: `?WorkerThreadProc@GameInputServer@@AEAAJXZ`
- size: `1007`
- prototype: `__int64 __fastcall(GameInputServer *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180042f80`

## callees

- `0x18000d68c`
- `0x1800182dc`
- `0x180025b80`
- `0x180027f1c`
- `0x180029a74`
- `0x18002aca0`
- `0x18002df84`
- `0x18003b79c`
- `0x18003ee94`
- `0x180042758`
- `0x180042b60`
- `0x180043060`
- `0x18004c881`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180042c1f`
- `ntdll!RtlAllocateHeap` at `0x180042c1f`
- `ntdll!NtWaitForSingleObject` at `0x180042eb7`
- `ntdll!NtWaitForSingleObject` at `0x180042eb7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042d8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042d8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042b89`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042b89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f1e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180042d36`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180042d36`

## pseudocode

```c
__int64 __fastcall GameInputServer::WorkerThreadProc(GameInputServer *this)
{
  char v1; // r13
  void *v3; // rsi
  HANDLE EventW; // rax
  _QWORD *v5; // r14
  _QWORD *v6; // r15
  int ServerPort; // ebx
  int v8; // r12d
  char *Heap; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  char *v13; // rdi
  void *v14; // rax
  __int64 v15; // rcx
  char v16; // al
  void *v17; // rcx
  int v18; // r14d
  __int64 *i; // rdi
  __int64 *j; // rbx
  FeedbackManager *v21; // rcx
  int FocusPolicy; // eax
  void *v23; // rcx
  NTSTATUS v24; // ebx
  int v26; // [rsp+60h] [rbp+8h]
  __int64 v27; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  v3 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v26 = 0;
  if ( EventW )
    v3 = EventW;
  if ( !*((_BYTE *)this + 132) )
  {
    v5 = (_QWORD *)((char *)this + 16);
    v6 = (_QWORD *)((char *)this + 16);
    do
    {
      ServerPort = 0;
      if ( byte_180069913 || (v6 = v5, !byte_180069916) )
      {
        if ( !*((_BYTE *)this + 256) )
        {
          v8 = 0;
          while ( 1 )
          {
            *v6 = 0;
            if ( !memcmp_0(&GameInputServer::c_gameInputServiceGuid, qword_1800554E8, 0x10u) )
              break;
            Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xA0u);
            v13 = Heap;
            if ( !Heap )
            {
              ServerPort = -2147024882;
              goto LABEL_21;
            }
            *(_QWORD *)Heap = &SipcObjectBase<ISIPCServer>::`vftable';
            *((_QWORD *)Heap + 1) = 2;
            *((_QWORD *)Heap + 2) = &SipcEndpointOwner::`vftable';
            *((_DWORD *)Heap + 10) = 1;
            *((_WORD *)Heap + 22) = 2;
            *(GUID *)(Heap + 24) = GameInputServer::c_gameInputServiceGuid;
            *((_QWORD *)Heap + 6) = 0;
            *(_QWORD *)Heap = &SipcServer::`vftable'{for `SipcObjectBase<ISIPCServer>'};
            *((_QWORD *)Heap + 2) = &SipcServer::`vftable'{for `SipcEndpointOwner'};
            *((_QWORD *)Heap + 12) = Heap + 88;
            *((_QWORD *)Heap + 11) = Heap + 88;
            *((_QWORD *)Heap + 15) = Heap + 112;
            *((_QWORD *)Heap + 14) = Heap + 112;
            *((_QWORD *)Heap + 18) = GameInputServer::OnSipcServerConnection;
            *((_QWORD *)Heap + 7) = 0;
            *((_QWORD *)Heap + 8) = 0;
            *((_QWORD *)Heap + 9) = 0;
            *((_QWORD *)Heap + 10) = 0;
            *((_DWORD *)Heap + 26) = 0;
            *((_DWORD *)Heap + 32) = 0;
            *((_QWORD *)Heap + 17) = 0;
            *((_QWORD *)Heap + 19) = this;
            ServerPort = AlpcPort::CreateServerPort(v11, v10, v12, (AlpcPort **)Heap + 7);
            if ( ServerPort >= 0 )
            {
              ServerPort = AggregateWaitHandle::Initialize((AggregateWaitHandle *)(v13 + 64));
              if ( ServerPort < 0 )
              {
                v1 = 0;
              }
              else
              {
                v14 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v13 + 7) + 40LL))(*((_QWORD *)v13 + 7));
                v1 = 0;
                ServerPort = AggregateWaitHandle::AddHandle((AggregateWaitHandle *)(v13 + 64), v14);
                if ( ServerPort >= 0 )
                {
                  *v6 = v13;
                  ServerPort = 0;
                  goto LABEL_21;
                }
              }
            }
            SipcObjectBase<ISIPCClient>::Release(v13);
            if ( ServerPort == -805306315 )
            {
              Sleep(0x1F4u);
              if ( (unsigned int)++v8 < 5 )
                continue;
            }
            goto LABEL_21;
          }
          ServerPort = -2147024809;
        }
      }
LABEL_21:
      if ( (unsigned int)Feature_Servicing_GameInputSvcRundown__private_IsEnabledDeviceUsageNoInline() )
      {
        *((_DWORD *)this + 72) = ServerPort;
        v16 = GameInputServer::WorkerThreadProc_::_17_::_lambda_1_::operator()(v15, (unsigned int)ServerPort);
        v17 = (void *)*((_QWORD *)this + 35);
        *((_BYTE *)this + 132) = v16;
        SetEvent(v17);
      }
      else if ( ServerPort < 0 )
      {
        GameInputFailFast((unsigned int)ServerPort, 2076);
        JUMPOUT(0x180042F4ELL);
      }
      while ( !*((_BYTE *)this + 132) )
      {
        if ( ServerPort < 0 )
          goto LABEL_60;
        while ( *v5 )
        {
          if ( *((_BYTE *)this + 132) )
            goto LABEL_35;
          if ( ServerPort < 0 || ServerPort == 1 )
            break;
          ServerPort = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 32LL))(*v5);
        }
        if ( !*((_BYTE *)this + 132) && ServerPort >= 0 )
          ServerPort = GameInputServer::ProcessQueuedWorkItems(this);
LABEL_35:
        v27 = 0;
        if ( *((_BYTE *)this + 132) )
          break;
        if ( ServerPort >= 0 )
        {
          v18 = *((_DWORD *)this + 32);
          for ( i = (__int64 *)*((_QWORD *)this + 7); i != (__int64 *)((char *)this + 56); i = (__int64 *)*i )
          {
            for ( j = (__int64 *)i[4]; j != i + 4; j = (__int64 *)*j )
            {
              if ( *((_DWORD *)i + 22) == v18 )
              {
                v21 = *(FeedbackManager **)(j[2] + 104);
                if ( v21 )
                  FeedbackManager::OnClientSignal(v21);
              }
              FocusPolicy = GameInputServer::BufferListEntry::GetFocusPolicy(j);
              if ( *((_DWORD *)j + 18) != FocusPolicy )
              {
                *((_DWORD *)j + 18) = FocusPolicy;
                v1 = 1;
              }
            }
          }
          v5 = (_QWORD *)((char *)this + 16);
          if ( v1 )
            GameInputServer::UpdateSystemButtonState(this);
          v1 = 0;
          v27 = 0x7FFFFFFFFFFFFFFFLL;
          ServerPort = 0;
        }
        if ( *((_BYTE *)this + 132) )
          break;
        if ( ServerPort < 0 )
          goto LABEL_60;
        do
        {
          if ( *v5 )
            v23 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 40LL))(*v5);
          else
            v23 = v3;
          v24 = NtWaitForSingleObject(v23, 1u, (PLARGE_INTEGER)((unsigned __int64)&v27 & -(__int64)(v27 != 0)));
        }
        while ( v24 == 257 );
        ServerPort = v24 | 0x10000000;
      }
      if ( ServerPort >= 0 )
        goto LABEL_61;
LABEL_60:
      ++v26;
LABEL_61:
      v6 = v5;
      if ( *v5 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
        *v5 = 0;
      }
    }
    while ( !*((_BYTE *)this + 132) );
  }
  if ( v3 )
    CloseHandle(v3);
  return 0;
}

```

## disassembly

```asm
0x180042b60  mov     [rsp+arg_18], rbx
0x180042b65  push    rbp
0x180042b66  push    rsi
0x180042b67  push    rdi
0x180042b68  push    r12
0x180042b6a  push    r13
0x180042b6c  push    r14
0x180042b6e  push    r15
0x180042b70  sub     rsp, 20h
0x180042b74  xor     r13d, r13d
0x180042b77  mov     rbp, rcx
0x180042b7a  xor     r9d, r9d; lpName
0x180042b7d  xor     r8d, r8d; bInitialState
0x180042b80  xor     ecx, ecx; lpEventAttributes
0x180042b82  mov     esi, r13d
0x180042b85  lea     edx, [r13+1]; bManualReset
0x180042b89  call    cs:__imp_CreateEventW
0x180042b90  nop     dword ptr [rax+rax+00h]
0x180042b95  test    rax, rax
0x180042b98  mov     [rsp+58h+arg_0], r13d
0x180042b9d  mov     [rsp+58h+arg_8], r13d
0x180042ba2  cmovnz  rsi, rax
0x180042ba6  cmp     [rbp+84h], r13b
0x180042bad  jnz     loc_180042F16
0x180042bb3  lea     r14, [rbp+10h]
0x180042bb7  mov     r15, r14
0x180042bba  cmp     cs:byte_180069913, r13b
0x180042bc1  mov     ebx, r13d
0x180042bc4  jnz     short loc_180042BD6
0x180042bc6  cmp     cs:byte_180069916, r13b
0x180042bcd  mov     r15, r14
0x180042bd0  jnz     loc_180042D5D
0x180042bd6  cmp     [rbp+100h], r13b
0x180042bdd  jnz     loc_180042D5D
0x180042be3  mov     r12d, r13d
0x180042be6  mov     r8d, 10h; Size
0x180042bec  mov     [r15], r13
0x180042bef  lea     rdx, qword_1800554E8; Buf2
0x180042bf6  lea     rcx, ?c_gameInputServiceGuid@GameInputServer@@0U_GUID@@B; Buf1
0x180042bfd  call    memcmp_0
0x180042c02  test    eax, eax
0x180042c04  jz      loc_180042D58
0x180042c0a  mov     rcx, gs:60h
0x180042c13  xor     edx, edx; Flags
0x180042c15  mov     r8d, 0A0h; Size
0x180042c1b  mov     rcx, [rcx+30h]; HeapHandle
0x180042c1f  call    cs:__imp_RtlAllocateHeap
0x180042c26  nop     dword ptr [rax+rax+00h]
0x180042c2b  mov     rdi, rax
0x180042c2e  test    rax, rax
0x180042c31  jz      loc_180042D51
0x180042c37  lea     rax, ??_7?$SipcObjectBase@UISIPCServer@@@@6B@; const SipcObjectBase<ISIPCServer>::`vftable'
0x180042c3e  mov     [rdi], rax
0x180042c41  lea     r9, [rdi+38h]
0x180042c45  mov     qword ptr [rdi+8], 2
0x180042c4d  lea     rax, ??_7SipcEndpointOwner@@6B@; const SipcEndpointOwner::`vftable'
0x180042c54  mov     [rdi+10h], rax
0x180042c58  lea     rax, ??_7SipcServer@@6B?$SipcObjectBase@UISIPCServer@@@@@; const SipcServer::`vftable'{for `SipcObjectBase<ISIPCServer>'}
0x180042c5f  movups  xmm0, xmmword ptr cs:?c_gameInputServiceGuid@GameInputServer@@0U_GUID@@B.Data1; _GUID const GameInputServer::c_gameInputServiceGuid ...
0x180042c66  mov     dword ptr [rdi+28h], 1
0x180042c6d  mov     word ptr [rdi+2Ch], 2
0x180042c73  movdqu  xmmword ptr [rdi+18h], xmm0
0x180042c78  mov     [rdi+30h], r13
0x180042c7c  mov     [rdi], rax
0x180042c7f  lea     rax, ??_7SipcServer@@6BSipcEndpointOwner@@@; const SipcServer::`vftable'{for `SipcEndpointOwner'}
0x180042c86  mov     [rdi+10h], rax
0x180042c8a  lea     rax, [rdi+58h]
0x180042c8e  mov     [rdi+60h], rax
0x180042c92  mov     [rax], rax
0x180042c95  lea     rax, [rdi+70h]
0x180042c99  mov     [rdi+78h], rax
0x180042c9d  mov     [rax], rax
0x180042ca0  lea     rax, ?OnSipcServerConnection@GameInputServer@@CAXPEAUISIPCServer@@PEBUSIPC_CLIENT_INFO@@PEAX@Z; GameInputServer::OnSipcServerConnection(ISIPCServer *,SIPC_CLIENT_INFO const *,void *)
0x180042ca7  mov     [rdi+90h], rax
0x180042cae  mov     [rdi+38h], r13
0x180042cb2  mov     [rdi+40h], r13
0x180042cb6  mov     [rdi+48h], r13
0x180042cba  mov     [rdi+50h], r13
0x180042cbe  mov     [rdi+68h], r13d
0x180042cc2  mov     [rdi+80h], r13d
0x180042cc9  mov     [rdi+88h], r13
0x180042cd0  mov     [rdi+98h], rbp
0x180042cd7  call    ?CreateServerPort@AlpcPort@@SAJAEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@PEAXPEAPEAVSipcPort@@@Z; AlpcPort::CreateServerPort(_GUID const &,SIPC_SERVICE_BOUNDARY,void *,SipcPort * *)
0x180042cdc  mov     ebx, eax
0x180042cde  test    eax, eax
0x180042ce0  js      short loc_180042D21
0x180042ce2  lea     rcx, [rdi+40h]; this
0x180042ce6  call    ?Initialize@AggregateWaitHandle@@QEAAJXZ; AggregateWaitHandle::Initialize(void)
0x180042ceb  mov     ebx, eax
0x180042ced  test    eax, eax
0x180042cef  js      short loc_180042D1E
0x180042cf1  mov     rcx, [rdi+38h]
0x180042cf5  mov     rax, [rcx]
0x180042cf8  mov     rax, [rax+28h]
0x180042cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d01  mov     rdx, rax; void *
0x180042d04  lea     rcx, [rdi+40h]; this
0x180042d08  call    ?AddHandle@AggregateWaitHandle@@QEAAJPEAX@Z; AggregateWaitHandle::AddHandle(void *)
0x180042d0d  xor     r13d, r13d
0x180042d10  mov     ebx, eax
0x180042d12  test    eax, eax
0x180042d14  js      short loc_180042D21
0x180042d16  mov     [r15], rdi
0x180042d19  mov     ebx, r13d
0x180042d1c  jmp     short loc_180042D5D
0x180042d1e  xor     r13d, r13d
0x180042d21  mov     rcx, rdi
0x180042d24  call    ?Release@?$SipcObjectBase@UISIPCClient@@@@UEAAKXZ; SipcObjectBase<ISIPCClient>::Release(void)
0x180042d29  cmp     ebx, 0D0000035h
0x180042d2f  jnz     short loc_180042D5D
0x180042d31  mov     ecx, 1F4h; dwMilliseconds
0x180042d36  call    cs:__imp_Sleep
0x180042d3d  nop     dword ptr [rax+rax+00h]
0x180042d42  inc     r12d
0x180042d45  cmp     r12d, 5
0x180042d49  jb      loc_180042BE6
0x180042d4f  jmp     short loc_180042D5D
0x180042d51  mov     ebx, 8007000Eh
0x180042d56  jmp     short loc_180042D5D
0x180042d58  mov     ebx, 80070057h
0x180042d5d  call    Feature_Servicing_GameInputSvcRundown__private_IsEnabledDeviceUsageNoInline
0x180042d62  test    eax, eax
0x180042d64  jnz     short loc_180042D73
0x180042d66  test    ebx, ebx
0x180042d68  js      loc_180042F42
0x180042d6e  jmp     loc_180042ED0
0x180042d73  mov     edx, ebx
0x180042d75  mov     [rbp+120h], ebx
0x180042d7b  call    _GameInputServer__WorkerThreadProc____17____lambda_1___operator__
0x180042d80  mov     rcx, [rbp+118h]; hEvent
0x180042d87  mov     [rbp+84h], al
0x180042d8d  call    cs:__imp_SetEvent
0x180042d94  nop     dword ptr [rax+rax+00h]
0x180042d99  jmp     loc_180042ED0
0x180042d9e  test    ebx, ebx
0x180042da0  js      loc_180042EE1
0x180042da6  jmp     short loc_180042DC8
0x180042da8  cmp     [rbp+84h], r13b
0x180042daf  jnz     short loc_180042DE7
0x180042db1  test    ebx, ebx
0x180042db3  js      short loc_180042DD0
0x180042db5  cmp     ebx, 1
0x180042db8  jz      short loc_180042DD0
0x180042dba  mov     rax, [rcx]
0x180042dbd  mov     rax, [rax+20h]
0x180042dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042dc6  mov     ebx, eax
0x180042dc8  mov     rcx, [r14]
0x180042dcb  test    rcx, rcx
0x180042dce  jnz     short loc_180042DA8
0x180042dd0  cmp     [rbp+84h], r13b
0x180042dd7  jnz     short loc_180042DE7
0x180042dd9  test    ebx, ebx
0x180042ddb  js      short loc_180042DE7
0x180042ddd  mov     rcx, rbp; this
0x180042de0  call    ?ProcessQueuedWorkItems@GameInputServer@@AEAAJXZ; GameInputServer::ProcessQueuedWorkItems(void)
0x180042de5  mov     ebx, eax
0x180042de7  mov     [rsp+58h+arg_10], r13
0x180042dec  cmp     [rbp+84h], r13b
0x180042df3  jnz     loc_180042EDD
0x180042df9  test    ebx, ebx
0x180042dfb  js      short loc_180042E79
0x180042dfd  mov     r14d, [rbp+80h]
0x180042e04  lea     r15, [rbp+38h]
0x180042e08  nop
0x180042e09  mov     rdi, [r15]
0x180042e0c  cmp     rdi, r15
0x180042e0f  jz      short loc_180042E53
0x180042e11  lea     r12, [rdi+20h]
0x180042e15  mov     rbx, [r12]
0x180042e19  cmp     rbx, r12
0x180042e1c  jz      short loc_180042E4E
0x180042e1e  cmp     [rdi+58h], r14d
0x180042e22  jnz     short loc_180042E36
0x180042e24  mov     rax, [rbx+10h]
0x180042e28  mov     rcx, [rax+68h]; this
0x180042e2c  test    rcx, rcx
0x180042e2f  jz      short loc_180042E36
0x180042e31  call    ?OnClientSignal@FeedbackManager@@QEAAXXZ; FeedbackManager::OnClientSignal(void)
0x180042e36  mov     rcx, rbx
0x180042e39  call    ?GetFocusPolicy@BufferListEntry@GameInputServer@@QEBA?AW4GameInputFocusPolicy@@XZ; GameInputServer::BufferListEntry::GetFocusPolicy(void)
0x180042e3e  cmp     [rbx+48h], eax
0x180042e41  jz      short loc_180042E49
0x180042e43  mov     [rbx+48h], eax
0x180042e46  mov     r13b, 1
0x180042e49  mov     rbx, [rbx]
0x180042e4c  jmp     short loc_180042E19
0x180042e4e  mov     rdi, [rdi]
0x180042e51  jmp     short loc_180042E0C
0x180042e53  lea     r14, [rbp+10h]
0x180042e57  test    r13b, r13b
0x180042e5a  jz      short loc_180042E64
0x180042e5c  mov     rcx, rbp; this
0x180042e5f  call    ?UpdateSystemButtonState@GameInputServer@@AEAAXXZ; GameInputServer::UpdateSystemButtonState(void)
0x180042e64  mov     rax, 7FFFFFFFFFFFFFFFh
0x180042e6e  xor     r13d, r13d
0x180042e71  mov     [rsp+58h+arg_10], rax
0x180042e76  mov     ebx, r13d
0x180042e79  cmp     [rbp+84h], r13b
0x180042e80  jnz     short loc_180042EDD
0x180042e82  test    ebx, ebx
0x180042e84  js      short loc_180042EE1
0x180042e86  mov     rcx, [r14]
0x180042e89  test    rcx, rcx
0x180042e8c  jz      short loc_180042E9F
0x180042e8e  mov     rax, [rcx]
0x180042e91  mov     rax, [rax+28h]
0x180042e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e9a  mov     rcx, rax
0x180042e9d  jmp     short loc_180042EA2
0x180042e9f  mov     rcx, rsi; Handle
0x180042ea2  mov     rax, [rsp+58h+arg_10]
0x180042ea7  mov     dl, 1; Alertable
0x180042ea9  neg     rax
0x180042eac  lea     rax, [rsp+58h+arg_10]
0x180042eb1  sbb     r8, r8
0x180042eb4  and     r8, rax; Timeout
0x180042eb7  call    cs:__imp_NtWaitForSingleObject
0x180042ebe  nop     dword ptr [rax+rax+00h]
0x180042ec3  mov     ebx, eax
0x180042ec5  cmp     eax, 101h
0x180042eca  jz      short loc_180042E86
0x180042ecc  bts     ebx, 1Ch
0x180042ed0  cmp     [rbp+84h], r13b
0x180042ed7  jz      loc_180042D9E
0x180042edd  test    ebx, ebx
0x180042edf  jns     short loc_180042EEF
0x180042ee1  mov     [rsp+58h+arg_8], ebx
0x180042ee5  mov     eax, [rsp+58h+arg_0]
0x180042ee9  inc     eax
0x180042eeb  mov     [rsp+58h+arg_0], eax
0x180042eef  mov     rcx, [r14]
0x180042ef2  mov     r15, r14
0x180042ef5  test    rcx, rcx
0x180042ef8  jz      short loc_180042F09
0x180042efa  mov     rax, [rcx]
0x180042efd  mov     rax, [rax+10h]
0x180042f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f06  mov     [r14], r13
0x180042f09  cmp     [rbp+84h], r13b
0x180042f10  jz      loc_180042BBA
0x180042f16  test    rsi, rsi
0x180042f19  jz      short loc_180042F2A
0x180042f1b  mov     rcx, rsi; hObject
0x180042f1e  call    cs:__imp_CloseHandle
0x180042f25  nop     dword ptr [rax+rax+00h]
0x180042f2a  mov     rbx, [rsp+58h+arg_18]
0x180042f2f  xor     eax, eax
0x180042f31  add     rsp, 20h
0x180042f35  pop     r15
0x180042f37  pop     r14
0x180042f39  pop     r13
0x180042f3b  pop     r12
0x180042f3d  pop     rdi
0x180042f3e  pop     rsi
0x180042f3f  pop     rbp
0x180042f40  retn
0x180042f42  mov     edx, 81Ch
0x180042f47  mov     ecx, ebx
0x180042f49  call    GameInputFailFast
```
