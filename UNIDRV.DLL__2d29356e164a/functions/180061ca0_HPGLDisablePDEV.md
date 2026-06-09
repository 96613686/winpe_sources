# HPGLDisablePDEV

- ea: `0x180061ca0`
- end: `0x180061d25`
- name: `HPGLDisablePDEV`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180061c68`
- `0x180061ca0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180061d14`
- `KERNEL32!LocalFree` at `0x180061d14`
- `GDI32!EngDeletePalette` at `0x180061cc2`
- `GDI32!EngDeletePalette` at `0x180061cc2`

## pseudocode

```c
unsigned int __fastcall HPGLDisablePDEV(__int64 a1, unsigned int a2)
{
  _QWORD *v2; // rbx
  HPALETTE v4; // rcx
  unsigned int result; // eax
  BrushCache *v6; // rcx
  BrushCache *v7; // rcx
  void *v8; // rcx

  v2 = *(_QWORD **)(a1 + 8);
  if ( v2 )
  {
    v4 = (HPALETTE)v2[548];
    if ( v4 )
    {
      result = EngDeletePalette(v4);
      v2[548] = 0;
    }
    v6 = (BrushCache *)v2[551];
    if ( v6 )
    {
      result = (unsigned int)BrushCache::`scalar deleting destructor'(v6, a2);
      v2[551] = 0;
    }
    v7 = (BrushCache *)v2[552];
    if ( v7 )
    {
      result = (unsigned int)BrushCache::`scalar deleting destructor'(v7, a2);
      v2[552] = 0;
    }
    v8 = *(void **)(a1 + 8);
    if ( v8 )
      return (unsigned int)LocalFree(v8);
  }
  return result;
}

```

## disassembly

```asm
0x180061ca0  mov     [rsp+arg_0], rbx
0x180061ca5  push    rdi
0x180061ca6  sub     rsp, 20h
0x180061caa  mov     rbx, [rcx+8]
0x180061cae  mov     rdi, rcx
0x180061cb1  test    rbx, rbx
0x180061cb4  jz      short loc_180061D1A
0x180061cb6  mov     rcx, [rbx+1120h]; hpal
0x180061cbd  test    rcx, rcx
0x180061cc0  jz      short loc_180061CD3
0x180061cc2  call    cs:__imp_EngDeletePalette
0x180061cc8  mov     qword ptr [rbx+1120h], 0
0x180061cd3  mov     rcx, [rbx+1138h]; this
0x180061cda  test    rcx, rcx
0x180061cdd  jz      short loc_180061CEF
0x180061cdf  call    ??_GBrushCache@@QEAAPEAXI@Z; BrushCache::`scalar deleting destructor'(uint)
0x180061ce4  mov     qword ptr [rbx+1138h], 0
0x180061cef  mov     rcx, [rbx+1140h]; this
0x180061cf6  test    rcx, rcx
0x180061cf9  jz      short loc_180061D0B
0x180061cfb  call    ??_GBrushCache@@QEAAPEAXI@Z; BrushCache::`scalar deleting destructor'(uint)
0x180061d00  mov     qword ptr [rbx+1140h], 0
0x180061d0b  mov     rcx, [rdi+8]; hMem
0x180061d0f  test    rcx, rcx
0x180061d12  jz      short loc_180061D1A
0x180061d14  call    cs:__imp_LocalFree
0x180061d1a  mov     rbx, [rsp+28h+arg_0]
0x180061d1f  add     rsp, 20h
0x180061d23  pop     rdi
0x180061d24  retn
```
