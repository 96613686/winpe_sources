# HPGLDisablePDEV

- ea: `0x180063210`
- end: `0x1800632a2`
- name: `HPGLDisablePDEV`
- size: `146`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800631dc`
- `0x180063210`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006328a`
- `KERNEL32!LocalFree` at `0x18006328a`
- `GDI32!EngDeletePalette` at `0x180063232`
- `GDI32!EngDeletePalette` at `0x180063232`

## pseudocode

```c
unsigned int __fastcall HPGLDisablePDEV(__int64 a1)
{
  _QWORD *v1; // rbx
  HPALETTE v3; // rcx
  unsigned int result; // eax
  BrushCache *v5; // rcx
  BrushCache *v6; // rcx
  void *v7; // rcx

  v1 = *(_QWORD **)(a1 + 8);
  if ( v1 )
  {
    v3 = (HPALETTE)v1[548];
    if ( v3 )
    {
      result = EngDeletePalette(v3);
      v1[548] = 0;
    }
    v5 = (BrushCache *)v1[551];
    if ( v5 )
    {
      result = (unsigned int)BrushCache::`scalar deleting destructor'(v5);
      v1[551] = 0;
    }
    v6 = (BrushCache *)v1[552];
    if ( v6 )
    {
      result = (unsigned int)BrushCache::`scalar deleting destructor'(v6);
      v1[552] = 0;
    }
    v7 = *(void **)(a1 + 8);
    if ( v7 )
      return (unsigned int)LocalFree(v7);
  }
  return result;
}

```

## disassembly

```asm
0x180063210  mov     [rsp+arg_0], rbx
0x180063215  push    rdi
0x180063216  sub     rsp, 20h
0x18006321a  mov     rbx, [rcx+8]
0x18006321e  mov     rdi, rcx
0x180063221  test    rbx, rbx
0x180063224  jz      short loc_180063296
0x180063226  mov     rcx, [rbx+1120h]; hpal
0x18006322d  test    rcx, rcx
0x180063230  jz      short loc_180063249
0x180063232  call    cs:__imp_EngDeletePalette
0x180063239  nop     dword ptr [rax+rax+00h]
0x18006323e  mov     qword ptr [rbx+1120h], 0
0x180063249  mov     rcx, [rbx+1138h]; this
0x180063250  test    rcx, rcx
0x180063253  jz      short loc_180063265
0x180063255  call    ??_GBrushCache@@QEAAPEAXI@Z; BrushCache::`scalar deleting destructor'(uint)
0x18006325a  mov     qword ptr [rbx+1138h], 0
0x180063265  mov     rcx, [rbx+1140h]; this
0x18006326c  test    rcx, rcx
0x18006326f  jz      short loc_180063281
0x180063271  call    ??_GBrushCache@@QEAAPEAXI@Z; BrushCache::`scalar deleting destructor'(uint)
0x180063276  mov     qword ptr [rbx+1140h], 0
0x180063281  mov     rcx, [rdi+8]; hMem
0x180063285  test    rcx, rcx
0x180063288  jz      short loc_180063296
0x18006328a  call    cs:__imp_LocalFree
0x180063291  nop     dword ptr [rax+rax+00h]
0x180063296  mov     rbx, [rsp+28h+arg_0]
0x18006329b  add     rsp, 20h
0x18006329f  pop     rdi
0x1800632a0  retn
```
