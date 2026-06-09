# Microsoft::WRL::SimpleClassFactory<CCPLUserMgrBroker,0>::`scalar deleting destructor'(uint)

- ea: `0x140002950`
- end: `0x140002973`
- name: `??_G?$SimpleClassFactory@VCCPLUserMgrBroker@@$0A@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `35`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001184`
- `0x140002950`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::SimpleClassFactory<CCPLUserMgrBroker,0>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140002950  push    rbx
0x140002952  sub     rsp, 20h
0x140002956  mov     dword ptr [rcx+0Ch], 0C0000001h
0x14000295d  mov     rbx, rcx
0x140002960  test    dl, 1
0x140002963  jz      short loc_14000296A
0x140002965  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000296a  mov     rax, rbx
0x14000296d  add     rsp, 20h
0x140002971  pop     rbx
0x140002972  retn
```
