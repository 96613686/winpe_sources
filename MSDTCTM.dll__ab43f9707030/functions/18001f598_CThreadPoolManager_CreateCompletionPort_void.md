# CThreadPoolManager::CreateCompletionPort(void)

- ea: `0x18001f598`
- end: `0x18001f666`
- name: `?CreateCompletionPort@CThreadPoolManager@@AEAAJXZ`
- size: `206`
- prototype: `__int64 __fastcall(CThreadPoolManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800ac4a4`

## callees

- `0x1800063b0`
- `0x18001f598`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f608`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18001f5f6`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18001f5f6`

## string_xrefs

- `0x18001f5d1`: `com\complus\dtc\dtc\tipgw\commgr\src\threadpoolmanager.cpp`
- `0x18001f62d`: `com\complus\dtc\dtc\tipgw\commgr\src\threadpoolmanager.cpp`
- `0x18001f621`: `Failed to create TIP thread pool completion port, hr=%08x`
- `0x18001f5c2`: `CThreadPoolManager::CreateCompletionPort`
- `0x18001f5b7`: `Creating TIP thread pool completion port`

## pseudocode

```c
__int64 __fastcall CThreadPoolManager::CreateCompletionPort(CThreadPoolManager *this)
{
  signed int LastError; // eax
  unsigned int v2; // ebx

  if ( CThreadPoolManager::m_hCompletionPort )
    return 0;
  TraceStringInline(
    10,
    4,
    L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
    141,
    L"CThreadPoolManager::CreateCompletionPort",
    0,
    L"Creating TIP thread pool completion port");
  CThreadPoolManager::m_hCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  if ( CThreadPoolManager::m_hCompletionPort )
    return 0;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  TraceStringInline(
    10,
    1,
    L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
    156,
    L"CThreadPoolManager::CreateCompletionPort",
    0,
    L"Failed to create TIP thread pool completion port, hr=%08x",
    v2);
  return v2;
}

```

## disassembly

```asm
0x18001f598  mov     r11, rsp
0x18001f59b  mov     [r11+8], rbx
0x18001f59f  push    rbp
0x18001f5a0  sub     rsp, 40h
0x18001f5a4  cmp     cs:?m_hCompletionPort@CThreadPoolManager@@0PEAXEA, 0; void * CThreadPoolManager::m_hCompletionPort
0x18001f5ac  jnz     loc_18001F659
0x18001f5b2  mov     edx, 4
0x18001f5b7  lea     rax, aCreatingTipThr; "Creating TIP thread pool completion por"...
0x18001f5be  mov     [r11-18h], rax
0x18001f5c2  lea     rbp, aCthreadpoolman; "CThreadPoolManager::CreateCompletionPor"...
0x18001f5c9  mov     qword ptr [r11-20h], 0
0x18001f5d1  lea     r8, aComComplusDtcD_70; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x18001f5d8  mov     r9d, 8Dh
0x18001f5de  mov     [r11-28h], rbp
0x18001f5e2  lea     ecx, [rdx+6]
0x18001f5e5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f5ea  xor     r9d, r9d; NumberOfConcurrentThreads
0x18001f5ed  xor     r8d, r8d; CompletionKey
0x18001f5f0  xor     edx, edx; ExistingCompletionPort
0x18001f5f2  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18001f5f6  call    cs:__imp_CreateIoCompletionPort
0x18001f5fc  mov     cs:?m_hCompletionPort@CThreadPoolManager@@0PEAXEA, rax; void * CThreadPoolManager::m_hCompletionPort
0x18001f603  test    rax, rax
0x18001f606  jnz     short loc_18001F659
0x18001f608  call    cs:__imp_GetLastError
0x18001f60e  mov     ebx, eax
0x18001f610  test    eax, eax
0x18001f612  jle     short loc_18001F61D
0x18001f614  movzx   ebx, ax
0x18001f617  or      ebx, 80070000h
0x18001f61d  mov     [rsp+48h+var_10], ebx
0x18001f621  lea     rax, aFailedToCreate_1; "Failed to create TIP thread pool comple"...
0x18001f628  mov     [rsp+48h+var_18], rax
0x18001f62d  lea     r8, aComComplusDtcD_70; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x18001f634  mov     edx, 1
0x18001f639  mov     [rsp+48h+var_20], 0
0x18001f642  mov     r9d, 9Ch
0x18001f648  mov     [rsp+48h+var_28], rbp
0x18001f64d  lea     ecx, [rdx+9]
0x18001f650  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f655  mov     eax, ebx
0x18001f657  jmp     short loc_18001F65B
0x18001f659  xor     eax, eax
0x18001f65b  mov     rbx, [rsp+48h+arg_0]
0x18001f660  add     rsp, 40h
0x18001f664  pop     rbp
0x18001f665  retn
```
