# RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b_

- ea: `0x18008c3c0`
- end: `0x18008c43f`
- name: `RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b___`
- size: `127`
- prototype: `HRESULT __fastcall(RemoveClipboardDataObject::__l14::<lambda_acbbe6d18a978d7bf2cb06affbc8b61b> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800255a8`

## callees

- `0x18008c3c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c400`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008c41b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008c41b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008c3f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008c3f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008c42f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008c42f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008c426`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008c426`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b_(
        RemoveClipboardDataObject::__l14::<lambda_acbbe6d18a978d7bf2cb06affbc8b61b> operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_8a24869d9b18bed7b3421b4230e9e935> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  void **pDataObjInMTA; // [rsp+40h] [rbp+8h] BYREF
  HRESULT hr; // [rsp+48h] [rbp+10h] BYREF

  pDataObjInMTA = operation.pDataObjInMTA;
  hr = 0;
  hrHandlerOverOperation.operation = (RemoveClipboardDataObject::__l14::<lambda_acbbe6d18a978d7bf2cb06affbc8b61b> *)&pDataObjInMTA;
  hrHandlerOverOperation.hr = &hr;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_fd5f26b17dc0b306889b51c5fa24ff59_, &hrHandlerOverOperation, 0);
  v2 = v1;
  if ( v1 )
  {
    SubmitThreadpoolWork(v1);
    WaitForThreadpoolWorkCallbacks(v2, 0);
    CloseThreadpoolWork(v2);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
  return (unsigned int)hr;
}

```

## disassembly

```asm
0x18008c3c0  mov     r11, rsp
0x18008c3c3  mov     [r11+8], operation
0x18008c3c7  push    rbx
0x18008c3c8  sub     rsp, 30h
0x18008c3cc  lea     rax, [r11+8]
0x18008c3d0  mov     [rsp+38h+hr], 0
0x18008c3d8  mov     [r11-18h], rax
0x18008c3dc  lea     rdx, [r11-18h]; pv
0x18008c3e0  lea     rax, [r11+10h]
0x18008c3e4  xor     r8d, r8d; pcbe
0x18008c3e7  lea     operation, MTAThreadPoolWorker__lambda_fd5f26b17dc0b306889b51c5fa24ff59___; pfnwk
0x18008c3ee  mov     [r11-10h], rax
0x18008c3f2  call    cs:__imp_CreateThreadpoolWork
0x18008c3f8  mov     rbx, rax
0x18008c3fb  test    rax, rax
0x18008c3fe  jnz     short loc_18008C418
0x18008c400  call    cs:__imp_GetLastError
0x18008c406  test    eax, eax
0x18008c408  jle     short loc_18008C412
0x18008c40a  movzx   eax, ax
0x18008c40d  or      eax, 80070000h
0x18008c412  mov     [rsp+38h+hr], eax
0x18008c416  jmp     short loc_18008C435
0x18008c418  mov     operation, rbx; pwk
0x18008c41b  call    cs:__imp_SubmitThreadpoolWork
0x18008c421  xor     edx, edx; fCancelPendingCallbacks
0x18008c423  mov     operation, rbx; pwk
0x18008c426  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008c42c  mov     operation, rbx; pwk
0x18008c42f  call    cs:__imp_CloseThreadpoolWork
0x18008c435  mov     eax, [rsp+38h+hr]
0x18008c439  add     rsp, 30h
0x18008c43d  pop     rbx
0x18008c43e  retn
```
