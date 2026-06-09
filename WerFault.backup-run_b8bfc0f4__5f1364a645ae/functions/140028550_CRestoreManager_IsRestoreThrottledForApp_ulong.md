# CRestoreManager::IsRestoreThrottledForApp(ulong)

- ea: `0x140028550`
- end: `0x14002871f`
- name: `?IsRestoreThrottledForApp@CRestoreManager@@SAHK@Z`
- size: `463`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400280fc`

## callees

- `0x140002728`
- `0x140005430`
- `0x140014474`
- `0x14001570c`
- `0x140028550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400285a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400285a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028634`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140028609`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140028609`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400286f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400286f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400286d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400286d6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002858f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002858f`

## pseudocode

```c
_BOOL8 __fastcall CRestoreManager::IsRestoreThrottledForApp(DWORD dwProcessId)
{
  BOOL v2; // ebx
  char *v3; // rdi
  signed int LastError; // eax
  DWORD v5; // eax
  int v6; // eax
  unsigned __int64 v7; // r9
  unsigned __int64 QWORD; // rbx
  LPFILETIME lpUserTime; // [rsp+20h] [rbp-30h]
  bool v11; // [rsp+28h] [rbp-28h]
  LPCWSTR lpValue[2]; // [rsp+30h] [rbp-20h] BYREF
  _WORD v13[8]; // [rsp+40h] [rbp-10h] BYREF
  struct _FILETIME ExitTime; // [rsp+78h] [rbp+28h] BYREF
  struct _FILETIME CreationTime; // [rsp+80h] [rbp+30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp+38h] BYREF

  lpValue[0] = v13;
  lpValue[1] = v13;
  v2 = 0;
  v13[0] = 0;
  SystemTimeAsFileTime = 0;
  CreationTime = 0;
  ExitTime = 0;
  v3 = (char *)OpenProcess(0x400u, 0, dwProcessId);
  if ( v3 == (char *)-1LL || v3 + 1 == (char *)1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids,
        (unsigned int)LastError);
    }
  }
  else
  {
    if ( GetProcessTimes(v3, &CreationTime, &ExitTime, &ExitTime, &ExitTime) )
    {
      LODWORD(lpUserTime) = CreationTime.dwLowDateTime;
      v6 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
             lpValue,
             L"%i|%d|%d",
             dwProcessId,
             CreationTime.dwHighDateTime,
             lpUserTime);
      if ( v6 >= 0 )
      {
        QWORD = UtilRegGetQWORD(
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Hangs\\NHRTimes",
                  lpValue[0],
                  v7,
                  0,
                  v11);
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v2 = *(_QWORD *)&SystemTimeAsFileTime - QWORD < 0x23C34600;
      }
      else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids,
          (unsigned int)v6);
      }
    }
    else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, v5);
    }
    CloseHandle(v3);
  }
  if ( lpValue[0] != v13 )
    operator delete((void *)lpValue[0], (const struct std::nothrow_t *)&std::nothrow);
  return v2;
}

```

## disassembly

```asm
0x140028550  mov     [rsp-18h+arg_0], rbx
0x140028555  push    rbp
0x140028556  push    rsi
0x140028557  push    rdi
0x140028558  mov     rbp, rsp
0x14002855b  sub     rsp, 50h
0x14002855f  lea     rax, [rbp+var_10]
0x140028563  mov     esi, ecx
0x140028565  mov     [rbp+lpValue], rax
0x140028569  mov     r8d, ecx; dwProcessId
0x14002856c  lea     rax, [rbp+var_10]
0x140028570  xor     edx, edx; bInheritHandle
0x140028572  mov     [rbp+var_18], rax
0x140028576  mov     ecx, 400h; dwDesiredAccess
0x14002857b  xor     eax, eax
0x14002857d  xor     ebx, ebx
0x14002857f  mov     [rbp+var_10], ax
0x140028583  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140028587  mov     qword ptr [rbp+CreationTime.dwLowDateTime], rax
0x14002858b  mov     qword ptr [rbp+ExitTime.dwLowDateTime], rax
0x14002858f  call    cs:__imp_OpenProcess
0x140028595  mov     rdi, rax
0x140028598  inc     rax
0x14002859b  cmp     rax, 1
0x14002859f  ja      short loc_1400285F1
0x1400285a1  call    cs:__imp_GetLastError
0x1400285a7  test    eax, eax
0x1400285a9  jle     short loc_1400285B3
0x1400285ab  movzx   eax, ax
0x1400285ae  or      eax, 80070000h
0x1400285b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400285ba  lea     rdx, WPP_GLOBAL_Control
0x1400285c1  cmp     rcx, rdx
0x1400285c4  jz      loc_1400286F7
0x1400285ca  test    byte ptr [rcx+1Ch], 1
0x1400285ce  jz      loc_1400286F7
0x1400285d4  mov     rcx, [rcx+10h]
0x1400285d8  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x1400285df  mov     edx, 2Bh ; '+'
0x1400285e4  mov     r9d, eax
0x1400285e7  call    WPP_SF_d
0x1400285ec  jmp     loc_1400286F7
0x1400285f1  lea     rax, [rbp+ExitTime]
0x1400285f5  mov     rcx, rdi; hProcess
0x1400285f8  lea     r9, [rbp+ExitTime]; lpKernelTime
0x1400285fc  mov     [rsp+50h+lpUserTime], rax; lpUserTime
0x140028601  lea     r8, [rbp+ExitTime]; lpExitTime
0x140028605  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x140028609  call    cs:__imp_GetProcessTimes
0x14002860f  test    eax, eax
0x140028611  jnz     short loc_14002865E
0x140028613  mov     rax, cs:WPP_GLOBAL_Control
0x14002861a  lea     rdx, WPP_GLOBAL_Control
0x140028621  cmp     rax, rdx
0x140028624  jz      loc_1400286EE
0x14002862a  test    byte ptr [rax+1Ch], 1
0x14002862e  jz      loc_1400286EE
0x140028634  call    cs:__imp_GetLastError
0x14002863a  mov     rcx, cs:WPP_GLOBAL_Control
0x140028641  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x140028648  mov     edx, 2Ch ; ','
0x14002864d  mov     r9d, eax
0x140028650  mov     rcx, [rcx+10h]
0x140028654  call    WPP_SF_d
0x140028659  jmp     loc_1400286EE
0x14002865e  mov     eax, [rbp+CreationTime.dwLowDateTime]
0x140028661  lea     rdx, aIDD; "%i|%d|%d"
0x140028668  mov     r9d, [rbp+CreationTime.dwHighDateTime]
0x14002866c  lea     rcx, [rbp+lpValue]
0x140028670  mov     r8d, esi
0x140028673  mov     dword ptr [rsp+50h+lpUserTime], eax
0x140028677  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14002867c  test    eax, eax
0x14002867e  jns     short loc_1400286B3
0x140028680  mov     rcx, cs:WPP_GLOBAL_Control
0x140028687  lea     rdx, WPP_GLOBAL_Control
0x14002868e  cmp     rcx, rdx
0x140028691  jz      short loc_1400286EE
0x140028693  test    byte ptr [rcx+1Ch], 1
0x140028697  jz      short loc_1400286EE
0x140028699  mov     rcx, [rcx+10h]
0x14002869d  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x1400286a4  mov     edx, 2Dh ; '-'
0x1400286a9  mov     r9d, eax
0x1400286ac  call    WPP_SF_d
0x1400286b1  jmp     short loc_1400286EE
0x1400286b3  mov     r8, [rbp+lpValue]; lpValue
0x1400286b7  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\Windows E"...
0x1400286be  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400286c5  mov     [rsp+50h+lpUserTime], rbx; bool *
0x1400286ca  call    ?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z; UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)
0x1400286cf  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400286d3  mov     rbx, rax
0x1400286d6  call    cs:__imp_GetSystemTimeAsFileTime
0x1400286dc  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400286e0  sub     rax, rbx
0x1400286e3  xor     ebx, ebx
0x1400286e5  cmp     rax, 23C34600h
0x1400286eb  setb    bl
0x1400286ee  mov     rcx, rdi; hObject
0x1400286f1  call    cs:__imp_CloseHandle
0x1400286f7  mov     rcx, [rbp+lpValue]; void *
0x1400286fb  lea     rax, [rbp+var_10]
0x1400286ff  cmp     rcx, rax
0x140028702  jz      short loc_140028710
0x140028704  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002870b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140028710  mov     eax, ebx
0x140028712  mov     rbx, [rsp+50h+arg_0]
0x140028717  add     rsp, 50h
0x14002871b  pop     rdi
0x14002871c  pop     rsi
0x14002871d  pop     rbp
0x14002871e  retn
```
