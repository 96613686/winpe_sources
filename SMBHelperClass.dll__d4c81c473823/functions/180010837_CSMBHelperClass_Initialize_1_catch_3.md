# _CSMBHelperClass::Initialize_::_1_::catch$3

- ea: `0x180010837`
- end: `0x180010870`
- name: `_CSMBHelperClass::Initialize_::_1_::catch$3`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180010858`
- `msvcrt!??1exception@@UEAA@XZ` at `0x180010858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001084b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001084b`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::Initialize_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CoTaskMemFree(*(LPVOID *)(a2 + 224));
  exception::~exception((exception *)(a2 + 128));
  return 0;
}

```

## disassembly

```asm
0x180010837  mov     [rsp+arg_8], rdx
0x18001083c  push    rbp
0x18001083d  sub     rsp, 20h
0x180010841  mov     rbp, rdx
0x180010844  mov     rcx, [rbp+0E0h]; pv
0x18001084b  call    cs:__imp_CoTaskMemFree
0x180010851  lea     rcx, [rbp+80h]
0x180010858  call    cs:__imp_??1exception@@UEAA@XZ; exception::~exception(void)
0x18001085e  nop
0x18001085f  mov     rax, 0
0x180010869  add     rsp, 20h
0x18001086d  pop     rbp
0x18001086e  retn
```
