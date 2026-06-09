# BfeNotifyComplete

- ea: `0x180065334`
- end: `0x18006544d`
- name: `BfeNotifyComplete`
- size: `281`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180063a40`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180036a50`
- `0x180058b30`
- `0x180065334`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1800653ab`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800653ab`
- `ntdll!RtlGetNextEntryHashTable` at `0x18006539d`
- `ntdll!RtlGetNextEntryHashTable` at `0x18006539d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800653d4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800653d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065364`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065364`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065416`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800653de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800653de`

## string_xrefs

- `0x180065404`: `BfeNotifyComplete`
- `0x180065421`: `BfeNotifyComplete`

## pseudocode

```c
__int64 __fastcall BfeNotifyComplete(LPCRITICAL_SECTION lpCriticalSection, unsigned int **a2)
{
  __int64 i; // rax
  __int64 v5; // rcx
  __int64 v6; // rdi
  HANDLE *p_LockSemaphore; // rcx
  __int64 LastError; // r8
  const char *v9; // rdx
  __int64 v10; // rbx
  __int128 v12; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+30h] [rbp-28h]

  v12 = 0;
  v13 = 0;
  EnterCriticalSection(lpCriticalSection);
  for ( i = WfpHashtableFind(&lpCriticalSection[5].LockSemaphore, **a2, &v12);
        ;
        i = RtlGetNextEntryHashTable(p_LockSemaphore, &v12) )
  {
    v6 = i;
    if ( !i )
    {
      LastError = 1460;
      goto LABEL_12;
    }
    p_LockSemaphore = &lpCriticalSection[5].LockSemaphore;
    if ( *(_DWORD *)(i + 32) == **a2 )
      break;
  }
  RtlRemoveEntryHashTable(p_LockSemaphore, i, 0);
  *(_DWORD *)(v6 + 48) = 0;
  v5 = (*a2)[1];
  if ( (_DWORD)v5 != *(_DWORD *)(v6 + 36) && (_DWORD)v5 != 14 )
  {
    LastError = 1629;
LABEL_12:
    v9 = "BfeNotifyComplete";
    goto LABEL_13;
  }
  if ( SetEvent(*(HANDLE *)(v6 + 56)) )
  {
    v10 = 0;
    *(_QWORD *)(v6 + 40) = *a2;
    *a2 = 0;
    goto LABEL_14;
  }
  LastError = GetLastError();
  v9 = "SetEvent";
LABEL_13:
  v10 = WfpReportSysErrorAsWinError(v5, v9, LastError);
LABEL_14:
  LeaveCriticalSection(lpCriticalSection);
  if ( v10 )
    WfpReportError(v10, "BfeNotifyComplete");
  return v10;
}

```

## disassembly

```asm
0x180065334  mov     [rsp+arg_10], rbx
0x180065339  push    rbp
0x18006533a  push    rsi
0x18006533b  push    rdi
0x18006533c  sub     rsp, 40h
0x180065340  mov     rax, cs:__security_cookie
0x180065347  xor     rax, rsp
0x18006534a  mov     [rsp+58h+var_20], rax
0x18006534f  xorps   xmm0, xmm0
0x180065352  xor     eax, eax
0x180065354  movups  [rsp+58h+var_38], xmm0
0x180065359  mov     [rsp+58h+var_28], rax
0x18006535e  mov     rsi, rdx
0x180065361  mov     rbp, rcx
0x180065364  call    cs:__imp_EnterCriticalSection
0x18006536a  mov     rax, [rsi]
0x18006536d  lea     rbx, [rbp+0E0h]
0x180065374  lea     r8, [rsp+58h+var_38]
0x180065379  mov     rcx, rbx
0x18006537c  mov     edx, [rax]
0x18006537e  call    WfpHashtableFind
0x180065383  mov     rdi, rax
0x180065386  test    rax, rax
0x180065389  jz      short loc_1800653FE
0x18006538b  mov     rcx, [rsi]
0x18006538e  mov     edx, [rcx]
0x180065390  mov     rcx, rbx
0x180065393  cmp     [rax+20h], edx
0x180065396  jz      short loc_1800653A5
0x180065398  lea     rdx, [rsp+58h+var_38]
0x18006539d  call    cs:__imp_RtlGetNextEntryHashTable
0x1800653a3  jmp     short loc_180065383
0x1800653a5  xor     r8d, r8d
0x1800653a8  mov     rdx, rdi
0x1800653ab  call    cs:__imp_RtlRemoveEntryHashTable
0x1800653b1  mov     dword ptr [rdi+30h], 0
0x1800653b8  mov     rax, [rsi]
0x1800653bb  mov     ecx, [rax+4]
0x1800653be  cmp     ecx, [rdi+24h]
0x1800653c1  jz      short loc_1800653D0
0x1800653c3  cmp     ecx, 0Eh
0x1800653c6  jz      short loc_1800653D0
0x1800653c8  mov     r8d, 65Dh
0x1800653ce  jmp     short loc_180065404
0x1800653d0  mov     rcx, [rdi+38h]; hEvent
0x1800653d4  call    cs:__imp_SetEvent
0x1800653da  test    eax, eax
0x1800653dc  jnz     short loc_1800653F0
0x1800653de  call    cs:__imp_GetLastError
0x1800653e4  mov     r8d, eax
0x1800653e7  lea     rdx, aSetevent; "SetEvent"
0x1800653ee  jmp     short loc_18006540B
0x1800653f0  mov     rax, [rsi]
0x1800653f3  xor     ebx, ebx
0x1800653f5  mov     [rdi+28h], rax
0x1800653f9  mov     [rsi], rbx
0x1800653fc  jmp     short loc_180065413
0x1800653fe  mov     r8d, 5B4h
0x180065404  lea     rdx, aBfenotifycompl; "BfeNotifyComplete"
0x18006540b  call    WfpReportSysErrorAsWinError
0x180065410  mov     rbx, rax
0x180065413  mov     rcx, rbp; lpCriticalSection
0x180065416  call    cs:__imp_LeaveCriticalSection
0x18006541c  test    rbx, rbx
0x18006541f  jz      short loc_180065430
0x180065421  lea     rdx, aBfenotifycompl; "BfeNotifyComplete"
0x180065428  mov     rcx, rbx
0x18006542b  call    WfpReportError
0x180065430  mov     rax, rbx
0x180065433  mov     rcx, [rsp+58h+var_20]
0x180065438  xor     rcx, rsp; StackCookie
0x18006543b  call    __security_check_cookie
0x180065440  mov     rbx, [rsp+58h+arg_10]
0x180065445  add     rsp, 40h
0x180065449  pop     rdi
0x18006544a  pop     rsi
0x18006544b  pop     rbp
0x18006544c  retn
```
