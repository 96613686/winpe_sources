# GameInputServerManager::LoadGameInput(void)

- ea: `0x14000199c`
- end: `0x140001ce3`
- name: `?LoadGameInput@GameInputServerManager@@AEAAJXZ`
- size: `839`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION **this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140001cec`

## callees

- `0x140001008`
- `0x1400017c8`
- `0x14000199c`
- `0x14000652c`
- `0x140006750`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400019c5`
- `ntdll!RtlAllocateHeap` at `0x140001a2c`
- `ntdll!RtlAllocateHeap` at `0x1400019c5`
- `ntdll!RtlAllocateHeap` at `0x140001a2c`
- `ntdll!RtlFreeHeap` at `0x140001a88`
- `ntdll!RtlFreeHeap` at `0x140001bac`
- `ntdll!RtlFreeHeap` at `0x140001be1`
- `ntdll!RtlFreeHeap` at `0x140001a88`
- `ntdll!RtlFreeHeap` at `0x140001bac`
- `ntdll!RtlFreeHeap` at `0x140001be1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140001a01`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140001a64`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140001a01`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140001a64`

## pseudocode

```c
__int64 __fastcall GameInputServerManager::LoadGameInput(struct _RTL_CRITICAL_SECTION **this)
{
  struct _RTL_CRITICAL_SECTION *Heap; // rax
  const WCHAR *v3; // r8
  __int64 v4; // r9
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  const WCHAR *v6; // r8
  struct _RTL_CRITICAL_SECTION *v7; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  const char **v9; // rcx
  char *v10; // rdx
  int Module; // edi
  __int64 v12; // r8
  __int64 v13; // r9
  struct _RTL_CRITICAL_SECTION *v15; // rdi
  int Server; // ebx
  __int64 v17; // r9
  int v18; // [rsp+68h] [rbp+28h] BYREF
  int v19; // [rsp+70h] [rbp+30h] BYREF
  const char *v20; // [rsp+78h] [rbp+38h] BYREF

  Heap = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x50u);
  v5 = Heap;
  if ( !Heap )
  {
    if ( (unsigned int)dword_14000E000 <= 2
      || (qword_14000E010 & 0x800) == 0
      || (qword_14000E018 & 0x800) != qword_14000E018 )
    {
      return 2147942414LL;
    }
    v19 = 36;
    v20 = "onecore\\xbox\\gameinput\\published\\svc\\gameinputservermanager.cpp";
    v10 = byte_14000A465;
    v9 = &v20;
    goto LABEL_32;
  }
  LODWORD(Heap->DebugInfo) = 0;
  *(_QWORD *)&Heap->LockCount = 0;
  Heap->OwningThread = 0;
  Heap->LockSemaphore = 0;
  Heap->SpinCount = 0;
  InitializeCriticalSection(Heap + 1);
  if ( (unsigned int)GameInputModule::LoadModule(v5, 2, v6) )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x50u);
    v8 = v7;
    if ( v7 )
    {
      LODWORD(v7->DebugInfo) = 0;
      *(_QWORD *)&v7->LockCount = 0;
      v7->OwningThread = 0;
      v7->LockSemaphore = 0;
      v7->SpinCount = 0;
      InitializeCriticalSection(v7 + 1);
    }
    else
    {
      v8 = 0;
    }
    GameInputModule::~GameInputModule(v5);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    if ( !v8 )
    {
      if ( (unsigned int)dword_14000E000 <= 2 )
        return 2147942414LL;
      v9 = (const char **)qword_14000E018;
      if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
        return 2147942414LL;
      v19 = 54;
      v20 = "onecore\\xbox\\gameinput\\published\\svc\\gameinputservermanager.cpp";
      v10 = byte_14000A415;
LABEL_32:
      v18 = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v9,
        (int)v10,
        (__int64)v3,
        v4,
        (__int64 **)&v20,
        (__int64)&v19,
        (__int64)&v18);
      return 2147942414LL;
    }
    Module = GameInputModule::LoadModule(v8, 1, v3);
    if ( Module == 1 )
      Module = -2147418113;
    if ( Module < 0 )
    {
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v18 = Module;
        v20 = "onecore\\xbox\\gameinput\\published\\svc\\gameinputservermanager.cpp";
        v19 = 63;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14000E018,
          (int)&unk_14000A3D8,
          v12,
          v13,
          (__int64 **)&v20,
          (__int64)&v19,
          (__int64)&v18);
      }
      GameInputModule::~GameInputModule(v8);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
      return (unsigned int)Module;
    }
  }
  else
  {
    v8 = v5;
  }
  v15 = *this;
  *this = v8;
  if ( v15 )
  {
    GameInputModule::~GameInputModule(v15);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  }
  Server = GameInputServerManager::CreateServer((GameInputServerManager *)this);
  if ( Server < 0
    && (unsigned int)dword_14000E000 > 2
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    v18 = Server;
    v20 = "onecore\\xbox\\gameinput\\published\\svc\\gameinputservermanager.cpp";
    v19 = 68;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_14000E010,
      (int)byte_14000A39B,
      qword_14000E018,
      v17,
      (__int64 **)&v20,
      (__int64)&v19,
      (__int64)&v18);
  }
  return (unsigned int)Server;
}

```

## disassembly

```asm
0x14000199c  mov     [rsp-18h+arg_0], rbx
0x1400019a1  push    rbp
0x1400019a2  push    rsi
0x1400019a3  push    rdi
0x1400019a4  mov     rbp, rsp
0x1400019a7  sub     rsp, 40h
0x1400019ab  mov     rsi, rcx
0x1400019ae  mov     ebx, 50h ; 'P'
0x1400019b3  mov     rcx, gs:60h
0x1400019bc  mov     r8d, ebx; Size
0x1400019bf  xor     edx, edx; Flags
0x1400019c1  mov     rcx, [rcx+30h]; HeapHandle
0x1400019c5  call    cs:__imp_RtlAllocateHeap
0x1400019cb  mov     rdi, rax
0x1400019ce  test    rax, rax
0x1400019d1  jz      loc_140001C63
0x1400019d7  lea     rcx, [rax+28h]; lpCriticalSection
0x1400019db  mov     dword ptr [rax], 0
0x1400019e1  mov     qword ptr [rax+8], 0
0x1400019e9  mov     qword ptr [rax+10h], 0
0x1400019f1  mov     qword ptr [rax+18h], 0
0x1400019f9  mov     qword ptr [rax+20h], 0
0x140001a01  call    cs:__imp_InitializeCriticalSection
0x140001a07  lea     edx, [rbx-4Eh]
0x140001a0a  mov     rcx, rdi
0x140001a0d  call    ?LoadModule@GameInputModule@@AEAAJW4ModuleKind@1@AEBUGameInputVersion@@@Z; GameInputModule::LoadModule(GameInputModule::ModuleKind,GameInputVersion const &)
0x140001a12  test    eax, eax
0x140001a14  jz      loc_140001BB9
0x140001a1a  mov     rcx, gs:60h
0x140001a23  mov     r8d, ebx; Size
0x140001a26  xor     edx, edx; Flags
0x140001a28  mov     rcx, [rcx+30h]; HeapHandle
0x140001a2c  call    cs:__imp_RtlAllocateHeap
0x140001a32  mov     rbx, rax
0x140001a35  test    rax, rax
0x140001a38  jz      short loc_140001A6C
0x140001a3a  lea     rcx, [rax+28h]; lpCriticalSection
0x140001a3e  mov     dword ptr [rax], 0
0x140001a44  mov     qword ptr [rax+8], 0
0x140001a4c  mov     qword ptr [rax+10h], 0
0x140001a54  mov     qword ptr [rax+18h], 0
0x140001a5c  mov     qword ptr [rax+20h], 0
0x140001a64  call    cs:__imp_InitializeCriticalSection
0x140001a6a  jmp     short loc_140001A6E
0x140001a6c  xor     ebx, ebx
0x140001a6e  mov     rcx, rdi; this
0x140001a71  call    ??1GameInputModule@@QEAA@XZ; GameInputModule::~GameInputModule(void)
0x140001a76  mov     rcx, gs:60h
0x140001a7f  mov     r8, rdi; P
0x140001a82  xor     edx, edx; Flags
0x140001a84  mov     rcx, [rcx+30h]; HeapHandle
0x140001a88  call    cs:__imp_RtlFreeHeap
0x140001a8e  test    rbx, rbx
0x140001a91  jnz     short loc_140001B06
0x140001a93  mov     eax, cs:dword_14000E000
0x140001a99  cmp     eax, 2
0x140001a9c  jbe     loc_140001CD1
0x140001aa2  mov     rcx, cs:qword_14000E018
0x140001aa9  mov     edx, 800h
0x140001aae  mov     rax, cs:qword_14000E010
0x140001ab5  test    rdx, rax
0x140001ab8  jz      loc_140001CD1
0x140001abe  mov     rax, rcx
0x140001ac1  and     rax, rdx
0x140001ac4  cmp     rax, rcx
0x140001ac7  jnz     loc_140001CD1
0x140001acd  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\published\\sv"...
0x140001ad4  mov     [rbp+arg_10], 36h ; '6'
0x140001adb  mov     [rbp+arg_18], rax
0x140001adf  lea     rdx, byte_14000A415
0x140001ae6  lea     rax, [rbp+arg_8]
0x140001aea  mov     [rsp+40h+var_10], rax
0x140001aef  lea     rax, [rbp+arg_10]
0x140001af3  mov     [rsp+40h+var_18], rax
0x140001af8  lea     rax, [rbp+arg_18]
0x140001afc  mov     [rsp+40h+var_20], rax
0x140001b01  jmp     loc_140001CC5
0x140001b06  mov     edx, 1
0x140001b0b  mov     rcx, rbx
0x140001b0e  call    ?LoadModule@GameInputModule@@AEAAJW4ModuleKind@1@AEBUGameInputVersion@@@Z; GameInputModule::LoadModule(GameInputModule::ModuleKind,GameInputVersion const &)
0x140001b13  mov     edi, eax
0x140001b15  mov     eax, 8000FFFFh
0x140001b1a  cmp     edi, 1
0x140001b1d  cmovz   edi, eax
0x140001b20  test    edi, edi
0x140001b22  jns     loc_140001BBC
0x140001b28  mov     eax, cs:dword_14000E000
0x140001b2e  cmp     eax, 2
0x140001b31  jbe     short loc_140001B92
0x140001b33  mov     rcx, cs:qword_14000E018
0x140001b3a  mov     edx, 800h
0x140001b3f  mov     rax, cs:qword_14000E010
0x140001b46  test    rdx, rax
0x140001b49  jz      short loc_140001B92
0x140001b4b  mov     rax, rcx
0x140001b4e  and     rax, rdx
0x140001b51  cmp     rax, rcx
0x140001b54  jnz     short loc_140001B92
0x140001b56  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\published\\sv"...
0x140001b5d  mov     [rbp+arg_8], edi
0x140001b60  mov     [rbp+arg_18], rax
0x140001b64  lea     rdx, unk_14000A3D8
0x140001b6b  lea     rax, [rbp+arg_8]
0x140001b6f  mov     [rbp+arg_10], 3Fh ; '?'
0x140001b76  mov     [rsp+40h+var_10], rax
0x140001b7b  lea     rax, [rbp+arg_10]
0x140001b7f  mov     [rsp+40h+var_18], rax
0x140001b84  lea     rax, [rbp+arg_18]
0x140001b88  mov     [rsp+40h+var_20], rax
0x140001b8d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140001b92  mov     rcx, rbx; this
0x140001b95  call    ??1GameInputModule@@QEAA@XZ; GameInputModule::~GameInputModule(void)
0x140001b9a  mov     rcx, gs:60h
0x140001ba3  mov     r8, rbx; P
0x140001ba6  xor     edx, edx; Flags
0x140001ba8  mov     rcx, [rcx+30h]; HeapHandle
0x140001bac  call    cs:__imp_RtlFreeHeap
0x140001bb2  mov     eax, edi
0x140001bb4  jmp     loc_140001CD6
0x140001bb9  mov     rbx, rdi
0x140001bbc  mov     rdi, [rsi]
0x140001bbf  mov     [rsi], rbx
0x140001bc2  test    rdi, rdi
0x140001bc5  jz      short loc_140001BE7
0x140001bc7  mov     rcx, rdi; this
0x140001bca  call    ??1GameInputModule@@QEAA@XZ; GameInputModule::~GameInputModule(void)
0x140001bcf  mov     rcx, gs:60h
0x140001bd8  mov     r8, rdi; P
0x140001bdb  xor     edx, edx; Flags
0x140001bdd  mov     rcx, [rcx+30h]; HeapHandle
0x140001be1  call    cs:__imp_RtlFreeHeap
0x140001be7  mov     rcx, rsi; this
0x140001bea  call    ?CreateServer@GameInputServerManager@@AEAAJXZ; GameInputServerManager::CreateServer(void)
0x140001bef  mov     ebx, eax
0x140001bf1  test    eax, eax
0x140001bf3  jns     short loc_140001C5F
0x140001bf5  mov     ecx, cs:dword_14000E000
0x140001bfb  cmp     ecx, 2
0x140001bfe  jbe     short loc_140001C5F
0x140001c00  mov     r8, cs:qword_14000E018
0x140001c07  mov     edx, 800h
0x140001c0c  mov     rcx, cs:qword_14000E010
0x140001c13  test    rdx, rcx
0x140001c16  jz      short loc_140001C5F
0x140001c18  mov     rax, r8
0x140001c1b  and     rax, rdx
0x140001c1e  cmp     rax, r8
0x140001c21  jnz     short loc_140001C5F
0x140001c23  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\published\\sv"...
0x140001c2a  mov     [rbp+arg_8], ebx
0x140001c2d  mov     [rbp+arg_18], rax
0x140001c31  lea     rdx, byte_14000A39B
0x140001c38  lea     rax, [rbp+arg_8]
0x140001c3c  mov     [rbp+arg_10], 44h ; 'D'
0x140001c43  mov     [rsp+40h+var_10], rax
0x140001c48  lea     rax, [rbp+arg_10]
0x140001c4c  mov     [rsp+40h+var_18], rax
0x140001c51  lea     rax, [rbp+arg_18]
0x140001c55  mov     [rsp+40h+var_20], rax
0x140001c5a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140001c5f  mov     eax, ebx
0x140001c61  jmp     short loc_140001CD6
0x140001c63  mov     eax, cs:dword_14000E000
0x140001c69  cmp     eax, 2
0x140001c6c  jbe     short loc_140001CD1
0x140001c6e  mov     rcx, cs:qword_14000E018
0x140001c75  mov     edx, 800h
0x140001c7a  mov     rax, cs:qword_14000E010
0x140001c81  test    rdx, rax
0x140001c84  jz      short loc_140001CD1
0x140001c86  mov     rax, rcx
0x140001c89  and     rax, rdx
0x140001c8c  cmp     rax, rcx
0x140001c8f  jnz     short loc_140001CD1
0x140001c91  lea     rcx, [rbp+arg_8]
0x140001c95  mov     [rbp+arg_10], 24h ; '$'
0x140001c9c  mov     [rsp+40h+var_10], rcx
0x140001ca1  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\published\\sv"...
0x140001ca8  lea     rcx, [rbp+arg_10]
0x140001cac  mov     [rbp+arg_18], rax
0x140001cb0  mov     [rsp+40h+var_18], rcx
0x140001cb5  lea     rdx, byte_14000A465
0x140001cbc  lea     rcx, [rbp+arg_18]
0x140001cc0  mov     [rsp+40h+var_20], rcx
0x140001cc5  mov     [rbp+arg_8], 8007000Eh
0x140001ccc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140001cd1  mov     eax, 8007000Eh
0x140001cd6  mov     rbx, [rsp+40h+arg_0]
0x140001cdb  add     rsp, 40h
0x140001cdf  pop     rdi
0x140001ce0  pop     rsi
0x140001ce1  pop     rbp
0x140001ce2  retn
```
