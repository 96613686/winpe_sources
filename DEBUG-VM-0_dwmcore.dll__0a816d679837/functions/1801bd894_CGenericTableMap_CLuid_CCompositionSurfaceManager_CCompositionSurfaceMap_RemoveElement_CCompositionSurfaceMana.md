# CGenericTableMap<CLuid,CCompositionSurfaceManager::CCompositionSurfaceMap>::RemoveElement(CCompositionSurfaceManager::CCompositionSurfaceMap *)

- ea: `0x1801bd894`
- end: `0x1801bd8cd`
- name: `?RemoveElement@?$CGenericTableMap@VCLuid@@VCCompositionSurfaceMap@CCompositionSurfaceManager@@@@QEAAXPEAVCCompositionSurfaceMap@CCompositionSurfaceManager@@@Z`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801bd840`
- `0x1802338b0`
- `0x180235a50`

## callees

- `0x1801bd894`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1801bd8c5`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1801bd8c5`
- `ntdll!RtlDeleteElementGenericTable` at `0x1801bd8ae`
- `ntdll!RtlDeleteElementGenericTable` at `0x1801bd8ae`

## pseudocode

```c
void __fastcall CGenericTableMap<CLuid,CCompositionSurfaceManager::CCompositionSurfaceMap>::RemoveElement(
        struct _RTL_GENERIC_TABLE *a1,
        _QWORD *a2)
{
  _QWORD Buffer[3]; // [rsp+20h] [rbp-18h] BYREF

  Buffer[0] = *a2;
  Buffer[1] = 0;
  if ( !RtlDeleteElementGenericTable(a1, Buffer) )
    RaiseFailFastException(0, 0, 1u);
}

```

## disassembly

```asm
0x1801bd894  sub     rsp, 38h
0x1801bd898  mov     rax, [rdx]
0x1801bd89b  lea     rdx, [rsp+38h+Buffer]; Buffer
0x1801bd8a0  mov     [rsp+38h+Buffer], rax
0x1801bd8a5  mov     [rsp+38h+var_10], 0
0x1801bd8ae  call    cs:__imp_RtlDeleteElementGenericTable
0x1801bd8b4  test    al, al
0x1801bd8b6  jz      short loc_1801BD8BD
0x1801bd8b8  add     rsp, 38h
0x1801bd8bc  retn
0x1801bd8bd  xor     edx, edx; pContextRecord
0x1801bd8bf  xor     ecx, ecx; pExceptionRecord
0x1801bd8c1  lea     r8d, [rdx+1]; dwFlags
0x1801bd8c5  call    cs:__imp_RaiseFailFastException
0x1801bd8cb  jmp     short loc_1801BD8B8
```
