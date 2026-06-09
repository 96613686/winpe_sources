# FreeSemanticVector(tagSemanticVector *)

- ea: `0x14005d48c`
- end: `0x14005d4cd`
- name: `?FreeSemanticVector@@YAXPEAUtagSemanticVector@@@Z`
- size: `65`
- prototype: `void __fastcall(struct tagSemanticVector *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005ccd8`
- `0x14005e5fc`
- `0x14005fa54`

## callees

- `0x14005d48c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005d4a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005d4b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005d4a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005d4b9`

## pseudocode

```c
void __fastcall FreeSemanticVector(struct tagSemanticVector *a1)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( a1 )
  {
    v2 = (void *)*((_QWORD *)a1 + 1);
    if ( v2 )
    {
      CoTaskMemFree(v2);
      *((_QWORD *)a1 + 1) = 0;
    }
    v3 = (void *)*((_QWORD *)a1 + 3);
    if ( v3 )
    {
      CoTaskMemFree(v3);
      *((_QWORD *)a1 + 3) = 0;
    }
  }
}

```

## disassembly

```asm
0x14005d48c  test    rcx, rcx
0x14005d48f  jz      short locret_14005D4CC
0x14005d491  push    rbx
0x14005d492  sub     rsp, 20h
0x14005d496  mov     rbx, rcx
0x14005d499  mov     rcx, [rcx+8]; pv
0x14005d49d  test    rcx, rcx
0x14005d4a0  jz      short loc_14005D4B0
0x14005d4a2  call    cs:__imp_CoTaskMemFree
0x14005d4a8  mov     qword ptr [rbx+8], 0
0x14005d4b0  mov     rcx, [rbx+18h]; pv
0x14005d4b4  test    rcx, rcx
0x14005d4b7  jz      short loc_14005D4C7
0x14005d4b9  call    cs:__imp_CoTaskMemFree
0x14005d4bf  mov     qword ptr [rbx+18h], 0
0x14005d4c7  add     rsp, 20h
0x14005d4cb  pop     rbx
0x14005d4cc  retn
```
