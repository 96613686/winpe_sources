# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180011bc0`
- end: `0x180011cb8`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `248`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011bc0`
- `0x180086010`

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
0x180011bc0  mov     [rsp+arg_0], rbx
0x180011bc5  mov     [rsp+arg_8], rsi
0x180011bca  push    rdi
0x180011bcb  sub     rsp, 20h
0x180011bcf  mov     rsi, r8
0x180011bd2  mov     r8, rdx
0x180011bd5  mov     rdi, r9
0x180011bd8  test    r9, r9
0x180011bdb  jz      loc_180011C92
0x180011be1  mov     qword ptr [r9], 0
0x180011be8  test    rdx, rdx
0x180011beb  jnz     short loc_180011C6B
0x180011bed  mov     rax, [rcx+8]
0x180011bf1  lea     rdx, [rsp+28h+arg_18]
0x180011bf6  mov     [rsp+28h+arg_18], 0
0x180011bfe  mov     rcx, r8
0x180011c01  mov     rax, [rax+8]
0x180011c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c0a  mov     rbx, rax
0x180011c0d  test    rax, rax
0x180011c10  jz      loc_180011C99
0x180011c16  cmp     [rsp+28h+arg_18], 0
0x180011c1b  mov     rcx, rbx
0x180011c1e  mov     rax, [rax]
0x180011c21  jl      loc_180011CA8
0x180011c27  mov     rax, [rax+8]
0x180011c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c30  mov     rax, [rbx]
0x180011c33  mov     r8, rdi
0x180011c36  mov     rdx, rsi
0x180011c39  mov     rcx, rbx
0x180011c3c  mov     rax, [rax]
0x180011c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c44  mov     [rsp+28h+arg_18], eax
0x180011c48  mov     rcx, rbx
0x180011c4b  mov     rax, [rbx]
0x180011c4e  mov     rax, [rax+10h]
0x180011c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c57  mov     eax, [rsp+28h+arg_18]
0x180011c5b  mov     rbx, [rsp+28h+arg_0]
0x180011c60  mov     rsi, [rsp+28h+arg_8]
0x180011c65  add     rsp, 20h
0x180011c69  pop     rdi
0x180011c6a  retn
0x180011c6b  mov     rax, [rsi]
0x180011c6e  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180011c75  jnz     short loc_180011C82
0x180011c77  mov     rax, [rsi+8]
0x180011c7b  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180011c82  test    rax, rax
0x180011c85  jz      loc_180011BED
0x180011c8b  mov     eax, 80004002h
0x180011c90  jmp     short loc_180011C5B
0x180011c92  mov     eax, 80004003h
0x180011c97  jmp     short loc_180011C5B
0x180011c99  mov     eax, [rsp+28h+arg_18]
0x180011c9d  test    eax, eax
0x180011c9f  js      short loc_180011C5B
0x180011ca1  mov     eax, 8007000Eh
0x180011ca6  jmp     short loc_180011C5B
0x180011ca8  mov     rax, [rax+18h]
0x180011cac  mov     edx, 1
0x180011cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb6  jmp     short loc_180011C57
```
