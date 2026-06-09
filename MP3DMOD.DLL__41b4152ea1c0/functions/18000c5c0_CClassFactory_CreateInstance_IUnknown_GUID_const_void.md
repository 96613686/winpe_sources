# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000c5c0`
- end: `0x18000c6b8`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `248`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010130`

## callees

- `0x18000c5c0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v9; // rcx
  __int64 v10; // rax
  __int64 result; // rax
  __int64 v12; // rax
  int v13; // [rsp+48h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
  {
    v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v12 )
      return 2147500034LL;
  }
  v6 = *((_QWORD *)this + 1);
  v13 = 0;
  v7 = (_QWORD *)(*(__int64 (__fastcall **)(struct IUnknown *, int *))(v6 + 8))(a2, &v13);
  v8 = v7;
  if ( v7 )
  {
    v9 = v7;
    v10 = *v7;
    if ( v13 < 0 )
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(v10 + 24))(v9, 1);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *))(v10 + 8))(v9);
      v13 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v8)(v8, a3, a4);
      (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
    }
    return (unsigned int)v13;
  }
  else
  {
    result = (unsigned int)v13;
    if ( v13 >= 0 )
      return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000c5c0  mov     [rsp+arg_0], rbx
0x18000c5c5  mov     [rsp+arg_8], rsi
0x18000c5ca  push    rdi
0x18000c5cb  sub     rsp, 20h
0x18000c5cf  mov     rsi, r8
0x18000c5d2  mov     r8, rdx
0x18000c5d5  mov     rdi, r9
0x18000c5d8  test    r9, r9
0x18000c5db  jz      loc_18000C692
0x18000c5e1  mov     qword ptr [r9], 0
0x18000c5e8  test    rdx, rdx
0x18000c5eb  jnz     short loc_18000C66B
0x18000c5ed  mov     rax, [rcx+8]
0x18000c5f1  lea     rdx, [rsp+28h+arg_18]
0x18000c5f6  mov     [rsp+28h+arg_18], 0
0x18000c5fe  mov     rcx, r8
0x18000c601  mov     rax, [rax+8]
0x18000c605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c60a  mov     rbx, rax
0x18000c60d  test    rax, rax
0x18000c610  jz      loc_18000C699
0x18000c616  cmp     [rsp+28h+arg_18], 0
0x18000c61b  mov     rcx, rbx
0x18000c61e  mov     rax, [rax]
0x18000c621  jl      loc_18000C6A8
0x18000c627  mov     rax, [rax+8]
0x18000c62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c630  mov     rax, [rbx]
0x18000c633  mov     r8, rdi
0x18000c636  mov     rdx, rsi
0x18000c639  mov     rcx, rbx
0x18000c63c  mov     rax, [rax]
0x18000c63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c644  mov     [rsp+28h+arg_18], eax
0x18000c648  mov     rcx, rbx
0x18000c64b  mov     rax, [rbx]
0x18000c64e  mov     rax, [rax+10h]
0x18000c652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c657  mov     eax, [rsp+28h+arg_18]
0x18000c65b  mov     rbx, [rsp+28h+arg_0]
0x18000c660  mov     rsi, [rsp+28h+arg_8]
0x18000c665  add     rsp, 20h
0x18000c669  pop     rdi
0x18000c66a  retn
0x18000c66b  mov     rax, [rsi]
0x18000c66e  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c675  jnz     short loc_18000C682
0x18000c677  mov     rax, [rsi+8]
0x18000c67b  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c682  test    rax, rax
0x18000c685  jz      loc_18000C5ED
0x18000c68b  mov     eax, 80004002h
0x18000c690  jmp     short loc_18000C65B
0x18000c692  mov     eax, 80004003h
0x18000c697  jmp     short loc_18000C65B
0x18000c699  mov     eax, [rsp+28h+arg_18]
0x18000c69d  test    eax, eax
0x18000c69f  js      short loc_18000C65B
0x18000c6a1  mov     eax, 8007000Eh
0x18000c6a6  jmp     short loc_18000C65B
0x18000c6a8  mov     rax, [rax+18h]
0x18000c6ac  mov     edx, 1
0x18000c6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6b6  jmp     short loc_18000C657
```
