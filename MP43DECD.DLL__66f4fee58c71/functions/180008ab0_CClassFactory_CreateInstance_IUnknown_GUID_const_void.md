# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180008ab0`
- end: `0x180008b9b`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `235`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008db0`

## callees

- `0x180008ab0`
- `0x180022010`

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
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // rcx
  __int64 v11; // rax
  int v12; // [rsp+48h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2
    && (*(_QWORD *)&a3->Data1 != *(_QWORD *)&IID_IUnknown.Data1 || *(_QWORD *)a3->Data4 != *(_QWORD *)IID_IUnknown.Data4) )
  {
    return 2147500034LL;
  }
  v7 = *((_QWORD *)this + 1);
  v12 = 0;
  v8 = (_QWORD *)(*(__int64 (__fastcall **)(struct IUnknown *, int *))(v7 + 8))(a2, &v12);
  v9 = v8;
  if ( v8 )
  {
    v10 = v8;
    v11 = *v8;
    if ( v12 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(v11 + 8))(v10);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v9)(v9, a3, a4);
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(v11 + 24))(v10, 1);
    }
    return (unsigned int)v12;
  }
  else
  {
    result = (unsigned int)v12;
    if ( v12 >= 0 )
      return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008ab0  mov     [rsp+arg_0], rbx
0x180008ab5  mov     [rsp+arg_8], rsi
0x180008aba  push    rdi
0x180008abb  sub     rsp, 20h
0x180008abf  mov     rsi, r8
0x180008ac2  mov     r8, rdx
0x180008ac5  mov     rdi, r9
0x180008ac8  test    r9, r9
0x180008acb  jnz     short loc_180008AD7
0x180008acd  mov     eax, 80004003h
0x180008ad2  jmp     loc_180008B8B
0x180008ad7  mov     qword ptr [r9], 0
0x180008ade  test    r8, r8
0x180008ae1  jz      short loc_180008B06
0x180008ae3  mov     rax, [rsi]
0x180008ae6  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180008aed  jnz     short loc_180008AFC
0x180008aef  mov     rax, [rsi+8]
0x180008af3  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180008afa  jz      short loc_180008B06
0x180008afc  mov     eax, 80004002h
0x180008b01  jmp     loc_180008B8B
0x180008b06  mov     rax, [rcx+8]
0x180008b0a  lea     rdx, [rsp+28h+arg_18]
0x180008b0f  mov     [rsp+28h+arg_18], 0
0x180008b17  mov     rcx, r8
0x180008b1a  mov     rax, [rax+8]
0x180008b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b23  mov     rbx, rax
0x180008b26  test    rax, rax
0x180008b29  jnz     short loc_180008B3A
0x180008b2b  mov     eax, [rsp+28h+arg_18]
0x180008b2f  test    eax, eax
0x180008b31  js      short loc_180008B8B
0x180008b33  mov     eax, 8007000Eh
0x180008b38  jmp     short loc_180008B8B
0x180008b3a  cmp     [rsp+28h+arg_18], 0
0x180008b3f  mov     rcx, rbx
0x180008b42  mov     rax, [rax]
0x180008b45  jge     short loc_180008B57
0x180008b47  mov     rax, [rax+18h]
0x180008b4b  mov     edx, 1
0x180008b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b55  jmp     short loc_180008B87
0x180008b57  mov     rax, [rax+8]
0x180008b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b60  mov     rax, [rbx]
0x180008b63  mov     r8, rdi
0x180008b66  mov     rdx, rsi
0x180008b69  mov     rcx, rbx
0x180008b6c  mov     rax, [rax]
0x180008b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b74  mov     [rsp+28h+arg_18], eax
0x180008b78  mov     rcx, rbx
0x180008b7b  mov     rax, [rbx]
0x180008b7e  mov     rax, [rax+10h]
0x180008b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b87  mov     eax, [rsp+28h+arg_18]
0x180008b8b  mov     rbx, [rsp+28h+arg_0]
0x180008b90  mov     rsi, [rsp+28h+arg_8]
0x180008b95  add     rsp, 20h
0x180008b99  pop     rdi
0x180008b9a  retn
```
