# CProfileCache::Release(void)

- ea: `0x180006980`
- end: `0x1800069b9`
- name: `?Release@CProfileCache@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(CProfileCache *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180006190`
- `0x180006980`
- `0x1800070f4`

## pseudocode

```c
__int64 __fastcall CProfileCache::Release(CProfileCache *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 18);
  if ( !v2 && this )
  {
    CProfileCache::~CProfileCache(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180006980  mov     [rsp+arg_0], rbx
0x180006985  push    rdi
0x180006986  sub     rsp, 20h
0x18000698a  mov     rbx, rcx
0x18000698d  or      edi, 0FFFFFFFFh
0x180006990  lock xadd [rcx+48h], edi
0x180006995  sub     edi, 1
0x180006998  jnz     short loc_1800069AC
0x18000699a  test    rcx, rcx
0x18000699d  jz      short loc_1800069AC
0x18000699f  call    ??1CProfileCache@@AEAA@XZ; CProfileCache::~CProfileCache(void)
0x1800069a4  mov     rcx, rbx; lpMem
0x1800069a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800069ac  mov     rbx, [rsp+28h+arg_0]
0x1800069b1  mov     eax, edi
0x1800069b3  add     rsp, 20h
0x1800069b7  pop     rdi
0x1800069b8  retn
```
