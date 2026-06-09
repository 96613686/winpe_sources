# _com_error::~_com_error(void)

- ea: `0x180015480`
- end: `0x1800154c7`
- name: `??1_com_error@@UEAA@XZ`
- size: `71`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015480`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800154ba`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800154ba`

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
0x180015480  push    rbx
0x180015482  sub     rsp, 30h
0x180015486  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001548f  mov     rbx, rcx
0x180015492  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180015499  mov     [rcx], rax
0x18001549c  mov     rcx, [rcx+10h]
0x1800154a0  test    rcx, rcx
0x1800154a3  jz      short loc_1800154B1
0x1800154a5  mov     rax, [rcx]
0x1800154a8  mov     rax, [rax+10h]
0x1800154ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154b1  mov     rcx, [rbx+18h]; hMem
0x1800154b5  test    rcx, rcx
0x1800154b8  jz      short loc_1800154C1
0x1800154ba  call    cs:__imp_LocalFree
0x1800154c0  nop
0x1800154c1  add     rsp, 30h
0x1800154c5  pop     rbx
0x1800154c6  retn
```
