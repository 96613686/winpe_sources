# _com_error::`scalar deleting destructor'(uint)

- ea: `0x1800105a0`
- end: `0x1800105ff`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `95`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002014`
- `0x1800105a0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800105d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800105d7`

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
0x1800105a0  mov     [rsp+arg_0], rbx
0x1800105a5  push    rdi
0x1800105a6  sub     rsp, 20h
0x1800105aa  mov     edi, edx
0x1800105ac  mov     rbx, rcx
0x1800105af  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800105b6  mov     [rcx], rax
0x1800105b9  mov     rcx, [rcx+10h]
0x1800105bd  test    rcx, rcx
0x1800105c0  jz      short loc_1800105CE
0x1800105c2  mov     rax, [rcx]
0x1800105c5  mov     rax, [rax+10h]
0x1800105c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105ce  mov     rcx, [rbx+18h]; hMem
0x1800105d2  test    rcx, rcx
0x1800105d5  jz      short loc_1800105DE
0x1800105d7  call    cs:__imp_LocalFree
0x1800105dd  nop
0x1800105de  test    dil, 1
0x1800105e2  jz      short loc_1800105F1
0x1800105e4  mov     edx, 20h ; ' '; unsigned __int64
0x1800105e9  mov     rcx, rbx; void *
0x1800105ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800105f1  mov     rax, rbx
0x1800105f4  mov     rbx, [rsp+28h+arg_0]
0x1800105f9  add     rsp, 20h
0x1800105fd  pop     rdi
0x1800105fe  retn
```
