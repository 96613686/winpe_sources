# CRestoreManager::IsRestoreThrottledForApp(ulong)

- ea: `0x140029ffc`
- end: `0x14002a1f0`
- name: `?IsRestoreThrottledForApp@CRestoreManager@@SAHK@Z`
- size: `500`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140029bb0`

## callees

- `0x140002748`
- `0x1400054e4`
- `0x140014f14`
- `0x140016288`
- `0x140029ffc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a0f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a0f2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14002a0c1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14002a0c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a1bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a1bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002a19a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002a19a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002a03b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002a03b`

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
0x140029ffc  mov     [rsp-18h+arg_0], rbx
0x14002a001  push    rbp
0x14002a002  push    rsi
0x14002a003  push    rdi
0x14002a004  mov     rbp, rsp
0x14002a007  sub     rsp, 50h
0x14002a00b  lea     rax, [rbp+var_10]
0x14002a00f  mov     esi, ecx
0x14002a011  mov     [rbp+lpValue], rax
0x14002a015  mov     r8d, ecx; dwProcessId
0x14002a018  lea     rax, [rbp+var_10]
0x14002a01c  xor     edx, edx; bInheritHandle
0x14002a01e  mov     [rbp+var_18], rax
0x14002a022  mov     ecx, 400h; dwDesiredAccess
0x14002a027  xor     eax, eax
0x14002a029  xor     ebx, ebx
0x14002a02b  mov     [rbp+var_10], ax
0x14002a02f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14002a033  mov     qword ptr [rbp+CreationTime.dwLowDateTime], rax
0x14002a037  mov     qword ptr [rbp+ExitTime.dwLowDateTime], rax
0x14002a03b  call    cs:__imp_OpenProcess
0x14002a042  nop     dword ptr [rax+rax+00h]
0x14002a047  mov     rdi, rax
0x14002a04a  inc     rax
0x14002a04d  cmp     rax, 1
0x14002a051  ja      short loc_14002A0A9
0x14002a053  call    cs:__imp_GetLastError
0x14002a05a  nop     dword ptr [rax+rax+00h]
0x14002a05f  test    eax, eax
0x14002a061  jle     short loc_14002A06B
0x14002a063  movzx   eax, ax
0x14002a066  or      eax, 80070000h
0x14002a06b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a072  lea     rdx, WPP_GLOBAL_Control
0x14002a079  cmp     rcx, rdx
0x14002a07c  jz      loc_14002A1C7
0x14002a082  test    byte ptr [rcx+1Ch], 1
0x14002a086  jz      loc_14002A1C7
0x14002a08c  mov     rcx, [rcx+10h]
0x14002a090  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002a097  mov     edx, 2Bh ; '+'
0x14002a09c  mov     r9d, eax
0x14002a09f  call    WPP_SF_d
0x14002a0a4  jmp     loc_14002A1C7
0x14002a0a9  lea     rax, [rbp+ExitTime]
0x14002a0ad  mov     rcx, rdi; hProcess
0x14002a0b0  lea     r9, [rbp+ExitTime]; lpKernelTime
0x14002a0b4  mov     [rsp+50h+lpUserTime], rax; lpUserTime
0x14002a0b9  lea     r8, [rbp+ExitTime]; lpExitTime
0x14002a0bd  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x14002a0c1  call    cs:__imp_GetProcessTimes
0x14002a0c8  nop     dword ptr [rax+rax+00h]
0x14002a0cd  test    eax, eax
0x14002a0cf  jnz     short loc_14002A122
0x14002a0d1  mov     rax, cs:WPP_GLOBAL_Control
0x14002a0d8  lea     rdx, WPP_GLOBAL_Control
0x14002a0df  cmp     rax, rdx
0x14002a0e2  jz      loc_14002A1B8
0x14002a0e8  test    byte ptr [rax+1Ch], 1
0x14002a0ec  jz      loc_14002A1B8
0x14002a0f2  call    cs:__imp_GetLastError
0x14002a0f9  nop     dword ptr [rax+rax+00h]
0x14002a0fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a105  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002a10c  mov     edx, 2Ch ; ','
0x14002a111  mov     r9d, eax
0x14002a114  mov     rcx, [rcx+10h]
0x14002a118  call    WPP_SF_d
0x14002a11d  jmp     loc_14002A1B8
0x14002a122  mov     eax, [rbp+CreationTime.dwLowDateTime]
0x14002a125  lea     rdx, aIDD; "%i|%d|%d"
0x14002a12c  mov     r9d, [rbp+CreationTime.dwHighDateTime]
0x14002a130  lea     rcx, [rbp+lpValue]
0x14002a134  mov     r8d, esi
0x14002a137  mov     dword ptr [rsp+50h+lpUserTime], eax
0x14002a13b  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14002a140  test    eax, eax
0x14002a142  jns     short loc_14002A177
0x14002a144  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a14b  lea     rdx, WPP_GLOBAL_Control
0x14002a152  cmp     rcx, rdx
0x14002a155  jz      short loc_14002A1B8
0x14002a157  test    byte ptr [rcx+1Ch], 1
0x14002a15b  jz      short loc_14002A1B8
0x14002a15d  mov     rcx, [rcx+10h]
0x14002a161  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002a168  mov     edx, 2Dh ; '-'
0x14002a16d  mov     r9d, eax
0x14002a170  call    WPP_SF_d
0x14002a175  jmp     short loc_14002A1B8
0x14002a177  mov     r8, [rbp+lpValue]; lpValue
0x14002a17b  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\Windows E"...
0x14002a182  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14002a189  mov     [rsp+50h+lpUserTime], rbx; bool *
0x14002a18e  call    ?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z; UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)
0x14002a193  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002a197  mov     rbx, rax
0x14002a19a  call    cs:__imp_GetSystemTimeAsFileTime
0x14002a1a1  nop     dword ptr [rax+rax+00h]
0x14002a1a6  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14002a1aa  sub     rax, rbx
0x14002a1ad  xor     ebx, ebx
0x14002a1af  cmp     rax, 23C34600h
0x14002a1b5  setb    bl
0x14002a1b8  mov     rcx, rdi; hObject
0x14002a1bb  call    cs:__imp_CloseHandle
0x14002a1c2  nop     dword ptr [rax+rax+00h]
0x14002a1c7  mov     rcx, [rbp+lpValue]; void *
0x14002a1cb  lea     rax, [rbp+var_10]
0x14002a1cf  cmp     rcx, rax
0x14002a1d2  jz      short loc_14002A1E0
0x14002a1d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002a1db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002a1e0  mov     eax, ebx
0x14002a1e2  mov     rbx, [rsp+50h+arg_0]
0x14002a1e7  add     rsp, 50h
0x14002a1eb  pop     rdi
0x14002a1ec  pop     rsi
0x14002a1ed  pop     rbp
0x14002a1ee  retn
```
