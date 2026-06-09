# CIEAdminBrokerObject::RemoveExtractedFilesAndDirs(ushort *,sSESSION *)

- ea: `0x4060a0`
- end: `0x4060c7`
- name: `?RemoveExtractedFilesAndDirs@CIEAdminBrokerObject@@UAGJPAGPAUsSESSION@@@Z`
- size: `39`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, struct sSESSION *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x405849`
- `0x4060a0`

## pseudocode

```c

```

## disassembly

```asm
0x4060a0  mov     edi, edi
0x4060a2  push    ebp; unsigned __int16 *
0x4060a3  mov     ebp, esp
0x4060a5  mov     eax, [ebp+this]
0x4060a8  mov     edx, 80004005h
0x4060ad  mov     ecx, [eax+8]
0x4060b0  test    ecx, ecx
0x4060b2  jz      short loc_4060C1
0x4060b4  push    [ebp+arg_8]; this
0x4060b7  mov     edx, [ebp+arg_4]
0x4060ba  call    ?RemoveExtractedFilesAndDirs@CActiveXInstallBroker@@QAGJPAGPAUsSESSION@@@Z; CActiveXInstallBroker::RemoveExtractedFilesAndDirs(ushort *,sSESSION *)
0x4060bf  mov     edx, eax
0x4060c1  mov     eax, edx
0x4060c3  pop     ebp
0x4060c4  retn    0Ch
```
