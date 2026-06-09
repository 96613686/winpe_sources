# BfeNotifySync

- ea: `0x180065454`
- end: `0x180065620`
- name: `BfeNotifySync`
- size: `460`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18006d4d4`
- `0x180070e6c`
- `0x180070fdc`
- `0x180071528`
- `0x180071c5c`

## callees

- `0x18000dab0`
- `0x18000e000`
- `0x18001236c`
- `0x180012a30`
- `0x180018b74`
- `0x180058b30`
- `0x1800595ac`
- `0x180065454`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1800655d0`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800655d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800654bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800654bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180065549`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180065549`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800654ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065554`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800654ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065554`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006553c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800655d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006553c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800655d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800654cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006558b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800654cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006558b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800655e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800655e8`

## string_xrefs

- `0x1800654d5`: `CreateEventW`

## pseudocode

```c
__int64 __fastcall BfeNotifySync(LPCRITICAL_SECTION lpCriticalSection, __int64 a2, DWORD a3, _QWORD *a4)
{
  DWORD LastError; // eax
  __int64 v9; // rcx
  __int64 v10; // rbx
  DWORD v11; // esi
  __int64 v12; // rcx
  unsigned int v13; // esi
  __int64 v14; // r8
  const char *v15; // rdx
  _BYTE v17[16]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v18; // [rsp+30h] [rbp-40h]
  __int64 v19; // [rsp+38h] [rbp-38h]
  unsigned int LockCount; // [rsp+40h] [rbp-30h]
  int v21; // [rsp+44h] [rbp-2Ch]
  __int64 v22; // [rsp+48h] [rbp-28h] BYREF
  int v23; // [rsp+50h] [rbp-20h]
  HANDLE hHandle; // [rsp+58h] [rbp-18h]

  memset_0(v17, 0, 0x40u);
  *a4 = 0;
  v19 = *(_QWORD *)(a2 + 8);
  v21 = *(_DWORD *)(a2 + 16);
  v22 = 0;
  v23 = 0;
  hHandle = CreateEventW(0, 0, 0, 0);
  if ( !hHandle )
  {
    LastError = GetLastError();
    v10 = WfpReportSysErrorAsWinError(v9, "CreateEventW", LastError);
    goto LABEL_19;
  }
  EnterCriticalSection(lpCriticalSection);
  LockCount = lpCriticalSection[1].LockCount;
  v18 = LockCount;
  v10 = WfpHashtableInsert(&lpCriticalSection[5].LockSemaphore, v17);
  if ( !v10 )
  {
    v23 = 1;
    v10 = BfeNotifyOneWay(lpCriticalSection);
    if ( !v10 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v11 = WaitForSingleObject(hHandle, a3);
      EnterCriticalSection(lpCriticalSection);
      v12 = v22;
      if ( !v22 )
      {
        if ( v11 == -1 )
        {
          v14 = GetLastError();
          v15 = "WaitForSingleObject";
LABEL_15:
          v10 = WfpReportSysErrorAsWinError(v12, v15, v14);
          goto LABEL_16;
        }
        v14 = 1460;
        if ( v11 != 258 )
          v14 = 1223;
LABEL_14:
        v15 = "BfeNotifySync";
        goto LABEL_15;
      }
      if ( *(_DWORD *)(v22 + 4) == 14 )
      {
        v13 = **(_DWORD **)(v22 + 8);
        if ( v13 )
        {
          WfpMemFree(&v22);
          v14 = v13;
          goto LABEL_14;
        }
      }
      *a4 = v22;
    }
  }
LABEL_16:
  if ( v23 )
    RtlRemoveEntryHashTable(&lpCriticalSection[5].LockSemaphore, v17, 0);
  LeaveCriticalSection(lpCriticalSection);
LABEL_19:
  if ( hHandle )
    CloseHandle(hHandle);
  if ( v10 )
    WfpReportError(v10, "BfeNotifySync");
  return v10;
}

```

## disassembly

```asm
0x180065454  push    rbp
0x180065456  push    rbx
0x180065457  push    rsi
0x180065458  push    rdi
0x180065459  push    r12
0x18006545b  push    r14
0x18006545d  push    r15
0x18006545f  mov     rbp, rsp
0x180065462  sub     rsp, 70h
0x180065466  mov     rax, cs:__security_cookie
0x18006546d  xor     rax, rsp
0x180065470  mov     [rbp+var_10], rax
0x180065474  mov     rsi, rdx
0x180065477  mov     r12d, r8d
0x18006547a  xor     edx, edx; Val
0x18006547c  mov     rdi, rcx
0x18006547f  lea     rcx, [rbp+var_50]; void *
0x180065483  mov     r15, r9
0x180065486  lea     r8d, [rdx+40h]; Size
0x18006548a  call    memset_0
0x18006548f  mov     qword ptr [r15], 0
0x180065496  xor     r9d, r9d; lpName
0x180065499  mov     rax, [rsi+8]
0x18006549d  xor     r8d, r8d; bInitialState
0x1800654a0  mov     [rbp+var_38], rax
0x1800654a4  xor     edx, edx; bManualReset
0x1800654a6  mov     eax, [rsi+10h]
0x1800654a9  xor     ecx, ecx; lpEventAttributes
0x1800654ab  mov     [rbp+var_2C], eax
0x1800654ae  mov     [rbp+var_28], 0
0x1800654b6  mov     [rbp+var_20], 0
0x1800654bd  call    cs:__imp_CreateEventW
0x1800654c3  mov     [rbp+hHandle], rax
0x1800654c7  test    rax, rax
0x1800654ca  jnz     short loc_1800654E9
0x1800654cc  call    cs:__imp_GetLastError
0x1800654d2  mov     r8d, eax
0x1800654d5  lea     rdx, aCreateeventw; "CreateEventW"
0x1800654dc  call    WfpReportSysErrorAsWinError
0x1800654e1  mov     rbx, rax
0x1800654e4  jmp     loc_1800655DF
0x1800654e9  mov     rcx, rdi; lpCriticalSection
0x1800654ec  call    cs:__imp_EnterCriticalSection
0x1800654f2  mov     eax, [rdi+30h]
0x1800654f5  lea     r14, [rdi+0E0h]
0x1800654fc  mov     rcx, r14
0x1800654ff  mov     [rbp+var_30], eax
0x180065502  lea     rdx, [rbp+var_50]
0x180065506  mov     [rbp+var_40], rax
0x18006550a  call    WfpHashtableInsert
0x18006550f  mov     rbx, rax
0x180065512  test    rax, rax
0x180065515  jnz     loc_1800655C0
0x18006551b  mov     rdx, rsi
0x18006551e  mov     [rbp+var_20], 1
0x180065525  mov     rcx, rdi; lpCriticalSection
0x180065528  call    BfeNotifyOneWay
0x18006552d  mov     rbx, rax
0x180065530  test    rax, rax
0x180065533  jnz     loc_1800655C0
0x180065539  mov     rcx, rdi; lpCriticalSection
0x18006553c  call    cs:__imp_LeaveCriticalSection
0x180065542  mov     rcx, [rbp+hHandle]; hHandle
0x180065546  mov     edx, r12d; dwMilliseconds
0x180065549  call    cs:__imp_WaitForSingleObject
0x18006554f  mov     rcx, rdi; lpCriticalSection
0x180065552  mov     esi, eax
0x180065554  call    cs:__imp_EnterCriticalSection
0x18006555a  mov     rcx, [rbp+var_28]
0x18006555e  test    rcx, rcx
0x180065561  jz      short loc_180065586
0x180065563  cmp     dword ptr [rcx+4], 0Eh
0x180065567  jnz     short loc_180065581
0x180065569  mov     rax, [rcx+8]
0x18006556d  mov     esi, [rax]
0x18006556f  test    esi, esi
0x180065571  jz      short loc_180065581
0x180065573  lea     rcx, [rbp+var_28]
0x180065577  call    WfpMemFree
0x18006557c  mov     r8d, esi
0x18006557f  jmp     short loc_1800655B1
0x180065581  mov     [r15], rcx
0x180065584  jmp     short loc_1800655C0
0x180065586  cmp     esi, 0FFFFFFFFh
0x180065589  jnz     short loc_18006559D
0x18006558b  call    cs:__imp_GetLastError
0x180065591  mov     r8d, eax
0x180065594  lea     rdx, aWaitforsingleo; "WaitForSingleObject"
0x18006559b  jmp     short loc_1800655B8
0x18006559d  mov     r8d, 5B4h
0x1800655a3  cmp     esi, 102h
0x1800655a9  jz      short loc_1800655B1
0x1800655ab  mov     r8d, 4C7h
0x1800655b1  lea     rdx, aBfenotifysync; "BfeNotifySync"
0x1800655b8  call    WfpReportSysErrorAsWinError
0x1800655bd  mov     rbx, rax
0x1800655c0  cmp     [rbp+var_20], 0
0x1800655c4  jz      short loc_1800655D6
0x1800655c6  xor     r8d, r8d
0x1800655c9  lea     rdx, [rbp+var_50]
0x1800655cd  mov     rcx, r14
0x1800655d0  call    cs:__imp_RtlRemoveEntryHashTable
0x1800655d6  mov     rcx, rdi; lpCriticalSection
0x1800655d9  call    cs:__imp_LeaveCriticalSection
0x1800655df  mov     rcx, [rbp+hHandle]; hObject
0x1800655e3  test    rcx, rcx
0x1800655e6  jz      short loc_1800655EE
0x1800655e8  call    cs:__imp_CloseHandle
0x1800655ee  test    rbx, rbx
0x1800655f1  jz      short loc_180065602
0x1800655f3  lea     rdx, aBfenotifysync; "BfeNotifySync"
0x1800655fa  mov     rcx, rbx
0x1800655fd  call    WfpReportError
0x180065602  mov     rax, rbx
0x180065605  mov     rcx, [rbp+var_10]
0x180065609  xor     rcx, rsp; StackCookie
0x18006560c  call    __security_check_cookie
0x180065611  add     rsp, 70h
0x180065615  pop     r15
0x180065617  pop     r14
0x180065619  pop     r12
0x18006561b  pop     rdi
0x18006561c  pop     rsi
0x18006561d  pop     rbx
0x18006561e  pop     rbp
0x18006561f  retn
```
