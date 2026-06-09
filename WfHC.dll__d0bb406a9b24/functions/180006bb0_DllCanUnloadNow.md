# DllCanUnloadNow

- ea: `0x180006bb0`
- end: `0x180006bd9`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000e010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(__int64 *))(qword_1800160C0 + 24))(&qword_1800160C0) != 0;
}

```

## disassembly

```asm
0x180006bb0  sub     rsp, 28h
0x180006bb4  mov     rax, cs:qword_1800160C0
0x180006bbb  lea     rcx, qword_1800160C0
0x180006bc2  mov     rax, [rax+18h]
0x180006bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bcb  xor     ecx, ecx
0x180006bcd  test    eax, eax
0x180006bcf  setnz   cl
0x180006bd2  mov     eax, ecx
0x180006bd4  add     rsp, 28h
0x180006bd8  retn
```
