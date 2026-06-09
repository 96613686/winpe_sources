# CIEAdminBrokerObject::EnumerateFiles(ushort *,char const *,sSESSION *)

- ea: `0x406040`
- end: `0x40606a`
- name: `?EnumerateFiles@CIEAdminBrokerObject@@UAGJPAGPBDPAUsSESSION@@@Z`
- size: `42`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const char *, struct sSESSION *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x405628`
- `0x406040`

## pseudocode

```c

```

## disassembly

```asm
0x406040  mov     edi, edi
0x406042  push    ebp; char *
0x406043  mov     ebp, esp
0x406045  mov     eax, [ebp+this]
0x406048  mov     edx, 80004005h
0x40604d  mov     ecx, [eax+8]
0x406050  test    ecx, ecx
0x406052  jz      short loc_406064
0x406054  push    [ebp+arg_C]; unsigned __int16 *
0x406057  mov     edx, [ebp+arg_4]
0x40605a  push    [ebp+arg_8]; this
0x40605d  call    ?EnumerateFiles@CActiveXInstallBroker@@QAGJPAGPBDPAUsSESSION@@@Z; CActiveXInstallBroker::EnumerateFiles(ushort *,char const *,sSESSION *)
0x406062  mov     edx, eax
0x406064  mov     eax, edx
0x406066  pop     ebp
0x406067  retn    10h
```
