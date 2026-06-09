# XcGetLoadError(IXMLDOMDocument2 *)

- ea: `0x180012808`
- end: `0x180012884`
- name: `?XcGetLoadError@@YAKPEAUIXMLDOMDocument2@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d2c4`
- `0x18000e3f0`
- `0x180012fe0`

## callees

- `0x180012808`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall XcGetLoadError(struct IXMLDOMDocument2 *a1)
{
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  unsigned int v2; // ebx
  int v4; // [rsp+30h] [rbp+8h] BYREF
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  lpVtbl = a1->lpVtbl;
  v5 = 0;
  v2 = 1206;
  v4 = 0;
  if ( !((unsigned int (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *))lpVtbl->get_parseError)(a1, &v5)
    && !(*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 56LL))(v5, &v4)
    && v4 == -2147024882 )
  {
    v2 = 14;
  }
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return v2;
}

```

## disassembly

```asm
0x180012808  push    rbx
0x18001280a  sub     rsp, 20h
0x18001280e  mov     rax, [rcx]
0x180012811  lea     rdx, [rsp+28h+arg_8]
0x180012816  mov     [rsp+28h+arg_8], 0
0x18001281f  mov     ebx, 4B6h
0x180012824  mov     [rsp+28h+arg_0], 0
0x18001282c  mov     rax, [rax+1E0h]
0x180012833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012838  test    eax, eax
0x18001283a  jnz     short loc_180012866
0x18001283c  mov     rcx, [rsp+28h+arg_8]
0x180012841  lea     rdx, [rsp+28h+arg_0]
0x180012846  mov     rax, [rcx]
0x180012849  mov     rax, [rax+38h]
0x18001284d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012852  test    eax, eax
0x180012854  jnz     short loc_180012866
0x180012856  cmp     [rsp+28h+arg_0], 8007000Eh
0x18001285e  mov     eax, 0Eh
0x180012863  cmovz   ebx, eax
0x180012866  mov     rcx, [rsp+28h+arg_8]
0x18001286b  test    rcx, rcx
0x18001286e  jz      short loc_18001287C
0x180012870  mov     rdx, [rcx]
0x180012873  mov     rax, [rdx+10h]
0x180012877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001287c  mov     eax, ebx
0x18001287e  add     rsp, 20h
0x180012882  pop     rbx
0x180012883  retn
```
