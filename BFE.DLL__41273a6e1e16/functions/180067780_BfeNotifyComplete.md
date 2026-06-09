# BfeNotifyComplete

- ea: `0x180067780`
- end: `0x1800678c2`
- name: `BfeNotifyComplete`
- size: `322`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180065da0`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x1800358d0`
- `0x18005aa60`
- `0x180067780`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180067807`
- `ntdll!RtlRemoveEntryHashTable` at `0x180067807`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800677f3`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800677f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180067836`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180067836`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800677b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800677b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067884`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067846`

## string_xrefs

- `0x180067872`: `BfeNotifyComplete`
- `0x180067895`: `BfeNotifyComplete`

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
0x180067780  mov     [rsp+arg_10], rbx
0x180067785  push    rbp
0x180067786  push    rsi
0x180067787  push    rdi
0x180067788  sub     rsp, 40h
0x18006778c  mov     rax, cs:__security_cookie
0x180067793  xor     rax, rsp
0x180067796  mov     [rsp+58h+var_20], rax
0x18006779b  xorps   xmm0, xmm0
0x18006779e  xor     eax, eax
0x1800677a0  movups  [rsp+58h+var_38], xmm0
0x1800677a5  mov     [rsp+58h+var_28], rax
0x1800677aa  mov     rsi, rdx
0x1800677ad  mov     rbp, rcx
0x1800677b0  call    cs:__imp_EnterCriticalSection
0x1800677b7  nop     dword ptr [rax+rax+00h]
0x1800677bc  mov     rax, [rsi]
0x1800677bf  lea     rbx, [rbp+0E0h]
0x1800677c6  lea     r8, [rsp+58h+var_38]
0x1800677cb  mov     rcx, rbx
0x1800677ce  mov     edx, [rax]
0x1800677d0  call    WfpHashtableFind
0x1800677d5  mov     rdi, rax
0x1800677d8  test    rax, rax
0x1800677db  jz      loc_18006786C
0x1800677e1  mov     rcx, [rsi]
0x1800677e4  mov     edx, [rcx]
0x1800677e6  mov     rcx, rbx
0x1800677e9  cmp     [rax+20h], edx
0x1800677ec  jz      short loc_180067801
0x1800677ee  lea     rdx, [rsp+58h+var_38]
0x1800677f3  call    cs:__imp_RtlGetNextEntryHashTable
0x1800677fa  nop     dword ptr [rax+rax+00h]
0x1800677ff  jmp     short loc_1800677D5
0x180067801  xor     r8d, r8d
0x180067804  mov     rdx, rdi
0x180067807  call    cs:__imp_RtlRemoveEntryHashTable
0x18006780e  nop     dword ptr [rax+rax+00h]
0x180067813  mov     dword ptr [rdi+30h], 0
0x18006781a  mov     rax, [rsi]
0x18006781d  mov     ecx, [rax+4]
0x180067820  cmp     ecx, [rdi+24h]
0x180067823  jz      short loc_180067832
0x180067825  cmp     ecx, 0Eh
0x180067828  jz      short loc_180067832
0x18006782a  mov     r8d, 65Dh
0x180067830  jmp     short loc_180067872
0x180067832  mov     rcx, [rdi+38h]; hEvent
0x180067836  call    cs:__imp_SetEvent
0x18006783d  nop     dword ptr [rax+rax+00h]
0x180067842  test    eax, eax
0x180067844  jnz     short loc_18006785E
0x180067846  call    cs:__imp_GetLastError
0x18006784d  nop     dword ptr [rax+rax+00h]
0x180067852  mov     r8d, eax
0x180067855  lea     rdx, aSetevent; "SetEvent"
0x18006785c  jmp     short loc_180067879
0x18006785e  mov     rax, [rsi]
0x180067861  xor     ebx, ebx
0x180067863  mov     [rdi+28h], rax
0x180067867  mov     [rsi], rbx
0x18006786a  jmp     short loc_180067881
0x18006786c  mov     r8d, 5B4h
0x180067872  lea     rdx, aBfenotifycompl; "BfeNotifyComplete"
0x180067879  call    WfpReportSysErrorAsWinError
0x18006787e  mov     rbx, rax
0x180067881  mov     rcx, rbp; lpCriticalSection
0x180067884  call    cs:__imp_LeaveCriticalSection
0x18006788b  nop     dword ptr [rax+rax+00h]
0x180067890  test    rbx, rbx
0x180067893  jz      short loc_1800678A4
0x180067895  lea     rdx, aBfenotifycompl; "BfeNotifyComplete"
0x18006789c  mov     rcx, rbx
0x18006789f  call    WfpReportError
0x1800678a4  mov     rax, rbx
0x1800678a7  mov     rcx, [rsp+58h+var_20]
0x1800678ac  xor     rcx, rsp; StackCookie
0x1800678af  call    __security_check_cookie
0x1800678b4  mov     rbx, [rsp+58h+arg_10]
0x1800678b9  add     rsp, 40h
0x1800678bd  pop     rdi
0x1800678be  pop     rsi
0x1800678bf  pop     rbp
0x1800678c0  retn
```
