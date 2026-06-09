# _com_error::~_com_error(void)

- ea: `0x1800099b4`
- end: `0x1800099f2`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800099b4`
- `0x18000d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800099e5`
- `KERNEL32!LocalFree` at `0x1800099e5`

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
0x1800099b4  push    rbx
0x1800099b6  sub     rsp, 20h
0x1800099ba  mov     rbx, rcx
0x1800099bd  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800099c4  mov     [rcx], rax
0x1800099c7  mov     rcx, [rcx+10h]
0x1800099cb  test    rcx, rcx
0x1800099ce  jz      short loc_1800099DC
0x1800099d0  mov     rax, [rcx]
0x1800099d3  mov     rax, [rax+10h]
0x1800099d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099dc  mov     rcx, [rbx+18h]; hMem
0x1800099e0  test    rcx, rcx
0x1800099e3  jz      short loc_1800099EC
0x1800099e5  call    cs:__imp_LocalFree
0x1800099eb  nop
0x1800099ec  add     rsp, 20h
0x1800099f0  pop     rbx
0x1800099f1  retn
```
