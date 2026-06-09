# CRestoreManager::UpdateRestoreThrottleTimeForApp(ulong)

- ea: `0x1400295b8`
- end: `0x140029796`
- name: `?UpdateRestoreThrottleTimeForApp@CRestoreManager@@SAJK@Z`
- size: `478`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14002877c`

## callees

- `0x140002728`
- `0x140005430`
- `0x140012510`
- `0x140014474`
- `0x1400295b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400296a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400296a2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140029672`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140029672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029765`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029765`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400295f4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400295f4`

## pseudocode

```c
__int64 __fastcall CRestoreManager::UpdateRestoreThrottleTimeForApp(DWORD dwProcessId)
{
  HANDLE v2; // rdi
  signed int v3; // eax
  int v4; // ebx
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
           (__int64)v10,
           (__int64)L"%i|%d|%d",
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
0x1400295b8  mov     [rsp-8+arg_0], rbx
0x1400295bd  mov     [rsp-8+arg_18], rdi
0x1400295c2  push    rbp
0x1400295c3  mov     rbp, rsp
0x1400295c6  sub     rsp, 50h
0x1400295ca  lea     rax, [rbp+var_10]
0x1400295ce  mov     ebx, ecx
0x1400295d0  mov     [rbp+var_20], rax
0x1400295d4  mov     r8d, ecx; dwProcessId
0x1400295d7  lea     rax, [rbp+var_10]
0x1400295db  xor     edx, edx; bInheritHandle
0x1400295dd  mov     [rbp+var_18], rax
0x1400295e1  mov     ecx, 400h; dwDesiredAccess
0x1400295e6  xor     eax, eax
0x1400295e8  mov     [rbp+var_10], ax
0x1400295ec  mov     qword ptr [rbp+CreationTime.dwLowDateTime], rax
0x1400295f0  mov     qword ptr [rbp+ExitTime.dwLowDateTime], rax
0x1400295f4  call    cs:__imp_OpenProcess
0x1400295fa  mov     rdi, rax
0x1400295fd  lea     rcx, [rax+1]
0x140029601  cmp     rcx, 1
0x140029605  ja      short loc_14002965A
0x140029607  call    cs:__imp_GetLastError
0x14002960d  mov     ebx, eax
0x14002960f  test    eax, eax
0x140029611  jle     short loc_14002961C
0x140029613  movzx   ebx, ax
0x140029616  or      ebx, 80070000h
0x14002961c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029623  lea     rax, WPP_GLOBAL_Control
0x14002962a  cmp     rcx, rax
0x14002962d  jz      loc_14002976B
0x140029633  test    byte ptr [rcx+1Ch], 1
0x140029637  jz      loc_14002976B
0x14002963d  mov     rcx, [rcx+10h]
0x140029641  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x140029648  mov     edx, 27h ; '''
0x14002964d  mov     r9d, ebx
0x140029650  call    WPP_SF_d
0x140029655  jmp     loc_14002976B
0x14002965a  lea     rax, [rbp+ExitTime]
0x14002965e  mov     rcx, rdi; hProcess
0x140029661  lea     r9, [rbp+ExitTime]; lpKernelTime
0x140029665  mov     [rsp+50h+lpUserTime], rax; lpUserTime
0x14002966a  lea     r8, [rbp+ExitTime]; lpExitTime
0x14002966e  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x140029672  call    cs:__imp_GetProcessTimes
0x140029678  test    eax, eax
0x14002967a  jnz     short loc_1400296CC
0x14002967c  mov     ebx, 80004005h
0x140029681  mov     rcx, cs:WPP_GLOBAL_Control
0x140029688  lea     rax, WPP_GLOBAL_Control
0x14002968f  cmp     rcx, rax
0x140029692  jz      loc_140029762
0x140029698  test    byte ptr [rcx+1Ch], 1
0x14002969c  jz      loc_140029762
0x1400296a2  call    cs:__imp_GetLastError
0x1400296a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400296af  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x1400296b6  mov     edx, 28h ; '('
0x1400296bb  mov     r9d, eax
0x1400296be  mov     rcx, [rcx+10h]
0x1400296c2  call    WPP_SF_d
0x1400296c7  jmp     loc_140029762
0x1400296cc  mov     eax, [rbp+CreationTime.dwLowDateTime]
0x1400296cf  lea     rdx, aIDD; "%i|%d|%d"
0x1400296d6  mov     r9d, [rbp+CreationTime.dwHighDateTime]
0x1400296da  lea     rcx, [rbp+var_20]
0x1400296de  mov     r8d, ebx
0x1400296e1  mov     dword ptr [rsp+50h+lpUserTime], eax
0x1400296e5  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400296ea  mov     ebx, eax
0x1400296ec  test    eax, eax
0x1400296ee  jns     short loc_140029723
0x1400296f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400296f7  lea     rax, WPP_GLOBAL_Control
0x1400296fe  cmp     rcx, rax
0x140029701  jz      short loc_140029762
0x140029703  test    byte ptr [rcx+1Ch], 1
0x140029707  jz      short loc_140029762
0x140029709  mov     edx, 29h ; ')'
0x14002970e  mov     rcx, [rcx+10h]
0x140029712  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x140029719  mov     r9d, ebx
0x14002971c  call    WPP_SF_d
0x140029721  jmp     short loc_140029762
0x140029723  mov     r8, [rbp+var_20]; wchar_t *
0x140029727  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\Windows E"...
0x14002972e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140029735  call    ?UtilRegSetCurrentTime@@YAJPEAUHKEY__@@PEB_W1@Z; UtilRegSetCurrentTime(HKEY__ *,wchar_t const *,wchar_t const *)
0x14002973a  mov     ebx, eax
0x14002973c  test    eax, eax
0x14002973e  jns     short loc_140029760
0x140029740  mov     rcx, cs:WPP_GLOBAL_Control
0x140029747  lea     rax, WPP_GLOBAL_Control
0x14002974e  cmp     rcx, rax
0x140029751  jz      short loc_140029762
0x140029753  test    byte ptr [rcx+1Ch], 1
0x140029757  jz      short loc_140029762
0x140029759  mov     edx, 2Ah ; '*'
0x14002975e  jmp     short loc_14002970E
0x140029760  xor     ebx, ebx
0x140029762  mov     rcx, rdi; hObject
0x140029765  call    cs:__imp_CloseHandle
0x14002976b  mov     rcx, [rbp+var_20]; void *
0x14002976f  lea     rax, [rbp+var_10]
0x140029773  cmp     rcx, rax
0x140029776  jz      short loc_140029784
0x140029778  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002977f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140029784  mov     rdi, [rsp+50h+arg_18]
0x140029789  mov     eax, ebx
0x14002978b  mov     rbx, [rsp+50h+arg_0]
0x140029790  add     rsp, 50h
0x140029794  pop     rbp
0x140029795  retn
```
