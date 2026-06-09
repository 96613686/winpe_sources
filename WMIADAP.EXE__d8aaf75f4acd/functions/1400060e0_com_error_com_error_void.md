# _com_error::~_com_error(void)

- ea: `0x1400060e0`
- end: `0x14000611d`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006130`

## callees

- `0x1400060e0`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006111`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006111`

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
0x1400060e0  push    rbx
0x1400060e2  sub     rsp, 20h
0x1400060e6  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1400060ed  mov     rbx, rcx
0x1400060f0  mov     [rcx], rax
0x1400060f3  mov     rcx, [rcx+10h]
0x1400060f7  test    rcx, rcx
0x1400060fa  jz      short loc_140006108
0x1400060fc  mov     rax, [rcx]
0x1400060ff  mov     rax, [rax+10h]
0x140006103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006108  mov     rcx, [rbx+18h]; hMem
0x14000610c  test    rcx, rcx
0x14000610f  jz      short loc_140006117
0x140006111  call    cs:__imp_LocalFree
0x140006117  add     rsp, 20h
0x14000611b  pop     rbx
0x14000611c  retn
```
