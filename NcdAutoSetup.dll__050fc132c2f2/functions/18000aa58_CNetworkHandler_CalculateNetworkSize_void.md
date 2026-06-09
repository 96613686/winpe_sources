# CNetworkHandler::CalculateNetworkSize(void)

- ea: `0x18000aa58`
- end: `0x18000b1df`
- name: `?CalculateNetworkSize@CNetworkHandler@@QEAAJXZ`
- size: `1927`
- prototype: `__int64 __fastcall(CNetworkHandler *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000b1e8`
- `0x180010120`

## callees

- `0x1800079e0`
- `0x180008034`
- `0x18000a4b0`
- `0x18000a644`
- `0x18000a778`
- `0x18000aa58`
- `0x1800111f4`
- `0x180013840`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x18000b16a`
- `ntdll!WinSqmAddToStreamEx` at `0x18000b16a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af44`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ab77`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ab84`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ab8e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000af05`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000b03d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ab77`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ab84`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ab8e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000af05`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000b03d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ab61`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000aebf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b07d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ab61`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000aebf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b07d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b086`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b086`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000affa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000affa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ac24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ac24`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000add3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000add3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000accb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ace5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b0cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000accb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ace5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b0cf`

## pseudocode

```c
__int64 __fastcall CNetworkHandler::CalculateNetworkSize(CNetworkHandler *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // r14d
  int v6; // esi
  int v7; // ebx
  __int64 v8; // r8
  _BYTE *v9; // rcx
  __int64 v10; // rdx
  signed int started; // ebx
  signed int LastError; // eax
  int v13; // esi
  __int64 **v14; // r12
  _QWORD *v15; // rcx
  __int64 *i; // rax
  DWORD v17; // eax
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  signed int v21; // eax
  _QWORD *v22; // rcx
  ULONGLONG v23; // rdi
  ULONGLONG TickCount64; // [rsp+30h] [rbp-68h] BYREF
  int v25; // [rsp+38h] [rbp-60h]
  int v26; // [rsp+3Ch] [rbp-5Ch]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  v4 = 0;
  if ( (unsigned int)SMIsShuttingDown() )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    return 2147500036LL;
  }
  v6 = 0;
  if ( (Microsoft_Windows_NcdAutoSetupEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v2, NetworkSizeCalculationStart, v3, 1, &TickCount64);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( *((_DWORD *)this + 18) )
  {
    v7 = 1;
  }
  else
  {
    v7 = 0;
    if ( *((_DWORD *)this + 16) )
    {
      *((_DWORD *)this + 17) = 1;
      SetEvent(g_ahNetworkSizeCalculationCancelEvents);
    }
    else
    {
      *((_DWORD *)this + 16) = 1;
      v6 = 1;
      ResetEvent(g_ahNetworkSizeCalculationCancelEvents);
      ResetEvent(*(&g_ahNetworkSizeCalculationCancelEvents + 1));
      ResetEvent(*((HANDLE *)this + 7));
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || (v9[28] & 8) == 0 )
      goto LABEL_27;
    v10 = 69;
    goto LABEL_26;
  }
  if ( !v6 )
  {
    started = 0;
    if ( v9 != (_BYTE *)&WPP_GLOBAL_Control && (v9[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)v9 + 2), 70, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    if ( WaitForSingleObject(*((HANDLE *)this + 7), 0xFFFFFFFF) )
    {
      LastError = GetLastError();
      started = LastError;
      if ( LastError > 0 )
        started = (unsigned __int16)LastError | 0x80070000;
      if ( started >= 0 )
        started = -2147467259;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_41;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    }
    v9 = WPP_GLOBAL_Control;
LABEL_41:
    if ( !*((_DWORD *)this + 18) )
    {
      if ( v9 != (_BYTE *)&WPP_GLOBAL_Control && (v9[28] & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)v9 + 2), 73, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
        goto LABEL_120;
      }
      goto LABEL_121;
    }
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || (v9[28] & 8) == 0 )
    {
LABEL_27:
      started = -2147467260;
      goto LABEL_121;
    }
    v10 = 72;
LABEL_26:
    WPP_SF_(*((_QWORD *)v9 + 2), v10, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    v9 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  v13 = 0;
  TickCount64 = GetTickCount64();
  v14 = (__int64 **)((char *)this + 80);
  while ( 1 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
        v15 = WPP_GLOBAL_Control;
      }
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x20) != 0 )
        WPP_SF_(v15[2], 142, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    for ( i = *v14; i != (__int64 *)v14; i = (__int64 *)*i )
      *((_DWORD *)i + 10) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    started = CDeviceHandler::StartDiscovery(*((CDeviceHandler **)this + 6));
    if ( started < 0 )
      break;
    g_dwCurrentAutoSetupCount = 0;
    v17 = WaitForMultipleObjectsEx(
            2u,
            &g_ahNetworkSizeCalculationCancelEvents,
            0,
            1000 * g_dwNetworkSizeCalculationTimeout,
            0);
    if ( v17 == 258 || v17 == 1 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
        v22 = WPP_GLOBAL_Control;
      }
      v4 = 1;
      if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 8) != 0 )
        WPP_SF_(v22[2], 76, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
      v13 = 0;
      if ( *((_DWORD *)this + 17) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
        *((_DWORD *)this + 17) = 0;
        ResetEvent(g_ahNetworkSizeCalculationCancelEvents);
        v13 = 1;
      }
      else
      {
        *((_DWORD *)this + 16) = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
        SetEvent(*((HANDLE *)this + 7));
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v20 = 79;
        goto LABEL_112;
      }
    }
    else
    {
      v4 = 0;
      if ( v17 )
      {
        v21 = GetLastError();
        started = v21;
        if ( v21 > 0 )
          started = (unsigned __int16)v21 | 0x80070000;
        if ( started >= 0 )
          started = -2147467259;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
            v18 = WPP_GLOBAL_Control;
          }
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
            WPP_SF_(v18[2], 81, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
        }
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
        if ( *((_DWORD *)this + 18) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
          *((_DWORD *)this + 16) = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
          SetEvent(*((HANDLE *)this + 7));
          started = -2147467260;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
          *((_DWORD *)this + 17) = 0;
          ResetEvent(g_ahNetworkSizeCalculationCancelEvents);
          v13 = 1;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v20 = 85;
LABEL_112:
          WPP_SF_(v19[2], v20, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
        }
      }
    }
    CDeviceHandler::StopDiscovery(*((CDeviceHandler **)this + 6));
    if ( started < 0 || !v13 )
      break;
    TickCount64 = GetTickCount64();
  }
  v23 = (GetTickCount64() - TickCount64) / 0x3E8;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    TickCount64 = 0x100000010LL;
    v26 = 0;
    v25 = v23;
    WinSqmAddToStreamEx(0, 7551, 1, &TickCount64, 0);
LABEL_120:
    v9 = WPP_GLOBAL_Control;
  }
LABEL_121:
  if ( (Microsoft_Windows_NcdAutoSetupEnableBits & 2) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(v9, NetworkSizeCalculationStop, v8, 1, &TickCount64);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (_BYTE *)&WPP_GLOBAL_Control && (v9[28] & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)v9 + 2), 88, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000aa58  push    rbx
0x18000aa5a  push    rbp
0x18000aa5b  push    rsi
0x18000aa5c  push    rdi
0x18000aa5d  push    r12
0x18000aa5f  push    r13
0x18000aa61  push    r14
0x18000aa63  push    r15
0x18000aa65  sub     rsp, 58h
0x18000aa69  mov     rax, cs:__security_cookie
0x18000aa70  xor     rax, rsp
0x18000aa73  mov     [rsp+98h+var_58], rax
0x18000aa78  mov     rdi, rcx
0x18000aa7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa82  lea     r12, WPP_GLOBAL_Control
0x18000aa89  lea     r13, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000aa90  cmp     rcx, r12
0x18000aa93  jz      short loc_18000AAAC
0x18000aa95  test    byte ptr [rcx+1Ch], 20h
0x18000aa99  jz      short loc_18000AAAC
0x18000aa9b  mov     rcx, [rcx+10h]
0x18000aa9f  mov     edx, 41h ; 'A'
0x18000aaa4  mov     r8, r13
0x18000aaa7  call    WPP_SF_
0x18000aaac  call    ?SMIsShuttingDown@@YAHXZ; SMIsShuttingDown(void)
0x18000aab1  xor     r14d, r14d
0x18000aab4  test    eax, eax
0x18000aab6  jz      short loc_18000AAE4
0x18000aab8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aabf  cmp     rcx, r12
0x18000aac2  jz      short loc_18000AADA
0x18000aac4  test    byte ptr [rcx+1Ch], 4
0x18000aac8  jz      short loc_18000AADA
0x18000aaca  mov     rcx, [rcx+10h]
0x18000aace  lea     edx, [r14+42h]
0x18000aad2  mov     r8, r13
0x18000aad5  call    WPP_SF_
0x18000aada  mov     eax, 80004004h
0x18000aadf  jmp     loc_18000B1C1
0x18000aae4  test    cs:Microsoft_Windows_NcdAutoSetupEnableBits, 2
0x18000aaeb  mov     esi, r14d
0x18000aaee  mov     r15d, 1
0x18000aaf4  jz      short loc_18000AB0F
0x18000aaf6  lea     rax, [rsp+98h+var_68]
0x18000aafb  mov     r9d, r15d
0x18000aafe  lea     rdx, NetworkSizeCalculationStart
0x18000ab05  mov     qword ptr [rsp+98h+bAlertable], rax
0x18000ab0a  call    McGenEventWrite_EventWriteTransfer
0x18000ab0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab16  cmp     rcx, r12
0x18000ab19  jz      short loc_18000AB32
0x18000ab1b  test    byte ptr [rcx+1Ch], 8
0x18000ab1f  jz      short loc_18000AB32
0x18000ab21  mov     rcx, [rcx+10h]
0x18000ab25  mov     edx, 43h ; 'C'
0x18000ab2a  mov     r8, r13
0x18000ab2d  call    WPP_SF_
0x18000ab32  lea     rbp, [rdi+88h]
0x18000ab39  mov     rcx, rbp; lpCriticalSection
0x18000ab3c  call    cs:__imp_EnterCriticalSection
0x18000ab42  cmp     [rdi+48h], r14d
0x18000ab46  jz      short loc_18000AB4D
0x18000ab48  mov     ebx, r15d
0x18000ab4b  jmp     short loc_18000AB94
0x18000ab4d  mov     ebx, r14d
0x18000ab50  cmp     [rdi+40h], r14d
0x18000ab54  jz      short loc_18000AB69
0x18000ab56  mov     [rdi+44h], r15d
0x18000ab5a  mov     rcx, qword ptr cs:?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA; hEvent
0x18000ab61  call    cs:__imp_SetEvent
0x18000ab67  jmp     short loc_18000AB94
0x18000ab69  mov     [rdi+40h], r15d
0x18000ab6d  mov     esi, r15d
0x18000ab70  mov     rcx, qword ptr cs:?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA; hEvent
0x18000ab77  call    cs:__imp_ResetEvent
0x18000ab7d  mov     rcx, qword ptr cs:?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA+8; hEvent
0x18000ab84  call    cs:__imp_ResetEvent
0x18000ab8a  mov     rcx, [rdi+38h]; hEvent
0x18000ab8e  call    cs:__imp_ResetEvent
0x18000ab94  mov     rcx, rbp; lpCriticalSection
0x18000ab97  call    cs:__imp_LeaveCriticalSection
0x18000ab9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aba4  cmp     rcx, r12
0x18000aba7  jz      short loc_18000ABC7
0x18000aba9  test    byte ptr [rcx+1Ch], 8
0x18000abad  jz      short loc_18000ABC7
0x18000abaf  mov     rcx, [rcx+10h]
0x18000abb3  mov     edx, 44h ; 'D'
0x18000abb8  mov     r8, r13
0x18000abbb  call    WPP_SF_
0x18000abc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abc7  test    ebx, ebx
0x18000abc9  jz      short loc_18000ABF8
0x18000abcb  cmp     rcx, r12
0x18000abce  jz      short loc_18000ABEE
0x18000abd0  test    byte ptr [rcx+1Ch], 8
0x18000abd4  jz      short loc_18000ABEE
0x18000abd6  mov     edx, 45h ; 'E'
0x18000abdb  mov     rcx, [rcx+10h]
0x18000abdf  mov     r8, r13
0x18000abe2  call    WPP_SF_
0x18000abe7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abee  mov     ebx, 80004004h
0x18000abf3  jmp     loc_18000B177
0x18000abf8  test    esi, esi
0x18000abfa  jnz     loc_18000ACC8
0x18000ac00  mov     ebx, r14d
0x18000ac03  cmp     rcx, r12
0x18000ac06  jz      short loc_18000AC1D
0x18000ac08  test    byte ptr [rcx+1Ch], 8
0x18000ac0c  jz      short loc_18000AC1D
0x18000ac0e  mov     rcx, [rcx+10h]
0x18000ac12  lea     edx, [rsi+46h]
0x18000ac15  mov     r8, r13
0x18000ac18  call    WPP_SF_
0x18000ac1d  mov     rcx, [rdi+38h]; hHandle
0x18000ac21  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ac24  call    cs:__imp_WaitForSingleObject
0x18000ac2a  test    eax, eax
0x18000ac2c  jz      short loc_18000AC75
0x18000ac2e  call    cs:__imp_GetLastError
0x18000ac34  mov     ebx, eax
0x18000ac36  test    eax, eax
0x18000ac38  jle     short loc_18000AC43
0x18000ac3a  movzx   ebx, ax
0x18000ac3d  or      ebx, 80070000h
0x18000ac43  test    ebx, ebx
0x18000ac45  mov     r15d, 80004005h
0x18000ac4b  cmovns  ebx, r15d
0x18000ac4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac56  cmp     rcx, r12
0x18000ac59  jz      short loc_18000AC7C
0x18000ac5b  test    byte ptr [rcx+1Ch], 2
0x18000ac5f  jz      short loc_18000AC7C
0x18000ac61  mov     rcx, [rcx+10h]
0x18000ac65  mov     edx, 47h ; 'G'
0x18000ac6a  mov     r9d, ebx
0x18000ac6d  mov     r8, r13
0x18000ac70  call    WPP_SF_d
0x18000ac75  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac7c  cmp     [rdi+48h], r14d
0x18000ac80  jz      short loc_18000AC9F
0x18000ac82  cmp     rcx, r12
0x18000ac85  jz      loc_18000ABEE
0x18000ac8b  test    byte ptr [rcx+1Ch], 8
0x18000ac8f  jz      loc_18000ABEE
0x18000ac95  mov     edx, 48h ; 'H'
0x18000ac9a  jmp     loc_18000ABDB
0x18000ac9f  cmp     rcx, r12
0x18000aca2  jz      loc_18000B177
0x18000aca8  test    byte ptr [rcx+1Ch], 8
0x18000acac  jz      loc_18000B177
0x18000acb2  mov     rcx, [rcx+10h]
0x18000acb6  mov     edx, 49h ; 'I'
0x18000acbb  mov     r8, r13
0x18000acbe  call    WPP_SF_
0x18000acc3  jmp     loc_18000B170
0x18000acc8  mov     esi, r14d
0x18000accb  call    cs:__imp_GetTickCount64
0x18000acd1  mov     [rsp+98h+var_68], rax
0x18000acd6  lea     r12, [rdi+50h]
0x18000acda  mov     r15d, 80004005h
0x18000ace0  test    r14d, r14d
0x18000ace3  jz      short loc_18000ACF0
0x18000ace5  call    cs:__imp_GetTickCount64
0x18000aceb  mov     [rsp+98h+var_68], rax
0x18000acf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acf7  lea     rbx, WPP_GLOBAL_Control
0x18000acfe  cmp     rcx, rbx
0x18000ad01  jz      short loc_18000AD45
0x18000ad03  test    byte ptr [rcx+1Ch], 8
0x18000ad07  jz      short loc_18000AD25
0x18000ad09  mov     rcx, [rcx+10h]
0x18000ad0d  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000ad14  mov     edx, 4Ah ; 'J'
0x18000ad19  call    WPP_SF_
0x18000ad1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad25  cmp     rcx, rbx
0x18000ad28  jz      short loc_18000AD45
0x18000ad2a  test    byte ptr [rcx+1Ch], 20h
0x18000ad2e  jz      short loc_18000AD45
0x18000ad30  mov     rcx, [rcx+10h]
0x18000ad34  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000ad3b  mov     edx, 8Eh
0x18000ad40  call    WPP_SF_
0x18000ad45  lea     rcx, [rdi+60h]; lpCriticalSection
0x18000ad49  call    cs:__imp_EnterCriticalSection
0x18000ad4f  mov     rax, [r12]
0x18000ad53  jmp     short loc_18000AD5F
0x18000ad55  mov     dword ptr [rax+28h], 0
0x18000ad5c  mov     rax, [rax]
0x18000ad5f  cmp     rax, r12
0x18000ad62  jnz     short loc_18000AD55
0x18000ad64  lea     rcx, [rdi+60h]; lpCriticalSection
0x18000ad68  call    cs:__imp_LeaveCriticalSection
0x18000ad6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad75  cmp     rcx, rbx
0x18000ad78  jz      short loc_18000AD95
0x18000ad7a  test    byte ptr [rcx+1Ch], 20h
0x18000ad7e  jz      short loc_18000AD95
0x18000ad80  mov     rcx, [rcx+10h]
0x18000ad84  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000ad8b  mov     edx, 8Fh
0x18000ad90  call    WPP_SF_
0x18000ad95  mov     rcx, [rdi+30h]; this
0x18000ad99  call    ?StartDiscovery@CDeviceHandler@@QEAAJXZ; CDeviceHandler::StartDiscovery(void)
0x18000ad9e  mov     ebx, eax
0x18000ada0  test    eax, eax
0x18000ada2  js      loc_18000B0CF
0x18000ada8  imul    r9d, cs:?g_dwNetworkSizeCalculationTimeout@@3KA, 3E8h; dwMilliseconds
0x18000adb3  lea     rdx, ?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA; lpHandles
0x18000adba  xor     r8d, r8d; bWaitAll
0x18000adbd  mov     cs:?g_dwCurrentAutoSetupCount@@3KA, 0; ulong g_dwCurrentAutoSetupCount
0x18000adc7  mov     [rsp+98h+bAlertable], 0; bAlertable
0x18000adcf  lea     ecx, [r8+2]; nCount
0x18000add3  call    cs:__imp_WaitForMultipleObjectsEx
0x18000add9  cmp     eax, 102h
0x18000adde  jz      loc_18000AF9D
0x18000ade4  cmp     eax, 1
0x18000ade7  jz      loc_18000AF9D
0x18000aded  xor     r14d, r14d
0x18000adf0  test    eax, eax
0x18000adf2  jnz     loc_18000AF44
0x18000adf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adff  lea     rax, WPP_GLOBAL_Control
0x18000ae06  cmp     rcx, rax
0x18000ae09  jz      short loc_18000AE53
0x18000ae0b  test    byte ptr [rcx+1Ch], 8
0x18000ae0f  jz      short loc_18000AE33
0x18000ae11  mov     rcx, [rcx+10h]
0x18000ae15  lea     edx, [r14+50h]
0x18000ae19  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000ae20  call    WPP_SF_
0x18000ae25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae2c  lea     rax, WPP_GLOBAL_Control
0x18000ae33  cmp     rcx, rax
0x18000ae36  jz      short loc_18000AE53
0x18000ae38  test    byte ptr [rcx+1Ch], 8
0x18000ae3c  jz      short loc_18000AE53
0x18000ae3e  mov     rcx, [rcx+10h]
0x18000ae42  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000ae49  mov     edx, 51h ; 'Q'
0x18000ae4e  call    WPP_SF_
0x18000ae53  mov     rcx, rbp; lpCriticalSection
0x18000ae56  call    cs:__imp_EnterCriticalSection
0x18000ae5c  cmp     [rdi+48h], r14d
0x18000ae60  jz      short loc_18000AECC
0x18000ae62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae69  lea     rbx, WPP_GLOBAL_Control
0x18000ae70  cmp     rcx, rbx
0x18000ae73  jz      short loc_18000AE90
0x18000ae75  test    byte ptr [rcx+1Ch], 8
0x18000ae79  jz      short loc_18000AE90
0x18000ae7b  mov     rcx, [rcx+10h]
0x18000ae7f  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000ae86  mov     edx, 52h ; 'R'
0x18000ae8b  call    WPP_SF_
0x18000ae90  mov     [rdi+40h], r14d
0x18000ae94  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae9b  cmp     rcx, rbx
0x18000ae9e  jz      short loc_18000AEBB
0x18000aea0  test    byte ptr [rcx+1Ch], 8
0x18000aea4  jz      short loc_18000AEBB
0x18000aea6  mov     rcx, [rcx+10h]
0x18000aeaa  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000aeb1  mov     edx, 53h ; 'S'
0x18000aeb6  call    WPP_SF_
0x18000aebb  mov     rcx, [rdi+38h]; hEvent
0x18000aebf  call    cs:__imp_SetEvent
0x18000aec5  mov     ebx, 80004004h
0x18000aeca  jmp     short loc_18000AF10
0x18000aecc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aed3  lea     rax, WPP_GLOBAL_Control
0x18000aeda  cmp     rcx, rax
0x18000aedd  jz      short loc_18000AEFA
0x18000aedf  test    byte ptr [rcx+1Ch], 8
0x18000aee3  jz      short loc_18000AEFA
0x18000aee5  mov     rcx, [rcx+10h]
0x18000aee9  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000aef0  mov     edx, 54h ; 'T'
0x18000aef5  call    WPP_SF_
0x18000aefa  mov     [rdi+44h], r14d
0x18000aefe  mov     rcx, qword ptr cs:?g_ahNetworkSizeCalculationCancelEvents@@3PAPEAXA; hEvent
0x18000af05  call    cs:__imp_ResetEvent
0x18000af0b  mov     esi, 1
0x18000af10  mov     rcx, rbp; lpCriticalSection
0x18000af13  call    cs:__imp_LeaveCriticalSection
0x18000af19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af20  lea     rax, WPP_GLOBAL_Control
0x18000af27  cmp     rcx, rax
0x18000af2a  jz      loc_18000B0BA
0x18000af30  test    byte ptr [rcx+1Ch], 8
0x18000af34  jz      loc_18000B0BA
0x18000af3a  mov     edx, 55h ; 'U'
0x18000af3f  jmp     loc_18000B0AA
0x18000af44  call    cs:__imp_GetLastError
0x18000af4a  mov     ebx, eax
0x18000af4c  test    eax, eax
0x18000af4e  jle     short loc_18000AF59
0x18000af50  movzx   ebx, ax
  ... truncated ...
```
