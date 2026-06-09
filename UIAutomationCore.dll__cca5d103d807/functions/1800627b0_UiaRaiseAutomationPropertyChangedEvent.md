# UiaRaiseAutomationPropertyChangedEvent

- ea: `0x1800627b0`
- end: `0x180063214`
- name: `UiaRaiseAutomationPropertyChangedEvent`
- size: `2660`
- prototype: `HRESULT __stdcall(IRawElementProviderSimple *pProvider, PROPERTYID id, VARIANT *__struct_ptr oldValue, VARIANT *__struct_ptr newValue)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800ca7c0`

## callees

- `0x18002f580`
- `0x180061630`
- `0x180061aec`
- `0x1800627b0`
- `0x180063580`
- `0x1800637c0`
- `0x18006410c`
- `0x180064788`
- `0x180065aac`
- `0x1800975b0`
- `0x1800ad62c`
- `0x18011c6d4`
- `0x180133550`
- `0x180179d4c`
- `0x180186cd0`
- `0x1801b62e0`
- `0x1801e8320`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180062b5e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180062c61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180062d9d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180062b5e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180062c61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180062d9d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180062f17`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180062f17`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180062942`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180062942`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006286c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006286c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006289a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062d81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006289a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ee1`
- `OLEAUT32!__imp_SysAllocString` at `0x180062b70`
- `OLEAUT32!__imp_SysAllocString` at `0x180062c73`
- `OLEAUT32!__imp_SysAllocString` at `0x180062daf`
- `OLEAUT32!__imp_SysAllocString` at `0x180062b70`
- `OLEAUT32!__imp_SysAllocString` at `0x180062c73`
- `OLEAUT32!__imp_SysAllocString` at `0x180062daf`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180062fae`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180062fae`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x180062abd`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x180062abd`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!NotifyWinEvent` at `0x180062b23`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!NotifyWinEvent` at `0x180062b23`

## string_xrefs

- `0x180062cfc`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi.cpp`

## pseudocode

```c
HRESULT __stdcall UiaRaiseAutomationPropertyChangedEvent(
        IRawElementProviderSimple *pProvider,
        PROPERTYID id,
        VARIANT *oldValue,
        VARIANT *newValue)
{
  VARIANT *v4; // r14
  VARIANT *v5; // r12
  IRawElementProviderSimple *v7; // r15
  PVOID *v8; // rcx
  GUID **v9; // rbx
  int v10; // ecx
  int v11; // ecx
  HRESULT v12; // ebx
  const char *v13; // r9
  __int64 v14; // rbx
  __int64 v15; // rdi
  __int128 v16; // xmm0
  IRecordInfo *pRecInfo; // xmm1_8
  __int128 v18; // xmm0
  IRecordInfo *v19; // xmm1_8
  int v20; // r8d
  PVOID v21; // rcx
  DWORD *v23; // r14
  DWORD *v24; // r12
  DWORD v25; // r15d
  WINBOOL v26; // r8d
  const unsigned __int16 *v27; // rbx
  signed int v28; // r13d
  unsigned __int16 *v29; // rdi
  bool v30; // zf
  const unsigned __int16 *v31; // rbx
  signed int v32; // r13d
  unsigned __int16 *v33; // rdi
  int v34; // r8d
  PVOID v35; // rcx
  const unsigned __int16 *v36; // rbx
  signed int v37; // r13d
  unsigned __int16 *ProviderInfo; // rdi
  int v39; // r8d
  signed int v40; // eax
  signed int v41; // eax
  signed int LastError; // eax
  int v43; // eax
  DWORD v44; // edx
  struct UserDefinedPropertyInfo *i; // rbx
  const OLECHAR *v46; // r8
  const OLECHAR *v47; // rax
  const OLECHAR *v48; // rcx
  const OLECHAR *v49; // rax
  const OLECHAR *v50; // r8
  const OLECHAR *v51; // rax
  const OLECHAR *v52; // r8
  const OLECHAR *v53; // rax
  const OLECHAR *v54; // rcx
  const OLECHAR *v55; // rax
  int *v56; // [rsp+20h] [rbp-E0h]
  __int64 v57; // [rsp+30h] [rbp-D0h]
  WINBOOL fPending; // [rsp+40h] [rbp-C0h] BYREF
  VARIANT *v59; // [rsp+48h] [rbp-B8h] BYREF
  struct IRawElementProviderSimple *v60; // [rsp+50h] [rbp-B0h]
  int v61; // [rsp+58h] [rbp-A8h] BYREF
  int v62; // [rsp+5Ch] [rbp-A4h] BYREF
  struct UiaEventArgs v63; // [rsp+60h] [rbp-A0h] BYREF
  PROPERTYID v64; // [rsp+68h] [rbp-98h]
  int v65; // [rsp+6Ch] [rbp-94h]
  _BYTE v66[48]; // [rsp+70h] [rbp-90h]
  _QWORD v67[2]; // [rsp+A0h] [rbp-60h] BYREF
  HWND hwnd[2]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[512]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  v4 = newValue;
  v59 = newValue;
  v5 = oldValue;
  v67[0] = oldValue;
  v7 = pProvider;
  v60 = pProvider;
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
  {
    v56 = (int *)hwnd;
    McGenEventWrite_EventWriteTransfer(pProvider, UIAutomationCoreAPI_UiaRaiseEvent_Start);
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (_DWORD)oldValue,
      (unsigned int)"UiaRaiseAutomationPropertyChangedEvent",
      (char)v7,
      id);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v7 )
  {
    v30 = v8 == &WPP_GLOBAL_Control;
    goto LABEL_59;
  }
  EnterCriticalSection(&_schemaLock);
  if ( (unsigned int)(id - 30000) > 0xAF )
  {
    for ( i = g_pUserDefinedProperties; ; i = *(struct UserDefinedPropertyInfo **)i )
    {
      if ( !i )
      {
        LeaveCriticalSection(&_schemaLock);
        goto LABEL_82;
      }
      if ( *((_DWORD *)i + 6) == id )
        break;
    }
    v9 = (GUID **)((char *)i + 16);
  }
  else
  {
    v9 = &(&off_1802DE930)[8 * (unsigned __int64)(unsigned int)(id - 30000)];
  }
  LeaveCriticalSection(&_schemaLock);
  if ( !v9 )
  {
LABEL_82:
    if ( LoadStringW(g_hInstance, 0x12Cu, Buffer, 512) )
    {
      v67[0] = SysAllocString(Buffer);
      v36 = (const unsigned __int16 *)v67[0];
      if ( v67[0] )
        v37 = 0;
      else
        v37 = -2147024882;
    }
    else
    {
      v36 = 0;
      v67[0] = 0;
      LastError = GetLastError();
      v37 = LastError;
      if ( LastError > 0 )
        v37 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v37 >= 0 )
      Error::SetError(v36, 0);
    ProviderInfo = GetProviderInfo((struct IUnknown *)v7);
    v59 = (VARIANT *)ProviderInfo;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v52 = &word_180313900;
      v53 = &word_180313900;
      if ( ProviderInfo )
        v52 = ProviderInfo;
      if ( v36 )
        v53 = v36;
      WPP_SF_SdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, (__int64)v53, (__int64)v52);
    }
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 1) != 0 )
    {
      v54 = &word_180313900;
      if ( ProviderInfo )
        v54 = ProviderInfo;
      v55 = &word_180313900;
      if ( v36 )
        v55 = v36;
      McTemplateU0zdzzz_EventWriteTransfer(
        (_DWORD)v54,
        (unsigned int)Error_ProviderError,
        (unsigned int)L"UiaRaiseAutomationPropertyChangedEvent",
        -2147024809,
        (__int64)v55,
        (__int64)&word_180313900,
        (__int64)v54);
    }
    AutoCleanupInfo<unsigned short *>::SafeRelease(&v59);
    AutoCleanupInfo<unsigned short *>::SafeRelease(v67);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        v39,
        (unsigned int)"UiaRaiseAutomationPropertyChangedEvent",
        (char)v7,
        id);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) == 0 )
      return -2147024809;
LABEL_63:
    McGenEventWrite_EventWriteTransfer(v8, "x");
    return -2147024809;
  }
  if ( v5->vt && v5->vt != *((_WORD *)v9 + 20) )
  {
    if ( LoadStringW(g_hInstance, 0x12Du, Buffer, 512) )
    {
      v67[0] = SysAllocString(Buffer);
      v31 = (const unsigned __int16 *)v67[0];
      if ( v67[0] )
        v32 = 0;
      else
        v32 = -2147024882;
    }
    else
    {
      v31 = 0;
      v67[0] = 0;
      v41 = GetLastError();
      v32 = v41;
      if ( v41 > 0 )
        v32 = (unsigned __int16)v41 | 0x80070000;
    }
    if ( v32 >= 0 )
      Error::SetError(v31, 0);
    v33 = GetProviderInfo((struct IUnknown *)v7);
    v59 = (VARIANT *)v33;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v46 = &word_180313900;
      v47 = &word_180313900;
      if ( v33 )
        v46 = v33;
      if ( v31 )
        v47 = v31;
      WPP_SF_SdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, (__int64)v47, (__int64)v46);
    }
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 1) == 0 )
      goto LABEL_58;
    v48 = &word_180313900;
    if ( v33 )
      v48 = v33;
    v49 = &word_180313900;
    v57 = (__int64)v48;
    if ( v31 )
      v49 = v31;
LABEL_133:
    McTemplateU0zdzzz_EventWriteTransfer(
      (_DWORD)v48,
      (unsigned int)Error_ProviderError,
      (unsigned int)L"UiaRaiseAutomationPropertyChangedEvent",
      -2147024809,
      (__int64)v49,
      (__int64)&word_180313900,
      v57);
LABEL_58:
    AutoCleanupInfo<unsigned short *>::SafeRelease(&v59);
    AutoCleanupInfo<unsigned short *>::SafeRelease(v67);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v30 = WPP_GLOBAL_Control == &WPP_GLOBAL_Control;
LABEL_59:
    if ( !v30 && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
      WPP_SF_sqd(
        (unsigned int)v8[2],
        13,
        (_DWORD)oldValue,
        (unsigned int)"UiaRaiseAutomationPropertyChangedEvent",
        (char)v7,
        id);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) == 0 )
      return -2147024809;
    goto LABEL_63;
  }
  if ( v4->vt && v4->vt != *((_WORD *)v9 + 20) )
  {
    if ( LoadStringW(g_hInstance, 0x12Eu, Buffer, 512) )
    {
      v67[0] = SysAllocString(Buffer);
      v27 = (const unsigned __int16 *)v67[0];
      if ( v67[0] )
        v28 = 0;
      else
        v28 = -2147024882;
    }
    else
    {
      v27 = 0;
      v67[0] = 0;
      v40 = GetLastError();
      v28 = v40;
      if ( v40 > 0 )
        v28 = (unsigned __int16)v40 | 0x80070000;
    }
    if ( v28 >= 0 )
      Error::SetError(v27, 0);
    v29 = GetProviderInfo((struct IUnknown *)v7);
    v59 = (VARIANT *)v29;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v50 = &word_180313900;
      v51 = &word_180313900;
      if ( v29 )
        v50 = v29;
      if ( v27 )
        v51 = v27;
      WPP_SF_SdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, (__int64)v51, (__int64)v50);
    }
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 1) == 0 )
      goto LABEL_58;
    v48 = &word_180313900;
    if ( v29 )
      v48 = v29;
    v49 = &word_180313900;
    v57 = (__int64)v48;
    if ( v27 )
      v49 = v27;
    goto LABEL_133;
  }
  if ( !BasicUiaUtils::s_isDesktopDetermined )
  {
    BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
    BasicUiaUtils::s_isDesktopDetermined = 1;
  }
  if ( !BasicUiaUtils::s_isDesktop )
    goto LABEL_32;
  v61 = 0;
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McTemplateU0zqq_EventWriteTransfer(
      v10,
      (unsigned int)UiaProviderCallout_Start,
      (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
      0,
      0);
  v12 = ((__int64 (__fastcall *)(IRawElementProviderSimple *, int *))v7->lpVtbl->get_ProviderOptions)(v7, &v61);
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McTemplateU0zqq_EventWriteTransfer(
      v11,
      (unsigned int)UiaProviderCallout_Stop,
      (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
      0,
      0);
  if ( v12 >= 0 )
  {
    if ( (v61 & 0x80u) == 0 )
    {
      fPending = 0;
      if ( __std_init_once_begin_initialize(&BasicUtils::s_initOnceIsInCrossMachineRemoteSession, 0, &fPending, 0) )
      {
        if ( fPending )
        {
          v43 = lambda_312a8970364be71481f3490781272cd3_::operator()();
          if ( v43 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x37F,
              (unsigned int)"wil",
              (const char *)(unsigned int)v43,
              (int)v56);
            v44 = 4;
          }
          else
          {
            v44 = 0;
          }
          InitOnceComplete(&BasicUtils::s_initOnceIsInCrossMachineRemoteSession, v44, 0);
        }
      }
      else
      {
        wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v13);
      }
      if ( !BasicUtils::s_inCrossMachineRemoteSession )
      {
        fPending = 0;
        if ( id )
        {
          v15 = *((_QWORD *)&MsaaEventMap + 1);
          v14 = MsaaEventMap;
          hwnd[0] = 0;
          while ( v14 != v15 )
          {
            if ( *(_DWORD *)(v14 + 8) == id )
            {
              v23 = *(DWORD **)(v14 + 16);
              v24 = *(DWORD **)(v14 + 24);
              while ( v23 != v24 )
              {
                v25 = *v23;
                if ( IsWinEventHookInstalled(*v23) )
                {
                  if ( !hwnd[0] || (v26 = fPending) == 0 )
                  {
                    if ( (int)GetProviderEventInfo(v60, hwnd, &fPending) < 0 )
                      goto LABEL_134;
                    v26 = fPending;
                    if ( !fPending )
                    {
                      if ( (int)EventMap::AddEntry((char *)g_TheEventMap, hwnd[0], v60, &fPending) < 0 )
                      {
LABEL_134:
                        v7 = v60;
                        goto LABEL_31;
                      }
                      v26 = fPending;
                    }
                  }
                  NotifyWinEvent(v25, hwnd[0], v26, 0);
                }
                ++v23;
              }
            }
            v14 += 48;
          }
          v7 = v60;
          if ( (unsigned int)(id - 49152) <= 0x3FFF )
          {
            v62 = 0;
            FireWinEventIfHookInstalled(v60, id, 1, hwnd, &fPending, &v62);
          }
LABEL_31:
          v5 = (VARIANT *)v67[0];
          v4 = v59;
        }
      }
    }
LABEL_32:
    v16 = *(_OWORD *)&v5->vt;
    *(_QWORD *)&v66[12] = 0;
    pRecInfo = v5->pRecInfo;
    *(_QWORD *)&v66[20] = 0;
    *(_QWORD *)&v66[36] = 0;
    v65 = 0;
    *(_OWORD *)v66 = v16;
    v18 = *(_OWORD *)&v4->vt;
    v63.Type = EventArgsType_PropertyChanged;
    *(_QWORD *)&v66[16] = pRecInfo;
    v19 = v4->pRecInfo;
    *(_OWORD *)&v66[24] = v18;
    v63.EventId = 20004;
    v64 = id;
    *(_QWORD *)&v66[40] = v19;
    EventManager::RaiseEvent(v7, &v63, 0);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        v20,
        (unsigned int)"UiaRaiseAutomationPropertyChangedEvent",
        (char)v7,
        id);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v21, "x");
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x174,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi.cpp",
    (const char *)(unsigned int)v12,
    (int)v56);
  v35 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      v34,
      (unsigned int)"UiaRaiseAutomationPropertyChangedEvent",
      (char)v7,
      id);
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v35, "x");
  return v12;
}

```

## disassembly

```asm
0x1800627b0  push    rbp
0x1800627b2  push    rsi
0x1800627b3  push    r12
0x1800627b5  push    r14
0x1800627b7  push    r15
0x1800627b9  lea     rbp, [rsp-3F0h]
0x1800627c1  sub     rsp, 4F0h
0x1800627c8  mov     rax, cs:__security_cookie
0x1800627cf  xor     rax, rsp
0x1800627d2  mov     [rbp+410h+var_50], rax
0x1800627d9  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800627e0  mov     r14, r9
0x1800627e3  mov     [rsp+510h+var_4C8], r9
0x1800627e8  mov     r12, r8
0x1800627eb  mov     [rbp+410h+var_470], r8
0x1800627ef  mov     esi, edx
0x1800627f1  mov     r15, rcx
0x1800627f4  mov     [rsp+510h+var_4C0], rcx
0x1800627f9  jnz     loc_180062FD2
0x1800627ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180062806  lea     rax, WPP_GLOBAL_Control
0x18006280d  cmp     rcx, rax
0x180062810  jz      short loc_180062844
0x180062812  test    byte ptr [rcx+1Ch], 10h
0x180062816  jz      short loc_180062844
0x180062818  mov     rcx, [rcx+10h]
0x18006281c  lea     r9, aUiaraiseautoma_1; "UiaRaiseAutomationPropertyChangedEvent"
0x180062823  mov     edx, 0Ch
0x180062828  mov     dword ptr [rsp+510h+var_4E8], esi
0x18006282c  mov     [rsp+510h+var_4F0], r15; int
0x180062831  call    WPP_SF_sqd
0x180062836  mov     rcx, cs:WPP_GLOBAL_Control
0x18006283d  lea     rax, WPP_GLOBAL_Control
0x180062844  mov     [rsp+510h+var_28], rbx
0x18006284c  mov     [rsp+510h+var_30], rdi
0x180062854  mov     [rsp+510h+var_38], r13
0x18006285c  test    r15, r15
0x18006285f  jz      loc_180062D72
0x180062865  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006286c  call    cs:__imp_EnterCriticalSection
0x180062872  lea     eax, [rsi-7530h]
0x180062878  cmp     eax, 0AFh
0x18006287d  ja      loc_180062F22
0x180062883  mov     ebx, eax
0x180062885  lea     rax, off_1802DE930
0x18006288c  shl     rbx, 6
0x180062890  add     rbx, rax
0x180062893  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006289a  call    cs:__imp_LeaveCriticalSection
0x1800628a0  test    rbx, rbx
0x1800628a3  jz      loc_180062D87
0x1800628a9  movzx   eax, word ptr [r12]
0x1800628ae  test    ax, ax
0x1800628b1  jnz     loc_180062C41
0x1800628b7  movzx   eax, word ptr [r14]
0x1800628bb  test    ax, ax
0x1800628be  jnz     loc_180062B3E
0x1800628c4  movzx   eax, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x1800628cb  nop
0x1800628cc  test    al, al
0x1800628ce  jz      loc_180062FA9
0x1800628d4  xor     r13d, r13d
0x1800628d7  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, r13b; bool BasicUiaUtils::s_isDesktop
0x1800628de  jz      loc_1800629B3
0x1800628e4  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800628eb  mov     [rsp+510h+var_4B8], r13d
0x1800628f0  jnz     loc_180062F44
0x1800628f6  mov     rax, [r15]
0x1800628f9  lea     rdx, [rsp+510h+var_4B8]
0x1800628fe  mov     rcx, r15
0x180062901  mov     rax, [rax+18h]
0x180062905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006290a  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180062911  mov     ebx, eax
0x180062913  jnz     loc_180062F64
0x180062919  test    ebx, ebx
0x18006291b  js      loc_180062CF5
0x180062921  test    byte ptr [rsp+510h+var_4B8], 80h
0x180062926  jnz     loc_1800629B3
0x18006292c  xor     r9d, r9d; lpContext
0x18006292f  mov     [rsp+510h+fPending], r13d
0x180062934  lea     r8, [rsp+510h+fPending]; fPending
0x180062939  xor     edx, edx; dwFlags
0x18006293b  lea     rcx, ?s_initOnceIsInCrossMachineRemoteSession@BasicUtils@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x180062942  call    cs:__imp___std_init_once_begin_initialize
0x180062948  test    eax, eax
0x18006294a  jz      loc_180062E64
0x180062950  cmp     [rsp+510h+fPending], r13d
0x180062955  jnz     loc_180062F02
0x18006295b  cmp     cs:?s_inCrossMachineRemoteSession@BasicUtils@@0_NA, r13b; bool BasicUtils::s_inCrossMachineRemoteSession
0x180062962  jnz     short loc_1800629B3
0x180062964  mov     [rsp+510h+fPending], r13d
0x180062969  test    esi, esi
0x18006296b  jz      short loc_1800629B3
0x18006296d  mov     rbx, qword ptr cs:?MsaaEventMap@@3V?$vector@UEventMapEntry@@V?$allocator@UEventMapEntry@@@std@@@std@@B; std::vector<EventMapEntry> const MsaaEventMap
0x180062974  mov     rdi, qword ptr cs:?MsaaEventMap@@3V?$vector@UEventMapEntry@@V?$allocator@UEventMapEntry@@@std@@@std@@B+8; std::vector<EventMapEntry> const MsaaEventMap
0x18006297b  mov     [rbp+410h+hwnd], r13
0x18006297f  nop
0x180062980  cmp     rbx, rdi
0x180062983  jz      short loc_180062994
0x180062985  cmp     [rbx+8], esi
0x180062988  jz      loc_180062AA6
0x18006298e  add     rbx, 30h ; '0'
0x180062992  jmp     short loc_180062980
0x180062994  mov     r15, [rsp+510h+var_4C0]
0x180062999  lea     eax, [rsi-0C000h]
0x18006299f  cmp     eax, 3FFFh
0x1800629a4  jbe     loc_180063136
0x1800629aa  mov     r12, [rbp+410h+var_470]
0x1800629ae  mov     r14, [rsp+510h+var_4C8]
0x1800629b3  movups  xmm0, xmmword ptr [r12]
0x1800629b8  lea     rdx, [rsp+510h+var_4B0]; struct UiaEventArgs *
0x1800629bd  mov     [rsp+510h+var_494], r13
0x1800629c2  movsd   xmm1, qword ptr [r12+10h]
0x1800629c9  xor     r8d, r8d; bool
0x1800629cc  mov     qword ptr [rbp+410h+var_48C], r13
0x1800629d0  mov     rcx, r15; struct IRawElementProviderSimple *
0x1800629d3  mov     [rbp+410h+var_47C], r13
0x1800629d7  mov     qword ptr [rsp+510h+var_4A4], r13
0x1800629dc  movaps  [rsp+510h+var_4A4+4], xmm0
0x1800629e1  movups  xmm0, xmmword ptr [r14]
0x1800629e5  mov     [rsp+510h+var_4B0.Type], 1
0x1800629ed  movsd   [rbp+410h+var_494+4], xmm1
0x1800629f2  movsd   xmm1, qword ptr [r14+10h]
0x1800629f8  movups  [rbp+410h+var_48C+4], xmm0
0x1800629fc  mov     [rsp+510h+var_4B0.EventId], 4E24h
0x180062a04  mov     [rsp+510h+var_4A8], esi
0x180062a08  movsd   [rbp+410h+var_47C+4], xmm1
0x180062a0d  call    ?RaiseEvent@EventManager@@SAXPEAUIRawElementProviderSimple@@PEAUUiaEventArgs@@_N@Z; EventManager::RaiseEvent(IRawElementProviderSimple *,UiaEventArgs *,bool)
0x180062a12  mov     rcx, cs:WPP_GLOBAL_Control
0x180062a19  lea     r12, WPP_GLOBAL_Control
0x180062a20  cmp     rcx, r12
0x180062a23  jz      short loc_180062A49
0x180062a25  test    byte ptr [rcx+1Ch], 10h
0x180062a29  jz      short loc_180062A49
0x180062a2b  mov     rcx, [rcx+10h]
0x180062a2f  lea     r9, aUiaraiseautoma_1; "UiaRaiseAutomationPropertyChangedEvent"
0x180062a36  mov     edx, 0Dh
0x180062a3b  mov     dword ptr [rsp+510h+var_4E8], esi
0x180062a3f  mov     [rsp+510h+var_4F0], r15
0x180062a44  call    WPP_SF_sqd
0x180062a49  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180062a50  jz      short loc_180062A6D
0x180062a52  lea     rax, [rbp+410h+var_470]
0x180062a56  mov     r9d, 1
0x180062a5c  lea     rdx, UIAutomationCoreAPI_UiaRaiseEvent_Stop; "x"
0x180062a63  mov     [rsp+510h+var_4F0], rax
0x180062a68  call    McGenEventWrite_EventWriteTransfer
0x180062a6d  xor     eax, eax
0x180062a6f  mov     r13, [rsp+510h+var_38]
0x180062a77  mov     rdi, [rsp+510h+var_30]
0x180062a7f  mov     rbx, [rsp+510h+var_28]
0x180062a87  mov     rcx, [rbp+410h+var_50]
0x180062a8e  xor     rcx, rsp; StackCookie
0x180062a91  call    __security_check_cookie
0x180062a96  add     rsp, 4F0h
0x180062a9d  pop     r15
0x180062a9f  pop     r14
0x180062aa1  pop     r12
0x180062aa3  pop     rsi
0x180062aa4  pop     rbp
0x180062aa5  retn
0x180062aa6  mov     r14, [rbx+10h]
0x180062aaa  mov     r12, [rbx+18h]
0x180062aae  cmp     r14, r12
0x180062ab1  jz      loc_18006298E
0x180062ab7  mov     r15d, [r14]
0x180062aba  mov     ecx, r15d; event
0x180062abd  call    cs:__imp_IsWinEventHookInstalled
0x180062ac3  test    eax, eax
0x180062ac5  jz      short loc_180062B29
0x180062ac7  cmp     [rbp+410h+hwnd], r13
0x180062acb  jnz     short loc_180062B32
0x180062acd  mov     rcx, [rsp+510h+var_4C0]; struct IRawElementProviderSimple *
0x180062ad2  lea     r8, [rsp+510h+fPending]; int *
0x180062ad7  lea     rdx, [rbp+410h+hwnd]; HWND *
0x180062adb  call    ?GetProviderEventInfo@@YAJPEAUIRawElementProviderSimple@@PEAPEAUHWND__@@PEAJ@Z; GetProviderEventInfo(IRawElementProviderSimple *,HWND__ * *,long *)
0x180062ae0  test    eax, eax
0x180062ae2  js      loc_180063168
0x180062ae8  mov     r8d, [rsp+510h+fPending]
0x180062aed  test    r8d, r8d
0x180062af0  jnz     short loc_180062B19
0x180062af2  mov     r8, [rsp+510h+var_4C0]; struct IRawElementProviderSimple *
0x180062af7  lea     r9, [rsp+510h+fPending]; int *
0x180062afc  mov     rdx, [rbp+410h+hwnd]; HWND
0x180062b00  lea     rcx, ?g_TheEventMap@@3V?$object_without_destructor_on_shutdown@VEventMap@@@wil@@A; Parameter
0x180062b07  call    ?AddEntry@EventMap@@QEAAJPEAUHWND__@@PEAUIRawElementProviderSimple@@PEAJ@Z; EventMap::AddEntry(HWND__ *,IRawElementProviderSimple *,long *)
0x180062b0c  test    eax, eax
0x180062b0e  js      loc_180063168
0x180062b14  mov     r8d, [rsp+510h+fPending]; idObject
0x180062b19  mov     rdx, [rbp+410h+hwnd]; hwnd
0x180062b1d  xor     r9d, r9d; idChild
0x180062b20  mov     ecx, r15d; event
0x180062b23  call    cs:__imp_NotifyWinEvent
0x180062b29  add     r14, 4
0x180062b2d  jmp     loc_180062AAE
0x180062b32  mov     r8d, [rsp+510h+fPending]
0x180062b37  test    r8d, r8d
0x180062b3a  jnz     short loc_180062B19
0x180062b3c  jmp     short loc_180062ACD
0x180062b3e  cmp     ax, [rbx+28h]
0x180062b42  jz      loc_1800628C4
0x180062b48  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180062b4f  lea     r8, [rbp+410h+Buffer]; lpBuffer
0x180062b53  mov     r9d, 200h; cchBufferMax
0x180062b59  mov     edx, 12Eh; uID
0x180062b5e  call    cs:__imp_LoadStringW
0x180062b64  test    eax, eax
0x180062b66  jz      loc_180062E81
0x180062b6c  lea     rcx, [rbp+410h+Buffer]; psz
0x180062b70  call    cs:__imp_SysAllocString
0x180062b76  mov     [rbp+410h+var_470], rax
0x180062b7a  mov     rbx, rax
0x180062b7d  test    rax, rax
0x180062b80  jnz     loc_180063094
0x180062b86  mov     r13d, 8007000Eh
0x180062b8c  test    r13d, r13d
0x180062b8f  jns     loc_18006309C
0x180062b95  mov     rcx, r15; struct IUnknown *
0x180062b98  call    ?GetProviderInfo@@YAPEAGPEAUIUnknown@@@Z; GetProviderInfo(IUnknown *)
0x180062b9d  mov     rdi, rax
0x180062ba0  mov     [rsp+510h+var_4C8], rax
0x180062ba5  mov     rcx, cs:WPP_GLOBAL_Control
0x180062bac  lea     r12, WPP_GLOBAL_Control
0x180062bb3  lea     r14, word_180313900
0x180062bba  cmp     rcx, r12
0x180062bbd  jnz     loc_1800630AB
0x180062bc3  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 1
0x180062bca  jnz     loc_1800630F5
0x180062bd0  lea     rcx, [rsp+510h+var_4C8]
0x180062bd5  call    ?SafeRelease@?$AutoCleanupInfo@PEAG@@SAXAEAPEAG@Z; AutoCleanupInfo<ushort *>::SafeRelease(ushort * &)
0x180062bda  lea     rcx, [rbp+410h+var_470]
0x180062bde  call    ?SafeRelease@?$AutoCleanupInfo@PEAG@@SAXAEAPEAG@Z; AutoCleanupInfo<ushort *>::SafeRelease(ushort * &)
0x180062be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180062bea  cmp     rcx, r12
0x180062bed  jz      short loc_180062C13
0x180062bef  test    byte ptr [rcx+1Ch], 10h
0x180062bf3  jz      short loc_180062C13
0x180062bf5  mov     rcx, [rcx+10h]
0x180062bf9  lea     r9, aUiaraiseautoma_1; "UiaRaiseAutomationPropertyChangedEvent"
0x180062c00  mov     edx, 0Dh
0x180062c05  mov     dword ptr [rsp+510h+var_4E8], esi
0x180062c09  mov     [rsp+510h+var_4F0], r15
0x180062c0e  call    WPP_SF_sqd
0x180062c13  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180062c1a  jz      short loc_180062C37
0x180062c1c  lea     rax, [rbp+410h+var_470]
0x180062c20  mov     r9d, 1
0x180062c26  lea     rdx, UIAutomationCoreAPI_UiaRaiseEvent_Stop; "x"
0x180062c2d  mov     [rsp+510h+var_4F0], rax
0x180062c32  call    McGenEventWrite_EventWriteTransfer
0x180062c37  mov     eax, 80070057h
0x180062c3c  jmp     loc_180062A6F
0x180062c41  cmp     ax, [rbx+28h]
0x180062c45  jz      loc_1800628B7
0x180062c4b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180062c52  lea     r8, [rbp+410h+Buffer]; lpBuffer
0x180062c56  mov     r9d, 200h; cchBufferMax
0x180062c5c  mov     edx, 12Dh; uID
0x180062c61  call    cs:__imp_LoadStringW
0x180062c67  test    eax, eax
0x180062c69  jz      loc_180062EAC
0x180062c6f  lea     rcx, [rbp+410h+Buffer]; psz
0x180062c73  call    cs:__imp_SysAllocString
0x180062c79  mov     [rbp+410h+var_470], rax
0x180062c7d  mov     rbx, rax
0x180062c80  test    rax, rax
0x180062c83  jnz     loc_180062FF2
0x180062c89  mov     r13d, 8007000Eh
0x180062c8f  test    r13d, r13d
0x180062c92  jns     loc_180062FFA
0x180062c98  mov     rcx, r15; struct IUnknown *
0x180062c9b  call    ?GetProviderInfo@@YAPEAGPEAUIUnknown@@@Z; GetProviderInfo(IUnknown *)
0x180062ca0  mov     rdi, rax
0x180062ca3  mov     [rsp+510h+var_4C8], rax
0x180062ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180062caf  lea     r12, WPP_GLOBAL_Control
0x180062cb6  lea     r14, word_180313900
0x180062cbd  cmp     rcx, r12
0x180062cc0  jnz     loc_180063009
0x180062cc6  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 1
0x180062ccd  jnz     loc_180063053
0x180062cd3  lea     rcx, [rsp+510h+var_4C8]
0x180062cd8  call    ?SafeRelease@?$AutoCleanupInfo@PEAG@@SAXAEAPEAG@Z; AutoCleanupInfo<ushort *>::SafeRelease(ushort * &)
0x180062cdd  lea     rcx, [rbp+410h+var_470]
0x180062ce1  call    ?SafeRelease@?$AutoCleanupInfo@PEAG@@SAXAEAPEAG@Z; AutoCleanupInfo<ushort *>::SafeRelease(ushort * &)
0x180062ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ced  cmp     rcx, r12
0x180062cf0  jmp     loc_180062BED
0x180062cf5  mov     rcx, [rbp+418h]; this
0x180062cfc  lea     r8, aOnecoreWindows_45; "onecore\\windows\\accessibletech\\uiaut"...
0x180062d03  mov     r9d, ebx; char *
0x180062d06  mov     edx, 174h; void *
0x180062d0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d17  lea     r12, WPP_GLOBAL_Control
0x180062d1e  cmp     rcx, r12
0x180062d21  jz      short loc_180062D47
0x180062d23  test    byte ptr [rcx+1Ch], 10h
0x180062d27  jz      short loc_180062D47
  ... truncated ...
```
