# CAppRecorderPlugin::StopRecordingSession(ulong)

- ea: `0x140051348`
- end: `0x1400517bd`
- name: `?StopRecordingSession@CAppRecorderPlugin@@AEAAJK@Z`
- size: `1141`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400507f0`

## callees

- `0x140002748`
- `0x1400030f8`
- `0x1400054e4`
- `0x140011a04`
- `0x140014a88`
- `0x140014ee4`
- `0x140014f14`
- `0x140051348`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1400514fb`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1400514fb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140051646`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140051697`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140051646`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140051697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400515f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400515f6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140051708`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140051708`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1400515e6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1400515e6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400516d6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400516d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051571`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051587`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051747`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005178c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400517a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051571`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051587`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051747`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005178c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400517a2`
- `wer!WerpAddTerminationReason` at `0x1400516f5`
- `wer!WerpAddTerminationReason` at `0x1400516f5`

## pseudocode

```c
__int64 __fastcall CAppRecorderPlugin::StopRecordingSession(CAppRecorderPlugin *this, unsigned int a2)
{
  char *v3; // rsi
  int SystemDirectory2; // eax
  unsigned int v5; // ebx
  CUserModeHangReport *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  signed int LastError; // eax
  signed int v10; // eax
  DWORD ProcessId; // eax
  struct _PROCESS_INFORMATION hObject; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpApplicationName[2]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v15[8]; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpName[2]; // [rsp+88h] [rbp-78h] BYREF
  _WORD v17[8]; // [rsp+98h] [rbp-68h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+A8h] [rbp-58h] BYREF
  _WORD v19[12]; // [rsp+B8h] [rbp-48h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&hObject, 0, sizeof(hObject));
  lpCommandLine[0] = v19;
  lpCommandLine[1] = v19;
  v19[0] = 0;
  lpApplicationName[0] = v15;
  lpApplicationName[1] = v15;
  v15[0] = 0;
  v3 = 0;
  lpName[0] = v17;
  lpName[1] = v17;
  v17[0] = 0;
  SystemDirectory2 = UtilGetSystemDirectory2(lpApplicationName, 0);
  v5 = SystemDirectory2;
  if ( SystemDirectory2 >= 0 )
  {
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            lpApplicationName,
                            L"psr.exe",
                            7) )
    {
      SystemDirectory2 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                           lpCommandLine,
                           L"%s /stop",
                           lpApplicationName[0]);
      v5 = SystemDirectory2;
      if ( SystemDirectory2 >= 0 )
      {
        SystemDirectory2 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             lpName,
                             L"%d-AppRecorderEnabled",
                             a2);
        v5 = SystemDirectory2;
        if ( SystemDirectory2 >= 0 )
        {
          v3 = (char *)OpenEventW(0x100000u, 0, lpName[0]);
          if ( v3 == (char *)-1LL || v3 + 1 == (char *)1 )
          {
            LastError = GetLastError();
            v5 = LastError;
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_47;
            }
            v7 = 37;
          }
          else
          {
            StartupInfo.cb = 104;
            if ( hObject.hProcess )
              CloseHandle(hObject.hProcess);
            if ( hObject.hThread )
              CloseHandle(hObject.hThread);
            memset(&hObject, 0, sizeof(hObject));
            if ( CreateProcessW(lpApplicationName[0], lpCommandLine[0], 0, 0, 0, 0, 0, 0, &StartupInfo, &hObject) )
            {
              if ( WaitForSingleObject(v3, 0x4E20u) == 258
                && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
              }
              if ( hObject.hProcess && WaitForSingleObject(hObject.hProcess, 0x4E20u) == 258 )
              {
                if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
                }
                ProcessId = GetProcessId(hObject.hProcess);
                WerpAddTerminationReason(ProcessId, 2, L"WerAppRecorderNonResponsive");
                TerminateProcess(hObject.hProcess, 0);
                v5 = -2147467259;
              }
              else
              {
                v5 = 0;
              }
              goto LABEL_47;
            }
            v10 = GetLastError();
            v5 = v10;
            if ( v10 > 0 )
              v5 = (unsigned __int16)v10 | 0x80070000;
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_47;
            }
            v7 = 38;
          }
          v8 = v5;
          goto LABEL_6;
        }
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 36;
          goto LABEL_5;
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 35;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v5 = -2147024882;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 34;
        v8 = 2147942414LL;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 33;
LABEL_5:
      v8 = (unsigned int)SystemDirectory2;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v8);
    }
  }
LABEL_47:
  if ( lpName[0] != v17 )
    operator delete((void *)lpName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(v3 + 1) > 1 )
    CloseHandle(v3);
  if ( lpApplicationName[0] != v15 )
    operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpCommandLine[0] != v19 )
    operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  return v5;
}

```

## disassembly

```asm
0x140051348  mov     [rsp-8+arg_0], rcx
0x14005134d  push    rbp
0x14005134e  push    rbx
0x14005134f  push    rsi
0x140051350  push    rdi
0x140051351  lea     rbp, [rsp-48h]
0x140051356  sub     rsp, 148h
0x14005135d  mov     edi, edx
0x14005135f  xor     edx, edx; Val
0x140051361  lea     r8d, [rdx+68h]; Size
0x140051365  lea     rcx, [rbp+60h+StartupInfo]; void *
0x140051369  call    memset_0
0x14005136e  xorps   xmm0, xmm0
0x140051371  xor     eax, eax
0x140051373  movups  xmmword ptr [rsp+160h+hObject], xmm0
0x140051378  mov     [rsp+160h+var_100], rax
0x14005137d  lea     rax, [rbp+60h+var_A8]
0x140051381  mov     [rbp+60h+lpCommandLine], rax
0x140051385  lea     rax, [rbp+60h+var_A8]
0x140051389  mov     [rbp+60h+var_B0], rax
0x14005138d  xor     eax, eax
0x14005138f  mov     [rbp+60h+var_A8], ax
0x140051393  lea     rax, [rsp+160h+var_E8]
0x140051398  mov     [rsp+160h+lpApplicationName], rax
0x14005139d  lea     rax, [rsp+160h+var_E8]
0x1400513a2  mov     [rsp+160h+var_F0], rax
0x1400513a7  xor     eax, eax
0x1400513a9  mov     [rsp+160h+var_E8], ax
0x1400513ae  xor     esi, esi
0x1400513b0  mov     [rbp+60h+arg_0], rsi
0x1400513b4  lea     rax, [rbp+60h+var_C8]
0x1400513b8  mov     [rbp+60h+lpName], rax
0x1400513bc  lea     rax, [rbp+60h+var_C8]
0x1400513c0  mov     [rbp+60h+var_D0], rax
0x1400513c4  xor     eax, eax
0x1400513c6  mov     [rbp+60h+var_C8], ax
0x1400513ca  xor     edx, edx
0x1400513cc  lea     rcx, [rsp+160h+lpApplicationName]
0x1400513d1  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)
0x1400513d6  mov     ebx, eax
0x1400513d8  test    eax, eax
0x1400513da  jns     short loc_140051418
0x1400513dc  lea     rdi, WPP_GLOBAL_Control
0x1400513e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400513ea  cmp     rcx, rdi
0x1400513ed  jz      loc_14005171D
0x1400513f3  test    byte ptr [rcx+1Ch], 1
0x1400513f7  jz      loc_14005171D
0x1400513fd  lea     edx, [rsi+21h]
0x140051400  mov     r9d, eax
0x140051403  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14005140a  mov     rcx, [rcx+10h]
0x14005140e  call    WPP_SF_d
0x140051413  jmp     loc_14005171D
0x140051418  mov     r8d, 7
0x14005141e  lea     rdx, aPsrExe; "psr.exe"
0x140051425  lea     rcx, [rsp+160h+lpApplicationName]
0x14005142a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14005142f  test    al, al
0x140051431  jnz     short loc_140051466
0x140051433  mov     ebx, 8007000Eh
0x140051438  lea     rdi, WPP_GLOBAL_Control
0x14005143f  mov     rcx, cs:WPP_GLOBAL_Control
0x140051446  cmp     rcx, rdi
0x140051449  jz      loc_14005171D
0x14005144f  test    byte ptr [rcx+1Ch], 1
0x140051453  jz      loc_14005171D
0x140051459  mov     edx, 22h ; '"'
0x14005145e  mov     r9d, 8007000Eh
0x140051464  jmp     short loc_140051403
0x140051466  mov     r8, [rsp+160h+lpApplicationName]
0x14005146b  lea     rdx, aSStop; "%s /stop"
0x140051472  lea     rcx, [rbp+60h+lpCommandLine]
0x140051476  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14005147b  mov     ebx, eax
0x14005147d  test    eax, eax
0x14005147f  jns     short loc_1400514AC
0x140051481  lea     rdi, WPP_GLOBAL_Control
0x140051488  mov     rcx, cs:WPP_GLOBAL_Control
0x14005148f  cmp     rcx, rdi
0x140051492  jz      loc_14005171D
0x140051498  test    byte ptr [rcx+1Ch], 1
0x14005149c  jz      loc_14005171D
0x1400514a2  mov     edx, 23h ; '#'
0x1400514a7  jmp     loc_140051400
0x1400514ac  mov     r8d, edi
0x1400514af  lea     rdx, aDApprecorderen; "%d-AppRecorderEnabled"
0x1400514b6  lea     rcx, [rbp+60h+lpName]
0x1400514ba  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400514bf  mov     ebx, eax
0x1400514c1  test    eax, eax
0x1400514c3  jns     short loc_1400514F0
0x1400514c5  lea     rdi, WPP_GLOBAL_Control
0x1400514cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400514d3  cmp     rcx, rdi
0x1400514d6  jz      loc_14005171D
0x1400514dc  test    byte ptr [rcx+1Ch], 1
0x1400514e0  jz      loc_14005171D
0x1400514e6  mov     edx, 24h ; '$'
0x1400514eb  jmp     loc_140051400
0x1400514f0  mov     r8, [rbp+60h+lpName]; lpName
0x1400514f4  xor     edx, edx; bInheritHandle
0x1400514f6  mov     ecx, 100000h; dwDesiredAccess
0x1400514fb  call    cs:__imp_OpenEventW
0x140051502  nop     dword ptr [rax+rax+00h]
0x140051507  mov     rsi, rax
0x14005150a  mov     [rbp+60h+arg_0], rax
0x14005150e  inc     rax
0x140051511  cmp     rax, 1
0x140051515  ja      short loc_140051560
0x140051517  call    cs:__imp_GetLastError
0x14005151e  nop     dword ptr [rax+rax+00h]
0x140051523  mov     ebx, eax
0x140051525  test    eax, eax
0x140051527  jle     short loc_140051532
0x140051529  movzx   ebx, ax
0x14005152c  or      ebx, 80070000h
0x140051532  lea     rdi, WPP_GLOBAL_Control
0x140051539  mov     rcx, cs:WPP_GLOBAL_Control
0x140051540  cmp     rcx, rdi
0x140051543  jz      loc_14005171D
0x140051549  test    byte ptr [rcx+1Ch], 1
0x14005154d  jz      loc_14005171D
0x140051553  mov     edx, 25h ; '%'
0x140051558  mov     r9d, ebx
0x14005155b  jmp     loc_140051403
0x140051560  mov     [rbp+60h+StartupInfo.cb], 68h ; 'h'
0x140051567  mov     rcx, [rsp+160h+hObject]; hObject
0x14005156c  test    rcx, rcx
0x14005156f  jz      short loc_14005157D
0x140051571  call    cs:__imp_CloseHandle
0x140051578  nop     dword ptr [rax+rax+00h]
0x14005157d  mov     rcx, [rsp+160h+hObject+8]; hObject
0x140051582  test    rcx, rcx
0x140051585  jz      short loc_140051593
0x140051587  call    cs:__imp_CloseHandle
0x14005158e  nop     dword ptr [rax+rax+00h]
0x140051593  xorps   xmm0, xmm0
0x140051596  xor     eax, eax
0x140051598  movups  xmmword ptr [rsp+160h+hObject], xmm0
0x14005159d  mov     [rsp+160h+var_100], rax
0x1400515a2  lea     rax, [rsp+160h+hObject]
0x1400515a7  mov     [rsp+160h+lpProcessInformation], rax; lpProcessInformation
0x1400515ac  lea     rax, [rbp+60h+StartupInfo]
0x1400515b0  mov     [rsp+160h+lpStartupInfo], rax; lpStartupInfo
0x1400515b5  mov     [rsp+160h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1400515be  mov     [rsp+160h+lpEnvironment], 0; lpEnvironment
0x1400515c7  mov     [rsp+160h+dwCreationFlags], 0; dwCreationFlags
0x1400515cf  mov     [rsp+160h+bInheritHandles], 0; bInheritHandles
0x1400515d7  xor     r9d, r9d; lpThreadAttributes
0x1400515da  xor     r8d, r8d; lpProcessAttributes
0x1400515dd  mov     rdx, [rbp+60h+lpCommandLine]; lpCommandLine
0x1400515e1  mov     rcx, [rsp+160h+lpApplicationName]; lpApplicationName
0x1400515e6  call    cs:__imp_CreateProcessW
0x1400515ed  nop     dword ptr [rax+rax+00h]
0x1400515f2  test    eax, eax
0x1400515f4  jnz     short loc_14005163C
0x1400515f6  call    cs:__imp_GetLastError
0x1400515fd  nop     dword ptr [rax+rax+00h]
0x140051602  mov     ebx, eax
0x140051604  test    eax, eax
0x140051606  jle     short loc_140051611
0x140051608  movzx   ebx, ax
0x14005160b  or      ebx, 80070000h
0x140051611  lea     rdi, WPP_GLOBAL_Control
0x140051618  mov     rcx, cs:WPP_GLOBAL_Control
0x14005161f  cmp     rcx, rdi
0x140051622  jz      loc_14005171D
0x140051628  test    byte ptr [rcx+1Ch], 1
0x14005162c  jz      loc_14005171D
0x140051632  mov     edx, 26h ; '&'
0x140051637  jmp     loc_140051558
0x14005163c  mov     ebx, 4E20h
0x140051641  mov     edx, ebx; dwMilliseconds
0x140051643  mov     rcx, rsi; hHandle
0x140051646  call    cs:__imp_WaitForSingleObject
0x14005164d  nop     dword ptr [rax+rax+00h]
0x140051652  lea     rdi, WPP_GLOBAL_Control
0x140051659  cmp     eax, 102h
0x14005165e  jnz     short loc_140051687
0x140051660  mov     rcx, cs:WPP_GLOBAL_Control
0x140051667  cmp     rcx, rdi
0x14005166a  jz      short loc_140051687
0x14005166c  test    byte ptr [rcx+1Ch], 2
0x140051670  jz      short loc_140051687
0x140051672  mov     edx, 27h ; '''
0x140051677  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14005167e  mov     rcx, [rcx+10h]
0x140051682  call    WPP_SF_
0x140051687  mov     rcx, [rsp+160h+hObject]; hHandle
0x14005168c  test    rcx, rcx
0x14005168f  jz      loc_14005171B
0x140051695  mov     edx, ebx; dwMilliseconds
0x140051697  call    cs:__imp_WaitForSingleObject
0x14005169e  nop     dword ptr [rax+rax+00h]
0x1400516a3  cmp     eax, 102h
0x1400516a8  jnz     short loc_14005171B
0x1400516aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400516b1  cmp     rcx, rdi
0x1400516b4  jz      short loc_1400516D1
0x1400516b6  test    byte ptr [rcx+1Ch], 1
0x1400516ba  jz      short loc_1400516D1
0x1400516bc  mov     edx, 28h ; '('
0x1400516c1  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x1400516c8  mov     rcx, [rcx+10h]
0x1400516cc  call    WPP_SF_
0x1400516d1  mov     rcx, [rsp+160h+hObject]; Process
0x1400516d6  call    cs:__imp_GetProcessId
0x1400516dd  nop     dword ptr [rax+rax+00h]
0x1400516e2  mov     ecx, eax
0x1400516e4  mov     r9d, 1
0x1400516ea  lea     r8, aWerapprecorder; "WerAppRecorderNonResponsive"
0x1400516f1  lea     edx, [r9+1]
0x1400516f5  call    cs:__imp_WerpAddTerminationReason
0x1400516fc  nop     dword ptr [rax+rax+00h]
0x140051701  xor     edx, edx; uExitCode
0x140051703  mov     rcx, [rsp+160h+hObject]; hProcess
0x140051708  call    cs:__imp_TerminateProcess
0x14005170f  nop     dword ptr [rax+rax+00h]
0x140051714  mov     ebx, 80004005h
0x140051719  jmp     short loc_14005171D
0x14005171b  xor     ebx, ebx
0x14005171d  lea     rax, [rbp+60h+var_C8]
0x140051721  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140051728  mov     rcx, [rbp+60h+lpName]; void *
0x14005172c  cmp     rcx, rax
0x14005172f  jz      short loc_14005173A
0x140051731  mov     rdx, rdi; struct std::nothrow_t *
0x140051734  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140051739  nop
0x14005173a  lea     rax, [rsi+1]
0x14005173e  cmp     rax, 1
0x140051742  jbe     short loc_140051754
0x140051744  mov     rcx, rsi; hObject
0x140051747  call    cs:__imp_CloseHandle
0x14005174e  nop     dword ptr [rax+rax+00h]
0x140051753  nop
0x140051754  lea     rax, [rsp+160h+var_E8]
0x140051759  mov     rcx, [rsp+160h+lpApplicationName]; void *
0x14005175e  cmp     rcx, rax
0x140051761  jz      short loc_14005176C
0x140051763  mov     rdx, rdi; struct std::nothrow_t *
0x140051766  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005176b  nop
0x14005176c  lea     rax, [rbp+60h+var_A8]
0x140051770  mov     rcx, [rbp+60h+lpCommandLine]; void *
0x140051774  cmp     rcx, rax
0x140051777  jz      short loc_140051782
0x140051779  mov     rdx, rdi; struct std::nothrow_t *
0x14005177c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140051781  nop
0x140051782  mov     rcx, [rsp+160h+hObject]; hObject
0x140051787  test    rcx, rcx
0x14005178a  jz      short loc_140051798
0x14005178c  call    cs:__imp_CloseHandle
0x140051793  nop     dword ptr [rax+rax+00h]
0x140051798  mov     rcx, [rsp+160h+hObject+8]; hObject
0x14005179d  test    rcx, rcx
0x1400517a0  jz      short loc_1400517AE
0x1400517a2  call    cs:__imp_CloseHandle
0x1400517a9  nop     dword ptr [rax+rax+00h]
0x1400517ae  mov     eax, ebx
0x1400517b0  add     rsp, 148h
0x1400517b7  pop     rdi
0x1400517b8  pop     rsi
0x1400517b9  pop     rbx
0x1400517ba  pop     rbp
0x1400517bb  retn
```
