# PAL_System_CondWait

- ea: `0x18001a450`
- end: `0x18001a755`
- name: `PAL_System_CondWait`
- size: `773`
- prototype: `__int64 __usercall@<rax>(HANDLE *pHandles@<rcx>, DWORD nCount@<edx>, BOOL bWaitAll, int, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800182d0`
- `0x180087fc8`

## callees

- `0x180001180`
- `0x180001518`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a490`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a490`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a487`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a59a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a487`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a59a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001a4e1`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001a4e1`
- `USER32!DispatchMessageW` at `0x18001a523`
- `USER32!DispatchMessageW` at `0x18001a523`
- `USER32!PeekMessageW` at `0x18001a508`
- `USER32!PeekMessageW` at `0x18001a508`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18001a542`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18001a577`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18001a542`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18001a577`

## string_xrefs

- `0x18001a5cd`: `Thread: 0x%x got a WM_QUIT`
- `0x18001a62a`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18001a671`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18001a686`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_CondWait(
        HANDLE *pHandles,
        DWORD nCount,
        const char *a3,
        DWORD a4,
        BOOL bWaitAll,
        int a6,
        DWORD *a7)
{
  DWORD *v10; // rdi
  unsigned int v11; // ebx
  DWORD v12; // ecx
  int v13; // r8d
  int v14; // r9d
  unsigned int v15; // r12d
  unsigned int i; // r15d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  DWORD v20; // eax
  DWORD TickCount; // eax
  DWORD v22; // ecx
  const char *v24; // [rsp+50h] [rbp-31h] BYREF
  const char *v25; // [rsp+58h] [rbp-29h] BYREF
  tagMSG Msg; // [rsp+60h] [rbp-21h] BYREF
  const char *v27; // [rsp+D0h] [rbp+4Fh] BYREF
  const char *v28; // [rsp+E0h] [rbp+5Fh] BYREF
  DWORD dwMilliseconds; // [rsp+E8h] [rbp+67h] BYREF

  dwMilliseconds = a4;
  v28 = a3;
  memset(&Msg, 0, sizeof(Msg));
  LODWORD(v28) = GetTickCount();
  LODWORD(v27) = GetCurrentThreadId();
  if ( pHandles && (v10 = a7) != 0 && nCount )
  {
    if ( bWaitAll )
      *a7 = 0;
    v11 = -2147467259;
    if ( a6 )
    {
      v12 = WaitForMultipleObjects(nCount, pHandles, bWaitAll, a4);
    }
    else
    {
      v15 = a4;
      while ( 1 )
      {
LABEL_9:
        for ( i = 0; i < 0x64; ++i )
        {
          if ( !PeekMessageW(&Msg, 0, 0, 0, 1u) )
            break;
          if ( Msg.message == 18 )
          {
            if ( (unsigned int)dword_1800EB958 > 4 )
            {
              dwMilliseconds = (unsigned int)v27;
              v28 = "Thread: 0x%x got a WM_QUIT";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v17,
                (unsigned int)byte_1800CD059,
                v18,
                v19,
                (__int64)&v28,
                (__int64)&dwMilliseconds);
            }
            return (unsigned int)-2092629812;
          }
          DispatchMessageW(&Msg);
        }
        v12 = MsgWaitForMultipleObjectsEx(nCount, pHandles, 0, 0, 6u);
        if ( v12 <= nCount - 1 )
          goto LABEL_26;
        if ( v12 != 192 )
        {
          v20 = MsgWaitForMultipleObjectsEx(nCount, pHandles, dwMilliseconds, 0x1CFFu, 6u);
          v12 = v20;
          if ( v20 != 192 )
          {
            if ( v20 != nCount )
              goto LABEL_26;
            if ( v15 != -1 )
              break;
          }
        }
      }
      TickCount = GetTickCount();
      v22 = TickCount - (_DWORD)v28;
      if ( TickCount - (unsigned int)v28 < v15 )
      {
        v15 -= v22;
        LODWORD(v28) = TickCount;
        goto LABEL_9;
      }
      if ( (unsigned int)dword_1800EB958 > 2 )
      {
        dwMilliseconds = 242;
        v25 = "Timeout processing window messages";
        v27 = "PAL_System_CondWait";
        v24 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
        LODWORD(v28) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)byte_1800CD0C9,
          v13,
          v14,
          (__int64)&v25,
          (__int64)&v28,
          (__int64)&v24,
          (__int64)&dwMilliseconds,
          (__int64)&v27);
      }
      v12 = 258;
    }
LABEL_26:
    if ( v12 > nCount - 1 )
    {
      if ( v12 < 0x80 || v12 > nCount + 127 )
      {
        if ( v12 == 258 )
        {
          *v10 = 0;
          return (unsigned int)-2092629813;
        }
        else if ( (unsigned int)dword_1800EB958 > 2 )
        {
          v27 = "PAL_System_CondWait";
          v24 = "Wait Failed with unknown error";
          dwMilliseconds = 295;
          v25 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
          LODWORD(v28) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)byte_1800CD153,
            v13,
            v14,
            (__int64)&v24,
            (__int64)&v28,
            (__int64)&v25,
            (__int64)&dwMilliseconds,
            (__int64)&v27);
        }
      }
      else
      {
        if ( !bWaitAll )
          *v10 = v12 - 128;
        return (unsigned int)-2092629814;
      }
    }
    else
    {
      if ( !bWaitAll )
        *v10 = v12;
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x18001a450  mov     [rsp-8+dwMilliseconds], r9d
0x18001a455  mov     [rsp-8+arg_10], r8
0x18001a45a  push    rbp
0x18001a45b  push    rbx
0x18001a45c  push    rsi
0x18001a45d  push    rdi
0x18001a45e  push    r12
0x18001a460  push    r13
0x18001a462  push    r15
0x18001a464  lea     rbp, [rsp-0Fh]
0x18001a469  sub     rsp, 90h
0x18001a470  xorps   xmm0, xmm0
0x18001a473  mov     r15d, r9d
0x18001a476  movups  xmmword ptr [rbp+3Fh+Msg.hwnd], xmm0
0x18001a47a  mov     esi, edx
0x18001a47c  mov     r13, rcx
0x18001a47f  movups  xmmword ptr [rbp+3Fh+Msg.wParam], xmm0
0x18001a483  movups  xmmword ptr [rbp+3Fh+Msg.time], xmm0
0x18001a487  call    cs:__imp_GetTickCount
0x18001a48d  mov     dword ptr [rbp+3Fh+arg_10], eax
0x18001a490  call    cs:__imp_GetCurrentThreadId
0x18001a496  mov     dword ptr [rbp+3Fh+arg_0], eax
0x18001a499  test    r13, r13
0x18001a49c  jz      loc_18001A73C
0x18001a4a2  mov     rdi, [rbp+3Fh+arg_30]
0x18001a4a6  test    rdi, rdi
0x18001a4a9  jz      loc_18001A73C
0x18001a4af  test    esi, esi
0x18001a4b1  jz      loc_18001A73C
0x18001a4b7  cmp     [rbp+3Fh+bWaitAll], 0
0x18001a4bb  jz      short loc_18001A4C3
0x18001a4bd  mov     dword ptr [rdi], 0
0x18001a4c3  cmp     [rbp+3Fh+arg_28], 0
0x18001a4c7  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x18001a4ce  mov     ebx, 80004005h
0x18001a4d3  jz      short loc_18001A4EE
0x18001a4d5  mov     r8d, [rbp+3Fh+bWaitAll]; bWaitAll
0x18001a4d9  mov     r9d, r15d; dwMilliseconds
0x18001a4dc  mov     rdx, r13; lpHandles
0x18001a4df  mov     ecx, esi; nCount
0x18001a4e1  call    cs:__imp_WaitForMultipleObjects
0x18001a4e7  mov     ecx, eax
0x18001a4e9  jmp     loc_18001A686
0x18001a4ee  mov     r12d, r15d
0x18001a4f1  xor     r15d, r15d
0x18001a4f4  xor     r9d, r9d; wMsgFilterMax
0x18001a4f7  mov     [rsp+0C0h+wRemoveMsg], 1; wRemoveMsg
0x18001a4ff  xor     r8d, r8d; wMsgFilterMin
0x18001a502  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x18001a506  xor     edx, edx; hWnd
0x18001a508  call    cs:__imp_PeekMessageW
0x18001a50e  test    eax, eax
0x18001a510  jz      short loc_18001A52F
0x18001a512  cmp     [rbp+3Fh+Msg.message], 12h
0x18001a516  jz      loc_18001A5B5
0x18001a51c  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x18001a520  inc     r15d
0x18001a523  call    cs:__imp_DispatchMessageW
0x18001a529  cmp     r15d, 64h ; 'd'
0x18001a52d  jb      short loc_18001A4F4
0x18001a52f  xor     r9d, r9d; dwWakeMask
0x18001a532  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x18001a53a  xor     r8d, r8d; dwMilliseconds
0x18001a53d  mov     rdx, r13; pHandles
0x18001a540  mov     ecx, esi; nCount
0x18001a542  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18001a548  mov     ecx, eax
0x18001a54a  lea     eax, [rsi-1]
0x18001a54d  cmp     ecx, eax
0x18001a54f  jbe     loc_18001A67F
0x18001a555  mov     r15d, 0C0h
0x18001a55b  cmp     ecx, r15d
0x18001a55e  jz      short loc_18001A4F1
0x18001a560  mov     r8d, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x18001a564  mov     r9d, 1CFFh; dwWakeMask
0x18001a56a  mov     rdx, r13; pHandles
0x18001a56d  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x18001a575  mov     ecx, esi; nCount
0x18001a577  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18001a57d  mov     ecx, eax
0x18001a57f  cmp     eax, r15d
0x18001a582  jz      loc_18001A4F1
0x18001a588  cmp     eax, esi
0x18001a58a  jnz     loc_18001A67F
0x18001a590  cmp     r12d, 0FFFFFFFFh
0x18001a594  jz      loc_18001A4F1
0x18001a59a  call    cs:__imp_GetTickCount
0x18001a5a0  mov     ecx, eax
0x18001a5a2  sub     ecx, dword ptr [rbp+3Fh+arg_10]
0x18001a5a5  cmp     ecx, r12d
0x18001a5a8  jnb     short loc_18001A5F9
0x18001a5aa  sub     r12d, ecx
0x18001a5ad  mov     dword ptr [rbp+3Fh+arg_10], eax
0x18001a5b0  jmp     loc_18001A4F1
0x18001a5b5  mov     eax, cs:dword_1800EB958
0x18001a5bb  cmp     eax, 4
0x18001a5be  jbe     short loc_18001A5EF
0x18001a5c0  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x18001a5c3  lea     rdx, byte_1800CD059
0x18001a5ca  mov     [rbp+3Fh+dwMilliseconds], eax
0x18001a5cd  lea     rax, aThread0xXGotAW; "Thread: 0x%x got a WM_QUIT"
0x18001a5d4  mov     [rbp+3Fh+arg_10], rax
0x18001a5d8  lea     rax, [rbp+3Fh+dwMilliseconds]
0x18001a5dc  mov     [rsp+0C0h+var_98], rax
0x18001a5e1  lea     rax, [rbp+3Fh+arg_10]
0x18001a5e5  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x18001a5ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001a5ef  mov     ebx, 834500CCh
0x18001a5f4  jmp     loc_18001A741
0x18001a5f9  mov     eax, cs:dword_1800EB958
0x18001a5ff  cmp     eax, 2
0x18001a602  jbe     short loc_18001A66A
0x18001a604  lea     rax, aTimeoutProcess; "Timeout processing window messages"
0x18001a60b  mov     [rbp+3Fh+dwMilliseconds], 0F2h
0x18001a612  mov     [rbp+3Fh+var_68], rax
0x18001a616  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x18001a61d  lea     rax, [rbp+3Fh+arg_0]
0x18001a621  mov     [rbp+3Fh+arg_0], r12
0x18001a625  mov     [rsp+0C0h+var_80], rax
0x18001a62a  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001a631  lea     rax, [rbp+3Fh+dwMilliseconds]
0x18001a635  mov     [rbp+3Fh+var_70], r15
0x18001a639  mov     [rsp+0C0h+var_88], rax
0x18001a63e  lea     rdx, byte_1800CD0C9
0x18001a645  lea     rax, [rbp+3Fh+var_70]
0x18001a649  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x18001a64c  mov     [rsp+0C0h+var_90], rax
0x18001a651  lea     rax, [rbp+3Fh+arg_10]
0x18001a655  mov     [rsp+0C0h+var_98], rax
0x18001a65a  lea     rax, [rbp+3Fh+var_68]
0x18001a65e  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x18001a663  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001a668  jmp     short loc_18001A678
0x18001a66a  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x18001a671  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001a678  mov     ecx, 102h
0x18001a67d  jmp     short loc_18001A68D
0x18001a67f  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x18001a686  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001a68d  lea     eax, [rsi-1]
0x18001a690  cmp     ecx, eax
0x18001a692  ja      short loc_18001A6A3
0x18001a694  cmp     [rbp+3Fh+bWaitAll], 0
0x18001a698  jnz     short loc_18001A69C
0x18001a69a  mov     [rdi], ecx
0x18001a69c  xor     ebx, ebx
0x18001a69e  jmp     loc_18001A741
0x18001a6a3  cmp     ecx, 80h
0x18001a6a9  jb      short loc_18001A6C4
0x18001a6ab  lea     eax, [rsi+7Fh]
0x18001a6ae  cmp     ecx, eax
0x18001a6b0  ja      short loc_18001A6C4
0x18001a6b2  cmp     [rbp+3Fh+bWaitAll], 0
0x18001a6b6  jnz     short loc_18001A6BD
0x18001a6b8  lea     eax, [rcx-80h]
0x18001a6bb  mov     [rdi], eax
0x18001a6bd  mov     ebx, 834500CAh
0x18001a6c2  jmp     short loc_18001A741
0x18001a6c4  cmp     ecx, 102h
0x18001a6ca  jnz     short loc_18001A6D9
0x18001a6cc  mov     dword ptr [rdi], 0
0x18001a6d2  mov     ebx, 834500CBh
0x18001a6d7  jmp     short loc_18001A741
0x18001a6d9  mov     eax, cs:dword_1800EB958
0x18001a6df  cmp     eax, 2
0x18001a6e2  jbe     short loc_18001A741
0x18001a6e4  lea     rax, aWaitFailedWith; "Wait Failed with unknown error"
0x18001a6eb  mov     [rbp+3Fh+arg_0], r12
0x18001a6ef  mov     [rbp+3Fh+var_70], rax
0x18001a6f3  lea     rdx, byte_1800CD153
0x18001a6fa  lea     rax, [rbp+3Fh+arg_0]
0x18001a6fe  mov     [rbp+3Fh+dwMilliseconds], 127h
0x18001a705  mov     [rsp+0C0h+var_80], rax
0x18001a70a  lea     rax, [rbp+3Fh+dwMilliseconds]
0x18001a70e  mov     [rsp+0C0h+var_88], rax
0x18001a713  lea     rax, [rbp+3Fh+var_68]
0x18001a717  mov     [rsp+0C0h+var_90], rax
0x18001a71c  lea     rax, [rbp+3Fh+arg_10]
0x18001a720  mov     [rsp+0C0h+var_98], rax
0x18001a725  lea     rax, [rbp+3Fh+var_70]
0x18001a729  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x18001a72e  mov     [rbp+3Fh+var_68], r15
0x18001a732  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x18001a735  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001a73a  jmp     short loc_18001A741
0x18001a73c  mov     ebx, 80070057h
0x18001a741  mov     eax, ebx
0x18001a743  add     rsp, 90h
0x18001a74a  pop     r15
0x18001a74c  pop     r13
0x18001a74e  pop     r12
0x18001a750  pop     rdi
0x18001a751  pop     rsi
0x18001a752  pop     rbx
0x18001a753  pop     rbp
0x18001a754  retn
```
