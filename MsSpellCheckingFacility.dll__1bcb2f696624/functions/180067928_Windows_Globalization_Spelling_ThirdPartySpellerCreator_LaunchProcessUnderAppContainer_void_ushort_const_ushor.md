# Windows::Globalization::Spelling::ThirdPartySpellerCreator::LaunchProcessUnderAppContainer(void *,ushort const *,ushort const *,ulong *)

- ea: `0x180067928`
- end: `0x180067b93`
- name: `?LaunchProcessUnderAppContainer@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAXPEBG1PEAK@Z`
- size: `619`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800666a4`

## callees

- `0x180061320`
- `0x180062314`
- `0x180067928`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067ab1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067ab1`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18006799f`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180067a18`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18006799f`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180067a18`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180067a85`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180067a85`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180067b07`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180067b07`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180067b51`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180067b51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800679db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067b57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800679db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067b57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800679e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800679e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067b65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800679af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800679bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800679af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800679bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067b11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067b33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067b43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067b33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067b43`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Globalization::Spelling::ThirdPartySpellerCreator::LaunchProcessUnderAppContainer(
        unsigned __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  signed int v5; // edi
  struct _PROC_THREAD_ATTRIBUTE_LIST *v7; // rbx
  signed int LastError; // eax
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v11; // rax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  HANDLE hThread; // rcx
  HANDLE v16; // rax
  ULONG_PTR Size; // [rsp+50h] [rbp-B0h] BYREF
  __int128 Value; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v23; // [rsp+F8h] [rbp-8h]
  WCHAR CommandLine[264]; // [rsp+100h] [rbp+0h] BYREF

  *a4 = 0;
  v5 = 0;
  memset_0(&StartupInfo, 0, 0x70u);
  v20 = 0;
  Size = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  Value = 0;
  if ( InitializeProcThreadAttributeList(0, 1u, 0, &Size) || GetLastError() == 122 )
    goto LABEL_6;
  v7 = 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_6:
    v9 = Size;
    ProcessHeap = GetProcessHeap();
    v11 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 0, v9);
    v7 = v11;
    if ( v11 )
    {
      if ( InitializeProcThreadAttributeList(v11, 1u, 0, &Size) || GetLastError() == 122 )
        goto LABEL_13;
      v12 = GetLastError();
      v5 = v12;
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
      if ( v5 >= 0 )
      {
LABEL_13:
        v20 = 0;
        Value = a1;
        if ( !UpdateProcThreadAttribute(v7, 0, 0x20009u, &Value, 0x18u, 0, 0) )
        {
          v13 = GetLastError();
          v5 = v13;
          if ( v13 > 0 )
            v5 = (unsigned __int16)v13 | 0x80070000;
        }
      }
    }
    else
    {
      v5 = -2147024882;
    }
  }
  _o_wcscpy_s(CommandLine, 260, L"msspellcheckinghost.exe");
  if ( v5 >= 0 )
  {
    StartupInfo.cb = 112;
    v23 = v7;
    if ( !CreateProcessW(0, CommandLine, 0, 0, 0, 0x80010u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v14 = GetLastError();
      v5 = v14;
      if ( v14 > 0 )
        v5 = (unsigned __int16)v14 | 0x80070000;
    }
  }
  hThread = ProcessInformation.hThread;
  *a4 = ProcessInformation.dwProcessId;
  if ( hThread )
    CloseHandle(hThread);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( v7 )
  {
    DeleteProcThreadAttributeList(v7);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v7);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180067928  mov     [rsp-8+arg_8], rbx
0x18006792d  push    rbp
0x18006792e  push    rsi
0x18006792f  push    rdi
0x180067930  push    r12
0x180067932  push    r14
0x180067934  lea     rbp, [rsp-220h]
0x18006793c  sub     rsp, 320h
0x180067943  mov     rax, cs:__security_cookie
0x18006794a  xor     rax, rsp
0x18006794d  mov     [rbp+240h+var_30], rax
0x180067954  mov     rsi, rcx
0x180067957  mov     dword ptr [r9], 0
0x18006795e  xor     edi, edi
0x180067960  lea     rcx, [rbp+240h+StartupInfo]; void *
0x180067964  xor     edx, edx; Val
0x180067966  mov     r14, r9
0x180067969  lea     r8d, [rdi+70h]; Size
0x18006796d  call    memset_0
0x180067972  xor     eax, eax
0x180067974  lea     r9, [rsp+340h+Size]; lpSize
0x180067979  xorps   xmm0, xmm0
0x18006797c  mov     qword ptr [rbp+240h+ProcessInformation.dwProcessId], rax
0x180067980  xorps   xmm1, xmm1
0x180067983  mov     [rsp+340h+var_2D8], rax
0x180067988  xor     r8d, r8d; dwFlags
0x18006798b  mov     [rsp+340h+Size], rax
0x180067990  lea     edx, [rdi+1]; dwAttributeCount
0x180067993  xor     ecx, ecx; lpAttributeList
0x180067995  movups  xmmword ptr [rsp+340h+ProcessInformation.hProcess], xmm0
0x18006799a  movups  [rsp+340h+Value], xmm1
0x18006799f  call    cs:__imp_InitializeProcThreadAttributeList
0x1800679a5  mov     r12d, 80070000h
0x1800679ab  test    eax, eax
0x1800679ad  jnz     short loc_1800679D6
0x1800679af  call    cs:__imp_GetLastError
0x1800679b5  cmp     eax, 7Ah ; 'z'
0x1800679b8  jz      short loc_1800679D6
0x1800679ba  xor     ebx, ebx
0x1800679bc  call    cs:__imp_GetLastError
0x1800679c2  mov     edi, eax
0x1800679c4  test    eax, eax
0x1800679c6  jle     short loc_1800679CE
0x1800679c8  movzx   edi, ax
0x1800679cb  or      edi, r12d
0x1800679ce  test    edi, edi
0x1800679d0  js      loc_180067AA1
0x1800679d6  mov     rbx, [rsp+340h+Size]
0x1800679db  call    cs:__imp_GetProcessHeap
0x1800679e1  mov     r8, rbx; dwBytes
0x1800679e4  xor     edx, edx; dwFlags
0x1800679e6  mov     rcx, rax; hHeap
0x1800679e9  call    cs:__imp_HeapAlloc
0x1800679ef  mov     rbx, rax
0x1800679f2  test    rax, rax
0x1800679f5  jnz     short loc_180067A01
0x1800679f7  mov     edi, 8007000Eh
0x1800679fc  jmp     loc_180067AA1
0x180067a01  test    edi, edi
0x180067a03  js      loc_180067AA1
0x180067a09  xor     r8d, r8d; dwFlags
0x180067a0c  lea     r9, [rsp+340h+Size]; lpSize
0x180067a11  mov     rcx, rbx; lpAttributeList
0x180067a14  lea     edx, [r8+1]; dwAttributeCount
0x180067a18  call    cs:__imp_InitializeProcThreadAttributeList
0x180067a1e  test    eax, eax
0x180067a20  jnz     short loc_180067A43
0x180067a22  call    cs:__imp_GetLastError
0x180067a28  cmp     eax, 7Ah ; 'z'
0x180067a2b  jz      short loc_180067A43
0x180067a2d  call    cs:__imp_GetLastError
0x180067a33  mov     edi, eax
0x180067a35  test    eax, eax
0x180067a37  jle     short loc_180067A3F
0x180067a39  movzx   edi, ax
0x180067a3c  or      edi, r12d
0x180067a3f  test    edi, edi
0x180067a41  js      short loc_180067AA1
0x180067a43  mov     [rsp+340h+lpReturnSize], 0; lpReturnSize
0x180067a4c  lea     r9, [rsp+340h+Value]; lpValue
0x180067a51  mov     [rsp+340h+lpPreviousValue], 0; lpPreviousValue
0x180067a5a  xor     edx, edx; dwFlags
0x180067a5c  mov     r8d, 20009h; Attribute
0x180067a62  mov     [rsp+340h+cbSize], 18h; cbSize
0x180067a6b  mov     rcx, rbx; lpAttributeList
0x180067a6e  mov     [rsp+340h+var_2D8], 0
0x180067a77  mov     qword ptr [rsp+340h+Value+8], 0
0x180067a80  mov     qword ptr [rsp+340h+Value], rsi
0x180067a85  call    cs:__imp_UpdateProcThreadAttribute
0x180067a8b  test    eax, eax
0x180067a8d  jnz     short loc_180067AA1
0x180067a8f  call    cs:__imp_GetLastError
0x180067a95  mov     edi, eax
0x180067a97  test    eax, eax
0x180067a99  jle     short loc_180067AA1
0x180067a9b  movzx   edi, ax
0x180067a9e  or      edi, r12d
0x180067aa1  lea     r8, aMsspellcheckin_0; "msspellcheckinghost.exe"
0x180067aa8  mov     edx, 104h
0x180067aad  lea     rcx, [rbp+240h+CommandLine]
0x180067ab1  call    cs:__imp__o_wcscpy_s
0x180067ab7  test    edi, edi
0x180067ab9  js      short loc_180067B23
0x180067abb  lea     rax, [rsp+340h+ProcessInformation]
0x180067ac0  mov     [rbp+240h+StartupInfo.cb], 70h ; 'p'
0x180067ac7  mov     [rsp+340h+lpProcessInformation], rax; lpProcessInformation
0x180067acc  lea     rdx, [rbp+240h+CommandLine]; lpCommandLine
0x180067ad0  lea     rax, [rbp+240h+StartupInfo]
0x180067ad4  mov     [rbp+240h+var_248], rbx
0x180067ad8  mov     [rsp+340h+lpStartupInfo], rax; lpStartupInfo
0x180067add  xor     r9d, r9d; lpThreadAttributes
0x180067ae0  mov     [rsp+340h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180067ae9  xor     r8d, r8d; lpProcessAttributes
0x180067aec  mov     [rsp+340h+lpReturnSize], 0; lpEnvironment
0x180067af5  xor     ecx, ecx; lpApplicationName
0x180067af7  mov     dword ptr [rsp+340h+lpPreviousValue], 80010h; dwCreationFlags
0x180067aff  mov     dword ptr [rsp+340h+cbSize], 0; bInheritHandles
0x180067b07  call    cs:__imp_CreateProcessW
0x180067b0d  test    eax, eax
0x180067b0f  jnz     short loc_180067B23
0x180067b11  call    cs:__imp_GetLastError
0x180067b17  mov     edi, eax
0x180067b19  test    eax, eax
0x180067b1b  jle     short loc_180067B23
0x180067b1d  movzx   edi, ax
0x180067b20  or      edi, r12d
0x180067b23  mov     rcx, [rsp+340h+ProcessInformation.hThread]; hObject
0x180067b28  mov     eax, [rbp+240h+ProcessInformation.dwProcessId]
0x180067b2b  mov     [r14], eax
0x180067b2e  test    rcx, rcx
0x180067b31  jz      short loc_180067B39
0x180067b33  call    cs:__imp_CloseHandle
0x180067b39  mov     rcx, [rsp+340h+ProcessInformation.hProcess]; hObject
0x180067b3e  test    rcx, rcx
0x180067b41  jz      short loc_180067B49
0x180067b43  call    cs:__imp_CloseHandle
0x180067b49  test    rbx, rbx
0x180067b4c  jz      short loc_180067B6B
0x180067b4e  mov     rcx, rbx; lpAttributeList
0x180067b51  call    cs:__imp_DeleteProcThreadAttributeList
0x180067b57  call    cs:__imp_GetProcessHeap
0x180067b5d  mov     r8, rbx; lpMem
0x180067b60  xor     edx, edx; dwFlags
0x180067b62  mov     rcx, rax; hHeap
0x180067b65  call    cs:__imp_HeapFree
0x180067b6b  mov     eax, edi
0x180067b6d  mov     rcx, [rbp+240h+var_30]
0x180067b74  xor     rcx, rsp; StackCookie
0x180067b77  call    __security_check_cookie
0x180067b7c  mov     rbx, [rsp+340h+arg_8]
0x180067b84  add     rsp, 320h
0x180067b8b  pop     r14
0x180067b8d  pop     r12
0x180067b8f  pop     rdi
0x180067b90  pop     rsi
0x180067b91  pop     rbp
0x180067b92  retn
```
