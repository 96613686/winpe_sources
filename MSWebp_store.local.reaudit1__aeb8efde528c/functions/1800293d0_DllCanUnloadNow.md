# DllCanUnloadNow

- ea: `0x1800293d0`
- end: `0x180029416`
- name: `DllCanUnloadNow`
- size: `70`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180029194`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800293e8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800293e8`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rdx

  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_1800464A0 = 1;
  return (unsigned __int8)sub_180029194(&qword_180046498, v0, 0) ^ 1;
}

```

## disassembly

```asm
0x1800293d0  sub     rsp, 28h
0x1800293d4  xor     r9d, r9d; Context
0x1800293d7  lea     rdx, InitFn; InitFn
0x1800293de  xor     r8d, r8d; Parameter
0x1800293e1  lea     rcx, InitOnce; InitOnce
0x1800293e8  call    cs:InitOnceExecuteOnce
0x1800293ef  nop     dword ptr [rax+rax+00h]
0x1800293f4  xor     r8d, r8d
0x1800293f7  mov     cs:byte_1800464A0, 1
0x1800293fe  lea     rcx, qword_180046498
0x180029405  call    sub_180029194
0x18002940a  movzx   eax, al
0x18002940d  xor     eax, 1
0x180029410  add     rsp, 28h
0x180029414  retn
```
