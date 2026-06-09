# CalaisHandlerEx

- ea: `0x1800144e0`
- end: `0x180014b22`
- name: `CalaisHandlerEx`
- size: `1602`
- prototype: `DWORD __fastcall(DWORD dwControl, DWORD dwEventType, char *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800022b0`
- `0x1800075d0`
- `0x1800136a0`
- `0x1800144e0`
- `0x180019bc4`
- `0x18001b304`
- `0x18001b3fc`
- `0x18001b7b0`
- `0x180023168`
- `0x180028b28`
- `0x180028bd4`
- `0x180028c50`
- `0x180029ea0`
- `0x18002a150`
- `0x18002a414`
- `0x18002a494`
- `0x18002a5c0`
- `0x18002a67c`
- `0x18003261b`
- `0x180032696`
- `0x180037010`

## import_xrefs

- `msvcrt!?set_terminate@@YAP6AXXZP6AXXZ@Z` at `0x180014507`
- `msvcrt!?set_terminate@@YAP6AXXZP6AXXZ@Z` at `0x180014507`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014a10`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014a10`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800145a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800145a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a70`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180014538`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001454a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180014538`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001454a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180014a66`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180014a66`

## string_xrefs

- `0x1800148ba`: `DBT_DEVICEQUERYREMOVE/dbch_handle`
- `0x18001486a`: `DBT_DEVICEQUERYREMOVEFAILED/dbch_handle`
- `0x1800147b4`: `DBT_DEVICEREMOVEPENDING/dbch_handle`
- `0x1800146f3`: `DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_HANDLE/dbch_handle`
- `0x18001470b`: `DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_HANDLE/dbch_hdevnotify`

## pseudocode

```c
DWORD __fastcall CalaisHandlerEx(DWORD dwControl, DWORD dwEventType, char *lpEventData, LPVOID lpContext)
{
  DWORD result; // eax
  __int64 v7; // rcx
  int v8; // edx
  int v9; // r8d
  const unsigned __int16 *v10; // r9
  unsigned __int8 *v11; // rcx
  DWORD v12; // r14d
  DWORD v13; // r14d
  DWORD v14; // r14d
  int v15; // r14d
  void *v16; // rcx
  char *v17; // rdx
  const unsigned __int8 *v18; // rcx
  const unsigned __int16 *v19; // r9
  const WCHAR *v20; // r14
  void *v21; // rcx
  unsigned __int16 *v22; // r14
  void *v23; // rcx
  const unsigned __int8 *v24; // rax
  __int64 v25; // r8
  unsigned __int16 *v26; // r15
  void *v27; // rcx
  const unsigned __int16 *v28; // r14
  unsigned int v29; // eax
  unsigned int v30; // eax
  DWORD LastError; // r8d
  const unsigned __int8 *v32; // rcx
  __int64 v33; // rcx
  DWORD v34; // r8d
  const unsigned __int8 *v35; // rcx
  int v36; // edx
  int v37; // r8d
  int v38; // r9d
  unsigned __int16 *v39; // [rsp+20h] [rbp-C8h]
  unsigned __int16 *v40; // [rsp+20h] [rbp-C8h]
  unsigned __int16 *v41; // [rsp+20h] [rbp-C8h]
  unsigned __int16 *v42; // [rsp+20h] [rbp-C8h]
  unsigned __int16 *v43; // [rsp+20h] [rbp-C8h]
  unsigned __int16 *v44; // [rsp+20h] [rbp-C8h]
  DWORD v45; // [rsp+30h] [rbp-B8h]
  ulong pExceptionObject; // [rsp+34h] [rbp-B4h] BYREF
  ulong v47; // [rsp+38h] [rbp-B0h] BYREF
  const unsigned __int16 *v48; // [rsp+40h] [rbp-A8h]
  CCriticalSectionObject *v49; // [rsp+48h] [rbp-A0h]
  void **v50; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int16 *v51; // [rsp+58h] [rbp-90h]
  __int64 v52; // [rsp+60h] [rbp-88h]
  void **v53; // [rsp+70h] [rbp-78h] BYREF
  int v54; // [rsp+78h] [rbp-70h]
  void **v55; // [rsp+80h] [rbp-68h]
  __int64 v56; // [rsp+88h] [rbp-60h]
  __int64 v57; // [rsp+90h] [rbp-58h]
  void **v58; // [rsp+98h] [rbp-50h]
  __int64 v59; // [rsp+A0h] [rbp-48h]
  __int64 v60; // [rsp+A8h] [rbp-40h]
  ulong v61; // [rsp+B0h] [rbp-38h] BYREF
  ulong v62; // [rsp+B4h] [rbp-34h] BYREF
  ulong v63; // [rsp+B8h] [rbp-30h] BYREF
  ulong v64; // [rsp+BCh] [rbp-2Ch] BYREF
  ulong v65; // [rsp+C4h] [rbp-24h] BYREF
  ulong v66; // [rsp+C8h] [rbp-20h] BYREF

  set_terminate(CalaisTerminate);
  if ( _InterlockedExchange((volatile __int32 *)&g_fBlockServiceHandler, 1) )
    return 1115;
  if ( !TlsSetValue(dwTlsIndex, (LPVOID)_InterlockedIncrement(&dword_18004BF90)) || !TlsSetValue(dword_18004B240, 0) )
  {
    result = GetLastError();
    if ( result )
    {
      _InterlockedExchange((volatile __int32 *)&g_fBlockServiceHandler, 0);
      return result;
    }
  }
  v49 = qword_18004BD38;
  (**(void (__fastcall ***)(CCriticalSectionObject *, _QWORD, _QWORD))qword_18004BD38)(qword_18004BD38, 0, 0);
  if ( !g_hCalaisShutdown || (v45 = 0, !WaitForSingleObject(g_hCalaisShutdown, 0)) )
  {
    _InterlockedExchange((volatile __int32 *)&g_fBlockServiceHandler, 0);
    (*(void (__fastcall **)(CCriticalSectionObject *))(*(_QWORD *)v49 + 8LL))(v49);
    return 1115;
  }
  try
  {
    switch ( dwControl )
    {
      case 0xDu:
        goto LABEL_93;
      case 1u:
        ServiceStatus.dwCurrentState = 3;
        ServiceStatus.dwCheckPoint = 0;
        ServiceStatus.dwWaitHint = 30000;
        if ( !SetEvent(hEvent) )
        {
          LastError = GetLastError();
          CalaisError(v32, 0x204u, LastError, 0, 0, 0);
        }
        goto LABEL_93;
      case 2u:
        ServiceStatus.dwCurrentState = 7;
        goto LABEL_93;
      case 3u:
        ServiceStatus.dwCurrentState = 4;
        goto LABEL_93;
    }
    if ( dwControl != 11 )
    {
      if ( dwControl == 14 && dwEventType - 5 <= 1 && (Microsoft_Windows_Smartcard_TriggerEnableBits & 1) != 0 )
        McTemplateU0j_EventWriteTransfer();
      goto LABEL_93;
    }
    v53 = &CTextString::`vftable';
    v55 = &CBuffer::`vftable';
    v56 = 0;
    v57 = 0;
    v58 = &CBuffer::`vftable';
    v59 = 0;
    v60 = 0;
    v54 = 3;
    WppTraceIndent(v7, 2);
    v11 = (unsigned __int8 *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sl(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, (_DWORD)v10, dwEventType);
    }
    v12 = dwEventType - 0x8000;
    if ( !v12 )
    {
      try
      {
        v48 = 0;
        if ( *((_DWORD *)lpEventData + 1) == 5 )
        {
          CTextString::operator=(&v53, lpEventData + 28);
          v28 = CTextString::Unicode((CTextString *)&v53);
          v48 = v28;
          if ( !memcmp_0(&GUID_DEVINTERFACE_SMARTCARD_READER, lpEventData + 12, 0x10u) )
          {
            v29 = CalaisAsyncAddReader(
                    (unsigned int (*)(const unsigned __int16 *, unsigned int))AddReaderDriver,
                    v28,
                    1u);
            if ( v29 )
            {
              pExceptionObject = v29;
              throw &pExceptionObject;
            }
          }
          else if ( !memcmp_0(&GUID_DEVINTERFACE_NGC_CONTAINER, lpEventData + 12, 0x10u) )
          {
            v30 = CalaisAsyncAddReader((unsigned int (*)(const unsigned __int16 *, unsigned int))AddNgcReader, v28, 0);
            if ( v30 )
            {
              v47 = v30;
              throw &v47;
            }
          }
        }
      }
      catch ( ulong v61 )
      {
        CalaisError(v11, 0x202u, v61, v48, 0, 0);
        goto LABEL_71;
      }
      catch ( ... )
      {
        CalaisError(v11, 0x205u, v48, v10, v43);
        goto LABEL_71;
      }
      goto LABEL_71;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      try
      {
        if ( *((_DWORD *)lpEventData + 1) == 6 )
        {
          v27 = (void *)*((_QWORD *)lpEventData + 2);
          if ( v27 )
          {
            CalaisDisableReader(v27);
          }
          else
          {
            CalaisError(0, 0x20Bu, L"DBT_DEVICEQUERYREMOVE/dbch_handle", v10, v44);
            v45 = 2404;
          }
        }
        else
        {
          v45 = 1;
        }
      }
      catch ( ulong v62 )
      {
        v45 = 2404;
        goto LABEL_71;
      }
      catch ( ... )
      {
        CalaisError(v11, 0x20Au, L"DBT_DEVICEQUERYREMOVE", v10, v42);
        v45 = 2404;
        goto LABEL_71;
      }
      goto LABEL_71;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      try
      {
        v50 = &CBuffer::`vftable';
        v22 = 0;
        v51 = 0;
        v52 = 0;
        if ( *((_DWORD *)lpEventData + 1) == 6 )
        {
          v23 = (void *)*((_QWORD *)lpEventData + 2);
          if ( v23 )
          {
            v24 = (const unsigned __int8 *)CalaisConfirmClosingReader(v23);
            if ( v24 )
            {
              v25 = -1;
              do
                ++v25;
              while ( *(_WORD *)&v24[2 * v25] );
              CBuffer::Set((CBuffer *)&v50, v24, 2 * v25 + 2);
              v26 = (unsigned __int16 *)&Data;
              v22 = v51;
              if ( HIDWORD(v52) )
                v26 = v51;
              v11 = (unsigned __int8 *)*((_QWORD *)lpEventData + 3);
              if ( v11 )
              {
                CalaisRemoveReader(v11);
                if ( v26 )
                  CalaisAddReader((unsigned int (*)(const unsigned __int16 *, unsigned int))AddReaderDriver, v26, 1u);
              }
            }
          }
          else
          {
            CalaisError(0, 0x209u, L"DBT_DEVICEQUERYREMOVEFAILED/dbch_handle", v10, v44);
          }
        }
      }
      catch ( ulong v63 )
      {
        v22 = v51;
      }
      catch ( ... )
      {
        CalaisError(v11, 0x201u, L"DBT_DEVICEQUERYREMOVEFAILED", v10, v41);
        v22 = v51;
      }
      if ( v22 )
        operator delete[](v22);
      goto LABEL_71;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      try
      {
        if ( *((_DWORD *)lpEventData + 1) == 6 )
        {
          v21 = (void *)*((_QWORD *)lpEventData + 2);
          if ( v21 )
            CalaisDisableReader(v21);
          else
            CalaisError(0, 0x200u, L"DBT_DEVICEREMOVEPENDING/dbch_handle", v10, v44);
        }
      }
      catch ( ulong v64 )
      {
        goto LABEL_71;
      }
      catch ( ... )
      {
        CalaisError(v11, 0x1FFu, L"DBT_DEVICEREMOVEPENDING", v10, v40);
        goto LABEL_71;
      }
      goto LABEL_71;
    }
    if ( v15 == 1 )
    {
      if ( *((_DWORD *)lpEventData + 1) == 5 )
      {
        v17 = lpEventData + 28;
        if ( *((_WORD *)lpEventData + 15) )
        {
          CTextString::operator=(&v53, v17);
        }
        else
        {
          try
          {
            CTextString::operator=(&v53, v17);
          }
          catch ( ulong v65 )
          {
            goto LABEL_71;
          }
          catch ( ... )
          {
            CalaisError(v18, 0x1FCu, L"DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_DEVICEINTERFACE", v19, v39);
            goto LABEL_71;
          }
        }
        v20 = CTextString::Unicode((CTextString *)&v53);
        if ( !memcmp_0(&GUID_DEVINTERFACE_SMARTCARD_READER, lpEventData + 12, 0x10u)
          || !memcmp_0(&GUID_DEVINTERFACE_NGC_CONTAINER, lpEventData + 12, 0x10u) )
        {
          CalaisRemoveDevice(v20);
        }
        goto LABEL_71;
      }
      if ( *((_DWORD *)lpEventData + 1) == 6 )
      {
        v16 = (void *)*((_QWORD *)lpEventData + 2);
        if ( v16 )
        {
          if ( *((_QWORD *)lpEventData + 3) )
          {
            CalaisDisableReader(v16);
            CalaisRemoveReader(*((void **)lpEventData + 3));
            goto LABEL_71;
          }
        }
        else
        {
          CalaisError(0, 0x1FEu, L"DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_HANDLE/dbch_handle", v10, v44);
          if ( *((_QWORD *)lpEventData + 3) )
            goto LABEL_71;
        }
        CalaisError(
          (const unsigned __int8 *)v16,
          0x207u,
          L"DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_HANDLE/dbch_hdevnotify",
          v10,
          v44);
      }
    }
LABEL_71:
    CTextString::~CTextString((CTextString *)&v53);
  }
  catch ( ulong v66 )
  {
  }
  catch ( ... )
  {
  }
LABEL_93:
  ServiceStatus.dwWin32ExitCode = v45;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    v34 = GetLastError();
    CalaisError(v35, 0x203u, v34, 0, 0, 0);
  }
  WppTraceIndent(v33, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_slD(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, v37, v38, dwControl, v45);
  }
  _InterlockedExchange((volatile __int32 *)&g_fBlockServiceHandler, 0);
  (*(void (__fastcall **)(CCriticalSectionObject *))(*(_QWORD *)v49 + 8LL))(v49);
  return v45;
}

```

## disassembly

```asm
0x1800144e0  mov     [rsp+arg_8], rbx
0x1800144e5  mov     [rsp+arg_10], rsi
0x1800144ea  mov     [rsp+arg_0], ecx
0x1800144ee  push    rdi
0x1800144ef  push    r14
0x1800144f1  push    r15
0x1800144f3  sub     rsp, 0D0h
0x1800144fa  mov     rsi, r8
0x1800144fd  mov     r14d, edx
0x180014500  lea     rcx, ?CalaisTerminate@@YAXXZ; CalaisTerminate(void)
0x180014507  call    cs:__imp_?set_terminate@@YAP6AXXZP6AXXZ@Z; set_terminate(void (*)(void))
0x18001450d  mov     eax, 1
0x180014512  xchg    eax, cs:?g_fBlockServiceHandler@@3KA; ulong g_fBlockServiceHandler
0x180014518  test    eax, eax
0x18001451a  jnz     loc_180014B04
0x180014520  mov     eax, 1
0x180014525  lock xadd cs:dword_18004BF90, eax
0x18001452d  inc     eax
0x18001452f  movsxd  rdx, eax; lpTlsValue
0x180014532  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180014538  call    cs:__imp_TlsSetValue
0x18001453e  test    eax, eax
0x180014540  jz      short loc_180014554
0x180014542  xor     edx, edx; lpTlsValue
0x180014544  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18001454a  call    cs:__imp_TlsSetValue
0x180014550  test    eax, eax
0x180014552  jnz     short loc_18001456B
0x180014554  call    cs:__imp_GetLastError
0x18001455a  test    eax, eax
0x18001455c  jz      short loc_18001456B
0x18001455e  xor     ebx, ebx
0x180014560  xchg    ebx, cs:?g_fBlockServiceHandler@@3KA; ulong g_fBlockServiceHandler
0x180014566  jmp     loc_180014B09
0x18001456b  mov     rcx, cs:qword_18004BD38
0x180014572  mov     [rsp+0E8h+var_A0], rcx
0x180014577  mov     rax, [rcx]
0x18001457a  xor     r8d, r8d
0x18001457d  xor     edx, edx
0x18001457f  mov     rax, [rax]
0x180014582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014587  nop
0x180014588  mov     rcx, cs:?g_hCalaisShutdown@@3PEAXEA; hHandle
0x18001458f  xor     ebx, ebx
0x180014591  test    rcx, rcx
0x180014594  jz      loc_180014AEC
0x18001459a  mov     [rsp+0E8h+var_B8], ebx
0x18001459e  xor     edx, edx; dwMilliseconds
0x1800145a0  call    cs:__imp_WaitForSingleObject
0x1800145a6  test    eax, eax
0x1800145a8  jz      loc_180014AEC
0x1800145ae  mov     eax, [rsp+0E8h+arg_0]
0x1800145b5  cmp     eax, 0Dh
0x1800145b8  jz      loc_180014A3A
0x1800145be  sub     eax, 1
0x1800145c1  jz      loc_1800149EF
0x1800145c7  sub     eax, 1
0x1800145ca  jz      loc_1800149E3
0x1800145d0  sub     eax, 1
0x1800145d3  jz      loc_1800149D7
0x1800145d9  sub     eax, 8
0x1800145dc  jz      short loc_18001460B
0x1800145de  cmp     eax, 3
0x1800145e1  jnz     loc_180014A3A
0x1800145e7  lea     eax, [r14-5]
0x1800145eb  cmp     eax, 1
0x1800145ee  ja      loc_180014A3A
0x1800145f4  test    cs:Microsoft_Windows_Smartcard_TriggerEnableBits, 1
0x1800145fb  jz      loc_180014A3A
0x180014601  call    McTemplateU0j_EventWriteTransfer
0x180014606  jmp     loc_180014A3A
0x18001460b  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180014612  mov     [rsp+0E8h+var_78], rax
0x180014617  lea     r15, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001461e  mov     [rsp+0E8h+var_68], r15
0x180014626  mov     [rsp+0E8h+var_60], rbx
0x18001462e  mov     [rsp+0E8h+var_58], rbx
0x180014636  mov     [rsp+0E8h+var_50], r15
0x18001463e  mov     [rsp+0E8h+var_48], rbx
0x180014646  mov     [rsp+0E8h+var_40], rbx
0x18001464e  mov     [rsp+0E8h+var_70], 3
0x180014656  mov     edx, 2
0x18001465b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180014660  lea     rdi, WPP_GLOBAL_Control
0x180014667  mov     rcx, cs:WPP_GLOBAL_Control
0x18001466e  cmp     rcx, rdi
0x180014671  jz      short loc_18001468D
0x180014673  test    byte ptr [rcx+1Ch], 8
0x180014677  jz      short loc_18001468D
0x180014679  cmp     byte ptr [rcx+19h], 4
0x18001467d  jb      short loc_18001468D
0x18001467f  mov     dword ptr [rsp+0E8h+var_C8], r14d; unsigned __int16 *
0x180014684  mov     rcx, [rcx+10h]
0x180014688  call    WPP_SF_sl
0x18001468d  sub     r14d, 8000h
0x180014694  jz      loc_1800148EC
0x18001469a  sub     r14d, 1
0x18001469e  jz      loc_1800148A4
0x1800146a4  sub     r14d, 1
0x1800146a8  jz      loc_1800147D4
0x1800146ae  sub     r14d, 1
0x1800146b2  jz      loc_18001479E
0x1800146b8  cmp     r14d, 1
0x1800146bc  jnz     loc_1800149CB
0x1800146c2  mov     ecx, [rsi+4]
0x1800146c5  sub     ecx, 5
0x1800146c8  jz      short loc_180014722
0x1800146ca  cmp     ecx, r14d
0x1800146cd  jnz     loc_180014794
0x1800146d3  mov     rcx, [rsi+10h]; unsigned __int8 *
0x1800146d7  test    rcx, rcx
0x1800146da  jz      short loc_1800146F3
0x1800146dc  cmp     qword ptr [rsi+18h], 0
0x1800146e1  jz      short loc_18001470B
0x1800146e3  call    ?CalaisDisableReader@@YAPEBGPEAX@Z; CalaisDisableReader(void *)
0x1800146e8  mov     rcx, [rsi+18h]; void *
0x1800146ec  call    ?CalaisRemoveReader@@YAKPEAX@Z; CalaisRemoveReader(void *)
0x1800146f1  jmp     short loc_18001471C
0x1800146f3  lea     r8, aDbtDeviceremov_1; "DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_HAN"...
0x1800146fa  mov     edx, 1FEh; unsigned int
0x1800146ff  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x180014704  cmp     qword ptr [rsi+18h], 0
0x180014709  jnz     short loc_18001471C
0x18001470b  lea     r8, aDbtDeviceremov_4; "DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_HAN"...
0x180014712  mov     edx, 207h; unsigned int
0x180014717  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18001471c  jmp     short loc_180014787
0x18001471e  jmp     short loc_18001478B
0x180014720  jmp     short loc_18001478B
0x180014722  lea     rdx, [rsi+1Ch]
0x180014726  lea     rcx, [rsp+0E8h+var_78]
0x18001472b  cmp     bx, [rsi+1Eh]
0x18001472f  jnz     short loc_180014738
0x180014731  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x180014736  jmp     short loc_18001473D
0x180014738  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x18001473d  lea     rcx, [rsp+0E8h+var_78]; this
0x180014742  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180014747  mov     r14, rax
0x18001474a  mov     r8d, 10h; Size
0x180014750  lea     rdx, [rsi+0Ch]; Buf2
0x180014754  lea     rcx, GUID_DEVINTERFACE_SMARTCARD_READER; Buf1
0x18001475b  call    memcmp_0
0x180014760  test    eax, eax
0x180014762  jz      short loc_18001477E
0x180014764  mov     r8d, 10h; Size
0x18001476a  lea     rdx, [rsi+0Ch]; Buf2
0x18001476e  lea     rcx, GUID_DEVINTERFACE_NGC_CONTAINER; Buf1
0x180014775  call    memcmp_0
0x18001477a  test    eax, eax
0x18001477c  jnz     short loc_180014787
0x18001477e  mov     rcx, r14; lpString1
0x180014781  call    ?CalaisRemoveDevice@@YAKPEBG@Z; CalaisRemoveDevice(ushort const *)
0x180014786  nop
0x180014787  jmp     short loc_180014794
0x180014789  jmp     short $+2
0x18001478b  lea     rdi, WPP_GLOBAL_Control
0x180014792  xor     ebx, ebx
0x180014794  jmp     loc_1800149BE
0x180014799  jmp     loc_1800149C2
0x18001479e  cmp     dword ptr [rsi+4], 6
0x1800147a2  jnz     short loc_1800147C5
0x1800147a4  mov     rcx, [rsi+10h]; unsigned __int8 *
0x1800147a8  test    rcx, rcx
0x1800147ab  jz      short loc_1800147B4
0x1800147ad  call    ?CalaisDisableReader@@YAPEBGPEAX@Z; CalaisDisableReader(void *)
0x1800147b2  jmp     short loc_1800147C5
0x1800147b4  lea     r8, aDbtDeviceremov_5; "DBT_DEVICEREMOVEPENDING/dbch_handle"
0x1800147bb  mov     edx, 200h; unsigned int
0x1800147c0  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x1800147c5  jmp     loc_1800149BE
0x1800147ca  jmp     loc_1800149C2
0x1800147cf  jmp     loc_1800149C2
0x1800147d4  mov     [rsp+0E8h+var_98], r15
0x1800147d9  mov     r14, rbx
0x1800147dc  mov     [rsp+0E8h+var_90], rbx
0x1800147e1  mov     [rsp+0E8h+var_88], rbx
0x1800147e6  cmp     dword ptr [rsi+4], 6
0x1800147ea  jnz     loc_18001487C
0x1800147f0  mov     rcx, [rsi+10h]; unsigned __int8 *
0x1800147f4  test    rcx, rcx
0x1800147f7  jz      short loc_18001486A
0x1800147f9  call    ?CalaisConfirmClosingReader@@YAPEBGPEAX@Z; CalaisConfirmClosingReader(void *)
0x1800147fe  test    rax, rax
0x180014801  jz      short loc_18001487C
0x180014803  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001480a  lea     r8, [r8+1]
0x18001480e  cmp     word ptr [rax+r8*2], 0
0x180014814  jnz     short loc_18001480A
0x180014816  lea     r8d, ds:2[r8*2]; unsigned int
0x18001481e  mov     rdx, rax; unsigned __int8 *
0x180014821  lea     rcx, [rsp+0E8h+var_98]; this
0x180014826  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18001482b  lea     r15, Data
0x180014832  mov     r14, [rsp+0E8h+var_90]
0x180014837  cmp     dword ptr [rsp+0E8h+var_88+4], 0
0x18001483c  cmova   r15, r14
0x180014840  mov     rcx, [rsi+18h]; void *
0x180014844  test    rcx, rcx
0x180014847  jz      short loc_18001487C
0x180014849  call    ?CalaisRemoveReader@@YAKPEAX@Z; CalaisRemoveReader(void *)
0x18001484e  test    r15, r15
0x180014851  jz      short loc_18001487C
0x180014853  mov     r8d, 1; unsigned int
0x180014859  mov     rdx, r15; unsigned __int16 *
0x18001485c  lea     rcx, ?AddReaderDriver@@YAKPEBGK@Z; unsigned int (*)(const unsigned __int16 *, unsigned int)
0x180014863  call    ?CalaisAddReader@@YAKP6AKPEBGK@Z0K@Z; CalaisAddReader(ulong (*)(ushort const *,ulong),ushort const *,ulong)
0x180014868  jmp     short loc_18001487C
0x18001486a  lea     r8, aDbtDevicequery_0; "DBT_DEVICEQUERYREMOVEFAILED/dbch_handle"
0x180014871  mov     edx, 209h; unsigned int
0x180014876  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18001487b  nop
0x18001487c  jmp     short loc_18001488E
0x18001487e  jmp     short $+2
0x180014880  mov     r14, [rsp+0E8h+var_90]
0x180014885  lea     rdi, WPP_GLOBAL_Control
0x18001488c  xor     ebx, ebx
0x18001488e  test    r14, r14
0x180014891  jz      loc_1800149CB
0x180014897  mov     rcx, r14; Block
0x18001489a  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001489f  jmp     loc_1800149CB
0x1800148a4  cmp     dword ptr [rsi+4], 6
0x1800148a8  jnz     short loc_1800148D5
0x1800148aa  mov     rcx, [rsi+10h]; unsigned __int8 *
0x1800148ae  test    rcx, rcx
0x1800148b1  jz      short loc_1800148BA
0x1800148b3  call    ?CalaisDisableReader@@YAPEBGPEAX@Z; CalaisDisableReader(void *)
0x1800148b8  jmp     short loc_1800148DD
0x1800148ba  lea     r8, aDbtDevicequery_2; "DBT_DEVICEQUERYREMOVE/dbch_handle"
0x1800148c1  mov     edx, 20Bh; unsigned int
0x1800148c6  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x1800148cb  mov     [rsp+0E8h+var_B8], 964h
0x1800148d3  jmp     short loc_1800148DD
0x1800148d5  mov     [rsp+0E8h+var_B8], 1
0x1800148dd  jmp     loc_1800149BE
0x1800148e2  jmp     loc_1800149C2
0x1800148e7  jmp     loc_1800149C2
0x1800148ec  mov     [rsp+0E8h+var_A8], rbx
0x1800148f1  cmp     dword ptr [rsi+4], 5
0x1800148f5  jnz     loc_1800149BE
0x1800148fb  lea     rdx, [rsi+1Ch]
0x1800148ff  lea     rcx, [rsp+0E8h+var_78]
0x180014904  cmp     bx, [rsi+1Eh]
0x180014908  jnz     short loc_180014911
0x18001490a  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x18001490f  jmp     short loc_180014916
0x180014911  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x180014916  lea     rcx, [rsp+0E8h+var_78]; this
0x18001491b  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180014920  mov     r14, rax
0x180014923  mov     [rsp+0E8h+var_A8], rax
0x180014928  mov     r8d, 10h; Size
0x18001492e  lea     rdx, [rsi+0Ch]; Buf2
0x180014932  lea     rcx, GUID_DEVINTERFACE_SMARTCARD_READER; Buf1
0x180014939  call    memcmp_0
0x18001493e  test    eax, eax
0x180014940  jnz     short loc_180014974
0x180014942  mov     r8d, 1; unsigned int
0x180014948  mov     rdx, r14; unsigned __int16 *
0x18001494b  lea     rcx, ?AddReaderDriver@@YAKPEBGK@Z; unsigned int (*)(const unsigned __int16 *, unsigned int)
0x180014952  call    ?CalaisAsyncAddReader@@YAKP6AKPEBGK@Z0K@Z; CalaisAsyncAddReader(ulong (*)(ushort const *,ulong),ushort const *,ulong)
0x180014957  test    eax, eax
0x180014959  jz      short loc_1800149BE
0x18001495b  mov     [rsp+0E8h+var_B8], eax
0x18001495f  mov     [rsp+0E8h+pExceptionObject], eax
0x180014963  lea     rdx, _TI1K; pThrowInfo
0x18001496a  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18001496f  call    _CxxThrowException_0
0x180014974  mov     r8d, 10h; Size
0x18001497a  lea     rdx, [rsi+0Ch]; Buf2
0x18001497e  lea     rcx, GUID_DEVINTERFACE_NGC_CONTAINER; Buf1
0x180014985  call    memcmp_0
0x18001498a  test    eax, eax
0x18001498c  jnz     short loc_1800149BE
0x18001498e  xor     r8d, r8d; unsigned int
0x180014991  mov     rdx, r14; unsigned __int16 *
0x180014994  lea     rcx, ?AddNgcReader@@YAKPEBGK@Z; unsigned int (*)(const unsigned __int16 *, unsigned int)
0x18001499b  call    ?CalaisAsyncAddReader@@YAKP6AKPEBGK@Z0K@Z; CalaisAsyncAddReader(ulong (*)(ushort const *,ulong),ushort const *,ulong)
0x1800149a0  test    eax, eax
0x1800149a2  jz      short loc_1800149BE
0x1800149a4  mov     [rsp+0E8h+var_B8], eax
0x1800149a8  mov     [rsp+0E8h+var_B0], eax
0x1800149ac  lea     rdx, _TI1K; pThrowInfo
0x1800149b3  lea     rcx, [rsp+0E8h+var_B0]; pExceptionObject
0x1800149b8  call    _CxxThrowException_0
0x1800149be  jmp     short loc_1800149CB
0x1800149c0  jmp     short $+2
0x1800149c2  xor     ebx, ebx
0x1800149c4  lea     rdi, WPP_GLOBAL_Control
0x1800149cb  lea     rcx, [rsp+0E8h+var_78]; this
0x1800149d0  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x1800149d5  jmp     short loc_180014A41
0x1800149d7  mov     cs:ServiceStatus.dwCurrentState, 4
0x1800149e1  jmp     short loc_180014A3A
0x1800149e3  mov     cs:ServiceStatus.dwCurrentState, 7
0x1800149ed  jmp     short loc_180014A3A
0x1800149ef  mov     cs:ServiceStatus.dwCurrentState, 3
0x1800149f9  mov     cs:ServiceStatus.dwCheckPoint, ebx
0x1800149ff  mov     cs:ServiceStatus.dwWaitHint, 7530h
  ... truncated ...
```
