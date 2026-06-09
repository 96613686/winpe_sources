# Broker::RpcClientToken::CheckCapability(ulong,int)

- ea: `0x18000c69c`
- end: `0x18000c6f9`
- name: `?CheckCapability@RpcClientToken@Broker@@QEAA_NKH@Z`
- size: `93`
- prototype: `bool __fastcall(void **this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ef50`

## callees

- `0x18000c700`
- `0x18000c7b8`
- `0x18000c864`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c6e6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c6e6`

## pseudocode

```c
bool __fastcall Broker::RpcClientToken::CheckCapability(void **this, unsigned int a2)
{
  int v4; // r9d
  char v6; // [rsp+30h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+20h] BYREF

  Broker::CoInitWrapper::CoInitWrapper((Broker::CoInitWrapper *)&v6);
  Broker::BackgroundTaskCapabilityWrapper::BackgroundTaskCapabilityWrapper(&ppv);
  LOBYTE(a2) = Broker::BackgroundTaskCapabilityWrapper::CheckCapability(
                 (Broker::BackgroundTaskCapabilityWrapper *)&ppv,
                 this[1],
                 a2,
                 v4);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CoUninitialize();
  return a2;
}

```

## disassembly

```asm
0x18000c69c  mov     [rsp+arg_8], rbx
0x18000c6a1  push    rdi
0x18000c6a2  sub     rsp, 20h
0x18000c6a6  mov     ebx, edx
0x18000c6a8  mov     rdi, rcx
0x18000c6ab  lea     rcx, [rsp+28h+arg_0]; this
0x18000c6b0  call    ??0CoInitWrapper@Broker@@QEAA@XZ; Broker::CoInitWrapper::CoInitWrapper(void)
0x18000c6b5  nop
0x18000c6b6  lea     rcx, [rsp+28h+ppv]; ppv
0x18000c6bb  call    ??0BackgroundTaskCapabilityWrapper@Broker@@QEAA@XZ; Broker::BackgroundTaskCapabilityWrapper::BackgroundTaskCapabilityWrapper(void)
0x18000c6c0  nop
0x18000c6c1  mov     r8d, ebx; unsigned int
0x18000c6c4  mov     rdx, [rdi+8]; void *
0x18000c6c8  lea     rcx, [rsp+28h+ppv]; this
0x18000c6cd  call    ?CheckCapability@BackgroundTaskCapabilityWrapper@Broker@@QEAA_NPEAXKH@Z; Broker::BackgroundTaskCapabilityWrapper::CheckCapability(void *,ulong,int)
0x18000c6d2  mov     bl, al
0x18000c6d4  mov     rcx, [rsp+28h+ppv]
0x18000c6d9  mov     rdx, [rcx]
0x18000c6dc  mov     rax, [rdx+10h]
0x18000c6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6e5  nop
0x18000c6e6  call    cs:__imp_CoUninitialize
0x18000c6ec  mov     al, bl
0x18000c6ee  mov     rbx, [rsp+28h+arg_8]
0x18000c6f3  add     rsp, 20h
0x18000c6f7  pop     rdi
0x18000c6f8  retn
```
