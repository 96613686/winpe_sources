# IdsRunCommand(ushort const *,ushort const *)

- ea: `0x1800dc0ec`
- end: `0x1800dc30c`
- name: `?IdsRunCommand@@YAKPEBG0@Z`
- size: `544`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800dbd4c`

## callees

- `0x180012920`
- `0x180019c84`
- `0x18007a9cf`
- `0x1800dc0ec`

## import_xrefs

- `msvcrt!printf` at `0x1800dc279`
- `msvcrt!printf` at `0x1800dc279`
- `msvcrt!wcscat_s` at `0x1800dc1af`
- `msvcrt!wcscat_s` at `0x1800dc1af`
- `msvcrt!wcscpy_s` at `0x1800dc1a1`
- `msvcrt!wcscpy_s` at `0x1800dc1a1`
- `ntdll!RtlAllocateHeap` at `0x1800dc187`
- `ntdll!RtlAllocateHeap` at `0x1800dc1f3`
- `ntdll!RtlAllocateHeap` at `0x1800dc187`
- `ntdll!RtlAllocateHeap` at `0x1800dc1f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc1ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc29c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc1ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc29c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800dc25e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800dc25e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc286`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc286`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc291`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800dc1bd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800dc20e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800dc1bd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800dc20e`

## string_xrefs

- `0x1800dc270`: `Failed to create crash process with [%d]\n`
- `0x1800dc133`: `IdsRunCommand`
- `0x1800dc2b4`: `IdsRunCommand`
- `0x1800dc121`: `RunCommand [%ws][%ws]`

## pseudocode

```c
__int64 __fastcall IdsRunCommand(wchar_t *Source, wchar_t *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  DWORD v6; // ebx
  __int64 v7; // rdi
  wchar_t *Heap; // rax
  wchar_t *v9; // rsi
  DWORD v10; // eax
  WCHAR *v11; // rdi
  DWORD LastError; // eax
  int v13; // r8d
  DWORD v14; // ebp
  WCHAR *v15; // rax
  DWORD v16; // eax
  BOOL bInheritHandles[2]; // [rsp+20h] [rbp-F8h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-C8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-A8h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  AslLogCallPrintf(3, (unsigned int)"IdsRunCommand", 540, (unsigned int)"RunCommand [%ws][%ws]", Source, a2);
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  do
    ++v4;
  while ( Source[v4] );
  v6 = 8;
  v7 = (unsigned int)(v4 + v5 + 2);
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v7);
  v9 = Heap;
  if ( !Heap )
    return v6;
  wcscpy_s(Heap, (unsigned int)v7, Source);
  wcscat_s(v9, (unsigned int)v7, a2);
  v10 = ExpandEnvironmentStringsW(v9, 0, 0);
  if ( !v10 )
  {
    v11 = 0;
    LastError = GetLastError();
    v13 = 560;
LABEL_14:
    bInheritHandles[0] = LastError;
    v6 = LastError;
    AslLogCallPrintf(
      1,
      (unsigned int)"IdsRunCommand",
      v13,
      (unsigned int)"Failed to expand parameter string [%d] [%ws]",
      *(_QWORD *)bInheritHandles,
      v9);
    goto LABEL_15;
  }
  v14 = v10 + 1;
  v15 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (v10 + 1));
  v11 = v15;
  if ( !v15 )
    goto LABEL_15;
  v16 = ExpandEnvironmentStringsW(v9, v15, v14);
  if ( !v16 || v16 > v14 )
  {
    LastError = GetLastError();
    v13 = 576;
    goto LABEL_14;
  }
  StartupInfo.cb = 104;
  if ( CreateProcessW(0, v11, 0, 0, 0, 0x8000008u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    CloseHandle(ProcessInformation.hThread);
    CloseHandle(ProcessInformation.hProcess);
    v6 = 0;
  }
  else
  {
    v6 = GetLastError();
    printf("Failed to create crash process with [%d]\n", v6);
  }
LABEL_15:
  AslFree(NtCurrentPeb()->ProcessHeap, v9);
  if ( v11 )
    AslFree(NtCurrentPeb()->ProcessHeap, v11);
  return v6;
}

```

## disassembly

```asm
0x1800dc0ec  push    rbx
0x1800dc0ee  push    rbp
0x1800dc0ef  push    rsi
0x1800dc0f0  push    rdi
0x1800dc0f1  push    r14
0x1800dc0f3  push    r15
0x1800dc0f5  sub     rsp, 0E8h
0x1800dc0fc  mov     rbp, rdx
0x1800dc0ff  mov     r14, rcx
0x1800dc102  xor     edx, edx; Val
0x1800dc104  lea     rcx, [rsp+118h+StartupInfo]; void *
0x1800dc109  lea     r8d, [rdx+68h]; Size
0x1800dc10d  call    memset_0
0x1800dc112  xor     eax, eax
0x1800dc114  mov     qword ptr [rsp+118h+dwCreationFlags], rbp
0x1800dc119  xorps   xmm0, xmm0
0x1800dc11c  mov     qword ptr [rsp+118h+ProcessInformation.dwProcessId], rax
0x1800dc121  lea     r9, aRuncommandWsWs; "RunCommand [%ws][%ws]"
0x1800dc128  mov     qword ptr [rsp+118h+bInheritHandles], r14
0x1800dc12d  mov     r8d, 21Ch
0x1800dc133  lea     rdx, aIdsruncommand; "IdsRunCommand"
0x1800dc13a  lea     ecx, [rax+3]
0x1800dc13d  movups  xmmword ptr [rsp+118h+ProcessInformation.hProcess], xmm0
0x1800dc142  call    AslLogCallPrintf
0x1800dc147  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800dc14b  mov     rcx, rax
0x1800dc14e  xor     r15d, r15d
0x1800dc151  inc     rcx
0x1800dc154  cmp     [rbp+rcx*2+0], r15w
0x1800dc15a  jnz     short loc_1800DC151
0x1800dc15c  inc     rax
0x1800dc15f  cmp     [r14+rax*2], r15w
0x1800dc164  jnz     short loc_1800DC15C
0x1800dc166  lea     rdi, [rcx+2]
0x1800dc16a  mov     ebx, 8
0x1800dc16f  mov     rcx, gs:60h
0x1800dc178  add     rdi, rax
0x1800dc17b  mov     edi, edi
0x1800dc17d  mov     edx, ebx; Flags
0x1800dc17f  mov     rcx, [rcx+30h]; HeapHandle
0x1800dc183  lea     r8, [rdi+rdi]; Size
0x1800dc187  call    cs:__imp_RtlAllocateHeap
0x1800dc18d  mov     rsi, rax
0x1800dc190  test    rax, rax
0x1800dc193  jz      loc_1800DC2FA
0x1800dc199  mov     r8, r14; Source
0x1800dc19c  mov     edx, edi; SizeInWords
0x1800dc19e  mov     rcx, rax; Destination
0x1800dc1a1  call    cs:__imp_wcscpy_s
0x1800dc1a7  mov     r8, rbp; Source
0x1800dc1aa  mov     edx, edi; SizeInWords
0x1800dc1ac  mov     rcx, rsi; Destination
0x1800dc1af  call    cs:__imp_wcscat_s
0x1800dc1b5  xor     r8d, r8d; nSize
0x1800dc1b8  xor     edx, edx; lpDst
0x1800dc1ba  mov     rcx, rsi; lpSrc
0x1800dc1bd  call    cs:__imp_ExpandEnvironmentStringsW
0x1800dc1c3  test    eax, eax
0x1800dc1c5  jnz     short loc_1800DC1DB
0x1800dc1c7  mov     rdi, r15
0x1800dc1ca  call    cs:__imp_GetLastError
0x1800dc1d0  mov     r8d, 230h
0x1800dc1d6  jmp     loc_1800DC2A8
0x1800dc1db  mov     rcx, gs:60h
0x1800dc1e4  lea     ebp, [rax+1]
0x1800dc1e7  mov     r8d, ebp
0x1800dc1ea  mov     edx, ebx; Flags
0x1800dc1ec  add     r8, r8; Size
0x1800dc1ef  mov     rcx, [rcx+30h]; HeapHandle
0x1800dc1f3  call    cs:__imp_RtlAllocateHeap
0x1800dc1f9  mov     rdi, rax
0x1800dc1fc  test    rax, rax
0x1800dc1ff  jz      loc_1800DC2CB
0x1800dc205  mov     r8d, ebp; nSize
0x1800dc208  mov     rdx, rax; lpDst
0x1800dc20b  mov     rcx, rsi; lpSrc
0x1800dc20e  call    cs:__imp_ExpandEnvironmentStringsW
0x1800dc214  test    eax, eax
0x1800dc216  jz      loc_1800DC29C
0x1800dc21c  cmp     eax, ebp
0x1800dc21e  ja      short loc_1800DC29C
0x1800dc220  lea     rax, [rsp+118h+ProcessInformation]
0x1800dc225  mov     [rsp+118h+StartupInfo.cb], 68h ; 'h'
0x1800dc22d  mov     [rsp+118h+lpProcessInformation], rax; lpProcessInformation
0x1800dc232  xor     r9d, r9d; lpThreadAttributes
0x1800dc235  lea     rax, [rsp+118h+StartupInfo]
0x1800dc23a  xor     r8d, r8d; lpProcessAttributes
0x1800dc23d  mov     [rsp+118h+lpStartupInfo], rax; lpStartupInfo
0x1800dc242  mov     rdx, rdi; lpCommandLine
0x1800dc245  mov     [rsp+118h+lpCurrentDirectory], r15; lpCurrentDirectory
0x1800dc24a  xor     ecx, ecx; lpApplicationName
0x1800dc24c  mov     [rsp+118h+lpEnvironment], r15; lpEnvironment
0x1800dc251  mov     [rsp+118h+dwCreationFlags], 8000008h; dwCreationFlags
0x1800dc259  mov     [rsp+118h+bInheritHandles], r15d; bInheritHandles
0x1800dc25e  call    cs:__imp_CreateProcessW
0x1800dc264  test    eax, eax
0x1800dc266  jnz     short loc_1800DC281
0x1800dc268  call    cs:__imp_GetLastError
0x1800dc26e  mov     edx, eax
0x1800dc270  lea     rcx, aFailedToCreate_21; "Failed to create crash process with [%d"...
0x1800dc277  mov     ebx, eax
0x1800dc279  call    cs:__imp_printf
0x1800dc27f  jmp     short loc_1800DC2CB
0x1800dc281  mov     rcx, [rsp+118h+ProcessInformation.hThread]; hObject
0x1800dc286  call    cs:__imp_CloseHandle
0x1800dc28c  mov     rcx, [rsp+118h+ProcessInformation.hProcess]; hObject
0x1800dc291  call    cs:__imp_CloseHandle
0x1800dc297  mov     ebx, r15d
0x1800dc29a  jmp     short loc_1800DC2CB
0x1800dc29c  call    cs:__imp_GetLastError
0x1800dc2a2  mov     r8d, 240h
0x1800dc2a8  mov     qword ptr [rsp+118h+dwCreationFlags], rsi
0x1800dc2ad  lea     r9, aFailedToExpand_13; "Failed to expand parameter string [%d] "...
0x1800dc2b4  lea     rdx, aIdsruncommand; "IdsRunCommand"
0x1800dc2bb  mov     [rsp+118h+bInheritHandles], eax
0x1800dc2bf  mov     ecx, 1
0x1800dc2c4  mov     ebx, eax
0x1800dc2c6  call    AslLogCallPrintf
0x1800dc2cb  mov     rcx, gs:60h
0x1800dc2d4  mov     rdx, rsi
0x1800dc2d7  mov     rcx, [rcx+30h]
0x1800dc2db  call    AslFree
0x1800dc2e0  test    rdi, rdi
0x1800dc2e3  jz      short loc_1800DC2FA
0x1800dc2e5  mov     rcx, gs:60h
0x1800dc2ee  mov     rdx, rdi
0x1800dc2f1  mov     rcx, [rcx+30h]
0x1800dc2f5  call    AslFree
0x1800dc2fa  mov     eax, ebx
0x1800dc2fc  add     rsp, 0E8h
0x1800dc303  pop     r15
0x1800dc305  pop     r14
0x1800dc307  pop     rdi
0x1800dc308  pop     rsi
0x1800dc309  pop     rbp
0x1800dc30a  pop     rbx
0x1800dc30b  retn
```
