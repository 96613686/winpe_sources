# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x180005c44`
- end: `0x180005c79`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `53`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004674`
- `0x180005c18`

## callees

- `0x180005c44`

## import_xrefs

- `msvcrt!free` at `0x180005c59`
- `msvcrt!free` at `0x180005c59`

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
0x180005c44  mov     [rsp+arg_0], rbx
0x180005c49  push    rdi
0x180005c4a  sub     rsp, 20h
0x180005c4e  mov     rbx, rcx
0x180005c51  mov     rcx, [rcx]; Block
0x180005c54  test    rcx, rcx
0x180005c57  jz      short loc_180005C66
0x180005c59  call    cs:__imp_free
0x180005c5f  mov     qword ptr [rbx], 0
0x180005c66  mov     qword ptr [rbx+8], 0
0x180005c6e  mov     rbx, [rsp+28h+arg_0]
0x180005c73  add     rsp, 20h
0x180005c77  pop     rdi
0x180005c78  retn
```
