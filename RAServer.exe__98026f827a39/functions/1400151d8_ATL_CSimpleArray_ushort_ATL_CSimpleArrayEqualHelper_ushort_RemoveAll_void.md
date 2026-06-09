# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x1400151d8`
- end: `0x14001520d`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `53`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400150dc`
- `0x14001513c`

## callees

- `0x1400151d8`

## import_xrefs

- `msvcrt!free` at `0x1400151ed`
- `msvcrt!free` at `0x1400151ed`

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
0x1400151d8  mov     [rsp+arg_0], rbx
0x1400151dd  push    rdi
0x1400151de  sub     rsp, 20h
0x1400151e2  mov     rbx, rcx
0x1400151e5  mov     rcx, [rcx]; Block
0x1400151e8  test    rcx, rcx
0x1400151eb  jz      short loc_1400151FA
0x1400151ed  call    cs:__imp_free
0x1400151f3  mov     qword ptr [rbx], 0
0x1400151fa  mov     qword ptr [rbx+8], 0
0x140015202  mov     rbx, [rsp+28h+arg_0]
0x140015207  add     rsp, 20h
0x14001520b  pop     rdi
0x14001520c  retn
```
