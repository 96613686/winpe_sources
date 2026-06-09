# SyncMessageThread

- ea: `0x18000b720`
- end: `0x18000b8d6`
- name: `SyncMessageThread`
- size: `438`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b720`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000b74d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000b74d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b741`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b865`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b766`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b766`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b774`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b774`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b837`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b837`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8c1`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b7f1`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b7f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b8a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b8a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b853`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b853`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b883`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b883`
- `FLTLIB!FilterGetMessage` at `0x18000b7c1`
- `FLTLIB!FilterGetMessage` at `0x18000b7c1`

## pseudocode

```c
__int64 __fastcall SyncMessageThread(PVOID Parameter)
{
  struct _FILTER_MESSAGE_HEADER *v1; // rdi
  DWORD v2; // esi
  HANDLE CurrentThread; // rax
  HANDLE ProcessHeap; // rax
  signed int v5; // ebx
  HRESULT Message; // eax
  signed int v7; // eax
  HANDLE v8; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  signed int LastError; // eax
  HANDLE v11; // rax
  struct _OVERLAPPED Overlapped; // [rsp+20h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+78h] [rbp+30h] BYREF

  v1 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  NumberOfBytesTransferred = 0;
  v2 = 4096;
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 1);
  if ( !dword_180028BE8 )
    return 0;
  do
  {
    if ( !v1 )
    {
      ProcessHeap = GetProcessHeap();
      v1 = (struct _FILTER_MESSAGE_HEADER *)HeapAlloc(ProcessHeap, 0, v2);
      v5 = v1 == 0 ? 8 : 0;
      if ( !v1 )
        v5 |= 0x80070000;
      if ( v5 < 0 )
        break;
    }
    NumberOfBytesTransferred = 0;
    memset(&Overlapped, 0, sizeof(Overlapped));
    Message = FilterGetMessage(*(&hPort + 1), v1, v2, &Overlapped);
    v5 = Message;
    if ( Message >= 0 )
    {
      NumberOfBytesTransferred = Overlapped.InternalHigh;
LABEL_17:
      ThreadpoolWork = CreateThreadpoolWork(SyncWorkThread, v1, 0);
      if ( ThreadpoolWork )
      {
        v5 = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v5 < 0 )
      {
        if ( ThreadpoolWork )
          CloseThreadpoolWork(ThreadpoolWork);
        break;
      }
      SubmitThreadpoolWork(ThreadpoolWork);
      v2 = 4096;
LABEL_23:
      v1 = 0;
      continue;
    }
    if ( Message == -2147023899 )
    {
      if ( GetOverlappedResult(*(&hPort + 1), &Overlapped, &NumberOfBytesTransferred, 1) )
      {
        v5 = 0;
      }
      else
      {
        v7 = GetLastError();
        v5 = v7;
        if ( v7 > 0 )
          v5 = (unsigned __int16)v7 | 0x80070000;
      }
    }
    else if ( Message == -2147024890 )
    {
      break;
    }
    if ( v5 == -2147024774 )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v1);
      v2 = NumberOfBytesTransferred;
      goto LABEL_23;
    }
    if ( v5 >= 0 )
      goto LABEL_17;
  }
  while ( dword_180028BE8 );
  if ( v1 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v1);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b720  push    rbp
0x18000b722  push    rbx
0x18000b723  push    rsi
0x18000b724  push    rdi
0x18000b725  mov     rbp, rsp
0x18000b728  sub     rsp, 48h
0x18000b72c  xorps   xmm0, xmm0
0x18000b72f  xor     edi, edi
0x18000b731  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000b735  mov     [rbp+NumberOfBytesTransferred], edi
0x18000b738  mov     esi, 1000h
0x18000b73d  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000b741  call    cs:__imp_GetCurrentThread
0x18000b747  mov     rcx, rax; hThread
0x18000b74a  lea     edx, [rdi+1]; nPriority
0x18000b74d  call    cs:__imp_SetThreadPriority
0x18000b753  mov     eax, cs:dword_180028BE8
0x18000b759  test    eax, eax
0x18000b75b  jz      loc_18000B8C9
0x18000b761  test    rdi, rdi
0x18000b764  jnz     short loc_18000B79E
0x18000b766  call    cs:__imp_GetProcessHeap
0x18000b76c  mov     r8d, esi; dwBytes
0x18000b76f  xor     edx, edx; dwFlags
0x18000b771  mov     rcx, rax; hHeap
0x18000b774  call    cs:__imp_HeapAlloc
0x18000b77a  mov     rdi, rax
0x18000b77d  neg     rax
0x18000b780  sbb     ebx, ebx
0x18000b782  not     ebx
0x18000b784  and     ebx, 8
0x18000b787  mov     eax, ebx
0x18000b789  or      eax, 80070000h
0x18000b78e  test    rdi, rdi
0x18000b791  cmovz   ebx, eax
0x18000b794  test    ebx, ebx
0x18000b796  jz      short loc_18000B79E
0x18000b798  js      loc_18000B8AE
0x18000b79e  mov     rcx, qword ptr cs:hPort+8; hPort
0x18000b7a5  lea     r9, [rbp+Overlapped]; lpOverlapped
0x18000b7a9  xorps   xmm0, xmm0
0x18000b7ac  mov     [rbp+NumberOfBytesTransferred], 0
0x18000b7b3  mov     r8d, esi; dwMessageBufferSize
0x18000b7b6  mov     rdx, rdi; lpMessageBuffer
0x18000b7b9  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000b7bd  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000b7c1  call    cs:__imp_FilterGetMessage
0x18000b7c7  mov     ebx, eax
0x18000b7c9  test    eax, eax
0x18000b7cb  js      short loc_18000B7D5
0x18000b7cd  mov     eax, dword ptr [rbp+Overlapped.InternalHigh]
0x18000b7d0  mov     [rbp+NumberOfBytesTransferred], eax
0x18000b7d3  jmp     short loc_18000B846
0x18000b7d5  cmp     eax, 800703E5h
0x18000b7da  jnz     short loc_18000B816
0x18000b7dc  mov     rcx, qword ptr cs:hPort+8; hFile
0x18000b7e3  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18000b7e7  mov     r9d, 1; bWait
0x18000b7ed  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18000b7f1  call    cs:__imp_GetOverlappedResult
0x18000b7f7  test    eax, eax
0x18000b7f9  jnz     short loc_18000B812
0x18000b7fb  call    cs:__imp_GetLastError
0x18000b801  mov     ebx, eax
0x18000b803  test    eax, eax
0x18000b805  jle     short loc_18000B821
0x18000b807  movzx   ebx, ax
0x18000b80a  or      ebx, 80070000h
0x18000b810  jmp     short loc_18000B821
0x18000b812  xor     ebx, ebx
0x18000b814  jmp     short loc_18000B821
0x18000b816  cmp     eax, 80070006h
0x18000b81b  jz      loc_18000B8AE
0x18000b821  cmp     ebx, 8007007Ah
0x18000b827  jnz     short loc_18000B842
0x18000b829  call    cs:__imp_GetProcessHeap
0x18000b82f  mov     r8, rdi; lpMem
0x18000b832  xor     edx, edx; dwFlags
0x18000b834  mov     rcx, rax; hHeap
0x18000b837  call    cs:__imp_HeapFree
0x18000b83d  mov     esi, [rbp+NumberOfBytesTransferred]
0x18000b840  jmp     short loc_18000B88E
0x18000b842  test    ebx, ebx
0x18000b844  js      short loc_18000B890
0x18000b846  xor     r8d, r8d; pcbe
0x18000b849  lea     rcx, SyncWorkThread; pfnwk
0x18000b850  mov     rdx, rdi; pv
0x18000b853  call    cs:__imp_CreateThreadpoolWork
0x18000b859  mov     rsi, rax
0x18000b85c  test    rax, rax
0x18000b85f  jz      short loc_18000B865
0x18000b861  xor     ebx, ebx
0x18000b863  jmp     short loc_18000B87A
0x18000b865  call    cs:__imp_GetLastError
0x18000b86b  mov     ebx, eax
0x18000b86d  test    eax, eax
0x18000b86f  jle     short loc_18000B87A
0x18000b871  movzx   ebx, ax
0x18000b874  or      ebx, 80070000h
0x18000b87a  test    ebx, ebx
0x18000b87c  jz      short loc_18000B880
0x18000b87e  js      short loc_18000B8A0
0x18000b880  mov     rcx, rsi; pwk
0x18000b883  call    cs:__imp_SubmitThreadpoolWork
0x18000b889  mov     esi, 1000h
0x18000b88e  xor     edi, edi
0x18000b890  mov     eax, cs:dword_180028BE8
0x18000b896  test    eax, eax
0x18000b898  jnz     loc_18000B761
0x18000b89e  jmp     short loc_18000B8AE
0x18000b8a0  test    rsi, rsi
0x18000b8a3  jz      short loc_18000B8AE
0x18000b8a5  mov     rcx, rsi; pwk
0x18000b8a8  call    cs:__imp_CloseThreadpoolWork
0x18000b8ae  test    rdi, rdi
0x18000b8b1  jz      short loc_18000B8CB
0x18000b8b3  call    cs:__imp_GetProcessHeap
0x18000b8b9  mov     r8, rdi; lpMem
0x18000b8bc  xor     edx, edx; dwFlags
0x18000b8be  mov     rcx, rax; hHeap
0x18000b8c1  call    cs:__imp_HeapFree
0x18000b8c7  jmp     short loc_18000B8CB
0x18000b8c9  xor     ebx, ebx
0x18000b8cb  mov     eax, ebx
0x18000b8cd  add     rsp, 48h
0x18000b8d1  pop     rdi
0x18000b8d2  pop     rsi
0x18000b8d3  pop     rbx
0x18000b8d4  pop     rbp
0x18000b8d5  retn
```
