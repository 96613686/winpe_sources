# ATL::CAcl::CAce::`scalar deleting destructor'(uint)

- ea: `0x140012f10`
- end: `0x140012f70`
- name: `??_GCAce@CAcl@ATL@@UEAAPEAXI@Z`
- size: `96`
- prototype: `ATL::CAcl::CAce *__fastcall(ATL::CAcl::CAce *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1400093b4`
- `0x140012f10`
- `0x14001382c`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012f35`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012f35`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ATL::CAcl::CAce *__fastcall ATL::CAcl::CAce::`scalar deleting destructor'(ATL::CAcl::CAce *this, char a2)
{
  void *v4; // rcx

  *(_QWORD *)this = &ATL::CAcl::CAce::`vftable';
  v4 = (void *)*((_QWORD *)this + 17);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 17) = 0;
  }
  ATL::CSid::~CSid((ATL::CAcl::CAce *)((char *)this + 8));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140012f10  mov     [rsp+arg_0], rbx
0x140012f15  push    rdi
0x140012f16  sub     rsp, 20h
0x140012f1a  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x140012f21  mov     rbx, rcx
0x140012f24  mov     [rcx], rax
0x140012f27  mov     edi, edx
0x140012f29  mov     rcx, [rcx+88h]; Block
0x140012f30  test    rcx, rcx
0x140012f33  jz      short loc_140012F46
0x140012f35  call    cs:__imp_free
0x140012f3b  mov     qword ptr [rbx+88h], 0
0x140012f46  lea     rcx, [rbx+8]; this
0x140012f4a  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140012f4f  test    dil, 1
0x140012f53  jz      short loc_140012F62
0x140012f55  mov     edx, 90h
0x140012f5a  mov     rcx, rbx; Block
0x140012f5d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012f62  mov     rax, rbx
0x140012f65  mov     rbx, [rsp+28h+arg_0]
0x140012f6a  add     rsp, 20h
0x140012f6e  pop     rdi
0x140012f6f  retn
```
