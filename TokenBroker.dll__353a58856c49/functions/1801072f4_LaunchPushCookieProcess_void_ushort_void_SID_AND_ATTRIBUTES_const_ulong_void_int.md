# LaunchPushCookieProcess(void *,ushort *,void *,_SID_AND_ATTRIBUTES * const,ulong,void *,int)

- ea: `0x1801072f4`
- end: `0x1801074e1`
- name: `?LaunchPushCookieProcess@@YAKPEAXPEAG0QEAU_SID_AND_ATTRIBUTES@@K0H@Z`
- size: `493`
- prototype: `__int64 __fastcall(HANDLE hToken, LPWSTR lpCommandLine, void *, struct _SID_AND_ATTRIBUTES *const, unsigned int, void *lpEnvironment, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180106908`
- `0x180106b44`
- `0x1801074e8`
- `0x18010769c`

## callees

- `0x18008f234`
- `0x1801072f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180107368`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1801073b0`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180107368`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1801073b0`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180107476`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180107476`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1801073ff`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1801073ff`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801074bc`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801074bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18010749a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18010749a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801073ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801073ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801074a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801074af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801074a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801074af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801074c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801074c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18010738e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18010738e`

## pseudocode

```c
__int64 __fastcall LaunchPushCookieProcess(
        HANDLE hToken,
        LPWSTR lpCommandLine,
        void *a3,
        struct _SID_AND_ATTRIBUTES *const a4,
        unsigned int a5,
        void *lpEnvironment,
        int a7)
{
  DWORD LastError; // ebx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v12; // rdi
  int v13; // esi
  struct _PROC_THREAD_ATTRIBUTE_LIST *v14; // rax
  __int128 Value; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+70h] [rbp-90h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v20; // [rsp+F8h] [rbp-8h]
  ULONG_PTR Size; // [rsp+160h] [rbp+60h] BYREF

  LastError = 0;
  Size = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  v17 = 0;
  v12 = 0;
  Value = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( a3 )
  {
    v13 = 1;
    if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
        goto LABEL_19;
      LastError = 0;
    }
    v14 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)LocalAlloc(0x40u, Size);
    v12 = v14;
    if ( !v14 )
    {
      LastError = 8;
      goto LABEL_19;
    }
    if ( !InitializeProcThreadAttributeList(v14, 1u, 0, &Size) )
    {
      LastError = GetLastError();
      goto LABEL_19;
    }
    v17 = a5;
    *((_QWORD *)&Value + 1) = a4;
    *(_QWORD *)&Value = a3;
    if ( !UpdateProcThreadAttribute(v12, 0, 0x20009u, &Value, 0x18u, 0, 0) )
    {
      LastError = GetLastError();
LABEL_18:
      DeleteProcThreadAttributeList(v12);
      goto LABEL_19;
    }
  }
  else
  {
    v13 = 0;
  }
  StartupInfo.cb = 112;
  v20 = v12;
  if ( CreateProcessAsUserW(
         hToken,
         0,
         lpCommandLine,
         0,
         0,
         0,
         (a3 != 0 ? 0x80000 : 0) | (lpEnvironment != 0 ? 0x400 : 0),
         lpEnvironment,
         0,
         &StartupInfo,
         &ProcessInformation) )
  {
    if ( a7 )
      WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
    CloseHandle(ProcessInformation.hThread);
    CloseHandle(ProcessInformation.hProcess);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( v13 )
    goto LABEL_18;
LABEL_19:
  LocalFree(v12);
  return LastError;
}

```

## disassembly

```asm
0x1801072f4  push    rbp
0x1801072f6  push    rbx
0x1801072f7  push    rsi
0x1801072f8  push    rdi
0x1801072f9  push    r12
0x1801072fb  push    r13
0x1801072fd  push    r14
0x1801072ff  push    r15
0x180107301  lea     rbp, [rsp-8]
0x180107306  sub     rsp, 108h
0x18010730d  xor     ebx, ebx
0x18010730f  mov     r14, r8
0x180107312  mov     r12, rdx
0x180107315  mov     [rbp+40h+Size], rbx
0x180107319  mov     r13, rcx
0x18010731c  mov     qword ptr [rbp+40h+StartupInfo.cb], rbx
0x180107320  xorps   xmm0, xmm0
0x180107323  lea     rcx, [rbp+40h+StartupInfo.lpReserved]; void *
0x180107327  xor     eax, eax
0x180107329  lea     r8d, [rbx+68h]; Size
0x18010732d  xor     edx, edx; Val
0x18010732f  mov     [rsp+140h+var_D0], rax
0x180107334  mov     r15, r9
0x180107337  mov     edi, ebx
0x180107339  movups  [rsp+140h+Value], xmm0
0x18010733e  call    memset_0
0x180107343  xor     eax, eax
0x180107345  xorps   xmm0, xmm0
0x180107348  mov     qword ptr [rbp+40h+ProcessInformation.dwProcessId], rax
0x18010734c  movups  xmmword ptr [rsp+140h+ProcessInformation.hProcess], xmm0
0x180107351  test    r14, r14
0x180107354  jz      loc_180107416
0x18010735a  lea     esi, [rbx+1]
0x18010735d  xor     r8d, r8d; dwFlags
0x180107360  mov     edx, esi; dwAttributeCount
0x180107362  lea     r9, [rbp+40h+Size]; lpSize
0x180107366  xor     ecx, ecx; lpAttributeList
0x180107368  call    cs:__imp_InitializeProcThreadAttributeList
0x18010736e  test    eax, eax
0x180107370  jnz     short loc_180107385
0x180107372  call    cs:__imp_GetLastError
0x180107378  mov     ebx, eax
0x18010737a  cmp     eax, 7Ah ; 'z'
0x18010737d  jnz     loc_1801074C2
0x180107383  xor     ebx, ebx
0x180107385  mov     rdx, [rbp+40h+Size]; uBytes
0x180107389  mov     ecx, 40h ; '@'; uFlags
0x18010738e  call    cs:__imp_LocalAlloc
0x180107394  mov     rdi, rax
0x180107397  test    rax, rax
0x18010739a  jnz     short loc_1801073A4
0x18010739c  lea     ebx, [rax+8]
0x18010739f  jmp     loc_1801074C2
0x1801073a4  lea     r9, [rbp+40h+Size]; lpSize
0x1801073a8  xor     r8d, r8d; dwFlags
0x1801073ab  mov     edx, esi; dwAttributeCount
0x1801073ad  mov     rcx, rdi; lpAttributeList
0x1801073b0  call    cs:__imp_InitializeProcThreadAttributeList
0x1801073b6  test    eax, eax
0x1801073b8  jnz     short loc_1801073C7
0x1801073ba  call    cs:__imp_GetLastError
0x1801073c0  mov     ebx, eax
0x1801073c2  jmp     loc_1801074C2
0x1801073c7  mov     eax, [rbp+40h+arg_20]
0x1801073ca  lea     r9, [rsp+140h+Value]; lpValue
0x1801073cf  mov     [rsp+140h+lpReturnSize], rbx; lpReturnSize
0x1801073d4  xor     edx, edx; dwFlags
0x1801073d6  mov     [rsp+140h+lpPreviousValue], rbx; lpPreviousValue
0x1801073db  mov     r8d, 20009h; Attribute
0x1801073e1  mov     rcx, rdi; lpAttributeList
0x1801073e4  mov     [rsp+140h+cbSize], 18h; cbSize
0x1801073ed  mov     dword ptr [rsp+140h+var_D0], eax
0x1801073f1  mov     qword ptr [rsp+140h+Value+8], r15
0x1801073f6  mov     qword ptr [rsp+140h+Value], r14
0x1801073fb  mov     dword ptr [rsp+140h+var_D0+4], ebx
0x1801073ff  call    cs:__imp_UpdateProcThreadAttribute
0x180107405  test    eax, eax
0x180107407  jnz     short loc_180107418
0x180107409  call    cs:__imp_GetLastError
0x18010740f  mov     ebx, eax
0x180107411  jmp     loc_1801074B9
0x180107416  mov     esi, ebx
0x180107418  mov     rdx, [rbp+40h+arg_28]
0x18010741c  mov     r8, r12; lpCommandLine
0x18010741f  mov     rax, rdx
0x180107422  mov     [rbp+40h+StartupInfo.cb], 70h ; 'p'
0x180107429  neg     rax
0x18010742c  mov     [rbp+40h+var_48], rdi
0x180107430  sbb     ecx, ecx
0x180107432  and     ecx, 400h
0x180107438  neg     r14
0x18010743b  sbb     eax, eax
0x18010743d  xor     r9d, r9d; lpProcessAttributes
0x180107440  and     eax, 80000h
0x180107445  or      ecx, eax
0x180107447  lea     rax, [rsp+140h+ProcessInformation]
0x18010744c  mov     [rsp+140h+lpProcessInformation], rax; lpProcessInformation
0x180107451  lea     rax, [rbp+40h+StartupInfo]
0x180107455  mov     [rsp+140h+lpStartupInfo], rax; lpStartupInfo
0x18010745a  mov     [rsp+140h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x18010745f  mov     [rsp+140h+lpEnvironment], rdx; lpEnvironment
0x180107464  xor     edx, edx; lpApplicationName
0x180107466  mov     dword ptr [rsp+140h+lpReturnSize], ecx; dwCreationFlags
0x18010746a  mov     rcx, r13; hToken
0x18010746d  mov     dword ptr [rsp+140h+lpPreviousValue], ebx; bInheritHandles
0x180107471  mov     [rsp+140h+cbSize], rbx; lpThreadAttributes
0x180107476  call    cs:__imp_CreateProcessAsUserW
0x18010747c  test    eax, eax
0x18010747e  jnz     short loc_18010748A
0x180107480  call    cs:__imp_GetLastError
0x180107486  mov     ebx, eax
0x180107488  jmp     short loc_1801074B5
0x18010748a  cmp     [rbp+40h+arg_30], ebx
0x180107490  jz      short loc_1801074A0
0x180107492  mov     rcx, [rsp+140h+ProcessInformation.hProcess]; hHandle
0x180107497  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18010749a  call    cs:__imp_WaitForSingleObject
0x1801074a0  mov     rcx, [rbp+40h+ProcessInformation.hThread]; hObject
0x1801074a4  call    cs:__imp_CloseHandle
0x1801074aa  mov     rcx, [rsp+140h+ProcessInformation.hProcess]; hObject
0x1801074af  call    cs:__imp_CloseHandle
0x1801074b5  test    esi, esi
0x1801074b7  jz      short loc_1801074C2
0x1801074b9  mov     rcx, rdi; lpAttributeList
0x1801074bc  call    cs:__imp_DeleteProcThreadAttributeList
0x1801074c2  mov     rcx, rdi; hMem
0x1801074c5  call    cs:__imp_LocalFree
0x1801074cb  mov     eax, ebx
0x1801074cd  add     rsp, 108h
0x1801074d4  pop     r15
0x1801074d6  pop     r14
0x1801074d8  pop     r13
0x1801074da  pop     r12
0x1801074dc  pop     rdi
0x1801074dd  pop     rsi
0x1801074de  pop     rbx
0x1801074df  pop     rbp
0x1801074e0  retn
```
