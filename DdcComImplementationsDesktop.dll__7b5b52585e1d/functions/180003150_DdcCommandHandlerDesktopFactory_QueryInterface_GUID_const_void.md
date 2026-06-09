# DdcCommandHandlerDesktopFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x180003150`
- end: `0x1800031b6`
- name: `?QueryInterface@DdcCommandHandlerDesktopFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(DdcCommandHandlerDesktopFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003150`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall DdcCommandHandlerDesktopFactory::QueryInterface(
        DdcCommandHandlerDesktopFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IClassFactory.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IClassFactory.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(DdcCommandHandlerDesktopFactory *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180003150  sub     rsp, 28h
0x180003154  test    r8, r8
0x180003157  jnz     short loc_180003160
0x180003159  mov     eax, 80070057h
0x18000315e  jmp     short loc_1800031B1
0x180003160  mov     rax, [rdx]
0x180003163  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000316a  jnz     short loc_180003179
0x18000316c  mov     rax, [rdx+8]
0x180003170  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180003177  jz      short loc_180003192
0x180003179  mov     rax, [rdx]
0x18000317c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180003183  jnz     short loc_1800031A5
0x180003185  mov     rax, [rdx+8]
0x180003189  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180003190  jnz     short loc_1800031A5
0x180003192  mov     [r8], rcx
0x180003195  mov     rax, [rcx]
0x180003198  mov     rax, [rax+8]
0x18000319c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a1  xor     eax, eax
0x1800031a3  jmp     short loc_1800031B1
0x1800031a5  mov     qword ptr [r8], 0
0x1800031ac  mov     eax, 80004002h
0x1800031b1  add     rsp, 28h
0x1800031b5  retn
```
