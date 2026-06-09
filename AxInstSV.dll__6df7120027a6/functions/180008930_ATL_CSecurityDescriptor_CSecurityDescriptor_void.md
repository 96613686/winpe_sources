# ATL::CSecurityDescriptor::~CSecurityDescriptor(void)

- ea: `0x180008930`
- end: `0x180008971`
- name: `??1CSecurityDescriptor@ATL@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000c5ec`

## callees

- `0x180001744`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008947`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008951`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000895b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008947`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008951`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000895b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000896a`

## pseudocode

```c
void __fastcall ATL::CSecurityDescriptor::~CSecurityDescriptor(void **this)
{
  operator delete(*this);
  free(this[1]);
  free(this[2]);
  free(this[3]);
  free(this[4]);
}

```

## disassembly

```asm
0x180008930  push    rbx
0x180008932  sub     rsp, 20h
0x180008936  mov     rbx, rcx
0x180008939  xor     edx, edx
0x18000893b  mov     rcx, [rcx]; Block
0x18000893e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008943  mov     rcx, [rbx+8]; Block
0x180008947  call    cs:__imp_free
0x18000894d  mov     rcx, [rbx+10h]; Block
0x180008951  call    cs:__imp_free
0x180008957  mov     rcx, [rbx+18h]; Block
0x18000895b  call    cs:__imp_free
0x180008961  mov     rcx, [rbx+20h]
0x180008965  add     rsp, 20h
0x180008969  pop     rbx
0x18000896a  jmp     cs:__imp_free
```
