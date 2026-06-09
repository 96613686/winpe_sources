# EventWorkerThread(void *)

- ea: `0x18001df10`
- end: `0x18001dfe0`
- name: `?EventWorkerThread@@YAKPEAX@Z`
- size: `208`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001df10`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x18001df7c`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x18001df7c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001df18`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001df18`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001dfc9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001dfc9`

## pseudocode

```c
HRESULT __fastcall EventWorkerThread(PVOID Parameter)
{
  HRESULT result; // eax
  unsigned __int64 v2; // rbx
  DWORD NumberOfBytesTransferred; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 CompletionKey; // [rsp+50h] [rbp+18h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+58h] [rbp+20h] BYREF

  result = CoInitializeEx(0, 0);
  if ( !result )
  {
    ((void (__fastcall *)(struct IUnknown *))g_DeviceEnumerator->lpVtbl->AddRef)(g_DeviceEnumerator);
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
      v2 = CompletionKey;
      (**(void (__fastcall ***)(unsigned __int64))CompletionKey)(CompletionKey);
      (*(void (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)v2 + 8LL))(v2, 1);
    }
    ((void (__fastcall *)(struct IUnknown *))g_DeviceEnumerator->lpVtbl->Release)(g_DeviceEnumerator);
    CoUninitialize();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001df10  sub     rsp, 38h
0x18001df14  xor     edx, edx; dwCoInit
0x18001df16  xor     ecx, ecx; pvReserved
0x18001df18  call    cs:__imp_CoInitializeEx
0x18001df1e  test    eax, eax
0x18001df20  jz      short loc_18001DF27
0x18001df22  add     rsp, 38h
0x18001df26  retn
0x18001df27  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18001df2e  mov     [rsp+38h+var_8], rdi
0x18001df33  mov     rax, [rcx]
0x18001df36  mov     rax, [rax+8]
0x18001df3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df3f  xor     edi, edi
0x18001df41  mov     [rsp+38h+arg_0], rbx
0x18001df46  nop     word ptr [rax+rax+00000000h]
0x18001df50  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x18001df57  lea     r9, [rsp+38h+Overlapped]; lpOverlapped
0x18001df5c  lea     r8, [rsp+38h+CompletionKey]; lpCompletionKey
0x18001df61  mov     [rsp+38h+CompletionKey], rdi
0x18001df66  lea     rdx, [rsp+38h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18001df6b  mov     [rsp+38h+NumberOfBytesTransferred], edi
0x18001df6f  mov     [rsp+38h+Overlapped], rdi
0x18001df74  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18001df7c  call    cs:__imp_GetQueuedCompletionStatus
0x18001df82  test    eax, eax
0x18001df84  jz      short loc_18001DF50
0x18001df86  cmp     [rsp+38h+NumberOfBytesTransferred], 0FFFFFFFFh
0x18001df8b  jz      short loc_18001DFB6
0x18001df8d  mov     rbx, [rsp+38h+CompletionKey]
0x18001df92  mov     rcx, rbx
0x18001df95  mov     rax, [rbx]
0x18001df98  mov     rax, [rax]
0x18001df9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfa0  mov     rax, [rbx]
0x18001dfa3  mov     edx, 1
0x18001dfa8  mov     rcx, rbx
0x18001dfab  mov     rax, [rax+8]
0x18001dfaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfb4  jmp     short loc_18001DF50
0x18001dfb6  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18001dfbd  mov     rax, [rcx]
0x18001dfc0  mov     rax, [rax+10h]
0x18001dfc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfc9  call    cs:__imp_CoUninitialize
0x18001dfcf  mov     rdi, [rsp+38h+var_8]
0x18001dfd4  xor     eax, eax
0x18001dfd6  mov     rbx, [rsp+38h+arg_0]
0x18001dfdb  jmp     loc_18001DF22
```
