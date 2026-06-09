# av_hmac_update

- ea: `0x18003efa0`
- end: `0x18003efb1`
- name: `av_hmac_update`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18007a900`

## pseudocode

```c
__int64 __fastcall av_hmac_update(__int64 a1, __int64 a2, unsigned int a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(a1 + 24))(*(_QWORD *)a1, a2, a3);
}

```

## disassembly

```asm
0x18003efa0  mov     rax, [rcx+18h]
0x18003efa4  mov     rcx, [rcx]
0x18003efa7  mov     r8d, r8d
0x18003efaa  jmp     cs:__guard_dispatch_icall_fptr
```
