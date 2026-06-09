# UmepCleanupCompletionThread

- ea: `0x140086f78`
- end: `0x140087020`
- name: `UmepCleanupCompletionThread`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400872d0`

## callees

- `0x140086f78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140086fcd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140086fcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086fac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086fe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087003`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086fac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086fe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087003`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x140086f95`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x140086f95`

## pseudocode

```c
void UmepCleanupCompletionThread()
{
  if ( qword_14021FE28 )
  {
    if ( !PostQueuedCompletionStatus(ExistingCompletionPort, 0, 0, 0) )
    {
      CloseHandle(ExistingCompletionPort);
      ExistingCompletionPort = 0;
    }
    WaitForSingleObject(qword_14021FE28, 0xFFFFFFFF);
    CloseHandle(qword_14021FE28);
    qword_14021FE28 = 0;
  }
  if ( ExistingCompletionPort )
  {
    CloseHandle(ExistingCompletionPort);
    ExistingCompletionPort = 0;
  }
}

```

## disassembly

```asm
0x140086f78  sub     rsp, 28h
0x140086f7c  cmp     cs:qword_14021FE28, 0
0x140086f84  jz      short loc_140086FF7
0x140086f86  mov     rcx, cs:ExistingCompletionPort; CompletionPort
0x140086f8d  xor     r9d, r9d; lpOverlapped
0x140086f90  xor     r8d, r8d; dwCompletionKey
0x140086f93  xor     edx, edx; dwNumberOfBytesTransferred
0x140086f95  call    cs:__imp_PostQueuedCompletionStatus
0x140086f9c  nop     dword ptr [rax+rax+00h]
0x140086fa1  test    eax, eax
0x140086fa3  jnz     short loc_140086FC3
0x140086fa5  mov     rcx, cs:ExistingCompletionPort; hObject
0x140086fac  call    cs:__imp_CloseHandle
0x140086fb3  nop     dword ptr [rax+rax+00h]
0x140086fb8  mov     cs:ExistingCompletionPort, 0
0x140086fc3  mov     rcx, cs:qword_14021FE28; hHandle
0x140086fca  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140086fcd  call    cs:__imp_WaitForSingleObject
0x140086fd4  nop     dword ptr [rax+rax+00h]
0x140086fd9  mov     rcx, cs:qword_14021FE28; hObject
0x140086fe0  call    cs:__imp_CloseHandle
0x140086fe7  nop     dword ptr [rax+rax+00h]
0x140086fec  mov     cs:qword_14021FE28, 0
0x140086ff7  mov     rcx, cs:ExistingCompletionPort; hObject
0x140086ffe  test    rcx, rcx
0x140087001  jz      short loc_14008701A
0x140087003  call    cs:__imp_CloseHandle
0x14008700a  nop     dword ptr [rax+rax+00h]
0x14008700f  mov     cs:ExistingCompletionPort, 0
0x14008701a  add     rsp, 28h
0x14008701e  retn
```
