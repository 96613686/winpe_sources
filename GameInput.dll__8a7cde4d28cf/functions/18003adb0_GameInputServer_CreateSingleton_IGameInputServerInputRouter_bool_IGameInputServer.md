# GameInputServer::CreateSingleton(IGameInputServerInputRouter *,bool,IGameInputServer * *)

- ea: `0x18003adb0`
- end: `0x18003b11a`
- name: `?CreateSingleton@GameInputServer@@SAJPEAUIGameInputServerInputRouter@@_NPEAPEAUIGameInputServer@@@Z`
- size: `874`
- prototype: `__int64 __fastcall(struct IGameInputServerInputRouter *, bool, struct IGameInputServer **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18003ac90`
- `0x18003b120`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x18000d68c`
- `0x18002cf1c`
- `0x18002d6b0`
- `0x18003adb0`
- `0x18003bcd8`
- `0x1800496fc`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003aed1`
- `ntdll!RtlAllocateHeap` at `0x18003aed1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003add4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003add4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b068`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b0e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b068`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b0e7`

## pseudocode

```c
__int64 __fastcall GameInputServer::CreateSingleton(
        int (__fastcall ***a1)(struct IGameInputServerInputRouter *, GUID *, const char **),
        char a2,
        struct IGameInputServer **a3)
{
  struct RouterBase *v5; // rdi
  int (__fastcall **v6)(struct IGameInputServerInputRouter *, GUID *, const char **); // rax
  struct RouterBase *v7; // rcx
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  GameInputServer *Heap; // rax
  char v13; // r8
  GameInputServer *v14; // rcx
  int v15; // esi
  PVOID v16; // rax
  __int64 v17; // rdx
  int v18; // esi
  __int64 v19; // r8
  __int64 v20; // r9
  _QWORD *v21; // rsi
  struct RouterBase *v22; // rcx
  PVOID v24; // r14
  const struct std::nothrow_t *v25; // rdx
  struct RouterBase *v26; // [rsp+40h] [rbp-10h] BYREF
  const char *v27; // [rsp+48h] [rbp-8h] BYREF
  int v28; // [rsp+88h] [rbp+38h] BYREF
  int v29; // [rsp+98h] [rbp+48h] BYREF

  LOBYTE(v28) = a2;
  AcquireSRWLockExclusive(&GameInputServer::s_singletonLock);
  if ( GameInputServer::s_singleton )
  {
    GameInputFailFast(2147549183LL, 138);
    JUMPOUT(0x18003B119LL);
  }
  v5 = 0;
  v26 = 0;
  if ( a1 )
  {
    v6 = *a1;
    v7 = (struct RouterBase *)a1;
LABEL_13:
    ((void (__fastcall *)(struct RouterBase *))v6[1])(v7);
    goto LABEL_14;
  }
  v9 = CreateRouter(&v26);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v10 = qword_180069018;
      v8 = 1024;
      if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v28 = v9;
        v27 = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
        v29 = 148;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned __int8 *)word_1800625AA,
          qword_180069018,
          v11,
          (__int64 **)&v27,
          (__int64)&v29,
          (__int64)&v28);
      }
    }
    if ( v26 )
      (*(void (__fastcall **)(struct RouterBase *, __int64, __int64))(*(_QWORD *)v26 + 16LL))(v26, v8, v10);
    goto LABEL_36;
  }
  v5 = v26;
  a1 = 0;
  if ( v26 )
  {
    v6 = *(int (__fastcall ***)(struct IGameInputServerInputRouter *, GUID *, const char **))v26;
    a1 = (int (__fastcall ***)(struct IGameInputServerInputRouter *, GUID *, const char **))v26;
    v7 = v26;
    goto LABEL_13;
  }
LABEL_14:
  Heap = (GameInputServer *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x128u);
  if ( !Heap )
  {
    GameInputServer::s_singleton = 0;
    goto LABEL_41;
  }
  GameInputServer::s_singleton = GameInputServer::GameInputServer(Heap, a1, v13);
  if ( !GameInputServer::s_singleton )
  {
LABEL_41:
    v15 = -2147024882;
    goto LABEL_42;
  }
  v15 = GameInputServer::Initialize(v14);
  if ( v15 >= 0 )
  {
    *((_DWORD *)GameInputServer::s_singleton + 2) = 1;
    _mm_mfence();
    v16 = GameInputServer::s_singleton;
    *a3 = (struct IGameInputServer *)GameInputServer::s_singleton;
    if ( v5 )
    {
      *((_QWORD *)v5 + 3) = v16;
      v18 = (*(__int64 (__fastcall **)(struct RouterBase *, _QWORD))(*(_QWORD *)v5 + 104LL))(v5, 0);
      if ( v18 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v19 = qword_180069018;
          v17 = 1024;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v28 = v18;
            v27 = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
            v29 = 169;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              qword_180069010,
              (unsigned __int8 *)byte_1800609C9,
              qword_180069018,
              v20,
              (__int64 **)&v27,
              (__int64)&v29,
              (__int64)&v28);
          }
        }
        if ( a1 )
          (*a1)[2]((struct IGameInputServerInputRouter *)a1, (GUID *)v17, (const char **)v19);
        (*(void (__fastcall **)(struct RouterBase *, __int64, __int64))(*(_QWORD *)v5 + 16LL))(v5, v17, v19);
        v9 = v18;
LABEL_36:
        ReleaseSRWLockExclusive(&GameInputServer::s_singletonLock);
        return (unsigned int)v9;
      }
      (*(void (__fastcall **)(struct RouterBase *))(*(_QWORD *)v5 + 8LL))(v5);
      v21 = GameInputServer::s_singleton;
      v22 = (struct RouterBase *)*((_QWORD *)GameInputServer::s_singleton + 4);
      if ( v22 != v5 )
      {
        if ( v22 )
          (*(void (__fastcall **)(struct RouterBase *))(*(_QWORD *)v22 + 16LL))(v22);
        v21[4] = v5;
        (*(void (__fastcall **)(struct RouterBase *))(*(_QWORD *)v5 + 8LL))(v5);
      }
      (*(void (__fastcall **)(struct RouterBase *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    if ( a1 )
      ((void (__fastcall *)(int (__fastcall ***)(struct IGameInputServerInputRouter *, GUID *, const char **)))(*a1)[2])(a1);
    if ( v5 )
      (*(void (__fastcall **)(struct RouterBase *))(*(_QWORD *)v5 + 16LL))(v5);
    v9 = 0;
    goto LABEL_36;
  }
  v24 = GameInputServer::s_singleton;
  if ( GameInputServer::s_singleton )
  {
    GameInputServer::~GameInputServer((ULONG_PTR)GameInputServer::s_singleton);
    operator delete(v24, v25);
  }
  GameInputServer::s_singleton = 0;
LABEL_42:
  *a3 = 0;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(struct IGameInputServerInputRouter *, GUID *, const char **)))(*a1)[2])(a1);
  if ( v5 )
    (*(void (__fastcall **)(struct RouterBase *))(*(_QWORD *)v5 + 16LL))(v5);
  ReleaseSRWLockExclusive(&GameInputServer::s_singletonLock);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18003adb0  mov     [rsp-28h+arg_0], rbx
0x18003adb5  mov     byte ptr [rsp-28h+arg_8], dl
0x18003adb9  push    rbp
0x18003adba  push    rsi
0x18003adbb  push    rdi
0x18003adbc  push    r14
0x18003adbe  push    r15
0x18003adc0  mov     rbp, rsp
0x18003adc3  sub     rsp, 50h
0x18003adc7  mov     rbx, rcx
0x18003adca  mov     r15, r8
0x18003adcd  lea     rcx, ?s_singletonLock@GameInputServer@@0U_RTL_SRWLOCK@@A; SRWLock
0x18003add4  call    cs:__imp_AcquireSRWLockExclusive
0x18003addb  nop     dword ptr [rax+rax+00h]
0x18003ade0  cmp     cs:?s_singleton@GameInputServer@@0PEAV1@EA, 0; GameInputServer * GameInputServer::s_singleton
0x18003ade8  jnz     loc_18003B10A
0x18003adee  xor     edi, edi
0x18003adf0  mov     [rbp+var_10], rdi
0x18003adf4  test    rbx, rbx
0x18003adf7  jz      short loc_18003AE04
0x18003adf9  mov     rax, [rbx]
0x18003adfc  mov     rcx, rbx
0x18003adff  jmp     loc_18003AEB3
0x18003ae04  lea     rcx, [rbp+var_10]; struct RouterBase **
0x18003ae08  call    ?CreateRouter@@YAJPEAPEAVRouterBase@@@Z; CreateRouter(RouterBase * *)
0x18003ae0d  mov     ebx, eax
0x18003ae0f  test    eax, eax
0x18003ae11  jns     loc_18003AE9F
0x18003ae17  mov     ecx, cs:dword_180069000
0x18003ae1d  cmp     ecx, 2
0x18003ae20  jbe     short loc_18003AE81
0x18003ae22  mov     r8, cs:qword_180069018
0x18003ae29  mov     edx, 400h
0x18003ae2e  mov     rcx, cs:qword_180069010
0x18003ae35  test    rdx, rcx
0x18003ae38  jz      short loc_18003AE81
0x18003ae3a  mov     rax, r8
0x18003ae3d  and     rax, rdx
0x18003ae40  cmp     rax, r8
0x18003ae43  jnz     short loc_18003AE81
0x18003ae45  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x18003ae4c  mov     [rbp+arg_8], ebx
0x18003ae4f  mov     [rbp+var_8], rax
0x18003ae53  lea     rdx, word_1800625AA
0x18003ae5a  lea     rax, [rbp+arg_8]
0x18003ae5e  mov     [rbp+arg_18], 94h
0x18003ae65  mov     [rsp+50h+var_20], rax
0x18003ae6a  lea     rax, [rbp+arg_18]
0x18003ae6e  mov     [rsp+50h+var_28], rax
0x18003ae73  lea     rax, [rbp+var_8]
0x18003ae77  mov     [rsp+50h+var_30], rax
0x18003ae7c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003ae81  mov     rcx, [rbp+var_10]
0x18003ae85  test    rcx, rcx
0x18003ae88  jz      loc_18003B061
0x18003ae8e  mov     rax, [rcx]
0x18003ae91  mov     rax, [rax+10h]
0x18003ae95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae9a  jmp     loc_18003B061
0x18003ae9f  mov     rdi, [rbp+var_10]
0x18003aea3  xor     ebx, ebx
0x18003aea5  test    rdi, rdi
0x18003aea8  jz      short loc_18003AEBC
0x18003aeaa  mov     rax, [rdi]
0x18003aead  mov     rbx, rdi
0x18003aeb0  mov     rcx, rdi
0x18003aeb3  mov     rax, [rax+8]
0x18003aeb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aebc  mov     rcx, gs:60h
0x18003aec5  xor     edx, edx; Flags
0x18003aec7  mov     r8d, 128h; Size
0x18003aecd  mov     rcx, [rcx+30h]; HeapHandle
0x18003aed1  call    cs:__imp_RtlAllocateHeap
0x18003aed8  nop     dword ptr [rax+rax+00h]
0x18003aedd  test    rax, rax
0x18003aee0  jz      loc_18003B0A1
0x18003aee6  mov     rdx, rbx; struct IGameInputServerInputRouter *
0x18003aee9  mov     rcx, rax; this
0x18003aeec  call    ??0GameInputServer@@AEAA@PEAUIGameInputServerInputRouter@@_N@Z; GameInputServer::GameInputServer(IGameInputServerInputRouter *,bool)
0x18003aef1  mov     cs:?s_singleton@GameInputServer@@0PEAV1@EA, rax; GameInputServer * GameInputServer::s_singleton
0x18003aef8  test    rax, rax
0x18003aefb  jz      loc_18003B0AC
0x18003af01  call    ?Initialize@GameInputServer@@AEAAJXZ; GameInputServer::Initialize(void)
0x18003af06  mov     esi, eax
0x18003af08  test    eax, eax
0x18003af0a  js      loc_18003B078
0x18003af10  mov     rax, cs:?s_singleton@GameInputServer@@0PEAV1@EA; GameInputServer * GameInputServer::s_singleton
0x18003af17  nop
0x18003af18  mov     dword ptr [rax+8], 1
0x18003af1f  mfence
0x18003af22  mov     rax, cs:?s_singleton@GameInputServer@@0PEAV1@EA; GameInputServer * GameInputServer::s_singleton
0x18003af29  mov     [r15], rax
0x18003af2c  test    rdi, rdi
0x18003af2f  jz      loc_18003B037
0x18003af35  mov     [rdi+18h], rax
0x18003af39  xor     edx, edx
0x18003af3b  mov     rax, [rdi]
0x18003af3e  mov     rcx, rdi
0x18003af41  mov     rax, [rax+68h]
0x18003af45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af4a  mov     esi, eax
0x18003af4c  test    eax, eax
0x18003af4e  jns     loc_18003AFE5
0x18003af54  mov     ecx, cs:dword_180069000
0x18003af5a  cmp     ecx, 2
0x18003af5d  jbe     short loc_18003AFBE
0x18003af5f  mov     r8, cs:qword_180069018
0x18003af66  mov     edx, 400h
0x18003af6b  mov     rcx, cs:qword_180069010
0x18003af72  test    rdx, rcx
0x18003af75  jz      short loc_18003AFBE
0x18003af77  mov     rax, r8
0x18003af7a  and     rax, rdx
0x18003af7d  cmp     rax, r8
0x18003af80  jnz     short loc_18003AFBE
0x18003af82  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x18003af89  mov     [rbp+arg_8], esi
0x18003af8c  mov     [rbp+var_8], rax
0x18003af90  lea     rdx, byte_1800609C9
0x18003af97  lea     rax, [rbp+arg_8]
0x18003af9b  mov     [rbp+arg_18], 0A9h
0x18003afa2  mov     [rsp+50h+var_20], rax
0x18003afa7  lea     rax, [rbp+arg_18]
0x18003afab  mov     [rsp+50h+var_28], rax
0x18003afb0  lea     rax, [rbp+var_8]
0x18003afb4  mov     [rsp+50h+var_30], rax
0x18003afb9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003afbe  test    rbx, rbx
0x18003afc1  jz      short loc_18003AFD2
0x18003afc3  mov     rax, [rbx]
0x18003afc6  mov     rcx, rbx
0x18003afc9  mov     rax, [rax+10h]
0x18003afcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afd2  mov     rax, [rdi]
0x18003afd5  mov     rcx, rdi
0x18003afd8  mov     rax, [rax+10h]
0x18003afdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afe1  mov     ebx, esi
0x18003afe3  jmp     short loc_18003B061
0x18003afe5  mov     rax, [rdi]
0x18003afe8  mov     rcx, rdi
0x18003afeb  mov     rax, [rax+8]
0x18003afef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aff4  mov     rsi, cs:?s_singleton@GameInputServer@@0PEAV1@EA; GameInputServer * GameInputServer::s_singleton
0x18003affb  mov     rcx, [rsi+20h]
0x18003afff  cmp     rcx, rdi
0x18003b002  jz      short loc_18003B028
0x18003b004  test    rcx, rcx
0x18003b007  jz      short loc_18003B015
0x18003b009  mov     rax, [rcx]
0x18003b00c  mov     rax, [rax+10h]
0x18003b010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b015  mov     [rsi+20h], rdi
0x18003b019  mov     rcx, rdi
0x18003b01c  mov     rax, [rdi]
0x18003b01f  mov     rax, [rax+8]
0x18003b023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b028  mov     rax, [rdi]
0x18003b02b  mov     rcx, rdi
0x18003b02e  mov     rax, [rax+10h]
0x18003b032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b037  test    rbx, rbx
0x18003b03a  jz      short loc_18003B04B
0x18003b03c  mov     rax, [rbx]
0x18003b03f  mov     rcx, rbx
0x18003b042  mov     rax, [rax+10h]
0x18003b046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b04b  test    rdi, rdi
0x18003b04e  jz      short loc_18003B05F
0x18003b050  mov     rax, [rdi]
0x18003b053  mov     rcx, rdi
0x18003b056  mov     rax, [rax+10h]
0x18003b05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b05f  xor     ebx, ebx
0x18003b061  lea     rcx, ?s_singletonLock@GameInputServer@@0U_RTL_SRWLOCK@@A; SRWLock
0x18003b068  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b06f  nop     dword ptr [rax+rax+00h]
0x18003b074  mov     eax, ebx
0x18003b076  jmp     short loc_18003B0F5
0x18003b078  mov     r14, cs:?s_singleton@GameInputServer@@0PEAV1@EA; GameInputServer * GameInputServer::s_singleton
0x18003b07f  test    r14, r14
0x18003b082  jz      short loc_18003B094
0x18003b084  mov     rcx, r14; dwData
0x18003b087  call    ??1GameInputServer@@AEAA@XZ; GameInputServer::~GameInputServer(void)
0x18003b08c  mov     rcx, r14; P
0x18003b08f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003b094  mov     cs:?s_singleton@GameInputServer@@0PEAV1@EA, 0; GameInputServer * GameInputServer::s_singleton
0x18003b09f  jmp     short loc_18003B0B1
0x18003b0a1  mov     cs:?s_singleton@GameInputServer@@0PEAV1@EA, 0; GameInputServer * GameInputServer::s_singleton
0x18003b0ac  mov     esi, 8007000Eh
0x18003b0b1  mov     qword ptr [r15], 0
0x18003b0b8  test    rbx, rbx
0x18003b0bb  jz      short loc_18003B0CC
0x18003b0bd  mov     rax, [rbx]
0x18003b0c0  mov     rcx, rbx
0x18003b0c3  mov     rax, [rax+10h]
0x18003b0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0cc  test    rdi, rdi
0x18003b0cf  jz      short loc_18003B0E0
0x18003b0d1  mov     rax, [rdi]
0x18003b0d4  mov     rcx, rdi
0x18003b0d7  mov     rax, [rax+10h]
0x18003b0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0e0  lea     rcx, ?s_singletonLock@GameInputServer@@0U_RTL_SRWLOCK@@A; SRWLock
0x18003b0e7  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b0ee  nop     dword ptr [rax+rax+00h]
0x18003b0f3  mov     eax, esi
0x18003b0f5  mov     rbx, [rsp+50h+arg_0]
0x18003b0fd  add     rsp, 50h
0x18003b101  pop     r15
0x18003b103  pop     r14
0x18003b105  pop     rdi
0x18003b106  pop     rsi
0x18003b107  pop     rbp
0x18003b108  retn
0x18003b10a  mov     edx, 8Ah
0x18003b10f  mov     ecx, 8000FFFFh
0x18003b114  call    GameInputFailFast
```
