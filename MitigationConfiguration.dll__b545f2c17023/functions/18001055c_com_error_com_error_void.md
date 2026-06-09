# _com_error::~_com_error(void)

- ea: `0x18001055c`
- end: `0x18001059a`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001055c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001058d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001058d`

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
0x18001055c  push    rbx
0x18001055e  sub     rsp, 20h
0x180010562  mov     rbx, rcx
0x180010565  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001056c  mov     [rcx], rax
0x18001056f  mov     rcx, [rcx+10h]
0x180010573  test    rcx, rcx
0x180010576  jz      short loc_180010584
0x180010578  mov     rax, [rcx]
0x18001057b  mov     rax, [rax+10h]
0x18001057f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010584  mov     rcx, [rbx+18h]; hMem
0x180010588  test    rcx, rcx
0x18001058b  jz      short loc_180010594
0x18001058d  call    cs:__imp_LocalFree
0x180010593  nop
0x180010594  add     rsp, 20h
0x180010598  pop     rbx
0x180010599  retn
```
