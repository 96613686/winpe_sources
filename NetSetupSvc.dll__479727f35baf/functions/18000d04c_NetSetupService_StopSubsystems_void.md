# NetSetupService::StopSubsystems(void)

- ea: `0x18000d04c`
- end: `0x18000d0dd`
- name: `?StopSubsystems@NetSetupService@@AEAAXXZ`
- size: `145`
- prototype: `void __fastcall(NetSetupService *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1800091c0`
- `0x18000affc`

## callees

- `0x18000d04c`
- `0x180010608`

## import_xrefs

- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x18000d06e`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x18000d06e`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x18000d085`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x18000d085`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000d0ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000d0ca`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18000d0a1`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18000d0a1`

## pseudocode

```c
void __fastcall NetSetupService::StopSubsystems(NetSetupService *this, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // ecx

  v5 = *((_DWORD *)this + 34) - 1;
  if ( v5 )
  {
    if ( v5 != 1 )
      goto LABEL_5;
    RpcServerInterfaceGroupDeactivate(*((_QWORD *)this + 18), 1, a3, a4);
    *((_DWORD *)this + 34) = 1;
  }
  RpcServerInterfaceGroupClose(*((_QWORD *)this + 18));
  *((_DWORD *)this + 34) = 0;
LABEL_5:
  if ( *((_QWORD *)this + 27) )
  {
    DevCloseObjectQuery();
    *((_QWORD *)this + 27) = 0;
  }
  NetSetupSvcWnf::Stop((NetSetupService *)((char *)this + 152));
  WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 21), 1);
  *((_DWORD *)this + 30) = 0;
}

```

## disassembly

```asm
0x18000d04c  push    rbx
0x18000d04e  sub     rsp, 20h
0x18000d052  mov     rbx, rcx
0x18000d055  mov     ecx, [rcx+88h]
0x18000d05b  sub     ecx, 1
0x18000d05e  jz      short loc_18000D07E
0x18000d060  cmp     ecx, 1
0x18000d063  jnz     short loc_18000D095
0x18000d065  mov     edx, ecx
0x18000d067  mov     rcx, [rbx+90h]
0x18000d06e  call    cs:__imp_RpcServerInterfaceGroupDeactivate
0x18000d074  mov     dword ptr [rbx+88h], 1
0x18000d07e  mov     rcx, [rbx+90h]
0x18000d085  call    cs:__imp_RpcServerInterfaceGroupClose
0x18000d08b  mov     dword ptr [rbx+88h], 0
0x18000d095  mov     rcx, [rbx+0D8h]
0x18000d09c  test    rcx, rcx
0x18000d09f  jz      short loc_18000D0B2
0x18000d0a1  call    cs:__imp_DevCloseObjectQuery
0x18000d0a7  mov     qword ptr [rbx+0D8h], 0
0x18000d0b2  lea     rcx, [rbx+98h]; this
0x18000d0b9  call    ?Stop@NetSetupSvcWnf@@QEAAXXZ; NetSetupSvcWnf::Stop(void)
0x18000d0be  mov     rcx, [rbx+0A8h]; pwk
0x18000d0c5  mov     edx, 1; fCancelPendingCallbacks
0x18000d0ca  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000d0d0  mov     dword ptr [rbx+78h], 0
0x18000d0d7  add     rsp, 20h
0x18000d0db  pop     rbx
0x18000d0dc  retn
```
