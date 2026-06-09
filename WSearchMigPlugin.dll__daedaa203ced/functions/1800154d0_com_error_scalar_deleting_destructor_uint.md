# _com_error::`scalar deleting destructor'(uint)

- ea: `0x1800154d0`
- end: `0x180015539`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `105`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002b9c`
- `0x1800154d0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180015511`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180015511`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  __int64 v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
    LocalFree(v5);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800154d0  push    rdi
0x1800154d2  sub     rsp, 30h
0x1800154d6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800154df  mov     [rsp+38h+arg_0], rbx
0x1800154e4  mov     edi, edx
0x1800154e6  mov     rbx, rcx
0x1800154e9  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800154f0  mov     [rcx], rax
0x1800154f3  mov     rcx, [rcx+10h]
0x1800154f7  test    rcx, rcx
0x1800154fa  jz      short loc_180015508
0x1800154fc  mov     rax, [rcx]
0x1800154ff  mov     rax, [rax+10h]
0x180015503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015508  mov     rcx, [rbx+18h]; hMem
0x18001550c  test    rcx, rcx
0x18001550f  jz      short loc_180015518
0x180015511  call    cs:__imp_LocalFree
0x180015517  nop
0x180015518  test    dil, 1
0x18001551c  jz      short loc_18001552B
0x18001551e  mov     edx, 20h ; ' '
0x180015523  mov     rcx, rbx; Block
0x180015526  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001552b  mov     rax, rbx
0x18001552e  mov     rbx, [rsp+38h+arg_0]
0x180015533  add     rsp, 30h
0x180015537  pop     rdi
0x180015538  retn
```
