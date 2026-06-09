# CClassFactory_CreateInstance(long (*)(_GUID const &,void * *),_GUID const &,void * *)

- ea: `0x180003224`
- end: `0x1800032a3`
- name: `?CClassFactory_CreateInstance@@YAJP6AJAEBU_GUID@@PEAPEAX@Z01@Z`
- size: `127`
- prototype: `__int64 __fastcall(int (*)(const struct _GUID *, void **), const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003fd0`

## callees

- `0x180001a04`
- `0x1800031e8`
- `0x180003224`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CClassFactory_CreateInstance(
        int (*a1)(const struct _GUID *, void **),
        const struct _GUID *a2,
        void **a3)
{
  CClassFactory *v6; // rax
  CClassFactory *v7; // rax
  CClassFactory *v8; // rdi
  unsigned int v9; // ebx

  *a3 = 0;
  v6 = (CClassFactory *)operator new(0x18u);
  if ( v6 && (v7 = CClassFactory::CClassFactory(v6, a1), (v8 = v7) != 0) )
  {
    v9 = (**(__int64 (__fastcall ***)(CClassFactory *, const struct _GUID *, void **))v7)(v7, a2, a3);
    (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x180003224  mov     [rsp+arg_0], rbx
0x180003229  mov     [rsp+arg_8], rsi
0x18000322e  push    rdi
0x18000322f  sub     rsp, 20h
0x180003233  mov     rdi, rcx
0x180003236  mov     qword ptr [r8], 0
0x18000323d  mov     ecx, 18h; Size
0x180003242  mov     rbx, r8
0x180003245  mov     rsi, rdx
0x180003248  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000324d  test    rax, rax
0x180003250  jz      short loc_18000328C
0x180003252  mov     rdx, rdi; int (*)(const struct _GUID *, void **)
0x180003255  mov     rcx, rax; this
0x180003258  call    ??0CClassFactory@@QEAA@P6AJAEBU_GUID@@PEAPEAX@Z@Z; CClassFactory::CClassFactory(long (*)(_GUID const &,void * *))
0x18000325d  mov     rdi, rax
0x180003260  test    rax, rax
0x180003263  jz      short loc_18000328C
0x180003265  mov     rcx, [rax]
0x180003268  mov     r8, rbx
0x18000326b  mov     rdx, rsi
0x18000326e  mov     rax, [rcx]
0x180003271  mov     rcx, rdi
0x180003274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003279  mov     rcx, [rdi]
0x18000327c  mov     ebx, eax
0x18000327e  mov     rax, [rcx+10h]
0x180003282  mov     rcx, rdi
0x180003285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328a  jmp     short loc_180003291
0x18000328c  mov     ebx, 8007000Eh
0x180003291  mov     rsi, [rsp+28h+arg_8]
0x180003296  mov     eax, ebx
0x180003298  mov     rbx, [rsp+28h+arg_0]
0x18000329d  add     rsp, 20h
0x1800032a1  pop     rdi
0x1800032a2  retn
```
