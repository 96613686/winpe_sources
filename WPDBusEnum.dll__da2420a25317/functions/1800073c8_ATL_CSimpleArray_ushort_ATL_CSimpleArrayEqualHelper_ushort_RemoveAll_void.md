# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x1800073c8`
- end: `0x1800073fc`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007330`

## callees

- `0x1800073c8`
- `0x18000a156`

## pseudocode

```c
void __fastcall ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    free(v2);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
}

```

## disassembly

```asm
0x1800073c8  mov     [rsp+arg_0], rbx
0x1800073cd  push    rdi
0x1800073ce  sub     rsp, 20h
0x1800073d2  mov     rbx, rcx
0x1800073d5  mov     rcx, [rcx]; Block
0x1800073d8  test    rcx, rcx
0x1800073db  jz      short loc_1800073E9
0x1800073dd  call    free
0x1800073e2  mov     qword ptr [rbx], 0
0x1800073e9  mov     qword ptr [rbx+8], 0
0x1800073f1  mov     rbx, [rsp+28h+arg_0]
0x1800073f6  add     rsp, 20h
0x1800073fa  pop     rdi
0x1800073fb  retn
```
