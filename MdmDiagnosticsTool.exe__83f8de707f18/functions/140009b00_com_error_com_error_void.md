# _com_error::~_com_error(void)

- ea: `0x140009b00`
- end: `0x140009b44`
- name: `??1_com_error@@UEAA@XZ`
- size: `68`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140009b50`

## callees

- `0x140009b00`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140009b31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140009b31`

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
0x140009b00  push    rbx
0x140009b02  sub     rsp, 20h
0x140009b06  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x140009b0d  mov     rbx, rcx
0x140009b10  mov     [rcx], rax
0x140009b13  mov     rcx, [rcx+10h]
0x140009b17  test    rcx, rcx
0x140009b1a  jz      short loc_140009B28
0x140009b1c  mov     rax, [rcx]
0x140009b1f  mov     rax, [rax+10h]
0x140009b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b28  mov     rcx, [rbx+18h]; hMem
0x140009b2c  test    rcx, rcx
0x140009b2f  jz      short loc_140009B3D
0x140009b31  call    cs:__imp_LocalFree
0x140009b38  nop     dword ptr [rax+rax+00h]
0x140009b3d  add     rsp, 20h
0x140009b41  pop     rbx
0x140009b42  retn
```
