# CIEAdminBrokerObject::UpdateModuleUsage(ushort *,char const *,char const *,char const *,char const *,ulong)

- ea: `0x406000`
- end: `0x406033`
- name: `?UpdateModuleUsage@CIEAdminBrokerObject@@UAGJPAGPBD111K@Z`
- size: `51`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const char *, const char *, const char *, const char *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x405304`
- `0x406000`

## pseudocode

```c

```

## disassembly

```asm
0x406000  mov     edi, edi
0x406002  push    ebp; char *
0x406003  mov     ebp, esp
0x406005  mov     eax, [ebp+this]
0x406008  mov     edx, 80004005h
0x40600d  mov     ecx, [eax+8]
0x406010  test    ecx, ecx
0x406012  jz      short loc_40602D
0x406014  push    [ebp+arg_18]; char *
0x406017  mov     edx, [ebp+arg_4]
0x40601a  push    [ebp+arg_14]; char *
0x40601d  push    [ebp+arg_10]; char *
0x406020  push    [ebp+arg_C]; unsigned __int16 *
0x406023  push    [ebp+arg_8]; this
0x406026  call    ?UpdateModuleUsage@CActiveXInstallBroker@@QAGJPAGPBD111K@Z; CActiveXInstallBroker::UpdateModuleUsage(ushort *,char const *,char const *,char const *,char const *,ulong)
0x40602b  mov     edx, eax
0x40602d  mov     eax, edx
0x40602f  pop     ebp
0x406030  retn    1Ch
```
