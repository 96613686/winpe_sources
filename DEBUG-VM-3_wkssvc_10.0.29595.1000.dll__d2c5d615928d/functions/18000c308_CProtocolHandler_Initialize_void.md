# CProtocolHandler::Initialize(void)

- ea: `0x18000c308`
- end: `0x18000c45c`
- name: `?Initialize@CProtocolHandler@@QEAAKXZ`
- size: `340`
- prototype: `unsigned int __fastcall(CProtocolHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000beb4`

## callees

- `0x18000b97c`
- `0x18000c308`
- `0x18000c464`
- `0x18002055c`
- `0x180022b7c`
- `0x1800328d4`
- `0x18003295c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3f7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000c376`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000c376`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c38d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c38d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c41e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c41e`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000c3e8`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000c3e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall CProtocolHandler::Initialize(CProtocolHandler *this)
{
  CProtocolHandler *v1; // rdi
  unsigned int v2; // eax
  HANDLE EventW; // rax
  unsigned int result; // eax
  HANDLE IoCompletionPort; // rax
  HANDLE Thread; // rax
  struct _RTL_CRITICAL_SECTION *v7; // [rsp+40h] [rbp+8h]
  _OWORD *v8; // [rsp+40h] [rbp+8h]

  v1 = WitnessProtocolHandler;
  v2 = CProtocolHandler::ConfigureRegValue(WitnessProtocolHandler);
  if ( v2
    && WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 24, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v2);
  }
  v7 = (struct _RTL_CRITICAL_SECTION *)operator new(0x28u);
  InitializeCriticalSection(v7);
  *((_QWORD *)v1 + 10) = v7;
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)v1 + 17) = EventW;
  if ( !EventW )
    return 1450;
  v8 = operator new(0x68u);
  *(_QWORD *)v8 = 0;
  v8[5] = 0;
  *((_QWORD *)v8 + 12) = 0;
  *((_QWORD *)v1 + 7) = v8;
  result = CThreadPool::InitializeThreadPool((CThreadPool *)v8);
  if ( !result )
  {
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
    *((_QWORD *)v1 + 8) = IoCompletionPort;
    if ( !IoCompletionPort )
      return GetLastError();
    Thread = CreateThread(0, 0, StartIOProcessing, v1, 0, 0);
    *((_QWORD *)v1 + 9) = Thread;
    if ( Thread == (HANDLE)-1LL )
    {
      return GetLastError();
    }
    else
    {
      result = WitnessOpenRedirector((void **)v1 + 11);
      if ( !result )
      {
        result = CProtocolHandler::GetComputerInformation(v1);
        if ( !result )
          *((_DWORD *)v1 + 32) = 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c308  mov     [rsp+arg_8], rbx
0x18000c30d  mov     [rsp+arg_0], rcx
0x18000c312  push    rdi
0x18000c313  sub     rsp, 30h
0x18000c317  mov     rdi, cs:?WitnessProtocolHandler@@3PEAVCProtocolHandler@@EA; CProtocolHandler * WitnessProtocolHandler
0x18000c31e  mov     rcx, rdi; this
0x18000c321  call    ?ConfigureRegValue@CProtocolHandler@@AEAAKXZ; CProtocolHandler::ConfigureRegValue(void)
0x18000c326  test    eax, eax
0x18000c328  jz      short loc_18000C361
0x18000c32a  lea     rdx, WPP_witness_GLOBAL_Control
0x18000c331  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c338  cmp     rcx, rdx
0x18000c33b  jz      short loc_18000C361
0x18000c33d  test    byte ptr [rcx+1Ch], 1
0x18000c341  jz      short loc_18000C361
0x18000c343  cmp     byte ptr [rcx+19h], 1
0x18000c347  jb      short loc_18000C361
0x18000c349  mov     edx, 18h
0x18000c34e  mov     r9d, eax
0x18000c351  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18000c358  mov     rcx, [rcx+10h]
0x18000c35c  call    WPP_SF_d
0x18000c361  mov     ecx, 28h ; '('; Size
0x18000c366  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c36b  mov     rbx, rax
0x18000c36e  mov     [rsp+38h+arg_0], rax
0x18000c373  mov     rcx, rax; lpCriticalSection
0x18000c376  call    cs:__imp_InitializeCriticalSection
0x18000c37c  nop
0x18000c37d  mov     [rdi+50h], rbx
0x18000c381  xor     r9d, r9d; lpName
0x18000c384  lea     edx, [r9+1]; bManualReset
0x18000c388  xor     ecx, ecx; lpEventAttributes
0x18000c38a  mov     r8d, edx; bInitialState
0x18000c38d  call    cs:__imp_CreateEventW
0x18000c393  mov     [rdi+88h], rax
0x18000c39a  test    rax, rax
0x18000c39d  jnz     short loc_18000C3A9
0x18000c39f  mov     eax, 5AAh
0x18000c3a4  jmp     loc_18000C451
0x18000c3a9  mov     ecx, 68h ; 'h'; Size
0x18000c3ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c3b3  mov     [rsp+38h+arg_0], rax
0x18000c3b8  mov     qword ptr [rax], 0
0x18000c3bf  xorps   xmm0, xmm0
0x18000c3c2  xor     ecx, ecx
0x18000c3c4  movups  xmmword ptr [rax+50h], xmm0
0x18000c3c8  mov     [rax+60h], rcx
0x18000c3cc  mov     [rdi+38h], rax
0x18000c3d0  mov     rcx, rax; this
0x18000c3d3  call    ?InitializeThreadPool@CThreadPool@@QEAAKXZ; CThreadPool::InitializeThreadPool(void)
0x18000c3d8  test    eax, eax
0x18000c3da  jnz     short loc_18000C451
0x18000c3dc  xor     r9d, r9d; NumberOfConcurrentThreads
0x18000c3df  xor     r8d, r8d; CompletionKey
0x18000c3e2  xor     edx, edx; ExistingCompletionPort
0x18000c3e4  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18000c3e8  call    cs:__imp_CreateIoCompletionPort
0x18000c3ee  mov     [rdi+40h], rax
0x18000c3f2  test    rax, rax
0x18000c3f5  jnz     short loc_18000C3FF
0x18000c3f7  call    cs:__imp_GetLastError
0x18000c3fd  jmp     short loc_18000C451
0x18000c3ff  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000c408  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18000c410  mov     r9, rdi; lpParameter
0x18000c413  lea     r8, ?StartIOProcessing@@YAKPEAX@Z; lpStartAddress
0x18000c41a  xor     edx, edx; dwStackSize
0x18000c41c  xor     ecx, ecx; lpThreadAttributes
0x18000c41e  call    cs:__imp_CreateThread
0x18000c424  mov     [rdi+48h], rax
0x18000c428  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c42c  jz      short loc_18000C3F7
0x18000c42e  lea     rcx, [rdi+58h]; void **
0x18000c432  call    ?WitnessOpenRedirector@@YAKPEAPEAX@Z; WitnessOpenRedirector(void * *)
0x18000c437  test    eax, eax
0x18000c439  jnz     short loc_18000C451
0x18000c43b  mov     rcx, rdi; this
0x18000c43e  call    ?GetComputerInformation@CProtocolHandler@@QEAAKXZ; CProtocolHandler::GetComputerInformation(void)
0x18000c443  test    eax, eax
0x18000c445  jnz     short loc_18000C451
0x18000c447  mov     dword ptr [rdi+80h], 1
0x18000c451  mov     rbx, [rsp+38h+arg_8]
0x18000c456  add     rsp, 30h
0x18000c45a  pop     rdi
0x18000c45b  retn
```
