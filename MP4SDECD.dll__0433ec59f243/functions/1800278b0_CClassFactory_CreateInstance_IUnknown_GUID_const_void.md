# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800278b0`
- end: `0x18002799e`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `238`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e970`

## callees

- `0x1800278b0`
- `0x180046010`

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
0x1800278b0  mov     [rsp+arg_0], rbx
0x1800278b5  mov     [rsp+arg_8], rsi
0x1800278ba  push    rdi
0x1800278bb  sub     rsp, 20h
0x1800278bf  mov     rsi, r8
0x1800278c2  mov     r8, rdx
0x1800278c5  mov     rdi, r9
0x1800278c8  test    r9, r9
0x1800278cb  jnz     short loc_1800278D7
0x1800278cd  mov     eax, 80004003h
0x1800278d2  jmp     loc_18002798E
0x1800278d7  mov     qword ptr [r9], 0
0x1800278de  test    r8, r8
0x1800278e1  jz      short loc_180027909
0x1800278e3  mov     rax, [rsi]
0x1800278e6  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800278ed  jnz     short loc_1800278FA
0x1800278ef  mov     rax, [rsi+8]
0x1800278f3  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800278fa  test    rax, rax
0x1800278fd  jz      short loc_180027909
0x1800278ff  mov     eax, 80004002h
0x180027904  jmp     loc_18002798E
0x180027909  mov     rax, [rcx+8]
0x18002790d  lea     rdx, [rsp+28h+arg_18]
0x180027912  mov     [rsp+28h+arg_18], 0
0x18002791a  mov     rcx, r8
0x18002791d  mov     rax, [rax+8]
0x180027921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027926  mov     rbx, rax
0x180027929  test    rax, rax
0x18002792c  jnz     short loc_18002793D
0x18002792e  mov     eax, [rsp+28h+arg_18]
0x180027932  test    eax, eax
0x180027934  js      short loc_18002798E
0x180027936  mov     eax, 8007000Eh
0x18002793b  jmp     short loc_18002798E
0x18002793d  cmp     [rsp+28h+arg_18], 0
0x180027942  mov     rcx, rbx
0x180027945  mov     rax, [rax]
0x180027948  jge     short loc_18002795A
0x18002794a  mov     rax, [rax+18h]
0x18002794e  mov     edx, 1
0x180027953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027958  jmp     short loc_18002798A
0x18002795a  mov     rax, [rax+8]
0x18002795e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027963  mov     rax, [rbx]
0x180027966  mov     r8, rdi
0x180027969  mov     rdx, rsi
0x18002796c  mov     rcx, rbx
0x18002796f  mov     rax, [rax]
0x180027972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027977  mov     [rsp+28h+arg_18], eax
0x18002797b  mov     rcx, rbx
0x18002797e  mov     rax, [rbx]
0x180027981  mov     rax, [rax+10h]
0x180027985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002798a  mov     eax, [rsp+28h+arg_18]
0x18002798e  mov     rbx, [rsp+28h+arg_0]
0x180027993  mov     rsi, [rsp+28h+arg_8]
0x180027998  add     rsp, 20h
0x18002799c  pop     rdi
0x18002799d  retn
```
