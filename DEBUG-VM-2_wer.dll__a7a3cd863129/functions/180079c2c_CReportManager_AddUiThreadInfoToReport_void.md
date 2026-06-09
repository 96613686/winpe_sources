# CReportManager::AddUiThreadInfoToReport(void)

- ea: `0x180079c2c`
- end: `0x18007a171`
- name: `?AddUiThreadInfoToReport@CReportManager@@AEAAJXZ`
- size: `1349`
- prototype: `__int64 __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180079148`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x18001fe24`
- `0x18002c220`
- `0x180050db0`
- `0x1800708b8`
- `0x180078644`
- `0x180078f84`
- `0x180079c2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180079e2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180079e2b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079c74`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079d30`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079c74`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079d30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a0ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a0ff`
- `ntdll!NtQueryInformationThread` at `0x180079e5b`
- `ntdll!NtQueryInformationThread` at `0x180079e5b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180079ef8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180079f6f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180079ef8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180079f6f`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180079cde`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180079cde`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180079d4a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180079d4a`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x180079d7e`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x180079d7e`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x18007a057`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x18007a057`

## pseudocode

```c
__int64 __fastcall CReportManager::AddUiThreadInfoToReport(CReportManager *this)
{
  __int64 v1; // rax
  int v3; // esi
  void *v4; // rcx
  DWORD ProcessId; // r15d
  HANDLE v6; // r12
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  DWORD v10; // eax
  char *Toolhelp32Snapshot; // rbx
  signed int v12; // eax
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // rdi
  HANDLE v16; // rax
  NTSTATUS InformationThread; // eax
  wchar_t *v18; // rcx
  __int64 v19; // rdx
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  wchar_t *v24; // rcx
  __int64 v25; // rdx
  signed int LastError; // eax
  HANDLE v28; // [rsp+30h] [rbp-49h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-41h] BYREF
  HANDLE Process; // [rsp+40h] [rbp-39h] BYREF
  char *v31; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 Buffer; // [rsp+50h] [rbp-29h] BYREF
  _OWORD ThreadInformation[3]; // [rsp+58h] [rbp-21h] BYREF
  THREADENTRY32 te; // [rsp+88h] [rbp+Fh] BYREF

  v1 = *((_QWORD *)this + 1);
  v3 = 0;
  v4 = *(void **)(v1 + 6640);
  if ( v4 )
  {
    ProcessId = GetProcessId(v4);
    v6 = *(HANDLE *)(*((_QWORD *)this + 1) + 6640LL);
  }
  else if ( *(_QWORD *)(v1 + 9112) )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
    v7 = *((_QWORD *)this + 1);
    Process = 0;
    v8 = PssQuerySnapshot(*(_QWORD *)(v7 + 9112), 1, &Process);
    v9 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v9);
      return v9;
    }
    v10 = GetProcessId(Process);
    v6 = Process;
    ProcessId = v10;
  }
  else
  {
    ProcessId = 0;
    v6 = 0;
  }
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(4u, 0);
  v31 = Toolhelp32Snapshot;
  if ( Toolhelp32Snapshot == (char *)-1LL || Toolhelp32Snapshot + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_79;
    v14 = 56;
    goto LABEL_78;
  }
  te.dwSize = 28;
  memset(&te.cntUsage, 0, 24);
  if ( !Thread32First(Toolhelp32Snapshot, &te) )
  {
    v12 = GetLastError();
    v9 = v12;
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_79;
    v14 = 57;
LABEL_78:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v9);
LABEL_79:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v31);
    return v9;
  }
  utl::make_unique<_TEB,,0>(&lpBuffer);
  v15 = lpBuffer;
  if ( !lpBuffer )
  {
    v24 = WPP_GLOBAL_Control;
    v9 = -2147024882;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v25 = 58;
LABEL_71:
      WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v9);
    }
LABEL_72:
    utl::unique_ptr<_TEB,utl::default_delete<_TEB>>::~unique_ptr<_TEB,utl::default_delete<_TEB>>(&lpBuffer);
    goto LABEL_79;
  }
  do
  {
    if ( te.th32OwnerProcessID != ProcessId )
      continue;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
        te.th32ThreadID);
    memset(ThreadInformation, 0, sizeof(ThreadInformation));
    v16 = OpenThread(0x40u, 0, te.th32ThreadID);
    v28 = v16;
    if ( (unsigned __int64)v16 + 1 <= 1 )
    {
      v22 = GetLastError();
      v3 = v22;
      if ( v22 > 0 )
        v3 = (unsigned __int16)v22 | 0x80070000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_59;
      v19 = 60;
LABEL_58:
      WPP_SF_Dd(
        *((_QWORD *)v18 + 2),
        v19,
        WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
        (unsigned int)v3,
        te.th32ThreadID);
      goto LABEL_59;
    }
    InformationThread = NtQueryInformationThread(v16, ThreadBasicInformation, ThreadInformation, 0x30u, 0);
    if ( InformationThread < 0 )
    {
      v3 = InformationThread | 0x10000000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_59;
      v19 = 61;
      goto LABEL_58;
    }
    if ( !*((_QWORD *)&ThreadInformation[0] + 1) )
    {
      v3 = -2147467259;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
          te.th32ThreadID);
      goto LABEL_59;
    }
    if ( !ReadProcessMemory(v6, *((LPCVOID *)&ThreadInformation[0] + 1), v15, 0x1870u, 0) )
    {
      v20 = GetLastError();
      v3 = v20;
      if ( v20 > 0 )
        v3 = (unsigned __int16)v20 | 0x80070000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_59;
      v19 = 63;
      goto LABEL_58;
    }
    if ( v15[15] )
    {
      Buffer = 0;
      if ( ReadProcessMemory(v6, (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + 2144LL), &Buffer, 8u, 0) )
      {
        v3 = CReport::AddMemBlock(*((CReport **)this + 1), ProcessId, Buffer, 0x30u, 0);
        if ( v3 >= 0 )
          goto LABEL_59;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_59;
        v19 = 65;
      }
      else
      {
        v21 = GetLastError();
        v3 = v21;
        if ( v21 > 0 )
          v3 = (unsigned __int16)v21 | 0x80070000;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
          goto LABEL_59;
        v19 = 64;
      }
      goto LABEL_58;
    }
LABEL_59:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v28);
  }
  while ( Thread32Next(Toolhelp32Snapshot, &te) );
  if ( GetLastError() != 18 )
  {
    v23 = GetLastError();
    v9 = v23;
    if ( v23 > 0 )
      v9 = (unsigned __int16)v23 | 0x80070000;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v25 = 66;
      goto LABEL_71;
    }
    goto LABEL_72;
  }
  utl::unique_ptr<_TEB,utl::default_delete<_TEB>>::~unique_ptr<_TEB,utl::default_delete<_TEB>>(&lpBuffer);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v31);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180079c2c  mov     [rsp-8+arg_8], rbx
0x180079c31  mov     [rsp-8+arg_10], rsi
0x180079c36  push    rbp
0x180079c37  push    rdi
0x180079c38  push    r12
0x180079c3a  push    r13
0x180079c3c  push    r15
0x180079c3e  lea     rbp, [rsp-37h]
0x180079c43  sub     rsp, 0B0h
0x180079c4a  mov     rax, cs:__security_cookie
0x180079c51  xor     rax, rsp
0x180079c54  mov     [rbp+57h+var_28], rax
0x180079c58  mov     rax, [rcx+8]
0x180079c5c  lea     rdi, WPP_GLOBAL_Control
0x180079c63  mov     r13, rcx
0x180079c66  xor     esi, esi
0x180079c68  mov     rcx, [rax+19F0h]; Process
0x180079c6f  test    rcx, rcx
0x180079c72  jz      short loc_180079C8D
0x180079c74  call    cs:__imp_GetProcessId
0x180079c7a  mov     rcx, [r13+8]
0x180079c7e  mov     r15d, eax
0x180079c81  mov     r12, [rcx+19F0h]
0x180079c88  jmp     loc_180079D45
0x180079c8d  cmp     [rax+2398h], rsi
0x180079c94  jz      loc_180079D3F
0x180079c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180079ca1  cmp     rcx, rdi
0x180079ca4  jz      short loc_180079CC1
0x180079ca6  test    byte ptr [rcx+1Ch], 2
0x180079caa  jz      short loc_180079CC1
0x180079cac  mov     rcx, [rcx+10h]
0x180079cb0  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079cb7  mov     edx, 36h ; '6'
0x180079cbc  call    WPP_SF_
0x180079cc1  mov     rcx, [r13+8]
0x180079cc5  lea     r8, [rbp+57h+Process]
0x180079cc9  mov     r9d, 8
0x180079ccf  mov     [rbp+57h+Process], rsi
0x180079cd3  mov     rcx, [rcx+2398h]
0x180079cda  lea     edx, [r9-7]
0x180079cde  call    cs:__imp_PssQuerySnapshot
0x180079ce4  mov     ebx, eax
0x180079ce6  test    eax, eax
0x180079ce8  jz      short loc_180079D2C
0x180079cea  jle     short loc_180079CF5
0x180079cec  movzx   ebx, ax
0x180079cef  or      ebx, 80070000h
0x180079cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180079cfc  cmp     rcx, rdi
0x180079cff  jz      loc_18007A147
0x180079d05  test    byte ptr [rcx+1Ch], 1
0x180079d09  jz      loc_18007A147
0x180079d0f  mov     rcx, [rcx+10h]
0x180079d13  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079d1a  mov     edx, 37h ; '7'
0x180079d1f  mov     r9d, ebx
0x180079d22  call    WPP_SF_d
0x180079d27  jmp     loc_18007A147
0x180079d2c  mov     rcx, [rbp+57h+Process]; Process
0x180079d30  call    cs:__imp_GetProcessId
0x180079d36  mov     r12, [rbp+57h+Process]
0x180079d3a  mov     r15d, eax
0x180079d3d  jmp     short loc_180079D45
0x180079d3f  mov     r15d, esi
0x180079d42  mov     r12, rsi
0x180079d45  xor     edx, edx; th32ProcessID
0x180079d47  lea     ecx, [rdx+4]; dwFlags
0x180079d4a  call    cs:__imp_CreateToolhelp32Snapshot
0x180079d50  mov     rbx, rax
0x180079d53  mov     [rbp+57h+var_88], rax
0x180079d57  inc     rax
0x180079d5a  cmp     rax, 1
0x180079d5e  jbe     loc_18007A0FF
0x180079d64  xorps   xmm0, xmm0
0x180079d67  mov     qword ptr [rbp+57h+te.tpDeltaPri], rsi
0x180079d6b  lea     rdx, [rbp+57h+te]; lpte
0x180079d6f  mov     [rbp+57h+te.dwSize], 1Ch
0x180079d76  mov     rcx, rbx; hSnapshot
0x180079d79  movdqu  xmmword ptr [rbp+57h+te.cntUsage], xmm0
0x180079d7e  call    cs:__imp_Thread32First
0x180079d84  test    eax, eax
0x180079d86  jnz     short loc_180079DC1
0x180079d88  call    cs:__imp_GetLastError
0x180079d8e  mov     ebx, eax
0x180079d90  test    eax, eax
0x180079d92  jle     short loc_180079D9D
0x180079d94  movzx   ebx, ax
0x180079d97  or      ebx, 80070000h
0x180079d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079da4  cmp     rcx, rdi
0x180079da7  jz      loc_18007A13E
0x180079dad  test    byte ptr [rcx+1Ch], 1
0x180079db1  jz      loc_18007A13E
0x180079db7  mov     edx, 39h ; '9'
0x180079dbc  jmp     loc_18007A12B
0x180079dc1  lea     rcx, [rbp+57h+lpBuffer]
0x180079dc5  call    ??$make_unique@U_TEB@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_TEB@@U?$default_delete@U_TEB@@@utl@@@0@XZ; utl::make_unique<_TEB,,0>(void)
0x180079dca  mov     rdi, [rbp+57h+lpBuffer]
0x180079dce  test    rdi, rdi
0x180079dd1  jz      loc_18007A0BE
0x180079dd7  cmp     [rbp+57h+te.th32OwnerProcessID], r15d
0x180079ddb  jnz     loc_18007A050
0x180079de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180079de8  lea     rax, WPP_GLOBAL_Control
0x180079def  cmp     rcx, rax
0x180079df2  jz      short loc_180079E13
0x180079df4  test    byte ptr [rcx+1Ch], 4
0x180079df8  jz      short loc_180079E13
0x180079dfa  mov     r9d, [rbp+57h+te.th32ThreadID]
0x180079dfe  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079e05  mov     rcx, [rcx+10h]
0x180079e09  mov     edx, 3Bh ; ';'
0x180079e0e  call    WPP_SF_d
0x180079e13  mov     r8d, [rbp+57h+te.th32ThreadID]; dwThreadId
0x180079e17  xorps   xmm0, xmm0
0x180079e1a  xor     edx, edx; bInheritHandle
0x180079e1c  movups  [rbp+57h+ThreadInformation], xmm0
0x180079e20  movups  [rbp+57h+var_68], xmm0
0x180079e24  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180079e27  movups  [rbp+57h+var_58], xmm0
0x180079e2b  call    cs:__imp_OpenThread
0x180079e31  mov     [rbp+57h+var_A0], rax
0x180079e35  lea     rcx, [rax+1]
0x180079e39  cmp     rcx, 1
0x180079e3d  jbe     loc_180079FFA
0x180079e43  mov     r9d, 30h ; '0'; ThreadInformationLength
0x180079e49  mov     [rsp+0D0h+ReturnLength], 0; ReturnLength
0x180079e52  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x180079e56  xor     edx, edx; ThreadInformationClass
0x180079e58  mov     rcx, rax; ThreadHandle
0x180079e5b  call    cs:__imp_NtQueryInformationThread
0x180079e61  test    eax, eax
0x180079e63  jns     short loc_180079E96
0x180079e65  mov     esi, eax
0x180079e67  bts     esi, 1Ch
0x180079e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180079e72  lea     rax, WPP_GLOBAL_Control
0x180079e79  cmp     rcx, rax
0x180079e7c  jz      loc_18007A047
0x180079e82  test    byte ptr [rcx+1Ch], 2
0x180079e86  jz      loc_18007A047
0x180079e8c  mov     edx, 3Dh ; '='
0x180079e91  jmp     loc_18007A02D
0x180079e96  mov     rdx, qword ptr [rbp+57h+ThreadInformation+8]; lpBaseAddress
0x180079e9a  test    rdx, rdx
0x180079e9d  jnz     short loc_180079EE3
0x180079e9f  mov     esi, 80004005h
0x180079ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180079eab  lea     rax, WPP_GLOBAL_Control
0x180079eb2  cmp     rcx, rax
0x180079eb5  jz      loc_18007A047
0x180079ebb  test    byte ptr [rcx+1Ch], 1
0x180079ebf  jz      loc_18007A047
0x180079ec5  mov     r9d, [rbp+57h+te.th32ThreadID]
0x180079ec9  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079ed0  mov     rcx, [rcx+10h]
0x180079ed4  mov     edx, 3Eh ; '>'
0x180079ed9  call    WPP_SF_d
0x180079ede  jmp     loc_18007A047
0x180079ee3  mov     r9d, 1870h; nSize
0x180079ee9  mov     [rsp+0D0h+ReturnLength], 0; lpNumberOfBytesRead
0x180079ef2  mov     r8, rdi; lpBuffer
0x180079ef5  mov     rcx, r12; hProcess
0x180079ef8  call    cs:__imp_ReadProcessMemory
0x180079efe  xor     ecx, ecx
0x180079f00  test    eax, eax
0x180079f02  jnz     short loc_180079F44
0x180079f04  call    cs:__imp_GetLastError
0x180079f0a  mov     esi, eax
0x180079f0c  test    eax, eax
0x180079f0e  jle     short loc_180079F19
0x180079f10  movzx   esi, ax
0x180079f13  or      esi, 80070000h
0x180079f19  mov     rcx, cs:WPP_GLOBAL_Control
0x180079f20  lea     rax, WPP_GLOBAL_Control
0x180079f27  cmp     rcx, rax
0x180079f2a  jz      loc_18007A047
0x180079f30  test    byte ptr [rcx+1Ch], 2
0x180079f34  jz      loc_18007A047
0x180079f3a  mov     edx, 3Fh ; '?'
0x180079f3f  jmp     loc_18007A02D
0x180079f44  cmp     [rdi+78h], rcx
0x180079f48  jz      loc_18007A047
0x180079f4e  mov     rdx, qword ptr [rbp+57h+ThreadInformation+8]
0x180079f52  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180079f56  mov     [rbp+57h+Buffer], rcx
0x180079f5a  add     rdx, 860h; lpBaseAddress
0x180079f61  mov     [rsp+0D0h+ReturnLength], rcx; lpNumberOfBytesRead
0x180079f66  mov     r9d, 8; nSize
0x180079f6c  mov     rcx, r12; hProcess
0x180079f6f  call    cs:__imp_ReadProcessMemory
0x180079f75  test    eax, eax
0x180079f77  jnz     short loc_180079FB6
0x180079f79  call    cs:__imp_GetLastError
0x180079f7f  mov     esi, eax
0x180079f81  test    eax, eax
0x180079f83  jle     short loc_180079F8E
0x180079f85  movzx   esi, ax
0x180079f88  or      esi, 80070000h
0x180079f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180079f95  lea     rax, WPP_GLOBAL_Control
0x180079f9c  cmp     rcx, rax
0x180079f9f  jz      loc_18007A047
0x180079fa5  test    byte ptr [rcx+1Ch], 2
0x180079fa9  jz      loc_18007A047
0x180079faf  mov     edx, 40h ; '@'
0x180079fb4  jmp     short loc_18007A02D
0x180079fb6  mov     r8, [rbp+57h+Buffer]; unsigned __int64
0x180079fba  mov     r9d, 30h ; '0'; unsigned int
0x180079fc0  mov     rcx, [r13+8]; this
0x180079fc4  mov     edx, r15d; unsigned int
0x180079fc7  mov     dword ptr [rsp+0D0h+ReturnLength], 0; unsigned int
0x180079fcf  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x180079fd4  mov     esi, eax
0x180079fd6  test    eax, eax
0x180079fd8  jns     short loc_18007A047
0x180079fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180079fe1  lea     rax, WPP_GLOBAL_Control
0x180079fe8  cmp     rcx, rax
0x180079feb  jz      short loc_18007A047
0x180079fed  test    byte ptr [rcx+1Ch], 1
0x180079ff1  jz      short loc_18007A047
0x180079ff3  mov     edx, 41h ; 'A'
0x180079ff8  jmp     short loc_18007A02D
0x180079ffa  call    cs:__imp_GetLastError
0x18007a000  mov     esi, eax
0x18007a002  test    eax, eax
0x18007a004  jle     short loc_18007A00F
0x18007a006  movzx   esi, ax
0x18007a009  or      esi, 80070000h
0x18007a00f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a016  lea     rax, WPP_GLOBAL_Control
0x18007a01d  cmp     rcx, rax
0x18007a020  jz      short loc_18007A047
0x18007a022  test    byte ptr [rcx+1Ch], 2
0x18007a026  jz      short loc_18007A047
0x18007a028  mov     edx, 3Ch ; '<'
0x18007a02d  mov     eax, [rbp+57h+te.th32ThreadID]
0x18007a030  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18007a037  mov     rcx, [rcx+10h]
0x18007a03b  mov     r9d, esi
0x18007a03e  mov     dword ptr [rsp+0D0h+ReturnLength], eax
0x18007a042  call    WPP_SF_Dd
0x18007a047  lea     rcx, [rbp+57h+var_A0]
0x18007a04b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18007a050  lea     rdx, [rbp+57h+te]; lpte
0x18007a054  mov     rcx, rbx; hSnapshot
0x18007a057  call    cs:__imp_Thread32Next
0x18007a05d  test    eax, eax
0x18007a05f  jnz     loc_180079DD7
0x18007a065  call    cs:__imp_GetLastError
0x18007a06b  cmp     eax, 12h
0x18007a06e  jz      short loc_18007A0A5
0x18007a070  call    cs:__imp_GetLastError
0x18007a076  mov     ebx, eax
0x18007a078  test    eax, eax
0x18007a07a  jle     short loc_18007A085
0x18007a07c  movzx   ebx, ax
0x18007a07f  or      ebx, 80070000h
0x18007a085  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a08c  lea     rax, WPP_GLOBAL_Control
0x18007a093  cmp     rcx, rax
0x18007a096  jz      short loc_18007A0F4
0x18007a098  test    byte ptr [rcx+1Ch], 1
0x18007a09c  jz      short loc_18007A0F4
0x18007a09e  mov     edx, 42h ; 'B'
0x18007a0a3  jmp     short loc_18007A0E1
0x18007a0a5  lea     rcx, [rbp+57h+lpBuffer]
0x18007a0a9  call    ??1?$unique_ptr@U_TEB@@U?$default_delete@U_TEB@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<_TEB,utl::default_delete<_TEB>>::~unique_ptr<_TEB,utl::default_delete<_TEB>>(void)
0x18007a0ae  lea     rcx, [rbp+57h+var_88]
0x18007a0b2  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18007a0b7  mov     eax, esi
0x18007a0b9  jmp     loc_18007A149
0x18007a0be  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a0c5  lea     rax, WPP_GLOBAL_Control
0x18007a0cc  mov     ebx, 8007000Eh
0x18007a0d1  cmp     rcx, rax
0x18007a0d4  jz      short loc_18007A0F4
0x18007a0d6  test    byte ptr [rcx+1Ch], 1
0x18007a0da  jz      short loc_18007A0F4
0x18007a0dc  mov     edx, 3Ah ; ':'
0x18007a0e1  mov     rcx, [rcx+10h]
0x18007a0e5  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18007a0ec  mov     r9d, ebx
0x18007a0ef  call    WPP_SF_d
0x18007a0f4  lea     rcx, [rbp+57h+lpBuffer]
0x18007a0f8  call    ??1?$unique_ptr@U_TEB@@U?$default_delete@U_TEB@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<_TEB,utl::default_delete<_TEB>>::~unique_ptr<_TEB,utl::default_delete<_TEB>>(void)
0x18007a0fd  jmp     short loc_18007A13E
0x18007a0ff  call    cs:__imp_GetLastError
0x18007a105  mov     ebx, eax
0x18007a107  test    eax, eax
0x18007a109  jle     short loc_18007A114
0x18007a10b  movzx   ebx, ax
0x18007a10e  or      ebx, 80070000h
0x18007a114  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a11b  cmp     rcx, rdi
0x18007a11e  jz      short loc_18007A13E
0x18007a120  test    byte ptr [rcx+1Ch], 1
0x18007a124  jz      short loc_18007A13E
  ... truncated ...
```
