# CPropertyAttribute::CreatePropertyAttribute(_GUID const &,void * *)

- ea: `0x18000f8a8`
- end: `0x18000f918`
- name: `?CreatePropertyAttribute@CPropertyAttribute@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180006240`
- `0x180008a50`
- `0x18000f710`

## callees

- `0x18000f784`
- `0x18000f7ac`
- `0x18000f8a8`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CPropertyAttribute::CreatePropertyAttribute(const struct _GUID *a1, void **a2)
{
  int v4; // eax
  unsigned int v5; // edx
  CPropertyAttribute *v6; // rbx
  int v7; // edi
  CPropertyAttribute *v9; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  v4 = CPropertyAttribute::AllocatePropertyAttributeObject(&v9);
  v6 = v9;
  v7 = v4;
  if ( v4 < 0
    || (v7 = (**(__int64 (__fastcall ***)(CPropertyAttribute *, const struct _GUID *, void **))v9)(v9, a1, a2), v7 < 0) )
  {
    if ( v6 )
      CPropertyAttribute::`scalar deleting destructor'(v6, v5);
  }
  else
  {
    (*(void (__fastcall **)(CPropertyAttribute *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f8a8  push    rbx
0x18000f8aa  push    rbp
0x18000f8ab  push    rsi
0x18000f8ac  push    rdi
0x18000f8ad  sub     rsp, 28h
0x18000f8b1  mov     rbp, rcx
0x18000f8b4  mov     [rsp+48h+arg_10], 0
0x18000f8bd  lea     rcx, [rsp+48h+arg_10]; struct CPropertyAttribute **
0x18000f8c2  mov     rsi, rdx
0x18000f8c5  call    ?AllocatePropertyAttributeObject@CPropertyAttribute@@SAJPEAPEAV1@@Z; CPropertyAttribute::AllocatePropertyAttributeObject(CPropertyAttribute * *)
0x18000f8ca  mov     rbx, [rsp+48h+arg_10]
0x18000f8cf  mov     edi, eax
0x18000f8d1  test    eax, eax
0x18000f8d3  js      short loc_18000F900
0x18000f8d5  mov     rax, [rbx]
0x18000f8d8  mov     r8, rsi
0x18000f8db  mov     rdx, rbp
0x18000f8de  mov     rcx, rbx
0x18000f8e1  mov     rax, [rax]
0x18000f8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8e9  mov     edi, eax
0x18000f8eb  test    eax, eax
0x18000f8ed  js      short loc_18000F900
0x18000f8ef  mov     rax, [rbx]
0x18000f8f2  mov     rcx, rbx
0x18000f8f5  mov     rax, [rax+10h]
0x18000f8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8fe  jmp     short loc_18000F90D
0x18000f900  test    rbx, rbx
0x18000f903  jz      short loc_18000F90D
0x18000f905  mov     rcx, rbx; this
0x18000f908  call    ??_GCPropertyAttribute@@QEAAPEAXI@Z; CPropertyAttribute::`scalar deleting destructor'(uint)
0x18000f90d  mov     eax, edi
0x18000f90f  add     rsp, 28h
0x18000f913  pop     rdi
0x18000f914  pop     rsi
0x18000f915  pop     rbp
0x18000f916  pop     rbx
0x18000f917  retn
```
