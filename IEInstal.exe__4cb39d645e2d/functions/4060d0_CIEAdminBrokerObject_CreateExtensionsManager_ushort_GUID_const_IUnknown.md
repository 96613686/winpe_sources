# CIEAdminBrokerObject::CreateExtensionsManager(ushort *,_GUID const &,IUnknown * *)

- ea: `0x4060d0`
- end: `0x4060fa`
- name: `?CreateExtensionsManager@CIEAdminBrokerObject@@UAGJPAGABU_GUID@@PAPAUIUnknown@@@Z`
- size: `42`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x405966`
- `0x4060d0`

## pseudocode

```c

```

## disassembly

```asm
0x4060d0  mov     edi, edi
0x4060d2  push    ebp; struct _GUID *
0x4060d3  mov     ebp, esp
0x4060d5  mov     eax, [ebp+this]
0x4060d8  mov     edx, 80004005h
0x4060dd  mov     ecx, [eax+8]
0x4060e0  test    ecx, ecx
0x4060e2  jz      short loc_4060F4
0x4060e4  push    [ebp+ppv]; ppv
0x4060e7  mov     edx, [ebp+arg_4]
0x4060ea  push    [ebp+rclsid]; rclsid
0x4060ed  call    ?CreateExtensionsManager@CActiveXInstallBroker@@QAGJPAGABU_GUID@@PAPAUIUnknown@@@Z; CActiveXInstallBroker::CreateExtensionsManager(ushort *,_GUID const &,IUnknown * *)
0x4060f2  mov     edx, eax
0x4060f4  mov     eax, edx
0x4060f6  pop     ebp
0x4060f7  retn    10h
```
