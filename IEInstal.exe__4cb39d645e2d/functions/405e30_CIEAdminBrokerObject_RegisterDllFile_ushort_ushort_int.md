# CIEAdminBrokerObject::RegisterDllFile(ushort *,ushort *,int)

- ea: `0x405e30`
- end: `0x405e5c`
- name: `?RegisterDllFile@CIEAdminBrokerObject@@UAGJPAG0H@Z`
- size: `44`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x404806`
- `0x405e30`

## pseudocode

```c

```

## disassembly

```asm
0x405e30  mov     edi, edi
0x405e32  push    ebp; int
0x405e33  mov     ebp, esp
0x405e35  mov     eax, [ebp+this]
0x405e38  mov     edx, 80004005h
0x405e3d  mov     ecx, [eax+8]
0x405e40  test    ecx, ecx
0x405e42  jz      short loc_405E56
0x405e44  push    [ebp+arg_C]; unsigned __int16 *
0x405e47  mov     edx, [ebp+arg_4]
0x405e4a  push    0; unsigned __int16 *
0x405e4c  push    [ebp+cchDest]; cchDest
0x405e4f  call    ?RegisterDllFile2@CActiveXInstallBroker@@QAGJPAG0HH@Z; CActiveXInstallBroker::RegisterDllFile2(ushort *,ushort *,int,int)
0x405e54  mov     edx, eax
0x405e56  mov     eax, edx
0x405e58  pop     ebp
0x405e59  retn    10h
```
