# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x18000e128`
- end: `0x18000e15f`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `55`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e0e0`

## callees

- `0x18000e128`

## import_xrefs

- `msvcrt!free` at `0x18000e150`
- `msvcrt!free` at `0x18000e150`

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
0x18000e128  mov     [rsp+arg_0], rbx
0x18000e12d  push    rdi
0x18000e12e  sub     rsp, 20h
0x18000e132  mov     rbx, rcx
0x18000e135  mov     rcx, [rcx]; Block
0x18000e138  test    rcx, rcx
0x18000e13b  jnz     short loc_18000E150
0x18000e13d  mov     qword ptr [rbx+8], 0
0x18000e145  mov     rbx, [rsp+28h+arg_0]
0x18000e14a  add     rsp, 20h
0x18000e14e  pop     rdi
0x18000e14f  retn
0x18000e150  call    cs:__imp_free
0x18000e156  mov     qword ptr [rbx], 0
0x18000e15d  jmp     short loc_18000E13D
```
