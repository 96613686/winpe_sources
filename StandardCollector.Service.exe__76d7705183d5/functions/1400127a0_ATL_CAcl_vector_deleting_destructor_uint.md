# ATL::CAcl::`vector deleting destructor'(uint)

- ea: `0x1400127a0`
- end: `0x1400127e3`
- name: `??_ECAcl@ATL@@UEAAPEAXI@Z`
- size: `67`
- prototype: `void *__fastcall(ATL::CAcl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1400127a0`
- `0x14001382c`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400127bd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400127bd`

## pseudocode

```c
void **__fastcall ATL::CAcl::`vector deleting destructor'(void **this, char a2)
{
  *this = &ATL::CAcl::`vftable';
  free(this[1]);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400127a0  mov     [rsp+arg_0], rbx
0x1400127a5  push    rdi
0x1400127a6  sub     rsp, 20h
0x1400127aa  lea     rax, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x1400127b1  mov     rdi, rcx
0x1400127b4  mov     [rcx], rax
0x1400127b7  mov     ebx, edx
0x1400127b9  mov     rcx, [rcx+8]; Block
0x1400127bd  call    cs:__imp_free
0x1400127c3  test    bl, 1
0x1400127c6  jz      short loc_1400127D5
0x1400127c8  mov     edx, 18h
0x1400127cd  mov     rcx, rdi; Block
0x1400127d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400127d5  mov     rbx, [rsp+28h+arg_0]
0x1400127da  mov     rax, rdi
0x1400127dd  add     rsp, 20h
0x1400127e1  pop     rdi
0x1400127e2  retn
```
