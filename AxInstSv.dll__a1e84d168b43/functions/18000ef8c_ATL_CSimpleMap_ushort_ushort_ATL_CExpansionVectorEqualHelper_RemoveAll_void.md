# ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)

- ea: `0x18000ef8c`
- end: `0x18000efd7`
- name: `?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800088b4`
- `0x18000a03c`

## callees

- `0x18000ef8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000efa1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000efb7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000efa1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000efb7`

## pseudocode

```c
void __fastcall ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(
        __int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    free(v2);
    *(_QWORD *)a1 = 0;
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
  {
    free(v3);
    *(_QWORD *)(a1 + 8) = 0;
  }
  *(_DWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x18000ef8c  mov     [rsp+arg_0], rbx
0x18000ef91  push    rdi
0x18000ef92  sub     rsp, 20h
0x18000ef96  mov     rbx, rcx
0x18000ef99  mov     rcx, [rcx]; Block
0x18000ef9c  test    rcx, rcx
0x18000ef9f  jz      short loc_18000EFAE
0x18000efa1  call    cs:__imp_free
0x18000efa7  mov     qword ptr [rbx], 0
0x18000efae  mov     rcx, [rbx+8]; Block
0x18000efb2  test    rcx, rcx
0x18000efb5  jz      short loc_18000EFC5
0x18000efb7  call    cs:__imp_free
0x18000efbd  mov     qword ptr [rbx+8], 0
0x18000efc5  mov     dword ptr [rbx+10h], 0
0x18000efcc  mov     rbx, [rsp+28h+arg_0]
0x18000efd1  add     rsp, 20h
0x18000efd5  pop     rdi
0x18000efd6  retn
```
