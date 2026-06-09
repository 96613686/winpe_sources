# MessageDispatcher::_Stop(void)

- ea: `0x18005bd88`
- end: `0x18005be1d`
- name: `?_Stop@MessageDispatcher@@SAXXZ`
- size: `149`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001424c`
- `0x180015cd8`

## callees

- `0x180018abc`
- `0x18005ae94`
- `0x18005bd88`
- `0x18005bf60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005bda3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005bda3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bdb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bdb1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005bdc3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005bdc3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005bdd0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005bdd0`

## pseudocode

```c
void MessageDispatcher::_Stop(void)
{
  __int64 v0; // rdi
  std::_Ref_count_base *v1; // rcx
  std::_Ref_count_base *v2[2]; // [rsp+20h] [rbp-18h] BYREF

  v0 = *(_QWORD *)MessageDispatcher::getInstance(v2);
  EnterCriticalSection((LPCRITICAL_SECTION)(v0 + 16));
  *(_BYTE *)(v0 + 56) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v0 + 16));
  CloseThreadpoolCleanupGroupMembers(*(PTP_CLEANUP_GROUP *)(v0 + 136), 0, 0);
  CloseThreadpoolCleanupGroup(*(PTP_CLEANUP_GROUP *)(v0 + 136));
  *(_QWORD *)(v0 + 136) = 0;
  v1 = v2[1];
  if ( v2[1] )
    std::_Ref_count_base::_Decref(v2[1]);
  *(_OWORD *)v2 = 0;
  std::shared_ptr<MessageDispatcher>::operator=(v1, v2);
  if ( v2[1] )
    std::_Ref_count_base::_Decref(v2[1]);
}

```

## disassembly

```asm
0x18005bd88  mov     [rsp+arg_0], rbx
0x18005bd8d  push    rdi
0x18005bd8e  sub     rsp, 30h
0x18005bd92  lea     rcx, [rsp+38h+var_18]
0x18005bd97  call    ?getInstance@MessageDispatcher@@CA?AV?$shared_ptr@VMessageDispatcher@@@std@@XZ; MessageDispatcher::getInstance(void)
0x18005bd9c  mov     rdi, [rax]
0x18005bd9f  lea     rcx, [rdi+10h]; lpCriticalSection
0x18005bda3  call    cs:__imp_EnterCriticalSection
0x18005bda9  lea     rcx, [rdi+10h]; lpCriticalSection
0x18005bdad  mov     byte ptr [rdi+38h], 0
0x18005bdb1  call    cs:__imp_LeaveCriticalSection
0x18005bdb7  mov     rcx, [rdi+88h]; ptpcg
0x18005bdbe  xor     r8d, r8d; pvCleanupContext
0x18005bdc1  xor     edx, edx; fCancelPendingCallbacks
0x18005bdc3  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18005bdc9  mov     rcx, [rdi+88h]; ptpcg
0x18005bdd0  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18005bdd6  mov     qword ptr [rdi+88h], 0
0x18005bde1  mov     rcx, [rsp+38h+var_18+8]; this
0x18005bde6  test    rcx, rcx
0x18005bde9  jz      short loc_18005BDF0
0x18005bdeb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005bdf0  xorps   xmm0, xmm0
0x18005bdf3  lea     rdx, [rsp+38h+var_18]
0x18005bdf8  movdqu  xmmword ptr [rsp+38h+var_18], xmm0
0x18005bdfe  call    ??4?$shared_ptr@VMessageDispatcher@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MessageDispatcher>::operator=(std::shared_ptr<MessageDispatcher> &&)
0x18005be03  mov     rcx, [rsp+38h+var_18+8]; this
0x18005be08  test    rcx, rcx
0x18005be0b  jz      short loc_18005BE12
0x18005be0d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005be12  mov     rbx, [rsp+38h+arg_0]
0x18005be17  add     rsp, 30h
0x18005be1b  pop     rdi
0x18005be1c  retn
```
