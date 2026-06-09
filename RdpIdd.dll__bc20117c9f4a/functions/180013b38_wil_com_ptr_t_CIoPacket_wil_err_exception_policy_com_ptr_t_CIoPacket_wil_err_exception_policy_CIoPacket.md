# wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(CIoPacket *)

- ea: `0x180013b38`
- end: `0x180013b62`
- name: `??0?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCIoPacket@@@Z`
- size: `42`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016834`
- `0x18001818c`
- `0x180031c30`
- `0x180031dd8`
- `0x18003201c`
- `0x180032398`
- `0x180032c90`
- `0x180032ec0`
- `0x180034180`
- `0x1800346e4`
- `0x180035760`

## callees

- `0x180013b38`
- `0x18003f010`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(
        _QWORD *a1,
        __int64 a2)
{
  *a1 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  return a1;
}

```

## disassembly

```asm
0x180013b38  push    rbx
0x180013b3a  sub     rsp, 20h
0x180013b3e  mov     [rcx], rdx
0x180013b41  mov     rbx, rcx
0x180013b44  test    rdx, rdx
0x180013b47  jz      short loc_180013B58
0x180013b49  mov     rax, [rdx]
0x180013b4c  mov     rcx, rdx
0x180013b4f  mov     rax, [rax+8]
0x180013b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b58  mov     rax, rbx
0x180013b5b  add     rsp, 20h
0x180013b5f  pop     rbx
0x180013b60  retn
```
