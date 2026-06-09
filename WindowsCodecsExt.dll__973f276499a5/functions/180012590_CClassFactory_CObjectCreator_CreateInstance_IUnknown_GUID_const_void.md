# CClassFactory::CObjectCreator::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180012590`
- end: `0x180012644`
- name: `?CreateInstance@CObjectCreator@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `180`
- prototype: `__int64 __fastcall(CClassFactory::CObjectCreator *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180012590`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CObjectCreator::CreateInstance(
        CClassFactory::CObjectCreator *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  __int64 v7; // rdi
  int v8; // eax
  unsigned int v9; // ebx

  if ( a4 )
  {
    *a4 = 0;
    v6 = (*(__int64 (__fastcall **)(CClassFactory::CObjectCreator *, struct IUnknown *))(*((_QWORD *)this + 3) + 8LL))(
           this,
           a2);
    v7 = v6;
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
      v8 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v7)(v7, a3, a4);
      v9 = v8;
      if ( v8 < 0 && g_doStackCaptures )
        DoStackCapture(v8);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      return v9;
    }
    v9 = -2147024882;
  }
  else
  {
    v9 = -2147024809;
  }
  if ( g_doStackCaptures )
    DoStackCapture(v9);
  return v9;
}

```

## disassembly

```asm
0x180012590  mov     [rsp+arg_0], rbx
0x180012595  mov     [rsp+arg_8], rsi
0x18001259a  push    rdi
0x18001259b  sub     rsp, 20h
0x18001259f  mov     rbx, r9
0x1800125a2  mov     rsi, r8
0x1800125a5  test    r9, r9
0x1800125a8  jz      loc_180012634
0x1800125ae  mov     qword ptr [r9], 0
0x1800125b5  mov     rax, [rcx+18h]
0x1800125b9  mov     rax, [rax+8]
0x1800125bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125c2  mov     rdi, rax
0x1800125c5  test    rax, rax
0x1800125c8  jz      short loc_18001261D
0x1800125ca  mov     rax, [rax]
0x1800125cd  mov     rcx, rdi
0x1800125d0  mov     rax, [rax+8]
0x1800125d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125d9  mov     rax, [rdi]
0x1800125dc  mov     r8, rbx
0x1800125df  mov     rdx, rsi
0x1800125e2  mov     rcx, rdi
0x1800125e5  mov     rax, [rax]
0x1800125e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ed  mov     ebx, eax
0x1800125ef  test    eax, eax
0x1800125f1  jns     short loc_1800125FC
0x1800125f3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800125fa  jnz     short loc_18001263B
0x1800125fc  mov     rcx, [rdi]
0x1800125ff  mov     rax, [rcx+10h]
0x180012603  mov     rcx, rdi
0x180012606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001260b  mov     rsi, [rsp+28h+arg_8]
0x180012610  mov     eax, ebx
0x180012612  mov     rbx, [rsp+28h+arg_0]
0x180012617  add     rsp, 20h
0x18001261b  pop     rdi
0x18001261c  retn
0x18001261d  mov     ebx, 8007000Eh
0x180012622  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012629  jz      short loc_18001260B
0x18001262b  mov     ecx, ebx; int
0x18001262d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012632  jmp     short loc_18001260B
0x180012634  mov     ebx, 80070057h
0x180012639  jmp     short loc_180012622
0x18001263b  mov     ecx, eax; int
0x18001263d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012642  jmp     short loc_1800125FC
```
