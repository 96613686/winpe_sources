# CNetworkExplorerInfoBar::~CNetworkExplorerInfoBar(void)

- ea: `0x180008cb0`
- end: `0x180008ce9`
- name: `??1CNetworkExplorerInfoBar@@AEAA@XZ`
- size: `57`
- prototype: `void __fastcall(CNetworkExplorerInfoBar *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000af60`

## callees

- `0x180008cb0`
- `0x180010010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180008cdc`
- `GDI32!DeleteObject` at `0x180008cdc`

## pseudocode

```c
void __fastcall CNetworkExplorerInfoBar::~CNetworkExplorerInfoBar(CNetworkExplorerInfoBar *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CNetworkExplorerInfoBar::`vftable';
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    DeleteObject(v2);
}

```

## disassembly

```asm
0x180008cb0  push    rbx
0x180008cb2  sub     rsp, 20h
0x180008cb6  mov     rbx, rcx
0x180008cb9  lea     rax, ??_7CNetworkExplorerInfoBar@@6B@; const CNetworkExplorerInfoBar::`vftable'
0x180008cc0  mov     [rcx], rax
0x180008cc3  mov     rcx, [rcx+10h]
0x180008cc7  mov     rax, [rcx]
0x180008cca  mov     rax, [rax+10h]
0x180008cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cd3  mov     rcx, [rbx+18h]; ho
0x180008cd7  test    rcx, rcx
0x180008cda  jz      short loc_180008CE3
0x180008cdc  call    cs:__imp_DeleteObject
0x180008ce2  nop
0x180008ce3  add     rsp, 20h
0x180008ce7  pop     rbx
0x180008ce8  retn
```
