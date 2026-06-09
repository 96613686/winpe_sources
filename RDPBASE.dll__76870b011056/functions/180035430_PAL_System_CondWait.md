# PAL_System_CondWait

- ea: `0x180035430`
- end: `0x18003582a`
- name: `PAL_System_CondWait`
- size: `1018`
- prototype: `__int64 __usercall@<rax>(HANDLE *pHandles@<rcx>, DWORD nCount@<edx>, BOOL bWaitAll, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800351f0`

## callees

- `0x1800018a4`
- `0x180035430`
- `0x180078c20`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180035675`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180035675`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003547d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003547d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180035474`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180035597`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180035474`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180035597`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800354d9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800354d9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x180035507`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x180035507`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x180035522`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x180035522`
- `ext-ms-win-rtcore-ntuser-synch-ext-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180035540`
- `ext-ms-win-rtcore-ntuser-synch-ext-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180035573`
- `ext-ms-win-rtcore-ntuser-synch-ext-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180035540`
- `ext-ms-win-rtcore-ntuser-synch-ext-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180035573`

## string_xrefs

- `0x1800355e7`: `Thread: 0x%x got a WM_QUIT`
- `0x1800356e2`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18003573d`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18003574d`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_CondWait(
        HANDLE *pHandles,
        DWORD nCount,
        __int64 a3,
        DWORD a4,
        BOOL bWaitAll,
        int a6,
        DWORD *a7)
{
  DWORD TickCount; // r13d
  DWORD v11; // ecx
  int v12; // r8d
  int v13; // r9d
  unsigned int v14; // esi
  unsigned int i; // ebx
  DWORD v16; // eax
  DWORD v17; // eax
  DWORD v18; // ecx
  __int64 result; // rax
  DWORD dwMilliseconds; // [rsp+50h] [rbp-B0h] BYREF
  DWORD CurrentThreadId; // [rsp+54h] [rbp-ACh] BYREF
  const char *v22; // [rsp+58h] [rbp-A8h] BYREF
  const char *v23; // [rsp+60h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-98h] BYREF
  tagMSG Msg; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  char *v27; // [rsp+C0h] [rbp-40h]
  int v28; // [rsp+C8h] [rbp-38h]
  int v29; // [rsp+CCh] [rbp-34h]
  const char *v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  DWORD *p_CurrentThreadId; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+E8h] [rbp-18h]

  dwMilliseconds = a4;
  memset(&Msg, 0, sizeof(Msg));
  TickCount = GetTickCount();
  CurrentThreadId = GetCurrentThreadId();
  if ( !pHandles || !a7 || !nCount )
    return 2147942487LL;
  if ( bWaitAll )
    *a7 = 0;
  if ( a6 )
  {
    v11 = WaitForMultipleObjects(nCount, pHandles, bWaitAll, a4);
  }
  else
  {
    v14 = a4;
    while ( 1 )
    {
LABEL_9:
      for ( i = 0; i < 0x64; ++i )
      {
        if ( !PeekMessageW(&Msg, 0, 0, 0, 1u) )
          break;
        if ( Msg.message == 18 )
        {
          if ( (unsigned int)CallbackContext > 4 )
          {
            EventDescriptor.Keyword = 0;
            p_CurrentThreadId = &CurrentThreadId;
            v33 = 4;
            v30 = "Thread: 0x%x got a WM_QUIT";
            *(_DWORD *)&EventDescriptor.Level = 4;
            UserData.Ptr = (ULONGLONG)off_1801E7010;
            v31 = 27;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            UserData.Size = *(unsigned __int16 *)off_1801E7010;
            v27 = byte_1801CBE3D;
            UserData.Reserved = 2;
            v28 = 31;
            v29 = 1;
            dwMilliseconds = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
          }
          return 2202337484LL;
        }
        DispatchMessageW(&Msg);
      }
      v11 = MsgWaitForMultipleObjectsEx(nCount, pHandles, 0, 0, 6u);
      if ( v11 <= nCount - 1 )
        goto LABEL_27;
      if ( v11 != 192 )
      {
        v16 = MsgWaitForMultipleObjectsEx(nCount, pHandles, dwMilliseconds, 0x1CFFu, 6u);
        v11 = v16;
        if ( v16 != 192 )
        {
          if ( v16 != nCount )
            goto LABEL_27;
          if ( v14 != -1 )
            break;
        }
      }
    }
    v17 = GetTickCount();
    v18 = v17 - TickCount;
    if ( v17 - TickCount < v14 )
    {
      v14 -= v18;
      TickCount = v17;
      goto LABEL_9;
    }
    if ( (unsigned int)CallbackContext > 2 )
    {
      CurrentThreadId = 242;
      *(_QWORD *)&EventDescriptor.Id = "Timeout processing window messages";
      v22 = "PAL_System_CondWait";
      v23 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      dwMilliseconds = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v18,
        (unsigned int)byte_1801CBFFB,
        v12,
        v13,
        (__int64)&EventDescriptor,
        (__int64)&dwMilliseconds,
        (__int64)&v23,
        (__int64)&CurrentThreadId,
        (__int64)&v22);
    }
    v11 = 258;
  }
LABEL_27:
  if ( v11 > nCount - 1 )
  {
    if ( v11 < 0x80 || v11 > nCount + 127 )
    {
      if ( v11 == 258 )
      {
        result = 2202337483LL;
        *a7 = 0;
      }
      else
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          *(_QWORD *)&EventDescriptor.Id = "PAL_System_CondWait";
          CurrentThreadId = 295;
          v23 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
          dwMilliseconds = -2147467259;
          v22 = "Wait Failed with unknown error";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (unsigned int)&v22,
            (unsigned int)byte_1801CC085,
            v12,
            v13,
            (__int64)&v22,
            (__int64)&dwMilliseconds,
            (__int64)&v23,
            (__int64)&CurrentThreadId,
            (__int64)&EventDescriptor);
        }
        return 2147500037LL;
      }
    }
    else
    {
      if ( !bWaitAll )
        *a7 = v11 - 128;
      return 2202337482LL;
    }
  }
  else
  {
    if ( !bWaitAll )
      *a7 = v11;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180035430  push    rbp
0x180035432  push    rbx
0x180035433  push    rdi
0x180035434  push    r12
0x180035436  push    r13
0x180035438  push    r14
0x18003543a  lea     rbp, [rsp-8]
0x18003543f  sub     rsp, 108h
0x180035446  mov     rax, cs:__security_cookie
0x18003544d  xor     rax, rsp
0x180035450  mov     [rbp+30h+var_40], rax
0x180035454  mov     r14, [rbp+30h+arg_30]
0x180035458  xorps   xmm0, xmm0
0x18003545b  mov     ebx, r9d
0x18003545e  mov     edi, edx
0x180035460  mov     [rsp+130h+dwMilliseconds], ebx
0x180035464  mov     r12, rcx
0x180035467  movups  xmmword ptr [rsp+130h+Msg.hwnd], xmm0
0x18003546c  movups  xmmword ptr [rbp+30h+Msg.wParam], xmm0
0x180035470  movups  xmmword ptr [rbp+30h+Msg.time], xmm0
0x180035474  call    cs:__imp_GetTickCount
0x18003547a  mov     r13d, eax
0x18003547d  call    cs:__imp_GetCurrentThreadId
0x180035483  mov     [rsp+130h+var_DC], eax
0x180035487  test    r12, r12
0x18003548a  jz      loc_180035820
0x180035490  test    r14, r14
0x180035493  jz      loc_180035820
0x180035499  test    edi, edi
0x18003549b  jz      loc_180035820
0x1800354a1  mov     [rsp+130h+arg_10], rsi
0x1800354a9  mov     [rsp+130h+var_30], r15
0x1800354b1  mov     r15d, [rbp+30h+bWaitAll]
0x1800354b5  test    r15d, r15d
0x1800354b8  jz      short loc_1800354C1
0x1800354ba  mov     dword ptr [r14], 0
0x1800354c1  cmp     [rbp+30h+arg_28], 0
0x1800354c5  lea     rsi, aPalSystemCondw_0; "PAL_System_CondWait"
0x1800354cc  jz      short loc_1800354E6
0x1800354ce  mov     r9d, ebx; dwMilliseconds
0x1800354d1  mov     r8d, r15d; bWaitAll
0x1800354d4  mov     rdx, r12; lpHandles
0x1800354d7  mov     ecx, edi; nCount
0x1800354d9  call    cs:__imp_WaitForMultipleObjects
0x1800354df  mov     ecx, eax
0x1800354e1  jmp     loc_18003574D
0x1800354e6  mov     esi, ebx
0x1800354e8  nop     dword ptr [rax+rax+00000000h]
0x1800354f0  xor     ebx, ebx
0x1800354f2  xor     r9d, r9d; wMsgFilterMax
0x1800354f5  mov     [rsp+130h+wRemoveMsg], 1; wRemoveMsg
0x1800354fd  xor     r8d, r8d; wMsgFilterMin
0x180035500  lea     rcx, [rsp+130h+Msg]; lpMsg
0x180035505  xor     edx, edx; hWnd
0x180035507  call    cs:__imp_PeekMessageW
0x18003550d  test    eax, eax
0x18003550f  jz      short loc_18003552D
0x180035511  cmp     [rbp+30h+Msg.message], 12h
0x180035515  jz      loc_1800355B4
0x18003551b  lea     rcx, [rsp+130h+Msg]; lpMsg
0x180035520  inc     ebx
0x180035522  call    cs:__imp_DispatchMessageW
0x180035528  cmp     ebx, 64h ; 'd'
0x18003552b  jb      short loc_1800354F2
0x18003552d  xor     r9d, r9d; dwWakeMask
0x180035530  mov     [rsp+130h+wRemoveMsg], 6; dwFlags
0x180035538  xor     r8d, r8d; dwMilliseconds
0x18003553b  mov     rdx, r12; pHandles
0x18003553e  mov     ecx, edi; nCount
0x180035540  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180035546  mov     ecx, eax
0x180035548  lea     eax, [rdi-1]
0x18003554b  cmp     ecx, eax
0x18003554d  jbe     loc_180035746
0x180035553  cmp     ecx, 0C0h
0x180035559  jz      short loc_1800354F0
0x18003555b  mov     r8d, [rsp+130h+dwMilliseconds]; dwMilliseconds
0x180035560  mov     r9d, 1CFFh; dwWakeMask
0x180035566  mov     rdx, r12; pHandles
0x180035569  mov     [rsp+130h+wRemoveMsg], 6; dwFlags
0x180035571  mov     ecx, edi; nCount
0x180035573  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180035579  mov     ecx, eax
0x18003557b  cmp     eax, 0C0h
0x180035580  jz      loc_1800354F0
0x180035586  cmp     eax, edi
0x180035588  jnz     loc_180035746
0x18003558e  cmp     esi, 0FFFFFFFFh
0x180035591  jz      loc_1800354F0
0x180035597  call    cs:__imp_GetTickCount
0x18003559d  mov     ecx, eax
0x18003559f  sub     ecx, r13d
0x1800355a2  cmp     ecx, esi
0x1800355a4  jnb     loc_1800356AD
0x1800355aa  sub     esi, ecx
0x1800355ac  mov     r13d, eax
0x1800355af  jmp     loc_1800354F0
0x1800355b4  mov     eax, cs:CallbackContext
0x1800355ba  cmp     eax, 4
0x1800355bd  jbe     loc_18003567B
0x1800355c3  mov     eax, [rsp+130h+var_DC]
0x1800355c7  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x1800355cc  mov     [rsp+130h+var_DC], eax
0x1800355d0  xor     ecx, ecx
0x1800355d2  mov     [rsp+130h+EventDescriptor.Keyword], rcx
0x1800355d7  lea     rax, [rsp+130h+var_DC]
0x1800355dc  mov     [rbp+30h+var_50], rax
0x1800355e0  lea     rcx, _TraceLoggingMetadata
0x1800355e7  lea     rax, aThread0xXGotAW; "Thread: 0x%x got a WM_QUIT"
0x1800355ee  mov     [rbp+30h+var_48], 4
0x1800355f6  mov     [rbp+30h+var_60], rax
0x1800355fa  xor     r9d, r9d; RelatedActivityId
0x1800355fd  movzx   eax, cs:word_1801CBE33
0x180035604  xor     r8d, r8d; ActivityId
0x180035607  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18003560b  mov     rax, cs:off_1801E7010
0x180035612  mov     [rbp+30h+var_80.Ptr], rax
0x180035616  mov     [rbp+30h+var_58], 1Bh
0x18003561e  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x180035626  movzx   eax, word ptr [rax]
0x180035629  mov     [rbp+30h+var_80.Size], eax
0x18003562c  lea     rax, byte_1801CBE3D
0x180035633  mov     [rbp+30h+var_70], rax
0x180035637  lea     rax, _TraceLoggingMetadataEnd
0x18003563e  sub     eax, ecx
0x180035640  mov     dword ptr [rbp+30h+var_80.0Ch], 2
0x180035647  mov     [rbp+30h+var_68], 1Fh
0x18003564e  mov     [rbp+30h+var_64], 1
0x180035655  mov     [rsp+130h+dwMilliseconds], eax
0x180035659  mov     eax, [rsp+130h+dwMilliseconds]
0x18003565d  mov     rcx, cs:RegHandle; RegHandle
0x180035664  lea     rax, [rbp+30h+var_80]
0x180035668  mov     [rsp+130h+UserData], rax; UserData
0x18003566d  mov     [rsp+130h+wRemoveMsg], 4; UserDataCount
0x180035675  call    cs:__imp_EventWriteTransfer
0x18003567b  mov     eax, 834500CCh
0x180035680  mov     rsi, [rsp+130h+arg_10]
0x180035688  mov     r15, [rsp+130h+var_30]
0x180035690  mov     rcx, [rbp+30h+var_40]
0x180035694  xor     rcx, rsp; StackCookie
0x180035697  call    __security_check_cookie
0x18003569c  add     rsp, 108h
0x1800356a3  pop     r14
0x1800356a5  pop     r13
0x1800356a7  pop     r12
0x1800356a9  pop     rdi
0x1800356aa  pop     rbx
0x1800356ab  pop     rbp
0x1800356ac  retn
0x1800356ad  mov     eax, cs:CallbackContext
0x1800356b3  cmp     eax, 2
0x1800356b6  jbe     short loc_180035731
0x1800356b8  lea     rax, aTimeoutProcess; "Timeout processing window messages"
0x1800356bf  mov     [rsp+130h+var_DC], 0F2h
0x1800356c7  mov     qword ptr [rsp+130h+EventDescriptor.Id], rax
0x1800356cc  lea     rsi, aPalSystemCondw_0; "PAL_System_CondWait"
0x1800356d3  lea     rax, [rsp+130h+var_D8]
0x1800356d8  mov     [rsp+130h+var_D8], rsi
0x1800356dd  mov     [rsp+130h+var_F0], rax
0x1800356e2  lea     rbx, aOnecoreTermsrv_43; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800356e9  lea     rax, [rsp+130h+var_DC]
0x1800356ee  mov     [rsp+130h+var_D0], rbx
0x1800356f3  mov     [rsp+130h+var_F8], rax
0x1800356f8  lea     rdx, byte_1801CBFFB
0x1800356ff  lea     rax, [rsp+130h+var_D0]
0x180035704  mov     [rsp+130h+dwMilliseconds], 80004005h
0x18003570c  mov     [rsp+130h+var_100], rax
0x180035711  lea     rax, [rsp+130h+dwMilliseconds]
0x180035716  mov     [rsp+130h+UserData], rax
0x18003571b  lea     rax, [rsp+130h+EventDescriptor]
0x180035720  mov     qword ptr [rsp+130h+wRemoveMsg], rax
0x180035725  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003572a  mov     ecx, 102h
0x18003572f  jmp     short loc_180035754
0x180035731  lea     rsi, aPalSystemCondw_0; "PAL_System_CondWait"
0x180035738  mov     ecx, 102h
0x18003573d  lea     rbx, aOnecoreTermsrv_43; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180035744  jmp     short loc_180035754
0x180035746  lea     rsi, aPalSystemCondw_0; "PAL_System_CondWait"
0x18003574d  lea     rbx, aOnecoreTermsrv_43; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180035754  lea     eax, [rdi-1]
0x180035757  cmp     ecx, eax
0x180035759  ja      short loc_18003576C
0x18003575b  test    r15d, r15d
0x18003575e  jnz     short loc_180035763
0x180035760  mov     [r14], ecx
0x180035763  xor     ecx, ecx
0x180035765  mov     eax, ecx
0x180035767  jmp     loc_180035680
0x18003576c  cmp     ecx, 80h
0x180035772  jb      short loc_180035790
0x180035774  lea     eax, [rdi+7Fh]
0x180035777  cmp     ecx, eax
0x180035779  ja      short loc_180035790
0x18003577b  test    r15d, r15d
0x18003577e  jnz     short loc_180035786
0x180035780  lea     eax, [rcx-80h]
0x180035783  mov     [r14], eax
0x180035786  mov     eax, 834500CAh
0x18003578b  jmp     loc_180035680
0x180035790  cmp     ecx, 102h
0x180035796  jnz     short loc_1800357A7
0x180035798  xor     ecx, ecx
0x18003579a  mov     eax, 834500CBh
0x18003579f  mov     [r14], ecx
0x1800357a2  jmp     loc_180035680
0x1800357a7  mov     eax, cs:CallbackContext
0x1800357ad  cmp     eax, 2
0x1800357b0  jbe     short loc_180035816
0x1800357b2  lea     rcx, [rsp+130h+EventDescriptor]
0x1800357b7  mov     qword ptr [rsp+130h+EventDescriptor.Id], rsi
0x1800357bc  mov     [rsp+130h+var_F0], rcx
0x1800357c1  lea     rax, aWaitFailedWith; "Wait Failed with unknown error"
0x1800357c8  lea     rcx, [rsp+130h+var_DC]
0x1800357cd  mov     [rsp+130h+var_DC], 127h
0x1800357d5  mov     [rsp+130h+var_F8], rcx
0x1800357da  lea     rdx, byte_1801CC085
0x1800357e1  lea     rcx, [rsp+130h+var_D0]
0x1800357e6  mov     [rsp+130h+var_D0], rbx
0x1800357eb  mov     [rsp+130h+var_100], rcx
0x1800357f0  lea     rcx, [rsp+130h+dwMilliseconds]
0x1800357f5  mov     [rsp+130h+UserData], rcx
0x1800357fa  lea     rcx, [rsp+130h+var_D8]
0x1800357ff  mov     qword ptr [rsp+130h+wRemoveMsg], rcx
0x180035804  mov     [rsp+130h+dwMilliseconds], 80004005h
0x18003580c  mov     [rsp+130h+var_D8], rax
0x180035811  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180035816  mov     eax, 80004005h
0x18003581b  jmp     loc_180035680
0x180035820  mov     eax, 80070057h
0x180035825  jmp     loc_180035690
```
