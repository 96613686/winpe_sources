# CIEAdminBrokerObject::ExtractFiles(ushort *,char const *,sSESSION *)

- ea: `0x406070`
- end: `0x40609a`
- name: `?ExtractFiles@CIEAdminBrokerObject@@UAGJPAGPBDPAUsSESSION@@@Z`
- size: `42`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const char *, struct sSESSION *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x40576c`
- `0x406070`

## pseudocode

```c

```

## disassembly

```asm
0x406070  mov     edi, edi
0x406072  push    ebp; char *
0x406073  mov     ebp, esp
0x406075  mov     eax, [ebp+this]
0x406078  mov     edx, 80004005h
0x40607d  mov     ecx, [eax+8]
0x406080  test    ecx, ecx
0x406082  jz      short loc_406094
0x406084  push    [ebp+arg_C]; unsigned __int16 *
0x406087  mov     edx, [ebp+arg_4]
0x40608a  push    [ebp+arg_8]; this
0x40608d  call    ?ExtractFiles@CActiveXInstallBroker@@QAGJPAGPBDPAUsSESSION@@@Z; CActiveXInstallBroker::ExtractFiles(ushort *,char const *,sSESSION *)
0x406092  mov     edx, eax
0x406094  mov     eax, edx
0x406096  pop     ebp
0x406097  retn    10h
```
