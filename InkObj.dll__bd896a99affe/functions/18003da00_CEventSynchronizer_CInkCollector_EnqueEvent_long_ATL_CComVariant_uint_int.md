# CEventSynchronizer<CInkCollector>::EnqueEvent(long,ATL::CComVariant *,uint,int)

- ea: `0x18003da00`
- end: `0x18003dbc4`
- name: `?EnqueEvent@?$CEventSynchronizer@VCInkCollector@@@@QEAAJJPEAVCComVariant@ATL@@IH@Z`
- size: `452`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int)`
- caller_count: `17`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d780`
- `0x18003d8bc`
- `0x1800ac084`
- `0x1800ac134`
- `0x1800ac1e4`
- `0x1800ac2a0`
- `0x1800ac3a0`
- `0x1800ac44c`
- `0x1800ac4f8`
- `0x1800ac600`
- `0x1800ac6e0`
- `0x1800ac7c0`
- `0x1800ac8a0`
- `0x1800ac994`
- `0x1800aca64`
- `0x1800acb74`
- `0x1800acc20`

## callees

- `0x180002740`
- `0x180010350`
- `0x18003da00`
- `0x180049d50`
- `0x180079728`
- `0x1800abfbc`
- `0x1800b0f0c`
- `0x1800b4aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dacf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dacf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003db83`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003db83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003db0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003db0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003db6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003db6c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003dac1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003dac1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003da5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003da5f`
- `USER32!PostMessageW` at `0x18003db46`
- `USER32!PostMessageW` at `0x18003db46`
- `USER32!GetWindowThreadProcessId` at `0x18003da72`
- `USER32!GetWindowThreadProcessId` at `0x18003da72`
- `USER32!IsWindow` at `0x18003da51`
- `USER32!IsWindow` at `0x18003da51`

## pseudocode

```c
__int64 __fastcall CEventSynchronizer<CInkCollector>::EnqueEvent(
        LPCRITICAL_SECTION lpCriticalSection,
        int a2,
        ATL::CComVariant *a3,
        int a4)
{
  LPCRITICAL_SECTION v6; // rdi
  unsigned int v7; // edx
  signed int v8; // ebx
  DWORD CurrentThreadId; // r15d
  DWORD WindowThreadProcessId; // r12d
  void **v11; // rax
  void **v12; // rsi
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v15; // edx
  ATL::CComVariant *v16; // rcx
  void *v17; // rsi
  void *v19; // [rsp+28h] [rbp-40h] BYREF
  void **v20; // [rsp+30h] [rbp-38h] BYREF
  std::bad_alloc *v21; // [rsp+38h] [rbp-30h] BYREF

  v6 = lpCriticalSection;
  if ( lpCriticalSection[2].LockCount )
  {
    v8 = 0;
    if ( IsWindow((HWND)lpCriticalSection[-3].OwningThread) )
    {
      CurrentThreadId = GetCurrentThreadId();
      WindowThreadProcessId = GetWindowThreadProcessId((HWND)v6[-3].OwningThread, 0);
      v11 = (void **)WinMalloc(0x18u);
      v12 = v11;
      v20 = v11;
      if ( v11 )
      {
        *v11 = 0;
        *((_DWORD *)v11 + 2) = a2;
        v11[2] = a3;
        *((_DWORD *)v11 + 3) = a4;
        if ( CurrentThreadId == WindowThreadProcessId )
          goto LABEL_14;
        EventW = CreateEventW(0, 1, 0, 0);
        *v12 = EventW;
        if ( EventW )
          goto LABEL_14;
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v16 = (ATL::CComVariant *)v12[2];
        if ( v16 )
          ATL::CComVariant::`vector deleting destructor'(v16, v15);
        WinFree(v12);
        if ( v8 >= 0 )
        {
LABEL_14:
          v17 = *v12;
          v19 = v17;
          EnterCriticalSection(v6);
          try
          {
            std::deque<tagEVENTSYNCSTRUCT *>::push_back(&v6[1], &v20);
            if ( !LODWORD(v6[2].DebugInfo) )
            {
              LODWORD(v6[2].DebugInfo) = 1;
              if ( CurrentThreadId != WindowThreadProcessId )
                PostMessageW((HWND)v6[-3].OwningThread, HIDWORD(v6[2].DebugInfo), 0, 0);
            }
          }
          catch ( std::bad_alloc *v21 )
          {
            v6 = lpCriticalSection;
            v8 = -2147024882;
            v17 = v19;
          }
          LeaveCriticalSection(v6);
          if ( v8 >= 0 )
          {
            if ( CurrentThreadId == WindowThreadProcessId )
            {
              v8 = CEventSynchronizer<CInkCollector>::FireEvents(v6);
            }
            else if ( WaitForSingleObject(v17, 0x7530u) )
            {
              v8 = -2147418113;
            }
          }
          SafeCloseHandle(&v19);
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
    v8 = CEventSynchronizer<CInkCollector>::_FireEvent();
    if ( a3 )
      ATL::CComVariant::`vector deleting destructor'(a3, v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003da00  mov     rax, rsp
0x18003da03  mov     [rax+18h], rbx
0x18003da07  mov     [rax+20h], rsi
0x18003da0b  mov     [rax+10h], edx
0x18003da0e  mov     [rax+8], rcx
0x18003da12  push    rdi
0x18003da13  push    r12
0x18003da15  push    r13
0x18003da17  push    r14
0x18003da19  push    r15
0x18003da1b  sub     rsp, 40h
0x18003da1f  mov     r13d, r9d
0x18003da22  mov     r14, r8
0x18003da25  mov     rdi, rcx
0x18003da28  cmp     dword ptr [rcx+58h], 0
0x18003da2c  jnz     short loc_18003DA4B
0x18003da2e  call    ?_FireEvent@?$CEventSynchronizer@VCInkCollector@@@@QEAAJJPEAVCComVariant@ATL@@I@Z; CEventSynchronizer<CInkCollector>::_FireEvent(long,ATL::CComVariant *,uint)
0x18003da33  mov     ebx, eax
0x18003da35  test    r14, r14
0x18003da38  jz      loc_18003DBA8
0x18003da3e  mov     rcx, r14; this
0x18003da41  call    ??_ECComVariant@ATL@@QEAAPEAXI@Z; ATL::CComVariant::`vector deleting destructor'(uint)
0x18003da46  jmp     loc_18003DBA8
0x18003da4b  xor     ebx, ebx
0x18003da4d  mov     rcx, [rcx-68h]; hWnd
0x18003da51  call    cs:__imp_IsWindow
0x18003da57  test    eax, eax
0x18003da59  jz      loc_18003DBA8
0x18003da5f  call    cs:__imp_GetCurrentThreadId
0x18003da65  mov     r15d, eax
0x18003da68  mov     [rsp+68h+var_48], eax
0x18003da6c  xor     edx, edx; lpdwProcessId
0x18003da6e  mov     rcx, [rdi-68h]; hWnd
0x18003da72  call    cs:__imp_GetWindowThreadProcessId
0x18003da78  mov     r12d, eax
0x18003da7b  mov     [rsp+68h+var_44], eax
0x18003da7f  lea     ecx, [rbx+18h]; unsigned __int64
0x18003da82  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x18003da87  mov     rsi, rax
0x18003da8a  mov     [rsp+68h+var_38], rax
0x18003da8f  test    rax, rax
0x18003da92  jnz     short loc_18003DA9E
0x18003da94  mov     ebx, 8007000Eh
0x18003da99  jmp     loc_18003DBA8
0x18003da9e  mov     [rax], rbx
0x18003daa1  mov     eax, [rsp+68h+arg_8]
0x18003daa5  mov     [rsi+8], eax
0x18003daa8  mov     [rsi+10h], r14
0x18003daac  mov     [rsi+0Ch], r13d
0x18003dab0  cmp     r15d, r12d
0x18003dab3  jz      short loc_18003DB02
0x18003dab5  xor     r9d, r9d; lpName
0x18003dab8  xor     r8d, r8d; bInitialState
0x18003dabb  lea     edx, [r9+1]; bManualReset
0x18003dabf  xor     ecx, ecx; lpEventAttributes
0x18003dac1  call    cs:__imp_CreateEventW
0x18003dac7  mov     [rsi], rax
0x18003daca  test    rax, rax
0x18003dacd  jnz     short loc_18003DB02
0x18003dacf  call    cs:__imp_GetLastError
0x18003dad5  mov     ebx, eax
0x18003dad7  test    eax, eax
0x18003dad9  jle     short loc_18003DAE4
0x18003dadb  movzx   ebx, ax
0x18003dade  or      ebx, 80070000h
0x18003dae4  mov     rcx, [rsi+10h]; this
0x18003dae8  test    rcx, rcx
0x18003daeb  jz      short loc_18003DAF2
0x18003daed  call    ??_ECComVariant@ATL@@QEAAPEAXI@Z; ATL::CComVariant::`vector deleting destructor'(uint)
0x18003daf2  mov     rcx, rsi; void *
0x18003daf5  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18003dafa  test    ebx, ebx
0x18003dafc  js      loc_18003DBA8
0x18003db02  mov     rsi, [rsi]
0x18003db05  mov     [rsp+68h+var_40], rsi
0x18003db0a  mov     rcx, rdi; lpCriticalSection
0x18003db0d  call    cs:__imp_EnterCriticalSection
0x18003db13  nop
0x18003db14  lea     rcx, [rdi+28h]
0x18003db18  lea     rdx, [rsp+68h+var_38]
0x18003db1d  call    ?push_back@?$deque@PEAUtagEVENTSYNCSTRUCT@@V?$allocator@PEAUtagEVENTSYNCSTRUCT@@@std@@@std@@QEAAXAEBQEAUtagEVENTSYNCSTRUCT@@@Z; std::deque<tagEVENTSYNCSTRUCT *>::push_back(tagEVENTSYNCSTRUCT * const &)
0x18003db22  nop
0x18003db23  test    ebx, ebx
0x18003db25  js      short loc_18003DB69
0x18003db27  cmp     dword ptr [rdi+50h], 0
0x18003db2b  jnz     short loc_18003DB69
0x18003db2d  mov     dword ptr [rdi+50h], 1
0x18003db34  cmp     r15d, r12d
0x18003db37  jz      short loc_18003DB69
0x18003db39  xor     r9d, r9d; lParam
0x18003db3c  xor     r8d, r8d; wParam
0x18003db3f  mov     edx, [rdi+54h]; Msg
0x18003db42  mov     rcx, [rdi-68h]; hWnd
0x18003db46  call    cs:__imp_PostMessageW
0x18003db4c  jmp     short loc_18003DB69
0x18003db4e  mov     rdi, [rsp+68h+arg_0]
0x18003db53  mov     ebx, [rsp+68h+arg_20]
0x18003db5a  mov     rsi, [rsp+68h+var_40]
0x18003db5f  mov     r15d, [rsp+68h+var_48]
0x18003db64  mov     r12d, [rsp+68h+var_44]
0x18003db69  mov     rcx, rdi; lpCriticalSection
0x18003db6c  call    cs:__imp_LeaveCriticalSection
0x18003db72  test    ebx, ebx
0x18003db74  js      short loc_18003DB9E
0x18003db76  cmp     r15d, r12d
0x18003db79  jz      short loc_18003DB94
0x18003db7b  mov     edx, 7530h; dwMilliseconds
0x18003db80  mov     rcx, rsi; hHandle
0x18003db83  call    cs:__imp_WaitForSingleObject
0x18003db89  test    eax, eax
0x18003db8b  jz      short loc_18003DB9E
0x18003db8d  mov     ebx, 8000FFFFh
0x18003db92  jmp     short loc_18003DB9E
0x18003db94  mov     rcx, rdi; lpCriticalSection
0x18003db97  call    ?FireEvents@?$CEventSynchronizer@VCInkCollector@@@@QEAAJXZ; CEventSynchronizer<CInkCollector>::FireEvents(void)
0x18003db9c  mov     ebx, eax
0x18003db9e  lea     rcx, [rsp+68h+var_40]; void **
0x18003dba3  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18003dba8  mov     eax, ebx
0x18003dbaa  lea     r11, [rsp+68h+var_28]
0x18003dbaf  mov     rbx, [r11+40h]
0x18003dbb3  mov     rsi, [r11+48h]
0x18003dbb7  mov     rsp, r11
0x18003dbba  pop     r15
0x18003dbbc  pop     r14
0x18003dbbe  pop     r13
0x18003dbc0  pop     r12
0x18003dbc2  pop     rdi
0x18003dbc3  retn
```
