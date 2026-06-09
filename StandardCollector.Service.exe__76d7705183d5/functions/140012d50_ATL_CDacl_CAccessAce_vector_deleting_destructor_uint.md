# ATL::CDacl::CAccessAce::`vector deleting destructor'(uint)

- ea: `0x140012d50`
- end: `0x140012db0`
- name: `??_ECAccessAce@CDacl@ATL@@UEAAPEAXI@Z`
- size: `96`
- prototype: `void *__fastcall(ATL::CDacl::CAccessAce *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1400093b4`
- `0x140012d50`
- `0x14001382c`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012d75`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012d75`

## pseudocode

```c
ATL::CDacl::CAccessAce *__fastcall ATL::CDacl::CAccessAce::`vector deleting destructor'(
        ATL::CDacl::CAccessAce *this,
        char a2)
{
  void *v4; // rcx

  *(_QWORD *)this = &ATL::CAcl::CAce::`vftable';
  v4 = (void *)*((_QWORD *)this + 17);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 17) = 0;
  }
  ATL::CSid::~CSid((ATL::CDacl::CAccessAce *)((char *)this + 8));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140012d50  mov     [rsp+arg_0], rbx
0x140012d55  push    rdi
0x140012d56  sub     rsp, 20h
0x140012d5a  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x140012d61  mov     rbx, rcx
0x140012d64  mov     [rcx], rax
0x140012d67  mov     edi, edx
0x140012d69  mov     rcx, [rcx+88h]; Block
0x140012d70  test    rcx, rcx
0x140012d73  jz      short loc_140012D86
0x140012d75  call    cs:__imp_free
0x140012d7b  mov     qword ptr [rbx+88h], 0
0x140012d86  lea     rcx, [rbx+8]; this
0x140012d8a  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140012d8f  test    dil, 1
0x140012d93  jz      short loc_140012DA2
0x140012d95  mov     edx, 98h
0x140012d9a  mov     rcx, rbx; Block
0x140012d9d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012da2  mov     rax, rbx
0x140012da5  mov     rbx, [rsp+28h+arg_0]
0x140012daa  add     rsp, 20h
0x140012dae  pop     rdi
0x140012daf  retn
```
