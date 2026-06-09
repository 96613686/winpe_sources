# CReportManager::AddLoadedModulesToReport(void)

- ea: `0x180031e5c`
- end: `0x180032164`
- name: `?AddLoadedModulesToReport@CReportManager@@AEAAJXZ`
- size: `776`
- prototype: `__int64 __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180079198`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x18001fe24`
- `0x180029380`
- `0x180031e5c`
- `0x180046d74`
- `0x1800492a0`
- `0x18004a558`
- `0x180050db0`
- `0x1800517cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180031efe`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180031f74`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180031efe`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180031f74`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180031eb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180031eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320f9`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180031f2a`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180031f2a`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18003201c`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18003201c`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180032093`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180032093`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x180031fbc`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x180031fbc`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180031f8a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180031f8a`

## pseudocode

```c
__int64 __fastcall CReportManager::AddLoadedModulesToReport(CReportManager *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rcx
  DWORD ProcessId; // eax
  HANDLE v8; // r14
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  HANDLE Toolhelp32Snapshot; // rax
  HANDLE v16; // rbx
  DWORD v17; // eax
  int v18; // eax
  DWORD v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  DWORD LastError; // eax
  DWORD TickCount; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE Process; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE hSnapshot[2]; // [rsp+30h] [rbp-D0h] BYREF
  MODULEENTRY32W me; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Filename[264]; // [rsp+480h] [rbp+380h] BYREF

  hSnapshot[0] = 0;
  Process = 0;
  memset_0(&me, 0, sizeof(me));
  Filename[0] = 0;
  TickCount = GetTickCount();
  v2 = *((_QWORD *)this + 1);
  v3 = *(_QWORD *)(v2 + 5848);
  v4 = *(_QWORD *)(v2 + 5856) - v3;
  *(_QWORD *)(v2 + 5856) = v3;
  utl::_RangeDestroyApc<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
    v5,
    v3,
    v4 >> 5);
  v6 = *((_QWORD *)this + 1);
  if ( *(_QWORD *)(v6 + 6640) )
  {
    ProcessId = GetProcessId(*(HANDLE *)(v6 + 6640));
    v8 = *(HANDLE *)(*((_QWORD *)this + 1) + 6640LL);
  }
  else
  {
    v9 = *(_QWORD *)(v6 + 9112);
    if ( v9 )
    {
      v10 = PssQuerySnapshot(v9, 1, &Process);
      v11 = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          v11 = (unsigned __int16)v10 | 0x80070000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v13 = 48;
          v14 = v11;
LABEL_35:
          WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v14);
          goto LABEL_36;
        }
        goto LABEL_36;
      }
      ProcessId = GetProcessId(Process);
      v8 = Process;
    }
    else
    {
      v8 = 0;
      ProcessId = 0;
    }
  }
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, ProcessId);
  tlx::unique_any<tlx::file_handle_traits>::reset(hSnapshot, Toolhelp32Snapshot);
  v16 = hSnapshot[0];
  if ( (unsigned __int64)hSnapshot[0] + 1 <= 1 )
  {
    LastError = GetLastError();
    v18 = ERROR_HR_FROM_WIN32(LastError);
    v11 = v18;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v13 = 49;
      goto LABEL_34;
    }
  }
  else
  {
    me.dwSize = 1080;
    if ( Module32FirstW(hSnapshot[0], &me) )
    {
      while ( 1 )
      {
        if ( !K32GetModuleFileNameExW(v8, me.hModule, Filename, 0x104u) )
        {
          v19 = GetLastError();
          v20 = ERROR_HR_FROM_WIN32(v19);
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v20);
          StringCchCopyW(Filename, 0x104u, me.szExePath);
        }
        v18 = CReport::AddLoadedModule(*((CReport **)this + 1), Filename);
        v11 = v18;
        if ( v18 < 0 )
          break;
        if ( !Module32NextW(v16, &me) )
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          {
            v21 = CTimer::Stop((CTimer *)&TickCount);
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v21);
          }
          v11 = 0;
          goto LABEL_36;
        }
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 52;
        goto LABEL_34;
      }
    }
    else
    {
      v17 = GetLastError();
      v18 = ERROR_HR_FROM_WIN32(v17);
      v11 = v18;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 50;
LABEL_34:
        v14 = (unsigned int)v18;
        goto LABEL_35;
      }
    }
  }
LABEL_36:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(hSnapshot);
  return v11;
}

```

## disassembly

```asm
0x180031e5c  push    rbp
0x180031e5e  push    rbx
0x180031e5f  push    rsi
0x180031e60  push    rdi
0x180031e61  push    r14
0x180031e63  push    r15
0x180031e65  lea     rbp, [rsp-5A8h]
0x180031e6d  sub     rsp, 6A8h
0x180031e74  mov     rax, cs:__security_cookie
0x180031e7b  xor     rax, rsp
0x180031e7e  mov     [rbp+5D0h+var_40], rax
0x180031e85  mov     r15, rcx
0x180031e88  mov     [rsp+6D0h+hSnapshot], 0
0x180031e91  mov     esi, 438h
0x180031e96  mov     [rsp+6D0h+Process], 0
0x180031e9f  mov     r8d, esi; Size
0x180031ea2  lea     rcx, [rsp+6D0h+me]; void *
0x180031ea7  xor     edx, edx; Val
0x180031ea9  call    memset_0
0x180031eae  xor     eax, eax
0x180031eb0  mov     [rbp+5D0h+Filename], ax
0x180031eb7  call    cs:__imp_GetTickCount
0x180031ebd  mov     [rsp+6D0h+var_6B0], eax
0x180031ec1  mov     rax, [r15+8]
0x180031ec5  mov     rdx, [rax+16D8h]
0x180031ecc  mov     r8, [rax+16E0h]
0x180031ed3  sub     r8, rdx
0x180031ed6  mov     [rax+16E0h], rdx
0x180031edd  sar     r8, 5
0x180031ee1  call    ??$_RangeDestroyApc@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@0@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64)
0x180031ee6  mov     rcx, [r15+8]
0x180031eea  mov     ebx, 8
0x180031eef  mov     rax, [rcx+19F0h]
0x180031ef6  test    rax, rax
0x180031ef9  jz      short loc_180031F11
0x180031efb  mov     rcx, rax; Process
0x180031efe  call    cs:__imp_GetProcessId
0x180031f04  mov     rcx, [r15+8]
0x180031f08  mov     r14, [rcx+19F0h]
0x180031f0f  jmp     short loc_180031F86
0x180031f11  mov     rcx, [rcx+2398h]
0x180031f18  test    rcx, rcx
0x180031f1b  jz      short loc_180031F81
0x180031f1d  mov     r9d, ebx
0x180031f20  lea     r8, [rsp+6D0h+Process]
0x180031f25  mov     edx, 1
0x180031f2a  call    cs:__imp_PssQuerySnapshot
0x180031f30  mov     edi, eax
0x180031f32  test    eax, eax
0x180031f34  jz      short loc_180031F6F
0x180031f36  jle     short loc_180031F41
0x180031f38  movzx   edi, ax
0x180031f3b  or      edi, 80070000h
0x180031f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f48  lea     rsi, WPP_GLOBAL_Control
0x180031f4f  cmp     rcx, rsi
0x180031f52  jz      loc_180032139
0x180031f58  test    byte ptr [rcx+1Ch], 1
0x180031f5c  jz      loc_180032139
0x180031f62  mov     edx, 30h ; '0'
0x180031f67  mov     r9d, edi
0x180031f6a  jmp     loc_180032129
0x180031f6f  mov     rcx, [rsp+6D0h+Process]; Process
0x180031f74  call    cs:__imp_GetProcessId
0x180031f7a  mov     r14, [rsp+6D0h+Process]
0x180031f7f  jmp     short loc_180031F86
0x180031f81  xor     r14d, r14d
0x180031f84  xor     eax, eax
0x180031f86  mov     edx, eax; th32ProcessID
0x180031f88  mov     ecx, ebx; dwFlags
0x180031f8a  call    cs:__imp_CreateToolhelp32Snapshot
0x180031f90  mov     rdx, rax
0x180031f93  lea     rcx, [rsp+6D0h+hSnapshot]
0x180031f98  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180031f9d  mov     rbx, [rsp+6D0h+hSnapshot]
0x180031fa2  lea     rax, [rbx+1]
0x180031fa6  cmp     rax, 1
0x180031faa  jbe     loc_1800320F9
0x180031fb0  lea     rdx, [rsp+6D0h+me]; lpme
0x180031fb5  mov     [rsp+6D0h+me.dwSize], esi
0x180031fb9  mov     rcx, rbx; hSnapshot
0x180031fbc  call    cs:__imp_Module32FirstW
0x180031fc2  test    eax, eax
0x180031fc4  jnz     short loc_180032000
0x180031fc6  call    cs:__imp_GetLastError
0x180031fcc  mov     ecx, eax; unsigned int
0x180031fce  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180031fd3  mov     edi, eax
0x180031fd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180031fdc  lea     rsi, WPP_GLOBAL_Control
0x180031fe3  cmp     rcx, rsi
0x180031fe6  jz      loc_180032139
0x180031fec  test    byte ptr [rcx+1Ch], 1
0x180031ff0  jz      loc_180032139
0x180031ff6  mov     edx, 32h ; '2'
0x180031ffb  jmp     loc_180032126
0x180032000  lea     rsi, WPP_GLOBAL_Control
0x180032007  mov     rdx, [rsp+6D0h+me.hModule]; hModule
0x18003200c  lea     r8, [rbp+5D0h+Filename]; lpFilename
0x180032013  mov     r9d, 104h; nSize
0x180032019  mov     rcx, r14; hProcess
0x18003201c  call    cs:__imp_K32GetModuleFileNameExW
0x180032022  test    eax, eax
0x180032024  jnz     short loc_180032075
0x180032026  call    cs:__imp_GetLastError
0x18003202c  mov     ecx, eax; unsigned int
0x18003202e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180032033  mov     rcx, cs:WPP_GLOBAL_Control
0x18003203a  cmp     rcx, rsi
0x18003203d  jz      short loc_18003205D
0x18003203f  test    byte ptr [rcx+1Ch], 1
0x180032043  jz      short loc_18003205D
0x180032045  mov     rcx, [rcx+10h]
0x180032049  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180032050  mov     edx, 33h ; '3'
0x180032055  mov     r9d, eax
0x180032058  call    WPP_SF_d
0x18003205d  lea     r8, [rbp+5D0h+me.szExePath]; wchar_t *
0x180032064  mov     edx, 104h; unsigned __int64
0x180032069  lea     rcx, [rbp+5D0h+Filename]; wchar_t *
0x180032070  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180032075  mov     rcx, [r15+8]; this
0x180032079  lea     rdx, [rbp+5D0h+Filename]; wchar_t *
0x180032080  call    ?AddLoadedModule@CReport@@QEAAJPEB_W@Z; CReport::AddLoadedModule(wchar_t const *)
0x180032085  mov     edi, eax
0x180032087  test    eax, eax
0x180032089  js      short loc_1800320E0
0x18003208b  lea     rdx, [rsp+6D0h+me]; lpme
0x180032090  mov     rcx, rbx; hSnapshot
0x180032093  call    cs:__imp_Module32NextW
0x180032099  test    eax, eax
0x18003209b  jnz     loc_180032007
0x1800320a1  mov     rax, cs:WPP_GLOBAL_Control
0x1800320a8  cmp     rax, rsi
0x1800320ab  jz      short loc_1800320DC
0x1800320ad  test    byte ptr [rax+1Ch], 4
0x1800320b1  jz      short loc_1800320DC
0x1800320b3  lea     rcx, [rsp+6D0h+var_6B0]; this
0x1800320b8  call    ?Stop@CTimer@@QEAAKXZ; CTimer::Stop(void)
0x1800320bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800320c4  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x1800320cb  mov     edx, 35h ; '5'
0x1800320d0  mov     r9d, eax
0x1800320d3  mov     rcx, [rcx+10h]
0x1800320d7  call    WPP_SF_d
0x1800320dc  xor     edi, edi
0x1800320de  jmp     short loc_180032139
0x1800320e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800320e7  cmp     rcx, rsi
0x1800320ea  jz      short loc_180032139
0x1800320ec  test    byte ptr [rcx+1Ch], 1
0x1800320f0  jz      short loc_180032139
0x1800320f2  mov     edx, 34h ; '4'
0x1800320f7  jmp     short loc_180032126
0x1800320f9  call    cs:__imp_GetLastError
0x1800320ff  mov     ecx, eax; unsigned int
0x180032101  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180032106  mov     edi, eax
0x180032108  mov     rcx, cs:WPP_GLOBAL_Control
0x18003210f  lea     rsi, WPP_GLOBAL_Control
0x180032116  cmp     rcx, rsi
0x180032119  jz      short loc_180032139
0x18003211b  test    byte ptr [rcx+1Ch], 1
0x18003211f  jz      short loc_180032139
0x180032121  mov     edx, 31h ; '1'
0x180032126  mov     r9d, eax
0x180032129  mov     rcx, [rcx+10h]
0x18003212d  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180032134  call    WPP_SF_d
0x180032139  lea     rcx, [rsp+6D0h+hSnapshot]
0x18003213e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180032143  mov     eax, edi
0x180032145  mov     rcx, [rbp+5D0h+var_40]
0x18003214c  xor     rcx, rsp; StackCookie
0x18003214f  call    __security_check_cookie
0x180032154  add     rsp, 6A8h
0x18003215b  pop     r15
0x18003215d  pop     r14
0x18003215f  pop     rdi
0x180032160  pop     rsi
0x180032161  pop     rbx
0x180032162  pop     rbp
0x180032163  retn
```
