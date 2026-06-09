# CEventNotificationService::SwitchToMaintenanceMode(void)

- ea: `0x1400267d0`
- end: `0x140026bb4`
- name: `?SwitchToMaintenanceMode@CEventNotificationService@@IEAAJXZ`
- size: `996`
- prototype: `__int64 __fastcall(CEventNotificationService *__hidden this)`
- caller_count: `26`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x140017530`
- `0x140018304`
- `0x140019af0`
- `0x140019e40`
- `0x14001af00`
- `0x14001b330`
- `0x14001b6e0`
- `0x14001ba30`
- `0x14001bd90`
- `0x14001c110`
- `0x14001c520`
- `0x14001c870`
- `0x14001cbf0`
- `0x14001cf80`
- `0x14001d330`
- `0x14001ddc0`
- `0x14001e6c8`
- `0x140021a50`
- `0x140022d70`
- `0x140023ad0`
- `0x140023dd0`
- `0x140024230`
- `0x140024530`
- `0x140024830`
- `0x140024ed0`
- `0x140025050`

## callees

- `0x140015e1c`
- `0x140016268`
- `0x1400229c0`
- `0x1400267d0`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x14006eb38`
- `0x14007e010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x140026937`
- `KERNEL32!CreateThread` at `0x140026937`
- `KERNEL32!ResetEvent` at `0x140026912`
- `KERNEL32!ResetEvent` at `0x140026912`
- `KERNEL32!WaitForMultipleObjects` at `0x140026a24`
- `KERNEL32!WaitForMultipleObjects` at `0x140026a24`
- `KERNEL32!GetLastError` at `0x14002694d`
- `KERNEL32!GetLastError` at `0x140026a40`
- `KERNEL32!GetLastError` at `0x14002694d`
- `KERNEL32!GetLastError` at `0x140026a40`
- `KERNEL32!IsDebuggerPresent` at `0x1400268bf`
- `KERNEL32!IsDebuggerPresent` at `0x14002699a`
- `KERNEL32!IsDebuggerPresent` at `0x140026aad`
- `KERNEL32!IsDebuggerPresent` at `0x140026b24`
- `KERNEL32!IsDebuggerPresent` at `0x1400268bf`
- `KERNEL32!IsDebuggerPresent` at `0x14002699a`
- `KERNEL32!IsDebuggerPresent` at `0x140026aad`
- `KERNEL32!IsDebuggerPresent` at `0x140026b24`

## string_xrefs

- `0x140026802`: `CEventNotificationService::SwitchToMaintenanceMode\n`
- `0x14002681d`: `CEventNotificationService::SwitchToMaintenanceMode - m_modeCore = %s\n`
- `0x14002683a`: `Already in maintenance mode so nothing to do; exiting.`
- `0x140026846`: `CEventNotificationService::SwitchToMaintenanceMode`
- `0x14002688a`: `CEventNotificationService::SwitchToMaintenanceMode`
- `0x1400268a6`: `m_hStationThread == NULL`
- `0x140026962`: `m_hStationThread != 0`
- `0x140026a02`: `CEventNotificationService::SwitchToMaintenanceMode - waiting for hStationThread to load station manager\n`
- `0x140026a2c`: `CEventNotificationService::SwitchToMaintenanceMode - WaitForMultipleObjects handle %li was signaled\n`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::SwitchToMaintenanceMode(
        CEventNotificationService *this,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  __int64 v5; // rax
  signed int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  const unsigned __int16 *v9; // r9
  HANDLE Thread; // rax
  HANDLE v11; // rcx
  signed int LastError; // eax
  const unsigned __int16 *v13; // r13
  unsigned int v14; // r15d
  __int64 v15; // rax
  __int64 v16; // r15
  signed int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-48h]
  __int128 Handles; // [rsp+40h] [rbp-38h] BYREF
  struct _RTL_CRITICAL_SECTION **v21; // [rsp+80h] [rbp+8h] BYREF

  Handles = 0;
  CAutoCriticalSection::CAutoCriticalSection(
    (CAutoCriticalSection *)&v21,
    (CEventNotificationService *)((char *)this + 464),
    a3,
    a4);
  DEBUGMSG(L"CEventNotificationService::SwitchToMaintenanceMode\n");
  v5 = Utils::WmsModeToString(*((unsigned int *)this + 114));
  DEBUGMSG(L"CEventNotificationService::SwitchToMaintenanceMode - m_modeCore = %s\n", v5);
  if ( *((_DWORD *)this + 114) == 2 )
  {
    v6 = 0;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      422,
      L"CEventNotificationService::SwitchToMaintenanceMode",
      L"Already in maintenance mode so nothing to do; exiting.");
    goto LABEL_33;
  }
  v6 = CEventNotificationService::ReleaseCore(this);
  if ( v6 < 0 )
    goto LABEL_33;
  if ( *((_QWORD *)this + 13) )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x1ACu,
      L"CEventNotificationService::SwitchToMaintenanceMode",
      v9,
      L"m_hStationThread == NULL");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        428,
        L"CEventNotificationService::SwitchToMaintenanceMode",
        L"ASSERT",
        L"m_hStationThread == NULL");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        428,
        L"CEventNotificationService::SwitchToMaintenanceMode",
        L"ASSERT",
        L"m_hStationThread == NULL");
  }
  ResetEvent(*((HANDLE *)this + 14));
  Thread = CreateThread(0, 0, CEventNotificationService::s_StationThreadProc, this, 0, 0);
  *((_QWORD *)this + 13) = Thread;
  v11 = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v13 = L"m_hStationThread != 0";
    v14 = 433;
LABEL_12:
    if ( v6 >= 0 )
      v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v14,
      L"CEventNotificationService::SwitchToMaintenanceMode",
      L"CBRAEx",
      v13,
      v6);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v14,
        L"CEventNotificationService::SwitchToMaintenanceMode",
        L"CBRAEx",
        v13,
        v6);
    }
    else
    {
      LODWORD(v19) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v14,
        L"CEventNotificationService::SwitchToMaintenanceMode",
        L"CBRAEx",
        v13,
        v19);
    }
    goto LABEL_33;
  }
  v15 = *((_QWORD *)this + 14);
  *((_QWORD *)&Handles + 1) = v11;
  *(_QWORD *)&Handles = v15;
  DEBUGMSG(L"CEventNotificationService::SwitchToMaintenanceMode - waiting for hStationThread to load station manager\n");
  v16 = WaitForMultipleObjects(2u, (const HANDLE *)&Handles, 0, 0xFFFFFFFF);
  DEBUGMSG(
    L"CEventNotificationService::SwitchToMaintenanceMode - WaitForMultipleObjects handle %li was signaled\n",
    v16);
  if ( (_DWORD)v16 == -1 )
  {
    v17 = GetLastError();
    v6 = v17;
    if ( v17 > 0 )
      v6 = (unsigned __int16)v17 | 0x80070000;
    v13 = L"dwWaitResult != ((DWORD)0xFFFFFFFF)";
    v14 = 443;
    goto LABEL_12;
  }
  v6 = *((_DWORD *)this + 32);
  if ( v6 >= 0 )
  {
    if ( (_DWORD)v16 )
    {
      v6 = -2147467259;
    }
    else
    {
      if ( !*((_QWORD *)this + 65) )
      {
        LOGASSERT(
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          0x1BFu,
          L"CEventNotificationService::SwitchToMaintenanceMode",
          v9,
          L"m_pStationManager != NULL");
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            447,
            L"CEventNotificationService::SwitchToMaintenanceMode",
            L"ASSERT",
            L"m_pStationManager != NULL");
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            447,
            L"CEventNotificationService::SwitchToMaintenanceMode",
            L"ASSERT",
            L"m_pStationManager != NULL");
      }
      if ( !*((_QWORD *)this + 56) )
      {
        LOGASSERT(
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          0x1C0u,
          L"CEventNotificationService::SwitchToMaintenanceMode",
          v9,
          L"m_pCore != NULL");
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            448,
            L"CEventNotificationService::SwitchToMaintenanceMode",
            L"ASSERT",
            L"m_pCore != NULL");
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            448,
            L"CEventNotificationService::SwitchToMaintenanceMode",
            L"ASSERT",
            L"m_pCore != NULL");
      }
      v6 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this + 1) + 168LL))((char *)this + 8, 2);
    }
  }
LABEL_33:
  CAutoCriticalSection::~CAutoCriticalSection(&v21, v7, v8, v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400267d0  mov     rax, rsp
0x1400267d3  mov     [rax+10h], rbx
0x1400267d7  mov     [rax+18h], rbp
0x1400267db  push    rsi
0x1400267dc  push    r12
0x1400267de  push    r13
0x1400267e0  push    r14
0x1400267e2  push    r15
0x1400267e4  sub     rsp, 50h
0x1400267e8  mov     r14, rcx
0x1400267eb  lea     rdx, [rcx+1D0h]; struct CCriticalSection *
0x1400267f2  xorps   xmm0, xmm0
0x1400267f5  lea     rcx, [rax+8]; this
0x1400267f9  movups  xmmword ptr [rax-38h], xmm0
0x1400267fd  call    ??0CAutoCriticalSection@@QEAA@PEAVCCriticalSection@@@Z; CAutoCriticalSection::CAutoCriticalSection(CCriticalSection *)
0x140026802  lea     rcx, aCeventnotifica_89; "CEventNotificationService::SwitchToMain"...
0x140026809  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002680e  mov     ecx, [r14+1C8h]
0x140026815  call    ?WmsModeToString@Utils@@YAPEBGW4__MIDL___MIDL_itf_wmssvc_0000_0000_0001@@@Z; Utils::WmsModeToString(__MIDL___MIDL_itf_wmssvc_0000_0000_0001)
0x14002681a  mov     rdx, rax
0x14002681d  lea     rcx, aCeventnotifica_209; "CEventNotificationService::SwitchToMain"...
0x140026824  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140026829  mov     r12d, 2
0x14002682f  cmp     [r14+1C8h], r12d
0x140026836  jnz     short loc_140026873
0x140026838  xor     ebx, ebx
0x14002683a  lea     rax, aAlreadyInMaint; "Already in maintenance mode so nothing "...
0x140026841  mov     [rsp+78h+lpThreadId], rax
0x140026846  lea     rbp, aCeventnotifica_66; "CEventNotificationService::SwitchToMain"...
0x14002684d  mov     r9d, 1A6h
0x140026853  mov     qword ptr [rsp+78h+dwCreationFlags], rbp
0x140026858  lea     r8, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14002685f  lea     ecx, [rbx+4]; unsigned __int8
0x140026862  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140026869  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002686e  jmp     loc_140026B8B
0x140026873  mov     rcx, r14; this
0x140026876  call    ?ReleaseCore@CEventNotificationService@@IEAAJXZ; CEventNotificationService::ReleaseCore(void)
0x14002687b  mov     ebx, eax
0x14002687d  test    eax, eax
0x14002687f  js      loc_140026B8B
0x140026885  cmp     qword ptr [r14+68h], 0
0x14002688a  lea     rbp, aCeventnotifica_66; "CEventNotificationService::SwitchToMain"...
0x140026891  lea     rsi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140026898  lea     r13, aAssert; "ASSERT"
0x14002689f  jz      short loc_14002690E
0x1400268a1  mov     ebx, 1ACh
0x1400268a6  lea     r15, aMHstationthrea_1; "m_hStationThread == NULL"
0x1400268ad  mov     edx, ebx; unsigned int
0x1400268af  mov     qword ptr [rsp+78h+dwCreationFlags], r15; unsigned __int16 *
0x1400268b4  mov     r8, rbp; unsigned __int16 *
0x1400268b7  mov     rcx, rsi; unsigned __int16 *
0x1400268ba  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x1400268bf  call    cs:__imp_IsDebuggerPresent
0x1400268c5  test    eax, eax
0x1400268c7  jz      short loc_1400268EF
0x1400268c9  mov     [rsp+78h+var_48], r15
0x1400268ce  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400268d5  mov     [rsp+78h+lpThreadId], r13
0x1400268da  mov     r9d, ebx
0x1400268dd  mov     r8, rsi
0x1400268e0  mov     qword ptr [rsp+78h+dwCreationFlags], rbp
0x1400268e5  mov     ecx, r12d; unsigned __int8
0x1400268e8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400268ed  jmp     short loc_14002690E
0x1400268ef  mov     [rsp+78h+lpThreadId], r15
0x1400268f4  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400268fb  mov     r9, rbp
0x1400268fe  mov     qword ptr [rsp+78h+dwCreationFlags], r13
0x140026903  mov     r8d, ebx
0x140026906  mov     rdx, rsi
0x140026909  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002690e  mov     rcx, [r14+70h]; hEvent
0x140026912  call    cs:__imp_ResetEvent
0x140026918  mov     r9, r14; lpParameter
0x14002691b  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x140026924  lea     r8, ?s_StationThreadProc@CEventNotificationService@@KAKPEAX@Z; lpStartAddress
0x14002692b  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x140026933  xor     edx, edx; dwStackSize
0x140026935  xor     ecx, ecx; lpThreadAttributes
0x140026937  call    cs:__imp_CreateThread
0x14002693d  mov     [r14+68h], rax
0x140026941  mov     rcx, rax
0x140026944  test    rax, rax
0x140026947  jnz     loc_1400269F9
0x14002694d  call    cs:__imp_GetLastError
0x140026953  mov     ebx, eax
0x140026955  test    eax, eax
0x140026957  jle     short loc_140026962
0x140026959  movzx   ebx, ax
0x14002695c  or      ebx, 80070000h
0x140026962  lea     r13, aMHstationthrea_0; "m_hStationThread != 0"
0x140026969  mov     r15d, 1B1h
0x14002696f  mov     eax, 80004005h
0x140026974  lea     r14, aCbraex; "CBRAEx"
0x14002697b  test    ebx, ebx
0x14002697d  mov     r8, rbp; unsigned __int16 *
0x140026980  mov     r9, r14; unsigned __int16 *
0x140026983  mov     edx, r15d; unsigned int
0x140026986  cmovns  ebx, eax
0x140026989  mov     rcx, rsi; unsigned __int16 *
0x14002698c  mov     dword ptr [rsp+78h+lpThreadId], ebx; int
0x140026990  mov     qword ptr [rsp+78h+dwCreationFlags], r13; unsigned __int16 *
0x140026995  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002699a  call    cs:__imp_IsDebuggerPresent
0x1400269a0  test    eax, eax
0x1400269a2  jz      short loc_1400269D1
0x1400269a4  mov     [rsp+78h+var_40], ebx
0x1400269a8  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400269af  mov     [rsp+78h+var_48], r13
0x1400269b4  mov     r9d, r15d
0x1400269b7  mov     [rsp+78h+lpThreadId], r14
0x1400269bc  mov     r8, rsi
0x1400269bf  mov     ecx, r12d; unsigned __int8
0x1400269c2  mov     qword ptr [rsp+78h+dwCreationFlags], rbp
0x1400269c7  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400269cc  jmp     loc_140026B8B
0x1400269d1  mov     dword ptr [rsp+78h+var_48], ebx
0x1400269d5  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400269dc  mov     [rsp+78h+lpThreadId], r13
0x1400269e1  mov     r9, rbp
0x1400269e4  mov     r8d, r15d
0x1400269e7  mov     qword ptr [rsp+78h+dwCreationFlags], r14
0x1400269ec  mov     rdx, rsi
0x1400269ef  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400269f4  jmp     loc_140026B8B
0x1400269f9  mov     rax, [r14+70h]
0x1400269fd  mov     [rsp+78h+var_30], rcx
0x140026a02  lea     rcx, aCeventnotifica_203; "CEventNotificationService::SwitchToMain"...
0x140026a09  mov     [rsp+78h+Handles], rax
0x140026a0e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140026a13  or      ebx, 0FFFFFFFFh
0x140026a16  lea     rdx, [rsp+78h+Handles]; lpHandles
0x140026a1b  mov     r9d, ebx; dwMilliseconds
0x140026a1e  xor     r8d, r8d; bWaitAll
0x140026a21  mov     ecx, r12d; nCount
0x140026a24  call    cs:__imp_WaitForMultipleObjects
0x140026a2a  mov     edx, eax
0x140026a2c  lea     rcx, aCeventnotifica_163; "CEventNotificationService::SwitchToMain"...
0x140026a33  mov     r15d, eax
0x140026a36  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140026a3b  cmp     r15d, ebx
0x140026a3e  jnz     short loc_140026A67
0x140026a40  call    cs:__imp_GetLastError
0x140026a46  mov     ebx, eax
0x140026a48  test    eax, eax
0x140026a4a  jle     short loc_140026A55
0x140026a4c  movzx   ebx, ax
0x140026a4f  or      ebx, 80070000h
0x140026a55  lea     r13, aDwwaitresultDw; "dwWaitResult != ((DWORD)0xFFFFFFFF)"
0x140026a5c  mov     r15d, 1BBh
0x140026a62  jmp     loc_14002696F
0x140026a67  mov     ebx, [r14+80h]
0x140026a6e  test    ebx, ebx
0x140026a70  js      loc_140026B8B
0x140026a76  test    r15d, r15d
0x140026a79  jz      short loc_140026A85
0x140026a7b  mov     ebx, 80004005h
0x140026a80  jmp     loc_140026B8B
0x140026a85  cmp     qword ptr [r14+208h], 0
0x140026a8d  jnz     short loc_140026AFC
0x140026a8f  mov     ebx, 1BFh
0x140026a94  lea     r15, aMPstationmanag; "m_pStationManager != NULL"
0x140026a9b  mov     edx, ebx; unsigned int
0x140026a9d  mov     qword ptr [rsp+78h+dwCreationFlags], r15; unsigned __int16 *
0x140026aa2  mov     r8, rbp; unsigned __int16 *
0x140026aa5  mov     rcx, rsi; unsigned __int16 *
0x140026aa8  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140026aad  call    cs:__imp_IsDebuggerPresent
0x140026ab3  test    eax, eax
0x140026ab5  jz      short loc_140026ADD
0x140026ab7  mov     [rsp+78h+var_48], r15
0x140026abc  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140026ac3  mov     [rsp+78h+lpThreadId], r13
0x140026ac8  mov     r9d, ebx
0x140026acb  mov     r8, rsi
0x140026ace  mov     qword ptr [rsp+78h+dwCreationFlags], rbp
0x140026ad3  mov     ecx, r12d; unsigned __int8
0x140026ad6  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140026adb  jmp     short loc_140026AFC
0x140026add  mov     [rsp+78h+lpThreadId], r15
0x140026ae2  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140026ae9  mov     r9, rbp
0x140026aec  mov     qword ptr [rsp+78h+dwCreationFlags], r13
0x140026af1  mov     r8d, ebx
0x140026af4  mov     rdx, rsi
0x140026af7  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140026afc  cmp     qword ptr [r14+1C0h], 0
0x140026b04  jnz     short loc_140026B73
0x140026b06  mov     ebx, 1C0h
0x140026b0b  lea     r15, aMPcoreNull; "m_pCore != NULL"
0x140026b12  mov     edx, ebx; unsigned int
0x140026b14  mov     qword ptr [rsp+78h+dwCreationFlags], r15; unsigned __int16 *
0x140026b19  mov     r8, rbp; unsigned __int16 *
0x140026b1c  mov     rcx, rsi; unsigned __int16 *
0x140026b1f  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140026b24  call    cs:__imp_IsDebuggerPresent
0x140026b2a  test    eax, eax
0x140026b2c  jz      short loc_140026B54
0x140026b2e  mov     [rsp+78h+var_48], r15
0x140026b33  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140026b3a  mov     [rsp+78h+lpThreadId], r13
0x140026b3f  mov     r9d, ebx
0x140026b42  mov     r8, rsi
0x140026b45  mov     qword ptr [rsp+78h+dwCreationFlags], rbp
0x140026b4a  mov     ecx, r12d; unsigned __int8
0x140026b4d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140026b52  jmp     short loc_140026B73
0x140026b54  mov     [rsp+78h+lpThreadId], r15
0x140026b59  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140026b60  mov     r9, rbp
0x140026b63  mov     qword ptr [rsp+78h+dwCreationFlags], r13
0x140026b68  mov     r8d, ebx
0x140026b6b  mov     rdx, rsi
0x140026b6e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140026b73  lea     rcx, [r14+8]
0x140026b77  mov     edx, r12d
0x140026b7a  mov     rax, [rcx]
0x140026b7d  mov     rax, [rax+0A8h]
0x140026b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026b89  mov     ebx, eax
0x140026b8b  lea     rcx, [rsp+78h+arg_0]; this
0x140026b93  call    ??1CAutoCriticalSection@@QEAA@XZ; CAutoCriticalSection::~CAutoCriticalSection(void)
0x140026b98  lea     r11, [rsp+78h+var_28]
0x140026b9d  mov     eax, ebx
0x140026b9f  mov     rbx, [r11+38h]
0x140026ba3  mov     rbp, [r11+40h]
0x140026ba7  mov     rsp, r11
0x140026baa  pop     r15
0x140026bac  pop     r14
0x140026bae  pop     r13
0x140026bb0  pop     r12
0x140026bb2  pop     rsi
0x140026bb3  retn
```
