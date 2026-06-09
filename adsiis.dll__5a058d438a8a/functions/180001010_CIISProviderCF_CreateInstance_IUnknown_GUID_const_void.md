# CIISProviderCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001010`
- end: `0x1800010aa`
- name: `?CreateInstance@CIISProviderCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(CIISProviderCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001010`
- `0x180001ad0`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CIISProviderCF::CreateInstance(
        CIISProviderCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  struct CIISProvider *v7; // rsi
  unsigned int v8; // ebx
  struct CIISProvider *v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147500037LL;
  result = CIISProvider::Create(&v9);
  if ( (int)result >= 0 )
  {
    v7 = v9;
    if ( v9 )
    {
      v8 = (**(__int64 (__fastcall ***)(struct CIISProvider *, const struct _GUID *, void **))v9)(v9, a3, a4);
      (*(void (__fastcall **)(struct CIISProvider *))(*(_QWORD *)v7 + 16LL))(v7);
      return v8;
    }
    else
    {
      *a4 = 0;
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_8], rbx
0x180001015  push    rdi
0x180001016  sub     rsp, 20h
0x18000101a  mov     [rsp+28h+arg_18], 0
0x180001023  mov     rbx, r9
0x180001026  mov     rdi, r8
0x180001029  test    r9, r9
0x18000102c  jnz     short loc_180001035
0x18000102e  mov     eax, 80004003h
0x180001033  jmp     short loc_18000109F
0x180001035  mov     qword ptr [r9], 0
0x18000103c  test    rdx, rdx
0x18000103f  jz      short loc_180001048
0x180001041  mov     eax, 80004005h
0x180001046  jmp     short loc_18000109F
0x180001048  lea     rcx, [rsp+28h+arg_18]; struct CIISProvider **
0x18000104d  call    ?Create@CIISProvider@@SAJPEAPEAV1@@Z; CIISProvider::Create(CIISProvider * *)
0x180001052  test    eax, eax
0x180001054  js      short loc_18000109F
0x180001056  mov     [rsp+28h+arg_0], rsi
0x18000105b  mov     rsi, [rsp+28h+arg_18]
0x180001060  test    rsi, rsi
0x180001063  jz      short loc_18000108E
0x180001065  mov     rax, [rsi]
0x180001068  mov     r8, rbx
0x18000106b  mov     rdx, rdi
0x18000106e  mov     rcx, rsi
0x180001071  mov     rax, [rax]
0x180001074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001079  mov     rdx, [rsi]
0x18000107c  mov     ebx, eax
0x18000107e  mov     rcx, rsi
0x180001081  mov     rax, [rdx+10h]
0x180001085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000108a  mov     eax, ebx
0x18000108c  jmp     short loc_18000109A
0x18000108e  mov     qword ptr [rbx], 0
0x180001095  mov     eax, 8007000Eh
0x18000109a  mov     rsi, [rsp+28h+arg_0]
0x18000109f  mov     rbx, [rsp+28h+arg_8]
0x1800010a4  add     rsp, 20h
0x1800010a8  pop     rdi
0x1800010a9  retn
```
