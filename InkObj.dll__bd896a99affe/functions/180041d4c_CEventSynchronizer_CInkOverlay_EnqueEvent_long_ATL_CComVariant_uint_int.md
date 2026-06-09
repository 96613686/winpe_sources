# CEventSynchronizer<CInkOverlay>::EnqueEvent(long,ATL::CComVariant *,uint,int)

- ea: `0x180041d4c`
- end: `0x180041f34`
- name: `?EnqueEvent@?$CEventSynchronizer@VCInkOverlay@@@@QEAAJJPEAVCComVariant@ATL@@IH@Z`
- size: `488`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int)`
- caller_count: `27`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180041acc`
- `0x180041c10`
- `0x1800da92c`
- `0x1800da9dc`
- `0x1800daa8c`
- `0x1800dab48`
- `0x1800dac48`
- `0x1800dacf4`
- `0x1800dada0`
- `0x1800daea8`
- `0x1800daf88`
- `0x1800db068`
- `0x1800db148`
- `0x1800db23c`
- `0x1800db2e8`
- `0x1800db3b8`
- `0x1800db464`
- `0x1800db510`
- `0x1800db5bc`
- `0x1800db668`
- `0x1800db714`
- `0x1800db7e4`
- `0x1800db890`
- `0x1800db9a0`
- `0x1800dba4c`
- `0x1800e1434`
- `0x1800e2850`

## callees

- `0x180002740`
- `0x180010350`
- `0x180041d4c`
- `0x180049d50`
- `0x180079728`
- `0x1800b4aa0`
- `0x1800da864`
- `0x1800e0420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e38`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041ef3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041ef3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041e76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041e76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041edc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041edc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180041e2a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180041e2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041dc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041dc6`
- `USER32!PostMessageW` at `0x180041eb3`
- `USER32!PostMessageW` at `0x180041eb3`
- `USER32!GetWindowThreadProcessId` at `0x180041dd8`
- `USER32!GetWindowThreadProcessId` at `0x180041dd8`
- `USER32!IsWindow` at `0x180041db8`
- `USER32!IsWindow` at `0x180041db8`

## pseudocode

```c
__int64 __fastcall CEventSynchronizer<CInkOverlay>::EnqueEvent(
        char *lpCriticalSection,
        int a2,
        ATL::CComVariant *a3,
        int a4)
{
  char *v6; // rdi
  unsigned int v7; // edx
  signed int v8; // ebx
  __int64 v9; // rsi
  DWORD CurrentThreadId; // r12d
  DWORD WindowThreadProcessId; // r13d
  void **v12; // rax
  void **v13; // rsi
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v16; // edx
  ATL::CComVariant *v17; // rcx
  void *v18; // rsi
  void *v20; // [rsp+28h] [rbp-50h] BYREF
  void **v21; // [rsp+30h] [rbp-48h] BYREF
  HWND *v22; // [rsp+38h] [rbp-40h]
  std::bad_alloc *v23; // [rsp+40h] [rbp-38h] BYREF

  v6 = lpCriticalSection;
  if ( *((_DWORD *)lpCriticalSection + 22) )
  {
    v8 = 0;
    v9 = (__int64)(lpCriticalSection - 104);
    if ( !lpCriticalSection )
      v9 = 56;
    v22 = (HWND *)v9;
    if ( IsWindow(*(HWND *)v9) )
    {
      CurrentThreadId = GetCurrentThreadId();
      WindowThreadProcessId = GetWindowThreadProcessId(*(HWND *)v9, 0);
      v12 = (void **)WinMalloc(0x18u);
      v13 = v12;
      v21 = v12;
      if ( v12 )
      {
        *v12 = 0;
        *((_DWORD *)v12 + 2) = a2;
        v12[2] = a3;
        *((_DWORD *)v12 + 3) = a4;
        if ( CurrentThreadId == WindowThreadProcessId )
          goto LABEL_17;
        EventW = CreateEventW(0, 1, 0, 0);
        *v13 = EventW;
        if ( EventW )
          goto LABEL_17;
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v17 = (ATL::CComVariant *)v13[2];
        if ( v17 )
          ATL::CComVariant::`vector deleting destructor'(v17, v16);
        WinFree(v13);
        if ( v8 >= 0 )
        {
LABEL_17:
          v18 = *v13;
          v20 = v18;
          EnterCriticalSection((LPCRITICAL_SECTION)v6);
          try
          {
            std::deque<tagEVENTSYNCSTRUCT *>::push_back(v6 + 40, &v21);
            if ( !*((_DWORD *)v6 + 20) )
            {
              *((_DWORD *)v6 + 20) = 1;
              if ( CurrentThreadId != WindowThreadProcessId )
                PostMessageW(*v22, *((_DWORD *)v6 + 21), 0, 0);
            }
          }
          catch ( std::bad_alloc *v23 )
          {
            v6 = lpCriticalSection;
            v8 = -2147024882;
            v18 = v20;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)v6);
          if ( v8 >= 0 )
          {
            if ( CurrentThreadId == WindowThreadProcessId )
            {
              v8 = CEventSynchronizer<CInkOverlay>::FireEvents((LPCRITICAL_SECTION)v6);
            }
            else if ( WaitForSingleObject(v18, 0x7530u) )
            {
              v8 = -2147418113;
            }
          }
          SafeCloseHandle(&v20);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    v8 = CEventSynchronizer<CInkOverlay>::_FireEvent();
    if ( a4 && a3 )
      ATL::CComVariant::`vector deleting destructor'(a3, v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180041d4c  mov     rax, rsp
0x180041d4f  mov     [rax+18h], rbx
0x180041d53  mov     [rax+20h], rsi
0x180041d57  mov     [rax+10h], edx
0x180041d5a  mov     [rax+8], rcx
0x180041d5e  push    rdi
0x180041d5f  push    r12
0x180041d61  push    r13
0x180041d63  push    r14
0x180041d65  push    r15
0x180041d67  sub     rsp, 50h
0x180041d6b  mov     r15d, r9d
0x180041d6e  mov     r14, r8
0x180041d71  mov     rdi, rcx
0x180041d74  cmp     dword ptr [rcx+58h], 0
0x180041d78  jnz     short loc_180041DA0
0x180041d7a  call    ?_FireEvent@?$CEventSynchronizer@VCInkOverlay@@@@QEAAJJPEAVCComVariant@ATL@@I@Z; CEventSynchronizer<CInkOverlay>::_FireEvent(long,ATL::CComVariant *,uint)
0x180041d7f  mov     ebx, eax
0x180041d81  test    r15d, r15d
0x180041d84  jz      loc_180041F18
0x180041d8a  test    r14, r14
0x180041d8d  jz      loc_180041F18
0x180041d93  mov     rcx, r14; this
0x180041d96  call    ??_ECComVariant@ATL@@QEAAPEAXI@Z; ATL::CComVariant::`vector deleting destructor'(uint)
0x180041d9b  jmp     loc_180041F18
0x180041da0  xor     ebx, ebx
0x180041da2  lea     rsi, [rcx-68h]
0x180041da6  lea     eax, [rbx+38h]
0x180041da9  test    rdi, rdi
0x180041dac  cmovz   rsi, rax
0x180041db0  mov     [rsp+78h+var_40], rsi
0x180041db5  mov     rcx, [rsi]; hWnd
0x180041db8  call    cs:__imp_IsWindow
0x180041dbe  test    eax, eax
0x180041dc0  jz      loc_180041F18
0x180041dc6  call    cs:__imp_GetCurrentThreadId
0x180041dcc  mov     r12d, eax
0x180041dcf  mov     [rsp+78h+var_58], eax
0x180041dd3  xor     edx, edx; lpdwProcessId
0x180041dd5  mov     rcx, [rsi]; hWnd
0x180041dd8  call    cs:__imp_GetWindowThreadProcessId
0x180041dde  mov     r13d, eax
0x180041de1  mov     [rsp+78h+var_54], eax
0x180041de5  lea     ecx, [rbx+18h]; unsigned __int64
0x180041de8  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x180041ded  mov     rsi, rax
0x180041df0  mov     [rsp+78h+var_48], rax
0x180041df5  test    rax, rax
0x180041df8  jnz     short loc_180041E04
0x180041dfa  mov     ebx, 8007000Eh
0x180041dff  jmp     loc_180041F18
0x180041e04  mov     [rax], rbx
0x180041e07  mov     eax, [rsp+78h+arg_8]
0x180041e0e  mov     [rsi+8], eax
0x180041e11  mov     [rsi+10h], r14
0x180041e15  mov     [rsi+0Ch], r15d
0x180041e19  cmp     r12d, r13d
0x180041e1c  jz      short loc_180041E6B
0x180041e1e  xor     r9d, r9d; lpName
0x180041e21  xor     r8d, r8d; bInitialState
0x180041e24  lea     edx, [r9+1]; bManualReset
0x180041e28  xor     ecx, ecx; lpEventAttributes
0x180041e2a  call    cs:__imp_CreateEventW
0x180041e30  mov     [rsi], rax
0x180041e33  test    rax, rax
0x180041e36  jnz     short loc_180041E6B
0x180041e38  call    cs:__imp_GetLastError
0x180041e3e  mov     ebx, eax
0x180041e40  test    eax, eax
0x180041e42  jle     short loc_180041E4D
0x180041e44  movzx   ebx, ax
0x180041e47  or      ebx, 80070000h
0x180041e4d  mov     rcx, [rsi+10h]; this
0x180041e51  test    rcx, rcx
0x180041e54  jz      short loc_180041E5B
0x180041e56  call    ??_ECComVariant@ATL@@QEAAPEAXI@Z; ATL::CComVariant::`vector deleting destructor'(uint)
0x180041e5b  mov     rcx, rsi; void *
0x180041e5e  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x180041e63  test    ebx, ebx
0x180041e65  js      loc_180041F18
0x180041e6b  mov     rsi, [rsi]
0x180041e6e  mov     [rsp+78h+var_50], rsi
0x180041e73  mov     rcx, rdi; lpCriticalSection
0x180041e76  call    cs:__imp_EnterCriticalSection
0x180041e7c  nop
0x180041e7d  lea     rcx, [rdi+28h]
0x180041e81  lea     rdx, [rsp+78h+var_48]
0x180041e86  call    ?push_back@?$deque@PEAUtagEVENTSYNCSTRUCT@@V?$allocator@PEAUtagEVENTSYNCSTRUCT@@@std@@@std@@QEAAXAEBQEAUtagEVENTSYNCSTRUCT@@@Z; std::deque<tagEVENTSYNCSTRUCT *>::push_back(tagEVENTSYNCSTRUCT * const &)
0x180041e8b  nop
0x180041e8c  test    ebx, ebx
0x180041e8e  js      short loc_180041ED9
0x180041e90  cmp     dword ptr [rdi+50h], 0
0x180041e94  jnz     short loc_180041ED9
0x180041e96  mov     dword ptr [rdi+50h], 1
0x180041e9d  cmp     r12d, r13d
0x180041ea0  jz      short loc_180041ED9
0x180041ea2  xor     r9d, r9d; lParam
0x180041ea5  xor     r8d, r8d; wParam
0x180041ea8  mov     edx, [rdi+54h]; Msg
0x180041eab  mov     rcx, [rsp+78h+var_40]
0x180041eb0  mov     rcx, [rcx]; hWnd
0x180041eb3  call    cs:__imp_PostMessageW
0x180041eb9  jmp     short loc_180041ED9
0x180041ebb  mov     rdi, [rsp+78h+arg_0]
0x180041ec3  mov     ebx, [rsp+78h+arg_20]
0x180041eca  mov     rsi, [rsp+78h+var_50]
0x180041ecf  mov     r12d, [rsp+78h+var_58]
0x180041ed4  mov     r13d, [rsp+78h+var_54]
0x180041ed9  mov     rcx, rdi; lpCriticalSection
0x180041edc  call    cs:__imp_LeaveCriticalSection
0x180041ee2  test    ebx, ebx
0x180041ee4  js      short loc_180041F0E
0x180041ee6  cmp     r12d, r13d
0x180041ee9  jz      short loc_180041F04
0x180041eeb  mov     edx, 7530h; dwMilliseconds
0x180041ef0  mov     rcx, rsi; hHandle
0x180041ef3  call    cs:__imp_WaitForSingleObject
0x180041ef9  test    eax, eax
0x180041efb  jz      short loc_180041F0E
0x180041efd  mov     ebx, 8000FFFFh
0x180041f02  jmp     short loc_180041F0E
0x180041f04  mov     rcx, rdi; lpCriticalSection
0x180041f07  call    ?FireEvents@?$CEventSynchronizer@VCInkOverlay@@@@QEAAJXZ; CEventSynchronizer<CInkOverlay>::FireEvents(void)
0x180041f0c  mov     ebx, eax
0x180041f0e  lea     rcx, [rsp+78h+var_50]; void **
0x180041f13  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180041f18  mov     eax, ebx
0x180041f1a  lea     r11, [rsp+78h+var_28]
0x180041f1f  mov     rbx, [r11+40h]
0x180041f23  mov     rsi, [r11+48h]
0x180041f27  mov     rsp, r11
0x180041f2a  pop     r15
0x180041f2c  pop     r14
0x180041f2e  pop     r13
0x180041f30  pop     r12
0x180041f32  pop     rdi
0x180041f33  retn
```
