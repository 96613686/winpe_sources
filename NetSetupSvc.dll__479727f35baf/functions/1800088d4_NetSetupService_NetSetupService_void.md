# NetSetupService::NetSetupService(void)

- ea: `0x1800088d4`
- end: `0x180008a09`
- name: `??0NetSetupService@@QEAA@XZ`
- size: `309`
- prototype: `NetSetupService *__fastcall(NetSetupService *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180006d08`

## callees

- `0x180007048`
- `0x1800087d0`
- `0x180008ba0`
- `0x18000b1d4`
- `0x18000b2c0`
- `0x18001d15c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
NetSetupService *__fastcall NetSetupService::NetSetupService(NetSetupService *this)
{
  __int64 v2; // rcx

  StackLock::StackLock(this);
  StackLock::StackLock((NetSetupService *)((char *)this + 32));
  std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>((_QWORD *)this + 8);
  Event::Event((NetSetupService *)((char *)this + 88));
  *((_QWORD *)this + 12) = 0;
  Event::Event((NetSetupService *)((char *)this + 104));
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 16) = &NetSetupSvcKernelServices::`vftable';
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  NetSetupSvcDeviceManager::NetSetupSvcDeviceManager((char *)this + 168);
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = &QueuedServiceControl::`vftable';
  std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>((_QWORD *)this + 29);
  std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>((_QWORD *)this + 32);
  NetSetupService::OpenCurrentControlSetKey(v2, (char *)this + 280);
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_WORD *)this + 180) = 0;
  *((_BYTE *)this + 362) = 0;
  *((_DWORD *)this + 91) = -1;
  *((_QWORD *)this + 48) = 0;
  *((_DWORD *)this + 98) = 0;
  *((_BYTE *)this + 400) = 0;
  NetSetupService::OpenStateSeparationHives(this);
  return this;
}

```

## disassembly

```asm
0x1800088d4  mov     [rsp+arg_8], rbx
0x1800088d9  push    rdi
0x1800088da  sub     rsp, 30h
0x1800088de  mov     rdi, rcx
0x1800088e1  mov     [rsp+38h+var_18], rcx
0x1800088e6  call    ??0StackLock@@QEAA@XZ; StackLock::StackLock(void)
0x1800088eb  lea     rcx, [rdi+20h]; this
0x1800088ef  call    ??0StackLock@@QEAA@XZ; StackLock::StackLock(void)
0x1800088f4  lea     rcx, [rdi+40h]
0x1800088f8  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x1800088fd  nop
0x1800088fe  lea     rcx, [rdi+58h]; this
0x180008902  call    ??0Event@@QEAA@XZ; Event::Event(void)
0x180008907  nop
0x180008908  xor     ebx, ebx
0x18000890a  mov     [rdi+60h], rbx
0x18000890e  lea     rcx, [rdi+68h]; this
0x180008912  call    ??0Event@@QEAA@XZ; Event::Event(void)
0x180008917  nop
0x180008918  mov     [rdi+70h], rbx
0x18000891c  mov     [rdi+78h], ebx
0x18000891f  lea     rax, ??_7NetSetupSvcKernelServices@@6B@; const NetSetupSvcKernelServices::`vftable'
0x180008926  mov     [rdi+80h], rax
0x18000892d  mov     [rdi+88h], ebx
0x180008933  mov     [rdi+98h], rbx
0x18000893a  mov     [rdi+0A0h], rbx
0x180008941  lea     rcx, [rdi+0A8h]; pv
0x180008948  call    ??0NetSetupSvcDeviceManager@@QEAA@XZ; NetSetupSvcDeviceManager::NetSetupSvcDeviceManager(void)
0x18000894d  nop
0x18000894e  mov     [rdi+0D8h], rbx
0x180008955  lea     rax, ??_7QueuedServiceControl@@6B@; const QueuedServiceControl::`vftable'
0x18000895c  mov     [rdi+0E0h], rax
0x180008963  lea     rcx, [rdi+0E8h]
0x18000896a  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x18000896f  lea     rcx, [rdi+100h]
0x180008976  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x18000897b  nop
0x18000897c  lea     rdx, [rdi+118h]
0x180008983  call    ?OpenCurrentControlSetKey@NetSetupService@@AEAA?AVRegistryKey@@XZ; NetSetupService::OpenCurrentControlSetKey(void)
0x180008988  nop
0x180008989  mov     [rdi+120h], rbx
0x180008990  mov     [rdi+128h], rbx
0x180008997  mov     [rdi+130h], rbx
0x18000899e  mov     [rdi+138h], rbx
0x1800089a5  mov     [rdi+140h], rbx
0x1800089ac  mov     [rdi+148h], rbx
0x1800089b3  mov     [rdi+150h], rbx
0x1800089ba  mov     [rdi+158h], rbx
0x1800089c1  mov     [rdi+160h], rbx
0x1800089c8  mov     [rdi+168h], bx
0x1800089cf  mov     [rdi+16Ah], bl
0x1800089d5  mov     dword ptr [rdi+16Ch], 0FFFFFFFFh
0x1800089df  mov     [rdi+180h], rbx
0x1800089e6  mov     [rdi+188h], ebx
0x1800089ec  mov     [rdi+190h], bl
0x1800089f2  mov     rcx, rdi; this
0x1800089f5  call    ?OpenStateSeparationHives@NetSetupService@@AEAAXXZ; NetSetupService::OpenStateSeparationHives(void)
0x1800089fa  nop
0x1800089fb  mov     rax, rdi
0x1800089fe  mov     rbx, [rsp+38h+arg_8]
0x180008a03  add     rsp, 30h
0x180008a07  pop     rdi
0x180008a08  retn
```
