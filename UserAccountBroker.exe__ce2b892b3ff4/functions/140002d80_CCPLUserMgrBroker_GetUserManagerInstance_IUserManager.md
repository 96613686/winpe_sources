# CCPLUserMgrBroker::GetUserManagerInstance(IUserManager * *)

- ea: `0x140002d80`
- end: `0x140002d86`
- name: `?GetUserManagerInstance@CCPLUserMgrBroker@@UEAAJPEAPEAUIUserManager@@@Z`
- size: `6`
- prototype: `__int64 __fastcall(CCPLUserMgrBroker *__hidden this, struct IUserManager **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CCPLUserMgrBroker::GetUserManagerInstance(CCPLUserMgrBroker *this, struct IUserManager **a2)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x140002d80  mov     eax, 80004001h
0x140002d85  retn
```
