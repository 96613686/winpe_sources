# WaasMedic::CBSHandler::ProgressEx(_CbsInstallState,uint,uint,uint,int *)

- ea: `0x18000a350`
- end: `0x18000a36f`
- name: `?ProgressEx@CBSHandler@WaasMedic@@UEAAJW4_CbsInstallState@@IIIPEAH@Z`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall WaasMedic::CBSHandler::ProgressEx(__int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
}

```

## disassembly

```asm
0x18000a350  sub     rsp, 38h
0x18000a354  mov     rax, [rcx]
0x18000a357  mov     r10, [rsp+38h+arg_28]
0x18000a35c  mov     [rsp+38h+var_18], r10
0x18000a361  mov     rax, [rax+38h]
0x18000a365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a36a  add     rsp, 38h
0x18000a36e  retn
```
