# BdeSvcWorkTracking::BdeSvcWorkStopTransition(_TP_CALLBACK_INSTANCE *)

- ea: `0x180008b70`
- end: `0x180008f3d`
- name: `?BdeSvcWorkStopTransition@BdeSvcWorkTracking@@AEAAXPEAU_TP_CALLBACK_INSTANCE@@@Z`
- size: `973`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct _TP_CALLBACK_INSTANCE *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180009c30`
- `0x180040d30`

## callees

- `0x180008b70`
- `0x180009f30`
- `0x180009f60`
- `0x180034070`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008bc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008bc7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008cac`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008cac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008bad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008bad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008c3f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008de2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e75`

## pseudocode

```c
void __fastcall BdeSvcWorkTracking::BdeSvcWorkStopTransition(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _TP_CALLBACK_INSTANCE *a2)
{
  char v4; // bp
  DWORD CurrentThreadId; // esi
  HANDLE v6; // rbx
  PVOID *v7; // rcx
  DWORD v8; // eax
  DWORD v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  DWORD LastError; // eax
  void *v13; // rcx
  void (__fastcall *LockSemaphore)(struct _TP_CALLBACK_INSTANCE *); // rbx
  HANDLE Handles[2]; // [rsp+30h] [rbp-48h] BYREF

  v4 = 0;
  CurrentThreadId = GetCurrentThreadId();
  AcquireSRWLockShared(&g_srwlStopEvent);
  v6 = g_hStopEvent;
  ReleaseSRWLockShared(&g_srwlStopEvent);
  Handles[1] = *(HANDLE *)&lpCriticalSection[1].LockCount;
  Handles[0] = v6;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      WPP_SF_d(v7[2], 37, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, CurrentThreadId);
  }
  while ( 1 )
  {
    EnterCriticalSection(lpCriticalSection);
    if ( LODWORD(lpCriticalSection[1].OwningThread) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      goto LABEL_24;
    }
    if ( WaitForSingleObject(*(HANDLE *)&lpCriticalSection[1].LockCount, 0) != 258 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      BYTE4(lpCriticalSection[1].OwningThread) = 0;
LABEL_24:
      LeaveCriticalSection(lpCriticalSection);
      goto LABEL_26;
    }
    if ( v4 )
      break;
    LeaveCriticalSection(lpCriticalSection);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    v8 = WaitForMultipleObjectsEx(2u, Handles, 0, 0x2BF20u, 0);
    v9 = v8;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v8);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 == 1 )
    {
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
      {
        v11 = 44;
        goto LABEL_18;
      }
    }
    else if ( v9 )
    {
      if ( v9 != 258 && v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, LastError);
      }
      v4 = 1;
    }
    else
    {
      v4 = 1;
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
      {
        v11 = 43;
LABEL_18:
        WPP_SF_(v10[2], v11, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  v13 = *(void **)&lpCriticalSection[1].LockCount;
  LockSemaphore = (void (__fastcall *)(struct _TP_CALLBACK_INSTANCE *))lpCriticalSection[1].LockSemaphore;
  LODWORD(lpCriticalSection[1].OwningThread) = 1;
  lpCriticalSection[1].LockSemaphore = 0;
  if ( v13 )
  {
    CloseHandle(v13);
    *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( LockSemaphore )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    LockSemaphore(a2);
  }
LABEL_26:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
}

```

## disassembly

```asm
0x180008b70  mov     [rsp+arg_10], rbx
0x180008b75  push    rbp
0x180008b76  push    rsi
0x180008b77  push    rdi
0x180008b78  push    r14
0x180008b7a  push    r15
0x180008b7c  sub     rsp, 50h
0x180008b80  mov     rax, cs:__security_cookie
0x180008b87  xor     rax, rsp
0x180008b8a  mov     [rsp+78h+var_38], rax
0x180008b8f  mov     r14, rdx
0x180008b92  mov     rdi, rcx
0x180008b95  xor     bpl, bpl
0x180008b98  call    cs:__imp_GetCurrentThreadId
0x180008b9f  nop     dword ptr [rax+rax+00h]
0x180008ba4  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x180008bab  mov     esi, eax
0x180008bad  call    cs:__imp_AcquireSRWLockShared
0x180008bb4  nop     dword ptr [rax+rax+00h]
0x180008bb9  mov     rbx, cs:?g_hStopEvent@@3REAXEA; void * g_hStopEvent
0x180008bc0  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x180008bc7  call    cs:__imp_ReleaseSRWLockShared
0x180008bce  nop     dword ptr [rax+rax+00h]
0x180008bd3  mov     rcx, [rdi+30h]
0x180008bd7  mov     [rsp+78h+var_40], rcx
0x180008bdc  mov     [rsp+78h+Handles], rbx
0x180008be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008be8  lea     r15, WPP_GLOBAL_Control
0x180008bef  cmp     rcx, r15
0x180008bf2  jz      short loc_180008C1F
0x180008bf4  test    byte ptr [rcx+1Ch], 20h
0x180008bf8  jz      short loc_180008C16
0x180008bfa  mov     rcx, [rcx+10h]
0x180008bfe  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008c05  mov     edx, 24h ; '$'
0x180008c0a  call    WPP_SF_
0x180008c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c16  cmp     rcx, r15
0x180008c19  jnz     loc_180008DA8
0x180008c1f  xor     esi, esi
0x180008c21  mov     rcx, rdi; lpCriticalSection
0x180008c24  call    cs:__imp_EnterCriticalSection
0x180008c2b  nop     dword ptr [rax+rax+00h]
0x180008c30  cmp     [rdi+38h], esi
0x180008c33  jnz     loc_180008EE5
0x180008c39  mov     rcx, [rdi+30h]; hHandle
0x180008c3d  xor     edx, edx; dwMilliseconds
0x180008c3f  call    cs:__imp_WaitForSingleObject
0x180008c46  nop     dword ptr [rax+rax+00h]
0x180008c4b  cmp     eax, 102h
0x180008c50  jnz     loc_180008D39
0x180008c56  test    bpl, bpl
0x180008c59  jnz     loc_180008E32
0x180008c5f  mov     rcx, rdi; lpCriticalSection
0x180008c62  call    cs:__imp_LeaveCriticalSection
0x180008c69  nop     dword ptr [rax+rax+00h]
0x180008c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c75  cmp     rcx, r15
0x180008c78  jz      short loc_180008C95
0x180008c7a  test    byte ptr [rcx+1Ch], 8
0x180008c7e  jz      short loc_180008C95
0x180008c80  mov     rcx, [rcx+10h]
0x180008c84  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008c8b  mov     edx, 29h ; ')'
0x180008c90  call    WPP_SF_
0x180008c95  mov     r9d, 2BF20h; dwMilliseconds
0x180008c9b  mov     [rsp+78h+bAlertable], esi; bAlertable
0x180008c9f  xor     r8d, r8d; bWaitAll
0x180008ca2  lea     rdx, [rsp+78h+Handles]; lpHandles
0x180008ca7  mov     ecx, 2; nCount
0x180008cac  call    cs:__imp_WaitForMultipleObjectsEx
0x180008cb3  nop     dword ptr [rax+rax+00h]
0x180008cb8  mov     ebx, eax
0x180008cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cc1  cmp     rcx, r15
0x180008cc4  jz      short loc_180008CEB
0x180008cc6  test    byte ptr [rcx+1Ch], 8
0x180008cca  jz      short loc_180008CEB
0x180008ccc  mov     rcx, [rcx+10h]
0x180008cd0  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008cd7  mov     edx, 2Ah ; '*'
0x180008cdc  mov     r9d, eax
0x180008cdf  call    WPP_SF_d
0x180008ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ceb  cmp     ebx, 1
0x180008cee  jnz     short loc_180008D1D
0x180008cf0  cmp     rcx, r15
0x180008cf3  jz      loc_180008C21
0x180008cf9  test    byte ptr [rcx+1Ch], 8
0x180008cfd  jz      loc_180008C21
0x180008d03  mov     edx, 2Ch ; ','
0x180008d08  mov     rcx, [rcx+10h]
0x180008d0c  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008d13  call    WPP_SF_
0x180008d18  jmp     loc_180008C21
0x180008d1d  test    ebx, ebx
0x180008d1f  jz      loc_180008E12
0x180008d25  cmp     ebx, 102h
0x180008d2b  jnz     loc_180008DCF
0x180008d31  mov     bpl, 1
0x180008d34  jmp     loc_180008C21
0x180008d39  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d40  cmp     rcx, r15
0x180008d43  jnz     loc_180008EC1
0x180008d49  mov     [rdi+3Ch], sil
0x180008d4d  mov     rcx, rdi; lpCriticalSection
0x180008d50  call    cs:__imp_LeaveCriticalSection
0x180008d57  nop     dword ptr [rax+rax+00h]
0x180008d5c  jmp     short loc_180008D76
0x180008d5e  mov     rcx, rdi; lpCriticalSection
0x180008d61  call    cs:__imp_LeaveCriticalSection
0x180008d68  nop     dword ptr [rax+rax+00h]
0x180008d6d  test    rbx, rbx
0x180008d70  jnz     loc_180008E8A
0x180008d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d7d  cmp     rcx, r15
0x180008d80  jnz     loc_180008F19
0x180008d86  mov     rcx, [rsp+78h+var_38]
0x180008d8b  xor     rcx, rsp; StackCookie
0x180008d8e  call    __security_check_cookie
0x180008d93  mov     rbx, [rsp+78h+arg_10]
0x180008d9b  add     rsp, 50h
0x180008d9f  pop     r15
0x180008da1  pop     r14
0x180008da3  pop     rdi
0x180008da4  pop     rsi
0x180008da5  pop     rbp
0x180008da6  retn
0x180008da8  test    byte ptr [rcx+1Ch], 8
0x180008dac  jz      loc_180008C1F
0x180008db2  mov     rcx, [rcx+10h]
0x180008db6  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008dbd  mov     edx, 25h ; '%'
0x180008dc2  mov     r9d, esi
0x180008dc5  call    WPP_SF_d
0x180008dca  jmp     loc_180008C1F
0x180008dcf  cmp     rcx, r15
0x180008dd2  jz      loc_180008D31
0x180008dd8  test    byte ptr [rcx+1Ch], 2
0x180008ddc  jz      loc_180008D31
0x180008de2  call    cs:__imp_GetLastError
0x180008de9  nop     dword ptr [rax+rax+00h]
0x180008dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180008df5  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008dfc  mov     edx, 2Dh ; '-'
0x180008e01  mov     r9d, eax
0x180008e04  mov     rcx, [rcx+10h]
0x180008e08  call    WPP_SF_d
0x180008e0d  jmp     loc_180008D31
0x180008e12  mov     bpl, 1
0x180008e15  cmp     rcx, r15
0x180008e18  jz      loc_180008C21
0x180008e1e  test    byte ptr [rcx+1Ch], 8
0x180008e22  jz      loc_180008C21
0x180008e28  mov     edx, 2Bh ; '+'
0x180008e2d  jmp     loc_180008D08
0x180008e32  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e39  cmp     rcx, r15
0x180008e3c  jz      short loc_180008E59
0x180008e3e  test    byte ptr [rcx+1Ch], 8
0x180008e42  jz      short loc_180008E59
0x180008e44  mov     rcx, [rcx+10h]
0x180008e48  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008e4f  mov     edx, 28h ; '('
0x180008e54  call    WPP_SF_
0x180008e59  mov     rcx, [rdi+30h]; hObject
0x180008e5d  mov     rbx, [rdi+40h]
0x180008e61  mov     dword ptr [rdi+38h], 1
0x180008e68  mov     [rdi+40h], rsi
0x180008e6c  test    rcx, rcx
0x180008e6f  jz      loc_180008D5E
0x180008e75  call    cs:__imp_CloseHandle
0x180008e7c  nop     dword ptr [rax+rax+00h]
0x180008e81  mov     [rdi+30h], rsi
0x180008e85  jmp     loc_180008D5E
0x180008e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e91  cmp     rcx, r15
0x180008e94  jz      short loc_180008EB1
0x180008e96  test    byte ptr [rcx+1Ch], 8
0x180008e9a  jz      short loc_180008EB1
0x180008e9c  mov     rcx, [rcx+10h]
0x180008ea0  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008ea7  mov     edx, 2Eh ; '.'
0x180008eac  call    WPP_SF_
0x180008eb1  mov     rcx, r14
0x180008eb4  mov     rax, rbx
0x180008eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ebc  jmp     loc_180008D76
0x180008ec1  test    byte ptr [rcx+1Ch], 8
0x180008ec5  jz      loc_180008D49
0x180008ecb  mov     rcx, [rcx+10h]
0x180008ecf  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008ed6  mov     edx, 27h ; '''
0x180008edb  call    WPP_SF_
0x180008ee0  jmp     loc_180008D49
0x180008ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008eec  cmp     rcx, r15
0x180008eef  jz      loc_180008D4D
0x180008ef5  test    byte ptr [rcx+1Ch], 8
0x180008ef9  jz      loc_180008D4D
0x180008eff  mov     rcx, [rcx+10h]
0x180008f03  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008f0a  mov     edx, 26h ; '&'
0x180008f0f  call    WPP_SF_
0x180008f14  jmp     loc_180008D4D
0x180008f19  test    byte ptr [rcx+1Ch], 20h
0x180008f1d  jz      loc_180008D86
0x180008f23  mov     rcx, [rcx+10h]
0x180008f27  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008f2e  mov     edx, 2Fh ; '/'
0x180008f33  call    WPP_SF_
0x180008f38  jmp     loc_180008D86
```
