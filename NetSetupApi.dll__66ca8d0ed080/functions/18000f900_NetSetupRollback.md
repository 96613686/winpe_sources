# NetSetupRollback

- ea: `0x18000f900`
- end: `0x18000f930`
- name: `NetSetupRollback`
- size: `48`
- prototype: `__int64 *__fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800015b0`
- `0x1800016d0`
- `0x18000d48c`

## pseudocode

```c
__int64 *__fastcall NetSetupRollback(__int64 a1)
{
  char v2; // al

  EtwApiBegin(a1, 2);
  v2 = NetSetupExecuteInFrame__lambda_dfe28d390c313e0713506b203eb2d14c_(a1);
  return EtwApiEnd(a1, 2, v2);
}

```

## disassembly

```asm
0x18000f900  push    rbx
0x18000f902  sub     rsp, 20h
0x18000f906  mov     edx, 2
0x18000f90b  mov     rbx, rcx
0x18000f90e  call    EtwApiBegin
0x18000f913  mov     rcx, rbx
0x18000f916  call    NetSetupExecuteInFrame__lambda_dfe28d390c313e0713506b203eb2d14c___; NetSetupExecuteInFrame__lambda_dfe28d390c313e0713506b203eb2d14c_
0x18000f91b  mov     r8d, eax
0x18000f91e  mov     edx, 2
0x18000f923  mov     rcx, rbx
0x18000f926  add     rsp, 20h
0x18000f92a  pop     rbx
0x18000f92b  jmp     EtwApiEnd
```
