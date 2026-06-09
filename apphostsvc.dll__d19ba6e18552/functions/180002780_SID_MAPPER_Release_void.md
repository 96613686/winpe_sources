# SID_MAPPER::Release(void)

- ea: `0x180002780`
- end: `0x1800027b9`
- name: `?Release@SID_MAPPER@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(SID_MAPPER *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x180001048`
- `0x1800022c8`
- `0x180002780`

## pseudocode

```c
__int64 __fastcall SID_MAPPER::Release(SID_MAPPER *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 5);
  if ( !v2 && this )
  {
    SID_MAPPER::~SID_MAPPER(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180002780  mov     [rsp+arg_0], rbx
0x180002785  push    rdi
0x180002786  sub     rsp, 20h
0x18000278a  mov     rbx, rcx
0x18000278d  or      edi, 0FFFFFFFFh
0x180002790  lock xadd [rcx+14h], edi
0x180002795  sub     edi, 1
0x180002798  jnz     short loc_1800027AC
0x18000279a  test    rcx, rcx
0x18000279d  jz      short loc_1800027AC
0x18000279f  call    ??1SID_MAPPER@@QEAA@XZ; SID_MAPPER::~SID_MAPPER(void)
0x1800027a4  mov     rcx, rbx; Block
0x1800027a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800027ac  mov     rbx, [rsp+28h+arg_0]
0x1800027b1  mov     eax, edi
0x1800027b3  add     rsp, 20h
0x1800027b7  pop     rdi
0x1800027b8  retn
```
