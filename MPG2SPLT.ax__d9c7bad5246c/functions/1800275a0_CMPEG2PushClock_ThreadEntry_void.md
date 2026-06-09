# CMPEG2PushClock::ThreadEntry(void *)

- ea: `0x1800275a0`
- end: `0x18002766e`
- name: `?ThreadEntry@CMPEG2PushClock@@SAKPEAX@Z`
- size: `206`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180026bc8`
- `0x1800272e0`
- `0x1800275a0`
- `0x180034010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x180027653`
- `KERNEL32!WaitForMultipleObjects` at `0x180027653`
- `KERNEL32!ResetEvent` at `0x180027637`
- `KERNEL32!ResetEvent` at `0x180027637`
- `KERNEL32!LeaveCriticalSection` at `0x180027640`
- `KERNEL32!LeaveCriticalSection` at `0x180027640`
- `KERNEL32!EnterCriticalSection` at `0x1800275f3`
- `KERNEL32!EnterCriticalSection` at `0x18002761b`
- `KERNEL32!EnterCriticalSection` at `0x1800275f3`
- `KERNEL32!EnterCriticalSection` at `0x18002761b`

## pseudocode

```c
__int64 __fastcall CMPEG2PushClock::ThreadEntry(char *lpThreadParameter)
{
  DWORD v2; // esi
  const HANDLE *v3; // rbp
  DWORD v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  DWORD v6; // ebx
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v8 = 0;
  v2 = -1;
  v3 = (const HANDLE *)(lpThreadParameter + 304);
  while ( 1 )
  {
    v6 = WaitForMultipleObjects(2u, v3, 0, v2);
    if ( !v6 )
      return 0;
    if ( (*(int (__fastcall **)(char *, __int64 *))(*(_QWORD *)lpThreadParameter + 24LL))(lpThreadParameter, &v8) >= 0 )
    {
      v4 = v6 - 1;
      if ( v4 )
      {
        if ( v4 == 257 )
        {
          v5 = (struct _RTL_CRITICAL_SECTION *)(lpThreadParameter + 320);
          EnterCriticalSection((LPCRITICAL_SECTION)lpThreadParameter + 8);
          v2 = CMPEG2PushClock::ProcessNotificationTimeoutLocked_((CMPEG2PushClock *)lpThreadParameter, v8 + 10000);
          goto LABEL_7;
        }
      }
      else
      {
        v5 = (struct _RTL_CRITICAL_SECTION *)(lpThreadParameter + 320);
        EnterCriticalSection((LPCRITICAL_SECTION)lpThreadParameter + 8);
        v2 = CMPEG2PushClock::ResetWaitTimeLocked_((CMPEG2PushClock *)lpThreadParameter, v8);
        ResetEvent(*((HANDLE *)lpThreadParameter + 39));
LABEL_7:
        LeaveCriticalSection(v5);
      }
    }
  }
}

```

## disassembly

```asm
0x1800275a0  push    rbx
0x1800275a2  push    rbp
0x1800275a3  push    rsi
0x1800275a4  push    rdi
0x1800275a5  sub     rsp, 28h
0x1800275a9  mov     rdi, rcx
0x1800275ac  mov     [rsp+48h+arg_0], 0
0x1800275b5  or      esi, 0FFFFFFFFh
0x1800275b8  lea     rbp, [rcx+130h]
0x1800275bf  jmp     loc_180027646
0x1800275c4  mov     rax, [rdi]
0x1800275c7  lea     rdx, [rsp+48h+arg_0]
0x1800275cc  mov     rcx, rdi
0x1800275cf  mov     rax, [rax+18h]
0x1800275d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275d8  test    eax, eax
0x1800275da  js      short loc_180027646
0x1800275dc  sub     ebx, 1
0x1800275df  jz      short loc_180027611
0x1800275e1  cmp     ebx, 101h
0x1800275e7  jnz     short loc_180027646
0x1800275e9  lea     rbx, [rdi+140h]
0x1800275f0  mov     rcx, rbx; lpCriticalSection
0x1800275f3  call    cs:__imp_EnterCriticalSection
0x1800275f9  mov     rdx, [rsp+48h+arg_0]
0x1800275fe  mov     rcx, rdi; this
0x180027601  add     rdx, 2710h; __int64
0x180027608  call    ?ProcessNotificationTimeoutLocked_@CMPEG2PushClock@@AEAAK_J@Z; CMPEG2PushClock::ProcessNotificationTimeoutLocked_(__int64)
0x18002760d  mov     esi, eax
0x18002760f  jmp     short loc_18002763D
0x180027611  lea     rbx, [rdi+140h]
0x180027618  mov     rcx, rbx; lpCriticalSection
0x18002761b  call    cs:__imp_EnterCriticalSection
0x180027621  mov     rdx, [rsp+48h+arg_0]; __int64
0x180027626  mov     rcx, rdi; this
0x180027629  call    ?ResetWaitTimeLocked_@CMPEG2PushClock@@AEAAK_J@Z; CMPEG2PushClock::ResetWaitTimeLocked_(__int64)
0x18002762e  mov     rcx, [rdi+138h]; hEvent
0x180027635  mov     esi, eax
0x180027637  call    cs:__imp_ResetEvent
0x18002763d  mov     rcx, rbx; lpCriticalSection
0x180027640  call    cs:__imp_LeaveCriticalSection
0x180027646  xor     r8d, r8d; bWaitAll
0x180027649  mov     r9d, esi; dwMilliseconds
0x18002764c  mov     rdx, rbp; lpHandles
0x18002764f  lea     ecx, [r8+2]; nCount
0x180027653  call    cs:__imp_WaitForMultipleObjects
0x180027659  mov     ebx, eax
0x18002765b  test    eax, eax
0x18002765d  jnz     loc_1800275C4
0x180027663  xor     eax, eax
0x180027665  add     rsp, 28h
0x180027669  pop     rdi
0x18002766a  pop     rsi
0x18002766b  pop     rbp
0x18002766c  pop     rbx
0x18002766d  retn
```
