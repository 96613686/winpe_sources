# _com_error::~_com_error(void)

- ea: `0x18001d1b0`
- end: `0x18001d1ed`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d200`

## callees

- `0x18001d1b0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d1e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d1e1`

## pseudocode

```c
void __fastcall _com_error::~_com_error(_com_error *this)
{
  __int64 v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x18001d1b0  push    rbx
0x18001d1b2  sub     rsp, 20h
0x18001d1b6  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001d1bd  mov     rbx, rcx
0x18001d1c0  mov     [rcx], rax
0x18001d1c3  mov     rcx, [rcx+10h]
0x18001d1c7  test    rcx, rcx
0x18001d1ca  jz      short loc_18001D1D8
0x18001d1cc  mov     rax, [rcx]
0x18001d1cf  mov     rax, [rax+10h]
0x18001d1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1d8  mov     rcx, [rbx+18h]; hMem
0x18001d1dc  test    rcx, rcx
0x18001d1df  jz      short loc_18001D1E7
0x18001d1e1  call    cs:__imp_LocalFree
0x18001d1e7  add     rsp, 20h
0x18001d1eb  pop     rbx
0x18001d1ec  retn
```
