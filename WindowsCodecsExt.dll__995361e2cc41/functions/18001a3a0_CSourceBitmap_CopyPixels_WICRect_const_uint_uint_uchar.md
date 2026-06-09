# CSourceBitmap::CopyPixels(WICRect const *,uint,uint,uchar *)

- ea: `0x18001a3a0`
- end: `0x18001a406`
- name: `?CopyPixels@CSourceBitmap@@UEAAJPEBUWICRect@@IIPEAE@Z`
- size: `102`
- prototype: `__int64 __fastcall(CSourceBitmap *__hidden this, const struct WICRect *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a190`
- `0x18002cab0`

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CSourceBitmap::CopyPixels(
        CSourceBitmap *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  CSourceBitmap *v5; // rbx
  char *v10; // [rsp+60h] [rbp+8h] BYREF

  v5 = this;
  v10 = (char *)this + 160;
  CMTALock::Enter((CSourceBitmap *)((char *)this + 160));
  LODWORD(v5) = (*(__int64 (__fastcall **)(_QWORD, const struct WICRect *, _QWORD, _QWORD, unsigned __int8 *))(**((_QWORD **)v5 + 30) + 56LL))(
                  *((_QWORD *)v5 + 30),
                  a2,
                  a3,
                  a4,
                  a5);
  CGuard<CMTALock>::~CGuard<CMTALock>(&v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a3a0  push    rbx
0x18001a3a2  push    rbp
0x18001a3a3  push    rsi
0x18001a3a4  push    rdi
0x18001a3a5  sub     rsp, 38h
0x18001a3a9  mov     rbx, rcx
0x18001a3ac  mov     edi, r9d
0x18001a3af  add     rcx, 0A0h; this
0x18001a3b6  mov     esi, r8d
0x18001a3b9  mov     [rsp+58h+arg_0], rcx
0x18001a3be  mov     rbp, rdx
0x18001a3c1  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18001a3c6  mov     rcx, [rbx+0F0h]
0x18001a3cd  mov     r9d, edi
0x18001a3d0  mov     r10, [rsp+58h+arg_20]
0x18001a3d8  mov     r8d, esi
0x18001a3db  mov     rdx, rbp
0x18001a3de  mov     [rsp+58h+var_38], r10
0x18001a3e3  mov     rax, [rcx]
0x18001a3e6  mov     rax, [rax+38h]
0x18001a3ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3ef  lea     rcx, [rsp+58h+arg_0]
0x18001a3f4  mov     ebx, eax
0x18001a3f6  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18001a3fb  mov     eax, ebx
0x18001a3fd  add     rsp, 38h
0x18001a401  pop     rdi
0x18001a402  pop     rsi
0x18001a403  pop     rbp
0x18001a404  pop     rbx
0x18001a405  retn
```
