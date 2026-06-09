# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180007150`
- end: `0x1800071cc`
- name: `?CreateInstance@CClassFactory@@EEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `124`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000312c`
- `0x180007150`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v7; // ebx
  struct IUnknown *v8; // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v8 = 0;
  v7 = CNetworkItemFactory_CreateInstance(&v8);
  if ( v7 >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, void **))v8->lpVtbl->QueryInterface)(
           v8,
           a3,
           a4);
    ((void (__fastcall *)(struct IUnknown *))v8->lpVtbl->Release)(v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007150  mov     [rsp+arg_0], rbx
0x180007155  mov     [rsp+arg_10], rsi
0x18000715a  push    rdi
0x18000715b  sub     rsp, 20h
0x18000715f  mov     qword ptr [r9], 0
0x180007166  mov     rdi, r9
0x180007169  mov     rsi, r8
0x18000716c  test    rdx, rdx
0x18000716f  jz      short loc_180007178
0x180007171  mov     eax, 80040110h
0x180007176  jmp     short loc_1800071BC
0x180007178  lea     rcx, [rsp+28h+arg_8]; struct IUnknown **
0x18000717d  mov     [rsp+28h+arg_8], 0
0x180007186  call    ?CNetworkItemFactory_CreateInstance@@YAJPEAPEAUIUnknown@@@Z; CNetworkItemFactory_CreateInstance(IUnknown * *)
0x18000718b  mov     ebx, eax
0x18000718d  test    eax, eax
0x18000718f  js      short loc_1800071BA
0x180007191  mov     rcx, [rsp+28h+arg_8]
0x180007196  mov     r8, rdi
0x180007199  mov     rdx, rsi
0x18000719c  mov     rax, [rcx]
0x18000719f  mov     rax, [rax]
0x1800071a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a7  mov     rcx, [rsp+28h+arg_8]
0x1800071ac  mov     ebx, eax
0x1800071ae  mov     rax, [rcx]
0x1800071b1  mov     rax, [rax+10h]
0x1800071b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ba  mov     eax, ebx
0x1800071bc  mov     rbx, [rsp+28h+arg_0]
0x1800071c1  mov     rsi, [rsp+28h+arg_10]
0x1800071c6  add     rsp, 20h
0x1800071ca  pop     rdi
0x1800071cb  retn
```
