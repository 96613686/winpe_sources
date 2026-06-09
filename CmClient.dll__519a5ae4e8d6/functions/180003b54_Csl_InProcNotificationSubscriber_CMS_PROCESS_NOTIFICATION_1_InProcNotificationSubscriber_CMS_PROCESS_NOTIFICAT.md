# Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(void)

- ea: `0x180003b54`
- end: `0x180003bbe`
- name: `??1?$InProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c74`
- `0x180005788`

## callees

- `0x180003b54`
- `0x180006f7c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180003ba7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180003ba7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180003b84`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180003b84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b72`

## pseudocode

```c
void __fastcall Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(
        __int64 a1)
{
  __int64 v2; // rsi
  int v3; // ebx
  utl::_RefCountBase *v4; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    v3 = *(_DWORD *)(v2 + 100);
    if ( v3 == GetCurrentThreadId() )
      *(_BYTE *)(v2 + 105) = 1;
    else
      WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)a1, 1);
  }
  v4 = *(utl::_RefCountBase **)(a1 + 16);
  if ( v4 )
    utl::_RefCountBase::_DecStrong(v4);
  if ( *(_QWORD *)a1 )
    CloseThreadpoolWork(*(PTP_WORK *)a1);
}

```

## disassembly

```asm
0x180003b54  mov     [rsp+arg_0], rbx
0x180003b59  mov     [rsp+arg_8], rsi
0x180003b5e  push    rdi
0x180003b5f  sub     rsp, 20h
0x180003b63  mov     rdi, rcx
0x180003b66  mov     rsi, [rcx+8]
0x180003b6a  test    rsi, rsi
0x180003b6d  jz      short loc_180003B90
0x180003b6f  mov     ebx, [rsi+64h]
0x180003b72  call    cs:__imp_GetCurrentThreadId
0x180003b78  cmp     ebx, eax
0x180003b7a  jz      short loc_180003B8C
0x180003b7c  mov     edx, 1; fCancelPendingCallbacks
0x180003b81  mov     rcx, [rdi]; pwk
0x180003b84  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180003b8a  jmp     short loc_180003B90
0x180003b8c  mov     byte ptr [rsi+69h], 1
0x180003b90  mov     rcx, [rdi+10h]; this
0x180003b94  test    rcx, rcx
0x180003b97  jz      short loc_180003B9F
0x180003b99  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180003b9e  nop
0x180003b9f  mov     rcx, [rdi]; pwk
0x180003ba2  test    rcx, rcx
0x180003ba5  jz      short loc_180003BAE
0x180003ba7  call    cs:__imp_CloseThreadpoolWork
0x180003bad  nop
0x180003bae  mov     rbx, [rsp+28h+arg_0]
0x180003bb3  mov     rsi, [rsp+28h+arg_8]
0x180003bb8  add     rsp, 20h
0x180003bbc  pop     rdi
0x180003bbd  retn
```
