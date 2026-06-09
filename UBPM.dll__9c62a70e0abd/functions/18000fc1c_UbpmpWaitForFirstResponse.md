# UbpmpWaitForFirstResponse

- ea: `0x18000fc1c`
- end: `0x18000fdc1`
- name: `UbpmpWaitForFirstResponse`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180010450`

## callees

- `0x18000ea50`
- `0x18000fc1c`
- `0x1800351ec`
- `0x18003ed48`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000fc4b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000fc4b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000fcb0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000fcb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fc57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fc57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fccf`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fd1e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fd1e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000fd80`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000fd80`

## pseudocode

```c
__int64 __fastcall UbpmpWaitForFirstResponse(__int64 a1)
{
  int v2; // esi
  int v3; // r8d
  int v4; // r9d
  _BYTE *v5; // rbx
  DWORD LastError; // ebx
  const char *v8; // rax

  v2 = UbpmpWaitForHostResponse(*(unsigned __int8 *)(a1 + 432));
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_180050018 = GetCurrentThreadId();
  if ( v2 == -1 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
  }
  else
  {
    v5 = (_BYTE *)(a1 + 104);
    if ( !v2 )
      goto LABEL_3;
    if ( (*v5 & 2) != 0 && v2 != 1 )
    {
      ResetEvent(*(HANDLE *)(a1 + 48));
LABEL_3:
      *v5 &= ~1u;
      *v5 |= 8u;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *(unsigned int *)(a1 + 32));
      LastError = 0;
      goto LABEL_7;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = "NOT";
      if ( v2 != 258 )
        v8 = (const char *)&qword_180044758;
      WPP_SF_Ds(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)&qword_180044758, v3, v4, (__int64)v8);
    }
    LastError = 1460;
    if ( g_fBreakOnTaskhostTimeout && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
      __debugbreak();
  }
LABEL_7:
  dword_180050018 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  return LastError;
}

```

## disassembly

```asm
0x18000fc1c  mov     [rsp+arg_0], rbx
0x18000fc21  mov     [rsp+arg_8], rsi
0x18000fc26  push    rdi
0x18000fc27  sub     rsp, 30h
0x18000fc2b  mov     rdi, rcx
0x18000fc2e  movzx   ecx, byte ptr [rcx+1B0h]; bAlertable
0x18000fc35  mov     r8, [rdi+18h]
0x18000fc39  mov     rdx, [rdi+30h]
0x18000fc3d  call    UbpmpWaitForHostResponse
0x18000fc42  lea     rcx, g_TaskHostContextListLock
0x18000fc49  mov     esi, eax
0x18000fc4b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000fc52  nop     dword ptr [rax+rax+00h]
0x18000fc57  call    cs:__imp_GetCurrentThreadId
0x18000fc5e  nop     dword ptr [rax+rax+00h]
0x18000fc63  mov     cs:dword_180050018, eax
0x18000fc69  cmp     esi, 0FFFFFFFFh
0x18000fc6c  jz      short loc_18000FCCF
0x18000fc6e  lea     rbx, [rdi+68h]
0x18000fc72  test    esi, esi
0x18000fc74  jnz     loc_18000FD10
0x18000fc7a  and     byte ptr [rbx], 0FEh
0x18000fc7d  or      byte ptr [rbx], 8
0x18000fc80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc87  lea     rax, WPP_GLOBAL_Control
0x18000fc8e  cmp     rcx, rax
0x18000fc91  jz      short loc_18000FC9D
0x18000fc93  test    byte ptr [rcx+1Ch], 80h
0x18000fc97  jnz     loc_18000FDA3
0x18000fc9d  xor     ebx, ebx
0x18000fc9f  lea     rcx, g_TaskHostContextListLock
0x18000fca6  mov     cs:dword_180050018, 0
0x18000fcb0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000fcb7  nop     dword ptr [rax+rax+00h]
0x18000fcbc  mov     rsi, [rsp+38h+arg_8]
0x18000fcc1  mov     eax, ebx
0x18000fcc3  mov     rbx, [rsp+38h+arg_0]
0x18000fcc8  add     rsp, 30h
0x18000fccc  pop     rdi
0x18000fccd  retn
0x18000fccf  call    cs:__imp_GetLastError
0x18000fcd6  nop     dword ptr [rax+rax+00h]
0x18000fcdb  mov     ebx, eax
0x18000fcdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fce4  lea     rax, WPP_GLOBAL_Control
0x18000fceb  cmp     rcx, rax
0x18000fcee  jz      short loc_18000FC9F
0x18000fcf0  test    byte ptr [rcx+1Ch], 1
0x18000fcf4  jz      short loc_18000FC9F
0x18000fcf6  mov     rcx, [rcx+10h]
0x18000fcfa  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000fd01  mov     edx, 4Ch ; 'L'
0x18000fd06  mov     r9d, ebx
0x18000fd09  call    WPP_SF_d
0x18000fd0e  jmp     short loc_18000FC9F
0x18000fd10  test    byte ptr [rbx], 2
0x18000fd13  jz      short loc_18000FD2F
0x18000fd15  cmp     esi, 1
0x18000fd18  jz      short loc_18000FD2F
0x18000fd1a  mov     rcx, [rdi+30h]; hEvent
0x18000fd1e  call    cs:__imp_ResetEvent
0x18000fd25  nop     dword ptr [rax+rax+00h]
0x18000fd2a  jmp     loc_18000FC7A
0x18000fd2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd36  lea     rax, WPP_GLOBAL_Control
0x18000fd3d  cmp     rcx, rax
0x18000fd40  jz      short loc_18000FD6E
0x18000fd42  test    byte ptr [rcx+1Ch], 1
0x18000fd46  jz      short loc_18000FD6E
0x18000fd48  mov     rcx, [rcx+10h]
0x18000fd4c  lea     rdx, qword_180044758
0x18000fd53  cmp     esi, 102h
0x18000fd59  lea     rax, aNot; "NOT"
0x18000fd60  cmovnz  rax, rdx
0x18000fd64  mov     [rsp+38h+var_18], rax
0x18000fd69  call    WPP_SF_Ds
0x18000fd6e  cmp     cs:?g_fBreakOnTaskhostTimeout@@3EA, 0; uchar g_fBreakOnTaskhostTimeout
0x18000fd75  mov     ebx, 5B4h
0x18000fd7a  jz      loc_18000FC9F
0x18000fd80  call    cs:__imp_IsDebuggerPresent
0x18000fd87  nop     dword ptr [rax+rax+00h]
0x18000fd8c  test    eax, eax
0x18000fd8e  jnz     short loc_18000FD9D
0x18000fd90  cmp     ds:7FFE02D4h, al
0x18000fd97  jz      loc_18000FC9F
0x18000fd9d  int     3; Trap to Debugger
0x18000fd9e  jmp     loc_18000FC9F
0x18000fda3  mov     r9d, [rdi+20h]
0x18000fda7  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000fdae  mov     rcx, [rcx+10h]
0x18000fdb2  mov     edx, 4Eh ; 'N'
0x18000fdb7  call    WPP_SF_d
0x18000fdbc  jmp     loc_18000FC9D
```
