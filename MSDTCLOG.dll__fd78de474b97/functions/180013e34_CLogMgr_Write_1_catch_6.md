# _CLogMgr::_Write_::_1_::catch$6

- ea: `0x180013e34`
- end: `0x180013e6e`
- name: `_CLogMgr::_Write_::_1_::catch$6`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009d84`
- `0x18001266c`

## pseudocode

```c
void __fastcall __noreturn CLogMgr::_Write_::_1_::catch_6(__int64 a1, __int64 a2)
{
  CLogState::_RestoreLogState(*(CLogState **)(*(_QWORD *)(a2 + 192) + 400LL));
  *(_DWORD *)(a2 + 84) = *(_DWORD *)(a2 + 132);
  throw (ulong *)(a2 + 84);
}

```

## disassembly

```asm
0x180013e34  mov     [rsp+arg_8], rdx
0x180013e39  push    rbp
0x180013e3a  sub     rsp, 50h
0x180013e3e  mov     rbp, rdx
0x180013e41  mov     rcx, [rbp+0C0h]
0x180013e48  mov     rcx, [rcx+190h]; this
0x180013e4f  call    ?_RestoreLogState@CLogState@@AEAAXXZ; CLogState::_RestoreLogState(void)
0x180013e54  mov     ecx, [rbp+84h]
0x180013e5a  mov     [rbp+54h], ecx
0x180013e5d  lea     rdx, _TI1K; pThrowInfo
0x180013e64  lea     rcx, [rbp+54h]; pExceptionObject
0x180013e68  call    _CxxThrowException_0
```
