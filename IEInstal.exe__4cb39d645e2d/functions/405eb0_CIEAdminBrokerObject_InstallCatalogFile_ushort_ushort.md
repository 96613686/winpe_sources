# CIEAdminBrokerObject::InstallCatalogFile(ushort *,ushort *)

- ea: `0x405eb0`
- end: `0x405ed7`
- name: `?InstallCatalogFile@CIEAdminBrokerObject@@UAGJPAG0@Z`
- size: `39`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x40494e`
- `0x405eb0`

## pseudocode

```c

```

## disassembly

```asm
0x405eb0  mov     edi, edi
0x405eb2  push    ebp; unsigned __int16 *
0x405eb3  mov     ebp, esp
0x405eb5  mov     eax, [ebp+this]
0x405eb8  mov     edx, 80004005h
0x405ebd  mov     ecx, [eax+8]
0x405ec0  test    ecx, ecx
0x405ec2  jz      short loc_405ED1
0x405ec4  push    [ebp+pwszCatalogFile]; pwszCatalogFile
0x405ec7  mov     edx, [ebp+arg_4]
0x405eca  call    ?InstallCatalogFile@CActiveXInstallBroker@@QAGJPAG0@Z; CActiveXInstallBroker::InstallCatalogFile(ushort *,ushort *)
0x405ecf  mov     edx, eax
0x405ed1  mov     eax, edx
0x405ed3  pop     ebp
0x405ed4  retn    0Ch
```
