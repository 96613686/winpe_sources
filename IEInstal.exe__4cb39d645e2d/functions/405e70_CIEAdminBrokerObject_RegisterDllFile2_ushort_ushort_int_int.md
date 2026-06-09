# CIEAdminBrokerObject::RegisterDllFile2(ushort *,ushort *,int,int)

- ea: `0x405e70`
- end: `0x405e9d`
- name: `?RegisterDllFile2@CIEAdminBrokerObject@@UAGJPAG0HH@Z`
- size: `45`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned __int16 *, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x404806`
- `0x405e70`

## pseudocode

```c

```

## disassembly

```asm
0x405e70  mov     edi, edi
0x405e72  push    ebp; int
0x405e73  mov     ebp, esp
0x405e75  mov     eax, [ebp+this]
0x405e78  mov     edx, 80004005h
0x405e7d  mov     ecx, [eax+8]
0x405e80  test    ecx, ecx
0x405e82  jz      short loc_405E97
0x405e84  push    [ebp+arg_10]; unsigned __int16 *
0x405e87  mov     edx, [ebp+arg_4]
0x405e8a  push    [ebp+arg_C]; unsigned __int16 *
0x405e8d  push    [ebp+cchDest]; cchDest
0x405e90  call    ?RegisterDllFile2@CActiveXInstallBroker@@QAGJPAG0HH@Z; CActiveXInstallBroker::RegisterDllFile2(ushort *,ushort *,int,int)
0x405e95  mov     edx, eax
0x405e97  mov     eax, edx
0x405e99  pop     ebp
0x405e9a  retn    14h
```
