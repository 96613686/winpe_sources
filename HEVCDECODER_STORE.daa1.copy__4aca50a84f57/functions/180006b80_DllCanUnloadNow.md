# DllCanUnloadNow

- ea: `0x180006b80`
- end: `0x180006bc6`
- name: `DllCanUnloadNow`
- size: `70`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002ae0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006b98`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006b98`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rdx

  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_1801AB9C8 = 1;
  return (unsigned __int8)sub_180002AE0(&qword_1801AB9C0, v0, 0) ^ 1;
}

```

## disassembly

```asm
0x180006b80  sub     rsp, 28h
0x180006b84  xor     r9d, r9d; Context
0x180006b87  lea     rdx, InitFn; InitFn
0x180006b8e  xor     r8d, r8d; Parameter
0x180006b91  lea     rcx, InitOnce; InitOnce
0x180006b98  call    cs:InitOnceExecuteOnce
0x180006b9f  nop     dword ptr [rax+rax+00h]
0x180006ba4  xor     r8d, r8d
0x180006ba7  mov     cs:byte_1801AB9C8, 1
0x180006bae  lea     rcx, qword_1801AB9C0
0x180006bb5  call    sub_180002AE0
0x180006bba  movzx   eax, al
0x180006bbd  xor     eax, 1
0x180006bc0  add     rsp, 28h
0x180006bc4  retn
```
