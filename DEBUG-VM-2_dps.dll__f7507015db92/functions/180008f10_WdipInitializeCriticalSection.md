# WdipInitializeCriticalSection

- ea: `0x180008f10`
- end: `0x180008f6a`
- name: `WdipInitializeCriticalSection`
- size: `90`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003020`
- `0x180006188`
- `0x180007adc`
- `0x18000ed8c`
- `0x18000f534`

## callees

- `0x180008f10`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008f1f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008f1f`

## string_xrefs

- `0x180008f50`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`

## pseudocode

```c
__int64 __fastcall WdipInitializeCriticalSection(__int64 a1)
{
  InitializeCriticalSection((LPCRITICAL_SECTION)a1);
  *(_DWORD *)(a1 + 40) = 1;
  return 0;
}

```

## disassembly

```asm
0x180008f10  mov     [rsp+arg_0], rbx
0x180008f15  push    rdi
0x180008f16  sub     rsp, 30h
0x180008f1a  mov     rbx, rcx
0x180008f1d  xor     edi, edi
0x180008f1f  call    cs:__imp_InitializeCriticalSection
0x180008f25  nop
0x180008f26  mov     dword ptr [rbx+28h], 1
0x180008f2d  jmp     short loc_180008F5D
0x180008f2f  mov     edi, 8007000Eh
0x180008f34  mov     dword ptr [rsp+38h+Args], 0Eh; Args
0x180008f3c  lea     r9, aErrorD; "Error = %d"
0x180008f43  mov     r8d, 0E9h; int
0x180008f49  lea     rdx, aWdipinitialize; "WdipInitializeCriticalSection"
0x180008f50  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008f57  call    WdipTraceError
0x180008f5c  nop
0x180008f5d  mov     eax, edi
0x180008f5f  mov     rbx, [rsp+38h+arg_0]
0x180008f64  add     rsp, 30h
0x180008f68  pop     rdi
0x180008f69  retn
0x180018c66  push    rbp
0x180018c68  sub     rsp, 30h
0x180018c6c  mov     rbp, rdx
0x180018c6f  mov     rax, [rcx]
0x180018c72  xor     ecx, ecx
0x180018c74  cmp     dword ptr [rax], 0C0000017h
0x180018c7a  setz    cl
0x180018c7d  mov     eax, ecx
0x180018c7f  add     rsp, 30h
0x180018c83  pop     rbp
0x180018c84  retn
```
