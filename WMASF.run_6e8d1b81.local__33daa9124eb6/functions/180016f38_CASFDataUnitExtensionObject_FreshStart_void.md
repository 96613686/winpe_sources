# CASFDataUnitExtensionObject::FreshStart(void)

- ea: `0x180016f38`
- end: `0x180016f6d`
- name: `?FreshStart@CASFDataUnitExtensionObject@@IEAAXXZ`
- size: `53`
- prototype: `void __fastcall(CASFDataUnitExtensionObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180016d58`
- `0x180017320`

## callees

- `0x1800011c0`
- `0x180016f38`

## pseudocode

```c
void __fastcall CASFDataUnitExtensionObject::FreshStart(CASFDataUnitExtensionObject *this)
{
  void *v2; // rcx

  *(_OWORD *)((char *)this + 84) = 0;
  *((_WORD *)this + 50) = 0;
  *((_DWORD *)this + 26) = 0;
  v2 = (void *)*((_QWORD *)this + 14);
  if ( v2 )
    operator delete(v2);
  *((_QWORD *)this + 14) = 0;
}

```

## disassembly

```asm
0x180016f38  push    rbx
0x180016f3a  sub     rsp, 20h
0x180016f3e  xor     eax, eax
0x180016f40  xorps   xmm0, xmm0
0x180016f43  movups  xmmword ptr [rcx+54h], xmm0
0x180016f47  mov     [rcx+64h], ax
0x180016f4b  mov     rbx, rcx
0x180016f4e  mov     [rcx+68h], eax
0x180016f51  mov     rcx, [rcx+70h]; Block
0x180016f55  test    rcx, rcx
0x180016f58  jz      short loc_180016F5F
0x180016f5a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016f5f  mov     qword ptr [rbx+70h], 0
0x180016f67  add     rsp, 20h
0x180016f6b  pop     rbx
0x180016f6c  retn
```
