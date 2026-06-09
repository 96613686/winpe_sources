# ATL::CDacl::`vector deleting destructor'(uint)

- ea: `0x140012800`
- end: `0x140012834`
- name: `??_ECDacl@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `ATL::CDacl *__fastcall(ATL::CDacl *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140012710`
- `0x140012800`
- `0x14001382c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ATL::CDacl *__fastcall ATL::CDacl::`vector deleting destructor'(ATL::CDacl *this, char a2)
{
  ATL::CDacl::~CDacl(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140012800  mov     [rsp+arg_0], rbx
0x140012805  push    rdi
0x140012806  sub     rsp, 20h
0x14001280a  mov     ebx, edx
0x14001280c  mov     rdi, rcx
0x14001280f  call    ??1CDacl@ATL@@UEAA@XZ
0x140012814  test    bl, 1
0x140012817  jz      short loc_140012826
0x140012819  mov     edx, 38h ; '8'
0x14001281e  mov     rcx, rdi; Block
0x140012821  call    ??3@YAXPEAX_K@Z
0x140012826  mov     rbx, [rsp+28h+arg_0]
0x14001282b  mov     rax, rdi
0x14001282e  add     rsp, 20h
0x140012832  pop     rdi
0x140012833  retn
```
