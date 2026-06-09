# _com_error::~_com_error(void)

- ea: `0x180007f04`
- end: `0x180007f48`
- name: `??1_com_error@@UEAA@XZ`
- size: `68`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007f50`

## callees

- `0x180007f04`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f35`

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
0x180007f04  push    rbx
0x180007f06  sub     rsp, 20h
0x180007f0a  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180007f11  mov     rbx, rcx
0x180007f14  mov     [rcx], rax
0x180007f17  mov     rcx, [rcx+10h]
0x180007f1b  test    rcx, rcx
0x180007f1e  jz      short loc_180007F2C
0x180007f20  mov     rax, [rcx]
0x180007f23  mov     rax, [rax+10h]
0x180007f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2c  mov     rcx, [rbx+18h]; hMem
0x180007f30  test    rcx, rcx
0x180007f33  jz      short loc_180007F41
0x180007f35  call    cs:__imp_LocalFree
0x180007f3c  nop     dword ptr [rax+rax+00h]
0x180007f41  add     rsp, 20h
0x180007f45  pop     rbx
0x180007f46  retn
```
