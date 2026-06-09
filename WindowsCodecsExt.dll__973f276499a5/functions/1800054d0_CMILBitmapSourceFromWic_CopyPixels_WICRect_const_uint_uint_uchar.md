# CMILBitmapSourceFromWic::CopyPixels(WICRect const *,uint,uint,uchar *)

- ea: `0x1800054d0`
- end: `0x180005535`
- name: `?CopyPixels@CMILBitmapSourceFromWic@@UEAAJPEBUWICRect@@IIPEAE@Z`
- size: `101`
- prototype: `__int64 __fastcall(CMILBitmapSourceFromWic *__hidden this, const struct WICRect *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002c5e0`

## callees

- `0x1800054d0`
- `0x1800058c0`
- `0x1800058e0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMILBitmapSourceFromWic::CopyPixels(
        CMILBitmapSourceFromWic *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  CMTALock *v5; // r14
  unsigned int v10; // ebx

  v5 = (CMILBitmapSourceFromWic *)((char *)this - 56);
  CMTALock::Enter((CMILBitmapSourceFromWic *)((char *)this - 56));
  v10 = (*(__int64 (__fastcall **)(_QWORD, const struct WICRect *, _QWORD, _QWORD, unsigned __int8 *))(**((_QWORD **)this + 2) + 56LL))(
          *((_QWORD *)this + 2),
          a2,
          a3,
          a4,
          a5);
  if ( v5 )
    CMTALock::Leave(v5);
  return v10;
}

```

## disassembly

```asm
0x1800054d0  push    rbx
0x1800054d2  push    rbp
0x1800054d3  push    rsi
0x1800054d4  push    rdi
0x1800054d5  push    r14
0x1800054d7  sub     rsp, 30h
0x1800054db  lea     r14, [rcx-38h]
0x1800054df  mov     rbx, rcx
0x1800054e2  mov     rcx, r14; this
0x1800054e5  mov     edi, r9d
0x1800054e8  mov     esi, r8d
0x1800054eb  mov     rbp, rdx
0x1800054ee  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800054f3  mov     rcx, [rbx+10h]
0x1800054f7  mov     r9d, edi
0x1800054fa  mov     r10, [rsp+58h+arg_20]
0x180005502  mov     r8d, esi
0x180005505  mov     rdx, rbp
0x180005508  mov     [rsp+58h+var_38], r10
0x18000550d  mov     rax, [rcx]
0x180005510  mov     rax, [rax+38h]
0x180005514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005519  mov     ebx, eax
0x18000551b  test    r14, r14
0x18000551e  jz      short loc_180005528
0x180005520  mov     rcx, r14; this
0x180005523  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180005528  mov     eax, ebx
0x18000552a  add     rsp, 30h
0x18000552e  pop     r14
0x180005530  pop     rdi
0x180005531  pop     rsi
0x180005532  pop     rbp
0x180005533  pop     rbx
0x180005534  retn
```
