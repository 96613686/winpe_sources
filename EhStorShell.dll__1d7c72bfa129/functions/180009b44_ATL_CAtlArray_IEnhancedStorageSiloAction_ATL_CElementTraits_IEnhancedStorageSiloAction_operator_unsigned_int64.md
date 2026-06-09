# ATL::CAtlArray<IEnhancedStorageSiloAction *,ATL::CElementTraits<IEnhancedStorageSiloAction *>>::operator[](unsigned __int64)

- ea: `0x180009b44`
- end: `0x180009b65`
- name: `??A?$CAtlArray@PEAUIEnhancedStorageSiloAction@@V?$CElementTraits@PEAUIEnhancedStorageSiloAction@@@ATL@@@ATL@@QEAAAEAPEAUIEnhancedStorageSiloAction@@_K@Z`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004ef0`
- `0x180009d90`
- `0x180009f00`

## callees

- `0x180005a10`
- `0x180009b44`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<IEnhancedStorageSiloAction *,ATL::CElementTraits<IEnhancedStorageSiloAction *>>::operator[](
        _QWORD *a1,
        unsigned __int64 a2)
{
  if ( a2 >= a1[1] )
    ATL::AtlThrowImpl(-2147024809);
  return *a1 + 8 * a2;
}

```

## disassembly

```asm
0x180009b44  sub     rsp, 28h
0x180009b48  cmp     rdx, [rcx+8]
0x180009b4c  jb      short loc_180009B59
0x180009b4e  mov     ecx, 80070057h; int
0x180009b53  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009b59  mov     rax, [rcx]
0x180009b5c  lea     rax, [rax+rdx*8]
0x180009b60  add     rsp, 28h
0x180009b64  retn
```
