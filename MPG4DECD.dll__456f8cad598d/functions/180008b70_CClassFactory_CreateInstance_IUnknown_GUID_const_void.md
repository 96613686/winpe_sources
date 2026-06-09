# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180008b70`
- end: `0x180008c5b`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `235`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008e70`

## callees

- `0x180008b70`
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
0x180008b70  mov     [rsp+arg_0], rbx
0x180008b75  mov     [rsp+arg_8], rsi
0x180008b7a  push    rdi
0x180008b7b  sub     rsp, 20h
0x180008b7f  mov     rsi, r8
0x180008b82  mov     r8, rdx
0x180008b85  mov     rdi, r9
0x180008b88  test    r9, r9
0x180008b8b  jnz     short loc_180008B97
0x180008b8d  mov     eax, 80004003h
0x180008b92  jmp     loc_180008C4B
0x180008b97  mov     qword ptr [r9], 0
0x180008b9e  test    r8, r8
0x180008ba1  jz      short loc_180008BC6
0x180008ba3  mov     rax, [rsi]
0x180008ba6  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180008bad  jnz     short loc_180008BBC
0x180008baf  mov     rax, [rsi+8]
0x180008bb3  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180008bba  jz      short loc_180008BC6
0x180008bbc  mov     eax, 80004002h
0x180008bc1  jmp     loc_180008C4B
0x180008bc6  mov     rax, [rcx+8]
0x180008bca  lea     rdx, [rsp+28h+arg_18]
0x180008bcf  mov     [rsp+28h+arg_18], 0
0x180008bd7  mov     rcx, r8
0x180008bda  mov     rax, [rax+8]
0x180008bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008be3  mov     rbx, rax
0x180008be6  test    rax, rax
0x180008be9  jnz     short loc_180008BFA
0x180008beb  mov     eax, [rsp+28h+arg_18]
0x180008bef  test    eax, eax
0x180008bf1  js      short loc_180008C4B
0x180008bf3  mov     eax, 8007000Eh
0x180008bf8  jmp     short loc_180008C4B
0x180008bfa  cmp     [rsp+28h+arg_18], 0
0x180008bff  mov     rcx, rbx
0x180008c02  mov     rax, [rax]
0x180008c05  jge     short loc_180008C17
0x180008c07  mov     rax, [rax+18h]
0x180008c0b  mov     edx, 1
0x180008c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c15  jmp     short loc_180008C47
0x180008c17  mov     rax, [rax+8]
0x180008c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c20  mov     rax, [rbx]
0x180008c23  mov     r8, rdi
0x180008c26  mov     rdx, rsi
0x180008c29  mov     rcx, rbx
0x180008c2c  mov     rax, [rax]
0x180008c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c34  mov     [rsp+28h+arg_18], eax
0x180008c38  mov     rcx, rbx
0x180008c3b  mov     rax, [rbx]
0x180008c3e  mov     rax, [rax+10h]
0x180008c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c47  mov     eax, [rsp+28h+arg_18]
0x180008c4b  mov     rbx, [rsp+28h+arg_0]
0x180008c50  mov     rsi, [rsp+28h+arg_8]
0x180008c55  add     rsp, 20h
0x180008c59  pop     rdi
0x180008c5a  retn
```
