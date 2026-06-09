# CCContext::HookProc(int,unsigned __int64,__int64)

- ea: `0x180018bf0`
- end: `0x180019102`
- name: `?HookProc@CCContext@@KA_JH_K_J@Z`
- size: `1298`
- prototype: `LRESULT __stdcall(int code, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180010350`
- `0x180018bf0`
- `0x180021fc4`
- `0x180023a30`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018dcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018f0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018dcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018c66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018c66`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x180018e42`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x180018f66`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x180018e42`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x180018f66`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018e14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018e14`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180018fe1`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180018fe1`
- `USER32!CallNextHookEx` at `0x180018c95`
- `USER32!CallNextHookEx` at `0x180018c95`
- `USER32!GetWindowThreadProcessId` at `0x180018c60`
- `USER32!GetWindowThreadProcessId` at `0x180018d1c`
- `USER32!GetWindowThreadProcessId` at `0x180018d2d`
- `USER32!GetWindowThreadProcessId` at `0x180018c60`
- `USER32!GetWindowThreadProcessId` at `0x180018d1c`
- `USER32!GetWindowThreadProcessId` at `0x180018d2d`
- `USER32!GetAncestor` at `0x180018cfc`
- `USER32!GetAncestor` at `0x180018cfc`
- `USER32!EqualRect` at `0x180018ef6`
- `USER32!EqualRect` at `0x180018ef6`
- `USER32!MapWindowPoints` at `0x180018d9e`
- `USER32!MapWindowPoints` at `0x180018d9e`
- `USER32!GetClientRect` at `0x180018d84`
- `USER32!GetClientRect` at `0x180018d84`
- `USER32!IsWindow` at `0x180018c46`
- `USER32!IsWindow` at `0x180018c46`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180018d76`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180018d76`

## pseudocode

```c
LRESULT __fastcall CCContext::HookProc(int code, WPARAM wParam, LPARAM lParam)
{
  HWND v6; // rsi
  int v7; // r12d
  CComDllModule *v8; // rcx
  unsigned int v9; // edx
  HWND Ancestor; // r15
  DWORD WindowThreadProcessId; // r12d
  DWORD v13; // eax
  CAPCParam *v14; // rax
  CAPCParam *v15; // r15
  unsigned int v16; // edx
  CComDllModule *v17; // rcx
  CAPCParam *v18; // rax
  CComDllModule *v19; // rcx
  CAPCParam *v20; // r15
  unsigned int v21; // edx
  DWORD dwindex; // [rsp+30h] [rbp-78h] BYREF
  DWORD dwProcessId; // [rsp+34h] [rbp-74h] BYREF
  DWORD v24[4]; // [rsp+38h] [rbp-70h] BYREF
  WPARAM v25; // [rsp+48h] [rbp-60h]
  LPARAM v26; // [rsp+50h] [rbp-58h]
  struct tagRECT Rect; // [rsp+58h] [rbp-50h] BYREF

  v24[2] = code;
  v25 = wParam;
  v26 = lParam;
  if ( _InterlockedCompareExchange(&g_lServerFailing, 1, 1) && *(_DWORD *)(lParam + 16) != 2 )
    return CallNextHookEx(0, code, wParam, lParam);
  v6 = *(HWND *)(lParam + 24);
  if ( !IsWindow(v6) )
    return CallNextHookEx(0, code, wParam, lParam);
  v7 = 0;
  dwProcessId = 0;
  GetWindowThreadProcessId(v6, &dwProcessId);
  if ( GetCurrentProcessId() != dwProcessId || code < 0 )
    return CallNextHookEx(0, code, wParam, lParam);
  v9 = *(_DWORD *)(lParam + 16);
  if ( v9 == 32 )
  {
    if ( !dword_18016D79C )
      return CallNextHookEx(0, code, wParam, lParam);
LABEL_32:
    CComDllModule::ExecuteCallOnApcThread(
      v8,
      (void (*)(unsigned __int64))CCContext::EnableContext,
      (unsigned __int64)v6,
      0);
    dword_18016D79C = 0;
    return CallNextHookEx(0, code, wParam, lParam);
  }
  if ( v9 == 273 )
  {
    v17 = (CComDllModule *)*(unsigned __int16 *)(lParam + 10);
    if ( (unsigned __int16)((_WORD)v17 - 7) <= 1u )
      CComDllModule::ExecuteCallOnApcThread(
        v17,
        CCContext::BringWindowContextToTop,
        (unsigned __int64)v6,
        *(_WORD *)(lParam + 10) == 8);
  }
  else
  {
    if ( v9 <= 0x111 )
    {
      switch ( v9 )
      {
        case 2u:
          CComDllModule::ExecuteCallOnApcThread(
            v8,
            (void (*)(unsigned __int64))CCContext::UnhookContext,
            (unsigned __int64)v6,
            0);
          return CallNextHookEx(0, code, wParam, lParam);
        case 3u:
        case 5u:
          goto LABEL_15;
        case 6u:
        case 0x22u:
          if ( v9 == 6 )
          {
            LOBYTE(v7) = *(_QWORD *)(lParam + 8) != 0;
            goto LABEL_38;
          }
          if ( v9 == 34 )
            goto LABEL_50;
          break;
        case 0x47u:
          if ( v6 )
          {
            Ancestor = GetAncestor(v6, 2u);
            if ( Ancestor )
            {
              v24[0] = 0;
              dwindex = 0;
              WindowThreadProcessId = GetWindowThreadProcessId(v6, v24);
              v13 = GetWindowThreadProcessId(Ancestor, &dwindex);
              if ( dwindex != v24[0] || v13 != WindowThreadProcessId )
                CComDllModule::ExecuteCallOnApcThread(
                  (CComDllModule *)v24[0],
                  (void (*)(unsigned __int64))CCContext::EnableTimerForWndSubtree,
                  (unsigned __int64)v6,
                  0);
            }
          }
LABEL_15:
          Rect = 0;
          dwindex = 0;
          CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &hMutex, &dwindex);
          if ( !GetClientRect(v6, &Rect) )
            goto LABEL_18;
          MapWindowPoints(v6, 0, (LPPOINT)&Rect, 2u);
          if ( (HWND)qword_18016D280 == v6 && EqualRect(&Rect, &rc2) )
          {
            ReleaseMutex(hMutex);
          }
          else
          {
            qword_18016D280 = (__int64)v6;
            rc2 = Rect;
LABEL_18:
            ReleaseMutex(hMutex);
            if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + (unsigned int)tls_index)
                                                                           + 4LL) )
            {
              Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
              if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
              {
                `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
                dwFlags = 0;
                `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
                atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
                Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
              }
            }
            if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
            {
              v14 = (CAPCParam *)HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, 0x18u);
              v15 = v14;
              if ( v14 )
              {
                *((_QWORD *)v14 + 1) = v6;
                *((_DWORD *)v14 + 4) = 0;
                *(_QWORD *)v14 = 0;
                if ( !QueueUserAPC(CCContext::ResizeContext, hObject, (ULONG_PTR)v14) )
                  CAPCParam::`scalar deleting destructor'(v15, v16);
              }
            }
          }
          return CallNextHookEx(0, code, wParam, lParam);
        default:
          return CallNextHookEx(0, code, wParam, lParam);
      }
LABEL_37:
      if ( v9 == 546 )
      {
        v6 = *(HWND *)lParam;
LABEL_50:
        v7 = 1;
      }
LABEL_38:
      v18 = (CAPCParam *)WinMalloc(0x18u);
      v20 = v18;
      if ( v18 )
      {
        *((_QWORD *)v18 + 1) = v6;
        *((_DWORD *)v18 + 4) = v7;
        *(_QWORD *)v18 = 0;
        if ( !QueueUserAPC(CCContext::BringWindowContextToTop, hObject, (ULONG_PTR)v18) )
          CAPCParam::`scalar deleting destructor'(v20, v21);
      }
      if ( *(_DWORD *)(lParam + 16) == 546 )
        CComDllModule::ExecuteCallOnApcThread(v19, CCContext::BringWindowContextToTop, *(_QWORD *)(lParam + 8), 0);
      return CallNextHookEx(0, code, wParam, lParam);
    }
    switch ( v9 )
    {
      case 0x117u:
        CComDllModule::ExecuteCallOnApcThread(v8, CCContext::BringWindowContextToTop, (unsigned __int64)v6, 0);
        return CallNextHookEx(0, code, wParam, lParam);
      case 0x125u:
        CComDllModule::ExecuteCallOnApcThread(v8, CCContext::BringWindowContextToTop, (unsigned __int64)v6, 1);
        return CallNextHookEx(0, code, wParam, lParam);
      case 0x222u:
        goto LABEL_37;
      case 0x231u:
        CComDllModule::ExecuteCallOnApcThread(
          v8,
          (void (*)(unsigned __int64))CCContext::DisableContext,
          (unsigned __int64)v6,
          0);
        dword_18016D79C = 1;
        return CallNextHookEx(0, code, wParam, lParam);
      case 0x232u:
        goto LABEL_32;
    }
  }
  return CallNextHookEx(0, code, wParam, lParam);
}

```

## disassembly

```asm
0x180018bf0  push    rbx
0x180018bf2  push    rsi
0x180018bf3  push    rdi
0x180018bf4  push    r12
0x180018bf6  push    r13
0x180018bf8  push    r14
0x180018bfa  push    r15
0x180018bfc  sub     rsp, 70h
0x180018c00  mov     rax, cs:__security_cookie
0x180018c07  xor     rax, rsp
0x180018c0a  mov     [rsp+0A8h+var_40], rax
0x180018c0f  mov     rbx, r8
0x180018c12  mov     r14, rdx
0x180018c15  mov     edi, ecx
0x180018c17  mov     [rsp+0A8h+var_68], ecx
0x180018c1b  mov     [rsp+0A8h+var_60], rdx
0x180018c20  mov     [rsp+0A8h+var_58], rbx
0x180018c25  mov     r13d, 1
0x180018c2b  mov     eax, r13d
0x180018c2e  lock cmpxchg cs:?g_lServerFailing@@3JA, r13d; long g_lServerFailing
0x180018c37  test    eax, eax
0x180018c39  jnz     loc_180018E5D
0x180018c3f  mov     rsi, [r8+18h]
0x180018c43  mov     rcx, rsi; hWnd
0x180018c46  call    cs:__imp_IsWindow
0x180018c4c  test    eax, eax
0x180018c4e  jz      short def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018c50  xor     r12d, r12d
0x180018c53  mov     [rsp+0A8h+dwProcessId], r12d
0x180018c58  lea     rdx, [rsp+0A8h+dwProcessId]; lpdwProcessId
0x180018c5d  mov     rcx, rsi; hWnd
0x180018c60  call    cs:__imp_GetWindowThreadProcessId
0x180018c66  call    cs:__imp_GetCurrentProcessId
0x180018c6c  cmp     eax, [rsp+0A8h+dwProcessId]
0x180018c70  jnz     short def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018c72  test    edi, edi
0x180018c74  js      short def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018c76  mov     edx, [rbx+10h]
0x180018c79  cmp     edx, 20h ; ' '
0x180018c7c  jnz     short loc_180018CB8
0x180018c7e  cmp     cs:dword_18016D79C, r12d
0x180018c85  jnz     loc_180018ECC
0x180018c8b  mov     r9, rbx; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018c8e  mov     r8, r14; wParam
0x180018c91  mov     edx, edi; nCode
0x180018c93  xor     ecx, ecx; hhk
0x180018c95  call    cs:__imp_CallNextHookEx
0x180018c9b  mov     rcx, [rsp+0A8h+var_40]
0x180018ca0  xor     rcx, rsp; StackCookie
0x180018ca3  call    __security_check_cookie
0x180018ca8  add     rsp, 70h
0x180018cac  pop     r15
0x180018cae  pop     r14
0x180018cb0  pop     r13
0x180018cb2  pop     r12
0x180018cb4  pop     rdi
0x180018cb5  pop     rsi
0x180018cb6  pop     rbx
0x180018cb7  retn
0x180018cb8  cmp     edx, 111h
0x180018cbe  jz      loc_180018E6D
0x180018cc4  ja      loc_180018E9D
0x180018cca  lea     eax, [rdx-2]; switch 70 cases
0x180018ccd  cmp     eax, 45h
0x180018cd0  ja      short def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018cd2  lea     r8, __ImageBase
0x180018cd9  movzx   eax, ds:(byte_1800190BC - 180000000h)[r8+rax]
0x180018ce2  mov     ecx, ds:(jpt_180018CED - 180000000h)[r8+rax*4]
0x180018cea  add     rcx, r8; this
0x180018ced  jmp     rcx; switch jump
0x180018cef  test    rsi, rsi; jumptable 0000000180018CED case 71
0x180018cf2  jz      short loc_180018D4D; jumptable 0000000180018CED cases 3,5
0x180018cf4  mov     edx, 2; gaFlags
0x180018cf9  mov     rcx, rsi; hwnd
0x180018cfc  call    cs:__imp_GetAncestor
0x180018d02  mov     r15, rax
0x180018d05  test    rax, rax
0x180018d08  jz      short loc_180018D4D; jumptable 0000000180018CED cases 3,5
0x180018d0a  mov     [rsp+0A8h+var_70], r12d
0x180018d0f  mov     [rsp+0A8h+dwindex], r12d
0x180018d14  lea     rdx, [rsp+0A8h+var_70]; lpdwProcessId
0x180018d19  mov     rcx, rsi; hWnd
0x180018d1c  call    cs:__imp_GetWindowThreadProcessId
0x180018d22  mov     r12d, eax
0x180018d25  lea     rdx, [rsp+0A8h+dwindex]; lpdwProcessId
0x180018d2a  mov     rcx, r15; hWnd
0x180018d2d  call    cs:__imp_GetWindowThreadProcessId
0x180018d33  mov     ecx, [rsp+0A8h+var_70]; this
0x180018d37  cmp     [rsp+0A8h+dwindex], ecx
0x180018d3b  jnz     loc_180018F99
0x180018d41  cmp     eax, r12d
0x180018d44  jnz     loc_180018F99
0x180018d4a  xor     r12d, r12d
0x180018d4d  xorps   xmm0, xmm0; jumptable 0000000180018CED cases 3,5
0x180018d50  movdqu  xmmword ptr [rsp+0A8h+Rect.left], xmm0
0x180018d56  mov     [rsp+0A8h+dwindex], r12d
0x180018d5b  lea     rax, [rsp+0A8h+dwindex]
0x180018d60  mov     [rsp+0A8h+lpdwindex], rax; lpdwindex
0x180018d65  lea     r9, hMutex; pHandles
0x180018d6c  mov     r8d, r13d; cHandles
0x180018d6f  mov     edx, 0FFFFFFFFh; dwTimeout
0x180018d74  xor     ecx, ecx; dwFlags
0x180018d76  call    cs:__imp_CoWaitForMultipleHandles
0x180018d7c  lea     rdx, [rsp+0A8h+Rect]; lpRect
0x180018d81  mov     rcx, rsi; hWnd
0x180018d84  call    cs:__imp_GetClientRect
0x180018d8a  test    eax, eax
0x180018d8c  jz      short loc_180018DC4
0x180018d8e  mov     r9d, 2; cPoints
0x180018d94  lea     r8, [rsp+0A8h+Rect]; lpPoints
0x180018d99  xor     edx, edx; hWndTo
0x180018d9b  mov     rcx, rsi; hWndFrom
0x180018d9e  call    cs:__imp_MapWindowPoints
0x180018da4  cmp     cs:qword_18016D280, rsi
0x180018dab  jz      loc_180018EEA
0x180018db1  mov     cs:qword_18016D280, rsi
0x180018db8  movups  xmm0, xmmword ptr [rsp+0A8h+Rect.left]
0x180018dbd  movups  xmmword ptr cs:rc2.left, xmm0
0x180018dc4  mov     rcx, cs:hMutex; hMutex
0x180018dcb  call    cs:__imp_ReleaseMutex
0x180018dd1  mov     ecx, cs:_tls_index
0x180018dd7  mov     rax, gs:58h
0x180018de0  mov     edx, 4
0x180018de5  mov     rax, [rax+rcx*8]
0x180018de9  mov     ecx, [rdx+rax]
0x180018dec  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, ecx
0x180018df2  jg      loc_180018FB0
0x180018df8  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180018dff  test    rcx, rcx
0x180018e02  jz      def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018e08  mov     r8d, 18h; dwBytes
0x180018e0e  mov     edx, cs:dwFlags; dwFlags
0x180018e14  call    cs:__imp_HeapAlloc
0x180018e1a  mov     r15, rax
0x180018e1d  test    rax, rax
0x180018e20  jz      def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018e26  mov     [rax+8], rsi
0x180018e2a  mov     [rax+10h], r12d
0x180018e2e  mov     [rax], r12
0x180018e31  mov     r8, rax; dwData
0x180018e34  mov     rdx, cs:hObject; hThread
0x180018e3b  lea     rcx, ?ResizeContext@CCContext@@KAX_K@Z; pfnAPC
0x180018e42  call    cs:__imp_QueueUserAPC
0x180018e48  test    eax, eax
0x180018e4a  jnz     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018e50  mov     rcx, r15; this
0x180018e53  call    ??_GCAPCParam@@QEAAPEAXI@Z; CAPCParam::`scalar deleting destructor'(uint)
0x180018e58  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018e5d  cmp     dword ptr [r8+10h], 2
0x180018e62  jz      loc_180018C3F
0x180018e68  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018e6d  movzx   ecx, word ptr [rbx+0Ah]; this
0x180018e71  lea     eax, [rcx-7]
0x180018e74  cmp     ax, 1
0x180018e78  ja      def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018e7e  mov     r9d, r12d
0x180018e81  cmp     cx, 8
0x180018e85  setz    r9b; int
0x180018e89  mov     r8, rsi; unsigned __int64
0x180018e8c  lea     rdx, ?BringWindowContextToTop@CCContext@@KAX_K@Z; void (*)(unsigned __int64)
0x180018e93  call    ?ExecuteCallOnApcThread@CComDllModule@@QEAAXP6AX_K@Z0H@Z; CComDllModule::ExecuteCallOnApcThread(void (*)(unsigned __int64),unsigned __int64,int)
0x180018e98  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018e9d  mov     eax, edx
0x180018e9f  sub     eax, 117h
0x180018ea4  jz      loc_18001907D
0x180018eaa  sub     eax, 0Eh
0x180018ead  jz      loc_180019066
0x180018eb3  sub     eax, 0FDh
0x180018eb8  jz      short loc_180018F28
0x180018eba  sub     eax, 0Fh
0x180018ebd  jz      loc_180019030
0x180018ec3  cmp     eax, 1
0x180018ec6  jnz     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018ecc  xor     r9d, r9d; int
0x180018ecf  mov     r8, rsi; unsigned __int64
0x180018ed2  lea     rdx, ?EnableContext@CCContext@@KAX_K@Z; void (*)(unsigned __int64)
0x180018ed9  call    ?ExecuteCallOnApcThread@CComDllModule@@QEAAXP6AX_K@Z0H@Z; CComDllModule::ExecuteCallOnApcThread(void (*)(unsigned __int64),unsigned __int64,int)
0x180018ede  mov     cs:dword_18016D79C, r12d
0x180018ee5  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018eea  lea     rdx, rc2; lprc2
0x180018ef1  lea     rcx, [rsp+0A8h+Rect]; lprc1
0x180018ef6  call    cs:__imp_EqualRect
0x180018efc  test    eax, eax
0x180018efe  jz      loc_180018DB1
0x180018f04  mov     rcx, cs:hMutex; hMutex
0x180018f0b  call    cs:__imp_ReleaseMutex
0x180018f11  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018f16  cmp     edx, 6; jumptable 0000000180018CED cases 6,34
0x180018f19  jz      loc_180019022
0x180018f1f  cmp     edx, 22h ; '"'
0x180018f22  jz      loc_180019051
0x180018f28  cmp     edx, 222h
0x180018f2e  jz      loc_18001904E
0x180018f34  mov     ecx, 18h; unsigned __int64
0x180018f39  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x180018f3e  mov     r15, rax
0x180018f41  test    rax, rax
0x180018f44  jz      short loc_180018F74
0x180018f46  mov     [rax+8], rsi
0x180018f4a  mov     [rax+10h], r12d
0x180018f4e  mov     qword ptr [rax], 0
0x180018f55  mov     r8, rax; dwData
0x180018f58  mov     rdx, cs:hObject; hThread
0x180018f5f  lea     rcx, ?BringWindowContextToTop@CCContext@@KAX_K@Z; pfnAPC
0x180018f66  call    cs:__imp_QueueUserAPC
0x180018f6c  test    eax, eax
0x180018f6e  jz      loc_180019059
0x180018f74  cmp     dword ptr [rbx+10h], 222h
0x180018f7b  jnz     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018f81  xor     r9d, r9d; int
0x180018f84  mov     r8, [rbx+8]; unsigned __int64
0x180018f88  lea     rdx, ?BringWindowContextToTop@CCContext@@KAX_K@Z; void (*)(unsigned __int64)
0x180018f8f  call    ?ExecuteCallOnApcThread@CComDllModule@@QEAAXP6AX_K@Z0H@Z; CComDllModule::ExecuteCallOnApcThread(void (*)(unsigned __int64),unsigned __int64,int)
0x180018f94  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180018f99  xor     r9d, r9d; int
0x180018f9c  mov     r8, rsi; unsigned __int64
0x180018f9f  lea     rdx, ?EnableTimerForWndSubtree@CCContext@@KAX_K@Z; void (*)(unsigned __int64)
0x180018fa6  call    ?ExecuteCallOnApcThread@CComDllModule@@QEAAXP6AX_K@Z0H@Z; CComDllModule::ExecuteCallOnApcThread(void (*)(unsigned __int64),unsigned __int64,int)
0x180018fab  jmp     loc_180018D4A
0x180018fb0  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180018fb7  call    _Init_thread_header
0x180018fbc  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180018fc3  jnz     loc_180018DF8
0x180018fc9  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, r12; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180018fd0  mov     cs:dwFlags, r12d
0x180018fd7  xor     r8d, r8d; dwMaximumSize
0x180018fda  mov     edx, 10000h; dwInitialSize
0x180018fdf  xor     ecx, ecx; flOptions
0x180018fe1  call    cs:__imp_HeapCreate
0x180018fe7  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180018fee  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180018ff5  call    atexit
0x180018ffa  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180019001  call    _Init_thread_footer
0x180019006  jmp     loc_180018DF8
0x18001900b  xor     r9d, r9d; jumptable 0000000180018CED case 2
0x18001900e  mov     r8, rsi; unsigned __int64
0x180019011  lea     rdx, ?UnhookContext@CCContext@@KAX_K@Z; void (*)(unsigned __int64)
0x180019018  call    ?ExecuteCallOnApcThread@CComDllModule@@QEAAXP6AX_K@Z0H@Z; CComDllModule::ExecuteCallOnApcThread(void (*)(unsigned __int64),unsigned __int64,int)
0x18001901d  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180019022  cmp     qword ptr [rbx+8], 0
0x180019027  setnz   r12b
0x18001902b  jmp     loc_180018F34
0x180019030  xor     r9d, r9d; int
0x180019033  mov     r8, rsi; unsigned __int64
0x180019036  lea     rdx, ?DisableContext@CCContext@@KAX_K@Z; void (*)(unsigned __int64)
0x18001903d  call    ?ExecuteCallOnApcThread@CComDllModule@@QEAAXP6AX_K@Z0H@Z; CComDllModule::ExecuteCallOnApcThread(void (*)(unsigned __int64),unsigned __int64,int)
0x180019042  mov     cs:dword_18016D79C, r13d
0x180019049  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x18001904e  mov     rsi, [rbx]
0x180019051  mov     r12d, r13d
0x180019054  jmp     loc_180018F34
0x180019059  mov     rcx, r15; this
0x18001905c  call    ??_GCAPCParam@@QEAAPEAXI@Z; CAPCParam::`scalar deleting destructor'(uint)
0x180019061  jmp     loc_180018F74
0x180019066  mov     r9d, r13d; int
0x180019069  mov     r8, rsi; unsigned __int64
0x18001906c  lea     rdx, ?BringWindowContextToTop@CCContext@@KAX_K@Z; void (*)(unsigned __int64)
0x180019073  call    ?ExecuteCallOnApcThread@CComDllModule@@QEAAXP6AX_K@Z0H@Z; CComDllModule::ExecuteCallOnApcThread(void (*)(unsigned __int64),unsigned __int64,int)
0x180019078  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x18001907d  xor     r9d, r9d; int
0x180019080  mov     r8, rsi; unsigned __int64
0x180019083  lea     rdx, ?BringWindowContextToTop@CCContext@@KAX_K@Z; void (*)(unsigned __int64)
0x18001908a  call    ?ExecuteCallOnApcThread@CComDllModule@@QEAAXP6AX_K@Z0H@Z; CComDllModule::ExecuteCallOnApcThread(void (*)(unsigned __int64),unsigned __int64,int)
0x18001908f  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
0x180019094  mov     edi, [rsp+0A8h+var_68]
0x180019098  mov     r14, [rsp+0A8h+var_60]
0x18001909d  mov     rbx, [rsp+0A8h+var_58]
0x1800190a2  jmp     def_180018CED; jumptable 0000000180018CED default case, cases 4,7-33,35-70
```
