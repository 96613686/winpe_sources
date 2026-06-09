# GetKeyEncapsulationInterface

- ea: `0x180063690`
- end: `0x180063705`
- name: `GetKeyEncapsulationInterface`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180063690`
- `0x18007f765`

## string_xrefs

- `0x1800636cc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\interface.c`
- `0x1800636b3`: `Composite-ML-KEM`

## pseudocode

```c
__int64 __fastcall GetKeyEncapsulationInterface(__int64 a1, const wchar_t *a2, _QWORD *a3)
{
  unsigned int v5; // ebx

  if ( !wcscmp_0(a2, L"ML-KEM") || !wcscmp_0(a2, L"Composite-ML-KEM") )
  {
    v5 = 0;
    *a3 = &MSKeyEncapsulationFunctionTable;
  }
  else
  {
    v5 = -1073741637;
    DebugTraceError(
      3221225659LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\interface.c",
      363);
  }
  return v5;
}

```

## disassembly

```asm
0x180063690  mov     [rsp+arg_0], rbx
0x180063695  push    rdi
0x180063696  sub     rsp, 20h
0x18006369a  mov     rbx, rdx
0x18006369d  mov     rdi, r8
0x1800636a0  mov     rcx, rbx; String1
0x1800636a3  lea     rdx, aMlKem; "ML-KEM"
0x1800636aa  call    wcscmp_0
0x1800636af  test    eax, eax
0x1800636b1  jz      short loc_1800636EB
0x1800636b3  lea     rdx, aCompositeMlKem; "Composite-ML-KEM"
0x1800636ba  mov     rcx, rbx; String1
0x1800636bd  call    wcscmp_0
0x1800636c2  test    eax, eax
0x1800636c4  jz      short loc_1800636EB
0x1800636c6  mov     r9d, 16Bh
0x1800636cc  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800636d3  lea     rdx, aStatus; "Status"
0x1800636da  mov     ecx, 0C00000BBh
0x1800636df  mov     ebx, 0C00000BBh
0x1800636e4  call    DebugTraceError
0x1800636e9  jmp     short loc_1800636F7
0x1800636eb  lea     rax, MSKeyEncapsulationFunctionTable
0x1800636f2  xor     ebx, ebx
0x1800636f4  mov     [rdi], rax
0x1800636f7  mov     eax, ebx
0x1800636f9  mov     rbx, [rsp+28h+arg_0]
0x1800636fe  add     rsp, 20h
0x180063702  pop     rdi
0x180063703  retn
```
