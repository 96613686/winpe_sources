# GameInputClient::GetOrCreateSingleton(IGameInput * *)

- ea: `0x18000739c`
- end: `0x1800075f4`
- name: `?GetOrCreateSingleton@GameInputClient@@SAJPEAPEAUIGameInput@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(struct IGameInput **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800038d0`

## callees

- `0x180001304`
- `0x180003b34`
- `0x180003e28`
- `0x1800065d8`
- `0x18000739c`
- `0x180007e80`
- `0x180007ec0`
- `0x18000c11c`
- `0x18000d68c`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800074d7`
- `ntdll!RtlAllocateHeap` at `0x1800074d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800073b5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800073b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800075c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800075c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000743a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000743a`

## pseudocode

```c
__int64 __fastcall GameInputClient::GetOrCreateSingleton(struct IGameInput **a1)
{
  signed __int32 v2; // ecx
  __int64 v3; // rdx
  int Instance; // ebx
  int v5; // r8d
  int v6; // r9d
  GameInputClient *Heap; // rax
  GameInputClient *v8; // rcx
  struct IMMDeviceEnumerator *v9; // rcx
  PVOID v10; // rdi
  const struct std::nothrow_t *v11; // rdx
  const char *v13; // [rsp+40h] [rbp-10h] BYREF
  int v14; // [rsp+78h] [rbp+28h] BYREF
  int v15; // [rsp+80h] [rbp+30h] BYREF
  struct IMMDeviceEnumerator *ppv; // [rsp+88h] [rbp+38h] BYREF

  AcquireSRWLockExclusive(&GameInputClient::s_singletonLock);
  if ( GameInputClient::s_globalObjectCount )
  {
    v2 = _InterlockedExchangeAdd((volatile signed __int32 *)GameInputClient::s_singleton + 2, 1u);
    if ( v2 == -1 )
    {
      GameInputFailFast(2147500036LL, 206);
      JUMPOUT(0x1800075F3LL);
    }
    if ( v2 )
    {
      ++dword_1800696C8;
    }
    else
    {
      GameInputClient::IncrementGlobalObjectCount();
      ++dword_1800696A0;
    }
    GameInputClientDebugRefCountCheck();
    *a1 = (struct IGameInput *)GameInputClient::s_singleton;
LABEL_17:
    Instance = 0;
    goto LABEL_26;
  }
  ppv = 0;
  Instance = CoCreateInstance(
               &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
               0,
               0x17u,
               &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
               (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v3 = qword_180069018;
      if ( (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
      {
        v14 = Instance;
        v13 = "onecore\\xbox\\gameinput\\client\\gameinputclient.cpp";
        v15 = 122;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)&unk_180059548,
          v5,
          v6,
          (__int64)&v13,
          (__int64)&v15,
          (__int64)&v14);
      }
    }
    goto LABEL_24;
  }
  Heap = (GameInputClient *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x160u);
  if ( Heap )
  {
    GameInputClient::s_singleton = GameInputClient::GameInputClient(Heap, ppv);
    if ( GameInputClient::s_singleton )
    {
      Instance = GameInputClient::Initialize(v8);
      if ( Instance >= 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)GameInputClient::s_singleton + 2);
        ++dword_1800696A0;
        GameInputClientDebugRefCountCheck();
        GameInputClient::s_globalObjectCount = 1;
        _mm_mfence();
        v9 = ppv;
        *a1 = (struct IGameInput *)GameInputClient::s_singleton;
        if ( v9 )
        {
          ((void (__fastcall *)(struct IMMDeviceEnumerator *))v9->lpVtbl->Release)(v9);
          ppv = 0;
        }
        goto LABEL_17;
      }
      v10 = GameInputClient::s_singleton;
      if ( GameInputClient::s_singleton )
      {
        GameInputClient::~GameInputClient((GameInputClient *)GameInputClient::s_singleton);
        operator delete(v10, v11);
      }
      GameInputClient::s_singleton = 0;
      goto LABEL_23;
    }
  }
  else
  {
    GameInputClient::s_singleton = 0;
  }
  Instance = -2147024882;
LABEL_23:
  *a1 = 0;
LABEL_24:
  if ( ppv )
  {
    ((void (__fastcall *)(struct IMMDeviceEnumerator *, __int64))ppv->lpVtbl->Release)(ppv, v3);
    ppv = 0;
  }
LABEL_26:
  ReleaseSRWLockExclusive(&GameInputClient::s_singletonLock);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000739c  mov     [rsp-18h+arg_0], rbx
0x1800073a1  push    rbp
0x1800073a2  push    rsi
0x1800073a3  push    rdi
0x1800073a4  mov     rbp, rsp
0x1800073a7  sub     rsp, 50h
0x1800073ab  mov     rsi, rcx
0x1800073ae  lea     rcx, ?s_singletonLock@GameInputClient@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800073b5  call    cs:__imp_AcquireSRWLockExclusive
0x1800073bc  nop     dword ptr [rax+rax+00h]
0x1800073c1  mov     eax, cs:?s_globalObjectCount@GameInputClient@@0U?$atomic@I@utl@@A; utl::atomic<uint> GameInputClient::s_globalObjectCount
0x1800073c7  nop
0x1800073c8  test    eax, eax
0x1800073ca  jz      short loc_180007415
0x1800073cc  mov     rax, cs:?s_singleton@GameInputClient@@0PEAV1@EA; GameInputClient * GameInputClient::s_singleton
0x1800073d3  mov     ecx, 1
0x1800073d8  nop
0x1800073d9  lock xadd [rax+8], ecx
0x1800073de  lea     eax, [rcx+1]
0x1800073e1  nop
0x1800073e2  test    eax, eax
0x1800073e4  jz      loc_1800075E4
0x1800073ea  test    ecx, ecx
0x1800073ec  jnz     short loc_1800073FB
0x1800073ee  call    ?IncrementGlobalObjectCount@GameInputClient@@SAXXZ; GameInputClient::IncrementGlobalObjectCount(void)
0x1800073f3  inc     cs:dword_1800696A0
0x1800073f9  jmp     short loc_180007401
0x1800073fb  inc     cs:dword_1800696C8
0x180007401  call    GameInputClientDebugRefCountCheck
0x180007406  mov     rax, cs:?s_singleton@GameInputClient@@0PEAV1@EA; GameInputClient * GameInputClient::s_singleton
0x18000740d  mov     [rsi], rax
0x180007410  jmp     loc_180007560
0x180007415  xor     edx, edx; pUnkOuter
0x180007417  mov     [rbp+arg_18], 0
0x18000741f  lea     rax, [rbp+arg_18]
0x180007423  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x18000742a  mov     [rsp+50h+ppv], rax; ppv
0x18000742f  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x180007436  lea     r8d, [rdx+17h]; dwClsContext
0x18000743a  call    cs:__imp_CoCreateInstance
0x180007441  nop     dword ptr [rax+rax+00h]
0x180007446  mov     ebx, eax
0x180007448  test    eax, eax
0x18000744a  jns     short loc_1800074C2
0x18000744c  mov     ecx, cs:dword_180069000
0x180007452  cmp     ecx, 2
0x180007455  jbe     loc_1800075A4
0x18000745b  mov     rdx, cs:qword_180069018
0x180007462  mov     rcx, cs:qword_180069010
0x180007469  test    cl, 1
0x18000746c  jz      loc_1800075A4
0x180007472  mov     rax, rdx
0x180007475  and     eax, 1
0x180007478  cmp     rax, rdx
0x18000747b  jnz     loc_1800075A4
0x180007481  lea     rax, aOnecoreXboxGam_46; "onecore\\xbox\\gameinput\\client\\gamei"...
0x180007488  mov     [rbp+arg_8], ebx
0x18000748b  mov     [rbp+var_10], rax
0x18000748f  lea     rdx, unk_180059548
0x180007496  lea     rax, [rbp+arg_8]
0x18000749a  mov     [rbp+arg_10], 7Ah ; 'z'
0x1800074a1  mov     [rsp+50h+var_20], rax
0x1800074a6  lea     rax, [rbp+arg_10]
0x1800074aa  mov     [rsp+50h+var_28], rax
0x1800074af  lea     rax, [rbp+var_10]
0x1800074b3  mov     [rsp+50h+ppv], rax
0x1800074b8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800074bd  jmp     loc_1800075A4
0x1800074c2  mov     rcx, gs:60h
0x1800074cb  xor     edx, edx; Flags
0x1800074cd  mov     r8d, 160h; Size
0x1800074d3  mov     rcx, [rcx+30h]; HeapHandle
0x1800074d7  call    cs:__imp_RtlAllocateHeap
0x1800074de  nop     dword ptr [rax+rax+00h]
0x1800074e3  test    rax, rax
0x1800074e6  jz      loc_18000758D
0x1800074ec  mov     rdx, [rbp+arg_18]; struct IMMDeviceEnumerator *
0x1800074f0  mov     rcx, rax; this
0x1800074f3  call    ??0GameInputClient@@AEAA@PEAUIMMDeviceEnumerator@@@Z; GameInputClient::GameInputClient(IMMDeviceEnumerator *)
0x1800074f8  mov     cs:?s_singleton@GameInputClient@@0PEAV1@EA, rax; GameInputClient * GameInputClient::s_singleton
0x1800074ff  test    rax, rax
0x180007502  jz      loc_180007598
0x180007508  call    ?Initialize@GameInputClient@@AEAAJXZ; GameInputClient::Initialize(void)
0x18000750d  mov     ebx, eax
0x18000750f  test    eax, eax
0x180007511  js      short loc_180007564
0x180007513  mov     rax, cs:?s_singleton@GameInputClient@@0PEAV1@EA; GameInputClient * GameInputClient::s_singleton
0x18000751a  nop
0x18000751b  lock inc dword ptr [rax+8]
0x18000751f  nop
0x180007520  inc     cs:dword_1800696A0
0x180007526  call    GameInputClientDebugRefCountCheck
0x18000752b  nop
0x18000752c  mov     cs:?s_globalObjectCount@GameInputClient@@0U?$atomic@I@utl@@A, 1; utl::atomic<uint> GameInputClient::s_globalObjectCount
0x180007536  mfence
0x180007539  mov     rcx, [rbp+arg_18]
0x18000753d  mov     rax, cs:?s_singleton@GameInputClient@@0PEAV1@EA; GameInputClient * GameInputClient::s_singleton
0x180007544  mov     [rsi], rax
0x180007547  test    rcx, rcx
0x18000754a  jz      short loc_180007560
0x18000754c  mov     rax, [rcx]
0x18000754f  mov     rax, [rax+10h]
0x180007553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007558  mov     [rbp+arg_18], 0
0x180007560  xor     ebx, ebx
0x180007562  jmp     short loc_1800075C1
0x180007564  mov     rdi, cs:?s_singleton@GameInputClient@@0PEAV1@EA; GameInputClient * GameInputClient::s_singleton
0x18000756b  test    rdi, rdi
0x18000756e  jz      short loc_180007580
0x180007570  mov     rcx, rdi; this
0x180007573  call    ??1GameInputClient@@EEAA@XZ; GameInputClient::~GameInputClient(void)
0x180007578  mov     rcx, rdi; P
0x18000757b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007580  mov     cs:?s_singleton@GameInputClient@@0PEAV1@EA, 0; GameInputClient * GameInputClient::s_singleton
0x18000758b  jmp     short loc_18000759D
0x18000758d  mov     cs:?s_singleton@GameInputClient@@0PEAV1@EA, 0; GameInputClient * GameInputClient::s_singleton
0x180007598  mov     ebx, 8007000Eh
0x18000759d  mov     qword ptr [rsi], 0
0x1800075a4  mov     rcx, [rbp+arg_18]
0x1800075a8  test    rcx, rcx
0x1800075ab  jz      short loc_1800075C1
0x1800075ad  mov     rax, [rcx]
0x1800075b0  mov     rax, [rax+10h]
0x1800075b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075b9  mov     [rbp+arg_18], 0
0x1800075c1  lea     rcx, ?s_singletonLock@GameInputClient@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800075c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800075cf  nop     dword ptr [rax+rax+00h]
0x1800075d4  mov     eax, ebx
0x1800075d6  mov     rbx, [rsp+50h+arg_0]
0x1800075db  add     rsp, 50h
0x1800075df  pop     rdi
0x1800075e0  pop     rsi
0x1800075e1  pop     rbp
0x1800075e2  retn
0x1800075e4  mov     edx, 0CEh
0x1800075e9  mov     ecx, 80004004h
0x1800075ee  call    GameInputFailFast
```
