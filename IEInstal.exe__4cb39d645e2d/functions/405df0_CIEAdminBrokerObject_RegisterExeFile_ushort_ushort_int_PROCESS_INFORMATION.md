# CIEAdminBrokerObject::RegisterExeFile(ushort *,ushort *,int,_PROCESS_INFORMATION *)

- ea: `0x405df0`
- end: `0x405e1d`
- name: `?RegisterExeFile@CIEAdminBrokerObject@@UAGJPAG0HPAU_PROCESS_INFORMATION@@@Z`
- size: `45`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned __int16 *, int, struct _PROCESS_INFORMATION *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x404214`
- `0x405df0`

## pseudocode

```c

```

## disassembly

```asm
0x405df0  mov     edi, edi
0x405df2  push    ebp; int
0x405df3  mov     ebp, esp
0x405df5  mov     eax, [ebp+this]
0x405df8  mov     edx, 80004005h
0x405dfd  mov     ecx, [eax+8]
0x405e00  test    ecx, ecx
0x405e02  jz      short loc_405E17
0x405e04  push    [ebp+arg_10]; unsigned __int16 *
0x405e07  mov     edx, [ebp+arg_4]
0x405e0a  push    [ebp+arg_C]; unsigned __int16 *
0x405e0d  push    [ebp+arg_8]; this
0x405e10  call    ?RegisterExeFile@CActiveXInstallBroker@@QAGJPAG0HPAU_PROCESS_INFORMATION@@@Z; CActiveXInstallBroker::RegisterExeFile(ushort *,ushort *,int,_PROCESS_INFORMATION *)
0x405e15  mov     edx, eax
0x405e17  mov     eax, edx
0x405e19  pop     ebp
0x405e1a  retn    14h
```
