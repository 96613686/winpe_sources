# DllCanUnloadNow

- ea: `0x1800030c0`
- end: `0x18000310a`
- name: `DllCanUnloadNow`
- size: `74`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800030d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800030d8`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  InitOnceExecuteOnce(&InitOnce, (PINIT_ONCE_FN)InitFn, 0, 0);
  byte_18001F5B0 = 1;
  return (*(__int64 (__fastcall **)(__int64 *))(qword_18001F5A8 + 24))(&qword_18001F5A8) != 0;
}

```

## disassembly

```asm
0x1800030c0  sub     rsp, 28h
0x1800030c4  xor     r9d, r9d; Context
0x1800030c7  lea     rdx, InitFn; InitFn
0x1800030ce  xor     r8d, r8d; Parameter
0x1800030d1  lea     rcx, InitOnce; InitOnce
0x1800030d8  call    cs:InitOnceExecuteOnce
0x1800030de  mov     rax, cs:qword_18001F5A8
0x1800030e5  lea     rcx, qword_18001F5A8
0x1800030ec  mov     cs:byte_18001F5B0, 1
0x1800030f3  mov     rax, [rax+18h]
0x1800030f7  call    j__guard_dispatch_icall
0x1800030fc  xor     ecx, ecx
0x1800030fe  test    eax, eax
0x180003100  setnz   cl
0x180003103  mov     eax, ecx
0x180003105  add     rsp, 28h
0x180003109  retn
```
