# CRestoreManager::UpdateRestoreThrottleTimeForApp(ulong)

- ea: `0x14002b158`
- end: `0x14002b355`
- name: `?UpdateRestoreThrottleTimeForApp@CRestoreManager@@SAJK@Z`
- size: `509`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14002a25c`

## callees

- `0x140002748`
- `0x1400054e4`
- `0x140012dbc`
- `0x140014f14`
- `0x14002b158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b254`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14002b21e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14002b21e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b31d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b31d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002b194`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002b194`

## pseudocode

```c
__int64 __fastcall CRestoreManager::UpdateRestoreThrottleTimeForApp(DWORD dwProcessId)
{
  HANDLE v2; // rdi
  signed int v3; // eax
  signed int v4; // ebx
  DWORD LastError; // eax
  CUserModeHangReport *v6; // rcx
  __int64 v7; // rdx
  LPFILETIME lpUserTime; // [rsp+20h] [rbp-30h]
  wchar_t *v10[2]; // [rsp+30h] [rbp-20h] BYREF
  _WORD v11[8]; // [rsp+40h] [rbp-10h] BYREF
  struct _FILETIME ExitTime; // [rsp+68h] [rbp+18h] BYREF
  struct _FILETIME CreationTime; // [rsp+70h] [rbp+20h] BYREF

  v10[0] = v11;
  v10[1] = v11;
  v11[0] = 0;
  CreationTime = 0;
  ExitTime = 0;
  v2 = OpenProcess(0x400u, 0, dwProcessId);
  if ( (unsigned __int64)v2 + 1 > 1 )
  {
    if ( !GetProcessTimes(v2, &CreationTime, &ExitTime, &ExitTime, &ExitTime) )
    {
      v4 = -2147467259;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, LastError);
      }
      goto LABEL_21;
    }
    LODWORD(lpUserTime) = CreationTime.dwLowDateTime;
    v4 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
           v10,
           L"%i|%d|%d",
           dwProcessId,
           CreationTime.dwHighDateTime,
           lpUserTime);
    if ( v4 >= 0 )
    {
      v4 = UtilRegSetCurrentTime(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Hangs\\NHRTimes",
             v10[0]);
      if ( v4 >= 0 )
      {
        v4 = 0;
        goto LABEL_21;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_21;
      }
      v7 = 42;
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_21;
      }
      v7 = 41;
    }
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, (unsigned int)v4);
LABEL_21:
    CloseHandle(v2);
    goto LABEL_22;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, (unsigned int)v4);
  }
LABEL_22:
  if ( v10[0] != v11 )
    operator delete(v10[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002b158  mov     [rsp-8+arg_0], rbx
0x14002b15d  mov     [rsp-8+arg_18], rdi
0x14002b162  push    rbp
0x14002b163  mov     rbp, rsp
0x14002b166  sub     rsp, 50h
0x14002b16a  lea     rax, [rbp+var_10]
0x14002b16e  mov     ebx, ecx
0x14002b170  mov     [rbp+var_20], rax
0x14002b174  mov     r8d, ecx; dwProcessId
0x14002b177  lea     rax, [rbp+var_10]
0x14002b17b  xor     edx, edx; bInheritHandle
0x14002b17d  mov     [rbp+var_18], rax
0x14002b181  mov     ecx, 400h; dwDesiredAccess
0x14002b186  xor     eax, eax
0x14002b188  mov     [rbp+var_10], ax
0x14002b18c  mov     qword ptr [rbp+CreationTime.dwLowDateTime], rax
0x14002b190  mov     qword ptr [rbp+ExitTime.dwLowDateTime], rax
0x14002b194  call    cs:__imp_OpenProcess
0x14002b19b  nop     dword ptr [rax+rax+00h]
0x14002b1a0  mov     rdi, rax
0x14002b1a3  lea     rcx, [rax+1]
0x14002b1a7  cmp     rcx, 1
0x14002b1ab  ja      short loc_14002B206
0x14002b1ad  call    cs:__imp_GetLastError
0x14002b1b4  nop     dword ptr [rax+rax+00h]
0x14002b1b9  mov     ebx, eax
0x14002b1bb  test    eax, eax
0x14002b1bd  jle     short loc_14002B1C8
0x14002b1bf  movzx   ebx, ax
0x14002b1c2  or      ebx, 80070000h
0x14002b1c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b1cf  lea     rax, WPP_GLOBAL_Control
0x14002b1d6  cmp     rcx, rax
0x14002b1d9  jz      loc_14002B329
0x14002b1df  test    byte ptr [rcx+1Ch], 1
0x14002b1e3  jz      loc_14002B329
0x14002b1e9  mov     rcx, [rcx+10h]
0x14002b1ed  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002b1f4  mov     edx, 27h ; '''
0x14002b1f9  mov     r9d, ebx
0x14002b1fc  call    WPP_SF_d
0x14002b201  jmp     loc_14002B329
0x14002b206  lea     rax, [rbp+ExitTime]
0x14002b20a  mov     rcx, rdi; hProcess
0x14002b20d  lea     r9, [rbp+ExitTime]; lpKernelTime
0x14002b211  mov     [rsp+50h+lpUserTime], rax; lpUserTime
0x14002b216  lea     r8, [rbp+ExitTime]; lpExitTime
0x14002b21a  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x14002b21e  call    cs:__imp_GetProcessTimes
0x14002b225  nop     dword ptr [rax+rax+00h]
0x14002b22a  test    eax, eax
0x14002b22c  jnz     short loc_14002B284
0x14002b22e  mov     ebx, 80004005h
0x14002b233  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b23a  lea     rax, WPP_GLOBAL_Control
0x14002b241  cmp     rcx, rax
0x14002b244  jz      loc_14002B31A
0x14002b24a  test    byte ptr [rcx+1Ch], 1
0x14002b24e  jz      loc_14002B31A
0x14002b254  call    cs:__imp_GetLastError
0x14002b25b  nop     dword ptr [rax+rax+00h]
0x14002b260  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b267  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002b26e  mov     edx, 28h ; '('
0x14002b273  mov     r9d, eax
0x14002b276  mov     rcx, [rcx+10h]
0x14002b27a  call    WPP_SF_d
0x14002b27f  jmp     loc_14002B31A
0x14002b284  mov     eax, [rbp+CreationTime.dwLowDateTime]
0x14002b287  lea     rdx, aIDD; "%i|%d|%d"
0x14002b28e  mov     r9d, [rbp+CreationTime.dwHighDateTime]
0x14002b292  lea     rcx, [rbp+var_20]
0x14002b296  mov     r8d, ebx
0x14002b299  mov     dword ptr [rsp+50h+lpUserTime], eax
0x14002b29d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14002b2a2  mov     ebx, eax
0x14002b2a4  test    eax, eax
0x14002b2a6  jns     short loc_14002B2DB
0x14002b2a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b2af  lea     rax, WPP_GLOBAL_Control
0x14002b2b6  cmp     rcx, rax
0x14002b2b9  jz      short loc_14002B31A
0x14002b2bb  test    byte ptr [rcx+1Ch], 1
0x14002b2bf  jz      short loc_14002B31A
0x14002b2c1  mov     edx, 29h ; ')'
0x14002b2c6  mov     rcx, [rcx+10h]
0x14002b2ca  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002b2d1  mov     r9d, ebx
0x14002b2d4  call    WPP_SF_d
0x14002b2d9  jmp     short loc_14002B31A
0x14002b2db  mov     r8, [rbp+var_20]; wchar_t *
0x14002b2df  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\Windows E"...
0x14002b2e6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14002b2ed  call    ?UtilRegSetCurrentTime@@YAJPEAUHKEY__@@PEB_W1@Z; UtilRegSetCurrentTime(HKEY__ *,wchar_t const *,wchar_t const *)
0x14002b2f2  mov     ebx, eax
0x14002b2f4  test    eax, eax
0x14002b2f6  jns     short loc_14002B318
0x14002b2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b2ff  lea     rax, WPP_GLOBAL_Control
0x14002b306  cmp     rcx, rax
0x14002b309  jz      short loc_14002B31A
0x14002b30b  test    byte ptr [rcx+1Ch], 1
0x14002b30f  jz      short loc_14002B31A
0x14002b311  mov     edx, 2Ah ; '*'
0x14002b316  jmp     short loc_14002B2C6
0x14002b318  xor     ebx, ebx
0x14002b31a  mov     rcx, rdi; hObject
0x14002b31d  call    cs:__imp_CloseHandle
0x14002b324  nop     dword ptr [rax+rax+00h]
0x14002b329  mov     rcx, [rbp+var_20]; void *
0x14002b32d  lea     rax, [rbp+var_10]
0x14002b331  cmp     rcx, rax
0x14002b334  jz      short loc_14002B342
0x14002b336  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002b33d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002b342  mov     rdi, [rsp+50h+arg_18]
0x14002b347  mov     eax, ebx
0x14002b349  mov     rbx, [rsp+50h+arg_0]
0x14002b34e  add     rsp, 50h
0x14002b352  pop     rbp
0x14002b353  retn
```
