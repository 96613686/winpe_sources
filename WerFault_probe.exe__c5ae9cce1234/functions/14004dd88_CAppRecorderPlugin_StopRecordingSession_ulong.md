# CAppRecorderPlugin::StopRecordingSession(ulong)

- ea: `0x14004dd88`
- end: `0x14004e1a4`
- name: `?StopRecordingSession@CAppRecorderPlugin@@AEAAJK@Z`
- size: `1052`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14004d230`

## callees

- `0x140002728`
- `0x1400030a8`
- `0x140005430`
- `0x1400112cc`
- `0x140013ff0`
- `0x14001444c`
- `0x140014474`
- `0x14004dd88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004df3b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004df3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004e062`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004e0a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004e062`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004e0a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004df51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004df51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e018`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14004e108`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14004e108`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14004e00e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14004e00e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14004e0e2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14004e0e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004dfa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004dfb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e190`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004dfa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004dfb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e190`
- `wer!WerpAddTerminationReason` at `0x14004e0fb`
- `wer!WerpAddTerminationReason` at `0x14004e0fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
              }
              if ( hObject.hProcess && WaitForSingleObject(hObject.hProcess, 0x4E20u) == 258 )
              {
                if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
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
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v8);
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
0x14004dd88  mov     [rsp-8+arg_0], rcx
0x14004dd8d  push    rbp
0x14004dd8e  push    rbx
0x14004dd8f  push    rsi
0x14004dd90  push    rdi
0x14004dd91  lea     rbp, [rsp-48h]
0x14004dd96  sub     rsp, 148h
0x14004dd9d  mov     edi, edx
0x14004dd9f  xor     edx, edx; Val
0x14004dda1  lea     r8d, [rdx+68h]; Size
0x14004dda5  lea     rcx, [rbp+60h+StartupInfo]; void *
0x14004dda9  call    memset_0
0x14004ddae  xorps   xmm0, xmm0
0x14004ddb1  xor     eax, eax
0x14004ddb3  movups  xmmword ptr [rsp+160h+hObject], xmm0
0x14004ddb8  mov     [rsp+160h+var_100], rax
0x14004ddbd  lea     rax, [rbp+60h+var_A8]
0x14004ddc1  mov     [rbp+60h+lpCommandLine], rax
0x14004ddc5  lea     rax, [rbp+60h+var_A8]
0x14004ddc9  mov     [rbp+60h+var_B0], rax
0x14004ddcd  xor     eax, eax
0x14004ddcf  mov     [rbp+60h+var_A8], ax
0x14004ddd3  lea     rax, [rsp+160h+var_E8]
0x14004ddd8  mov     [rsp+160h+lpApplicationName], rax
0x14004dddd  lea     rax, [rsp+160h+var_E8]
0x14004dde2  mov     [rsp+160h+var_F0], rax
0x14004dde7  xor     eax, eax
0x14004dde9  mov     [rsp+160h+var_E8], ax
0x14004ddee  xor     esi, esi
0x14004ddf0  mov     [rbp+60h+arg_0], rsi
0x14004ddf4  lea     rax, [rbp+60h+var_C8]
0x14004ddf8  mov     [rbp+60h+lpName], rax
0x14004ddfc  lea     rax, [rbp+60h+var_C8]
0x14004de00  mov     [rbp+60h+var_D0], rax
0x14004de04  xor     eax, eax
0x14004de06  mov     [rbp+60h+var_C8], ax
0x14004de0a  xor     edx, edx
0x14004de0c  lea     rcx, [rsp+160h+lpApplicationName]
0x14004de11  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)
0x14004de16  mov     ebx, eax
0x14004de18  test    eax, eax
0x14004de1a  jns     short loc_14004DE58
0x14004de1c  lea     rdi, WPP_GLOBAL_Control
0x14004de23  mov     rcx, cs:WPP_GLOBAL_Control
0x14004de2a  cmp     rcx, rdi
0x14004de2d  jz      loc_14004E117
0x14004de33  test    byte ptr [rcx+1Ch], 1
0x14004de37  jz      loc_14004E117
0x14004de3d  lea     edx, [rsi+21h]
0x14004de40  mov     r9d, eax
0x14004de43  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004de4a  mov     rcx, [rcx+10h]
0x14004de4e  call    WPP_SF_d
0x14004de53  jmp     loc_14004E117
0x14004de58  mov     r8d, 7
0x14004de5e  lea     rdx, aPsrExe; "psr.exe"
0x14004de65  lea     rcx, [rsp+160h+lpApplicationName]
0x14004de6a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14004de6f  test    al, al
0x14004de71  jnz     short loc_14004DEA6
0x14004de73  mov     ebx, 8007000Eh
0x14004de78  lea     rdi, WPP_GLOBAL_Control
0x14004de7f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004de86  cmp     rcx, rdi
0x14004de89  jz      loc_14004E117
0x14004de8f  test    byte ptr [rcx+1Ch], 1
0x14004de93  jz      loc_14004E117
0x14004de99  mov     edx, 22h ; '"'
0x14004de9e  mov     r9d, 8007000Eh
0x14004dea4  jmp     short loc_14004DE43
0x14004dea6  mov     r8, [rsp+160h+lpApplicationName]
0x14004deab  lea     rdx, aSStop; "%s /stop"
0x14004deb2  lea     rcx, [rbp+60h+lpCommandLine]
0x14004deb6  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14004debb  mov     ebx, eax
0x14004debd  test    eax, eax
0x14004debf  jns     short loc_14004DEEC
0x14004dec1  lea     rdi, WPP_GLOBAL_Control
0x14004dec8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004decf  cmp     rcx, rdi
0x14004ded2  jz      loc_14004E117
0x14004ded8  test    byte ptr [rcx+1Ch], 1
0x14004dedc  jz      loc_14004E117
0x14004dee2  mov     edx, 23h ; '#'
0x14004dee7  jmp     loc_14004DE40
0x14004deec  mov     r8d, edi
0x14004deef  lea     rdx, aDApprecorderen; "%d-AppRecorderEnabled"
0x14004def6  lea     rcx, [rbp+60h+lpName]
0x14004defa  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14004deff  mov     ebx, eax
0x14004df01  test    eax, eax
0x14004df03  jns     short loc_14004DF30
0x14004df05  lea     rdi, WPP_GLOBAL_Control
0x14004df0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004df13  cmp     rcx, rdi
0x14004df16  jz      loc_14004E117
0x14004df1c  test    byte ptr [rcx+1Ch], 1
0x14004df20  jz      loc_14004E117
0x14004df26  mov     edx, 24h ; '$'
0x14004df2b  jmp     loc_14004DE40
0x14004df30  mov     r8, [rbp+60h+lpName]; lpName
0x14004df34  xor     edx, edx; bInheritHandle
0x14004df36  mov     ecx, 100000h; dwDesiredAccess
0x14004df3b  call    cs:__imp_OpenEventW
0x14004df41  mov     rsi, rax
0x14004df44  mov     [rbp+60h+arg_0], rax
0x14004df48  inc     rax
0x14004df4b  cmp     rax, 1
0x14004df4f  ja      short loc_14004DF94
0x14004df51  call    cs:__imp_GetLastError
0x14004df57  mov     ebx, eax
0x14004df59  test    eax, eax
0x14004df5b  jle     short loc_14004DF66
0x14004df5d  movzx   ebx, ax
0x14004df60  or      ebx, 80070000h
0x14004df66  lea     rdi, WPP_GLOBAL_Control
0x14004df6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004df74  cmp     rcx, rdi
0x14004df77  jz      loc_14004E117
0x14004df7d  test    byte ptr [rcx+1Ch], 1
0x14004df81  jz      loc_14004E117
0x14004df87  mov     edx, 25h ; '%'
0x14004df8c  mov     r9d, ebx
0x14004df8f  jmp     loc_14004DE43
0x14004df94  mov     [rbp+60h+StartupInfo.cb], 68h ; 'h'
0x14004df9b  mov     rcx, [rsp+160h+hObject]; hObject
0x14004dfa0  test    rcx, rcx
0x14004dfa3  jz      short loc_14004DFAB
0x14004dfa5  call    cs:__imp_CloseHandle
0x14004dfab  mov     rcx, [rsp+160h+hObject+8]; hObject
0x14004dfb0  test    rcx, rcx
0x14004dfb3  jz      short loc_14004DFBB
0x14004dfb5  call    cs:__imp_CloseHandle
0x14004dfbb  xorps   xmm0, xmm0
0x14004dfbe  xor     eax, eax
0x14004dfc0  movups  xmmword ptr [rsp+160h+hObject], xmm0
0x14004dfc5  mov     [rsp+160h+var_100], rax
0x14004dfca  lea     rax, [rsp+160h+hObject]
0x14004dfcf  mov     [rsp+160h+lpProcessInformation], rax; lpProcessInformation
0x14004dfd4  lea     rax, [rbp+60h+StartupInfo]
0x14004dfd8  mov     [rsp+160h+lpStartupInfo], rax; lpStartupInfo
0x14004dfdd  mov     [rsp+160h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14004dfe6  mov     [rsp+160h+lpEnvironment], 0; lpEnvironment
0x14004dfef  mov     [rsp+160h+dwCreationFlags], 0; dwCreationFlags
0x14004dff7  mov     [rsp+160h+bInheritHandles], 0; bInheritHandles
0x14004dfff  xor     r9d, r9d; lpThreadAttributes
0x14004e002  xor     r8d, r8d; lpProcessAttributes
0x14004e005  mov     rdx, [rbp+60h+lpCommandLine]; lpCommandLine
0x14004e009  mov     rcx, [rsp+160h+lpApplicationName]; lpApplicationName
0x14004e00e  call    cs:__imp_CreateProcessW
0x14004e014  test    eax, eax
0x14004e016  jnz     short loc_14004E058
0x14004e018  call    cs:__imp_GetLastError
0x14004e01e  mov     ebx, eax
0x14004e020  test    eax, eax
0x14004e022  jle     short loc_14004E02D
0x14004e024  movzx   ebx, ax
0x14004e027  or      ebx, 80070000h
0x14004e02d  lea     rdi, WPP_GLOBAL_Control
0x14004e034  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e03b  cmp     rcx, rdi
0x14004e03e  jz      loc_14004E117
0x14004e044  test    byte ptr [rcx+1Ch], 1
0x14004e048  jz      loc_14004E117
0x14004e04e  mov     edx, 26h ; '&'
0x14004e053  jmp     loc_14004DF8C
0x14004e058  mov     ebx, 4E20h
0x14004e05d  mov     edx, ebx; dwMilliseconds
0x14004e05f  mov     rcx, rsi; hHandle
0x14004e062  call    cs:__imp_WaitForSingleObject
0x14004e068  lea     rdi, WPP_GLOBAL_Control
0x14004e06f  cmp     eax, 102h
0x14004e074  jnz     short loc_14004E09D
0x14004e076  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e07d  cmp     rcx, rdi
0x14004e080  jz      short loc_14004E09D
0x14004e082  test    byte ptr [rcx+1Ch], 2
0x14004e086  jz      short loc_14004E09D
0x14004e088  mov     edx, 27h ; '''
0x14004e08d  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004e094  mov     rcx, [rcx+10h]
0x14004e098  call    WPP_SF_
0x14004e09d  mov     rcx, [rsp+160h+hObject]; hHandle
0x14004e0a2  test    rcx, rcx
0x14004e0a5  jz      short loc_14004E115
0x14004e0a7  mov     edx, ebx; dwMilliseconds
0x14004e0a9  call    cs:__imp_WaitForSingleObject
0x14004e0af  cmp     eax, 102h
0x14004e0b4  jnz     short loc_14004E115
0x14004e0b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e0bd  cmp     rcx, rdi
0x14004e0c0  jz      short loc_14004E0DD
0x14004e0c2  test    byte ptr [rcx+1Ch], 1
0x14004e0c6  jz      short loc_14004E0DD
0x14004e0c8  mov     edx, 28h ; '('
0x14004e0cd  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004e0d4  mov     rcx, [rcx+10h]
0x14004e0d8  call    WPP_SF_
0x14004e0dd  mov     rcx, [rsp+160h+hObject]; Process
0x14004e0e2  call    cs:__imp_GetProcessId
0x14004e0e8  mov     ecx, eax
0x14004e0ea  mov     r9d, 1
0x14004e0f0  lea     r8, aWerapprecorder; "WerAppRecorderNonResponsive"
0x14004e0f7  lea     edx, [r9+1]
0x14004e0fb  call    cs:__imp_WerpAddTerminationReason
0x14004e101  xor     edx, edx; uExitCode
0x14004e103  mov     rcx, [rsp+160h+hObject]; hProcess
0x14004e108  call    cs:__imp_TerminateProcess
0x14004e10e  mov     ebx, 80004005h
0x14004e113  jmp     short loc_14004E117
0x14004e115  xor     ebx, ebx
0x14004e117  lea     rax, [rbp+60h+var_C8]
0x14004e11b  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14004e122  mov     rcx, [rbp+60h+lpName]; void *
0x14004e126  cmp     rcx, rax
0x14004e129  jz      short loc_14004E134
0x14004e12b  mov     rdx, rdi; struct std::nothrow_t *
0x14004e12e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004e133  nop
0x14004e134  lea     rax, [rsi+1]
0x14004e138  cmp     rax, 1
0x14004e13c  jbe     short loc_14004E148
0x14004e13e  mov     rcx, rsi; hObject
0x14004e141  call    cs:__imp_CloseHandle
0x14004e147  nop
0x14004e148  lea     rax, [rsp+160h+var_E8]
0x14004e14d  mov     rcx, [rsp+160h+lpApplicationName]; void *
0x14004e152  cmp     rcx, rax
0x14004e155  jz      short loc_14004E160
0x14004e157  mov     rdx, rdi; struct std::nothrow_t *
0x14004e15a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004e15f  nop
0x14004e160  lea     rax, [rbp+60h+var_A8]
0x14004e164  mov     rcx, [rbp+60h+lpCommandLine]; void *
0x14004e168  cmp     rcx, rax
0x14004e16b  jz      short loc_14004E176
0x14004e16d  mov     rdx, rdi; struct std::nothrow_t *
0x14004e170  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004e175  nop
0x14004e176  mov     rcx, [rsp+160h+hObject]; hObject
0x14004e17b  test    rcx, rcx
0x14004e17e  jz      short loc_14004E186
0x14004e180  call    cs:__imp_CloseHandle
0x14004e186  mov     rcx, [rsp+160h+hObject+8]; hObject
0x14004e18b  test    rcx, rcx
0x14004e18e  jz      short loc_14004E196
0x14004e190  call    cs:__imp_CloseHandle
0x14004e196  mov     eax, ebx
0x14004e198  add     rsp, 148h
0x14004e19f  pop     rdi
0x14004e1a0  pop     rsi
0x14004e1a1  pop     rbx
0x14004e1a2  pop     rbp
0x14004e1a3  retn
```
