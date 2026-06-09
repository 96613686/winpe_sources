# ModernResourceManagerProxy::~ModernResourceManagerProxy(void)

- ea: `0x18001918c`
- end: `0x1800191cd`
- name: `??1ModernResourceManagerProxy@@UEAA@XZ`
- size: `65`
- prototype: `void __fastcall(ModernResourceManagerProxy *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800191e0`

## callees

- `0x18001918c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800191a8`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800191b7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800191a8`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800191b7`
- `RPCRT4!RpcBindingFree` at `0x1800191c6`

## pseudocode

```c
void __fastcall ModernResourceManagerProxy::~ModernResourceManagerProxy(ModernResourceManagerProxy *this)
{
  *(_QWORD *)this = &ModernResourceManagerProxy::`vftable';
  if ( *((_QWORD *)this + 7) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  if ( *((_QWORD *)this + 8) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  RpcBindingFree((RPC_BINDING_HANDLE *)this + 2);
}

```

## disassembly

```asm
0x18001918c  push    rbx
0x18001918e  sub     rsp, 20h
0x180019192  lea     rax, ??_7ModernResourceManagerProxy@@6B@; const ModernResourceManagerProxy::`vftable'
0x180019199  mov     rbx, rcx
0x18001919c  mov     [rcx], rax
0x18001919f  mov     rcx, [rcx+38h]
0x1800191a3  test    rcx, rcx
0x1800191a6  jz      short loc_1800191AE
0x1800191a8  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800191ae  mov     rcx, [rbx+40h]
0x1800191b2  test    rcx, rcx
0x1800191b5  jz      short loc_1800191BD
0x1800191b7  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800191bd  lea     rcx, [rbx+10h]
0x1800191c1  add     rsp, 20h
0x1800191c5  pop     rbx
0x1800191c6  jmp     cs:__imp_RpcBindingFree
```
