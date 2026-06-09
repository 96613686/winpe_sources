# _RootCause::addRepair_::_1_::catch$1

- ea: `0x1800113f5`
- end: `0x18001141a`
- name: `_RootCause::addRepair_::_1_::catch$1`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000257c`

## pseudocode

```c
void __fastcall __noreturn RootCause::addRepair_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 32) = 0;
  throw (TestException *)(a2 + 32);
}

```

## disassembly

```asm
0x1800113f5  mov     [rsp+arg_8], rdx
0x1800113fa  push    rbp
0x1800113fb  sub     rsp, 20h
0x1800113ff  mov     rbp, rdx
0x180011402  mov     dword ptr [rbp+20h], 0
0x180011409  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x180011410  lea     rcx, [rbp+20h]; pExceptionObject
0x180011414  call    _CxxThrowException_0
```
