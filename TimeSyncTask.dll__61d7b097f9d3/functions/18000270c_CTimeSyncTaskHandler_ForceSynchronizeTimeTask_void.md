# CTimeSyncTaskHandler::ForceSynchronizeTimeTask(void)

- ea: `0x18000270c`
- end: `0x1800028f9`
- name: `?ForceSynchronizeTimeTask@CTimeSyncTaskHandler@@AEAAJXZ`
- size: `493`
- prototype: `__int64 __fastcall(CTimeSyncTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002ba0`

## callees

- `0x180001460`
- `0x180002060`
- `0x18000270c`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000286a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000286a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800028ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800028ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002882`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002882`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800027a5`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000280e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800027a5`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000280e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000275d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000275d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000277a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000277a`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800027eb`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800027eb`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x1800027d4`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180002831`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x1800027d4`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180002831`

## string_xrefs

- `0x180002740`: `ServicesActive`
- `0x180002861`: `w32time.dll`

## pseudocode

```c
__int64 __fastcall CTimeSyncTaskHandler::ForceSynchronizeTimeTask(CTimeSyncTaskHandler *this)
{
  unsigned int v2; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  const unsigned __int16 *v5; // rcx
  char v6; // r14
  int v7; // eax
  HMODULE Library; // rax
  HMODULE v9; // rsi
  FARPROC ProcAddress; // r12
  int v11; // edi
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v15; // [rsp+48h] [rbp-30h]
  int v16; // [rsp+58h] [rbp-20h]

  pcbBytesNeeded = 0;
  v16 = 0;
  v2 = -2147467259;
  *(_OWORD *)Buffer = 0;
  v15 = 0;
  v3 = OpenSCManagerW(0, L"ServicesActive", 1u);
  if ( !v3 )
    return v2;
  v4 = OpenServiceW(v3, L"w32time", 0x14u);
  if ( !v4 || !QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
    return v2;
  if ( *(_DWORD *)&Buffer[4] != 1 )
  {
    if ( *(_DWORD *)&Buffer[4] != 3 )
    {
      v6 = 0;
      goto LABEL_14;
    }
    if ( (unsigned int)WaitServiceState(v4, 1, DWORD2(v15), 0) == 3 )
      return v2;
  }
  if ( !StartServiceW(v4, 0, 0) )
    return v2;
  if ( !QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
    return v2;
  v7 = *(_DWORD *)&Buffer[4];
  if ( *(_DWORD *)&Buffer[4] == 2 )
  {
    v7 = WaitServiceState(v4, 8, DWORD2(v15), 0);
    if ( v7 == 2 )
      return v2;
  }
  if ( v7 != 4 )
    return v2;
  v6 = 1;
LABEL_14:
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) == 1 )
  {
    v2 = -2147467260;
  }
  else
  {
    Library = LoadLibraryExW(L"w32time.dll", 0, 0);
    v9 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "W32TimeSyncNow");
      if ( ProcAddress )
      {
        v11 = 0;
        while ( ((unsigned int (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 1, 18) )
        {
          if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) == 1 )
          {
            v2 = -2147467260;
            goto LABEL_25;
          }
          if ( (unsigned int)++v11 > 0xA )
            goto LABEL_25;
        }
        v2 = 0;
      }
LABEL_25:
      FreeLibrary(v9);
    }
  }
  if ( v6 )
    TsStopService(v5);
  return v2;
}

```

## disassembly

```asm
0x18000270c  push    rbp
0x18000270e  push    rbx
0x18000270f  push    rsi
0x180002710  push    rdi
0x180002711  push    r12
0x180002713  push    r13
0x180002715  push    r14
0x180002717  push    r15
0x180002719  mov     rbp, rsp
0x18000271c  sub     rsp, 78h
0x180002720  mov     rax, cs:__security_cookie
0x180002727  xor     rax, rsp
0x18000272a  mov     [rbp+var_18], rax
0x18000272e  xor     eax, eax
0x180002730  mov     [rbp+var_48], 0
0x180002737  xorps   xmm0, xmm0
0x18000273a  mov     [rbp+var_20], eax
0x18000273d  mov     r15, rcx
0x180002740  lea     rdx, DatabaseName; "ServicesActive"
0x180002747  xor     ecx, ecx; lpMachineName
0x180002749  mov     ebx, 80004005h
0x18000274e  lea     r13d, [rax+1]
0x180002752  mov     r8d, r13d; dwDesiredAccess
0x180002755  movups  xmmword ptr [rbp+Buffer], xmm0
0x180002759  movups  [rbp+var_30], xmm0
0x18000275d  call    cs:__imp_OpenSCManagerW
0x180002763  test    rax, rax
0x180002766  jz      loc_1800028DA
0x18000276c  lea     r8d, [r13+13h]; dwDesiredAccess
0x180002770  mov     rcx, rax; hSCManager
0x180002773  lea     rdx, ServiceName; "w32time"
0x18000277a  call    cs:__imp_OpenServiceW
0x180002780  mov     rdi, rax
0x180002783  test    rax, rax
0x180002786  jz      loc_1800028DA
0x18000278c  lea     rax, [rbp+var_48]
0x180002790  xor     edx, edx; InfoLevel
0x180002792  lea     esi, [r13+23h]
0x180002796  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000279b  mov     r9d, esi; cbBufSize
0x18000279e  lea     r8, [rbp+Buffer]; lpBuffer
0x1800027a2  mov     rcx, rdi; hService
0x1800027a5  call    cs:__imp_QueryServiceStatusEx
0x1800027ab  test    eax, eax
0x1800027ad  jz      loc_1800028DA
0x1800027b3  cmp     dword ptr [rbp+Buffer+4], r13d
0x1800027b7  jz      short loc_1800027E3
0x1800027b9  cmp     dword ptr [rbp+Buffer+4], 3
0x1800027bd  jz      short loc_1800027C7
0x1800027bf  xor     r14b, r14b
0x1800027c2  jmp     loc_18000284C
0x1800027c7  mov     r8d, dword ptr [rbp+var_30+8]
0x1800027cb  xor     r9d, r9d
0x1800027ce  mov     edx, r13d
0x1800027d1  mov     rcx, rdi
0x1800027d4  call    cs:__imp_WaitServiceState
0x1800027da  cmp     eax, 3
0x1800027dd  jz      loc_1800028DA
0x1800027e3  xor     r8d, r8d; lpServiceArgVectors
0x1800027e6  xor     edx, edx; dwNumServiceArgs
0x1800027e8  mov     rcx, rdi; hService
0x1800027eb  call    cs:__imp_StartServiceW
0x1800027f1  test    eax, eax
0x1800027f3  jz      loc_1800028DA
0x1800027f9  lea     rax, [rbp+var_48]
0x1800027fd  mov     r9d, esi; cbBufSize
0x180002800  lea     r8, [rbp+Buffer]; lpBuffer
0x180002804  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180002809  xor     edx, edx; InfoLevel
0x18000280b  mov     rcx, rdi; hService
0x18000280e  call    cs:__imp_QueryServiceStatusEx
0x180002814  test    eax, eax
0x180002816  jz      loc_1800028DA
0x18000281c  mov     eax, dword ptr [rbp+Buffer+4]
0x18000281f  cmp     eax, 2
0x180002822  jnz     short loc_180002840
0x180002824  mov     r8d, dword ptr [rbp+var_30+8]
0x180002828  lea     edx, [rax+6]
0x18000282b  xor     r9d, r9d
0x18000282e  mov     rcx, rdi
0x180002831  call    cs:__imp_WaitServiceState
0x180002837  cmp     eax, 2
0x18000283a  jz      loc_1800028DA
0x180002840  cmp     eax, 4
0x180002843  jnz     loc_1800028DA
0x180002849  mov     r14b, r13b
0x18000284c  mov     eax, r13d
0x18000284f  lock cmpxchg [r15+24h], r13d
0x180002855  jnz     short loc_18000285E
0x180002857  mov     ebx, 80004004h
0x18000285c  jmp     short loc_1800028D0
0x18000285e  xor     r8d, r8d; dwFlags
0x180002861  lea     rcx, LibFileName; "w32time.dll"
0x180002868  xor     edx, edx; hFile
0x18000286a  call    cs:__imp_LoadLibraryExW
0x180002870  mov     rsi, rax
0x180002873  test    rax, rax
0x180002876  jz      short loc_1800028D0
0x180002878  lea     rdx, ProcName; "W32TimeSyncNow"
0x18000287f  mov     rcx, rax; hModule
0x180002882  call    cs:__imp_GetProcAddress
0x180002888  mov     r12, rax
0x18000288b  test    rax, rax
0x18000288e  jz      short loc_1800028C7
0x180002890  xor     edi, edi
0x180002892  mov     r8d, 12h
0x180002898  mov     edx, r13d
0x18000289b  xor     ecx, ecx
0x18000289d  mov     rax, r12
0x1800028a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a5  test    eax, eax
0x1800028a7  jz      short loc_1800028C5
0x1800028a9  mov     eax, r13d
0x1800028ac  lock cmpxchg [r15+24h], r13d
0x1800028b2  jz      short loc_1800028BE
0x1800028b4  add     edi, r13d
0x1800028b7  cmp     edi, 0Ah
0x1800028ba  jbe     short loc_180002892
0x1800028bc  jmp     short loc_1800028C7
0x1800028be  mov     ebx, 80004004h
0x1800028c3  jmp     short loc_1800028C7
0x1800028c5  xor     ebx, ebx
0x1800028c7  mov     rcx, rsi; hLibModule
0x1800028ca  call    cs:__imp_FreeLibrary
0x1800028d0  test    r14b, r14b
0x1800028d3  jz      short loc_1800028DA
0x1800028d5  call    ?TsStopService@@YAJPEBG@Z; TsStopService(ushort const *)
0x1800028da  mov     eax, ebx
0x1800028dc  mov     rcx, [rbp+var_18]
0x1800028e0  xor     rcx, rsp; StackCookie
0x1800028e3  call    __security_check_cookie
0x1800028e8  add     rsp, 78h
0x1800028ec  pop     r15
0x1800028ee  pop     r14
0x1800028f0  pop     r13
0x1800028f2  pop     r12
0x1800028f4  pop     rdi
0x1800028f5  pop     rsi
0x1800028f6  pop     rbx
0x1800028f7  pop     rbp
0x1800028f8  retn
```
