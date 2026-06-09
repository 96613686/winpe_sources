# CALACDecMFT::~CALACDecMFT(void)

- ea: `0x180001f78`
- end: `0x180001fee`
- name: `??1CALACDecMFT@@UEAA@XZ`
- size: `118`
- prototype: `void __fastcall(CALACDecMFT *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002110`
- `0x180004120`
- `0x180004190`

## callees

- `0x180001574`
- `0x180001f78`
- `0x180001ff4`
- `0x180007674`

## pseudocode

```c
void __fastcall CALACDecMFT::~CALACDecMFT(CALACDecMFT *this)
{
  ALACDecoder *v1; // rdi
  void *v3; // rcx

  v1 = (ALACDecoder *)*((_QWORD *)this + 22);
  *(_QWORD *)this = &CALACDecMFT::`vftable';
  if ( v1 )
  {
    ALACDecoder::~ALACDecoder(v1);
    operator delete(v1);
    *((_QWORD *)this + 22) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 23);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 23) = 0;
  }
  CMFTSimpleBase::~CMFTSimpleBase(this);
}

```

## disassembly

```asm
0x180001f78  mov     [rsp+arg_0], rbx
0x180001f7d  push    rdi
0x180001f7e  sub     rsp, 20h
0x180001f82  mov     rdi, [rcx+0B0h]
0x180001f89  lea     rax, ??_7CALACDecMFT@@6B@; const CALACDecMFT::`vftable'
0x180001f90  mov     [rcx], rax
0x180001f93  mov     rbx, rcx
0x180001f96  test    rdi, rdi
0x180001f99  jz      short loc_180001FBB
0x180001f9b  mov     rcx, rdi; this
0x180001f9e  call    ??1ALACDecoder@@QEAA@XZ; ALACDecoder::~ALACDecoder(void)
0x180001fa3  mov     edx, 40h ; '@'
0x180001fa8  mov     rcx, rdi; Block
0x180001fab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001fb0  mov     qword ptr [rbx+0B0h], 0
0x180001fbb  mov     rcx, [rbx+0B8h]; Block
0x180001fc2  test    rcx, rcx
0x180001fc5  jz      short loc_180001FDC
0x180001fc7  mov     edx, 18h
0x180001fcc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001fd1  mov     qword ptr [rbx+0B8h], 0
0x180001fdc  mov     rcx, rbx; this
0x180001fdf  mov     rbx, [rsp+28h+arg_0]
0x180001fe4  add     rsp, 20h
0x180001fe8  pop     rdi
0x180001fe9  jmp     ??1CMFTSimpleBase@@UEAA@XZ; CMFTSimpleBase::~CMFTSimpleBase(void)
```
