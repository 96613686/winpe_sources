# CRuntimeBrokerLifetimeExtensionFactory::CRuntimeBrokerLifetimeExtensionFactory(void)

- ea: `0x140006844`
- end: `0x140006899`
- name: `??0CRuntimeBrokerLifetimeExtensionFactory@@QEAA@XZ`
- size: `85`
- prototype: `CRuntimeBrokerLifetimeExtensionFactory *__fastcall(CRuntimeBrokerLifetimeExtensionFactory *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006260`

## callees

- `0x1400068e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140006885`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140006885`

## pseudocode

```c
CRuntimeBrokerLifetimeExtensionFactory *__fastcall CRuntimeBrokerLifetimeExtensionFactory::CRuntimeBrokerLifetimeExtensionFactory(
        CRuntimeBrokerLifetimeExtensionFactory *this)
{
  LPUNKNOWN *v1; // rbx

  v1 = (LPUNKNOWN *)((char *)this + 24);
  *((_DWORD *)this + 4) = 1;
  *(_QWORD *)this = &CRuntimeBrokerLifetimeExtensionFactory::`vftable'{for `IClassFactory'};
  *((_QWORD *)this + 1) = &CRuntimeBrokerLifetimeExtensionFactory::`vftable'{for `IMarshal'};
  *((_QWORD *)this + 3) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
  CoCreateFreeThreadedMarshaler(0, v1);
  return this;
}

```

## disassembly

```asm
0x140006844  mov     [rsp+arg_0], rbx
0x140006849  push    rdi
0x14000684a  sub     rsp, 20h
0x14000684e  lea     rbx, [rcx+18h]
0x140006852  mov     dword ptr [rcx+10h], 1
0x140006859  lea     rax, ??_7CRuntimeBrokerLifetimeExtensionFactory@@6BIClassFactory@@@; const CRuntimeBrokerLifetimeExtensionFactory::`vftable'{for `IClassFactory'}
0x140006860  mov     rdi, rcx
0x140006863  mov     [rcx], rax
0x140006866  lea     rax, ??_7CRuntimeBrokerLifetimeExtensionFactory@@6BIMarshal@@@; const CRuntimeBrokerLifetimeExtensionFactory::`vftable'{for `IMarshal'}
0x14000686d  mov     [rcx+8], rax
0x140006871  mov     rcx, rbx
0x140006874  mov     qword ptr [rbx], 0
0x14000687b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140006880  mov     rdx, rbx; ppunkMarshal
0x140006883  xor     ecx, ecx; punkOuter
0x140006885  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x14000688b  mov     rbx, [rsp+28h+arg_0]
0x140006890  mov     rax, rdi
0x140006893  add     rsp, 20h
0x140006897  pop     rdi
0x140006898  retn
```
