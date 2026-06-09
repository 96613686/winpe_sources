# LMCallback::CleanupInterfaces(bool)

- ea: `0x1800053b0`
- end: `0x180005425`
- name: `?CleanupInterfaces@LMCallback@@UEAAX_N@Z`
- size: `117`
- prototype: `void __fastcall(LMCallback *__hidden this, bool)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800053b0`
- `0x1800060f4`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800053f7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180005406`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180005415`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800053f7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180005406`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180005415`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x1800053de`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x1800053de`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x1800053e8`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x1800053e8`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800053c0`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800053c0`

## pseudocode

```c
void __fastcall LMCallback::CleanupInterfaces(LMCallback *this)
{
  DWORD v2; // ecx

  v2 = *((_DWORD *)this + 2);
  if ( v2 )
    CoRevokeClassObject(v2);
  if ( !(unsigned __int8)IsXboxLicensingUndocked() )
  {
    if ( *((_BYTE *)this + 24) )
    {
      RpcServerInterfaceGroupDeactivate(*((_QWORD *)this + 2), 1);
      RpcServerInterfaceGroupClose(*((_QWORD *)this + 2));
    }
    if ( *((_QWORD *)this + 4) )
      RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( *((_QWORD *)this + 5) )
      RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( *((_QWORD *)this + 6) )
      RtlUnsubscribeWnfNotificationWaitForCompletion();
  }
}

```

## disassembly

```asm
0x1800053b0  push    rbx
0x1800053b2  sub     rsp, 20h
0x1800053b6  mov     rbx, rcx
0x1800053b9  mov     ecx, [rcx+8]; dwRegister
0x1800053bc  test    ecx, ecx
0x1800053be  jz      short loc_1800053C6
0x1800053c0  call    cs:__imp_CoRevokeClassObject
0x1800053c6  call    IsXboxLicensingUndocked
0x1800053cb  test    al, al
0x1800053cd  jnz     short loc_18000541E
0x1800053cf  cmp     byte ptr [rbx+18h], 0
0x1800053d3  jz      short loc_1800053EE
0x1800053d5  mov     edx, 1
0x1800053da  mov     rcx, [rbx+10h]
0x1800053de  call    cs:__imp_RpcServerInterfaceGroupDeactivate
0x1800053e4  mov     rcx, [rbx+10h]
0x1800053e8  call    cs:__imp_RpcServerInterfaceGroupClose
0x1800053ee  mov     rcx, [rbx+20h]
0x1800053f2  test    rcx, rcx
0x1800053f5  jz      short loc_1800053FD
0x1800053f7  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800053fd  mov     rcx, [rbx+28h]
0x180005401  test    rcx, rcx
0x180005404  jz      short loc_18000540C
0x180005406  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000540c  mov     rcx, [rbx+30h]
0x180005410  test    rcx, rcx
0x180005413  jz      short loc_18000541C
0x180005415  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000541b  nop
0x18000541c  jmp     short $+2
0x18000541e  add     rsp, 20h
0x180005422  pop     rbx
0x180005423  retn
```
