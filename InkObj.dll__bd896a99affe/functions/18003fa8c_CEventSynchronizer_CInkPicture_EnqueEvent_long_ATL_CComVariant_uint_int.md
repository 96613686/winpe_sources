# CEventSynchronizer<CInkPicture>::EnqueEvent(long,ATL::CComVariant *,uint,int)

- ea: `0x18003fa8c`
- end: `0x18003fc79`
- name: `?EnqueEvent@?$CEventSynchronizer@VCInkPicture@@@@QEAAJJPEAVCComVariant@ATL@@IH@Z`
- size: `493`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int)`
- caller_count: `37`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f80c`
- `0x18003f950`
- `0x1800589e0`
- `0x1800e8dbc`
- `0x1800e8e6c`
- `0x1800e8f1c`
- `0x1800e8fd8`
- `0x1800e90d8`
- `0x1800e9184`
- `0x1800e9230`
- `0x1800e9338`
- `0x1800e93e4`
- `0x1800e9490`
- `0x1800e953c`
- `0x1800e961c`
- `0x1800e96fc`
- `0x1800e97dc`
- `0x1800e98d0`
- `0x1800e997c`
- `0x1800e9a4c`
- `0x1800e9b24`
- `0x1800e9bd0`
- `0x1800e9c7c`
- `0x1800e9d28`
- `0x1800e9dd4`
- `0x1800e9e80`
- `0x1800e9f5c`
- `0x1800ea008`
- `0x1800ea0d8`
- `0x1800ea10c`
- `0x1800ea1b8`
- `0x1800ea2c8`
- `0x1800ea374`
- `0x1800eb878`
- `0x1800ec298`
- `0x1800ec510`
- `0x1800f2e2c`

## callees

- `0x180002740`
- `0x180010350`
- `0x18003fa8c`
- `0x180049d50`
- `0x180079728`
- `0x1800b4aa0`
- `0x1800e8aac`
- `0x1800f0740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb7d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003fc38`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003fc38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fbbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fbbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003fc21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003fc21`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003fb6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003fb6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fb0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fb0b`
- `USER32!PostMessageW` at `0x18003fbf8`
- `USER32!PostMessageW` at `0x18003fbf8`
- `USER32!GetWindowThreadProcessId` at `0x18003fb1d`
- `USER32!GetWindowThreadProcessId` at `0x18003fb1d`
- `USER32!IsWindow` at `0x18003fafd`
- `USER32!IsWindow` at `0x18003fafd`

## pseudocode

```c
__int64 __fastcall CEventSynchronizer<CInkPicture>::EnqueEvent(
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
    v9 = (__int64)(lpCriticalSection - 216);
    if ( !lpCriticalSection )
      v9 = 168;
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
              v8 = CEventSynchronizer<CInkPicture>::FireEvents((LPCRITICAL_SECTION)v6);
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
    v8 = CEventSynchronizer<CInkPicture>::_FireEvent();
    if ( a4 && a3 )
      ATL::CComVariant::`vector deleting destructor'(a3, v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003fa8c  mov     rax, rsp
0x18003fa8f  mov     [rax+18h], rbx
0x18003fa93  mov     [rax+20h], rsi
0x18003fa97  mov     [rax+10h], edx
0x18003fa9a  mov     [rax+8], rcx
0x18003fa9e  push    rdi
0x18003fa9f  push    r12
0x18003faa1  push    r13
0x18003faa3  push    r14
0x18003faa5  push    r15
0x18003faa7  sub     rsp, 50h
0x18003faab  mov     r15d, r9d
0x18003faae  mov     r14, r8
0x18003fab1  mov     rdi, rcx
0x18003fab4  cmp     dword ptr [rcx+58h], 0
0x18003fab8  jnz     short loc_18003FAE0
0x18003faba  call    ?_FireEvent@?$CEventSynchronizer@VCInkPicture@@@@QEAAJJPEAVCComVariant@ATL@@I@Z; CEventSynchronizer<CInkPicture>::_FireEvent(long,ATL::CComVariant *,uint)
0x18003fabf  mov     ebx, eax
0x18003fac1  test    r15d, r15d
0x18003fac4  jz      loc_18003FC5D
0x18003faca  test    r14, r14
0x18003facd  jz      loc_18003FC5D
0x18003fad3  mov     rcx, r14; this
0x18003fad6  call    ??_ECComVariant@ATL@@QEAAPEAXI@Z; ATL::CComVariant::`vector deleting destructor'(uint)
0x18003fadb  jmp     loc_18003FC5D
0x18003fae0  xor     ebx, ebx
0x18003fae2  lea     rsi, [rcx-0D8h]
0x18003fae9  mov     eax, 0A8h
0x18003faee  test    rdi, rdi
0x18003faf1  cmovz   rsi, rax
0x18003faf5  mov     [rsp+78h+var_40], rsi
0x18003fafa  mov     rcx, [rsi]; hWnd
0x18003fafd  call    cs:__imp_IsWindow
0x18003fb03  test    eax, eax
0x18003fb05  jz      loc_18003FC5D
0x18003fb0b  call    cs:__imp_GetCurrentThreadId
0x18003fb11  mov     r12d, eax
0x18003fb14  mov     [rsp+78h+var_58], eax
0x18003fb18  xor     edx, edx; lpdwProcessId
0x18003fb1a  mov     rcx, [rsi]; hWnd
0x18003fb1d  call    cs:__imp_GetWindowThreadProcessId
0x18003fb23  mov     r13d, eax
0x18003fb26  mov     [rsp+78h+var_54], eax
0x18003fb2a  lea     ecx, [rbx+18h]; unsigned __int64
0x18003fb2d  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x18003fb32  mov     rsi, rax
0x18003fb35  mov     [rsp+78h+var_48], rax
0x18003fb3a  test    rax, rax
0x18003fb3d  jnz     short loc_18003FB49
0x18003fb3f  mov     ebx, 8007000Eh
0x18003fb44  jmp     loc_18003FC5D
0x18003fb49  mov     [rax], rbx
0x18003fb4c  mov     eax, [rsp+78h+arg_8]
0x18003fb53  mov     [rsi+8], eax
0x18003fb56  mov     [rsi+10h], r14
0x18003fb5a  mov     [rsi+0Ch], r15d
0x18003fb5e  cmp     r12d, r13d
0x18003fb61  jz      short loc_18003FBB0
0x18003fb63  xor     r9d, r9d; lpName
0x18003fb66  xor     r8d, r8d; bInitialState
0x18003fb69  lea     edx, [r9+1]; bManualReset
0x18003fb6d  xor     ecx, ecx; lpEventAttributes
0x18003fb6f  call    cs:__imp_CreateEventW
0x18003fb75  mov     [rsi], rax
0x18003fb78  test    rax, rax
0x18003fb7b  jnz     short loc_18003FBB0
0x18003fb7d  call    cs:__imp_GetLastError
0x18003fb83  mov     ebx, eax
0x18003fb85  test    eax, eax
0x18003fb87  jle     short loc_18003FB92
0x18003fb89  movzx   ebx, ax
0x18003fb8c  or      ebx, 80070000h
0x18003fb92  mov     rcx, [rsi+10h]; this
0x18003fb96  test    rcx, rcx
0x18003fb99  jz      short loc_18003FBA0
0x18003fb9b  call    ??_ECComVariant@ATL@@QEAAPEAXI@Z; ATL::CComVariant::`vector deleting destructor'(uint)
0x18003fba0  mov     rcx, rsi; void *
0x18003fba3  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18003fba8  test    ebx, ebx
0x18003fbaa  js      loc_18003FC5D
0x18003fbb0  mov     rsi, [rsi]
0x18003fbb3  mov     [rsp+78h+var_50], rsi
0x18003fbb8  mov     rcx, rdi; lpCriticalSection
0x18003fbbb  call    cs:__imp_EnterCriticalSection
0x18003fbc1  nop
0x18003fbc2  lea     rcx, [rdi+28h]
0x18003fbc6  lea     rdx, [rsp+78h+var_48]
0x18003fbcb  call    ?push_back@?$deque@PEAUtagEVENTSYNCSTRUCT@@V?$allocator@PEAUtagEVENTSYNCSTRUCT@@@std@@@std@@QEAAXAEBQEAUtagEVENTSYNCSTRUCT@@@Z; std::deque<tagEVENTSYNCSTRUCT *>::push_back(tagEVENTSYNCSTRUCT * const &)
0x18003fbd0  nop
0x18003fbd1  test    ebx, ebx
0x18003fbd3  js      short loc_18003FC1E
0x18003fbd5  cmp     dword ptr [rdi+50h], 0
0x18003fbd9  jnz     short loc_18003FC1E
0x18003fbdb  mov     dword ptr [rdi+50h], 1
0x18003fbe2  cmp     r12d, r13d
0x18003fbe5  jz      short loc_18003FC1E
0x18003fbe7  xor     r9d, r9d; lParam
0x18003fbea  xor     r8d, r8d; wParam
0x18003fbed  mov     edx, [rdi+54h]; Msg
0x18003fbf0  mov     rcx, [rsp+78h+var_40]
0x18003fbf5  mov     rcx, [rcx]; hWnd
0x18003fbf8  call    cs:__imp_PostMessageW
0x18003fbfe  jmp     short loc_18003FC1E
0x18003fc00  mov     rdi, [rsp+78h+arg_0]
0x18003fc08  mov     ebx, [rsp+78h+arg_20]
0x18003fc0f  mov     rsi, [rsp+78h+var_50]
0x18003fc14  mov     r12d, [rsp+78h+var_58]
0x18003fc19  mov     r13d, [rsp+78h+var_54]
0x18003fc1e  mov     rcx, rdi; lpCriticalSection
0x18003fc21  call    cs:__imp_LeaveCriticalSection
0x18003fc27  test    ebx, ebx
0x18003fc29  js      short loc_18003FC53
0x18003fc2b  cmp     r12d, r13d
0x18003fc2e  jz      short loc_18003FC49
0x18003fc30  mov     edx, 7530h; dwMilliseconds
0x18003fc35  mov     rcx, rsi; hHandle
0x18003fc38  call    cs:__imp_WaitForSingleObject
0x18003fc3e  test    eax, eax
0x18003fc40  jz      short loc_18003FC53
0x18003fc42  mov     ebx, 8000FFFFh
0x18003fc47  jmp     short loc_18003FC53
0x18003fc49  mov     rcx, rdi; lpCriticalSection
0x18003fc4c  call    ?FireEvents@?$CEventSynchronizer@VCInkPicture@@@@QEAAJXZ; CEventSynchronizer<CInkPicture>::FireEvents(void)
0x18003fc51  mov     ebx, eax
0x18003fc53  lea     rcx, [rsp+78h+var_50]; void **
0x18003fc58  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18003fc5d  mov     eax, ebx
0x18003fc5f  lea     r11, [rsp+78h+var_28]
0x18003fc64  mov     rbx, [r11+40h]
0x18003fc68  mov     rsi, [r11+48h]
0x18003fc6c  mov     rsp, r11
0x18003fc6f  pop     r15
0x18003fc71  pop     r14
0x18003fc73  pop     r13
0x18003fc75  pop     r12
0x18003fc77  pop     rdi
0x18003fc78  retn
```
