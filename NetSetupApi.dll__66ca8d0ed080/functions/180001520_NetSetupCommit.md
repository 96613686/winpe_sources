# NetSetupCommit

- ea: `0x180001520`
- end: `0x18000155e`
- name: `NetSetupCommit`
- size: `62`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c354`
- `0x18000c4a8`
- `0x18000fd78`

## callees

- `0x180001564`
- `0x1800015b0`
- `0x1800016d0`

## pseudocode

```c
__int64 __fastcall NetSetupCommit(__int64 a1)
{
  unsigned int v2; // ebx

  EtwApiBegin(a1, 3);
  v2 = NetSetupExecuteInFrame__lambda_37a8a0ce1795914e386a3d7ce46786e1_(a1);
  EtwApiEnd(a1, 3, v2);
  return v2;
}

```

## disassembly

```asm
0x180001520  mov     [rsp+arg_8], rbx
0x180001525  push    rdi
0x180001526  sub     rsp, 20h
0x18000152a  mov     edx, 3
0x18000152f  mov     rdi, rcx
0x180001532  call    EtwApiBegin
0x180001537  mov     rcx, rdi
0x18000153a  call    NetSetupExecuteInFrame__lambda_37a8a0ce1795914e386a3d7ce46786e1___; NetSetupExecuteInFrame__lambda_37a8a0ce1795914e386a3d7ce46786e1_
0x18000153f  mov     r8d, eax
0x180001542  mov     edx, 3
0x180001547  mov     rcx, rdi
0x18000154a  mov     ebx, eax
0x18000154c  call    EtwApiEnd
0x180001551  mov     eax, ebx
0x180001553  mov     rbx, [rsp+28h+arg_8]
0x180001558  add     rsp, 20h
0x18000155c  pop     rdi
0x18000155d  retn
```
