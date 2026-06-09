# Windows::PFIU::GetHistoryData(std::chrono::duration<int,std::ratio<60,1>>)

- ea: `0x1402b6a10`
- end: `0x1402b6efb`
- name: `?GetHistoryData@PFIU@Windows@@YA?AV?$tuple@V?$unique_ptr@T_PFIU_HISTORY_ENTRY@@Uprocess_heap_deleter@wil@@@wistd@@_KV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@V?$duration@HU?$ratio@$0DM@$00@std@@@45@@std@@V?$duration@HU?$ratio@$0DM@$00@std@@@chrono@4@@Z`
- size: `1259`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1402ad320`
- `0x1402b0474`
- `0x1402b1570`

## callees

- `0x14003c578`
- `0x14003fee4`
- `0x1400413a8`
- `0x140072498`
- `0x1400a5368`
- `0x14018b170`
- `0x1402b6a10`
- `0x14036efd0`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402b6abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402b6abd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1402b6baf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1402b6bd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1402b6baf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1402b6bd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1402b6be4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1402b6be4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1402b6bbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1402b6bbd`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x1402b6e3f`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x1402b6e3f`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1402b6ad8`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1402b6c88`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1402b6ccc`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1402b6d39`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1402b6ad8`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1402b6c88`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1402b6ccc`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1402b6d39`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1402b6b34`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1402b6b94`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1402b6def`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1402b6b34`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1402b6b94`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1402b6def`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1402b6a75`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1402b6a75`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1402b6aa0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1402b6aa0`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1402b6b6a`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1402b6b6a`

## string_xrefs

- `0x1402b6e94`: `C:\__w\1\s\src\orchestrator\system\windows\common\Time.cpp`
- `0x1402b6ea9`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\PFIUCommon.cpp`
- `0x1402b6ec2`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\PFIUCommon.cpp`
- `0x1402b6ed4`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\PFIUCommon.cpp`
- `0x1402b6ee9`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\PFIUCommon.cpp`
- `0x1402b6a6c`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::PFIU::GetHistoryData(__int64 a1, int a2)
{
  void *v4; // r14
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  bool v7; // r12
  SC_HANDLE v8; // rsi
  DWORD LastError; // eax
  unsigned __int64 v10; // rdx
  char v11; // al
  const char *v12; // r9
  unsigned int v13; // esi
  HANDLE ProcessHeap; // rax
  LPVOID v15; // rsi
  const char *v16; // r9
  void *v17; // r13
  HANDLE v18; // rax
  int v19; // eax
  unsigned __int64 v20; // rdx
  char v21; // al
  unsigned __int64 v22; // rdx
  char v23; // al
  unsigned __int64 v24; // rdx
  char v25; // al
  unsigned int pcbBytesNeeded; // [rsp+28h] [rbp-A9h]
  unsigned int v28[4]; // [rsp+48h] [rbp-89h] BYREF
  _QWORD v29[4]; // [rsp+58h] [rbp-79h] BYREF
  SC_HANDLE v30; // [rsp+88h] [rbp-49h]
  int v31; // [rsp+A8h] [rbp-29h] BYREF
  SIZE_T dwBytes; // [rsp+ACh] [rbp-25h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-19h] BYREF
  DWORD v34; // [rsp+C0h] [rbp-11h] BYREF
  SYSTEMTIME LocalTime; // [rsp+C8h] [rbp-9h]
  BYTE Buffer[16]; // [rsp+D8h] [rbp+7h] BYREF
  __int128 v37; // [rsp+E8h] [rbp+17h]
  int v38; // [rsp+F8h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  v4 = 0;
  *(_QWORD *)v28 = 0;
  dwBytes = 1;
  v31 = 0;
  LocalTime = 0;
  v5 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v6 = v5;
  v30 = v5;
  v7 = v5 != 0;
  if ( v5 )
  {
    v8 = OpenServiceW(v5, L"Sysmain", 4u);
    v29[0] = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      if ( LastError != 1060 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x34,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\PFIUCommon.cpp",
          (const char *)LastError,
          pcbBytesNeeded);
      *(_QWORD *)v28 = 0;
      GetSystemTimePreciseAsFileTime(v28);
      v10 = v28[0] + ((unsigned __int64)v28[1] << 32) - 116444736000000000LL;
      if ( a2 == 60 )
      {
        v11 = 0;
      }
      else
      {
        v11 = -1;
        if ( a2 <= 60 )
          v11 = 1;
      }
      if ( v11 < 0 )
        a2 = 60;
      *(_DWORD *)a1 = a2;
      *(_QWORD *)(a1 + 8) = v10;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      goto LABEL_47;
    }
    *(_OWORD *)Buffer = 0;
    v37 = 0;
    v38 = 0;
    v34 = 0;
    if ( !QueryServiceStatusEx(v8, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v34) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\PFIUCommon.cpp",
        v12);
    if ( ((*(_DWORD *)&Buffer[4] - 1) & 0xFFFFFFFD) == 0 )
    {
      *(_QWORD *)v28 = 0;
      GetSystemTimePreciseAsFileTime(v28);
      v22 = v28[0] + ((unsigned __int64)v28[1] << 32) - 116444736000000000LL;
      if ( a2 == 60 )
      {
        v23 = 0;
      }
      else
      {
        v23 = -1;
        if ( a2 <= 60 )
          v23 = 1;
      }
      if ( v23 < 0 )
        a2 = 60;
      *(_DWORD *)a1 = a2;
      *(_QWORD *)(a1 + 8) = v22;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      CloseServiceHandle(v8);
      goto LABEL_47;
    }
    CloseServiceHandle(v8);
  }
  v33 = 0;
  Windows::DockedHelpers::GetDockedSystem(&v33);
  do
  {
    v13 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v15 = HeapAlloc(ProcessHeap, 0, v13);
    v17 = v4;
    v4 = v15;
    *(_QWORD *)v28 = v15;
    if ( v17 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v17);
    }
    if ( !v15 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x49,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\PFIUCommon.cpp",
        v16);
    v19 = (*(__int64 (__fastcall **)(__int64, LPVOID, SIZE_T *, char *))(*(_QWORD *)v33 + 48LL))(
            v33,
            v15,
            &dwBytes,
            (char *)&dwBytes + 4);
    if ( !v19 )
      goto LABEL_23;
  }
  while ( v19 == -2147024774 );
  if ( v19 != -2147024699 && v19 != -2147023888 )
  {
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\PFIUCommon.cpp",
        (const char *)(unsigned int)v19,
        (int)&v31);
LABEL_23:
    v29[0] = L"PFIU minutesPerEntry was <= 0";
    v29[1] = 29;
    SystemInterface::Log<>(v29);
    *(_QWORD *)v28 = 0;
    GetSystemTimePreciseAsFileTime(v28);
    v20 = v28[0] + ((unsigned __int64)v28[1] << 32) - 116444736000000000LL;
    if ( a2 == 60 )
    {
      v21 = 0;
    }
    else
    {
      v21 = -1;
      if ( a2 <= 60 )
        v21 = 1;
    }
    if ( v21 < 0 )
      a2 = 60;
    *(_DWORD *)a1 = a2;
    *(_QWORD *)(a1 + 8) = v20;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)v28 = 0;
    *(_QWORD *)(a1 + 24) = v15;
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    goto LABEL_47;
  }
  *(_QWORD *)v28 = 0;
  GetSystemTimePreciseAsFileTime(v28);
  v24 = v28[0] + ((unsigned __int64)v28[1] << 32) - 116444736000000000LL;
  if ( a2 == 60 )
  {
    v25 = 0;
  }
  else
  {
    v25 = -1;
    if ( a2 <= 60 )
      v25 = 1;
  }
  if ( v25 < 0 )
    a2 = 60;
  *(_DWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = v24;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)v28 = 0;
  *(_QWORD *)(a1 + 24) = v15;
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
LABEL_47:
  if ( v7 )
    CloseServiceHandle(v6);
  return a1;
}

```

## disassembly

```asm
0x1402b6a10  mov     rax, rsp
0x1402b6a13  mov     [rax+10h], rbx
0x1402b6a17  mov     [rax+18h], rsi
0x1402b6a1b  mov     [rax+20h], rdi
0x1402b6a1f  push    rbp
0x1402b6a20  push    r12
0x1402b6a22  push    r13
0x1402b6a24  push    r14
0x1402b6a26  push    r15
0x1402b6a28  lea     rbp, [rax-5Fh]
0x1402b6a2c  sub     rsp, 100h
0x1402b6a33  mov     rax, cs:__security_cookie
0x1402b6a3a  xor     rax, rsp
0x1402b6a3d  mov     [rbp+57h+var_28], rax
0x1402b6a41  mov     ebx, edx
0x1402b6a43  mov     r15, rcx
0x1402b6a46  mov     qword ptr [rsp+120h+var_E0], rcx
0x1402b6a4b  xor     r14d, r14d
0x1402b6a4e  mov     qword ptr [rsp+120h+var_E0], r14
0x1402b6a53  lea     eax, [r14+1]
0x1402b6a57  mov     dword ptr [rbp+57h+dwBytes], eax
0x1402b6a5a  mov     dword ptr [rbp+57h+dwBytes+4], r14d
0x1402b6a5e  mov     [rbp+57h+var_80], r14d
0x1402b6a62  xorps   xmm0, xmm0
0x1402b6a65  movups  xmmword ptr [rbp+57h+LocalTime.wYear], xmm0
0x1402b6a69  mov     r8d, eax; dwDesiredAccess
0x1402b6a6c  lea     rdx, DatabaseName; "ServicesActive"
0x1402b6a73  xor     ecx, ecx; lpMachineName
0x1402b6a75  call    cs:__imp_OpenSCManagerW
0x1402b6a7b  mov     rdi, rax
0x1402b6a7e  mov     [rbp+57h+var_A0], rax
0x1402b6a82  test    rax, rax
0x1402b6a85  setnz   r12b
0x1402b6a89  test    rax, rax
0x1402b6a8c  jz      loc_1402B6B9A
0x1402b6a92  lea     r8d, [r14+4]; dwDesiredAccess
0x1402b6a96  lea     rdx, aSysmain; "Sysmain"
0x1402b6a9d  mov     rcx, rax; hSCManager
0x1402b6aa0  call    cs:__imp_OpenServiceW
0x1402b6aa6  mov     rsi, rax
0x1402b6aa9  mov     [rbp+57h+var_D0], rax
0x1402b6aad  test    rax, rax
0x1402b6ab0  setnz   r13b
0x1402b6ab4  test    rax, rax
0x1402b6ab7  jnz     loc_1402B6B3F
0x1402b6abd  call    cs:__imp_GetLastError
0x1402b6ac3  cmp     eax, 424h
0x1402b6ac8  jnz     loc_1402B6EBB
0x1402b6ace  mov     qword ptr [rsp+120h+var_E0], rsi
0x1402b6ad3  lea     rcx, [rsp+120h+var_E0]
0x1402b6ad8  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1402b6ade  mov     eax, [rsp+120h+var_E0+4]
0x1402b6ae2  shl     rax, 20h
0x1402b6ae6  mov     ecx, [rsp+120h+var_E0]
0x1402b6aea  mov     rdx, 0FE624E212AC18000h
0x1402b6af4  add     rdx, rax
0x1402b6af7  add     rdx, rcx
0x1402b6afa  lea     ecx, [rsi+3Ch]
0x1402b6afd  cmp     ebx, ecx
0x1402b6aff  jnz     short loc_1402B6B06
0x1402b6b01  mov     al, sil
0x1402b6b04  jmp     short loc_1402B6B15
0x1402b6b06  mov     eax, 0FFh
0x1402b6b0b  mov     r8d, 1
0x1402b6b11  cmovle  eax, r8d
0x1402b6b15  test    al, al
0x1402b6b17  cmovs   ebx, ecx
0x1402b6b1a  mov     [r15], ebx
0x1402b6b1d  mov     [r15+8], rdx
0x1402b6b21  mov     [r15+10h], rsi
0x1402b6b25  mov     [r15+18h], rsi
0x1402b6b29  test    r13b, r13b
0x1402b6b2c  jz      loc_1402B6DE7
0x1402b6b32  xor     ecx, ecx; hSCObject
0x1402b6b34  call    cs:__imp_CloseServiceHandle
0x1402b6b3a  jmp     loc_1402B6DE7
0x1402b6b3f  xorps   xmm0, xmm0
0x1402b6b42  xor     eax, eax
0x1402b6b44  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1402b6b48  movups  [rbp+57h+var_40], xmm0
0x1402b6b4c  mov     [rbp+57h+var_30], eax
0x1402b6b4f  mov     [rbp+57h+var_68], eax
0x1402b6b52  lea     rax, [rbp+57h+var_68]
0x1402b6b56  mov     [rsp+120h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1402b6b5b  mov     r9d, 24h ; '$'; cbBufSize
0x1402b6b61  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1402b6b65  xor     edx, edx; InfoLevel
0x1402b6b67  mov     rcx, rsi; hService
0x1402b6b6a  call    cs:__imp_QueryServiceStatusEx
0x1402b6b70  mov     rcx, [rbp+5Fh]; this
0x1402b6b74  test    eax, eax
0x1402b6b76  jz      loc_1402B6ED4
0x1402b6b7c  mov     eax, dword ptr [rbp+57h+Buffer+4]
0x1402b6b7f  dec     eax
0x1402b6b81  test    eax, 0FFFFFFFDh
0x1402b6b86  jz      loc_1402B6CBF
0x1402b6b8c  test    r13b, r13b
0x1402b6b8f  jz      short loc_1402B6B9A
0x1402b6b91  mov     rcx, rsi; hSCObject
0x1402b6b94  call    cs:__imp_CloseServiceHandle
0x1402b6b9a  mov     [rbp+57h+var_70], 0
0x1402b6ba2  lea     rcx, [rbp+57h+var_70]
0x1402b6ba6  call    ?GetDockedSystem@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedSystem@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedSystem(void)
0x1402b6bab  nop
0x1402b6bac  mov     esi, dword ptr [rbp+57h+dwBytes]
0x1402b6baf  call    cs:__imp_GetProcessHeap
0x1402b6bb5  mov     r8d, esi; dwBytes
0x1402b6bb8  xor     edx, edx; dwFlags
0x1402b6bba  mov     rcx, rax; hHeap
0x1402b6bbd  call    cs:__imp_HeapAlloc
0x1402b6bc3  mov     rsi, rax
0x1402b6bc6  mov     r13, r14
0x1402b6bc9  mov     r14, rax
0x1402b6bcc  mov     qword ptr [rsp+120h+var_E0], rax
0x1402b6bd1  test    r13, r13
0x1402b6bd4  jz      short loc_1402B6BEA
0x1402b6bd6  call    cs:__imp_GetProcessHeap
0x1402b6bdc  mov     rcx, rax; hHeap
0x1402b6bdf  mov     r8, r13; lpMem
0x1402b6be2  xor     edx, edx; dwFlags
0x1402b6be4  call    cs:__imp_HeapFree
0x1402b6bea  mov     rcx, [rbp+5Fh]; this
0x1402b6bee  xor     r13d, r13d
0x1402b6bf1  test    rsi, rsi
0x1402b6bf4  jz      loc_1402B6EA9
0x1402b6bfa  mov     rcx, [rbp+57h+var_70]
0x1402b6bfe  mov     rax, [rcx]
0x1402b6c01  lea     rdx, [rbp+57h+LocalTime]
0x1402b6c05  mov     [rsp+120h+var_F8], rdx
0x1402b6c0a  lea     rdx, [rbp+57h+var_80]
0x1402b6c0e  mov     [rsp+120h+pcbBytesNeeded], rdx; int
0x1402b6c13  lea     r9, [rbp+57h+dwBytes+4]
0x1402b6c17  lea     r8, [rbp+57h+dwBytes]
0x1402b6c1b  mov     rdx, rsi
0x1402b6c1e  mov     rax, [rax+30h]
0x1402b6c22  call    _guard_dispatch_icall
0x1402b6c27  test    eax, eax
0x1402b6c29  jz      short loc_1402B6C58
0x1402b6c2b  cmp     eax, 8007007Ah
0x1402b6c30  jz      loc_1402B6BAC
0x1402b6c36  cmp     eax, 800700C5h
0x1402b6c3b  jz      loc_1402B6D2F
0x1402b6c41  cmp     eax, 800703F0h
0x1402b6c46  jz      loc_1402B6D2F
0x1402b6c4c  mov     rcx, [rbp+5Fh]; this
0x1402b6c50  test    eax, eax
0x1402b6c52  js      loc_1402B6EE6
0x1402b6c58  cmp     [rbp+57h+var_80], r13d
0x1402b6c5c  ja      loc_1402B6E26
0x1402b6c62  lea     rax, aPfiuMinutesper_0; "PFIU minutesPerEntry was <= 0"
0x1402b6c69  mov     [rbp+57h+var_D0], rax
0x1402b6c6d  mov     [rbp+57h+var_C8], 1Dh
0x1402b6c75  lea     rcx, [rbp+57h+var_D0]
0x1402b6c79  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1402b6c7e  mov     qword ptr [rsp+120h+var_E0], r13
0x1402b6c83  lea     rcx, [rsp+120h+var_E0]
0x1402b6c88  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1402b6c8e  mov     eax, [rsp+120h+var_E0+4]
0x1402b6c92  shl     rax, 20h
0x1402b6c96  mov     ecx, [rsp+120h+var_E0]
0x1402b6c9a  mov     rdx, 0FE624E212AC18000h
0x1402b6ca4  add     rdx, rax
0x1402b6ca7  add     rdx, rcx
0x1402b6caa  mov     ecx, 3Ch ; '<'
0x1402b6caf  cmp     ebx, ecx
0x1402b6cb1  jnz     loc_1402B6DA9
0x1402b6cb7  mov     al, r13b
0x1402b6cba  jmp     loc_1402B6DB8
0x1402b6cbf  xor     r14d, r14d
0x1402b6cc2  mov     qword ptr [rsp+120h+var_E0], r14
0x1402b6cc7  lea     rcx, [rsp+120h+var_E0]
0x1402b6ccc  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1402b6cd2  mov     eax, [rsp+120h+var_E0+4]
0x1402b6cd6  shl     rax, 20h
0x1402b6cda  mov     ecx, [rsp+120h+var_E0]
0x1402b6cde  mov     rdx, 0FE624E212AC18000h
0x1402b6ce8  add     rdx, rax
0x1402b6ceb  add     rdx, rcx
0x1402b6cee  lea     ecx, [r14+3Ch]
0x1402b6cf2  cmp     ebx, ecx
0x1402b6cf4  jnz     short loc_1402B6CFB
0x1402b6cf6  mov     al, r14b
0x1402b6cf9  jmp     short loc_1402B6D0A
0x1402b6cfb  mov     eax, 0FFh
0x1402b6d00  mov     r8d, 1
0x1402b6d06  cmovle  eax, r8d
0x1402b6d0a  test    al, al
0x1402b6d0c  cmovs   ebx, ecx
0x1402b6d0f  mov     [r15], ebx
0x1402b6d12  mov     [r15+8], rdx
0x1402b6d16  mov     [r15+10h], r14
0x1402b6d1a  mov     [r15+18h], r14
0x1402b6d1e  test    r13b, r13b
0x1402b6d21  jz      loc_1402B6DE7
0x1402b6d27  mov     rcx, rsi
0x1402b6d2a  jmp     loc_1402B6B34
0x1402b6d2f  mov     qword ptr [rsp+120h+var_E0], r13
0x1402b6d34  lea     rcx, [rsp+120h+var_E0]
0x1402b6d39  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1402b6d3f  mov     eax, [rsp+120h+var_E0+4]
0x1402b6d43  shl     rax, 20h
0x1402b6d47  mov     ecx, [rsp+120h+var_E0]
0x1402b6d4b  mov     rdx, 0FE624E212AC18000h
0x1402b6d55  add     rdx, rax
0x1402b6d58  add     rdx, rcx
0x1402b6d5b  mov     ecx, 3Ch ; '<'
0x1402b6d60  cmp     ebx, ecx
0x1402b6d62  jnz     short loc_1402B6D69
0x1402b6d64  mov     al, r13b
0x1402b6d67  jmp     short loc_1402B6D78
0x1402b6d69  mov     eax, 0FFh
0x1402b6d6e  mov     r8d, 1
0x1402b6d74  cmovle  eax, r8d
0x1402b6d78  test    al, al
0x1402b6d7a  cmovs   ebx, ecx
0x1402b6d7d  mov     [r15], ebx
0x1402b6d80  mov     [r15+8], rdx
0x1402b6d84  mov     [r15+10h], r13
0x1402b6d88  mov     qword ptr [rsp+120h+var_E0], r13
0x1402b6d8d  mov     [r15+18h], rsi
0x1402b6d91  mov     rcx, [rbp+57h+var_70]
0x1402b6d95  test    rcx, rcx
0x1402b6d98  jz      short loc_1402B6DA7
0x1402b6d9a  mov     rax, [rcx]
0x1402b6d9d  mov     rax, [rax+10h]
0x1402b6da1  call    _guard_dispatch_icall
0x1402b6da6  nop
0x1402b6da7  jmp     short loc_1402B6DE7
0x1402b6da9  mov     eax, 0FFh
0x1402b6dae  mov     r8d, 1
0x1402b6db4  cmovle  eax, r8d
0x1402b6db8  test    al, al
0x1402b6dba  cmovs   ebx, ecx
0x1402b6dbd  mov     [r15], ebx
0x1402b6dc0  mov     [r15+8], rdx
0x1402b6dc4  mov     [r15+10h], r13
0x1402b6dc8  mov     qword ptr [rsp+120h+var_E0], r13
0x1402b6dcd  mov     [r15+18h], rsi
0x1402b6dd1  mov     rcx, [rbp+57h+var_70]
0x1402b6dd5  test    rcx, rcx
0x1402b6dd8  jz      short loc_1402B6DE7
0x1402b6dda  mov     rax, [rcx]
0x1402b6ddd  mov     rax, [rax+10h]
0x1402b6de1  call    _guard_dispatch_icall
0x1402b6de6  nop
0x1402b6de7  test    r12b, r12b
0x1402b6dea  jz      short loc_1402B6DF6
0x1402b6dec  mov     rcx, rdi; hSCObject
0x1402b6def  call    cs:__imp_CloseServiceHandle
0x1402b6df5  nop
0x1402b6df6  mov     rax, r15
0x1402b6df9  mov     rcx, [rbp+57h+var_28]
0x1402b6dfd  xor     rcx, rsp; StackCookie
0x1402b6e00  call    __security_check_cookie
0x1402b6e05  lea     r11, [rsp+120h+var_20]
0x1402b6e0d  mov     rbx, [r11+38h]
0x1402b6e11  mov     rsi, [r11+40h]
0x1402b6e15  mov     rdi, [r11+48h]
0x1402b6e19  mov     rsp, r11
0x1402b6e1c  pop     r15
0x1402b6e1e  pop     r14
0x1402b6e20  pop     r13
0x1402b6e22  pop     r12
0x1402b6e24  pop     rbp
0x1402b6e25  retn
0x1402b6e26  mov     r14d, dword ptr [rbp+57h+dwBytes+4]
0x1402b6e2a  xorps   xmm0, xmm0
0x1402b6e2d  movups  xmmword ptr [rbp+57h+UniversalTime.wYear], xmm0
0x1402b6e31  mov     rbx, [rbp+5Fh]
0x1402b6e35  lea     r8, [rbp+57h+UniversalTime]; lpUniversalTime
0x1402b6e39  lea     rdx, [rbp+57h+LocalTime]; lpLocalTime
0x1402b6e3d  xor     ecx, ecx; lpTimeZoneInformation
0x1402b6e3f  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x1402b6e45  test    eax, eax
0x1402b6e47  jz      short loc_1402B6E94
0x1402b6e49  movaps  xmm0, xmmword ptr [rbp+57h+UniversalTime.wYear]
0x1402b6e4d  movdqa  [rbp+57h+var_90], xmm0
0x1402b6e52  lea     rdx, [rbp+57h+var_90]
0x1402b6e56  lea     rcx, [rbp+57h+var_D0]
0x1402b6e5a  call    ?from_systemtime@Time@Windows@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBU_SYSTEMTIME@@@Z; Windows::Time::from_systemtime(_SYSTEMTIME const &)
0x1402b6e5f  mov     ecx, [rbp+57h+var_80]
0x1402b6e62  mov     [r15], ecx
0x1402b6e65  mov     rax, [rax]
0x1402b6e68  mov     [r15+8], rax
0x1402b6e6c  mov     [r15+10h], r14
0x1402b6e70  mov     qword ptr [rsp+120h+var_E0], r13
0x1402b6e75  mov     [r15+18h], rsi
0x1402b6e79  mov     rcx, [rbp+57h+var_70]
0x1402b6e7d  test    rcx, rcx
0x1402b6e80  jz      short loc_1402B6E8F
0x1402b6e82  mov     rax, [rcx]
0x1402b6e85  mov     rax, [rax+10h]
0x1402b6e89  call    _guard_dispatch_icall
0x1402b6e8e  nop
0x1402b6e8f  jmp     loc_1402B6DE7
0x1402b6e94  lea     r8, aCW1SSrcOrchest_110; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402b6e9b  mov     edx, 4Dh ; 'M'; void *
0x1402b6ea0  mov     rcx, rbx; this
0x1402b6ea3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1402b6ea9  lea     r8, aCW1SSrcOrchest_19; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
  ... truncated ...
```
