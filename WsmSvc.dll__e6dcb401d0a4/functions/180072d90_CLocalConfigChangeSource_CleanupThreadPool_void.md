# CLocalConfigChangeSource::CleanupThreadPool(void)

- ea: `0x180072d90`
- end: `0x180072e57`
- name: `?CleanupThreadPool@CLocalConfigChangeSource@@AEAAXXZ`
- size: `199`
- prototype: `void __fastcall(CLocalConfigChangeSource *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18007126c`
- `0x1800ea460`

## callees

- `0x180072d90`

## import_xrefs

- `miutils!RtlTryAcquireFastLockExclusive` at `0x180072db3`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x180072db3`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x180072e1e`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x180072e1e`
- `miutils!RtlReleaseFastLockExclusive` at `0x180072dcb`
- `miutils!RtlReleaseFastLockExclusive` at `0x180072dcb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180072e38`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180072e38`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180072e2b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180072e2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180072e13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180072e13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180072e08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180072e08`

## pseudocode

```c
void __fastcall CLocalConfigChangeSource::CleanupThreadPool(CLocalConfigChangeSource *this)
{
  struct _TP_WAIT *v1; // rsi
  char *v2; // rdi
  struct _TP_CLEANUP_GROUP *v4; // rcx

  v1 = (struct _TP_WAIT *)*((_QWORD *)this + 20);
  v2 = (char *)this + 168;
  if ( !(unsigned int)RtlTryAcquireFastLockExclusive((char *)this + 168) )
    RtlQueueAcquireFastLockExclusive(v2);
  *((_QWORD *)this + 20) = 0;
  RtlReleaseFastLockExclusive(v2);
  if ( v1 )
  {
    SetThreadpoolWait(v1, 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
  }
  v4 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 19);
  if ( v4 )
  {
    CloseThreadpoolCleanupGroupMembers(v4, 1, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 19));
    *((_QWORD *)this + 19) = 0;
  }
  if ( *((_DWORD *)this + 36) )
    *((_DWORD *)this + 36) = 0;
}

```

## disassembly

```asm
0x180072d90  mov     [rsp+arg_0], rbx
0x180072d95  mov     [rsp+arg_8], rsi
0x180072d9a  push    rdi
0x180072d9b  sub     rsp, 20h
0x180072d9f  mov     rsi, [rcx+0A0h]
0x180072da6  lea     rdi, [rcx+0A8h]
0x180072dad  mov     rbx, rcx
0x180072db0  mov     rcx, rdi
0x180072db3  call    cs:__imp_RtlTryAcquireFastLockExclusive
0x180072db9  test    eax, eax
0x180072dbb  jz      short loc_180072E1B
0x180072dbd  mov     rcx, rdi
0x180072dc0  mov     qword ptr [rbx+0A0h], 0
0x180072dcb  call    cs:__imp_RtlReleaseFastLockExclusive
0x180072dd1  mov     edi, 1
0x180072dd6  test    rsi, rsi
0x180072dd9  jnz     short loc_180072E00
0x180072ddb  mov     rcx, [rbx+98h]; ptpcg
0x180072de2  test    rcx, rcx
0x180072de5  jnz     short loc_180072E26
0x180072de7  cmp     dword ptr [rbx+90h], 0
0x180072dee  jnz     short loc_180072E4B
0x180072df0  mov     rbx, [rsp+28h+arg_0]
0x180072df5  mov     rsi, [rsp+28h+arg_8]
0x180072dfa  add     rsp, 20h
0x180072dfe  pop     rdi
0x180072dff  retn
0x180072e00  xor     r8d, r8d; pftTimeout
0x180072e03  xor     edx, edx; h
0x180072e05  mov     rcx, rsi; pwa
0x180072e08  call    cs:__imp_SetThreadpoolWait
0x180072e0e  mov     edx, edi; fCancelPendingCallbacks
0x180072e10  mov     rcx, rsi; pwa
0x180072e13  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180072e19  jmp     short loc_180072DDB
0x180072e1b  mov     rcx, rdi
0x180072e1e  call    cs:__imp_RtlQueueAcquireFastLockExclusive
0x180072e24  jmp     short loc_180072DBD
0x180072e26  xor     r8d, r8d; pvCleanupContext
0x180072e29  mov     edx, edi; fCancelPendingCallbacks
0x180072e2b  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180072e31  mov     rcx, [rbx+98h]; ptpcg
0x180072e38  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180072e3e  mov     qword ptr [rbx+98h], 0
0x180072e49  jmp     short loc_180072DE7
0x180072e4b  mov     dword ptr [rbx+90h], 0
0x180072e55  jmp     short loc_180072DF0
```
