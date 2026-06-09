# _com_error::~_com_error(void)

- ea: `0x140008890`
- end: `0x1400088ce`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400088e0`

## callees

- `0x140008890`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400088c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400088c1`

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
0x140008890  push    rbx
0x140008892  sub     rsp, 20h
0x140008896  mov     rbx, rcx
0x140008899  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1400088a0  mov     [rcx], rax
0x1400088a3  mov     rcx, [rcx+10h]
0x1400088a7  test    rcx, rcx
0x1400088aa  jz      short loc_1400088B8
0x1400088ac  mov     rax, [rcx]
0x1400088af  mov     rax, [rax+10h]
0x1400088b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088b8  mov     rcx, [rbx+18h]; hMem
0x1400088bc  test    rcx, rcx
0x1400088bf  jz      short loc_1400088C8
0x1400088c1  call    cs:__imp_LocalFree
0x1400088c7  nop
0x1400088c8  add     rsp, 20h
0x1400088cc  pop     rbx
0x1400088cd  retn
```
