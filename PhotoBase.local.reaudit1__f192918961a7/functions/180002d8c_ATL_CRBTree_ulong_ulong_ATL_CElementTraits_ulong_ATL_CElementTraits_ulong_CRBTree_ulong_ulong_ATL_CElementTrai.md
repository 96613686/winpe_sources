# ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::~CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>(void)

- ea: `0x180002d8c`
- end: `0x180002daf`
- name: `??1?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAA@XZ`
- size: `35`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d80`
- `0x180002de0`
- `0x180002df0`
- `0x180003550`
- `0x18000408c`

## callees

- `0x180002d8c`
- `0x180005f54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002da3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002da3`

## pseudocode

```c
void __fastcall ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::~CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>(
        _QWORD *a1)
{
  void *v2; // rcx

  ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RemoveAll(a1);
  v2 = (void *)a1[5];
  if ( v2 )
    free(v2);
}

```

## disassembly

```asm
0x180002d8c  push    rbx
0x180002d8e  sub     rsp, 20h
0x180002d92  mov     rbx, rcx
0x180002d95  call    ?RemoveAll@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAAXXZ; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RemoveAll(void)
0x180002d9a  mov     rcx, [rbx+28h]; Block
0x180002d9e  test    rcx, rcx
0x180002da1  jz      short loc_180002DA9
0x180002da3  call    cs:__imp_free
0x180002da9  add     rsp, 20h
0x180002dad  pop     rbx
0x180002dae  retn
```
