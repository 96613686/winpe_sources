# _com_error::~_com_error(void)

- ea: `0x1400094d0`
- end: `0x14000950d`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140009520`

## callees

- `0x1400094d0`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140009501`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140009501`

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
0x1400094d0  push    rbx
0x1400094d2  sub     rsp, 20h
0x1400094d6  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1400094dd  mov     rbx, rcx
0x1400094e0  mov     [rcx], rax
0x1400094e3  mov     rcx, [rcx+10h]
0x1400094e7  test    rcx, rcx
0x1400094ea  jz      short loc_1400094F8
0x1400094ec  mov     rax, [rcx]
0x1400094ef  mov     rax, [rax+10h]
0x1400094f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094f8  mov     rcx, [rbx+18h]; hMem
0x1400094fc  test    rcx, rcx
0x1400094ff  jz      short loc_140009507
0x140009501  call    cs:__imp_LocalFree
0x140009507  add     rsp, 20h
0x14000950b  pop     rbx
0x14000950c  retn
```
