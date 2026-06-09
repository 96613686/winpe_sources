# GameInputServer::OnSipcServerConnection(ISIPCServer *,SIPC_CLIENT_INFO const *,void *)

- ea: `0x18003dc00`
- end: `0x18003e19c`
- name: `?OnSipcServerConnection@GameInputServer@@CAXPEAUISIPCServer@@PEBUSIPC_CLIENT_INFO@@PEAX@Z`
- size: `1436`
- prototype: `static void(struct ISIPCServer *, const struct SIPC_CLIENT_INFO *, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180001008`
- `0x180001630`
- `0x18000c11c`
- `0x18001bf00`
- `0x18002d59c`
- `0x18002f774`
- `0x18003b238`
- `0x18003dc00`
- `0x1800425c0`
- `0x180042fd0`
- `0x180043018`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18003dee8`
- `ntdll!_wcsicmp` at `0x18003dee8`
- `ntdll!RtlAllocateHeap` at `0x18003dd46`
- `ntdll!RtlAllocateHeap` at `0x18003dd46`
- `ntdll!wcsrchr` at `0x18003deb9`
- `ntdll!wcsrchr` at `0x18003ded1`
- `ntdll!wcsrchr` at `0x18003deb9`
- `ntdll!wcsrchr` at `0x18003ded1`
- `ntdll!NtQueryInformationProcess` at `0x18003df65`
- `ntdll!NtQueryInformationProcess` at `0x18003df65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dde5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dff6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e07e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dde5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dff6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e07e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003de1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e063`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e0c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003de1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e063`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e0c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003deff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003df7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003deff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003df7a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003de6e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003df37`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003de6e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003df37`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18003de9c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18003de9c`

## pseudocode

```c
void __fastcall GameInputServer::OnSipcServerConnection(
        struct ISIPCServer *a1,
        const struct SIPC_CLIENT_INFO *a2,
        char *a3,
        int a4)
{
  int v7; // eax
  char *v8; // rbx
  struct GameInputServer::ClientListEntry *i; // rdx
  _QWORD **v10; // r12
  unsigned int v11; // r15d
  _QWORD *j; // rax
  __int64 v13; // rcx
  _QWORD *Heap; // rax
  int v15; // r8d
  int v16; // r9d
  char **v17; // rdi
  _QWORD *v18; // rax
  char *v19; // xmm1_8
  __int64 v20; // rax
  char **v21; // rax
  HANDLE v22; // rax
  void *v23; // rbx
  wchar_t *v24; // rax
  DWORD v25; // r8d
  int v26; // ebx
  HANDLE v27; // r15
  _QWORD *k; // rbx
  HKL v29; // r9
  char ***v30; // rcx
  __int64 v31; // r8
  FeedbackManager *v32; // rcx
  char *v33; // rdx
  char **v34; // rax
  const struct std::nothrow_t *v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  DWORD dwSize[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v38; // [rsp+58h] [rbp-A8h] BYREF
  const char *v39; // [rsp+60h] [rbp-A0h] BYREF
  const char *v40; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+70h] [rbp-90h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v43; // [rsp+98h] [rbp-68h]
  WCHAR ExeName[64]; // [rsp+B0h] [rbp-50h] BYREF

  if ( (unsigned int)dword_180069000 > 4
    && (qword_180069010 & 0x400) != 0
    && (qword_180069018 & 0x400) == qword_180069018 )
  {
    v7 = *((_DWORD *)a3 + 32);
    v40 = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
    v41 = v7;
    v38 = *((_DWORD *)a2 + 8);
    v39 = "GameInputServer: Client connection requested";
    dwSize[0] = 1062;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)byte_1800622D3,
      (unsigned int)"onecore\\xbox\\gameinput\\server\\gameinputserver.cpp",
      a4,
      (__int64)&v40,
      (__int64)dwSize,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v41);
  }
  v8 = a3 + 56;
  for ( i = (struct GameInputServer::ClientListEntry *)*((_QWORD *)a3 + 7);
        i != (struct GameInputServer::ClientListEntry *)v8;
        i = *(struct GameInputServer::ClientListEntry **)i )
  {
    if ( *((_DWORD *)a2 + 8) == *((_DWORD *)i + 22) )
    {
      GameInputServer::DisconnectClient((GameInputServer *)a3, i);
      break;
    }
  }
  v10 = (_QWORD **)(a3 + 80);
  v11 = 0;
  for ( j = (_QWORD *)*((_QWORD *)a3 + 10); j != v10; j = (_QWORD *)*j )
  {
    v13 = (__int64)(j + 5);
    if ( !j )
      v13 = 88;
    if ( (*(_DWORD *)(*(_QWORD *)v13 + 104LL) & 0x40000) != 0 || (*((_BYTE *)a2 + 49) & 1) == 0 )
      ++v11;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x80u);
  v17 = (char **)Heap;
  if ( !Heap )
    goto LABEL_52;
  Heap[2] = 0;
  Heap[3] = 0;
  *((_DWORD *)Heap + 12) = 0;
  v18 = Heap + 4;
  v18[1] = v18;
  *v18 = v18;
  *(_OWORD *)(v17 + 7) = *(_OWORD *)a2;
  *(_OWORD *)(v17 + 9) = *((_OWORD *)a2 + 1);
  *(_OWORD *)(v17 + 11) = *((_OWORD *)a2 + 2);
  v19 = (char *)*((_QWORD *)a2 + 6);
  *((_BYTE *)v17 + 120) = 0;
  v17[13] = v19;
  v17[14] = 0;
  v20 = *(_QWORD *)a1;
  v40 = (const char *)(v17 + 2);
  if ( (*(int (__fastcall **)(struct ISIPCServer *, _QWORD, void (__fastcall *)(Instance *__hidden, unsigned int), void *, char *, char **))(v20 + 24))(
         a1,
         v11,
         Instance::OnDeviceDisconnected,
         &GameInputServer::OnSipcEndpointStatus,
         a3,
         v17 + 2) < 0 )
  {
    GameInputServer::ClientListEntry::~ClientListEntry((GameInputServer::ClientListEntry *)v17);
    operator delete(v17, v36);
    return;
  }
  AcquireSRWLockExclusive((PSRWLOCK)a3 + 6);
  v21 = (char **)*((_QWORD *)a3 + 8);
  if ( *v21 != v8 )
    goto LABEL_57;
  *v17 = v8;
  v17[1] = (char *)v21;
  *v21 = (char *)v17;
  ++*((_DWORD *)a3 + 18);
  v39 = (const char *)(v17 + 1);
  *((_QWORD *)a3 + 8) = v17;
  ReleaseSRWLockExclusive((PSRWLOCK)a3 + 6);
  if ( byte_180069913 )
  {
    GameInputServer::ClientListEntry::UpdateKeyboardLayout((GameInputServer::ClientListEntry *)v17, 0);
  }
  else if ( qword_1800697A0 )
  {
    qword_1800697A0(GameInputServer::EnumWindowsCallback, v17);
  }
  if ( (unsigned int)Feature_52580392__private_IsEnabledDeviceUsageNoInline() )
  {
    v22 = OpenProcess(0x1000u, 0, *((_DWORD *)a2 + 8));
    v23 = v22;
    if ( v22 )
    {
      dwSize[0] = 64;
      if ( QueryFullProcessImageNameW(v22, 0, ExeName, dwSize) )
      {
        if ( wcsrchr(ExeName, 0x5Cu) )
        {
          v24 = wcsrchr(ExeName, 0x5Cu);
          if ( !_wcsicmp(v24 + 1, L"explorer.exe") )
            *((_BYTE *)v17 + 120) = 1;
        }
      }
      CloseHandle(v23);
    }
  }
  if ( (unsigned int)Feature_GameInput_ExclusiveInputToChildren__private_IsEnabledDeviceUsageNoInline() )
  {
    v25 = *((_DWORD *)a2 + 8);
    dwSize[0] = 0;
    memset(ProcessInformation, 0, sizeof(ProcessInformation));
    v43 = 0;
    v26 = 0;
    v27 = OpenProcess(0x400u, 0, v25);
    if ( v27 )
    {
      if ( NtQueryInformationProcess(v27, ProcessBasicInformation, ProcessInformation, 0x30u, dwSize) >= 0 )
        v26 = DWORD2(v43);
      CloseHandle(v27);
    }
    *((_DWORD *)v17 + 31) = v26;
  }
  for ( k = *v10; ; k = (_QWORD *)*k )
  {
    if ( k == v10 )
      goto LABEL_52;
    if ( (*(_DWORD *)(*(_QWORD *)(((unsigned __int64)(k - 6) & -(__int64)(k != 0)) + 0x58) + 104LL) & 0x40000) != 0
      || (*((_BYTE *)a2 + 49) & 1) == 0 )
    {
      break;
    }
LABEL_48:
    ;
  }
  v29 = (HKL)v17[14];
  *(_QWORD *)dwSize = 0;
  if ( (int)GameInputServer::BufferListEntry::Create(
              (struct GameInputServerDevice *)((unsigned __int64)(k - 6) & -(__int64)(k != 0)),
              *(struct ISIPCEndpoint **)v40,
              (const struct SIPC_CLIENT_INFO *)(v17 + 7),
              v29,
              (struct GameInputServer::BufferListEntry **)dwSize) >= 0 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)v17 + 3);
    v30 = (char ***)v17[5];
    if ( *v30 != v17 + 4 )
      goto LABEL_57;
    v31 = *(_QWORD *)dwSize;
    **(_QWORD **)dwSize = v17 + 4;
    *(_QWORD *)(v31 + 8) = v30;
    *v30 = (char **)v31;
    ++*((_DWORD *)v17 + 12);
    v17[5] = (char *)v31;
    if ( *((_DWORD *)v17 + 22) == *((_DWORD *)a3 + 32) )
    {
      v32 = *(FeedbackManager **)(((unsigned __int64)(k - 6) & -(__int64)(k != 0)) + 0x68);
      if ( v32 )
        FeedbackManager::SetClient(
          v32,
          (const struct FeedbackDataLayout *)((*(unsigned int *)(*(_QWORD *)(v31 + 56) + 24LL) + *(_QWORD *)(v31 + 56))
                                            & -(__int64)(*(_DWORD *)(*(_QWORD *)(v31 + 56) + 24LL) != 0)),
          *(_QWORD *)(v31 + 80),
          *(_BYTE *)(v31 + 88));
    }
    ReleaseSRWLockExclusive((PSRWLOCK)v17 + 3);
    v10 = (_QWORD **)(a3 + 80);
    goto LABEL_48;
  }
  AcquireSRWLockExclusive((PSRWLOCK)a3 + 6);
  v33 = *v17;
  if ( *((char ***)*v17 + 1) != v17 || (v34 = *(char ***)v39, **(char ****)v39 != v17) )
LABEL_57:
    __fastfail(3u);
  *v34 = v33;
  *((_QWORD *)v33 + 1) = v34;
  --*((_DWORD *)a3 + 18);
  GameInputServer::ClientListEntry::~ClientListEntry((GameInputServer::ClientListEntry *)v17);
  operator delete(v17, v35);
  ReleaseSRWLockExclusive((PSRWLOCK)a3 + 6);
LABEL_52:
  if ( (unsigned int)dword_180069000 > 4
    && (qword_180069010 & 0x400) != 0
    && (qword_180069018 & 0x400) == qword_180069018 )
  {
    dwSize[0] = *((_DWORD *)a2 + 8);
    v40 = "GameInputServer: Client connected";
    v39 = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
    v38 = 1223;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)byte_1800626DB,
      v15,
      v16,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v40,
      (__int64)dwSize);
  }
}

```

## disassembly

```asm
0x18003dc00  mov     [rsp-8+arg_18], rbx
0x18003dc05  push    rbp
0x18003dc06  push    rsi
0x18003dc07  push    rdi
0x18003dc08  push    r12
0x18003dc0a  push    r13
0x18003dc0c  push    r14
0x18003dc0e  push    r15
0x18003dc10  lea     rbp, [rsp-40h]
0x18003dc15  sub     rsp, 140h
0x18003dc1c  mov     rax, cs:__security_cookie
0x18003dc23  xor     rax, rsp
0x18003dc26  mov     [rbp+70h+var_40], rax
0x18003dc2a  mov     eax, cs:dword_180069000
0x18003dc30  mov     rsi, r8
0x18003dc33  lea     r8, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x18003dc3a  mov     r14, rdx
0x18003dc3d  mov     r13, rcx
0x18003dc40  mov     edx, 400h
0x18003dc45  cmp     eax, 4
0x18003dc48  jbe     loc_18003DCD6
0x18003dc4e  mov     rcx, cs:qword_180069018
0x18003dc55  mov     rax, cs:qword_180069010
0x18003dc5c  test    rdx, rax
0x18003dc5f  jz      short loc_18003DCD6
0x18003dc61  mov     rax, rcx
0x18003dc64  and     rax, rdx
0x18003dc67  cmp     rax, rcx
0x18003dc6a  jnz     short loc_18003DCD6
0x18003dc6c  mov     eax, [rsi+80h]
0x18003dc72  lea     rdx, byte_1800622D3
0x18003dc79  nop
0x18003dc7a  mov     [rsp+170h+var_108], r8
0x18003dc7f  mov     [rsp+170h+var_100], eax
0x18003dc83  mov     eax, [r14+20h]
0x18003dc87  mov     [rsp+170h+var_118], eax
0x18003dc8b  lea     rax, aGameinputserve_5; "GameInputServer: Client connection requ"...
0x18003dc92  mov     [rsp+170h+var_110], rax
0x18003dc97  lea     rax, [rsp+170h+var_100]
0x18003dc9c  mov     [rsp+170h+var_130], rax
0x18003dca1  lea     rax, [rsp+170h+var_118]
0x18003dca6  mov     [rsp+170h+var_138], rax
0x18003dcab  lea     rax, [rsp+170h+var_110]
0x18003dcb0  mov     [rsp+170h+var_140], rax
0x18003dcb5  lea     rax, [rsp+170h+dwSize]
0x18003dcba  mov     [rsp+170h+var_148], rax
0x18003dcbf  lea     rax, [rsp+170h+var_108]
0x18003dcc4  mov     [rsp+170h+ReturnLength], rax
0x18003dcc9  mov     [rsp+170h+dwSize], 426h
0x18003dcd1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003dcd6  lea     rbx, [rsi+38h]
0x18003dcda  mov     rdx, [rbx]; struct GameInputServer::ClientListEntry *
0x18003dcdd  cmp     rdx, rbx
0x18003dce0  jz      short loc_18003DCF8
0x18003dce2  mov     eax, [rdx+58h]
0x18003dce5  cmp     [r14+20h], eax
0x18003dce9  jz      short loc_18003DCF0
0x18003dceb  mov     rdx, [rdx]
0x18003dcee  jmp     short loc_18003DCDD
0x18003dcf0  mov     rcx, rsi; this
0x18003dcf3  call    ?DisconnectClient@GameInputServer@@AEAAXAEAUClientListEntry@1@@Z; GameInputServer::DisconnectClient(GameInputServer::ClientListEntry &)
0x18003dcf8  lea     r12, [rsi+50h]
0x18003dcfc  xor     r15d, r15d
0x18003dcff  mov     rax, [r12]
0x18003dd03  cmp     rax, r12
0x18003dd06  jz      short loc_18003DD31
0x18003dd08  lea     rcx, [rax+28h]
0x18003dd0c  test    rax, rax
0x18003dd0f  jnz     short loc_18003DD16
0x18003dd11  mov     ecx, 58h ; 'X'
0x18003dd16  mov     rcx, [rcx]
0x18003dd19  test    dword ptr [rcx+68h], 40000h
0x18003dd20  jnz     short loc_18003DD29
0x18003dd22  test    byte ptr [r14+31h], 1
0x18003dd27  jnz     short loc_18003DD2C
0x18003dd29  inc     r15d
0x18003dd2c  mov     rax, [rax]
0x18003dd2f  jmp     short loc_18003DD03
0x18003dd31  mov     rcx, gs:60h
0x18003dd3a  xor     edx, edx; Flags
0x18003dd3c  mov     r8d, 80h; Size
0x18003dd42  mov     rcx, [rcx+30h]; HeapHandle
0x18003dd46  call    cs:__imp_RtlAllocateHeap
0x18003dd4d  nop     dword ptr [rax+rax+00h]
0x18003dd52  xor     ecx, ecx
0x18003dd54  mov     rdi, rax
0x18003dd57  test    rax, rax
0x18003dd5a  jz      loc_18003E0D1
0x18003dd60  mov     [rax+10h], rcx
0x18003dd64  lea     r9, ?OnSipcEndpointStatus@GameInputServer@@CAXPEAUISIPCEndpoint@@W4SIPC_ENDPOINT_STATUS@@PEAX@Z; GameInputServer::OnSipcEndpointStatus(ISIPCEndpoint *,SIPC_ENDPOINT_STATUS,void *)
0x18003dd6b  mov     [rax+18h], rcx
0x18003dd6f  lea     r8, ?OnDeviceDisconnected@Instance@@UEAAXI@Z; Instance::OnDeviceDisconnected(uint)
0x18003dd76  mov     [rax+30h], ecx
0x18003dd79  add     rax, 20h ; ' '
0x18003dd7d  mov     edx, r15d
0x18003dd80  mov     [rax+8], rax
0x18003dd84  mov     [rax], rax
0x18003dd87  movups  xmm0, xmmword ptr [r14]
0x18003dd8b  movups  xmmword ptr [rdi+38h], xmm0
0x18003dd8f  movups  xmm1, xmmword ptr [r14+10h]
0x18003dd94  movups  xmmword ptr [rdi+48h], xmm1
0x18003dd98  movups  xmm0, xmmword ptr [r14+20h]
0x18003dd9d  movups  xmmword ptr [rdi+58h], xmm0
0x18003dda1  movsd   xmm1, qword ptr [r14+30h]
0x18003dda7  mov     [rdi+78h], cl
0x18003ddaa  movsd   qword ptr [rdi+68h], xmm1
0x18003ddaf  mov     [rdi+70h], rcx
0x18003ddb3  lea     rcx, [rdi+10h]
0x18003ddb7  mov     rax, [r13+0]
0x18003ddbb  mov     [rsp+170h+var_148], rcx
0x18003ddc0  mov     [rsp+170h+var_108], rcx
0x18003ddc5  mov     rcx, r13
0x18003ddc8  mov     [rsp+170h+ReturnLength], rsi
0x18003ddcd  mov     rax, [rax+18h]
0x18003ddd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddd6  test    eax, eax
0x18003ddd8  js      loc_18003E18A
0x18003ddde  lea     r13, [rsi+30h]
0x18003dde2  mov     rcx, r13; SRWLock
0x18003dde5  call    cs:__imp_AcquireSRWLockExclusive
0x18003ddec  nop     dword ptr [rax+rax+00h]
0x18003ddf1  mov     rax, [rbx+8]
0x18003ddf5  cmp     [rax], rbx
0x18003ddf8  jnz     loc_18003E183
0x18003ddfe  mov     [rdi], rbx
0x18003de01  lea     rcx, [rdi+8]
0x18003de05  mov     [rcx], rax
0x18003de08  mov     [rax], rdi
0x18003de0b  inc     dword ptr [rbx+10h]
0x18003de0e  mov     [rsp+170h+var_110], rcx
0x18003de13  mov     rcx, r13; SRWLock
0x18003de16  mov     [rbx+8], rdi
0x18003de1a  call    cs:__imp_ReleaseSRWLockExclusive
0x18003de21  nop     dword ptr [rax+rax+00h]
0x18003de26  cmp     cs:byte_180069913, 0
0x18003de2d  jz      short loc_18003DE3B
0x18003de2f  xor     edx, edx; unsigned int
0x18003de31  mov     rcx, rdi; this
0x18003de34  call    ?UpdateKeyboardLayout@ClientListEntry@GameInputServer@@QEAAXK@Z; GameInputServer::ClientListEntry::UpdateKeyboardLayout(ulong)
0x18003de39  jmp     short loc_18003DE56
0x18003de3b  mov     rax, cs:qword_1800697A0
0x18003de42  test    rax, rax
0x18003de45  jz      short loc_18003DE56
0x18003de47  mov     rdx, rdi
0x18003de4a  lea     rcx, ?EnumWindowsCallback@GameInputServer@@CAHPEAUHWND__@@_J@Z; GameInputServer::EnumWindowsCallback(HWND__ *,__int64)
0x18003de51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de56  call    Feature_52580392__private_IsEnabledDeviceUsageNoInline
0x18003de5b  test    eax, eax
0x18003de5d  jz      loc_18003DF0B
0x18003de63  mov     r8d, [r14+20h]; dwProcessId
0x18003de67  xor     edx, edx; bInheritHandle
0x18003de69  mov     ecx, 1000h; dwDesiredAccess
0x18003de6e  call    cs:__imp_OpenProcess
0x18003de75  nop     dword ptr [rax+rax+00h]
0x18003de7a  mov     rbx, rax
0x18003de7d  test    rax, rax
0x18003de80  jz      loc_18003DF0B
0x18003de86  lea     r9, [rsp+170h+dwSize]; lpdwSize
0x18003de8b  mov     [rsp+170h+dwSize], 40h ; '@'
0x18003de93  lea     r8, [rbp+70h+ExeName]; lpExeName
0x18003de97  xor     edx, edx; dwFlags
0x18003de99  mov     rcx, rax; hProcess
0x18003de9c  call    cs:__imp_QueryFullProcessImageNameW
0x18003dea3  nop     dword ptr [rax+rax+00h]
0x18003dea8  test    eax, eax
0x18003deaa  jz      short loc_18003DEFC
0x18003deac  mov     r15d, 5Ch ; '\'
0x18003deb2  lea     rcx, [rbp+70h+ExeName]; Str
0x18003deb6  mov     edx, r15d; Ch
0x18003deb9  call    cs:__imp_wcsrchr
0x18003dec0  nop     dword ptr [rax+rax+00h]
0x18003dec5  test    rax, rax
0x18003dec8  jz      short loc_18003DEFC
0x18003deca  mov     edx, r15d; Ch
0x18003decd  lea     rcx, [rbp+70h+ExeName]; Str
0x18003ded1  call    cs:__imp_wcsrchr
0x18003ded8  nop     dword ptr [rax+rax+00h]
0x18003dedd  lea     rdx, aExplorerExe; "explorer.exe"
0x18003dee4  lea     rcx, [rax+2]; String1
0x18003dee8  call    cs:__imp__wcsicmp
0x18003deef  nop     dword ptr [rax+rax+00h]
0x18003def4  test    eax, eax
0x18003def6  jnz     short loc_18003DEFC
0x18003def8  mov     byte ptr [rdi+78h], 1
0x18003defc  mov     rcx, rbx; hObject
0x18003deff  call    cs:__imp_CloseHandle
0x18003df06  nop     dword ptr [rax+rax+00h]
0x18003df0b  call    Feature_GameInput_ExclusiveInputToChildren__private_IsEnabledDeviceUsageNoInline
0x18003df10  test    eax, eax
0x18003df12  jz      short loc_18003DF89
0x18003df14  mov     r8d, [r14+20h]; dwProcessId
0x18003df18  xorps   xmm0, xmm0
0x18003df1b  xor     edx, edx; bInheritHandle
0x18003df1d  mov     [rsp+170h+dwSize], 0
0x18003df25  mov     ecx, 400h; dwDesiredAccess
0x18003df2a  movups  [rsp+170h+ProcessInformation], xmm0
0x18003df2f  movups  [rbp+70h+var_E8], xmm0
0x18003df33  movups  [rbp+70h+var_D8], xmm0
0x18003df37  call    cs:__imp_OpenProcess
0x18003df3e  nop     dword ptr [rax+rax+00h]
0x18003df43  xor     ebx, ebx
0x18003df45  mov     r15, rax
0x18003df48  test    rax, rax
0x18003df4b  jz      short loc_18003DF86
0x18003df4d  lea     rax, [rsp+170h+dwSize]
0x18003df52  xor     edx, edx; ProcessInformationClass
0x18003df54  lea     r9d, [rbx+30h]; ProcessInformationLength
0x18003df58  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x18003df5d  lea     r8, [rsp+170h+ProcessInformation]; ProcessInformation
0x18003df62  mov     rcx, r15; ProcessHandle
0x18003df65  call    cs:__imp_NtQueryInformationProcess
0x18003df6c  nop     dword ptr [rax+rax+00h]
0x18003df71  test    eax, eax
0x18003df73  mov     rcx, r15; hObject
0x18003df76  cmovns  ebx, dword ptr [rbp+70h+var_D8+8]
0x18003df7a  call    cs:__imp_CloseHandle
0x18003df81  nop     dword ptr [rax+rax+00h]
0x18003df86  mov     [rdi+7Ch], ebx
0x18003df89  mov     rbx, [r12]
0x18003df8d  cmp     rbx, r12
0x18003df90  jz      loc_18003E0D1
0x18003df96  mov     rax, rbx
0x18003df99  lea     rcx, [rbx-30h]
0x18003df9d  neg     rax
0x18003dfa0  sbb     r15, r15
0x18003dfa3  and     r15, rcx
0x18003dfa6  mov     rax, [r15+58h]
0x18003dfaa  test    dword ptr [rax+68h], 40000h
0x18003dfb1  jnz     short loc_18003DFBE
0x18003dfb3  test    byte ptr [r14+31h], 1
0x18003dfb8  jnz     loc_18003E073
0x18003dfbe  mov     r9, [rdi+70h]; HKL
0x18003dfc2  lea     rax, [rsp+170h+dwSize]
0x18003dfc7  mov     [rsp+170h+ReturnLength], rax; struct GameInputServer::BufferListEntry **
0x18003dfcc  lea     r8, [rdi+38h]; struct SIPC_CLIENT_INFO *
0x18003dfd0  mov     rax, [rsp+170h+var_108]
0x18003dfd5  nop
0x18003dfd6  mov     rcx, r15; this
0x18003dfd9  mov     qword ptr [rsp+170h+dwSize], 0
0x18003dfe2  mov     rdx, [rax]; struct ISIPCEndpoint *
0x18003dfe5  call    ?Create@BufferListEntry@GameInputServer@@SAJPEAVGameInputServerDevice@@PEAUISIPCEndpoint@@PEBUSIPC_CLIENT_INFO@@PEAUHKL__@@PEAPEAU12@@Z; GameInputServer::BufferListEntry::Create(GameInputServerDevice *,ISIPCEndpoint *,SIPC_CLIENT_INFO const *,HKL__ *,GameInputServer::BufferListEntry * *)
0x18003dfea  test    eax, eax
0x18003dfec  js      loc_18003E07B
0x18003dff2  lea     rcx, [rdi+18h]; SRWLock
0x18003dff6  call    cs:__imp_AcquireSRWLockExclusive
0x18003dffd  nop     dword ptr [rax+rax+00h]
0x18003e002  lea     rax, [rdi+20h]
0x18003e006  mov     rcx, [rax+8]
0x18003e00a  cmp     [rcx], rax
0x18003e00d  jnz     loc_18003E183
0x18003e013  mov     r8, qword ptr [rsp+170h+dwSize]
0x18003e018  mov     [r8], rax
0x18003e01b  mov     [r8+8], rcx
0x18003e01f  mov     [rcx], r8
0x18003e022  inc     dword ptr [rax+10h]
0x18003e025  mov     [rax+8], r8
0x18003e029  mov     eax, [rsi+80h]
0x18003e02f  nop
0x18003e030  cmp     [rdi+58h], eax
0x18003e033  jnz     short loc_18003E05F
0x18003e035  mov     rcx, [r15+68h]; this
0x18003e039  test    rcx, rcx
0x18003e03c  jz      short loc_18003E05F
0x18003e03e  mov     rax, [r8+38h]
0x18003e042  mov     edx, [rax+18h]
0x18003e045  lea     r9, [rdx+rax]
0x18003e049  neg     rdx
0x18003e04c  sbb     rdx, rdx
0x18003e04f  and     rdx, r9; struct FeedbackDataLayout *
0x18003e052  mov     r9b, [r8+58h]; unsigned __int8
0x18003e056  mov     r8, [r8+50h]; unsigned __int64
0x18003e05a  call    ?SetClient@FeedbackManager@@QEAAXPEBVFeedbackDataLayout@@_KE@Z; FeedbackManager::SetClient(FeedbackDataLayout const *,unsigned __int64,uchar)
0x18003e05f  lea     rcx, [rdi+18h]; SRWLock
0x18003e063  call    cs:__imp_ReleaseSRWLockExclusive
0x18003e06a  nop     dword ptr [rax+rax+00h]
0x18003e06f  lea     r12, [rsi+50h]
0x18003e073  mov     rbx, [rbx]
0x18003e076  jmp     loc_18003DF8D
0x18003e07b  mov     rcx, r13; SRWLock
0x18003e07e  call    cs:__imp_AcquireSRWLockExclusive
0x18003e085  nop     dword ptr [rax+rax+00h]
0x18003e08a  mov     rdx, [rdi]
0x18003e08d  cmp     [rdx+8], rdi
0x18003e091  jnz     loc_18003E183
0x18003e097  mov     rax, [rsp+170h+var_110]
0x18003e09c  mov     rax, [rax]
0x18003e09f  cmp     [rax], rdi
0x18003e0a2  jnz     loc_18003E183
0x18003e0a8  mov     [rax], rdx
0x18003e0ab  mov     rcx, rdi; this
0x18003e0ae  mov     [rdx+8], rax
0x18003e0b2  dec     dword ptr [rsi+48h]
0x18003e0b5  call    ??1ClientListEntry@GameInputServer@@QEAA@XZ; GameInputServer::ClientListEntry::~ClientListEntry(void)
0x18003e0ba  mov     rcx, rdi; P
0x18003e0bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003e0c2  mov     rcx, r13; SRWLock
0x18003e0c5  call    cs:__imp_ReleaseSRWLockExclusive
0x18003e0cc  nop     dword ptr [rax+rax+00h]
0x18003e0d1  mov     eax, cs:dword_180069000
0x18003e0d7  cmp     eax, 4
  ... truncated ...
```
