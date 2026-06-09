# GetManagedApps

- ea: `0x1800030c0`
- end: `0x180003365`
- name: `GetManagedApps`
- size: `677`
- prototype: `RPC_STATUS __fastcall(__int64, __int64, int, int, _OWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800030c0`
- `0x18001b1a0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000312e`
- `RPCRT4!RpcImpersonateClient` at `0x18000312e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000313d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000313d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000323b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000323b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003155`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000315f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000318d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000315f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000318d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003249`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000333b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000334a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000333b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000334a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003358`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003167`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003167`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000317f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000317f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000331c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000331c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003291`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800031ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003264`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800031ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003264`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003287`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003287`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800032db`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800032db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800031d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800031d4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000329a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000329a`

## pseudocode

```c
RPC_STATUS __fastcall GetManagedApps(__int64 a1, __int64 a2, int a3, int a4, _OWORD *a5)
{
  int v6; // r8d
  RPC_STATUS result; // eax
  DWORD LastError; // ebx
  HANDLE EventW; // rsi
  HANDLE CurrentThread; // rax
  CGPRPCServerBase *v11; // rdi
  HMODULE Library; // r15
  HANDLE Thread; // rdi
  DWORD v14; // eax
  CGPRPCServerBase *v15; // r14
  int v16; // eax
  void *TokenHandle; // [rsp+30h] [rbp-41h] BYREF
  HANDLE Handles[2]; // [rsp+38h] [rbp-39h] BYREF
  _QWORD Parameter[5]; // [rsp+48h] [rbp-29h] BYREF
  __int64 v20; // [rsp+70h] [rbp-1h]

  TokenHandle = 0;
  if ( !a5 )
    return 87;
  *a5 = 0;
  if ( a4 != 0x10000 )
    return 87;
  v6 = a3 - 1;
  if ( v6 )
  {
    if ( v6 != 1 || !a2 )
      return 87;
  }
  else if ( a2 )
  {
    return 87;
  }
  result = RpcImpersonateClient(0);
  LastError = result;
  if ( !result )
  {
    EventW = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
      LastError = GetLastError();
    RevertToSelf();
    if ( !LastError )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        v11 = CRPCServiceManager::_pSingletonManager;
        LastError = 1066;
        Library = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)CRPCServiceManager::_pSingletonManager + 88));
        if ( *((_DWORD *)v11 + 33) && *((_DWORD *)v11 + 34) < 0x10000u )
        {
          Library = LoadLibraryExW(*((LPCWSTR *)v11 + 9), 0, 0x800u);
          if ( Library )
          {
            ++*((_DWORD *)v11 + 34);
            LastError = 0;
          }
          else
          {
            LastError = GetLastError();
          }
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 88));
        if ( !LastError )
        {
          Parameter[2] = TokenHandle;
          v20 = 0;
          Parameter[0] = a2;
          Parameter[1] = a5;
          Parameter[3] = EventW;
          Parameter[4] = Library;
          Thread = CreateThread(0, 0, GetManagedAppsProc, Parameter, 0, 0);
          if ( Thread )
            goto LABEL_28;
          v14 = GetLastError();
          v15 = CRPCServiceManager::_pSingletonManager;
          LastError = v14;
          if ( !v14 )
            LastError = 14;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)CRPCServiceManager::_pSingletonManager + 88));
          --*((_DWORD *)v15 + 34);
          if ( !*((_DWORD *)v15 + 33) && !*((_DWORD *)v15 + 34) )
            SetEvent(*((HANDLE *)v15 + 10));
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 88));
          FreeLibrary(Library);
          if ( !LastError )
          {
LABEL_28:
            Handles[0] = EventW;
            Handles[1] = Thread;
            if ( *(_DWORD *)&gDebugLevel )
              _DebugMsg(4u, 0xCB5u);
            WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
            v16 = *(_DWORD *)&gDebugLevel;
            if ( *(_DWORD *)&gDebugLevel )
            {
              _DebugMsg(4u, 0xCB6u);
              v16 = *(_DWORD *)&gDebugLevel;
            }
            LastError = v20;
            if ( (v16 & 0x10) != 0 )
            {
              if ( v16 )
                _DebugMsg(4u, 0xCBDu);
              WaitForSingleObject(Thread, 0xFFFFFFFF);
              if ( *(_DWORD *)&gDebugLevel )
                _DebugMsg(4u, 0xCBEu);
            }
            CloseHandle(Thread);
          }
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( EventW )
      CloseHandle(EventW);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x1800030c0  push    rbp
0x1800030c2  push    rbx
0x1800030c3  push    rsi
0x1800030c4  push    rdi
0x1800030c5  push    r12
0x1800030c7  push    r13
0x1800030c9  push    r14
0x1800030cb  push    r15
0x1800030cd  lea     rbp, [rsp-17h]
0x1800030d2  sub     rsp, 88h
0x1800030d9  mov     r12, [rbp+4Fh+arg_20]
0x1800030dd  xor     r13d, r13d
0x1800030e0  mov     [rbp+4Fh+TokenHandle], r13
0x1800030e4  mov     r14, rdx
0x1800030e7  test    r12, r12
0x1800030ea  jz      short loc_18000310E
0x1800030ec  xorps   xmm0, xmm0
0x1800030ef  movups  xmmword ptr [r12], xmm0
0x1800030f4  cmp     r9d, 10000h
0x1800030fb  jnz     short loc_18000310E
0x1800030fd  sub     r8d, 1
0x180003101  jz      short loc_180003127
0x180003103  cmp     r8d, 1
0x180003107  jnz     short loc_18000310E
0x180003109  test    rdx, rdx
0x18000310c  jnz     short loc_18000312C
0x18000310e  mov     eax, 57h ; 'W'
0x180003113  add     rsp, 88h
0x18000311a  pop     r15
0x18000311c  pop     r14
0x18000311e  pop     r13
0x180003120  pop     r12
0x180003122  pop     rdi
0x180003123  pop     rsi
0x180003124  pop     rbx
0x180003125  pop     rbp
0x180003126  retn
0x180003127  test    r14, r14
0x18000312a  jnz     short loc_18000310E
0x18000312c  xor     ecx, ecx; BindingHandle
0x18000312e  call    cs:__imp_RpcImpersonateClient
0x180003134  mov     ebx, eax
0x180003136  test    eax, eax
0x180003138  jnz     short loc_180003113
0x18000313a  mov     rsi, r13
0x18000313d  call    cs:__imp_GetCurrentThread
0x180003143  lea     edi, [rbx+1]
0x180003146  mov     edx, 2000Eh; DesiredAccess
0x18000314b  mov     rcx, rax; ThreadHandle
0x18000314e  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x180003152  mov     r8d, edi; OpenAsSelf
0x180003155  call    cs:__imp_OpenThreadToken
0x18000315b  test    eax, eax
0x18000315d  jnz     short loc_180003167
0x18000315f  call    cs:__imp_GetLastError
0x180003165  mov     ebx, eax
0x180003167  call    cs:__imp_RevertToSelf
0x18000316d  test    ebx, ebx
0x18000316f  jnz     loc_180003341
0x180003175  xor     r9d, r9d; lpName
0x180003178  xor     r8d, r8d; bInitialState
0x18000317b  mov     edx, edi; bManualReset
0x18000317d  xor     ecx, ecx; lpEventAttributes
0x18000317f  call    cs:__imp_CreateEventW
0x180003185  mov     rsi, rax
0x180003188  test    rax, rax
0x18000318b  jnz     short loc_18000319A
0x18000318d  call    cs:__imp_GetLastError
0x180003193  mov     ebx, eax
0x180003195  jmp     loc_180003341
0x18000319a  mov     rdi, cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA; CRPCServiceManager * CRPCServiceManager::_pSingletonManager
0x1800031a1  mov     ebx, 42Ah
0x1800031a6  mov     r15, r13
0x1800031a9  lea     rcx, [rdi+58h]; lpCriticalSection
0x1800031ad  call    cs:__imp_EnterCriticalSection
0x1800031b3  cmp     [rdi+84h], r13d
0x1800031ba  jz      short loc_1800031F4
0x1800031bc  cmp     dword ptr [rdi+88h], 10000h
0x1800031c6  jnb     short loc_1800031F4
0x1800031c8  mov     rcx, [rdi+48h]; lpLibFileName
0x1800031cc  xor     edx, edx; hFile
0x1800031ce  mov     r8d, 800h; dwFlags
0x1800031d4  call    cs:__imp_LoadLibraryExW
0x1800031da  mov     r15, rax
0x1800031dd  test    rax, rax
0x1800031e0  jz      short loc_1800031EC
0x1800031e2  inc     dword ptr [rdi+88h]
0x1800031e8  xor     ebx, ebx
0x1800031ea  jmp     short loc_1800031F4
0x1800031ec  call    cs:__imp_GetLastError
0x1800031f2  mov     ebx, eax
0x1800031f4  lea     rcx, [rdi+58h]; lpCriticalSection
0x1800031f8  call    cs:__imp_LeaveCriticalSection
0x1800031fe  test    ebx, ebx
0x180003200  jnz     loc_180003341
0x180003206  mov     rax, [rbp+4Fh+TokenHandle]
0x18000320a  lea     r9, [rbp+4Fh+Parameter]; lpParameter
0x18000320e  mov     [rsp+0C0h+lpThreadId], r13; lpThreadId
0x180003213  lea     r8, ?GetManagedAppsProc@@YAKPEAX@Z; lpStartAddress
0x18000321a  xor     edx, edx; dwStackSize
0x18000321c  mov     [rbp+4Fh+var_68], rax
0x180003220  xor     ecx, ecx; lpThreadAttributes
0x180003222  mov     [rbp+4Fh+var_50], r13
0x180003226  mov     [rbp+4Fh+Parameter], r14
0x18000322a  mov     [rbp+4Fh+var_70], r12
0x18000322e  mov     [rbp+4Fh+var_60], rsi
0x180003232  mov     [rbp+4Fh+var_58], r15
0x180003236  mov     [rsp+0C0h+dwCreationFlags], r13d; dwCreationFlags
0x18000323b  call    cs:__imp_CreateThread
0x180003241  mov     rdi, rax
0x180003244  test    rax, rax
0x180003247  jnz     short loc_1800032A8
0x180003249  call    cs:__imp_GetLastError
0x18000324f  mov     r14, cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA; CRPCServiceManager * CRPCServiceManager::_pSingletonManager
0x180003256  mov     ebx, eax
0x180003258  lea     eax, [rdi+0Eh]
0x18000325b  test    ebx, ebx
0x18000325d  cmovz   ebx, eax
0x180003260  lea     rcx, [r14+58h]; lpCriticalSection
0x180003264  call    cs:__imp_EnterCriticalSection
0x18000326a  dec     dword ptr [r14+88h]
0x180003271  cmp     [r14+84h], r13d
0x180003278  jnz     short loc_18000328D
0x18000327a  cmp     [r14+88h], r13d
0x180003281  jnz     short loc_18000328D
0x180003283  mov     rcx, [r14+50h]; hEvent
0x180003287  call    cs:__imp_SetEvent
0x18000328d  lea     rcx, [r14+58h]; lpCriticalSection
0x180003291  call    cs:__imp_LeaveCriticalSection
0x180003297  mov     rcx, r15; hLibModule
0x18000329a  call    cs:__imp_FreeLibrary
0x1800032a0  test    ebx, ebx
0x1800032a2  jnz     loc_180003341
0x1800032a8  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x1800032af  mov     r14d, 4
0x1800032b5  mov     [rbp+4Fh+Handles], rsi
0x1800032b9  mov     [rbp+4Fh+var_80], rdi
0x1800032bd  jz      short loc_1800032CC
0x1800032bf  mov     edx, 0CB5h; unsigned int
0x1800032c4  mov     ecx, r14d; unsigned int
0x1800032c7  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800032cc  xor     r8d, r8d; bWaitAll
0x1800032cf  lea     rdx, [rbp+4Fh+Handles]; lpHandles
0x1800032d3  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800032d7  lea     ecx, [r8+2]; nCount
0x1800032db  call    cs:__imp_WaitForMultipleObjects
0x1800032e1  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x1800032e7  test    eax, eax
0x1800032e9  jz      short loc_1800032FE
0x1800032eb  mov     edx, 0CB6h; unsigned int
0x1800032f0  mov     ecx, r14d; unsigned int
0x1800032f3  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800032f8  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x1800032fe  mov     ebx, dword ptr [rbp+4Fh+var_50]
0x180003301  test    al, 10h
0x180003303  jz      short loc_180003338
0x180003305  test    eax, eax
0x180003307  jz      short loc_180003316
0x180003309  mov     edx, 0CBDh; unsigned int
0x18000330e  mov     ecx, r14d; unsigned int
0x180003311  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180003316  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003319  mov     rcx, rdi; hHandle
0x18000331c  call    cs:__imp_WaitForSingleObject
0x180003322  cmp     cs:?gDebugLevel@@3KA, r13d; ulong gDebugLevel
0x180003329  jz      short loc_180003338
0x18000332b  mov     edx, 0CBEh; unsigned int
0x180003330  mov     ecx, r14d; unsigned int
0x180003333  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180003338  mov     rcx, rdi; hObject
0x18000333b  call    cs:__imp_CloseHandle
0x180003341  mov     rcx, [rbp+4Fh+TokenHandle]; hObject
0x180003345  test    rcx, rcx
0x180003348  jz      short loc_180003350
0x18000334a  call    cs:__imp_CloseHandle
0x180003350  test    rsi, rsi
0x180003353  jz      short loc_18000335E
0x180003355  mov     rcx, rsi; hObject
0x180003358  call    cs:__imp_CloseHandle
0x18000335e  mov     eax, ebx
0x180003360  jmp     loc_180003113
```
