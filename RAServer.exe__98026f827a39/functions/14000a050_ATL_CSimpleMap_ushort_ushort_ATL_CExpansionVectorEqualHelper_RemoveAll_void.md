# ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)

- ea: `0x14000a050`
- end: `0x14000a09b`
- name: `?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ`
- size: `75`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a00`
- `0x140005074`

## callees

- `0x14000a050`

## import_xrefs

- `msvcrt!free` at `0x14000a065`
- `msvcrt!free` at `0x14000a07b`
- `msvcrt!free` at `0x14000a065`
- `msvcrt!free` at `0x14000a07b`

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
0x14000a050  mov     [rsp+arg_0], rbx
0x14000a055  push    rdi
0x14000a056  sub     rsp, 20h
0x14000a05a  mov     rbx, rcx
0x14000a05d  mov     rcx, [rcx]; Block
0x14000a060  test    rcx, rcx
0x14000a063  jz      short loc_14000A072
0x14000a065  call    cs:__imp_free
0x14000a06b  mov     qword ptr [rbx], 0
0x14000a072  mov     rcx, [rbx+8]; Block
0x14000a076  test    rcx, rcx
0x14000a079  jz      short loc_14000A089
0x14000a07b  call    cs:__imp_free
0x14000a081  mov     qword ptr [rbx+8], 0
0x14000a089  mov     dword ptr [rbx+10h], 0
0x14000a090  mov     rbx, [rsp+28h+arg_0]
0x14000a095  add     rsp, 20h
0x14000a099  pop     rdi
0x14000a09a  retn
```
