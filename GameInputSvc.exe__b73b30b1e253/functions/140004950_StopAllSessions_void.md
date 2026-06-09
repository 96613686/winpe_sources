# StopAllSessions(void)

- ea: `0x140004950`
- end: `0x140004ab3`
- name: `?StopAllSessions@@YAXXZ`
- size: `355`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400028f8`
- `0x1400038b0`

## callees

- `0x140003a18`
- `0x140003b3c`
- `0x140004950`
- `0x140006b48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400049d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400049d4`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140004a71`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140004a71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004972`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004972`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004a82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004a82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004a8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004a8b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x140004a36`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x140004a36`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x140004aa5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x140004aa5`

## pseudocode

```c
void StopAllSessions(void)
{
  __int64 **v0; // rcx
  __int64 *v1; // rax
  __int64 v2; // rcx
  __int64 *v3; // rax
  __int64 *v4; // rcx
  __int64 i; // rbx
  HANDLE v6; // rax
  void *v7; // rdi
  __int64 *v8; // [rsp+30h] [rbp-10h] BYREF
  __int64 *v9; // [rsp+38h] [rbp-8h]
  DWORD pCount; // [rsp+60h] [rbp+20h] BYREF
  LPCWSTR lpName; // [rsp+68h] [rbp+28h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+70h] [rbp+30h] BYREF

  v9 = (__int64 *)&v8;
  v8 = (__int64 *)&v8;
  EnterCriticalSection(&CriticalSection);
  while ( 1 )
  {
    v1 = (__int64 *)qword_14000E6F0;
    v2 = *(_QWORD *)qword_14000E6F0;
    if ( *(__int64 **)(qword_14000E6F0 + 8) != &qword_14000E6F0 || *(_QWORD *)(v2 + 8) != qword_14000E6F0 )
LABEL_7:
      __fastfail(3u);
    qword_14000E6F0 = *(_QWORD *)qword_14000E6F0;
    *(_QWORD *)(v2 + 8) = &qword_14000E6F0;
    if ( v1 == &qword_14000E6F0 )
      break;
    v0 = (__int64 **)v9;
    if ( (__int64 **)*v9 != &v8 )
      goto LABEL_7;
    v1[1] = (__int64)v9;
    *v1 = (__int64)&v8;
    *v0 = v1;
    v9 = v1;
  }
  LeaveCriticalSection(&CriticalSection);
  while ( 1 )
  {
    v3 = v8;
    v4 = (__int64 *)*v8;
    if ( (__int64 **)v8[1] != &v8 || (__int64 *)v4[1] != v8 )
      goto LABEL_7;
    v8 = (__int64 *)*v8;
    v4[1] = (__int64)&v8;
    if ( v3 == (__int64 *)&v8 )
      break;
    DeleteSession(v3);
  }
  ppSessionInfo = 0;
  pCount = 0;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    for ( i = 0; (unsigned int)i < pCount; i = (unsigned int)(i + 1) )
    {
      lpName = 0;
      if ( (int)CreateEventName(ppSessionInfo[i].SessionId, &lpName) >= 0 )
      {
        v6 = OpenEventW(2u, 0, lpName);
        v7 = v6;
        if ( v6 )
        {
          SetEvent(v6);
          CloseHandle(v7);
        }
        operator delete[]((PVOID)lpName);
      }
    }
    WTSFreeMemory(ppSessionInfo);
  }
}

```

## disassembly

```asm
0x140004950  push    rbp
0x140004952  push    rbx
0x140004953  push    rdi
0x140004954  mov     rbp, rsp
0x140004957  sub     rsp, 40h
0x14000495b  lea     rax, [rbp+var_10]
0x14000495f  mov     [rbp+var_8], rax
0x140004963  lea     rcx, CriticalSection; lpCriticalSection
0x14000496a  lea     rax, [rbp+var_10]
0x14000496e  mov     [rbp+var_10], rax
0x140004972  call    cs:__imp_EnterCriticalSection
0x140004978  lea     r8, qword_14000E6F0
0x14000497f  jmp     short loc_1400049B6
0x140004981  cmp     [rcx+8], rax
0x140004985  jnz     short loc_1400049C6
0x140004987  mov     cs:qword_14000E6F0, rcx
0x14000498e  mov     [rcx+8], r8
0x140004992  cmp     rax, r8
0x140004995  jz      short loc_1400049CD
0x140004997  mov     rcx, [rbp+var_8]
0x14000499b  lea     rdx, [rbp+var_10]
0x14000499f  cmp     [rcx], rdx
0x1400049a2  jnz     short loc_1400049C6
0x1400049a4  mov     [rax+8], rcx
0x1400049a8  lea     rdx, [rbp+var_10]
0x1400049ac  mov     [rax], rdx
0x1400049af  mov     [rcx], rax
0x1400049b2  mov     [rbp+var_8], rax
0x1400049b6  mov     rax, cs:qword_14000E6F0
0x1400049bd  mov     rcx, [rax]
0x1400049c0  cmp     [rax+8], r8
0x1400049c4  jz      short loc_140004981
0x1400049c6  mov     ecx, 3
0x1400049cb  int     29h; Win8: RtlFailFast(ecx)
0x1400049cd  lea     rcx, CriticalSection; lpCriticalSection
0x1400049d4  call    cs:__imp_LeaveCriticalSection
0x1400049da  jmp     short loc_1400049FF
0x1400049dc  cmp     [rcx+8], rax
0x1400049e0  jnz     short loc_1400049C6
0x1400049e2  mov     [rbp+var_10], rcx
0x1400049e6  lea     rdx, [rbp+var_10]
0x1400049ea  mov     [rcx+8], rdx
0x1400049ee  lea     rcx, [rbp+var_10]
0x1400049f2  cmp     rax, rcx
0x1400049f5  jz      short loc_140004A12
0x1400049f7  mov     rcx, rax
0x1400049fa  call    DeleteSession
0x1400049ff  mov     rax, [rbp+var_10]
0x140004a03  lea     rdx, [rbp+var_10]
0x140004a07  mov     rcx, [rax]
0x140004a0a  cmp     [rax+8], rdx
0x140004a0e  jz      short loc_1400049DC
0x140004a10  jmp     short loc_1400049C6
0x140004a12  xor     edx, edx; Reserved
0x140004a14  mov     [rbp+ppSessionInfo], 0
0x140004a1c  lea     rax, [rbp+arg_0]
0x140004a20  mov     [rbp+arg_0], 0
0x140004a27  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x140004a2b  mov     [rsp+40h+pCount], rax; pCount
0x140004a30  xor     ecx, ecx; hServer
0x140004a32  lea     r8d, [rdx+1]; Version
0x140004a36  call    cs:__imp_WTSEnumerateSessionsW
0x140004a3c  test    eax, eax
0x140004a3e  jz      short loc_140004AAB
0x140004a40  xor     ebx, ebx
0x140004a42  cmp     [rbp+arg_0], ebx
0x140004a45  jbe     short loc_140004AA1
0x140004a47  mov     rcx, [rbp+ppSessionInfo]
0x140004a4b  lea     r8, [rbx+rbx*2]
0x140004a4f  lea     rdx, [rbp+lpName]
0x140004a53  mov     [rbp+lpName], 0
0x140004a5b  mov     ecx, [rcx+r8*8]
0x140004a5f  call    CreateEventName
0x140004a64  test    eax, eax
0x140004a66  js      short loc_140004A9A
0x140004a68  mov     r8, [rbp+lpName]; lpName
0x140004a6c  xor     edx, edx; bInheritHandle
0x140004a6e  lea     ecx, [rdx+2]; dwDesiredAccess
0x140004a71  call    cs:__imp_OpenEventW
0x140004a77  mov     rdi, rax
0x140004a7a  test    rax, rax
0x140004a7d  jz      short loc_140004A91
0x140004a7f  mov     rcx, rax; hEvent
0x140004a82  call    cs:__imp_SetEvent
0x140004a88  mov     rcx, rdi; hObject
0x140004a8b  call    cs:__imp_CloseHandle
0x140004a91  mov     rcx, [rbp+lpName]; P
0x140004a95  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140004a9a  inc     ebx
0x140004a9c  cmp     ebx, [rbp+arg_0]
0x140004a9f  jb      short loc_140004A47
0x140004aa1  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x140004aa5  call    cs:__imp_WTSFreeMemory
0x140004aab  add     rsp, 40h
0x140004aaf  pop     rdi
0x140004ab0  pop     rbx
0x140004ab1  pop     rbp
0x140004ab2  retn
```
