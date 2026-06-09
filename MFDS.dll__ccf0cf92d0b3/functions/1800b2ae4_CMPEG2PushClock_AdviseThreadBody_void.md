# CMPEG2PushClock::AdviseThreadBody(void)

- ea: `0x1800b2ae4`
- end: `0x1800b2da8`
- name: `?AdviseThreadBody@CMPEG2PushClock@@QEAAXXZ`
- size: `708`
- prototype: `void __fastcall(CMPEG2PushClock *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800b3b30`

## callees

- `0x180002820`
- `0x1800052c0`
- `0x18000b8c0`
- `0x18002d514`
- `0x1800b2ae4`
- `0x1800b35e0`
- `0x1800b3940`
- `0x1800b4004`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800b2cda`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800b2cda`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800b2c5f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800b2c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2bf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2c6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2bf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2c6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2bd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2c3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2bd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2c3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b2b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b2c20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b2c91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b2d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b2d59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b2b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b2c20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b2c91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b2d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b2d59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2b4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2c12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2c83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2cfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2d4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2b4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2c12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2c83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2cfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2d4b`

## string_xrefs

- `0x1800b2b07`: `CMPEG2PushClock::AdviseThreadBody`

## pseudocode

```c
void __fastcall CMPEG2PushClock::AdviseThreadBody(CMPEG2PushClock *this)
{
  char v2; // al
  DWORD v3; // esi
  DWORD CurrentThreadId; // ebx
  HANDLE CurrentThread; // rax
  DWORD v6; // ebx
  DWORD v7; // ebx
  HANDLE v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  DWORD v11; // ebx
  DWORD v12; // ebx
  HANDLE v13; // rax
  DWORD v14; // ebx
  HANDLE v15; // rax
  char v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v17 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v16, "CMPEG2PushClock::AdviseThreadBody", 1147);
  v2 = byte_1800EACCB;
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 24, &WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids, this);
    v2 = byte_1800EACCB;
  }
  v3 = -1;
  if ( (unsigned __int8)v2 >= 0x10u )
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentThread = GetCurrentThread();
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      25,
      &WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids,
      this,
      CurrentThread,
      CurrentThreadId);
  }
  while ( 1 )
  {
    v11 = WaitForMultipleObjectsEx(2u, (const HANDLE *)this + 38, 0, v3, 0);
    if ( !v11 )
      break;
    if ( (*(int (__fastcall **)(CMPEG2PushClock *, __int64 *))(*(_QWORD *)this + 24LL))(this, &v17) >= 0 )
    {
      v6 = v11 - 1;
      if ( v6 )
      {
        if ( v6 == 257 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)this + 8);
          v3 = CMPEG2PushClock::ProcessNotificationTimeoutLocked_(this, v17 + 10000);
          LeaveCriticalSection((LPCRITICAL_SECTION)this + 8);
          if ( (unsigned __int8)byte_1800EACCB >= 0x10u )
          {
            v7 = GetCurrentThreadId();
            v8 = GetCurrentThread();
            v10 = 27;
            goto LABEL_13;
          }
        }
      }
      else
      {
        EnterCriticalSection((LPCRITICAL_SECTION)this + 8);
        v3 = CMPEG2PushClock::ResetWaitTimeLocked_(this, v17);
        ResetEvent(*((HANDLE *)this + 39));
        LeaveCriticalSection((LPCRITICAL_SECTION)this + 8);
        if ( (unsigned __int8)byte_1800EACCB >= 0x10u )
        {
          v7 = GetCurrentThreadId();
          v8 = GetCurrentThread();
          v10 = 28;
LABEL_13:
          WPP_SF_qqDd(*((_QWORD *)WPP_GLOBAL_Control + 17), v10, v9, this, v8, v7, v3);
        }
      }
    }
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x10u )
  {
    v12 = GetCurrentThreadId();
    v13 = GetCurrentThread();
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      26,
      &WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids,
      this,
      v13,
      v12);
    if ( (unsigned __int8)byte_1800EACCB >= 0x10u )
    {
      v14 = GetCurrentThreadId();
      v15 = GetCurrentThread();
      WPP_SF_qqD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        29,
        &WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids,
        this,
        v15,
        v14);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
}

```

## disassembly

```asm
0x1800b2ae4  mov     [rsp+arg_10], rbx
0x1800b2ae9  push    rbp
0x1800b2aea  push    rsi
0x1800b2aeb  push    rdi
0x1800b2aec  sub     rsp, 40h
0x1800b2af0  mov     rdi, rcx
0x1800b2af3  mov     [rsp+58h+arg_8], 0
0x1800b2afc  lea     rcx, [rsp+58h+arg_0]; this
0x1800b2b01  mov     r8d, 47Bh; int
0x1800b2b07  lea     rdx, aCmpeg2pushcloc_6; "CMPEG2PushClock::AdviseThreadBody"
0x1800b2b0e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b2b13  mov     al, cs:byte_1800EACCB
0x1800b2b19  cmp     al, 20h ; ' '
0x1800b2b1b  jb      short loc_1800B2B45
0x1800b2b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2b24  lea     r8, WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids
0x1800b2b2b  mov     edx, 18h
0x1800b2b30  mov     r9, rdi
0x1800b2b33  mov     rcx, [rcx+88h]
0x1800b2b3a  call    WPP_SF_q
0x1800b2b3f  mov     al, cs:byte_1800EACCB
0x1800b2b45  or      esi, 0FFFFFFFFh
0x1800b2b48  cmp     al, 10h
0x1800b2b4a  jb      short loc_1800B2B91
0x1800b2b4c  call    cs:__imp_GetCurrentThreadId
0x1800b2b53  nop     dword ptr [rax+rax+00h]
0x1800b2b58  mov     ebx, eax
0x1800b2b5a  call    cs:__imp_GetCurrentThread
0x1800b2b61  nop     dword ptr [rax+rax+00h]
0x1800b2b66  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2b6d  lea     r8, WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids
0x1800b2b74  mov     edx, 19h
0x1800b2b79  mov     [rsp+58h+var_30], ebx
0x1800b2b7d  mov     r9, rdi
0x1800b2b80  mov     qword ptr [rsp+58h+bAlertable], rax
0x1800b2b85  mov     rcx, [rcx+88h]
0x1800b2b8c  call    WPP_SF_qqD
0x1800b2b91  lea     rbp, [rdi+130h]
0x1800b2b98  jmp     loc_1800B2CC5
0x1800b2b9d  mov     rax, [rdi]
0x1800b2ba0  lea     rdx, [rsp+58h+arg_8]
0x1800b2ba5  mov     rcx, rdi
0x1800b2ba8  mov     rax, [rax+18h]
0x1800b2bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2bb1  test    eax, eax
0x1800b2bb3  js      loc_1800B2CC5
0x1800b2bb9  sub     ebx, 1
0x1800b2bbc  jz      short loc_1800B2C33
0x1800b2bbe  cmp     ebx, 101h
0x1800b2bc4  jnz     loc_1800B2CC5
0x1800b2bca  lea     rbx, [rdi+140h]
0x1800b2bd1  mov     rcx, rbx; lpCriticalSection
0x1800b2bd4  call    cs:__imp_EnterCriticalSection
0x1800b2bdb  nop     dword ptr [rax+rax+00h]
0x1800b2be0  mov     rdx, [rsp+58h+arg_8]
0x1800b2be5  mov     rcx, rdi; this
0x1800b2be8  add     rdx, 2710h; __int64
0x1800b2bef  call    ?ProcessNotificationTimeoutLocked_@CMPEG2PushClock@@AEAAK_J@Z; CMPEG2PushClock::ProcessNotificationTimeoutLocked_(__int64)
0x1800b2bf4  mov     rcx, rbx; lpCriticalSection
0x1800b2bf7  mov     esi, eax
0x1800b2bf9  call    cs:__imp_LeaveCriticalSection
0x1800b2c00  nop     dword ptr [rax+rax+00h]
0x1800b2c05  cmp     cs:byte_1800EACCB, 10h
0x1800b2c0c  jb      loc_1800B2CC5
0x1800b2c12  call    cs:__imp_GetCurrentThreadId
0x1800b2c19  nop     dword ptr [rax+rax+00h]
0x1800b2c1e  mov     ebx, eax
0x1800b2c20  call    cs:__imp_GetCurrentThread
0x1800b2c27  nop     dword ptr [rax+rax+00h]
0x1800b2c2c  mov     edx, 1Bh
0x1800b2c31  jmp     short loc_1800B2CA2
0x1800b2c33  lea     rbx, [rdi+140h]
0x1800b2c3a  mov     rcx, rbx; lpCriticalSection
0x1800b2c3d  call    cs:__imp_EnterCriticalSection
0x1800b2c44  nop     dword ptr [rax+rax+00h]
0x1800b2c49  mov     rdx, [rsp+58h+arg_8]; __int64
0x1800b2c4e  mov     rcx, rdi; this
0x1800b2c51  call    ?ResetWaitTimeLocked_@CMPEG2PushClock@@AEAAK_J@Z; CMPEG2PushClock::ResetWaitTimeLocked_(__int64)
0x1800b2c56  mov     rcx, [rdi+138h]; hEvent
0x1800b2c5d  mov     esi, eax
0x1800b2c5f  call    cs:__imp_ResetEvent
0x1800b2c66  nop     dword ptr [rax+rax+00h]
0x1800b2c6b  mov     rcx, rbx; lpCriticalSection
0x1800b2c6e  call    cs:__imp_LeaveCriticalSection
0x1800b2c75  nop     dword ptr [rax+rax+00h]
0x1800b2c7a  cmp     cs:byte_1800EACCB, 10h
0x1800b2c81  jb      short loc_1800B2CC5
0x1800b2c83  call    cs:__imp_GetCurrentThreadId
0x1800b2c8a  nop     dword ptr [rax+rax+00h]
0x1800b2c8f  mov     ebx, eax
0x1800b2c91  call    cs:__imp_GetCurrentThread
0x1800b2c98  nop     dword ptr [rax+rax+00h]
0x1800b2c9d  mov     edx, 1Ch
0x1800b2ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2ca9  mov     r9, rdi
0x1800b2cac  mov     [rsp+58h+var_28], esi
0x1800b2cb0  mov     [rsp+58h+var_30], ebx
0x1800b2cb4  mov     qword ptr [rsp+58h+bAlertable], rax
0x1800b2cb9  mov     rcx, [rcx+88h]
0x1800b2cc0  call    WPP_SF_qqDd
0x1800b2cc5  xor     r8d, r8d; bWaitAll
0x1800b2cc8  mov     [rsp+58h+bAlertable], 0; bAlertable
0x1800b2cd0  mov     r9d, esi; dwMilliseconds
0x1800b2cd3  mov     rdx, rbp; lpHandles
0x1800b2cd6  lea     ecx, [r8+2]; nCount
0x1800b2cda  call    cs:__imp_WaitForMultipleObjectsEx
0x1800b2ce1  nop     dword ptr [rax+rax+00h]
0x1800b2ce6  mov     ebx, eax
0x1800b2ce8  test    eax, eax
0x1800b2cea  jnz     loc_1800B2B9D
0x1800b2cf0  cmp     cs:byte_1800EACCB, 10h
0x1800b2cf7  jb      loc_1800B2D90
0x1800b2cfd  call    cs:__imp_GetCurrentThreadId
0x1800b2d04  nop     dword ptr [rax+rax+00h]
0x1800b2d09  mov     ebx, eax
0x1800b2d0b  call    cs:__imp_GetCurrentThread
0x1800b2d12  nop     dword ptr [rax+rax+00h]
0x1800b2d17  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2d1e  lea     r8, WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids
0x1800b2d25  mov     edx, 1Ah
0x1800b2d2a  mov     [rsp+58h+var_30], ebx
0x1800b2d2e  mov     r9, rdi
0x1800b2d31  mov     qword ptr [rsp+58h+bAlertable], rax
0x1800b2d36  mov     rcx, [rcx+88h]
0x1800b2d3d  call    WPP_SF_qqD
0x1800b2d42  cmp     cs:byte_1800EACCB, 10h
0x1800b2d49  jb      short loc_1800B2D90
0x1800b2d4b  call    cs:__imp_GetCurrentThreadId
0x1800b2d52  nop     dword ptr [rax+rax+00h]
0x1800b2d57  mov     ebx, eax
0x1800b2d59  call    cs:__imp_GetCurrentThread
0x1800b2d60  nop     dword ptr [rax+rax+00h]
0x1800b2d65  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2d6c  lea     r8, WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids
0x1800b2d73  mov     edx, 1Dh
0x1800b2d78  mov     [rsp+58h+var_30], ebx
0x1800b2d7c  mov     r9, rdi
0x1800b2d7f  mov     qword ptr [rsp+58h+bAlertable], rax
0x1800b2d84  mov     rcx, [rcx+88h]
0x1800b2d8b  call    WPP_SF_qqD
0x1800b2d90  lea     rcx, [rsp+58h+arg_0]; this
0x1800b2d95  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b2d9a  mov     rbx, [rsp+58h+arg_10]
0x1800b2d9f  add     rsp, 40h
0x1800b2da3  pop     rdi
0x1800b2da4  pop     rsi
0x1800b2da5  pop     rbp
0x1800b2da6  retn
```
