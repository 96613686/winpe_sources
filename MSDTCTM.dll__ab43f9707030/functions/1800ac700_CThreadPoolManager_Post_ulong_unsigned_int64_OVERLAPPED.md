# CThreadPoolManager::Post(ulong,unsigned __int64,_OVERLAPPED *)

- ea: `0x1800ac700`
- end: `0x1800ac7dc`
- name: `?Post@CThreadPoolManager@@QEAAJK_KPEAU_OVERLAPPED@@@Z`
- size: `220`
- prototype: `int(CThreadPoolManager *__hidden this, unsigned int, unsigned __int64, struct _OVERLAPPED *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b6700`
- `0x1800b79cc`
- `0x1800b7c70`
- `0x1800b7d10`

## callees

- `0x1800063b0`
- `0x1800ac700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac778`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800ac76e`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800ac76e`

## string_xrefs

- `0x1800ac740`: `com\complus\dtc\dtc\tipgw\commgr\src\threadpoolmanager.cpp`
- `0x1800ac7a1`: `com\complus\dtc\dtc\tipgw\commgr\src\threadpoolmanager.cpp`
- `0x1800ac721`: `CThreadPoolManager::Post`
- `0x1800ac716`: `Posting to TIP thread pool completion port`
- `0x1800ac795`: `Failed to post to TIP thread pool completion port, hr=%08x`

## pseudocode

```c
__int64 __fastcall CThreadPoolManager::Post(CThreadPoolManager *this, __int64 a2, __int64 a3, struct _OVERLAPPED *a4)
{
  unsigned int v5; // ebx
  signed int LastError; // eax

  TraceStringInline(
    10,
    4,
    L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
    207,
    L"CThreadPoolManager::Post",
    0,
    L"Posting to TIP thread pool completion port");
  if ( !CThreadPoolManager::m_fThreadPoolReady )
  {
    v5 = -2147418113;
LABEL_7:
    TraceStringInline(
      10,
      1,
      L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
      231,
      L"CThreadPoolManager::Post",
      0,
      L"Failed to post to TIP thread pool completion port, hr=%08x",
      v5);
    return v5;
  }
  v5 = 0;
  if ( !PostQueuedCompletionStatus(CThreadPoolManager::m_hCompletionPort, 0, 2u, a4) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
      goto LABEL_7;
  }
  return v5;
}

```

## disassembly

```asm
0x1800ac700  mov     r11, rsp
0x1800ac703  mov     [r11+8], rbx
0x1800ac707  mov     [r11+10h], rdi
0x1800ac70b  push    r14
0x1800ac70d  sub     rsp, 40h
0x1800ac711  mov     edx, 4
0x1800ac716  lea     rax, aPostingToTipTh; "Posting to TIP thread pool completion p"...
0x1800ac71d  mov     [r11-18h], rax
0x1800ac721  lea     r14, aCthreadpoolman_0; "CThreadPoolManager::Post"
0x1800ac728  mov     rdi, r9
0x1800ac72b  mov     qword ptr [r11-20h], 0
0x1800ac733  mov     r9d, 0CFh
0x1800ac739  mov     [r11-28h], r14
0x1800ac73d  lea     ecx, [rdx+6]
0x1800ac740  lea     r8, aComComplusDtcD_70; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x1800ac747  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800ac74c  cmp     cs:?m_fThreadPoolReady@CThreadPoolManager@@0HA, 0; int CThreadPoolManager::m_fThreadPoolReady
0x1800ac753  jnz     short loc_1800AC75C
0x1800ac755  mov     ebx, 8000FFFFh
0x1800ac75a  jmp     short loc_1800AC791
0x1800ac75c  mov     rcx, cs:?m_hCompletionPort@CThreadPoolManager@@0PEAXEA; CompletionPort
0x1800ac763  xor     ebx, ebx
0x1800ac765  mov     r9, rdi; lpOverlapped
0x1800ac768  xor     edx, edx; dwNumberOfBytesTransferred
0x1800ac76a  lea     r8d, [rbx+2]; dwCompletionKey
0x1800ac76e  call    cs:__imp_PostQueuedCompletionStatus
0x1800ac774  test    eax, eax
0x1800ac776  jnz     short loc_1800AC7C9
0x1800ac778  call    cs:__imp_GetLastError
0x1800ac77e  mov     ebx, eax
0x1800ac780  test    eax, eax
0x1800ac782  jle     short loc_1800AC78D
0x1800ac784  movzx   ebx, ax
0x1800ac787  or      ebx, 80070000h
0x1800ac78d  test    ebx, ebx
0x1800ac78f  jns     short loc_1800AC7C9
0x1800ac791  mov     [rsp+48h+var_10], ebx
0x1800ac795  lea     rax, aFailedToPostTo; "Failed to post to TIP thread pool compl"...
0x1800ac79c  mov     [rsp+48h+var_18], rax
0x1800ac7a1  lea     r8, aComComplusDtcD_70; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x1800ac7a8  mov     edx, 1
0x1800ac7ad  mov     [rsp+48h+var_20], 0
0x1800ac7b6  mov     r9d, 0E7h
0x1800ac7bc  mov     [rsp+48h+var_28], r14
0x1800ac7c1  lea     ecx, [rdx+9]
0x1800ac7c4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800ac7c9  mov     rdi, [rsp+48h+arg_8]
0x1800ac7ce  mov     eax, ebx
0x1800ac7d0  mov     rbx, [rsp+48h+arg_0]
0x1800ac7d5  add     rsp, 40h
0x1800ac7d9  pop     r14
0x1800ac7db  retn
```
