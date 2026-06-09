# EventWorkerThread(void *)

- ea: `0x18001ec10`
- end: `0x18001ecc2`
- name: `?EventWorkerThread@@YAKPEAX@Z`
- size: `178`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f5f4`
- `0x18001ec10`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001ec1a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001ec1a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001ec97`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001ec97`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x18001ec5d`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x18001ec5d`

## string_xrefs

- `0x18001ecad`: `EventWorkerThread`

## pseudocode

```c
__int64 __fastcall EventWorkerThread(PVOID Parameter)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  unsigned __int64 v3; // rbx
  DWORD NumberOfBytesTransferred; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 CompletionKey; // [rsp+50h] [rbp+18h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+58h] [rbp+20h] BYREF

  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 )
  {
    AudPolicyLogError("EventWorkerThread", 130, v1);
    return v2;
  }
  else
  {
    while ( 1 )
    {
      do
      {
        CompletionKey = 0;
        NumberOfBytesTransferred = 0;
        Overlapped = 0;
      }
      while ( !GetQueuedCompletionStatus(
                 g_WorkerEventPort,
                 &NumberOfBytesTransferred,
                 &CompletionKey,
                 &Overlapped,
                 0xFFFFFFFF) );
      if ( NumberOfBytesTransferred == -1 )
        break;
      v3 = CompletionKey;
      (**(void (__fastcall ***)(unsigned __int64))CompletionKey)(CompletionKey);
      (*(void (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)v3 + 8LL))(v3, 1);
    }
    CoUninitialize();
    return 0;
  }
}

```

## disassembly

```asm
0x18001ec10  push    rbx
0x18001ec12  sub     rsp, 30h
0x18001ec16  xor     edx, edx; dwCoInit
0x18001ec18  xor     ecx, ecx; pvReserved
0x18001ec1a  call    cs:__imp_CoInitializeEx
0x18001ec20  mov     ebx, eax
0x18001ec22  test    eax, eax
0x18001ec24  jnz     loc_18001ECAA
0x18001ec2a  mov     [rsp+38h+arg_0], rdi
0x18001ec2f  xor     edi, edi
0x18001ec31  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x18001ec38  lea     r9, [rsp+38h+Overlapped]; lpOverlapped
0x18001ec3d  lea     r8, [rsp+38h+CompletionKey]; lpCompletionKey
0x18001ec42  mov     [rsp+38h+CompletionKey], rdi
0x18001ec47  lea     rdx, [rsp+38h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18001ec4c  mov     [rsp+38h+NumberOfBytesTransferred], edi
0x18001ec50  mov     [rsp+38h+Overlapped], rdi
0x18001ec55  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18001ec5d  call    cs:__imp_GetQueuedCompletionStatus
0x18001ec63  test    eax, eax
0x18001ec65  jz      short loc_18001EC31
0x18001ec67  cmp     [rsp+38h+NumberOfBytesTransferred], 0FFFFFFFFh
0x18001ec6c  jz      short loc_18001EC97
0x18001ec6e  mov     rbx, [rsp+38h+CompletionKey]
0x18001ec73  mov     rcx, rbx
0x18001ec76  mov     rax, [rbx]
0x18001ec79  mov     rax, [rax]
0x18001ec7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec81  mov     rax, [rbx]
0x18001ec84  mov     edx, 1
0x18001ec89  mov     rcx, rbx
0x18001ec8c  mov     rax, [rax+8]
0x18001ec90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec95  jmp     short loc_18001EC31
0x18001ec97  call    cs:__imp_CoUninitialize
0x18001ec9d  mov     rdi, [rsp+38h+arg_0]
0x18001eca2  xor     eax, eax
0x18001eca4  add     rsp, 30h
0x18001eca8  pop     rbx
0x18001eca9  retn
0x18001ecaa  mov     r8d, ebx; int
0x18001ecad  lea     rcx, aEventworkerthr; "EventWorkerThread"
0x18001ecb4  mov     edx, 82h; int
0x18001ecb9  call    ?AudPolicyLogError@@YAXPEBDHJ@Z; AudPolicyLogError(char const *,int,long)
0x18001ecbe  mov     eax, ebx
0x18001ecc0  jmp     short loc_18001ECA4
```
