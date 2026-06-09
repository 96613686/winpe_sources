# DllCanUnloadNow

- ea: `0x18013c090`
- end: `0x18013c0d6`
- name: `DllCanUnloadNow`
- size: `70`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18013b7f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18013c0a8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18013c0a8`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rdx

  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_180270498 = 1;
  return (unsigned __int8)sub_18013B7F0(&qword_180270490, v0, 0) ^ 1;
}

```

## disassembly

```asm
0x18013c090  sub     rsp, 28h
0x18013c094  xor     r9d, r9d; Context
0x18013c097  lea     rdx, InitFn; InitFn
0x18013c09e  xor     r8d, r8d; Parameter
0x18013c0a1  lea     rcx, InitOnce; InitOnce
0x18013c0a8  call    cs:InitOnceExecuteOnce
0x18013c0af  nop     dword ptr [rax+rax+00h]
0x18013c0b4  xor     r8d, r8d
0x18013c0b7  mov     cs:byte_180270498, 1
0x18013c0be  lea     rcx, qword_180270490
0x18013c0c5  call    sub_18013B7F0
0x18013c0ca  movzx   eax, al
0x18013c0cd  xor     eax, 1
0x18013c0d0  add     rsp, 28h
0x18013c0d4  retn
```
