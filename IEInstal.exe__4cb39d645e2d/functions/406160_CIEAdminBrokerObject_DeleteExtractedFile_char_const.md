# CIEAdminBrokerObject::DeleteExtractedFile(char const *)

- ea: `0x406160`
- end: `0x406184`
- name: `?DeleteExtractedFile@CIEAdminBrokerObject@@UAGJPBD@Z`
- size: `36`
- prototype: `int(CIEAdminBrokerObject *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4058f8`
- `0x406160`

## pseudocode

```c
int __stdcall CIEAdminBrokerObject::DeleteExtractedFile(CIEAdminBrokerObject *this, const char *a2)
{
  int v2; // edx
  int *v3; // ecx

  v2 = -2147467259;
  v3 = (int *)*((_DWORD *)this + 2);
  if ( v3 )
    return CActiveXInstallBroker::DeleteExtractedFile(v3, a2);
  return v2;
}

```

## disassembly

```asm
0x406160  mov     edi, edi
0x406162  push    ebp; this
0x406163  mov     ebp, esp
0x406165  mov     eax, [ebp+this]
0x406168  mov     edx, 80004005h
0x40616d  mov     ecx, [eax+8]
0x406170  test    ecx, ecx
0x406172  jz      short loc_40617E
0x406174  mov     edx, [ebp+arg_4]
0x406177  call    ?DeleteExtractedFile@CActiveXInstallBroker@@QAGJPBD@Z; CActiveXInstallBroker::DeleteExtractedFile(char const *)
0x40617c  mov     edx, eax
0x40617e  mov     eax, edx
0x406180  pop     ebp
0x406181  retn    8
```
