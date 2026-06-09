# FreeSemanticVector(tagSemanticVector *)

- ea: `0x14004433c`
- end: `0x14004437d`
- name: `?FreeSemanticVector@@YAXPEAUtagSemanticVector@@@Z`
- size: `65`
- prototype: `void __fastcall(struct tagSemanticVector *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140043b40`
- `0x1400454ac`
- `0x1400469a4`

## callees

- `0x14004433c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044352`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044369`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044352`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044369`

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
0x14004433c  test    rcx, rcx
0x14004433f  jz      short locret_14004437C
0x140044341  push    rbx
0x140044342  sub     rsp, 20h
0x140044346  mov     rbx, rcx
0x140044349  mov     rcx, [rcx+8]; pv
0x14004434d  test    rcx, rcx
0x140044350  jz      short loc_140044360
0x140044352  call    cs:__imp_CoTaskMemFree
0x140044358  mov     qword ptr [rbx+8], 0
0x140044360  mov     rcx, [rbx+18h]; pv
0x140044364  test    rcx, rcx
0x140044367  jz      short loc_140044377
0x140044369  call    cs:__imp_CoTaskMemFree
0x14004436f  mov     qword ptr [rbx+18h], 0
0x140044377  add     rsp, 20h
0x14004437b  pop     rbx
0x14004437c  retn
```
