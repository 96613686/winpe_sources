# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180008f60`
- end: `0x18000904e`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `238`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006c3b0`

## callees

- `0x180008f60`
- `0x180085010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  _QWORD *v11; // rcx
  __int64 v12; // rax
  int v13; // [rsp+48h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
  {
    v7 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v7 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v7 )
      return 2147500034LL;
  }
  v8 = *((_QWORD *)this + 1);
  v13 = 0;
  v9 = (_QWORD *)(*(__int64 (__fastcall **)(struct IUnknown *, int *))(v8 + 8))(a2, &v13);
  v10 = v9;
  if ( v9 )
  {
    v11 = v9;
    v12 = *v9;
    if ( v13 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(v12 + 8))(v11);
      v13 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v10)(v10, a3, a4);
      (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(v12 + 24))(v11, 1);
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
0x180008f60  mov     [rsp+arg_0], rbx
0x180008f65  mov     [rsp+arg_8], rsi
0x180008f6a  push    rdi
0x180008f6b  sub     rsp, 20h
0x180008f6f  mov     rsi, r8
0x180008f72  mov     r8, rdx
0x180008f75  mov     rdi, r9
0x180008f78  test    r9, r9
0x180008f7b  jnz     short loc_180008F87
0x180008f7d  mov     eax, 80004003h
0x180008f82  jmp     loc_18000903E
0x180008f87  mov     qword ptr [r9], 0
0x180008f8e  test    r8, r8
0x180008f91  jz      short loc_180008FB9
0x180008f93  mov     rax, [rsi]
0x180008f96  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180008f9d  jnz     short loc_180008FAA
0x180008f9f  mov     rax, [rsi+8]
0x180008fa3  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180008faa  test    rax, rax
0x180008fad  jz      short loc_180008FB9
0x180008faf  mov     eax, 80004002h
0x180008fb4  jmp     loc_18000903E
0x180008fb9  mov     rax, [rcx+8]
0x180008fbd  lea     rdx, [rsp+28h+arg_18]
0x180008fc2  mov     [rsp+28h+arg_18], 0
0x180008fca  mov     rcx, r8
0x180008fcd  mov     rax, [rax+8]
0x180008fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fd6  mov     rbx, rax
0x180008fd9  test    rax, rax
0x180008fdc  jnz     short loc_180008FED
0x180008fde  mov     eax, [rsp+28h+arg_18]
0x180008fe2  test    eax, eax
0x180008fe4  js      short loc_18000903E
0x180008fe6  mov     eax, 8007000Eh
0x180008feb  jmp     short loc_18000903E
0x180008fed  cmp     [rsp+28h+arg_18], 0
0x180008ff2  mov     rcx, rbx
0x180008ff5  mov     rax, [rax]
0x180008ff8  jge     short loc_18000900A
0x180008ffa  mov     rax, [rax+18h]
0x180008ffe  mov     edx, 1
0x180009003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009008  jmp     short loc_18000903A
0x18000900a  mov     rax, [rax+8]
0x18000900e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009013  mov     rax, [rbx]
0x180009016  mov     r8, rdi
0x180009019  mov     rdx, rsi
0x18000901c  mov     rcx, rbx
0x18000901f  mov     rax, [rax]
0x180009022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009027  mov     [rsp+28h+arg_18], eax
0x18000902b  mov     rcx, rbx
0x18000902e  mov     rax, [rbx]
0x180009031  mov     rax, [rax+10h]
0x180009035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000903a  mov     eax, [rsp+28h+arg_18]
0x18000903e  mov     rbx, [rsp+28h+arg_0]
0x180009043  mov     rsi, [rsp+28h+arg_8]
0x180009048  add     rsp, 20h
0x18000904c  pop     rdi
0x18000904d  retn
```
