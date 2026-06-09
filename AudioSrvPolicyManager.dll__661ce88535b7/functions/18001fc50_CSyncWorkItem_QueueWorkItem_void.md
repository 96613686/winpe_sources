# CSyncWorkItem::QueueWorkItem(void)

- ea: `0x18001fc50`
- end: `0x18001fc8a`
- name: `?QueueWorkItem@CSyncWorkItem@@UEAAJXZ`
- size: `58`
- prototype: `__int64 __fastcall(ULONG_PTR dwCompletionKey)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001fc50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc6d`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18001fc63`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18001fc63`

## pseudocode

```c
signed int __fastcall CSyncWorkItem::QueueWorkItem(ULONG_PTR dwCompletionKey)
{
  signed int result; // eax

  if ( PostQueuedCompletionStatus(g_WorkerEventPort, 0, dwCompletionKey, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001fc50  sub     rsp, 28h
0x18001fc54  mov     r8, rcx; dwCompletionKey
0x18001fc57  xor     r9d, r9d; lpOverlapped
0x18001fc5a  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x18001fc61  xor     edx, edx; dwNumberOfBytesTransferred
0x18001fc63  call    cs:__imp_PostQueuedCompletionStatus
0x18001fc69  test    eax, eax
0x18001fc6b  jnz     short loc_18001FC86
0x18001fc6d  call    cs:__imp_GetLastError
0x18001fc73  test    eax, eax
0x18001fc75  jg      short loc_18001FC7C
0x18001fc77  add     rsp, 28h
0x18001fc7b  retn
0x18001fc7c  movzx   eax, ax
0x18001fc7f  or      eax, 80070000h
0x18001fc84  jmp     short loc_18001FC77
0x18001fc86  xor     eax, eax
0x18001fc88  jmp     short loc_18001FC77
```
