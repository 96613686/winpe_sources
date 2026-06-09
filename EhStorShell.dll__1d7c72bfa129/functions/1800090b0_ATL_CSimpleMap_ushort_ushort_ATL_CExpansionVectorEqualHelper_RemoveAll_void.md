# ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)

- ea: `0x1800090b0`
- end: `0x1800090fb`
- name: `?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ`
- size: `75`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007acc`
- `0x1800085d4`

## callees

- `0x1800090b0`

## import_xrefs

- `msvcrt!free` at `0x1800090c5`
- `msvcrt!free` at `0x1800090db`
- `msvcrt!free` at `0x1800090c5`
- `msvcrt!free` at `0x1800090db`

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
0x1800090b0  mov     [rsp+arg_0], rbx
0x1800090b5  push    rdi
0x1800090b6  sub     rsp, 20h
0x1800090ba  mov     rbx, rcx
0x1800090bd  mov     rcx, [rcx]; Block
0x1800090c0  test    rcx, rcx
0x1800090c3  jz      short loc_1800090D2
0x1800090c5  call    cs:__imp_free
0x1800090cb  mov     qword ptr [rbx], 0
0x1800090d2  mov     rcx, [rbx+8]; Block
0x1800090d6  test    rcx, rcx
0x1800090d9  jz      short loc_1800090E9
0x1800090db  call    cs:__imp_free
0x1800090e1  mov     qword ptr [rbx+8], 0
0x1800090e9  mov     dword ptr [rbx+10h], 0
0x1800090f0  mov     rbx, [rsp+28h+arg_0]
0x1800090f5  add     rsp, 20h
0x1800090f9  pop     rdi
0x1800090fa  retn
```
