# _com_error::~_com_error(void)

- ea: `0x18001c6c8`
- end: `0x18001c70d`
- name: `??1_com_error@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c720`

## callees

- `0x18001c6c8`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6f9`

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
0x18001c6c8  push    rbx
0x18001c6ca  sub     rsp, 20h
0x18001c6ce  mov     rbx, rcx
0x18001c6d1  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001c6d8  mov     [rcx], rax
0x18001c6db  mov     rcx, [rcx+10h]
0x18001c6df  test    rcx, rcx
0x18001c6e2  jz      short loc_18001C6F0
0x18001c6e4  mov     rax, [rcx]
0x18001c6e7  mov     rax, [rax+10h]
0x18001c6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6f0  mov     rcx, [rbx+18h]; hMem
0x18001c6f4  test    rcx, rcx
0x18001c6f7  jz      short loc_18001C706
0x18001c6f9  call    cs:__imp_LocalFree
0x18001c700  nop     dword ptr [rax+rax+00h]
0x18001c705  nop
0x18001c706  add     rsp, 20h
0x18001c70a  pop     rbx
0x18001c70b  retn
```
