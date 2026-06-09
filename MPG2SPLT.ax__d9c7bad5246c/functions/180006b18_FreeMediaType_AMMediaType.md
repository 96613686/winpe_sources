# FreeMediaType(_AMMediaType &)

- ea: `0x180006b18`
- end: `0x180006b4e`
- name: `?FreeMediaType@@YAXAEAU_AMMediaType@@@Z`
- size: `54`
- prototype: `void __fastcall(struct _AMMediaType *)`
- caller_count: `30`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800030c8`
- `0x180004a10`
- `0x180005db0`
- `0x1800063a0`
- `0x1800068e4`
- `0x180006af0`
- `0x180008bb8`
- `0x180008d84`
- `0x180008ea0`
- `0x180009348`
- `0x18000a2d0`
- `0x18000a434`
- `0x18000a510`
- `0x18000a870`
- `0x18000b934`
- `0x18000bed0`
- `0x18000ef04`
- `0x180014370`
- `0x180016410`
- `0x1800174cc`
- `0x18001cad0`
- `0x18001cc60`
- `0x18001fe90`
- `0x18001fff4`
- `0x180020208`
- `0x180020318`
- `0x1800203fc`
- `0x180020a34`
- `0x1800221c4`
- `0x18002b038`

## callees

- `0x180006b18`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006b2b`
- `ole32!CoTaskMemFree` at `0x180006b2b`

## pseudocode

```c
void __fastcall FreeMediaType(struct _AMMediaType *a1)
{
  if ( a1->cbFormat )
  {
    CoTaskMemFree(a1->pbFormat);
    a1->cbFormat = 0;
    a1->pbFormat = 0;
  }
  a1->pUnk = 0;
}

```

## disassembly

```asm
0x180006b18  push    rbx
0x180006b1a  sub     rsp, 20h
0x180006b1e  cmp     dword ptr [rcx+48h], 0
0x180006b22  mov     rbx, rcx
0x180006b25  jz      short loc_180006B40
0x180006b27  mov     rcx, [rcx+50h]; pv
0x180006b2b  call    cs:__imp_CoTaskMemFree
0x180006b31  mov     dword ptr [rbx+48h], 0
0x180006b38  mov     qword ptr [rbx+50h], 0
0x180006b40  mov     qword ptr [rbx+40h], 0
0x180006b48  add     rsp, 20h
0x180006b4c  pop     rbx
0x180006b4d  retn
```
