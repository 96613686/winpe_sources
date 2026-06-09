# BfeNotifySync

- ea: `0x1800678c8`
- end: `0x180067ad1`
- name: `BfeNotifySync`
- size: `521`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18006fbc0`
- `0x180073628`
- `0x1800737a4`
- `0x180073d40`
- `0x1800744b4`

## callees

- `0x18000e250`
- `0x18000e7e0`
- `0x180012d8c`
- `0x180013480`
- `0x1800197d0`
- `0x18005aa60`
- `0x18005b4fc`
- `0x1800678c8`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180067a6e`
- `ntdll!RtlRemoveEntryHashTable` at `0x180067a6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180067931`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180067931`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800679d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800679d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006796c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800679e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006796c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800679e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800679c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067a7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800679c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067a92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067a92`

## string_xrefs

- `0x180067955`: `CreateEventW`

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
0x1800678c8  push    rbp
0x1800678ca  push    rbx
0x1800678cb  push    rsi
0x1800678cc  push    rdi
0x1800678cd  push    r12
0x1800678cf  push    r14
0x1800678d1  push    r15
0x1800678d3  mov     rbp, rsp
0x1800678d6  sub     rsp, 70h
0x1800678da  mov     rax, cs:__security_cookie
0x1800678e1  xor     rax, rsp
0x1800678e4  mov     [rbp+var_10], rax
0x1800678e8  mov     rsi, rdx
0x1800678eb  mov     r12d, r8d
0x1800678ee  xor     edx, edx; Val
0x1800678f0  mov     rdi, rcx
0x1800678f3  lea     rcx, [rbp+var_50]; void *
0x1800678f7  mov     r15, r9
0x1800678fa  lea     r8d, [rdx+40h]; Size
0x1800678fe  call    memset_0
0x180067903  mov     qword ptr [r15], 0
0x18006790a  xor     r9d, r9d; lpName
0x18006790d  mov     rax, [rsi+8]
0x180067911  xor     r8d, r8d; bInitialState
0x180067914  mov     [rbp+var_38], rax
0x180067918  xor     edx, edx; bManualReset
0x18006791a  mov     eax, [rsi+10h]
0x18006791d  xor     ecx, ecx; lpEventAttributes
0x18006791f  mov     [rbp+var_2C], eax
0x180067922  mov     [rbp+var_28], 0
0x18006792a  mov     [rbp+var_20], 0
0x180067931  call    cs:__imp_CreateEventW
0x180067938  nop     dword ptr [rax+rax+00h]
0x18006793d  mov     [rbp+hHandle], rax
0x180067941  test    rax, rax
0x180067944  jnz     short loc_180067969
0x180067946  call    cs:__imp_GetLastError
0x18006794d  nop     dword ptr [rax+rax+00h]
0x180067952  mov     r8d, eax
0x180067955  lea     rdx, aCreateeventw; "CreateEventW"
0x18006795c  call    WfpReportSysErrorAsWinError
0x180067961  mov     rbx, rax
0x180067964  jmp     loc_180067A89
0x180067969  mov     rcx, rdi; lpCriticalSection
0x18006796c  call    cs:__imp_EnterCriticalSection
0x180067973  nop     dword ptr [rax+rax+00h]
0x180067978  mov     eax, [rdi+30h]
0x18006797b  lea     r14, [rdi+0E0h]
0x180067982  mov     rcx, r14
0x180067985  mov     [rbp+var_30], eax
0x180067988  lea     rdx, [rbp+var_50]
0x18006798c  mov     [rbp+var_40], rax
0x180067990  call    WfpHashtableInsert
0x180067995  mov     rbx, rax
0x180067998  test    rax, rax
0x18006799b  jnz     loc_180067A5E
0x1800679a1  mov     rdx, rsi
0x1800679a4  mov     [rbp+var_20], 1
0x1800679ab  mov     rcx, rdi; lpCriticalSection
0x1800679ae  call    BfeNotifyOneWay
0x1800679b3  mov     rbx, rax
0x1800679b6  test    rax, rax
0x1800679b9  jnz     loc_180067A5E
0x1800679bf  mov     rcx, rdi; lpCriticalSection
0x1800679c2  call    cs:__imp_LeaveCriticalSection
0x1800679c9  nop     dword ptr [rax+rax+00h]
0x1800679ce  mov     rcx, [rbp+hHandle]; hHandle
0x1800679d2  mov     edx, r12d; dwMilliseconds
0x1800679d5  call    cs:__imp_WaitForSingleObject
0x1800679dc  nop     dword ptr [rax+rax+00h]
0x1800679e1  mov     rcx, rdi; lpCriticalSection
0x1800679e4  mov     esi, eax
0x1800679e6  call    cs:__imp_EnterCriticalSection
0x1800679ed  nop     dword ptr [rax+rax+00h]
0x1800679f2  mov     rcx, [rbp+var_28]
0x1800679f6  test    rcx, rcx
0x1800679f9  jz      short loc_180067A1E
0x1800679fb  cmp     dword ptr [rcx+4], 0Eh
0x1800679ff  jnz     short loc_180067A19
0x180067a01  mov     rax, [rcx+8]
0x180067a05  mov     esi, [rax]
0x180067a07  test    esi, esi
0x180067a09  jz      short loc_180067A19
0x180067a0b  lea     rcx, [rbp+var_28]
0x180067a0f  call    WfpMemFree
0x180067a14  mov     r8d, esi
0x180067a17  jmp     short loc_180067A4F
0x180067a19  mov     [r15], rcx
0x180067a1c  jmp     short loc_180067A5E
0x180067a1e  cmp     esi, 0FFFFFFFFh
0x180067a21  jnz     short loc_180067A3B
0x180067a23  call    cs:__imp_GetLastError
0x180067a2a  nop     dword ptr [rax+rax+00h]
0x180067a2f  mov     r8d, eax
0x180067a32  lea     rdx, aWaitforsingleo; "WaitForSingleObject"
0x180067a39  jmp     short loc_180067A56
0x180067a3b  mov     r8d, 5B4h
0x180067a41  cmp     esi, 102h
0x180067a47  jz      short loc_180067A4F
0x180067a49  mov     r8d, 4C7h
0x180067a4f  lea     rdx, aBfenotifysync; "BfeNotifySync"
0x180067a56  call    WfpReportSysErrorAsWinError
0x180067a5b  mov     rbx, rax
0x180067a5e  cmp     [rbp+var_20], 0
0x180067a62  jz      short loc_180067A7A
0x180067a64  xor     r8d, r8d
0x180067a67  lea     rdx, [rbp+var_50]
0x180067a6b  mov     rcx, r14
0x180067a6e  call    cs:__imp_RtlRemoveEntryHashTable
0x180067a75  nop     dword ptr [rax+rax+00h]
0x180067a7a  mov     rcx, rdi; lpCriticalSection
0x180067a7d  call    cs:__imp_LeaveCriticalSection
0x180067a84  nop     dword ptr [rax+rax+00h]
0x180067a89  mov     rcx, [rbp+hHandle]; hObject
0x180067a8d  test    rcx, rcx
0x180067a90  jz      short loc_180067A9E
0x180067a92  call    cs:__imp_CloseHandle
0x180067a99  nop     dword ptr [rax+rax+00h]
0x180067a9e  test    rbx, rbx
0x180067aa1  jz      short loc_180067AB2
0x180067aa3  lea     rdx, aBfenotifysync; "BfeNotifySync"
0x180067aaa  mov     rcx, rbx
0x180067aad  call    WfpReportError
0x180067ab2  mov     rax, rbx
0x180067ab5  mov     rcx, [rbp+var_10]
0x180067ab9  xor     rcx, rsp; StackCookie
0x180067abc  call    __security_check_cookie
0x180067ac1  add     rsp, 70h
0x180067ac5  pop     r15
0x180067ac7  pop     r14
0x180067ac9  pop     r12
0x180067acb  pop     rdi
0x180067acc  pop     rsi
0x180067acd  pop     rbx
0x180067ace  pop     rbp
0x180067acf  retn
```
