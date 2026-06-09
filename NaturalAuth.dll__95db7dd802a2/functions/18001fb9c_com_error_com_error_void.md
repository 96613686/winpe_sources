# _com_error::~_com_error(void)

- ea: `0x18001fb9c`
- end: `0x18001fbda`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001fc30`
- `0x180043655`
- `0x180043806`
- `0x18004382a`
- `0x180043fdf`
- `0x180044270`

## callees

- `0x18001fb9c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fbcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fbcd`

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
0x18001fb9c  push    rbx
0x18001fb9e  sub     rsp, 20h
0x18001fba2  mov     rbx, rcx
0x18001fba5  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001fbac  mov     [rcx], rax
0x18001fbaf  mov     rcx, [rcx+10h]
0x18001fbb3  test    rcx, rcx
0x18001fbb6  jz      short loc_18001FBC4
0x18001fbb8  mov     rax, [rcx]
0x18001fbbb  mov     rax, [rax+10h]
0x18001fbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbc4  mov     rcx, [rbx+18h]; hMem
0x18001fbc8  test    rcx, rcx
0x18001fbcb  jz      short loc_18001FBD4
0x18001fbcd  call    cs:__imp_LocalFree
0x18001fbd3  nop
0x18001fbd4  add     rsp, 20h
0x18001fbd8  pop     rbx
0x18001fbd9  retn
```
