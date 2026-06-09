# NetworkLegacyUxTelemetry::NetworkExplorerOpen::~NetworkExplorerOpen(void)

- ea: `0x180008d50`
- end: `0x180008d75`
- name: `??1NetworkExplorerOpen@NetworkLegacyUxTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(NetworkLegacyUxTelemetry::NetworkExplorerOpen *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c984`
- `0x18000f52b`

## callees

- `0x1800089d4`
- `0x1800094b0`

## pseudocode

```c
void __fastcall NetworkLegacyUxTelemetry::NetworkExplorerOpen::~NetworkExplorerOpen(
        NetworkLegacyUxTelemetry::NetworkExplorerOpen *this)
{
  *(_QWORD *)this = &NetworkLegacyUxTelemetry::NetworkExplorerOpen::`vftable';
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180008d50  push    rbx
0x180008d52  sub     rsp, 20h
0x180008d56  lea     rax, ??_7NetworkExplorerOpen@NetworkLegacyUxTelemetry@@6B@; const NetworkLegacyUxTelemetry::NetworkExplorerOpen::`vftable'
0x180008d5d  mov     rbx, rcx
0x180008d60  mov     [rcx], rax
0x180008d63  call    ?Destroy@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180008d68  mov     rcx, rbx
0x180008d6b  add     rsp, 20h
0x180008d6f  pop     rbx
0x180008d70  jmp     ??1?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
