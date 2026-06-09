# WwanNhIntfInit(_GUID *)

- ea: `0x180017370`
- end: `0x18001763a`
- name: `?WwanNhIntfInit@@YAKPEAU_GUID@@@Z`
- size: `714`
- prototype: `unsigned int __fastcall(struct _GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180015ac8`
- `0x18008d844`

## callees

- `0x180012300`
- `0x180017370`
- `0x1800b6714`
- `0x1800b6a40`
- `0x1800b6ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001738a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001738a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800175e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017622`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800175e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017622`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800175cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800175cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017409`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017448`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017487`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800174c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017409`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017448`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017487`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800174c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800173c4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800173c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175c3`

## string_xrefs

- `0x1800173d4`: `Notification dispatcher: Error %d creating stop event for notification thread. Aborting thread creation`
- `0x18001741e`: `Notification dispatcher: Error %d creating stop event for notification thread. Aborting thread creation`
- `0x18001745d`: `Notification dispatcher: Error %d creating stop event for notification thread. Aborting thread creation`
- `0x18001749c`: `Notification dispatcher: Error %d creating stop event for notification thread. Aborting thread creation`
- `0x1800174db`: `Notification dispatcher: Error %d creating stop event for notification thread. Aborting thread creation`
- `0x180017573`: `Notification dispatcher: Error %d creating thread to dispatch notifications for (GUID: 0x%x 0x%x 0x%x 0x%x 0x%x 0x%x 0x%x 0x%x 0x%x 0x%x 0x%x)`

## pseudocode

```c
__int64 __fastcall WwanNhIntfInit(struct _GUID *a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  __int64 LastError; // r14
  HANDLE EventW; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v6; // rax
  HANDLE v7; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v8; // rax
  struct _WWAN_TP *v9; // r8
  _QWORD *v11; // rcx

  EnterCriticalSection(&stru_180152910);
  v2 = (struct _RTL_CRITICAL_SECTION *)WwanMemAlloc(0x80u);
  v3 = v2;
  if ( !v2 )
  {
    LODWORD(LastError) = 0;
    WwanLog::Error(
      "WwanNhIntfInit",
      0,
      L"Notification dispatcher: failed to allocate memory for new interface notification node.");
LABEL_20:
    LeaveCriticalSection(&stru_180152910);
    return (unsigned int)LastError;
  }
  if ( !InitializeCriticalSectionAndSpinCount(v2, 0) )
  {
    LastError = GetLastError();
    WwanLog::Error(
      "WwanNhIntfInit",
      0,
      L"Notification dispatcher: Error %d creating stop event for notification thread. Aborting thread creation",
      LastError);
LABEL_19:
    WwanMemFree(v3);
    goto LABEL_20;
  }
  *(_QWORD *)&v3[1].LockCount = v3 + 1;
  v3[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&v3[1];
  EventW = CreateEventW(0, 0, 0, 0);
  v3[1].SpinCount = (ULONG_PTR)EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    WwanLog::Error(
      "WwanNhIntfInit",
      0,
      L"Notification dispatcher: Error %d creating stop event for notification thread. Aborting thread creation",
      LastError);
LABEL_18:
    DeleteCriticalSection(v3);
    goto LABEL_19;
  }
  v6 = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateEventW(0, 0, 0, 0);
  v3[2].DebugInfo = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    WwanLog::Error(
      "WwanNhIntfInit",
      0,
      L"Notification dispatcher: Error %d creating stop event for notification thread. Aborting thread creation",
      LastError);
LABEL_17:
    CloseHandle((HANDLE)v3[1].SpinCount);
    goto LABEL_18;
  }
  v7 = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)&v3[2].LockCount = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    WwanLog::Error(
      "WwanNhIntfInit",
      0,
      L"Notification dispatcher: Error %d creating stop event for notification thread. Aborting thread creation",
      LastError);
LABEL_16:
    CloseHandle(v3[2].DebugInfo);
    goto LABEL_17;
  }
  v8 = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateEventW(0, 0, 0, 0);
  v3[3].DebugInfo = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    WwanLog::Error(
      "WwanNhIntfInit",
      0,
      L"Notification dispatcher: Error %d creating stop event for notification thread. Aborting thread creation",
      LastError);
LABEL_15:
    CloseHandle(*(HANDLE *)&v3[2].LockCount);
    goto LABEL_16;
  }
  *(struct _GUID *)&v3[2].OwningThread = *a1;
  LODWORD(LastError) = WwanCreateThread((unsigned int (*)(void *))NhDispatchNotification, v3, v9, 1);
  if ( (_DWORD)LastError )
  {
    WwanLog::Error(
      "WwanNhIntfInit",
      0,
      L"Notification dispatcher: Error %d creating thread to dispatch notifications for (GUID: 0x%x 0x%x 0x%x 0x%x 0x%x 0x"
       "%x 0x%x 0x%x 0x%x 0x%x 0x%x)",
      (unsigned int)LastError,
      a1->Data1,
      a1->Data2,
      a1->Data3,
      a1->Data4[0],
      a1->Data4[1],
      a1->Data4[2],
      a1->Data4[3],
      a1->Data4[4],
      a1->Data4[5],
      a1->Data4[6],
      a1->Data4[7]);
    CloseHandle(v3[3].DebugInfo);
    goto LABEL_15;
  }
  v11 = (_QWORD *)qword_180152940;
  if ( *(__int64 **)qword_180152940 != &qword_180152938 )
    __fastfail(3u);
  v3[1].LockSemaphore = (HANDLE)qword_180152940;
  v3[1].OwningThread = &qword_180152938;
  *v11 = (char *)v3 + 56;
  qword_180152940 = (__int64)&v3[1].OwningThread;
  LeaveCriticalSection(&stru_180152910);
  return 0;
}

```

## disassembly

```asm
0x180017370  push    rbx
0x180017372  push    rbp
0x180017373  push    rsi
0x180017374  push    rdi
0x180017375  push    r14
0x180017377  push    r15
0x180017379  sub     rsp, 88h
0x180017380  mov     r15, rcx
0x180017383  lea     rcx, stru_180152910; lpCriticalSection
0x18001738a  call    cs:__imp_EnterCriticalSection
0x180017390  mov     ecx, 80h; Size
0x180017395  call    WwanMemAlloc
0x18001739a  mov     rbp, rax
0x18001739d  test    rax, rax
0x1800173a0  jnz     short loc_1800173BF
0x1800173a2  xor     r14d, r14d
0x1800173a5  lea     r8, aNotificationDi_9; "Notification dispatcher: failed to allo"...
0x1800173ac  xor     edx, edx; struct _GUID *
0x1800173ae  lea     rcx, aWwannhintfinit_0; "WwanNhIntfInit"
0x1800173b5  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800173ba  jmp     loc_1800175DA
0x1800173bf  xor     edx, edx; dwSpinCount
0x1800173c1  mov     rcx, rbp; lpCriticalSection
0x1800173c4  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800173ca  test    eax, eax
0x1800173cc  jnz     short loc_1800173F4
0x1800173ce  call    cs:__imp_GetLastError
0x1800173d4  lea     r8, aNotificationDi_0; "Notification dispatcher: Error %d creat"...
0x1800173db  xor     edx, edx; struct _GUID *
0x1800173dd  mov     r9d, eax
0x1800173e0  lea     rcx, aWwannhintfinit_0; "WwanNhIntfInit"
0x1800173e7  mov     r14d, eax
0x1800173ea  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800173ef  jmp     loc_1800175D2
0x1800173f4  lea     rax, [rbp+28h]
0x1800173f8  xor     r9d, r9d; lpName
0x1800173fb  xor     r8d, r8d; bInitialState
0x1800173fe  mov     [rax+8], rax
0x180017402  xor     edx, edx; bManualReset
0x180017404  mov     [rax], rax
0x180017407  xor     ecx, ecx; lpEventAttributes
0x180017409  call    cs:__imp_CreateEventW
0x18001740f  mov     [rbp+48h], rax
0x180017413  test    rax, rax
0x180017416  jnz     short loc_18001743E
0x180017418  call    cs:__imp_GetLastError
0x18001741e  lea     r8, aNotificationDi_0; "Notification dispatcher: Error %d creat"...
0x180017425  xor     edx, edx; struct _GUID *
0x180017427  mov     r9d, eax
0x18001742a  lea     rcx, aWwannhintfinit_0; "WwanNhIntfInit"
0x180017431  mov     r14d, eax
0x180017434  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180017439  jmp     loc_1800175C9
0x18001743e  xor     r9d, r9d; lpName
0x180017441  xor     r8d, r8d; bInitialState
0x180017444  xor     edx, edx; bManualReset
0x180017446  xor     ecx, ecx; lpEventAttributes
0x180017448  call    cs:__imp_CreateEventW
0x18001744e  mov     [rbp+50h], rax
0x180017452  test    rax, rax
0x180017455  jnz     short loc_18001747D
0x180017457  call    cs:__imp_GetLastError
0x18001745d  lea     r8, aNotificationDi_0; "Notification dispatcher: Error %d creat"...
0x180017464  xor     edx, edx; struct _GUID *
0x180017466  mov     r9d, eax
0x180017469  lea     rcx, aWwannhintfinit_0; "WwanNhIntfInit"
0x180017470  mov     r14d, eax
0x180017473  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180017478  jmp     loc_1800175BF
0x18001747d  xor     r9d, r9d; lpName
0x180017480  xor     r8d, r8d; bInitialState
0x180017483  xor     edx, edx; bManualReset
0x180017485  xor     ecx, ecx; lpEventAttributes
0x180017487  call    cs:__imp_CreateEventW
0x18001748d  mov     [rbp+58h], rax
0x180017491  test    rax, rax
0x180017494  jnz     short loc_1800174BC
0x180017496  call    cs:__imp_GetLastError
0x18001749c  lea     r8, aNotificationDi_0; "Notification dispatcher: Error %d creat"...
0x1800174a3  xor     edx, edx; struct _GUID *
0x1800174a5  mov     r9d, eax
0x1800174a8  lea     rcx, aWwannhintfinit_0; "WwanNhIntfInit"
0x1800174af  mov     r14d, eax
0x1800174b2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800174b7  jmp     loc_1800175B5
0x1800174bc  xor     r9d, r9d; lpName
0x1800174bf  xor     r8d, r8d; bInitialState
0x1800174c2  xor     edx, edx; bManualReset
0x1800174c4  xor     ecx, ecx; lpEventAttributes
0x1800174c6  call    cs:__imp_CreateEventW
0x1800174cc  mov     [rbp+78h], rax
0x1800174d0  test    rax, rax
0x1800174d3  jnz     short loc_1800174FB
0x1800174d5  call    cs:__imp_GetLastError
0x1800174db  lea     r8, aNotificationDi_0; "Notification dispatcher: Error %d creat"...
0x1800174e2  xor     edx, edx; struct _GUID *
0x1800174e4  mov     r9d, eax
0x1800174e7  lea     rcx, aWwannhintfinit_0; "WwanNhIntfInit"
0x1800174ee  mov     r14d, eax
0x1800174f1  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800174f6  jmp     loc_1800175AB
0x1800174fb  movups  xmm0, xmmword ptr [r15]
0x1800174ff  mov     r9d, 1; int
0x180017505  lea     rcx, _NhDispatchNotification; unsigned int (*)(void *)
0x18001750c  mov     rdx, rbp; void *
0x18001750f  movdqu  xmmword ptr [rbp+60h], xmm0
0x180017514  call    ?WwanCreateThread@@YAKP6AKPEAX@Z0PEAU_WWAN_TP@@H@Z; WwanCreateThread(ulong (*)(void *),void *,_WWAN_TP *,int)
0x180017519  mov     r14d, eax
0x18001751c  test    eax, eax
0x18001751e  jz      loc_1800175EC
0x180017524  movzx   eax, byte ptr [r15+0Fh]
0x180017529  movzx   ecx, byte ptr [r15+0Eh]
0x18001752e  movzx   edx, byte ptr [r15+0Dh]
0x180017533  movzx   r8d, byte ptr [r15+0Ch]
0x180017538  movzx   r9d, byte ptr [r15+0Bh]
0x18001753d  movzx   r10d, byte ptr [r15+0Ah]
0x180017542  movzx   r11d, byte ptr [r15+9]
0x180017547  movzx   ebx, byte ptr [r15+8]
0x18001754c  movzx   edi, word ptr [r15+6]
0x180017551  movzx   esi, word ptr [r15+4]
0x180017556  mov     [rsp+0B8h+var_48], eax
0x18001755a  mov     eax, [r15]
0x18001755d  mov     [rsp+0B8h+var_50], ecx
0x180017561  lea     rcx, aWwannhintfinit_0; "WwanNhIntfInit"
0x180017568  mov     [rsp+0B8h+var_58], edx
0x18001756c  xor     edx, edx; struct _GUID *
0x18001756e  mov     [rsp+0B8h+var_60], r8d
0x180017573  lea     r8, aNotificationDi; "Notification dispatcher: Error %d creat"...
0x18001757a  mov     [rsp+0B8h+var_68], r9d
0x18001757f  mov     r9d, r14d
0x180017582  mov     [rsp+0B8h+var_70], r10d
0x180017587  mov     [rsp+0B8h+var_78], r11d
0x18001758c  mov     [rsp+0B8h+var_80], ebx
0x180017590  mov     [rsp+0B8h+var_88], edi
0x180017594  mov     [rsp+0B8h+var_90], esi
0x180017598  mov     [rsp+0B8h+var_98], eax
0x18001759c  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800175a1  mov     rcx, [rbp+78h]; hObject
0x1800175a5  call    cs:__imp_CloseHandle
0x1800175ab  mov     rcx, [rbp+58h]; hObject
0x1800175af  call    cs:__imp_CloseHandle
0x1800175b5  mov     rcx, [rbp+50h]; hObject
0x1800175b9  call    cs:__imp_CloseHandle
0x1800175bf  mov     rcx, [rbp+48h]; hObject
0x1800175c3  call    cs:__imp_CloseHandle
0x1800175c9  mov     rcx, rbp; lpCriticalSection
0x1800175cc  call    cs:__imp_DeleteCriticalSection
0x1800175d2  mov     rcx, rbp
0x1800175d5  call    WwanMemFree
0x1800175da  lea     rcx, stru_180152910; lpCriticalSection
0x1800175e1  call    cs:__imp_LeaveCriticalSection
0x1800175e7  mov     eax, r14d
0x1800175ea  jmp     short loc_18001762A
0x1800175ec  mov     rcx, cs:qword_180152940
0x1800175f3  lea     rdx, qword_180152938
0x1800175fa  cmp     [rcx], rdx
0x1800175fd  jz      short loc_180017606
0x1800175ff  mov     ecx, 3
0x180017604  int     29h; Win8: RtlFailFast(ecx)
0x180017606  lea     rax, [rbp+38h]
0x18001760a  mov     [rax+8], rcx
0x18001760e  mov     [rax], rdx
0x180017611  mov     [rcx], rax
0x180017614  lea     rcx, stru_180152910; lpCriticalSection
0x18001761b  mov     cs:qword_180152940, rax
0x180017622  call    cs:__imp_LeaveCriticalSection
0x180017628  xor     eax, eax
0x18001762a  add     rsp, 88h
0x180017631  pop     r15
0x180017633  pop     r14
0x180017635  pop     rdi
0x180017636  pop     rsi
0x180017637  pop     rbp
0x180017638  pop     rbx
0x180017639  retn
```
