# _CreateSystemObjectServer::_IsRequestApproved_::_1_::dtor$1

- ea: `0x1400099eb`
- end: `0x1400099f7`
- name: `_CreateSystemObjectServer::_IsRequestApproved_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140007468`

## pseudocode

```c
__int64 __fastcall CreateSystemObjectServer::_IsRequestApproved_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::unique_call<long (*)(void),&long CoRevertToSelf(void),1>::~unique_call<long (*)(void),&long CoRevertToSelf(void),1>(a2 + 64);
}

```

## disassembly

```asm
0x1400099eb  lea     rcx, [rdx+40h]
0x1400099f2  jmp     ??1?$unique_call@P6AJXZ$1?CoRevertToSelf@@YAJXZ$00@wil@@QEAA@XZ; wil::unique_call<long (*)(void),&CoRevertToSelf(void),1>::~unique_call<long (*)(void),&CoRevertToSelf(void),1>(void)
```
