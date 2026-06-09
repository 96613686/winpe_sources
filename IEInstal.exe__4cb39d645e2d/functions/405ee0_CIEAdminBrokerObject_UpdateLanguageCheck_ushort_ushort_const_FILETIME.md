# CIEAdminBrokerObject::UpdateLanguageCheck(ushort *,ushort const *,_FILETIME)

- ea: `0x405ee0`
- end: `0x405f0d`
- name: `?UpdateLanguageCheck@CIEAdminBrokerObject@@UAGJPAGPBGU_FILETIME@@@Z`
- size: `45`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const unsigned __int16 *, struct _FILETIME)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x404a9b`
- `0x405ee0`

## pseudocode

```c

```

## disassembly

```asm
0x405ee0  mov     edi, edi
0x405ee2  push    ebp; struct _FILETIME
0x405ee3  mov     ebp, esp
0x405ee5  mov     eax, [ebp+this]
0x405ee8  mov     edx, 80004005h
0x405eed  mov     ecx, [eax+8]
0x405ef0  test    ecx, ecx
0x405ef2  jz      short loc_405F07
0x405ef4  push    [ebp+arg_C.dwHighDateTime]; Data
0x405ef7  mov     edx, [ebp+arg_4]
0x405efa  push    [ebp+arg_C.dwLowDateTime]; unsigned __int16 *
0x405efd  push    [ebp+lpSubKey]; lpSubKey
0x405f00  call    ?UpdateLanguageCheck@CActiveXInstallBroker@@QAGJPAGPBGU_FILETIME@@@Z; CActiveXInstallBroker::UpdateLanguageCheck(ushort *,ushort const *,_FILETIME)
0x405f05  mov     edx, eax
0x405f07  mov     eax, edx
0x405f09  pop     ebp
0x405f0a  retn    14h
```
