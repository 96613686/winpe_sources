# WsbkGetMessageThread

- ea: `0x18004a170`
- end: `0x18004a6cb`
- name: `WsbkGetMessageThread`
- size: `1371`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180009e04`
- `0x18004a170`
- `0x18004d980`
- `0x1800502c2`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a1c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a1c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a25b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a67e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a25b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a67e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a275`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a275`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a68c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a68c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a55f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a5b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a55f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a5b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a602`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a69b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a69b`
- `WDSCORE!CurrentIP` at `0x18004a1f3`
- `WDSCORE!CurrentIP` at `0x18004a28b`
- `WDSCORE!CurrentIP` at `0x18004a3c2`
- `WDSCORE!CurrentIP` at `0x18004a46d`
- `WDSCORE!CurrentIP` at `0x18004a511`
- `WDSCORE!CurrentIP` at `0x18004a567`
- `WDSCORE!CurrentIP` at `0x18004a5ba`
- `WDSCORE!CurrentIP` at `0x18004a60a`
- `WDSCORE!CurrentIP` at `0x18004a1f3`
- `WDSCORE!CurrentIP` at `0x18004a28b`
- `WDSCORE!CurrentIP` at `0x18004a3c2`
- `WDSCORE!CurrentIP` at `0x18004a46d`
- `WDSCORE!CurrentIP` at `0x18004a511`
- `WDSCORE!CurrentIP` at `0x18004a567`
- `WDSCORE!CurrentIP` at `0x18004a5ba`
- `WDSCORE!CurrentIP` at `0x18004a60a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004a417`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004a663`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004a417`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004a663`
- `FLTLIB!FilterGetMessage` at `0x18004a37d`
- `FLTLIB!FilterGetMessage` at `0x18004a37d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18004a39e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18004a39e`

## string_xrefs

- `0x18004a1fc`: `WsbkGetMessageThread: Failed CreateEventW, hr = 0x%08x`
- `0x18004a214`: `WsbkGetMessageThread`
- `0x18004a2af`: `WsbkGetMessageThread`
- `0x18004a32f`: `WsbkGetMessageThread`
- `0x18004a614`: `WsbkGetMessageThread: Failed FilterGetMessage, hr = 0x%08x`
- `0x18004a297`: `WsbkGetMessageThread: Failed to allocate client request buffer; hr = 0x%08x`
- `0x18004a56d`: `WsbkGetMessageThread: Received message with invalid signature/version.`
- `0x18004a5c0`: `Thread exit event signaled`
- `0x18004a3c8`: `WsbkGetMessageThread: Cancel event signaled; ignoring`
- `0x18004a477`: `WsbkGetMessageThread: Received invalid message type: %d`
- `0x18004a51a`: `WsbkGetMessageThread: Failed WaitForMultipleObjects, hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WsbkGetMessageThread(HANDLE **Parameter)
{
  struct _FILTER_MESSAGE_HEADER *v2; // rbx
  signed int LastError; // eax
  unsigned int v4; // r14d
  DWORD v5; // esi
  __int64 v6; // rdi
  struct tagLOG_PARTIAL_MSG *v7; // rax
  HANDLE ProcessHeap; // rax
  int v9; // edi
  struct _FILTER_MESSAGE_HEADER *v10; // rax
  DWORD v11; // esi
  __int64 v12; // rdi
  struct tagLOG_PARTIAL_MSG *v13; // rax
  DWORD v14; // esi
  void *v15; // rcx
  HANDLE *v16; // rax
  HANDLE v17; // rax
  DWORD v18; // r8d
  struct _FILTER_MESSAGE_HEADER *p_MessageBuffer; // rdx
  HANDLE v20; // rcx
  DWORD v21; // eax
  DWORD v22; // eax
  DWORD v23; // esi
  __int64 v24; // rdi
  struct tagLOG_PARTIAL_MSG *v25; // rax
  DWORD v26; // esi
  __int64 v27; // rdi
  struct tagLOG_PARTIAL_MSG *v28; // rax
  HANDLE *v29; // rax
  __int64 MessageId_high; // rcx
  signed int v31; // eax
  unsigned int v32; // r14d
  DWORD v33; // esi
  __int64 v34; // rdi
  struct tagLOG_PARTIAL_MSG *v35; // rax
  DWORD v36; // esi
  __int64 v37; // rdi
  struct tagLOG_PARTIAL_MSG *v38; // rax
  DWORD v39; // esi
  __int64 v40; // rdi
  struct tagLOG_PARTIAL_MSG *v41; // rax
  DWORD v42; // esi
  __int64 v43; // rdi
  struct tagLOG_PARTIAL_MSG *v44; // rax
  HANDLE v45; // rax
  int v47; // [rsp+60h] [rbp-39h]
  HRESULT Message; // [rsp+64h] [rbp-35h]
  int v49; // [rsp+68h] [rbp-31h]
  struct _OVERLAPPED Overlapped; // [rsp+70h] [rbp-29h] BYREF
  _FILTER_MESSAGE_HEADER MessageBuffer; // [rsp+90h] [rbp-9h] BYREF
  __int64 v52; // [rsp+A0h] [rbp+7h]
  HANDLE Handles[2]; // [rsp+A8h] [rbp+Fh] BYREF
  HANDLE v54; // [rsp+B8h] [rbp+1Fh]

  v54 = 0;
  v2 = 0;
  memset(&Overlapped, 0, 24);
  *(_OWORD *)Handles = 0;
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( !Overlapped.hEvent )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(0x2000000, "WsbkGetMessageThread: Failed CreateEventW, hr = 0x%08x", v4);
    WdsSetupLogMessageW(
      v7,
      0,
      L"D",
      0,
      1402,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkGetMessageThread",
      v6,
      v5,
      0,
      0);
    goto LABEL_38;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl'::`2'::impl) )
  {
    ProcessHeap = GetProcessHeap();
    v9 = 131100;
    v49 = 131100;
    v10 = (struct _FILTER_MESSAGE_HEADER *)HeapAlloc(ProcessHeap, 8u, 0x2001Cu);
    v2 = v10;
    if ( !v10 )
    {
      v11 = GetLastError();
      v12 = CurrentIP();
      v13 = ConstructPartialMsgW(
              0x2000000,
              "WsbkGetMessageThread: Failed to allocate client request buffer; hr = 0x%08x",
              -2147024882);
      WdsSetupLogMessageW(
        v13,
        0,
        L"D",
        0,
        1413,
        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
        L"WsbkGetMessageThread",
        v12,
        v11,
        0,
        0);
      goto LABEL_38;
    }
    memset_0(v10, 0, 0x2001Cu);
  }
  else
  {
    v9 = 0;
    v49 = 0;
  }
  v14 = 2;
  v47 = 2;
  v15 = *Parameter[1];
  Handles[1] = Overlapped.hEvent;
  v16 = Parameter[2];
  Handles[0] = v15;
  if ( v16 )
  {
    v17 = *v16;
    if ( v17 )
    {
      v14 = 3;
      v54 = v17;
      v47 = 3;
    }
  }
  while ( 1 )
  {
    while ( 1 )
    {
      MessageBuffer = 0;
      v52 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl'::`2'::impl) )
      {
        v18 = v9;
        p_MessageBuffer = v2;
        v20 = **Parameter;
      }
      else
      {
        v20 = hObject;
        p_MessageBuffer = &MessageBuffer;
        v18 = 24;
      }
      Message = FilterGetMessage(v20, p_MessageBuffer, v18, &Overlapped);
      if ( Message != -2147023899 )
      {
        v42 = GetLastError();
        v43 = CurrentIP();
        v44 = ConstructPartialMsgW(0x2000000, "WsbkGetMessageThread: Failed FilterGetMessage, hr = 0x%08x", Message);
        WdsSetupLogMessageW(
          v44,
          0,
          L"D",
          0,
          1448,
          L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
          L"WsbkGetMessageThread",
          v43,
          v42,
          0,
          0);
        goto LABEL_38;
      }
      v21 = WaitForMultipleObjects(v14, Handles, 0, 0xFFFFFFFF);
      if ( !v21 )
      {
        v39 = GetLastError();
        v40 = CurrentIP();
        v41 = ConstructPartialMsgW(0x4000000, "Thread exit event signaled");
        WdsSetupLogMessageW(
          v41,
          0,
          L"D",
          0,
          1460,
          L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
          L"WsbkGetMessageThread",
          v40,
          v39,
          0,
          0);
        goto LABEL_38;
      }
      v22 = v21 - 1;
      if ( v22 )
        break;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl'::`2'::impl) )
      {
        if ( v2[1].ReplyLength != 1262637911 || *(&v2[1].ReplyLength + 1) != 1 )
        {
          v36 = GetLastError();
          v37 = CurrentIP();
          v38 = ConstructPartialMsgW(
                  0x2000000,
                  "WsbkGetMessageThread: Received message with invalid signature/version.");
          WdsSetupLogMessageW(
            v38,
            0,
            L"D",
            0,
            1470,
            L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
            L"WsbkGetMessageThread",
            v37,
            v36,
            0,
            0);
          goto LABEL_38;
        }
        if ( LODWORD(v2[1].MessageId) == 2 )
        {
          v29 = Parameter[3];
          if ( v29 )
          {
            MessageId_high = HIDWORD(v2[1].MessageId);
            goto LABEL_31;
          }
        }
        else if ( LODWORD(v2[1].MessageId) != 3 )
        {
          v26 = GetLastError();
          v27 = CurrentIP();
          v28 = ConstructPartialMsgW(
                  0x2000000,
                  "WsbkGetMessageThread: Received invalid message type: %d",
                  LODWORD(v2[1].MessageId));
          WdsSetupLogMessageW(
            v28,
            0,
            L"D",
            0,
            1488,
            L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
            L"WsbkGetMessageThread",
            v27,
            v26,
            0,
            0);
          goto LABEL_38;
        }
      }
      else
      {
        v29 = Parameter[3];
        if ( v29 )
        {
          MessageId_high = (unsigned int)v52;
LABEL_31:
          ((void (__fastcall *)(__int64, __int64, HANDLE *))v29)(MessageId_high, 10000, Parameter[4]);
        }
      }
    }
    if ( v22 != 1 )
      break;
    v23 = GetLastError();
    v24 = CurrentIP();
    v25 = ConstructPartialMsgW(50331648, "WsbkGetMessageThread: Cancel event signaled; ignoring");
    WdsSetupLogMessageW(
      v25,
      0,
      L"D",
      0,
      1501,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkGetMessageThread",
      v24,
      v23,
      0,
      0);
    v9 = v49;
    v14 = v47;
  }
  v31 = GetLastError();
  v32 = v31;
  if ( v31 > 0 )
    v32 = (unsigned __int16)v31 | 0x80070000;
  v33 = GetLastError();
  v34 = CurrentIP();
  v35 = ConstructPartialMsgW(0x2000000, "WsbkGetMessageThread: Failed WaitForMultipleObjects, hr = 0x%08x", v32);
  WdsSetupLogMessageW(
    v35,
    0,
    L"D",
    0,
    1505,
    L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
    L"WsbkGetMessageThread",
    v34,
    v33,
    0,
    0);
LABEL_38:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl'::`2'::impl)
    && v2 )
  {
    v45 = GetProcessHeap();
    HeapFree(v45, 0, v2);
  }
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  return 0;
}

```

## disassembly

```asm
0x18004a170  mov     [rsp-8+arg_8], rbx
0x18004a175  mov     [rsp-8+arg_10], rsi
0x18004a17a  push    rbp
0x18004a17b  push    rdi
0x18004a17c  push    r12
0x18004a17e  push    r13
0x18004a180  push    r14
0x18004a182  lea     rbp, [rsp-37h]
0x18004a187  sub     rsp, 0D0h
0x18004a18e  mov     rax, cs:__security_cookie
0x18004a195  xor     rax, rsp
0x18004a198  mov     [rbp+57h+var_30], rax
0x18004a19c  xor     eax, eax
0x18004a19e  xorps   xmm0, xmm0
0x18004a1a1  mov     r14, rcx
0x18004a1a4  mov     [rbp+57h+var_38], rax
0x18004a1a8  xorps   xmm1, xmm1
0x18004a1ab  xor     r9d, r9d; lpName
0x18004a1ae  xor     r8d, r8d; bInitialState
0x18004a1b1  xor     ecx, ecx; lpEventAttributes
0x18004a1b3  lea     edx, [rax+1]; bManualReset
0x18004a1b6  xor     ebx, ebx
0x18004a1b8  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18004a1bc  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18004a1c0  movups  xmmword ptr [rbp+57h+Handles], xmm1
0x18004a1c4  call    cs:__imp_CreateEventW
0x18004a1ca  mov     [rbp+57h+Overlapped.hEvent], rax
0x18004a1ce  test    rax, rax
0x18004a1d1  jnz     short loc_18004A247
0x18004a1d3  call    cs:__imp_GetLastError
0x18004a1d9  mov     r14d, eax
0x18004a1dc  test    eax, eax
0x18004a1de  jle     short loc_18004A1EB
0x18004a1e0  movzx   r14d, ax
0x18004a1e4  or      r14d, 80070000h
0x18004a1eb  call    cs:__imp_GetLastError
0x18004a1f1  mov     esi, eax
0x18004a1f3  call    cs:__imp_CurrentIP
0x18004a1f9  mov     r8d, r14d
0x18004a1fc  lea     rdx, aWsbkgetmessage_6; "WsbkGetMessageThread: Failed CreateEven"...
0x18004a203  mov     ecx, 2000000h; unsigned int
0x18004a208  mov     rdi, rax
0x18004a20b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a210  mov     [rsp+0F0h+var_A0], ebx
0x18004a214  lea     r12, aWsbkgetmessage_4; "WsbkGetMessageThread"
0x18004a21b  mov     [rsp+0F0h+var_A8], rbx
0x18004a220  lea     r13, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004a227  mov     [rsp+0F0h+var_B0], esi
0x18004a22b  mov     [rsp+0F0h+var_B8], rdi
0x18004a230  mov     [rsp+0F0h+var_C0], r12
0x18004a235  mov     [rsp+0F0h+var_C8], r13
0x18004a23a  mov     [rsp+0F0h+var_D0], 57Ah
0x18004a242  jmp     loc_18004A654
0x18004a247  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl(void)'::`2'::impl
0x18004a24e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(void)
0x18004a253  test    al, al
0x18004a255  jz      loc_18004A2F1
0x18004a25b  call    cs:__imp_GetProcessHeap
0x18004a261  mov     edi, 2001Ch
0x18004a266  mov     edx, 8; dwFlags
0x18004a26b  mov     rcx, rax; hHeap
0x18004a26e  mov     [rbp+57h+var_88], rdi
0x18004a272  mov     r8d, edi; dwBytes
0x18004a275  call    cs:__imp_HeapAlloc
0x18004a27b  mov     rbx, rax
0x18004a27e  test    rax, rax
0x18004a281  jnz     short loc_18004A2E2
0x18004a283  call    cs:__imp_GetLastError
0x18004a289  mov     esi, eax
0x18004a28b  call    cs:__imp_CurrentIP
0x18004a291  mov     r8d, 8007000Eh
0x18004a297  lea     rdx, aWsbkgetmessage_2; "WsbkGetMessageThread: Failed to allocat"...
0x18004a29e  mov     ecx, 2000000h; unsigned int
0x18004a2a3  mov     rdi, rax
0x18004a2a6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a2ab  mov     [rsp+0F0h+var_A0], ebx
0x18004a2af  lea     r12, aWsbkgetmessage_4; "WsbkGetMessageThread"
0x18004a2b6  mov     [rsp+0F0h+var_A8], rbx
0x18004a2bb  lea     r13, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004a2c2  mov     [rsp+0F0h+var_B0], esi
0x18004a2c6  mov     [rsp+0F0h+var_B8], rdi
0x18004a2cb  mov     [rsp+0F0h+var_C0], r12
0x18004a2d0  mov     [rsp+0F0h+var_C8], r13
0x18004a2d5  mov     [rsp+0F0h+var_D0], 585h
0x18004a2dd  jmp     loc_18004A654
0x18004a2e2  mov     r8, rdi; Size
0x18004a2e5  xor     edx, edx; Val
0x18004a2e7  mov     rcx, rax; void *
0x18004a2ea  call    memset_0
0x18004a2ef  jmp     short loc_18004A2F7
0x18004a2f1  xor     edi, edi
0x18004a2f3  mov     [rbp+57h+var_88], rdi
0x18004a2f7  mov     rax, [r14+8]
0x18004a2fb  mov     esi, 2
0x18004a300  mov     [rbp+57h+var_90], esi
0x18004a303  mov     rcx, [rax]
0x18004a306  mov     rax, [rbp+57h+Overlapped.hEvent]
0x18004a30a  mov     [rbp+57h+Handles+8], rax
0x18004a30e  mov     rax, [r14+10h]
0x18004a312  mov     [rbp+57h+Handles], rcx
0x18004a316  test    rax, rax
0x18004a319  jz      short loc_18004A32F
0x18004a31b  mov     rax, [rax]
0x18004a31e  test    rax, rax
0x18004a321  jz      short loc_18004A32F
0x18004a323  mov     esi, 3
0x18004a328  mov     [rbp+57h+var_38], rax
0x18004a32c  mov     [rbp+57h+var_90], esi
0x18004a32f  lea     r12, aWsbkgetmessage_4; "WsbkGetMessageThread"
0x18004a336  lea     r13, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004a33d  xorps   xmm0, xmm0
0x18004a340  xor     eax, eax
0x18004a342  movups  xmmword ptr [rbp+57h+MessageBuffer.ReplyLength], xmm0
0x18004a346  mov     [rbp+57h+var_50], rax
0x18004a34a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl(void)'::`2'::impl
0x18004a351  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(void)
0x18004a356  lea     r9, [rbp+57h+Overlapped]; lpOverlapped
0x18004a35a  test    al, al
0x18004a35c  jz      short loc_18004A36C
0x18004a35e  mov     rcx, [r14]
0x18004a361  mov     r8d, edi
0x18004a364  mov     rdx, rbx
0x18004a367  mov     rcx, [rcx]
0x18004a36a  jmp     short loc_18004A37D
0x18004a36c  mov     rcx, cs:hObject; hPort
0x18004a373  lea     rdx, [rbp+57h+MessageBuffer]; lpMessageBuffer
0x18004a377  mov     r8d, 18h; dwMessageBufferSize
0x18004a37d  call    cs:__imp_FilterGetMessage
0x18004a383  mov     [rbp+57h+var_8C], eax
0x18004a386  cmp     eax, 800703E5h
0x18004a38b  jnz     loc_18004A602
0x18004a391  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004a395  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18004a399  xor     r8d, r8d; bWaitAll
0x18004a39c  mov     ecx, esi; nCount
0x18004a39e  call    cs:__imp_WaitForMultipleObjects
0x18004a3a4  test    eax, eax
0x18004a3a6  jz      loc_18004A5B2
0x18004a3ac  sub     eax, 1
0x18004a3af  jz      short loc_18004A429
0x18004a3b1  cmp     eax, 1
0x18004a3b4  jnz     loc_18004A4F1
0x18004a3ba  call    cs:__imp_GetLastError
0x18004a3c0  mov     esi, eax
0x18004a3c2  call    cs:__imp_CurrentIP
0x18004a3c8  lea     rdx, aWsbkgetmessage_0; "WsbkGetMessageThread: Cancel event sign"...
0x18004a3cf  mov     ecx, 3000000h; unsigned int
0x18004a3d4  mov     rdi, rax
0x18004a3d7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a3dc  mov     [rsp+0F0h+var_A0], 0
0x18004a3e4  lea     r8, aD; "D"
0x18004a3eb  mov     [rsp+0F0h+var_A8], 0
0x18004a3f4  xor     r9d, r9d
0x18004a3f7  mov     [rsp+0F0h+var_B0], esi
0x18004a3fb  xor     edx, edx
0x18004a3fd  mov     [rsp+0F0h+var_B8], rdi
0x18004a402  mov     rcx, rax
0x18004a405  mov     [rsp+0F0h+var_C0], r12
0x18004a40a  mov     [rsp+0F0h+var_C8], r13
0x18004a40f  mov     [rsp+0F0h+var_D0], 5DDh
0x18004a417  call    cs:__imp_WdsSetupLogMessageW
0x18004a41d  mov     rdi, [rbp+57h+var_88]
0x18004a421  mov     esi, [rbp+57h+var_90]
0x18004a424  jmp     loc_18004A33D
0x18004a429  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl(void)'::`2'::impl
0x18004a430  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(void)
0x18004a435  test    al, al
0x18004a437  jz      loc_18004A4CE
0x18004a43d  cmp     dword ptr [rbx+10h], 4B425357h
0x18004a444  jnz     loc_18004A55F
0x18004a44a  cmp     dword ptr [rbx+14h], 1
0x18004a44e  jnz     loc_18004A55F
0x18004a454  mov     ecx, [rbx+18h]
0x18004a457  sub     ecx, 2
0x18004a45a  jz      short loc_18004A4BC
0x18004a45c  cmp     ecx, 1
0x18004a45f  jz      loc_18004A33D
0x18004a465  call    cs:__imp_GetLastError
0x18004a46b  mov     esi, eax
0x18004a46d  call    cs:__imp_CurrentIP
0x18004a473  mov     r8d, [rbx+18h]
0x18004a477  lea     rdx, aWsbkgetmessage_3; "WsbkGetMessageThread: Received invalid "...
0x18004a47e  mov     ecx, 2000000h; unsigned int
0x18004a483  mov     rdi, rax
0x18004a486  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a48b  mov     [rsp+0F0h+var_A0], 0
0x18004a493  mov     [rsp+0F0h+var_A8], 0
0x18004a49c  mov     [rsp+0F0h+var_B0], esi
0x18004a4a0  mov     [rsp+0F0h+var_B8], rdi
0x18004a4a5  mov     [rsp+0F0h+var_C0], r12
0x18004a4aa  mov     [rsp+0F0h+var_C8], r13
0x18004a4af  mov     [rsp+0F0h+var_D0], 5D0h
0x18004a4b7  jmp     loc_18004A654
0x18004a4bc  mov     rax, [r14+18h]
0x18004a4c0  test    rax, rax
0x18004a4c3  jz      loc_18004A33D
0x18004a4c9  mov     ecx, [rbx+1Ch]
0x18004a4cc  jmp     short loc_18004A4DE
0x18004a4ce  mov     rax, [r14+18h]
0x18004a4d2  test    rax, rax
0x18004a4d5  jz      loc_18004A33D
0x18004a4db  mov     ecx, dword ptr [rbp+57h+var_50]
0x18004a4de  mov     r8, [r14+20h]
0x18004a4e2  mov     edx, 2710h
0x18004a4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4ec  jmp     loc_18004A33D
0x18004a4f1  call    cs:__imp_GetLastError
0x18004a4f7  mov     r14d, eax
0x18004a4fa  test    eax, eax
0x18004a4fc  jle     short loc_18004A509
0x18004a4fe  movzx   r14d, ax
0x18004a502  or      r14d, 80070000h
0x18004a509  call    cs:__imp_GetLastError
0x18004a50f  mov     esi, eax
0x18004a511  call    cs:__imp_CurrentIP
0x18004a517  mov     r8d, r14d
0x18004a51a  lea     rdx, aWsbkgetmessage_5; "WsbkGetMessageThread: Failed WaitForMul"...
0x18004a521  mov     ecx, 2000000h; unsigned int
0x18004a526  mov     rdi, rax
0x18004a529  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a52e  mov     [rsp+0F0h+var_A0], 0
0x18004a536  mov     [rsp+0F0h+var_A8], 0
0x18004a53f  mov     [rsp+0F0h+var_B0], esi
0x18004a543  mov     [rsp+0F0h+var_B8], rdi
0x18004a548  mov     [rsp+0F0h+var_C0], r12
0x18004a54d  mov     [rsp+0F0h+var_C8], r13
0x18004a552  mov     [rsp+0F0h+var_D0], 5E1h
0x18004a55a  jmp     loc_18004A654
0x18004a55f  call    cs:__imp_GetLastError
0x18004a565  mov     esi, eax
0x18004a567  call    cs:__imp_CurrentIP
0x18004a56d  lea     rdx, aWsbkgetmessage_1; "WsbkGetMessageThread: Received message "...
0x18004a574  mov     ecx, 2000000h; unsigned int
0x18004a579  mov     rdi, rax
0x18004a57c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a581  mov     [rsp+0F0h+var_A0], 0
0x18004a589  mov     [rsp+0F0h+var_A8], 0
0x18004a592  mov     [rsp+0F0h+var_B0], esi
0x18004a596  mov     [rsp+0F0h+var_B8], rdi
0x18004a59b  mov     [rsp+0F0h+var_C0], r12
0x18004a5a0  mov     [rsp+0F0h+var_C8], r13
0x18004a5a5  mov     [rsp+0F0h+var_D0], 5BEh
0x18004a5ad  jmp     loc_18004A654
0x18004a5b2  call    cs:__imp_GetLastError
0x18004a5b8  mov     esi, eax
0x18004a5ba  call    cs:__imp_CurrentIP
0x18004a5c0  lea     rdx, aThreadExitEven; "Thread exit event signaled"
0x18004a5c7  mov     ecx, 4000000h; unsigned int
0x18004a5cc  mov     rdi, rax
0x18004a5cf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a5d4  mov     [rsp+0F0h+var_A0], 0
0x18004a5dc  mov     [rsp+0F0h+var_A8], 0
0x18004a5e5  mov     [rsp+0F0h+var_B0], esi
0x18004a5e9  mov     [rsp+0F0h+var_B8], rdi
0x18004a5ee  mov     [rsp+0F0h+var_C0], r12
0x18004a5f3  mov     [rsp+0F0h+var_C8], r13
0x18004a5f8  mov     [rsp+0F0h+var_D0], 5B4h
0x18004a600  jmp     short loc_18004A654
0x18004a602  call    cs:__imp_GetLastError
0x18004a608  mov     esi, eax
0x18004a60a  call    cs:__imp_CurrentIP
0x18004a610  mov     r8d, [rbp+57h+var_8C]
0x18004a614  lea     rdx, aWsbkgetmessage; "WsbkGetMessageThread: Failed FilterGetM"...
0x18004a61b  mov     ecx, 2000000h; unsigned int
0x18004a620  mov     rdi, rax
0x18004a623  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a628  mov     [rsp+0F0h+var_A0], 0
0x18004a630  mov     [rsp+0F0h+var_A8], 0
0x18004a639  mov     [rsp+0F0h+var_B0], esi
0x18004a63d  mov     [rsp+0F0h+var_B8], rdi
0x18004a642  mov     [rsp+0F0h+var_C0], r12
0x18004a647  mov     [rsp+0F0h+var_C8], r13
0x18004a64c  mov     [rsp+0F0h+var_D0], 5A8h
0x18004a654  xor     r9d, r9d
0x18004a657  lea     r8, aD; "D"
0x18004a65e  xor     edx, edx
0x18004a660  mov     rcx, rax
0x18004a663  call    cs:__imp_WdsSetupLogMessageW
0x18004a669  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl(void)'::`2'::impl
0x18004a670  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(void)
0x18004a675  test    al, al
0x18004a677  jz      short loc_18004A692
0x18004a679  test    rbx, rbx
0x18004a67c  jz      short loc_18004A692
0x18004a67e  call    cs:__imp_GetProcessHeap
0x18004a684  mov     r8, rbx; lpMem
0x18004a687  xor     edx, edx; dwFlags
0x18004a689  mov     rcx, rax; hHeap
0x18004a68c  call    cs:__imp_HeapFree
0x18004a692  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x18004a696  test    rcx, rcx
0x18004a699  jz      short loc_18004A6A1
0x18004a69b  call    cs:__imp_CloseHandle
0x18004a6a1  xor     eax, eax
0x18004a6a3  mov     rcx, [rbp+57h+var_30]
0x18004a6a7  xor     rcx, rsp; StackCookie
0x18004a6aa  call    __security_check_cookie
0x18004a6af  lea     r11, [rsp+0F0h+var_20]
0x18004a6b7  mov     rbx, [r11+38h]
0x18004a6bb  mov     rsi, [r11+40h]
  ... truncated ...
```
