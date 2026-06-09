# SharedSocket::HandleRetryTriggerCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *)

- ea: `0x180027f10`
- end: `0x180027f8f`
- name: `?HandleRetryTriggerCallback@SharedSocket@@CAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z`
- size: `127`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800267d8`
- `0x180027f10`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027f26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027f26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f7e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180027f74`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180027f74`

## pseudocode

```c
void __fastcall SharedSocket::HandleRetryTriggerCallback(__int64 a1, __int64 a2, __int64 a3)
{
  if ( a3 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a3 + 40));
    if ( *(_QWORD *)(a3 + 80) && !*(_BYTE *)(a3 + 208) )
    {
      if ( *(_DWORD *)(a3 + 240) >= 2u )
        *(_DWORD *)(a3 + 116) = 4;
      (**(void (__fastcall ***)(__int64))a3)(a3);
      SocketBrokerContext::NotifyApp(*(_QWORD *)(a3 + 80), a3, 0, *(unsigned int *)(a3 + 116));
      SubmitThreadpoolWork(*(PTP_WORK *)(a3 + 256));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a3 + 40));
  }
}

```

## disassembly

```asm
0x180027f10  test    r8, r8
0x180027f13  jz      short locret_180027F8E
0x180027f15  mov     [rsp+arg_0], rbx
0x180027f1a  push    rdi
0x180027f1b  sub     rsp, 20h
0x180027f1f  lea     rcx, [r8+28h]; lpCriticalSection
0x180027f23  mov     rbx, r8
0x180027f26  call    cs:__imp_EnterCriticalSection
0x180027f2c  cmp     qword ptr [rbx+50h], 0
0x180027f31  jz      short loc_180027F7A
0x180027f33  cmp     byte ptr [rbx+0D0h], 0
0x180027f3a  jnz     short loc_180027F7A
0x180027f3c  cmp     dword ptr [rbx+0F0h], 2
0x180027f43  jb      short loc_180027F4C
0x180027f45  mov     dword ptr [rbx+74h], 4
0x180027f4c  mov     rax, [rbx]
0x180027f4f  mov     rcx, rbx
0x180027f52  mov     rax, [rax]
0x180027f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f5a  mov     r9d, [rbx+74h]
0x180027f5e  xor     r8d, r8d
0x180027f61  mov     rcx, [rbx+50h]
0x180027f65  mov     rdx, rbx
0x180027f68  call    ?NotifyApp@SocketBrokerContext@@QEAAXPEAVSharedSocket@@KW4_SOCKET_BROKER_TRIGGER_REASON@@@Z; SocketBrokerContext::NotifyApp(SharedSocket *,ulong,_SOCKET_BROKER_TRIGGER_REASON)
0x180027f6d  mov     rcx, [rbx+100h]; pwk
0x180027f74  call    cs:__imp_SubmitThreadpoolWork
0x180027f7a  lea     rcx, [rbx+28h]; lpCriticalSection
0x180027f7e  call    cs:__imp_LeaveCriticalSection
0x180027f84  mov     rbx, [rsp+28h+arg_0]
0x180027f89  add     rsp, 20h
0x180027f8d  pop     rdi
0x180027f8e  retn
```
